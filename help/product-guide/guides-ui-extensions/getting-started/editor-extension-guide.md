---
title: Änderungen am Erweiterungs-Framework für Editor 2.0
description: Erfahren Sie mehr über die Änderungen im Erweiterungs-Framework für Editor 2.0
feature: Web Editor Configuration
role: Admin
level: Experienced
source-git-commit: 2ba8eadcb30faca01170cb13ae2da6fdf7da19c8
workflow-type: tm+mt
source-wordcount: '2003'
ht-degree: 4%

---

# Änderungen am Erweiterungs-Framework für Editor 2.0 (neuer Editor)

In diesem Dokument werden alle APIs behandelt, die `guides.editor` (und `guides`) als Teil des Erweiterungs-Frameworks für den neuen Editor (ProseMirror-basierter Editor) hinzugefügt wurden. Diese APIs ermöglichen es externen Erweiterungen, ohne direkte DOM-Manipulation oder internes Implementierungswissen mit dem Editor zu interagieren.

## Überblick

Das globale `guides` ist der Einstiegspunkt für alle Erweiterungsintegrationen:

```js
guides.editor    // Editor interaction APIs
guides.util      // Utility libraries (lodash, async)
guides.ready(cb) // Lifecycle hook fires when the editor is fully loaded
```

Alle `guides.editor` APIs können sicher über Erweiterungscontroller, Symbolleisten-Handler und Dialogfeldlogik aufgerufen werden.

## Lebenszyklus

`guides.ready(callback)`: Registriert einen Callback, der ausgeführt werden soll, sobald der Seitenansichts-Manager vollständig geladen wurde. Verwenden Sie dies, bevor Sie Plug-ins registrieren oder ein Editor-Setup durchführen.

**Signatur:**

```ts
guides.ready(callback: () => void): void
```

**Beispiel:**

```js
guides.ready(() => {
  // Safe to access guides.editor APIs here
  guides.editor.registerPlugin(createMyPlugin);
});
```

## Editor-Statuseigenschaften

- `guides.editor.filePath`: Gibt den Dateipfad des aktuell aktiven Dokuments aus.

  **Typ:** `string | undefined`

  **Beispiel: Lesen des Dateipfads für einen Metadaten-API-Aufruf:**

  ```js
  const filePath = guides.editor.filePath;
  if (filePath) {
  tcx.api.getMetadata(filePath).subscribe((metadata) => {
    // use metadata...
    });
  }
  ```

  **Beispiel: Bedingte Logik basierend auf dem Dateispeicherort**

  ```js
  const filePath = guides.editor.filePath;
  if (filePath?.endsWith(".ditamap")) {
    // ditamap-specific handling
  }
  ```

- `guides.editor.version`: Gibt die Versionszeichenfolge des aktuell geladenen Editors zurück.

  | Wert | Editor |
  |---------|------------------------------------|
  | `1.0.0` | Legacy-CKEditor (`xml_author_view`) |
  | `2.0.0` | Neuer Editor (ProseMirror-basiert) |

  **Typ:** `string`

  **Beispiel:**

  ```js
  if (guides.editor.version  === '1.0.0') {
    // CKEditor specific logic 
  }
  ```

- `guides.editor.appState(keyName)`: Liest einen Wert aus dem Anwendungsmodell anhand des Schlüsselnamens.

  **Signatur:**

  ```ts
  guides.editor.appState(keyName: string): unknown
  ```

  **Beispiel:**

  ```js
  const editorMode = guides.editor.appState('editorMode');
  ```

## Editor-Interaktion

- `guides.editor.focus()`: Setzt den Fokus auf den aktiven Editor. Rufen Sie dies auf, bevor Sie Befehle ausführen, für die der Editor den Fokus haben muss.

  **Signatur:**

  ```ts
  guides.editor.focus(): boolean
  ```

  **Beispiel: Fokus vor dem Einfügen von Inhalten**

  ```js
  guides.editor.focus();
  const hasSelection = !!guides.editor.runUtil('hasSelection');
  // ...proceed with wrap or insert
  ```

- `guides.editor.canInsertXmlElement(tagName, insertAfter?)`: Prüft, ob ein XML-Element an der aktuellen Cursorposition eingefügt werden kann.

  **Signatur:**

  ```ts
  guides.editor.canInsertXmlElement(tagName: string, insertAfter?: boolean): boolean
  ```

  **Beispiel: Vor dem Einfügen von`<xref>`** schützen

  ```js
  const canInsert = guides.editor.canInsertXmlElement("xref");
  if (!canInsert) {
    return tcx.util.showAlert("warning", "xref is not allowed here");
  }
  ```

  **Beispiel: Vor dem Einfügen von `<sup>` /`<sub>`** schützen

  ```js
  const canInsert = guides.editor.canInsertXmlElement("sup");
  if (!canInsert) {
    return tcx.util.showAlert("warning", "superscript is not allowed here");
  }
  ```

- `guides.editor.selectCurrentBlockElement()`: Wählt das aktuelle Element der Blockebene im Editor aus.

  **Signatur:**

  ```ts
  guides.editor.selectCurrentBlockElement(): boolean
  ```

  **Beispiel:**

  ```js
  guides.editor.selectCurrentBlockElement();
  ```

