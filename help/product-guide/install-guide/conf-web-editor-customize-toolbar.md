---
title: Symbolleiste anpassen
description: Erfahren Sie, wie Sie die Symbolleiste anpassen
exl-id: 14a82c7e-5c07-43a8-bd9e-b221d80f6d05
feature: Web Editor Configuration
role: Admin
level: Experienced
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '894'
ht-degree: 0%

---

# Symbolleiste anpassen {#id172FB00L0V6}

Standardmäßig werden im Web Editor die gängigsten redaktionellen Funktionen bereitgestellt, die für jeden DITA-Editor erforderlich sind. Funktionen wie das Einfügen von Elementen des Typs Liste \(nummeriert oder mit Aufzählungszeichen\), Querverweis, Inhaltsverweis, Tabelle, Absatz und Zeichenformatierung sind im Editor verfügbar. Zusätzlich zu diesen grundlegenden Elementen können Sie den Web-Editor anpassen, um Elemente einzufügen, die in Ihrer Authoring-Umgebung verwendet werden.

Es gibt zwei Möglichkeiten, die Symbolleiste des Web-Editors anzupassen:

- Hinzufügen neuer Funktionen zur Symbolleiste

- Entfernen vorhandener Funktionen aus der Symbolleiste


## Hinzufügen einer Funktion in der Symbolleiste

Das Hinzufügen einer Funktion zum Webeditor umfasst zwei Hauptaufgaben: das Hinzufügen eines Symbols für die Funktion in der Datei *ui\_config.json* und das Hinzufügen der Hintergrundfunktion in JavaScript.

**Fügen Sie ein Symbol in der Symbolleiste hinzu**

Führen Sie die folgenden Schritte aus, um der Symbolleiste des Web-Editors eine Funktion hinzuzufügen:

1. Melden Sie sich bei AEM an und öffnen Sie den CRXDE Lite-Modus.

1. Navigieren Sie zur Standardkonfigurationsdatei, die unter folgendem Speicherort verfügbar ist:

   `/libs/fmdita/clientlibs/clientlibs/xmleditor/ui_config.json`

1. Erstellen Sie eine Kopie der Standardkonfigurationsdatei an folgendem Speicherort:

   `/apps/fmdita/xmleditor/ui_config.json`

1. Navigieren Sie zur Datei &quot;`ui_config.json`&quot; und öffnen Sie sie im Knoten &quot;`apps`&quot;, um sie zu bearbeiten.

1. Fügen Sie in der Datei `ui_config.json` die Definition der neuen Funktion im Abschnitt &quot;Symbolleisten&quot;hinzu. In der Regel können Sie eine neue Schaltflächengruppe für Symbolleisten erstellen und eine oder mehrere Schaltflächen der Symbolleiste hinzufügen. Sie können auch eine neue Symbolleistenschaltfläche innerhalb einer vorhandenen Symbolleistengruppe hinzufügen. Die folgenden Details sind erforderlich, um eine neue Symbolleistengruppe zu erstellen:

   - **type:**Geben Sie `blockGroup` als `type` -Wert an. Dieser Wert gibt an, dass Sie eine Blockgruppe erstellen, die eine oder mehrere Symbolleistengruppen enthalten würde.

   - **extraclass:** Name der Klasse(n), getrennt durch Leerzeichen.

   - **Elemente:** Geben Sie die Definition aller Gruppen in der Symbolleiste an. Jede Gruppe kann ein oder mehrere Symbolleistensymbole enthalten. Um Symbole in einer Symbolleistengruppe zu definieren, müssen Sie das Attribut `type` innerhalb von `items` erneut definieren und dessen Wert auf `buttonGroup` setzen. Geben Sie einen oder mehrere Klassennamen in der Eigenschaft `extraclass` an. Geben Sie den Funktionsnamen in der Eigenschaft `label` an. Das folgende Codefragment aus der Datei `ui_config.json` zeigt die Definition des Haupt-Symbolleistenblocks gefolgt von der Definition `buttonGroup`:

     ```json
     "toolbar": {    
       "type": "blockGroup",    
       "extraclass": 
       "toolbar operations",    
         "items": [      
           {        
             "type": "buttonGroup",        
             "extraclass": "left-controls",        
             "label": "Left Controls",        
             "items": [
     ```

     In der Sammlung `items` müssen Sie die Definition für ein oder mehrere Symbolleistensymbole angeben.
