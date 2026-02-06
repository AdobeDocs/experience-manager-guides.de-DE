---
title: Komponentenzuordnung für AEM Sites
description: Erfahren Sie, wie Sie eine Komponentenzuordnung für AEM Sites vornehmen
feature: Installation
role: Admin
level: Experienced
exl-id: f59e3ad5-bf9c-468d-aab7-144c8c2335ac
source-git-commit: beb1ca15fdfb0e7ea30e6e685ac67a2a398cc064
workflow-type: tm+mt
source-wordcount: '1042'
ht-degree: 0%

---

# Komponentenzuordnung für AEM Sites

In diesem Artikel werden die verschiedenen Aspekte der Komponentenzuordnung für AEM Sites (Verwendung der Zuordnung zusammengesetzter Komponenten) behandelt.

## Zuordnungsregeln für Komponenten

Verwenden Sie ein JSON-Array von Regeln (Ihre `componentmapping.json`), um HTML in Komponenten zu konvertieren. Halten Sie die Regeln so einfach, explizit und spezifisch wie möglich.

### Targeting des HTML-Elements und seiner Klasse

- Schreiben Sie den HTML-Tag-Namen in `name`.
- Schließen Sie die CSS-Klasse ein, die auf dieses Element in `class` angewendet wird, falls die Klasse vorhanden ist.
Zum Beispiel:

  ```html
  <div class ="sample-class">
  <p> Sample html element </p>
  </div>
  ```

  ```json
  {
  "name": "div",
  "class": "sample-class",
  "resourceType": "guides-components/components/table",
  "attributeMap": []
  }
  ```

Stellen Sie beim Definieren der oben genannten Elemente Folgendes sicher:

- `name` kann eine kommagetrennte Liste sein (z. B. `"h1, h2"`).
- `class` muss im Element vorhanden sein (alle aufgelisteten Klassen müssen übereinstimmen).
- `resourceType` gibt an, dass Sie die `table`-Komponente verwenden möchten. Das `guides-components` Paket ist ein von Guides bereitgestellter vorkonfigurierter Service. Sie können bei Bedarf auch andere Komponentenpakete wie `core/wcm/` verwenden.

### Verwenden Sie attributeMap, um Eigenschaften auf dem JCR-Knoten zu speichern

Fügen Sie `attributeMap` Einträge hinzu, um Eigenschaften auf dem Ausgabeknoten festzulegen. Jeder Eintrag erzeugt `attrs[to] = value`.
Häufige Muster:

```json
// copy an attribute
{ "attribute": "src", "to": "image-src" }
// read content or tag name
{ "from": "textContent", "to": "jcr:title" }
{ "from": "outerHTML",  "to": "text" }
{ "from": "innerHTML",  "to": "text" }
{ "from": "name",       "to": "type" }  // the tag name, e.g., "h2"
// constant value
{ "value": true, "to": "textIsRich" }
```

Nachfolgend finden Sie ein Beispiel für die Verwendung von HTML zu JSON für ein Bildelement.

```html
<img src="/content/dam/aemg-docs/tragopan.svg" class="cmp-image__image" itemprop="contentUrl" data-cmp-hook-image="image" alt="">
```

```json
{
    "name": "img",
    "resourceType": "core/wcm/components/image/v2/image",
    "attributeMap": [
      {
        "from": "src",
        "to": "fileReference"
      },
      {
        "value": ["fileReference"],
        "to": "path-attributes"
      }
    ]
  }
```

### Normalisieren von Pfaden über einen dedizierten Eintrag

Wenn Sie Werte normalisieren (absolute Werte festlegen) möchten, deklarieren Sie mithilfe von , welche Attributschlüssel normalisiert werden sollen:

```json
{
  "value": ["text"],
  "to": "path-attributes"
}
```

Achten Sie auf die folgenden wichtigen Punkte:

- Fügen Sie die Liste der Eigenschaftsnamen, die bereinigt werden sollen, `value` (z. B. `["text"]` oder `["href", "src"]`).
- Das System normalisiert alle Werte, die unter diesen Eigenschaftsnamen gefunden werden, wenn die endgültige Komponente erstellt wird.


### Extrahieren von HTML-Werten vor der Aufspaltung in Komponenten