- `guides.editor.getValidElementNamesForInsertion(args)`: Gibt eine Liste gültiger XML-Elementnamen zurück, die an der aktuellen Position eingefügt werden können.

  **Signatur:**

  ```ts
  guides.editor.getValidElementNamesForInsertion(args: {
    insertMode?: 'after' | 'before' | 'rename',
    strict: boolean
  }): string[] | false
  ```

  **Beispiel:**

  ```js
  const validElements = guides.editor.getValidElementNamesForInsertion({
    insertMode: 'after',
    strict: true
  });
  ```

- `guides.editor.updateAttributeByXpath(args)`: Aktualisiert ein bestimmtes XML-Attribut auf einem Knoten, der durch seinen XPath identifiziert wird. Delegiert an die `updateAttributeByXpath`-Methode des aktiven Editors.

  **Signatur:**

  ```ts
  guides.editor.updateAttributeByXpath(args: UpdateXpathArgs): any
  ```

## Befehlsausführung

- `guides.editor.runCommand(commandName, ...args)`: Führt einen benannten Befehl im neuen Editor aus. Gibt `true` zurück, wenn der Befehl erfolgreich ausgeführt wurde, andernfalls `false`.

  **Signatur:**

  ```ts
  guides.editor.runCommand(commandName: string, ...args: any[]): boolean
  ```

  **Verfügbare Befehle**

  >[!NOTE]
  >
  > Stabilität: Die unten aufgeführten Befehle sind Teil der öffentlichen Oberfläche. Ihre Namen, Signaturen und beobachtbaren Verhaltensweisen werden als stabil betrachtet und aus Kompatibilitätsgründen beibehalten. Im Editor können zusätzliche Befehle vorhanden sein. Diese sind jedoch intern, nicht für die externe Verwendung vorgesehen und können ohne vorherige Ankündigung geändert oder entfernt werden.

  | Kategorie | Befehl | Argumente | Beschreibung |
  |---|---|---|---|
  | Allgemein | `undo` | _(keine)_ | Macht die letzte Dokumentänderung rückgängig |
  | Allgemein | `redo` | _(keine)_ | Stellt die letzte rückgängig gemachte Änderung wieder her |
  | Auswahl | `select` | `from: number, to?: number` | Wählt den Bereich von `from` bis `to` aus (oder `from`, wenn `to` weggelassen wird) |
  | Auswahl | `cursor` | `pos: number` | Bewegt den Cursor nach `pos` |
  | Auswahl | `selectNodesFromXpaths` | `xpaths: Array<{path: Array<{name: string, count: number}>}>` | Wählt Knoten aus, die durch XPath-Positionen identifiziert werden |
  | Formatierung | `toggleBold` | _(keine)_ | Schaltet die Fettformatierung der aktuellen Auswahl ein oder aus |
  | Formatierung | `toggleItalic` | _(keine)_ | Blendet die aktuelle Auswahl ein oder aus |
  | Formatierung | `toggleUnderline` | _(keine)_ | Schaltet die Unterstrichformatierung der aktuellen Auswahl ein oder aus |
  | Formatierung | `toggleFormatting` | `markType: string, allowEmptySelection?: boolean` | Blendet ein Formatierungselement (z. B. `'b'`, `'i'`, `'sup'`, `'sub'`) in der Auswahl ein oder aus. |
  | Einfügen | `insertText` | `text: string` | Fügt Text am Cursor ein |
  | Einfügen | `insertXml` | `xml: string, position?: number, options?: InsertXmlOptions` | Fügt Roh-XML an der Cursorposition ein |
  | Einfügen | `insertXmlAfterElement` | `elementName: string, xmlString: string` | Fügt XML unmittelbar nach dem nächsten übereinstimmenden `elementName` ein |
  | Einfügen | `replaceSelectionWithXml` | `xmlString: string` | Ersetzt die aktuelle Auswahl durch die angegebene XML |
  | Knotenvorgänge | `surroundWithElement` | `tagName: string, attrs?: Record<string,unknown>, replaceTextWithEmptyNode?: boolean` | Schließt die aktuelle Auswahl in das angegebene Element ein. |
  | Knotenvorgänge | `wrapNode` | `type: string, target?: number, attrs?: Record<string, unknown>` | Schließt den Knoten in `target` (oder den aktuellen Knoten) in ein -Element von `type` ein. |
  | Knotenvorgänge | `renameNode` | `newNodeName: string` | Benennt das Element des aktuellen Knotens um |
  | Knotenvorgänge | `unwrapNode` | _(keine)_ | Entfernt das Wrapper-Element des aktuellen Knotens und behält seinen Inhalt bei |
  | Löschen | `deleteSelection` | _(keine)_ | Löscht den aktuell ausgewählten Inhalt |
  | Löschen | `deleteNode` | _(keine)_ | Löscht den gesamten aktuellen Knoten |
  | Attribute | `setNodeXmlAttributes` | `position: number, attrs: Record<string, unknown>` | Legt mehrere XML-Attribute auf dem Knoten unter `position` fest |
  | Attribute | `setNodeXmlAttribute` | `position: number, attrName: string, value: string` | Setzt ein einzelnes XML-Attribut auf dem Knoten unter `position` |
  | Listen | `toggleList` | `listName: 'ol' \| 'ul'` | Blendet den aktuellen Block zwischen einer Liste des angegebenen Typs und einem Absatz ein oder aus |
  | Tabellen | `addRowAfter` | `count?: number` | Fügt `count` Zeilen unter der aktuellen Zeile hinzu (Standard 1) |
  | Tabellen | `addColumnAfter` | `count?: number` | Fügt `count` Spalten rechts von der aktuellen Spalte hinzu (Standard 1) |
  | Tabellen | `deleteRow` | _(keine)_ | Löscht die aktuelle Zeile |
  | Tabellen | `deleteColumn` | _(keine)_ | Löscht die aktuelle Spalte |
  | Tabellen | `mergeCells` | _(keine)_ | Führt die gerade ausgewählten Zellen zusammen |
  | Zwischenablage | `copy` | _(keine)_ | Kopiert die aktuelle Auswahl in die Zwischenablage |
  | Zwischenablage | `cut` | _(keine)_ | Schneidet die aktuelle Auswahl in die Zwischenablage aus |
  | Suchen und Ersetzen | `setSearchQuery` | `query: string, options?: { caseSensitive?: boolean, regex?: boolean }` | Legt die aktive Suchabfrage fest |
  | Suchen und Ersetzen | `findNext` | _(keine)_ | Wechselt zum nächsten Suchergebnis |
  | Suchen und Ersetzen | `replaceAll` | `replacement?: string` | Ersetzt alle Treffer der aktuellen Suchanfrage durch `replacement` |

   - **Beispiel: Legen Sie mehrere Attribute auf einem Knoten fest**

     ```js
     guides.editor.runCommand(
       "setNodeXmlAttributes",
       rootRange.from,
       { createdDate: "2024-01-01", author: "Jane Doe" }
     );
     ```

   - **Beispiel: Legen Sie ein einzelnes Attribut auf einem Knoten fest**

     ```js
     guides.editor.runCommand(
       "setNodeXmlAttribute",
       range.from,
       "placeholdertext",
       "Chapter 3 — Safety Requirements"
     );
     ```

   - **Beispiel: Auswahl mit einem Element umschließen und Attribute festlegen**

     ```js
     const didWrap = guides.editor.runCommand(
       "surroundWithElement",
       "ph",
       { outputclass: "highlight" },
       true   // replace text content with empty node
     );
     ```

   - **Beispiel: Auswahl in `<sup>` umbrechen (Hochgestellt ein/aus)**

     ```js
     const didWrap = guides.editor.runCommand('surroundWithElement', 'sup');
     if (!didWrap) {
       tcx.util.showAlert("warning", "superscript is not allowed here");
     }
     ```

   - **Beispiel: Aktuelle Knoten entpacken (Hochgestellt ein-/ausschalten)**

     ```js
     const didUnwrap = guides.editor.runCommand('unwrapNode');
     ```

   - **Beispiel: XML am Cursor einfügen, mit eingesetztem Caret-Zeichen**

     ```js
     guides.editor.runCommand(
       'insertXml',
       '<sup></sup>',
       undefined,
       { setCursorInContent: true, focusEditor: true, selectInsertedXml: false }
     );
     ```