Sie müssen die folgenden Eigenschaften definieren, um ein Symbolleistensymbol hinzuzufügen:

   - **type:** Geben Sie `button` als den Wert `type` an. Dieser Wert gibt an, dass Sie eine Symbolleistenschaltfläche hinzufügen.

   - **Symbol:** Geben Sie den Namen des Coral-Symbols an, das Sie in der Symbolleiste verwenden möchten.

   - **variant:** Geben Sie `quiet` als `variant` -Wert an.

   - **title:** Geben Sie die QuickInfo für das Symbol an.

   - **on-click:** Geben Sie den Befehlsnamen an, der für die Funktion in der JavaScript-Datei definiert ist. Wenn für Ihren Befehl Eingabeparameter erforderlich sind, geben Sie den Befehlsnamen wie folgt an:

     ```JavaScript
     "on-click": {"name": "AUTHOR_INSERT_ELEMENT", "args": "simpletable"}
     ```

   - **Anzeigen oder Ausblenden:** Wenn Sie die Eigenschaft `show` definieren, geben Sie die Modi an, in denen das Symbol angezeigt wird. Mögliche Werte sind - `@isAuthorMode`, `@isSourceMode`, `@isPreviewMode`, `true` \(in allen Modi anzeigen\) oder `false` \(in allen Modi ausblenden\).

   Anstelle von `show` können Sie auch die Eigenschaft `hide` definieren. Die möglichen Werte sind mit denen in der Eigenschaft `show` identisch, mit dem einzigen Unterschied, dass das Symbol für den angegebenen Modus nicht angezeigt wird.

1. Erstellen Sie einen Ordner *clientlib* und fügen Sie Ihren JavaScript in diesen Ordner ein.

1. Aktualisieren Sie die categories-Eigenschaft des Ordners *clientlib* , indem Sie ihm den Wert *apps.fmdita.xml\_editor.page\_overrides* zuweisen.

1. Speichern Sie die Datei *ui\_config.json* und laden Sie den Web Editor neu.


**JavaScript-Codebeispiele**

In diesem Abschnitt finden Sie zwei Beispiele für JavaScript-Code, die Ihnen bei den ersten Schritten mit dem Hinzufügen benutzerdefinierter Funktionen helfen. Das folgende Beispiel zeigt die AEM Guides-Versionsnummer, wenn ein Benutzer in der Symbolleiste auf das Symbol Version anzeigen klickt.

Fügen Sie einer JavaScript-Datei den folgenden Code hinzu:

```JavaScript
/**
* This file contains an example to show AEM Guides version 
* number when a user clicks on the Show Version icon in the toolbar. 
* Step 1. Create a clientlib folder and add save a file with your *JavaScript code into this folder. A code sample is shared below.
* Step 2: Update the categories property of the clientlib folder by *assigning it the value of 
* "apps.fmdita.xml_editor.page_overrides".
* Step 3: Add the feature in the ui_config.json file as shown after the *sample code. Save the ui_config.json file and reload the Web Editor
 */

(function (window) {
  "use strict";

  window.addEventListener('DOMContentLoaded', function () {
    fmxml.ready(function () {
      fmxml.eventHandler.subscribe({
        key: 'user.alert',
        next: function next() {
          alert("AEM Guides version x.x");
        }
      });
    });
  });
})(window);
```

Fügen Sie die Funktion in der Datei ui\_config.json wie folgt hinzu:

```json
 {
      "type": "button",
      "icon": "alert",
      "title": "About AEM Guides",
      "variant": "quiet",

  "show": "true",
      "on-click": "user.alert"
  } 
```

Das folgende Beispiel zeigt, wie Sie den Status eines Dokuments in eine aktive Datei in &quot;In Review&quot;ändern.