Verwenden Sie `from`, um anzugeben, wie ein Wert aus dem Element gelesen werden soll, bevor das Dokument in separate Komponenten aufgeteilt wird:

- `"textContent"`: Nur-Text des Elements
- `"outerHTML"`: Das Element und sein inneres Markup
- `"innerHTML"`: Nur das innere Markup des Elements
- Jede andere Zeichenfolge: als Attributname behandelt (z. B. `"src"`, `"href"`)


Beispiele:

```json
{ "from": "textContent", "to": "jcr:title" }
{ "from": "outerHTML",  "to": "text" }
{ "from": "innerHTML",  "to": "snippet" }
{ "from": "src",        "to": "image#src" }
```

### Minimales End-to-End-Beispiel in componentMapping.json

```json
[
  {
    "name": "h1, h2",
    "class": "topic-title",
    "resourceType": "core/wcm/components/title/v2/title",
    "attributeMap": [
      { "from": "textContent", "to": "text" },
      { "from": "name",        "to": "type" }
    ]
  },
  {
    "name": "img",
    "class": "hero",
    "resourceType": "weretail/components/content/heroimage",
    "attributeMap": [
      { "from": "src", "to": "image#src" },
      { "value": ["image#src"], "to": "path-attributes" }
    ]
  },
  {
    "name": "#element",
    "resourceType": "core/wcm/components/text/v2/text",
    "attributeMap": [
      { "from": "outerHTML", "to": "text" },
      { "value": true,        "to": "textIsRich" }
    ]
  }
]
```

Definieren Sie das Zielelement und die Klasse, verwenden Sie `attributeMap` zum Festlegen der Knoteneigenschaften, fügen Sie einen `path-attributes` Eintrag hinzu, um Pfade zu normalisieren, und wählen Sie die richtige `from` für die Werte aus, die Sie extrahieren möchten. Die oben verwendete `heroimage` ist eine Komponente in einer `we-retail`.

**Hinweis**: Es ist wichtig, den standardmäßigen Rich-Text zu besprechen und die Elemente zu identifizieren, für die er verwendet wird.

## Erstellen einer benutzerdefinierten Komponente

Erfahren Sie, wie Sie eine benutzerdefinierte Tabellenkomponente erstellen, die Bilder in ihren Zellen anzeigt. Dieser Ansatz gewährleistet ein sauberes, wiederverwendbares Design für dynamische Inhalte. Es behandelt, was Sie erstellen werden, warum es effektiv ist, die wichtigsten Voraussetzungen, allgemeines Design und mehr.

### Was Sie bauen werden

Eine benutzerdefinierte Tabellenkomponente, die HTML-Tabelleninhalte akzeptiert und alle darin enthaltenen `<img>` durch die Ausgabe der AEM-Kernbildkomponente ersetzt. Auf diese Weise können Sie die Funktionen des Kernbilds (responsive Bilder, Alt-Handhabung, Barrierefreiheit) wiederverwenden und gleichzeitig die volle Kontrolle über das Tabellen-Markup behalten.
Mit diesem Ansatz können Sie andere benutzerdefinierte Komponenten für Ihre AEM-Site erstellen (mithilfe der Zuordnung zusammengesetzter Komponenten).

### Gründe für diesen Ansatz

- **Wiederverwenden**: Nutzen Sie das ausgereifte Verhalten des Kernbilds, anstatt es erneut zu implementieren.
- **Konsistenz**: Bilder in Ihrer Tabelle verhalten sich genauso wie Bilder an anderen Stellen auf der Website.
- **Server-seitig**: Bilder werden auf dem Server für Leistung, SEO und Barrierefreiheit gerendert.

### Voraussetzungen

- AEM SDK wird ausgeführt und dieses Projekt ist ausgecheckt.
- Auf Ihrer AEM-Instanz installierte Kernkomponenten.
- Maven zum Erstellen und Bereitstellen verfügbar.

### Hochrangiges Design

- Der Autor stellt HTML für die Tabelle im Komponentendialogfeld bereit.
- Ein Sling-Modell analysiert diesen HTML, findet `<img>` Tags und ruft für jedes Bild einen Service auf, der die Kernbildkomponente Server-seitig rendert.
- Das Modell tauscht die ursprüngliche `<img>` gegen die HTML des erfassten Kernbilds aus und übergibt die fertige HTML zur Ausgabe an HTL.