- `guides.editor.canRunCommand(commandName, ...args)`: Überprüft, ob ein benannter Befehl derzeit ausgeführt werden kann, ohne ihn tatsächlich auszuführen.

  **Signatur:**

  ```ts
  guides.editor.canRunCommand(commandName: string, ...args: any[]): boolean
  ```

  **Beispiel:**

  ```js
  if (guides.editor.canRunCommand('surroundWithElement', 'sup')) {
    guides.editor.runCommand('surroundWithElement', 'sup');
  }
  ```

## Dienstprogrammfunktionen

- `guides.editor.runUtil(utilName, ...args)`: Ruft ein benanntes Dienstprogramm aus der Registrierung des neuen Editors auf. Gibt das Ergebnis des Dienstprogramms zurück, oder `undefined`, wenn das Dienstprogramm nicht gefunden wird.

  **Signatur:**

  ```ts
  guides.editor.runUtil(utilName: string, ...args: any[]): any
  ```

  **Verfügbare Dienstprogramme**

  >[!NOTE]
  >
  > Stabilität: Die unten aufgeführten Dienstprogramme sind Teil der öffentlichen Schnittstelle. Ihre Namen, Signaturen und beobachtbaren Verhaltensweisen werden als stabil betrachtet und aus Kompatibilitätsgründen beibehalten. Im Editor können zusätzliche Befehle vorhanden sein. Diese sind jedoch intern, nicht für die externe Verwendung vorgesehen und können ohne vorherige Ankündigung geändert oder entfernt werden.


  | Kategorie | Dienstprogramm | Argumente | Rückgabe | Beschreibung |
  |---|---|---|---|---|
  | Position | `getTextPos` | _(keine)_ | `{ start: number, end: number }` | Start- und Endpositionen der aktuellen Auswahl im ProseMirror-Dokument |
  | Position | `getNodePosition` | `position?: number` | `number` | Dokumentposition des aktuell ausgewählten/fokussierten Knotens |
  | Position | `mapToXpath` | `position: number` | `XPathPosition` | Ordnet eine ProseMirror-Position einem XPath-Deskriptor zu. |
  | Position | `inverseMap` | `xpath: XPathPosition \| number` | `number` | Ordnet einen XPath-Deskriptor (oder eine numerische Position) wieder einer ProseMirror-Position zu. |
  | Dokument | `getNodeTree` | _(keine)_ | `NodeTree \| null` | Strukturdarstellung des Dokuments, geeignet für die Gliederungswiedergabe |
  | Dokument | `getAncestorsNames` | `position?: number` | `string[]` | XML-Tag-Namen von Vorgängerknoten bei `position` |
  | Dokument | `getAncestorsDetails` | `position?: number` | `{ currNode: string, ancestors: Array<{tagName: string}>, previousSibling?: string, nextSibling?: string } \| undefined` | Aktueller Knoten, Vorgänger und unmittelbare gleichrangige Elemente unter `position` |
  | Dokument | `getAncestorXpaths` | `includeId?: boolean` | `AncestorXpathItem[]` | XPath-Zeichenfolgen für alle Vorgängerknoten |
  | Dokument | `getPreviousSibling` | `position?: number` | `string \| undefined` | Tag-Name des vorherigen gleichrangigen Elements, falls vorhanden |
  | Dokument | `getNextSibling` | `position?: number` | `string \| undefined` | Tag-Name des nächsten gleichrangigen Elements, falls vorhanden |
  | Dokument | `getTagName` | `position?: number` | `string \| null` | Tag-Name des Elements bei `position` (oder Cursor) |
  | Elementsuche | `findPositionRange` | `tagName: string` | `{ from: number, to: number } \| undefined` | Bereich des ersten Elements mit dem angegebenen Tag |
  | Elementsuche | `findPositionRanges` | `tagName: string` | `Array<{ from: number, to: number }>` | Alle Bereiche für Elemente, die `tagName` entsprechen |
  | Attribute | `getAttributeAtPosition` | `position: number, attrName: string` | `unknown` | Liest einen XML-Attributwert aus dem Knoten unter `position` |
  | Attribute | `getSerializableAttributes` | `xpath: string` | `Record<string, unknown>` | Alle serialisierbaren XML-Attribute für den Knoten unter `xpath` |
  | Serialisierung | `serialize` | _(keine)_ | `string` | Serialisiert das gesamte Dokument in XML |
  | Serialisierung | `serializeToText` | _(keine)_ | `string` | Serialisiert das gesamte Dokument im Klartext |
  | Serialisierung | `getRangeXml` | `xpaths: AncestorXpathItem[]` | `string` | Gibt die XML für einen XPath-definierten Bereich zurück. |
  | Auswahl | `getSelectedXml` | _(keine)_ | `string` | Derzeit ausgewählte Inhalte als XML-Zeichenfolge |
  | Auswahl | `getSelectedText` | _(keine)_ | `string` | Ausgewählter Text ohne Markup |
  | Auswahl | `hasSelection` | _(keine)_ | `boolean` | `true`, ob eine aktive Text-/Knotenauswahl vorhanden ist |
  | Auswahl | `isSelectionEditable` | _(keine)_ | `boolean` | ob sich die aktuelle Auswahl in bearbeitbaren Inhalten befindet |
  | Auswahl | `isPositionEditable` | `position: number` | `boolean` | ob `position` sich in bearbeitbaren Inhalten befindet |
  | Einfügen | `canInsert` | `name: string, position?: number, insertMode?: 'after' \| 'before' \| 'rename'` | `boolean` | Gibt an, ob `name` unter `position` (oder dem Cursor) eingefügt werden können |
  | Einfügen | `getInsertPosition` | `name: string, position?: number, insertMode?: 'after' \| 'before' \| 'rename'` | `number \| null` | Gültige Einfügeposition für `name` oder `null`, falls nicht einfügbar |
  | Einfügen | `getNodeXml` | `nodeName: string, nodeContent?: string` | `string \| null` | XML-Vorlage für einen Knotentyp |
  | Umbrechen/Umbenennen | `getValidWrapNodeElementNames` | _(keine)_ | `string[]` | Elementnamen, die den aktuellen Bereich umschließen können |
  | Umbrechen/Umbenennen | `getValidRenameNodeElementNames` | _(keine)_ | `string[]` | Elementnamen, in die der aktuelle Knoten umbenannt werden kann |
  | Tabellen | `getTableInfo` | `position?: number` | `{ rows: number, cols: number, header: number }` | Abmessungen der aktuellen Tabelle |
  | Tag-Ansicht | `isTagViewActive` | _(keine)_ | `boolean` | Ob das Tag-View Rendering aktiv ist |

  **Beispiel: Cursor-Position und Vorgängernamen abrufen**

  ```js
  const textPos = guides.editor.runUtil("getTextPos");
  const ancestorNames = guides.editor.runUtil(
    "getAncestorsNames",
    typeof textPos === "number" ? textPos : undefined
  );
  ```

  **Beispiel: Suchen aller `<xref>` Elemente und Lesen ihrer Attribute**

  ```js
  const xrefRanges = guides.editor.runUtil("findPositionRanges", "xref") || [];
  xrefRanges.forEach((range) => {
    const id = guides.editor.runUtil("getAttributeAtPosition", range.from, "id");
    const placeholderText = guides.editor.runUtil(
      "getAttributeAtPosition",
      range.from,
      "placeholdertext"
    );
  });
  ```

  **Beispiel: Suchen des Stammelementbereichs und Lesen seiner Attribute**

  ```js
  const rootRange = guides.editor.runUtil("findPositionRange", "concept"); // or "topic"
  if (rootRange) {
    const createdDate = guides.editor.runUtil(
      "getAttributeAtPosition",
      rootRange.from,
      "createdDate"
    );
    const author = guides.editor.runUtil(
      "getAttributeAtPosition",
      rootRange.from,
      "author"
    );
  }
  ```

  **Beispiel: Auswahl überprüfen und Vorgängerkontext vor einem Vorgang validieren**

  ```js
  const ancestorsDetails = guides.editor.runUtil('getAncestorsDetails');
  const selectedText = guides.editor.runUtil('getSelectedPlainText');
  const hasSelection = !!guides.editor.runUtil('hasSelection');
  
  const firstAncestor = ancestorsDetails?.currNode || ancestorsDetails?.ancestors?.[0]?.tagName;
  if (firstAncestor === 'ph') {
    tcx.util.showAlert("warning", "Operation is not allowed inside this element type.");
    return;
  }
  ```

  **Beispiel: Element-IDs von Vorgänger-XPaths abrufen**

  ```js
  const ancestorItems = guides.editor.runUtil('getAncestorXpaths', true);
  for (const item of ancestorItems) {
    const attrs = guides.editor.runUtil('getSerializableAttributes', item.xpath);
    if (attrs?.id) { /* use element ID */ }
  }
  ```

