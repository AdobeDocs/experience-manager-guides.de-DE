---
title: Migrieren von Änderungen am Erweiterungs-Framework für Editor 2.0
description: Erfahren Sie mehr über die Migration zum Erweiterungs-Framework für Editor 2.0
feature: Web Editor Configuration
role: Admin
level: Experienced
source-git-commit: 75954eab3ac1738705fe2a7280973af39b9214df
workflow-type: tm+mt
source-wordcount: '2006'
ht-degree: 3%

---


# Migrieren des Erweiterungs-Frameworks zum Editor 2.0 (neuer Editor)

Dieses Handbuch hilft Erweiterungsautoren zu verstehen, was beim Verschieben ihrer Anpassungen vom **alten Editor** zum **neuen Editor** in AEM Guides erforderlich ist, damit sie den Übergang reibungslos und mit minimaler Unterbrechung planen können.

>[!IMPORTANT]
> 
> Wenn Sie bereits über eine AEM Guides-Erweiterung (alten Editor) verfügen, einschließlich benutzerdefinierter Kontextmenüelemente, Symbolleistenschaltflächen, Dialogfelder, Attribut- oder Metadatenlogik oder Inhaltsstile, hilft Ihnen dieses Handbuch, das Arbeiten mit dem neuen Editor fortzusetzen.

## Überblick

- **Ihre Registrierung ändert sich nicht**: Verwenden Sie weiterhin `window.extension` / `tcx.extension.register`.
- **Die Arbeitsfläche des Editors ist eine neue Oberfläche.** Kontextmenüelemente müssen die neue Widget-ID deklarieren
  `markup_editor_menu`; Das Verhalten im Editor muss aufhören, das DOM zu berühren.