Die Tabelle wird einmal ausgegeben und enthält bereits Kernbild-Markup. Es ist keine Client-seitige DOM-Manipulation erforderlich.

### Ordnerstruktur und Schlüsseldateien (in diesem Repository)

- Komponenten-HTL und Client-Bibliotheken: `ui.apps/src/main/content/jcr_root/apps/guides-components/components/table/`
   - `table.html` (HTL-Renderer)
   - `_cq_editConfig.xml` (Listener aktualisieren)
   - `clientlibs/` mit `css.txt`, `js.txt`, `css/table.css`, `js/table.js`
- Sling-Modell: `core/src/main/java/com/adobe/guides/aem/components/core/models/TableModel.java`
- Bild-Rendering-Service: `core/src/main/java/com/adobe/guides/aem/components/core/services/ImageComponentRenderer.java`

### Implementierungsschritte

**Definieren der Tabellenkomponente (Komponentenknoten)**

Erstellen Sie die Komponente unter `apps/guides-components/components/table`. Wenn Sie noch keinen haben, fügen Sie einen minimalen `.content.xml` wie unten ein, um ihn im Seitenbereich zu registrieren.

```xml
<?xml version="1.0" encoding="UTF-8"?>
<jcr:root xmlns:sling="http://sling.apache.org/jcr/sling/1.0"
          xmlns:jcr="http://www.jcp.org/jcr/1.0"
          jcr:primaryType="cq:Component"
          jcr:title="Table"
          componentGroup="Guides - Custom"/>
```

Gibt AEM an, dass dies eine Komponente ist, die Autorinnen und Autoren zu Seiten hinzufügen können.

**Mit HTL rendern und Stile einschließen**

Verwenden Sie ein Sling-Modell und geben Sie den verarbeiteten HTML aus. Schließen Sie Ihre clientlib-Kategorie für CSS/JS ein.

```html
<sly data-sly-use.model="com.adobe.guides.aem.components.core.models.TableModel"
     data-sly-use.clientLib="/libs/granite/sightly/templates/clientlib.html">
</sly>
<sly data-sly-call="${clientLib.css @ categories='guides-components.table'}"></sly>
<sly data-sly-test="${wcmmode.edit && !model.hasContent}">
  <div class="cq-placeholder" data-emptytext="${component.title}"></div>
</sly>
<div data-sly-test="${model.hasContent}"
     class="gu-table-wrapper ${model.enableResponsive ? 'gu-table--responsive' : ''} gu-table--style-${model.tableStyle}"
     id="${model.componentId}">
  ${model.processedTableHtml @ context='unsafe'}
</div>
```

Das Modell gibt den vollständigen HTML zurück, wobei das Kernbild bereits gerendert ist, sodass HTL es einfach druckt.

**Fügen Sie das Sling-Modell hinzu, um HTML zu verarbeiten und das Kernbild zu rendern**

Das Modell liest Dialogfelder, analysiert die HTML-Tabelle, findet jede `<img>` und ersetzt sie über einen Service durch Core Image HTML.

Im Folgenden finden Sie einige wichtige Know-hows für `TableModel`:

- Liest `tableHtml`, `enableResponsive` und `tableStyle` aus den Ressourceneigenschaften.
- Verwendet Jsoup, um HTML sicher zu analysieren und zu bearbeiten.
- Ruft `ImageComponentRenderer` auf, um das Kernbild zu rendern und die HTML zu erfassen.
- Behält CSS-Klassen und -Stile aus dem ursprünglichen `<img>` bei.
- Normalisiert DAM-Pfade (entfernt `/jcr:content/renditions/*`).

```java
@Model(adaptables = {Resource.class, SlingHttpServletRequest.class},
       defaultInjectionStrategy = DefaultInjectionStrategy.OPTIONAL)
public class TableModel {
  @ValueMapValue private String tableHtml;
  @ValueMapValue private boolean enableResponsive;
  @ValueMapValue private String tableStyle;
  @OSGiService private ImageComponentRenderer imageRenderer;
  // ...
  @PostConstruct
  protected void init() {
    // parse HTML, for each <img> build image props (fileReference, alt, title)
    // call imageRenderer.renderImageComponent(...)
    // replace <img> with returned Core Image HTML
  }
  public String getProcessedTableHtml() { /* return final HTML */ }
}
```