## Dekorations-API

Die Dekorations-API bietet eine Alternative zum Schreiben vollständiger ProseMirror-Plug-ins für gängige visuelle Anpassungen. Anstatt `Plugin`, `PluginKey` und `DecorationSet` manuell zu verwalten, beschreiben Sie *Was* zu dekorieren und *Wie* und der zentrale Dekorations-Manager des Editors handhabt den ProseMirror-Status intern.

Dekorationen werden durch eine `id` identifiziert, sodass sie jederzeit unabhängig aktualisiert oder entfernt werden können.

>[!NOTE]
>
> **Nur neuer Editor** Diese APIs sind keine Ops im alten Editor (`version === '1.0.0'`).

- `guides.editor.addDecoration(id, selector, options)`: Fügt eine Dekorationsregel hinzu oder ersetzt sie. Alle Knoten, die im aktuellen Dokument mit `selector` übereinstimmen, werden nach `options` dekoriert. Die Dekoration wird bei jeder Dokumentenänderung automatisch wieder aufgetragen.

  **Signatur:**

  ```ts
  guides.editor.addDecoration(
    id: string,
    selector: string,
    options: DecorationOptions
  ): boolean
  ```

  **`DecorationOptions`:**

  | Feld | Typ | Beschreibung |
  |---|---|---|
  | `class` | `string` | CSS-Klassenname(n) wurde(n) den entsprechenden Knoten hinzugefügt |
  | `computeAttributes` | `(node, context) => Record<string, string>` | Funktion gibt dynamische `data-*` oder andere HTML-Attribute pro Knoten zurück |
  | `filter` | `(node) => boolean` | Optionales Prädikat - nur Knoten, bei denen dieses `true` zurückgegeben wird, sind dekoriert |

  Das `context` Objekt, das an `computeAttributes` übergeben wird, umfasst:
   - `index` - 0-basierte Position des Knotens unter gleichrangigen Elementen, die dem Selektor entsprechen

  **Beispiel: Fügen Sie eine CSS-Klasse zu allen `<section>` hinzu**

  ```js
  guides.editor.addDecoration('highlight-sections', 'section', {
    class: 'my-section-highlight'
  });
  ```

  **Beispiel: Fügen Sie jedem Abschnitt ein berechnetes `data-number-label` hinzu**

  ```js
  guides.editor.addDecoration('section-numbers', 'section', {
    computeAttributes: (node, context) => ({
      'data-number-label': String(context.index + 1)
    })
  });
  ```

  **Beispiel: Dekorieren Sie nur Abschnitte mit `importance="high"` Attribut**

  ```js
  guides.editor.addDecoration('important-sections', 'section', {
    class: 'section-important',
    filter: (node) => node.attrs?.xmlAttrs?.importance === 'high'
  });
  ```

  **Beispiel: Kombinieren Sie Klassen- und berechnete Attribute**

  ```js
  guides.editor.addDecoration('numbering-mode', 'conbody', {
    class: 'legacy-numbering'
  });
  
  guides.editor.addDecoration('section-numbers', 'section', {
    computeAttributes: (node, context) => ({
      'data-number-label': String(context.index + 1)
    })
  });
  ```