```JavaScript
/**
* This file contains an example to set the document state of an active *open documen to "In-Review". 
* Step 1. Create a clientlib folder and add save a file with your *JavaScript code into this folder. A code sample is shared below.
* Step 2: Update the categories property of the clientlib folder by *assigning it the value of 
* "apps.fmdita.xml_editor.page_overrides".
* Step 3: Add the feature in the ui_config.json file as shown after the *sample code. Save the ui_config.json file and reload the Web Editor
 */

(function (window) {
  "use strict";

  //Wait for the page has been completely loaded 

  window.addEventListener('DOMContentLoaded', function () {

    //Wait for the xml editor to start
    fmxml.ready(function () {

      //Subscribe to 'user.docstate.to.in-review' event
      fmxml.eventHandler.subscribe({
        key: 'user.docstate.to.in-review',
        next: function next() {
          var docstate = "In-Review"; // New docstate name
          var filePath = fmxml.curEditor.filePath; 
// Get the file path of active open file
          if (filePath) {
            //Call API to change the doc state
            $.ajax({
              type: 'POST',
              url: '/bin/fmdita/states',
              data: {
                paths: filePath,
                operation: "setdocstates",
                docstate: docstate
              }
            }).fail(function (xhr, textStatus, errorThrown) {
              console.error("Cannot update docstate to " + docstate);
            }).success(function (data) {
              console.log('docstate updated to ' + docstate);
            });
          }
        }
      });
    });
  });
})(window);
```

Fügen Sie die Funktion in der Datei ui\_config.json wie folgt hinzu:

```json
 {
      "type": "button",
      "icon": "actions",
      "title": "Change document state to In-Review",
      "variant": "quiet",
      "show": "true",
      "on-click": "user.docstate.to.in-review"
    } 
```

## Entfernen einer Funktion aus der Symbolleiste

Manchmal möchten Sie nicht alle derzeit im Web-Editor verfügbaren Funktionen bereitstellen. In diesem Fall können Sie die unerwünschte Funktion aus der Symbolleiste des Web-Editors entfernen.

Führen Sie die folgenden Schritte aus, um unerwünschte Funktionen aus der Symbolleiste zu entfernen:

1. Melden Sie sich bei AEM an und öffnen Sie den CRXDE Lite-Modus.

1. Navigieren Sie zur Standardkonfigurationsdatei, die unter folgendem Speicherort verfügbar ist:.

   `/libs/fmdita/clientlibs/clientlibs/xmleditor/ui_config.json`

1. Erstellen Sie eine Kopie der Standardkonfigurationsdatei an folgendem Speicherort:

   `/apps/fmdita/xmleditor/ui_config.json`

1. Navigieren Sie zur Datei &quot;`ui_config.json`&quot; und öffnen Sie sie im Knoten &quot;`apps`&quot;, um sie zu bearbeiten.
Die Datei `ui_config.json` enthält drei Abschnitte:

- **toolbars:**   Dieser Abschnitt enthält die Definition aller in der Symbolleiste des Editors verfügbaren Funktionen wie &quot;Nummerierte Liste einfügen/entfernen&quot;, &quot;\(Datei\) schließen&quot;, &quot;Speichern&quot;, &quot;Kommentare&quot;und mehr.

- **Tastaturbefehle:**   Dieser Abschnitt enthält die Definition von Tastaturbefehlen, die einer bestimmten Funktion im Editor zugewiesen sind.

- **templates:**   Dieser Abschnitt enthält die vordefinierte Struktur von DITA-Elementen, die Sie in Ihrem Dokument verwenden können. Standardmäßig enthält der Abschnitt &quot;Vorlagen&quot;Vorlagendefinitionen für Absätze, einfache Tabellen, Tabellen und Textelemente. Sie können eine Vorlagendefinition für jedes Element erstellen, indem Sie eine gültige XML-Struktur für das gewünschte Element hinzufügen. Wenn Sie beispielsweise ein `p` -Element mit jedem neuen `li` -Element in einer Liste hinzufügen möchten, können Sie den folgenden Code am Ende des Vorlagenabschnitts hinzufügen, um dies zu erreichen:

```HTML
"li": "<li><p></p></li>"
```

1. Entfernen Sie im Abschnitt &quot;Symbolleisten&quot;den Eintrag der Funktion, die Sie Ihren Benutzern nicht zur Verfügung stellen möchten.

1. Speichern Sie die Datei *ui\_config.json* und laden Sie den Web Editor neu.


**Übergeordnetes Thema:**[ Web-Editor anpassen](conf-web-editor.md)