- **Lesen/Schreiben des DOM beenden**: Ersetzen Sie `tcx.curEditor.*` DOM-Zugriff durch
  `guides.editor`-API: [Lesen mit `runUtil(...)`](#migrate-reads-dom-runutil), [Schreiben mit `runCommand(...)`](#migrate-writes-dom-mutation-runcommand), [Stil mit Dekorationen](#migrate-rendering-only-logic-dom-paint-decorations) und [Ausführen globaler Aktionen (Speichern) durch App-Ereignisse](#migrate-global-actions-savefocus-app-events) .
- **App-Shell-Menüs (Repository, Zuordnungs-Viewer, Datei/Ordner) sind unverändert**: Sie werden weiterhin unter ausgeführt
Das veraltete Framework.
- **Beide Editoren koexistieren**: Targeting beider mit Arrays. Beim Laden **Registrieren** Plug-ins bedingungslos; nur *Laufzeitaktionen* durch `guides.editor.version` (was `1.0.0` bleibt, bis eine Datei geöffnet ist, siehe [Editor und Bootstrap sicher erkennen](#detect-the-Editor-and-bootstrap-safely)).


## Warum der Wechsel?

| Kriterien | Legacy-CODE-Editor | Neuer Markup-Editor |
|---|---|---|
| Source der Wahrheit | DOM | ProseMirror-Dokument |
| Auswahl | `getSelection()` eines Stammdokuments | ProseMirror-Auswahl (Positionen/Bereiche) |
| So ändern Sie Inhalte | Ändern von DOM-Attributen/-Klassen | Befehl auslösen (Transaktion) |
| Rendering | DOM ist dauerhaft | DOM ist ein temporäres Rendering in einem Schatten-DOM, das jederzeit neu aufgebaut werden kann |
| Stile | Seiten- oder Clientlib-CSS | CSS injiziert Schatten-DOM über Register-Plug-in. Unter [Hello world: a CSS-only highlight plugin](#hello-world-a-css-only-highlight-plugin) finden Sie, wie Sie vorhandene Klassen verwenden und CSS hinzufügen und [Rendering-Only-Logik migrieren](#migrate-rendering-only-logic-dom-paint-decorations) um eine neue Klasse und Stile hinzuzufügen. |

Alle Erweiterungen, die das DOM mutieren, oder DOM-Änderungen werden nicht beibehalten, sondern beim nächsten Rendern gelöscht. Die Migration erfolgt im Wesentlichen *von „DOM-first“ zu „model-first*.

## Sicheres Erkennen von Editor und Bootstrap

Das globale `guides` ist der Einstiegspunkt für alle neuen Integrationen:

```js
guides.editor    // editor interaction APIs
guides.util      // bundled utility libs (lodash, async)
guides.ready(cb) // fires once at app load (view system ready) — before any file is open
```

`guides.editor.version` meldet den **derzeit geöffneten Editor** sodass er nur einmal pro
Die Datei ist tatsächlich geöffnet:

| `guides.editor.version` | Bedeutung |
|---|---|
| `2.0.0` | Eine MarkupEditor-Datei (ProseMirror) ist geöffnet |
| `1.0.0` | Eine ältere CKEditor-Datei ist geöffnet oder noch keine Datei ist geöffnet |

>[!IMPORTANT]
>
> Wenn das `guides.ready` auftritt, wurde noch keine Datei geöffnet. Daher wird `version` unabhängig davon, ob MarkupEditor aktiviert ist, als `1.0.0` gemeldet. Verwenden Sie `version` nicht, um festzustellen, ob Plug *ins registriert werden* (siehe [Plug-in-Registrierung und Runtime-Gating](#plugin-registration-and-runtime-gating)). Verwenden Sie sie nur, um *Laufzeitverhalten* zu verzweigen und sie am Ausführungspunkt (z. B. in einem Menühandler) auszuwerten, wo eine Datei garantiert geöffnet ist.

### Plug-in-Registrierung und Runtime-Gating

- **Registrierung** (`registerPlugin`, einmalige Einrichtung): Führen Sie sie **bedingungslos** in `guides.ready` aus. Dies ist ein harmloses No-op im alten Editor: Der alte Editor liest die Plug-in-Registrierung nie, und Ihre Factory wird nur ausgeführt, wenn tatsächlich ein MarkupEditor erstellt wird. Sie **nicht**.

- **Laufzeitaufrufe** (`runCommand`, `runUtil`, `addDecoration`, …): Das Gate nach Version ist vorhanden und entspricht zur Aufrufzeit nicht „1.0.0“. Sie werfen den alten Editor nicht auf (sie geben sicher `false`/`undefined` zurück), aber das Gating vermeidet Warnungen ohne Unterbrechung und ermöglicht es Ihnen, ein altes Fallback zu behalten.

```js
guides.ready(() => {
  // Always register — inert on legacy, applied only when a MarkupEditor opens.
  guides.editor.registerPlugin(createMyPlugin);
});

function onMenuClick() {
  if (guides.editor.version && guides.editor.version !== "1.0.0") {
    guides.editor.runCommand('surroundWithElement', 'sup'); // MarkupEditor path
  } else {
    // legacy path (or no-op)
  }
}
```

Übergeben Sie eine **Factory**-`() => ({ plugin, css })` - an `registerPlugin`, niemals eine konstruierte Plug-in-Instanz. Eine Nicht-Funktion ist die einzige Eingabe, die sie verwirft (und über beide Editoren ausgibt). Die Editor-Instanz wird nicht zwischengespeichert; `guides.editor.*` jedes Mal neu aufgerufen.

### Hello world: ein reines CSS-Highlight-Plug-in

Die kleinste nützliche Erweiterung **nur CSS** ein No-op ProseMirror-Plug-in plus Stile. Dies
Markiert jedes `<note>` mit gelbem Hintergrund im Editor:

```js
guides.ready(() => {
  guides.editor.registerPlugin(() => ({
    plugin: new guides.editor.prosemirror.state.Plugin({}), // no behavior — CSS only
    css: `[data-xml-element="note"] { background: #fff3cd; outline: 1px solid #ffe08a; }`
  }));
});
```

- Jedes Element wird als `data-xml-element="<tag>"` gerendert, sodass Sie jedes DITA-Element auf diese Weise als Ziel auswählen können
(`note`, `codeblock`, `section`, `table`, …).
- CSS **muss** über das registerPlugin bereitgestellt werden: Der Editor befindet sich in einem Shadow-DOM, daher kann die CSS-Datei page/clientlib nicht
Erreichen Sie ihn.
- Öffnen Sie ein DITA-Thema, das eine `<note>` enthält, um deren Anwendung zu sehen. Die Registrierung ist bedingungslos (§2.1),
Das ist sicher, auch wenn `version` zu `guides.ready` Zeit noch `1.0.0` ist.


## Inventarisieren der Erweiterung (Grep-Checkliste)

```bash
# DOM-first reads that will break
grep -rnE "rootDocument|rootElement|getSelection\(|selectedHtml|selectedText|\.xmlDoc|\.ancestors\b" src

# DOM/legacy writes that will break
grep -rnE "updateAttributes\(|setAttribute\(|classList\.|\.saveFile\(|resetDirty\(|validateRangeForInsertion\(" src

# The editor handle itself
grep -rn "tcx.curEditor" src

# Context-menu targeting + page CSS
grep -rnE "contextMenuWidget|dita_editor_menu|author_outline_element" src
grep -rn "dita_content_overrides" .
```

Jeder Treffer ist ein Migrationselement. Jede klassifizieren als: *Kontextmenüoberfläche*, *Status lesen*, *content
write*, *global action*, *rendering-only* oder *CSS*.


## Gemeinsam für beide Editoren

Die folgenden Verhaltensweisen und Strukturen gelten für beide Editoren gleichermaßen:

- **Registrierung:** `window.extension[id] = config` und/oder `tcx.extension.register(id, config)` am
Das `tcx-loaded` Ereignis.
- **Config-Objektform:** `{ id, contextMenuWidget, view: { items }, controller }`.
- **App-Shell-Kontextmenüs** Beibehaltung der vorhandenen Widget-IDs und des alten Verhaltens:

  | Oberfläche | Widget-ID (unverändert) |
  |---|---|
  | Repository-Bedienfeld (Datei/Ordner) | `repository_panel` / `file_options` / `folder_options` |
  | Karten-Viewer | `ditamap_viewer` / `map_view_options` |
  | Bedienfelder „Baseline/Voreinstellung“ | `baseline_panel_menu` / `preset_item_menu` |

  Elemente, die auf diese Oberflächen abzielen **müssen für** neuen Editor nicht verschoben werden
  `markup_editor_menu`.

## API-Ersatzreferenz

| Legacy (`tcx.curEditor…`/DOM) | Neuer Markup-Editor |
|---|---|
| `tcx.curEditor.filePath` | `guides.editor.filePath` |
| `getSelection()` / `selectedHtml` / `selectedText` | `runUtil('getSelectedXml' / 'getSelectedPlainText' / 'hasSelection')` |
| `rootDocument.querySelector(tag)` | `runUtil('findPositionRange' / 'findPositionRanges', tag)` |
| Element `.getAttribute`/`xmlDoc.attributes` | `runUtil('getAttributeAtPosition', pos, name)` / `getSerializableAttributes(xpath)` |
| Stamm-ID (`querySelector('[concept]').id`) | `runUtil('getAttributeAtPosition', 0, 'id')` |
| `editor.ancestors` | `runUtil('getAncestorsDetails' / 'getAncestorXpaths')` |
| `editor.updateAttributes(attrs, root)` | `runCommand('setNodeXmlAttributes', 0, attrs)` |
| Attr. auf Element festlegen | `runCommand('setNodeXmlAttribute', pos, name, value)` |
| Auswahl umbrechen/einfügen/entpacken | `runCommand('surroundWithElement' / 'insertXml' / 'unwrapNode', …)` |
| `canInsertXmlElement` / `validateRangeForInsertion` | `canRunCommand(name, …)` / `canInsertXmlElement(tag)` |
| `editor.focus()` | `guides.editor.focus()` |
| `tcx.curEditor.saveFile()` | `tcx.eventHandler.next(KEYS.AUTHOR_SAVE_KEY)` |
| `setAttribute`/`classList` für die Formatierung | `addDecoration` / `batchDecorations` / `registerPlugin` |
| page/clientlib-CSS für Inhaltseditor | `registerPlugin({ css })` (Shadow DOM) |
| `contextMenuWidget: 'dita_editor_menu'` | `['dita_editor_menu', 'markup_editor_menu']` |


## Migrieren von Kontextmenüelementen (Arbeitsfläche des Editors)

Dies gilt nur für Menüs, die auf den **Editor** (`dita_editor_menu`,
`author_outline_element`), d. h. das Breadcrumb-Menü mit der rechten Maustaste in der Bearbeitungsoberfläche.

### Routing im neuen Editor

```
window.extension[id]  ─►  filtered by contextMenuWidget == 'markup_editor_menu'
                      ─►  view.items rendered in the canvas menu
   (click) ───────────►  fires an extension event:
                          • eventid is a known global key  → run as a built-in editor command
                          • otherwise                       → your controller[eventid]() runs
```

### Neue Widget-ID hinzufügen (Array funktioniert weiterhin)

```js
// BEFORE
contextMenuWidget: 'dita_editor_menu',
// AFTER
contextMenuWidget: ['dita_editor_menu', 'markup_editor_menu'],
```

### Die erwartete Form beibehalten

- Verwertbare Elemente befinden sich unter `view.items` mit einem `data.eventid`.
- Jeder `controller` Methodenname **stimmt überein mit** seinem `eventid` genau.

```js
view: {
  items: [{
    displayName: 'Edit Cross Reference',
    icon: 'link',
    data: { eventid: 'editCrossReference' },
    target: { key: 'displayName', value: 'Cut', viewState: 'prepend' }
  }]
},
controller: {
  editCrossReference() { /* runs on click */ }
}
```

### `target` erneut verankern

Das neue Menü löst `target` mit den eigenen Menüelementen des Markup-Editors auf.

- `target.key`: `displayName | id | icon | eventid`
- `target.viewState`: `append | prepend | replace`
- Verankern in einem stabilen nativen Element, z. B. **`Cut`**.
- Wenn der Anker nicht aufgelöst wird, wird das Element weiterhin angezeigt, landet jedoch an der Standardposition
(Kein Fehler, repariere den Anker).

### Arbeitsplan pro Artikel auswählen

```js
data: { eventid: 'AUTHOR_CUT' }          // built-in command → routed natively, no controller needed
data: { eventid: 'editCrossReference' }  // custom → runs controller.editCrossReference()
```

Fügen Sie `readOnly: true` zu einem Element hinzu, das im schreibgeschützten Inhalt aktiviert bleiben muss.

### Handler-Text neu schreiben

Handler lesen in der Regel die Auswahl und mutieren einen Knoten, migrieren die des DOM.

## Lesevorgänge migrieren (DOM: `runUtil`)

```js
// BEFORE — DOM selection / queries
const { editor } = tcx.curEditor;
const html = editor.selectedHtml;
const topicId = editor.rootDocument.querySelector('[data-tcx-tag="concept"]').id;

// AFTER — read from the document model
const selectedXml = guides.editor.runUtil('getSelectedXml');
const hasSel      = !!guides.editor.runUtil('hasSelection'); // check if selection is empty
const topicId     = guides.editor.runUtil('getAttributeAtPosition', 0, 'id'); // root = position 0
```

Knoten nach Tag suchen, nach ID abgleichen, XML-Attribut lesen:

```js
let value = '';
for (const range of (guides.editor.runUtil('findPositionRanges', 'xref') || [])) {
  const id = guides.editor.runUtil('getAttributeAtPosition', range.from, 'id');
  if (String(id) !== String(targetId)) continue;
  value = guides.editor.runUtil('getAttributeAtPosition', range.from, 'placeholdertext') || '';
  break;
}
```

**Dienstprogramme lesen:** `getTextPos`, `getNodePosition`, `getSelectedXml`, `getSelectedPlainText`,
`hasSelection`, `getAncestorsNames`, `getAncestorsDetails`, `getAncestorXpaths`,
`findPositionRange`, `findPositionRanges`, `getAttributeAtPosition`, `getSerializableAttributes`. Siehe [Anhang](#appendix-a-more-exposed-utils-examples).


## Schreibvorgänge migrieren (DOM-Mutation: `runCommand`)

```js
// BEFORE
const root = editor.rootElement.findOne('[data-tcx-tag="concept"]');
editor.updateAttributes({ docOwner: 'Jane' }, root);

// AFTER — update the model; persists across rerenders
guides.editor.runCommand('setNodeXmlAttributes', 0, { docOwner: 'Jane' });
```

```js
// Set one attribute at a found position
guides.editor.runCommand('setNodeXmlAttribute', pos, 'placeholdertext', text);

// Wrap / insert / unwrap
guides.editor.runCommand('surroundWithElement', 'sup');
guides.editor.runCommand('insertXml', '<sup></sup>', undefined, { setCursorInContent: true });
guides.editor.runCommand('unwrapNode');
```

**Voraussetzung**

```js
guides.editor.focus();
if (!guides.editor.canInsertXmlElement('xref')) {
  return tcx.util.showAlert('warning', 'xref is not allowed here'); 
}
if (guides.editor.canRunCommand('surroundWithElement', 'sup')) {
  guides.editor.runCommand('surroundWithElement', 'sup');
}
```

**Befehle:** `setNodeXmlAttributes`, `setNodeXmlAttribute`, `surroundWithElement`, `insertXml`,
`unwrapNode`. Siehe [Anhang](#appendix-b-more-exposed-commands-examples).

## Globale Aktionen migrieren (Speichern/Fokus: App-Ereignisse)

```js
// BEFORE
tcx.curEditor?.saveFile?.();
// AFTER
tcx.eventHandler.next(tcx.eventHandler.KEYS.AUTHOR_SAVE_KEY);
```

`resetDirty(...)` und `tcx.curEditor.html` haben kein MarkupEditor-Äquivalent. Legen Sie sie daher beim Speichern ab.
durch das Ereignis behandelt schmutzigen Status zentral. Verwenden Sie `guides.editor.focus()` für den Fokus.


## Migrieren der Rendering-Only-Logik (DOM-Paint: decorations)

Alle Elemente, die CSS-Klassen, `data-*` oder „Anzeigetext“ durch Mutation des DOM hinzugefügt haben, müssen
Werden Sie **Dekoration** oder es verschwindet beim Rendern. Im Folgenden finden Sie einfache deklarative Fälle:

```js
guides.editor.addDecoration('important-sections', 'section', {
  class: 'section-important',
  computeAttributes: (node, ctx) => ({ 'data-number-label': String(ctx.index + 1) }),
  filter: (node) => node.attrs?.xmlAttrs?.importance === 'high'
});

guides.editor.batchDecorations([
  { action: 'remove', id: 'legacy-numbering' },
  { action: 'add', id: 'division-numbering', selector: 'conbody', options: { class: 'division-numbering' } }
]);

guides.editor.removeDecoration('important-sections');
guides.editor.clearDecorations();
guides.editor.getDecorations();
```

Komplexe Fälle (benutzerdefinierter Status, gebrochener Status über Transaktions-Meta, Widget-Text): Registrieren eines
ProseMirror-Plug-in einmal unter Verwendung der bereitgestellten Bibliotheken:

```js
const createXrefPlugin = () => {
  const { Plugin, PluginKey } = guides.editor.prosemirror.state;
  const { Decoration, DecorationSet } = guides.editor.prosemirror.view;
  return {
    plugin: new Plugin({ key: new PluginKey('xrefDisplay'), props: { decorations(state) { /* … */ } } }),
    css: `.xref-broken { text-decoration: underline wavy red; }`
  };
};

guides.ready(() => guides.editor.registerPlugin(createXrefPlugin));
```

Plug-ins beim Laden der App (einmal) registrieren, nicht in Dialogfeldern oder wiederholt, dedupliziert die Registrierung nicht. `registerPlugin` akzeptiert eine **nur Factory-Funktion** keine Plug-in-Instanz.
`guides.editor.prosemirror` umfasst: `state`, `model`, `view`, `transform`, `commands`, `keymap`,
`history`, `tables`, `dropcursor`, `collab`, `markdown`.


## Migrieren von CSS (Seite clientlib → shadow DOM)

Der MarkupEditor wird in einem **Shadow-DOM** gerendert; die CSS-Dateien auf Seitenebene und in der AEM-Clientlib erreichen sie nicht.

```js
guides.editor.registerPlugin(() => ({
  plugin: new guides.editor.prosemirror.state.Plugin({}),   // no-op, CSS only
  css: `[data-xml-element="codeblock"] { font-family: monospace; background: #f5f5f5; }`
}));
```

Die alte Client-Bibliothekskategorie für Inhalte (`apps.guides.xml_editor.dita_content_overrides`) wird weiterhin angezeigt
Formatiert nur den alten Editor. Behalten Sie ihn bei, wenn Sie beide unterstützen, aber wissen, dass er im Markup-Editor inaktiv ist.

## Zugriff auf den Live EditorView (Plug-in `view` Eigenschaft): DOM-Escape-Schraffur

Dekorationen und Befehle sind der bevorzugte Ansatz. Einige Effekte können jedoch nicht als Dekoration implementiert werden. Verwenden Sie in diesen Fällen die `view`-Eigenschaft des Plug-ins, um auf die Live `EditorView` zuzugreifen und mit `editorView.dom` zu arbeiten. Dies ist die einzige unterstützte Möglichkeit, direkt mit dem gerenderten Editor-DOM zu interagieren.

```js
const createMyPlugin = () => {
  const { Plugin } = guides.editor.prosemirror.state;
  return {
    plugin: new Plugin({
      view(editorView) {
        const root = editorView.dom;          // the shadow-DOM editor node
        const apply = () => { /* re-color / rewrite target nodes in `root` */ };
        apply();
        return {
          update(view, prevState): apply,                       // re-apply after every rerender
          destroy() { /* remove any listeners/observers */ },
        };
      },
    }),
    css: `/* ... */`,
  };
};

guides.ready(() => guides.editor.registerPlugin(createMyPlugin));
```

**Schutzmaßnahmen**:

- Nur Schraffur mit Escape-Zeichen, verwenden Sie Dekorationen für Klassen, Beschriftungen und Stile.
- `editorView.dom` ist das einzige unterstützte Handle.
- Erneutes Anwenden von `update()`, damit die Änderung das Rendern übersteht; in `destroy()` bereinigen.

## Lebenszyklus der Plug-in-Registrierung

`registerPlugin` in `guides.ready` registriert die Factory nur einmal. Die Fabrik selbst läuft wieder
Jedes Mal, wenn eine Datei geöffnet wird - jede geöffnete MarkupEditor-Datei ruft sie auf, die Datei neu zu erstellen.
Plug-in-Instanz.

## Häufige Probleme

- Dabei adressiert der DOM-Code Knoten und `Range`en), **MarkupEditor (Positionen**, einfache Ganzzahlen, die in das Dokument indiziert werden (`0` = Dokumentstart, d. h. den Stamm). Ein `range` ist `{ from, to }`, zwei Positionen begrenzen einen Bereich - kein DOM-`Range`. Die Positionen ändern sich, wenn sich das Dokument ändert, also speichert keine Position zwischen den Bearbeitungen.
- **Element wird nicht im Menü Neuer Editor angezeigt**: `contextMenuWidget` fehlt
  `markup_editor_menu` oder die Konfiguration wurde registriert *nachdem)* Editor geöffnet wurde (Konfiguration wird gelesen)
  Einmal beim Editor-Aufbau registrieren (beim Laden der App).
- **Element wird an der falschen** angezeigt: `target` Anker wird nicht aufgelöst. Anker wird an einem Element verankert, das
im Menü Neu vorhanden ist (z. B. `Cut`).
- **Änderung „funktioniert“ dann verschwindet**: Sie haben das DOM mutiert. Verwenden eines Befehls (Schreiben) oder einer Dekoration
Stattdessen (Stil).
- **CSS hat keine Auswirkungen**: Es ist auf Seitenebene, der Editor befindet sich in einem Schatten-DOM. Verwenden von `registerPlugin({ css })`.
- **Unsichere Wachen werfen**: Muster wie `if (!tcx.curEditor && !tcx.curEditor.editor)` auswerten
  `.editor` auf ein falsches Objekt. Schützen Sie stattdessen `guides.editor` Funktionen:
  `if (!guides?.editor) return;`.
- **Versuch, App-Shell-Menüs zu migrieren**: Repository-/Zuordnungs-/Dateimenüs sind nicht die Editor-Arbeitsfläche;
Belassen Sie sie auf ihren alten Widget-IDs.

## Verifizierungs-Checkliste

- Kontextmenüelemente werden sowohl in den **des** als auch im MarkupEditor angezeigt.
- Elemente landen an der erwarteten Position.
- Benutzerdefinierte `eventid` werden `controller[eventid]` ausgeführt; globale Schlüssel lösen den integrierten Befehl aus.
- Statuslesevorgänge geben nach der Eingabe/Wiedergabe korrekte Werte zurück (Modell, nicht veraltetes DOM).
- Inhaltsschreibvorgänge *nach dem Speichern und erneuten Öffnen beibehalten*.
- Dekorationen überleben ein Rendering.
- Shadow-DOM-CSS wird im Editor sichtbar angewendet.
- Brände über `AUTHOR_SAVE_KEY` speichern und schmutzigen Zustand beseitigen.
- `readOnly` Elemente verhalten sich in gesperrten Inhalten korrekt.
- Vorschau oder nebeneinander; beabsichtigte schreibgeschützte DOM-Arbeit bleibt unverändert.
- `grep -rn "tcx.curEditor" src` ist sauber (oder nur der dokumentierte, absichtliche Rest).
- Plug-ins genau einmal registriert, innerhalb von `guides.ready`.


## Empfohlene Rollout-Sequenz

1. **Bootstrap**: Schließt die Einrichtung in `guides.ready` ein; registriert Plug-ins bedingungslos und fügt nur `version`-Gating für *Runtime* Aktionen hinzu (für Details siehe [Plug-in-Registrierung und Runtime-Gating](#plugin-registration-and-runtime-gating)).
2. **Kontextmenüoberfläche**: `markup_editor_menu` hinzufügen, `target` reparieren. Es werden jetzt Elemente angezeigt.
3. **Lesevorgänge**: Migrieren von Auswahl-/Attributlesevorgängen zu `runUtil`.
4. **Writes**: Migrieren von Mutationen zu `runCommand`; speichert in App-Ereignissen.
5. **Rendering**: Verschieben von DOM-Stilen in Dekorationen/`registerPlugin`; Verschieben von CSS in das Schatten-DOM.
6. **Harden**: Beheben Sie unsichere Wachen, entfernen Sie den Editor-Griff, überprüfen Sie auf beiden Editoren.

Sie können jeweils nur eine Oberfläche migrieren und die Legacy-Pfade weiterverwenden (Arrays + Versionsgating), sodass
Während der gesamten Transition wird der Build einer einzelnen Erweiterung auf beiden Editoren ausgeführt.

## Anhang A: Exponiertere Utils (Beispiele)

Die folgenden Utils können über `runUtil` verwendet werden.

| Dienstprogramm | Parameter → Rückgaben | Funktion |
|---|---|---|
| `getTextPos` | `(): { start, end }` | Aktuell ausgewählte Textknotengrenzen |
| `getValidElementNames` | `(ancestorLevel?): ElementName[]` | Elementnamen, die bei der aktuellen Auswahl rechtmäßig eingefügt/umschlossen werden könnten. |
| `getValidElementNamesBefore` | `(): ElementName[]` | Elementnamen sind unmittelbar vor der aktuellen Auswahl gültig. |
| `getSelectedText` | `(): string` | Ausgewählter roher Text. |
| `getSerializableAttributes` | `(): { [key]: string }` | XML-Attributzuordnung für den aktuellen Knoten, nach Attributnamen eingegeben |
| `getTagName` | `(): string \| null` | Tag-Name des aktuellen Knotens. |
| `hasSelection` | `(): boolean` | Gibt an, ob derzeit Inhalt ausgewählt ist. |
| `isSelectionEditable` | `(): boolean` | Gibt an, ob die aktuelle Auswahl bearbeitet werden kann. |
| `getAncestorPos` | `(name): number \| undefined` | Position des nächsten Vorgängers mit dem angegebenen Elementnamen aus der aktuellen Auswahl. |
| `getValidWrapNodeElementNames` | `(): ElementName[]` | Elementnamen, die für `wrapNode` bei der aktuellen Auswahl gültig sind. |
| `getValidRenameNodeElementNames` | `(): ElementName[]` | Elementnamen, in die der aktuelle Knoten rechtmäßig umbenannt werden kann. |
| `getValidSurroundElementNames` | `(): ElementName[]` | Elementnamen, die für `surroundWithElement` bei der aktuellen Auswahl gültig sind. |
| `serialize` | `(doc?): string` | Serialisiert ein ProseMirror-Dokument (oder das gesamte Dokument) in XML. |
| `getSelectedXml` | `(range?): string` | XML für die aktuelle Auswahl oder ein expliziter `{ from, to }`. |
| `getRangeXml` | `(xpaths): string` | XML für einen oder mehrere xpath-object-Bereiche (siehe xpath-Einschränkung von §8 - dies ist die Objektform, nicht die Zeichenfolgenform). |
| `mapToXpath` | `(position, doc?): XPathPosition` | Konvertiert eine Position in den Pfad des Objektformulars. |
| `inverseMap` | `(xpath \| position, doc?): number` | Konvertiert einen XPath (oder eine Position) eines Objektformulars zurück in eine Position. |
| `getAncestorsDetails` | `(): { ancestors, previousSibling, nextSibling, currNode } \| undefined` | Vorgängerkette plus direkte gleichrangige Elemente für den aktuellen Knoten. |
| `getAncestorsNames` | `(): ElementName[]` | Vorgängerkette nur als Elementnamen für den aktuellen Knoten. |
| `getPreviousSibling` | `(): ElementName \| undefined` | Name des vorherigen gleichrangigen Elements. |
| `getNextSibling` | `(): ElementName \| undefined` | Name des nächsten gleichrangigen Elements. |
| `getAncestorXpaths` | `(includeNodeAtPosition?): { tag, xpath }[]` | Vorgängerkette als `{tag, xpath}` Paare - Pfad der Objektform, nicht der `updateAttributeByXpath` Zeichenfolgenform (§8). |
| `getSelectedPlainText` | `(range?): string` | Nur-Text der aktuellen Auswahl oder ein expliziter Bereich. |
| `getDecorations` | `(): string[]` | IDs aller aktuell angewendeten Dekorationen. |
| `getResolvedDitaDocumentTitle` | `(props?): string` | Aufgelöster Anzeigetitel des DITA-Dokuments. `props`: `doc` ein bestimmtes Dokument als Ziel festzulegen `allowedPrefixElements` Elemente mit Titelpräfixen zuzulassen. |

## Anhang B: Exponiertere Befehle (Beispiele)

Die folgenden Befehle sind zusätzliche Beispiele dafür, was über `guides.editor.runCommand(name, ...args)` verfügbar gemacht wird.
Schützen Sie alle Befehle mit `guides.editor.canRunCommand(name, ...args)` zuerst, wenn sie im aktuellen Kontext nicht anwendbar sind.

| Befehl | Parameter | Funktion |
|---|---|---|
| `focusEditor` | `()` | Fokussiert den Editor. |
| `unwrapNode` | `()` | Entfernt das Element, das die aktuelle Auswahl umschließt, und behält seine untergeordneten Elemente bei. |
| `surroundWithElement` | `(elementName, attrs?, groupInline?)` | Schließt die aktuelle Auswahl in ein neues Inline-/Blockelement ein. `attrs`: XML-Attributzuordnung, die für das neue Wrapping-Element festgelegt wird. |
| `insertXml` | `(xml)` | Fügt ein XML-Fragment am Cursor ein. |
| `replaceSelectionWithXml` | `(xml)` | Ersetzt die aktuelle Auswahl durch XML. |
| `insertText` | `(text)` | Fügt Text am Cursor ein. |
| `selectNodesFromXpaths` | `(xpaths)` | Wählt einen oder mehrere Knoten unter den gegebenen Pfad-Objektformularen aus. |
| `delete` | `()` | Löscht die aktuelle Auswahl. |
| `undo` / `redo` | `()` | Standard-Rückgängig/Wiederholen. |
| `removeDecoration` | `(id)` | Entfernt eine einzelne Dekoration nach ID. |
| `clearDecorations` | `()` | Entfernt alle Dekorationen in der aktuellen geöffneten Datei. |
| `setFileReadOnly` | `(readOnly: boolean)` | Schaltet den schreibgeschützten Modus der Datei um. |
| `generateUniqueId` | `()` | Erzeugt ein eindeutiges ID-Attribut und weist es dem aktuellen Knoten zu. |