- `guides.editor.removeDecoration(id)`: Entfernt eine zuvor hinzugefügte Dekoration anhand ihrer ID.

  **Signatur:**

  ```ts
  guides.editor.removeDecoration(id: string): boolean
  ```

  **Beispiel:**

  ```js
  guides.editor.removeDecoration('section-numbers');
  ```

- `guides.editor.batchDecorations(changes)`: Wendet mehrere Änderungen beim Hinzufügen/Entfernen von Dekorationen in einem einzigen ProseMirror-Dispatch an. Verwenden Sie dies, wenn Sie mehrere Dekorationen gleichzeitig umschalten, um mehrfaches erneutes Rendern zu vermeiden.

  **Signatur:**

  ```ts
  guides.editor.batchDecorations(changes: DecorationBatchChange[]): boolean
  
  type DecorationBatchChange =
    | { action: 'add', id: string, selector: string, options: DecorationOptions }
    | { action: 'remove', id: string }
  ```

  **Beispiel: Automatisches Umschalten zwischen zwei Nummerierungsmodi**

  ```js
  guides.editor.batchDecorations([
    { action: 'remove', id: 'legacy-numbering' },
    {
      action: 'add',
      id: 'division-numbering',
      selector: 'conbody',
      options: { class: 'division-numbering' }
    }
  ]);
  ```

  **Beispiel: eine Dekoration entfernen und zwei neue hinzufügen**

  ```js
  guides.editor.batchDecorations([
    { action: 'remove', id: 'old-highlights' },
    {
      action: 'add',
      id: 'section-labels',
      selector: 'section',
      options: {
        computeAttributes: (node, ctx) => ({ 'data-section-index': String(ctx.index) })
      }
    },
    {
      action: 'add',
      id: 'note-style',
      selector: 'note',
      options: { class: 'styled-note' }
    }
  ]);
  ```