Dadurch wird die Logik auf dem Server zentralisiert und das Verhalten des Kernbilds wiederverwendet.

**Rendern des Kernbilds über einen Service (Server-seitiges Einschließen)**

`ImageComponentRenderer` rendert die Kernbildkomponente und erfasst die Ausgabe. IT

- Schließt eine Ressource ein, die `core/wcm/components/image/v2/image` erzwingt.
- verwendet `RequestDispatcher#include` zum Rendern.
- Erfasst die Antwort als Zeichenfolge.

```java
@Component(service = ImageComponentRenderer.class)
public class ImageComponentRenderer {
  private static final String IMAGE_RESOURCE_TYPE = "core/wcm/components/image/v2/image";
  public String renderImageComponent(Resource base, Map<String,Object> props,
                                     SlingHttpServletRequest req, SlingHttpServletResponse resp) {
    // create wrapped resource with IMAGE_RESOURCE_TYPE and props
    // dispatcher.include(...) with a response wrapper to capture HTML
    // return captured HTML
  }
}
```

Auf diese Weise **Sie das** Bild überall dort ablegen, wo Sie es benötigen, nicht nur als untergeordnete Komponente.

**Client-Bibliotheken**

Erstellen Sie eine Client-Bibliothek für kleine Stile oder zukünftige JS-Dateien. Die obige HTL lädt die `guides-components.table`.

```java
clientlibs/css.txt
  #base=css
  table.css
clientlibs/js.txt
  #base=js
  table.js
  
```

Dadurch bleiben die Stile/Skripte modular und auffindbar.

**Dialogfelder (Autoreneingaben)**

Dialogfeld mit mindestens den folgenden Eigenschaften hinzufügen:

- **Table HTML**: `./tableHtml` (textarea); die HTML der Tabelle.
- **Responsiv aktivieren**: `./enableResponsive` (Kontrollkästchen); schaltet eine responsive Wrapper-Klasse um.
- **Tabellenstil**: `./tableStyle` (Auswählen); wendet eine Stilmodifikatorklasse an.

Diese ordnen 1:1 den Eigenschaften des Sling-Modells zu und steuern das Rendering.

**Lassen Sie die Komponente in Vorlagen zu**

Bearbeiten Sie im Vorlageneditor die Layout-Container-Richtlinie > Zugelassene Komponenten > Aktivieren Sie Ihre Tabellenkomponente unter **Handbücher - Benutzerdefiniert**.

Die Autoren können erst dann Komponenten hinzufügen, wenn die Richtlinien dies zulassen.

## Tipps zur Inhaltserstellung

- Fügen Sie eine gültige HTML für die Tabelle ein. Das Modell bereinigt und passt Bild-URLs an.
- Verwenden Sie DAM-Asset-Pfade für Bilder. Die Ausgabedarstellungen werden auf den ursprünglichen Asset-Pfad normalisiert.
- Geben Sie alternativen Text in der HTML an, wenn möglich. Andernfalls werden Bilder als dekorativ markiert.

## Begrenzungen

- Der Dienst erzwingt Core Image v2. Um zwischen Versionen zu wechseln, aktualisieren Sie `IMAGE_RESOURCE_TYPE`.
- Für das synthetische Rendering ersetzt das Modell die generierten `.coreimg.`-URLs des Kernbilds durch direkte DAM-Pfade und entfernt `srcset`, um fehlerhafte URLs zu vermeiden.
- Das Rendering erfolgt einmalig auf dem Server. JavaScript ist optional.

## Kurzanleitung (Implementierung)

- HTML: `ui.apps/.../components/table/table.html`
- Clientlibs: `ui.apps/.../components/table/clientlibs/`
- Modell: `core/.../models/TableModel.java`
- Service: `core/.../services/ImageComponentRenderer.java`

Dieses Muster zeigt, wie Sie eine benutzerdefinierte Komponente Server-seitig mit einer Kernkomponente erstellen, wobei Sie Ihr Markup beibehalten und die Kernlogik wiederverwenden.