- `guides.editor.clearDecorations()`: Entfernt alle aktiven Dekorationen, die vom Dekorations-Manager verwaltet werden.

  **Signatur:**

  ```ts
  guides.editor.clearDecorations(): boolean
  ```

  **Beispiel:**

  ```js
  guides.editor.clearDecorations();
  ```

- `guides.editor.getDecorations()`: Gibt die IDs aller derzeit aktiven Dekorationen zurück.

  **Signatur:**

  ```ts
  guides.editor.getDecorations(): string[]
  ```

  **Beispiel:**

  ```js
  const active = guides.editor.getDecorations();
  console.log('Active decorations:', active);
  // e.g. ['section-numbers', 'numbering-mode', 'note-style']
  ```


### Dekorations-API im Vergleich zu `registerPlugin`

| Szenario | Verwendung |
|---|---|
| Anwenden von CSS-Klassen- oder `data-*` auf übereinstimmende Elemente | `addDecoration` |
| Umschalten oder Aktualisieren der Formatierung basierend auf dem Laufzeitstatus (Metadaten, Benutzeraktion) | `addDecoration` / `removeDecoration` / `batchDecorations` |
| Komplexe Plug-in-Logik: benutzerdefinierter Status, Tastenbindungen, Widget-Dekorationen, Ereignis-Handler | `registerPlugin` |
| CSS in das Schatten-DOM einfügen | `registerPlugin` mit `css` Feld |


## Registrierung des ProseMirror-Plug-ins

- `guides.editor.registerPlugin(factory)`: Registriert eine ProseMirror-Plug-in-Factory, die in jeder neuen Editor-Instanz enthalten sein soll. Nur Werksfunktionen werden akzeptiert, direkte Plug-in-Instanzen werden abgelehnt. Die Factory wird einmal pro Editor-Instanz aufgerufen, um einen isolierten Plug-in-Status sicherzustellen.

  **Signatur:**

  ```ts
  guides.editor.registerPlugin(factory: () => PluginConfig): void
  
  interface PluginConfig {
    plugin: ProseMirrorPlugin | ProseMirrorPlugin[]
    css?: string  // Injected into editor's shadow DOM
  }
  ```

  **Beispiel: Plug-ins registrieren, wenn der Editor bereit ist**

  ```js
  guides.ready(() => {
    guides.editor.registerPlugin(createNumberingPlugin);
    guides.editor.registerPlugin(createXrefPlugin);
  });
  ```

  **Beispiel: Inline-Factory mit CSS**

  ```js
  guides.editor.registerPlugin(() => ({
    plugin: new guides.editor.prosemirror.state.Plugin({
      key: new guides.editor.prosemirror.state.PluginKey("myPlugin"),
      props: {
        decorations(state) {
          // return DecorationSet...
        }
      }
    }),
    css: `.my-decoration { background: yellow; }`
  }));
  ```

  >[!NOTE]
  >
  > Über `css` übergebenes CSS wird in das Schatten-DOM des Editors eingefügt. Reguläre Stylesheets auf Seitenebene gelten nicht im Editor.

## ProseMirror-Bibliotheken

- `guides.editor.prosemirror`: stellt ProseMirror-Pakete direkt für die Verwendung bei der Plug-in-Entwicklung bereit. Dadurch wird vermieden, dass ProseMirror separat im Erweiterungs-Code gebündelt werden muss.

  | Eigenschaft | Paket |
  |---|---|
  | `state` | `prosemirror-state` |
  | `model` | `prosemirror-model` |
  | `view` | `prosemirror-view` |
  | `transform` | `prosemirror-transform` |
  | `commands` | `prosemirror-commands` |
  | `keymap` | `prosemirror-keymap` |
  | `history` | `prosemirror-history` |
  | `tables` | `prosemirror-tables` |
  | `dropcursor` | `prosemirror-dropcursor` |
  | `markdown` | `prosemirror-markdown` |

  **Beispiel: Erstellen eines Knotendekorations-Plug-ins**

  ```js
  const myPluginKey = new guides.editor.prosemirror.state.PluginKey("myPlugin");
  
  const createMyPlugin = () => {
    const { Plugin } = guides.editor.prosemirror.state;
    const { Decoration, DecorationSet } = guides.editor.prosemirror.view;
  
    return {
      plugin: new Plugin({
        key: myPluginKey,
        state: {
          init() { return { enabled: true }; },
          apply(tr, value) {
            const meta = tr.getMeta(myPluginKey);
            return meta ? { ...value, ...meta } : value;
          }
        },
        props: {
          decorations(state) {
            const decorations = [];
            state.doc.descendants((node, pos) => {
              if (node.type.name === "section") {
                decorations.push(
                  Decoration.node(pos, pos + node.nodeSize, { class: "my-section" })
                );
              }
            });
            return DecorationSet.create(state.doc, decorations);
          }
        }
      }),
      css: `.my-section { border-left: 3px solid #ccc; padding-left: 8px; }`
    };
  };
  ```

  **Beispiel: Erstellen eines Widget-Dekorations-Plug-ins (Inline-Anzeigetext)**

  ```js
  const xrefPluginKey = new guides.editor.prosemirror.state.PluginKey("xrefDisplay");
  
  const createXrefPlugin = () => {
    const { Plugin } = guides.editor.prosemirror.state;
    const { Decoration, DecorationSet } = guides.editor.prosemirror.view;
  
    return {
      plugin: new Plugin({
        key: xrefPluginKey,
        props: {
          decorations(state) {
            const decorations = [];
            state.doc.descendants((node, pos) => {
              if (node.type.name.includes("xref")) {
                const display = node.attrs?.xmlAttrs?.placeholdertext;
                if (display) {
                  decorations.push(
                    Decoration.widget(pos + 1, () => {
                      const el = document.createElement("span");
                      el.textContent = `[${display}]`;
                      el.setAttribute("contenteditable", "false");
                      return el;
                    }, { key: `xref-${pos}` })
                  );
                }
              }
            });
            return DecorationSet.create(state.doc, decorations);
          }
        }
      }),
      css: `.xref-display-text { color: #0074d9; pointer-events: none; }`
    };
  };
  ```

## CSS in den Editor einfügen

Der DITA-Editor für Handbücher lädt seine Inhaltsstile für den Autorenmodus aus einer Client-Bibliothek mit der Kategorie `apps.guides.dita_editor.content`. Diese Client-Bibliothek verfügt über eine `embed`-Deklaration, die automatisch alle unter der Kategorie registrierten Client-Bibliotheken abruft:

```
apps.guides.xml_editor.dita_content_overrides
```

Um benutzerdefiniertes CSS in den Inhaltsbereich des Editors einzufügen, erstellen Sie einen AEM-Clientlib-Knoten mit dieser Kategorie. Es ist keine zusätzliche Verkabelung erforderlich. Guides nimmt diese automatisch beim Laden der Editor-Seite auf.

**AEM ClientLib-Knotenstruktur (`/apps/my-extension/clientlibs/editor-content-overrides/.content.xml`)**

```xml
<?xml version="1.0" encoding="UTF-8"?>
<jcr:root xmlns:cq="http://www.day.com/jcr/cq/1.0"
          xmlns:jcr="http://www.jcp.org/jcr/1.0"
    jcr:primaryType="cq:ClientLibraryFolder"
    categories="[apps.guides.xml_editor.dita_content_overrides]"/>
```

Platzieren Sie Ihre CSS-Datei (`css.txt` + Ihre `.css`-Datei) in diesem Ordner. Er wird automatisch in das Content-Stylesheet des Editors eingebettet.

**Beispiel: Überschreiben von Stilen für Abschnittsüberschriften im Autorenmodus**

```css
/* /apps/my-extension/clientlibs/editor-content-overrides/css/content.css */

/* Increase section title font size in author mode */
.section > title {
  font-size: 1.4em;
  font-weight: bold;
  color: #333;
}

/* Highlight note blocks */
.note {
  border-left: 4px solid #0074d9;
  padding-left: 12px;
  background: #f0f7ff;
}
```

>[!NOTE]
>
>Dieses CSS ist nur für die veraltete, auf dem CKEditor basierende Autorenoberfläche bestimmt. Im neuen Editor (ProseMirror), der ein Schatten-DOM verwendet, hat dies keine Auswirkung.


### Neuer Editor: `css` in `registerPlugin`

Der neue Editor wird in einem **Shadow-DOM** gerendert, wodurch er von allen Stilen auf Seitenebene, einschließlich AEM-`clientlibs`, isoliert wird. Um CSS in die Autorenoberfläche des neuen Editors einzufügen, übergeben Sie eine `css` Zeichenfolge als Teil der von Ihrer Plug-in-Factory zurückgegebenen `PluginConfig`.

Das CSS wird jedes Mal als `<style>`-Tag direkt in den Schattenstamm des Editors eingefügt, wenn eine Editor-Instanz erstellt wird.

**Beispiel: Fügen Sie Stile zusammen mit einem Dekorations-Plug-in ein**

```js
guides.ready(() => {
  guides.editor.registerPlugin(() => ({
    plugin: createMyPlugin(), // your ProseMirror plugin
    css: `
      /* Styles scoped to the New Editor shadow DOM */
      .section > .title-node {
        font-size: 1.4em;
        font-weight: bold;
        color: #333;
      }

      .note-node {
        border-left: 4px solid #0074d9;
        padding-left: 12px;
        background: #f0f7ff;
      }
    `
  }));
});
```

**Beispiel: Nur-CSS-Plug-in (keine Dekorationslogik)**

```js
guides.ready(() => {
  guides.editor.registerPlugin(() => ({
    plugin: new guides.editor.prosemirror.state.Plugin({}), // no-op plugin
    css: `
      /* Custom author-mode typography */
      [data-xml-element="codeblock"] {
        font-family: monospace;
        background: #f5f5f5;
        padding: 8px;
        border-radius: 4px;
      }
    `
  }));
});
```

>[!NOTE]
>
> Dieses CSS gilt nur innerhalb des Schatten-DOM des neuen Editors. Dies hat keine Auswirkungen auf den Rest der Seite oder den alten Editor.


## Kontextmenüerweiterungen (`contextMenuWidget`)

Erweiterungen können dem Kontextmenü des Editors per Rechtsklick bzw. Breadcrumb Elemente hinzufügen, indem sie in ihrer Erweiterungskonfiguration ein `contextMenuWidget` Feld deklarieren. Dadurch wird dem Framework mitgeteilt, welches Editor-Menü ausgewählt werden soll.

### Widget-IDs

| Widget-ID | Editor |
|---|---|
| `dita_editor_menu` | Alte Autorenoberfläche des CKE-Editors (Breadcrumb + Kontextmenü für Elemente) |
| `markup_editor_menu` | Breadcrumb- und Element-Kontextmenü des neuen Editors (ProseMirror) |

Beide Widgets werden gleichzeitig auf der Seite bereitgestellt. Das Framework ordnet jede Erweiterung basierend auf diesem Feld dem richtigen Menü zu.

> Erweiterungen können auch beide Editoren ansprechen, indem sie ein Array übergeben: `contextMenuWidget: ["dita_editor_menu", "markup_editor_menu"]`

### Legacy-Editor: `dita_editor_menu`

Verwenden Sie dies für Erweiterungen, die im Kontextmenü des alten CKE-Editors angezeigt werden sollen.

```js
const myContextMenuExtension = {
  id: "dita_author_view_menu",
  contextMenuWidget: "dita_editor_menu",
  view: {
    items: [
      {
        displayName: "My Custom Action",
        data: { eventid: "myCustomAction" },
        icon: "textSpaceAfter",
        target: {
          key: "displayName",
          value: "Wrap Element",   // insert after this existing menu item
          viewState: "append",
        },
      },
    ],
  },
  controller: {
    myCustomAction() {
      console.log("Custom action triggered");
    },
  },
};
```

### Neuer Editor: `markup_editor_menu`

Verwenden Sie diese Option für Erweiterungen, die im Kontextmenü des neuen Editors angezeigt werden sollen (Breadcrumbs und Rechtsklick auf Elemente). Der Controller empfängt Ereignisse über `handleExtensionEvent`, der lokale Handler an den `markup_editor_menu`-Controller weiterleitet und globale Ereignisse über den App-Ereignishandler auslöst.

```js
const myMarkupContextMenu = {
  id: "dita_author_view_menu",
  contextMenuWidget: "markup_editor_menu",
  view: {
    items: [
      {
        displayName: "Edit Cross Reference",
        data: { eventid: "editCrossReference" },
        icon: "link",
        target: {
          key: "displayName",
          value: "Cut",
          viewState: "prepend",
        },
      },
      {
        displayName: "Remove Cross Reference",
        data: { eventid: "removeCrossReference" },
        icon: "deleteOutline",
        target: {
          key: "displayName",
          value: "Edit Cross Reference",
          viewState: "append",
        },
      },
    ],
  },
  controller: {
    editCrossReference() {
      // Use guides.editor APIs to read context
      const ancestorXpaths = guides.editor.runUtil("getAncestorXpaths", true);
      // open dialog or take action...
    },
    removeCrossReference() {
      guides.editor.runCommand("unwrapNode");
    },
  },
};
```

## Dienstprogrammbibliotheken

- `guides.util.lodash`:The die Dienstprogramm-Bibliothek Lodash, dieselbe Instanz im Paket mit dem Editor.

  ```js
  const uniqueIds = guides.util.lodash.uniq(ids);
  ```

- `guides.util.async`: Async-Dienstprogrammbibliothek zur Verwendung durch Erweiterungen.

  ```js
  guides.util.async.parallel([task1, task2], callback);
  ```

## Vollständige API-Referenz

| API | Beschreibung |
|---|---|
| `filePath` | Abrufen des Dateipfads des aktiven Dokuments |
| `version` | Abrufen der geladenen Editor-Versionszeichenfolge |
| `appState(key)` | Lesen eines Werts aus dem Anwendungsmodell |
| `focus()` | Aktiven Editor fokussieren |
| `canInsertXmlElement(tag, insertAfter?)` | Überprüfen, ob ein Element am Cursor eingefügt werden kann |
| `selectCurrentBlockElement()` | Aktuelles Blockelement auswählen |
| `getValidElementNamesForInsertion(args)` | Auflisten gültiger Elementnamen für das Einfügen |
| `updateAttributeByXpath(args)` | Aktualisieren eines Attributs nach XPath |
| `runCommand(name, ...args)` | Führt einen benannten Editor-Befehl aus |
| `canRunCommand(name, ...args)` | Überprüfen, ob ein Befehl ausgeführt werden kann |
| `runUtil(name, ...args)` | Aufrufen eines benannten Editor-Dienstprogramms |
| `addDecoration(id, selector, options)` | Hinzufügen oder Ersetzen einer benannten Dekorationsregel für übereinstimmende Elemente |
| `removeDecoration(id)` | Entfernen einer Dekorationsregel nach ID |
| `batchDecorations(changes)` | Mehrere Änderungen beim Hinzufügen/Entfernen von Dekorationen in einem Dispatch anwenden |
| `clearDecorations()` | Alle aktiven Dekorationsregeln entfernen |
| `getDecorations()` | IDs aller aktuell aktiven Dekorationen abrufen |
| `registerPlugin(factory)` | Registrieren einer ProseMirror-Plug-in-Fabrik (auch der Mechanismus für die Schatten-DOM-CSS-Injektion) |
| `prosemirror.state` | `prosemirror-state` |
| `prosemirror.model` | `prosemirror-model` |
| `prosemirror.view` | `prosemirror-view` |
| `prosemirror.transform` | `prosemirror-transform` |
| `prosemirror.commands` | `prosemirror-commands` |
| `prosemirror.keymap` | `prosemirror-keymap` |
| `prosemirror.history` | `prosemirror-history` |
| `prosemirror.tables` | `prosemirror-tables` |
| `prosemirror.dropcursor` | `prosemirror-dropcursor` |
| `prosemirror.collab` | `prosemirror-collab` |
| `prosemirror.markdown` | `prosemirror-markdown` |
