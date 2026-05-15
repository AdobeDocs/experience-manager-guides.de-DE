---
title: Symbolleiste anpassen
description: Erfahren Sie, wie Sie die Symbolleiste anpassen
exl-id: 14a82c7e-5c07-43a8-bd9e-b221d80f6d05
feature: Web Editor Configuration
role: Admin
level: Experienced
TQID: https://experienceleague.adobe.com/eZq4BTrrbSDDDuYas-D4iCw4WS6Pvzas2AhBPl67LKo
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2:
  - id: ab01a588-7dea-43f2-a699-0b3f128465d6
  - id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
subfeature_v2:
  - id: ad602516-aca3-4247-9ae8-f393d958efa9
  - id: b0521e56-a0b2-40b6-bf47-ebc98751f9ba
  - id: d4f22c6d-7923-41e5-9da3-527ff8df4bc8
  - id: f89f75b0-cf2e-4e96-aec8-fe8c39cbd0ef
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 967
ht-degree: 0%

---

# Symbolleiste anpassen {#id172FB00L0V6}

Standardmäßig werden im Lieferumfang des Web-Editors die gängigsten redaktionellen Funktionen enthalten sein, die von einem DITA-Editor benötigt werden. Funktionen wie das Einfügen von Elementen des Typs \(nummeriert oder mit Aufzählungszeichen\), Querverweis, Inhaltsreferenz, Tabelle, Absatz und Zeichenformatierung sind im Editor verfügbar. Zusätzlich zu diesen grundlegenden Elementen können Sie den Web-Editor so anpassen, dass Elemente eingefügt werden, die in Ihrer Autorenumgebung verwendet werden.

>[!NOTE]
>
> Bei der Migration von der alten Benutzeroberfläche zur neuen AEM Guides-Benutzeroberfläche (anwendbar ab Version 2502 und 5.0 von AEM Guides) müssen Aktualisierungen an `ui_config` in flexiblere und modulare Benutzeroberflächenkonfigurationen konvertiert werden. Dieses Framework hilft bei der nahtlosen Übernahme von Änderungen in die editor_toolbar und ggf. andere Target-Widgets. Weitere Informationen finden Sie unter [Übersicht über die Konfiguration der Convert-Benutzeroberfläche](https://experienceleague.adobe.com/de/docs/experience-manager-guides-learn/videos/advanced-user-guide/conver-ui-config).

Es gibt zwei Möglichkeiten, die Symbolleiste des Web-Editors anzupassen:

- Hinzufügen einer neuen Funktion zur Symbolleiste

- Entfernen vorhandener Funktionen aus der Symbolleiste


## Funktion in der Symbolleiste hinzufügen

Das Hinzufügen einer Funktion zum Web-Editor umfasst zwei Hauptaufgaben: Hinzufügen eines Symbols für die Funktion in der Datei *ui\_config.json* und Hinzufügen der Hintergrundfunktion in JavaScript.

**Fügen Sie ein Symbol in der Symbolleiste hinzu**

Führen Sie die folgenden Schritte aus, um der Symbolleiste des Web-Editors eine Funktion hinzuzufügen:

1. Melden Sie sich bei AEM an und öffnen Sie den CRXDE Lite-Modus.

1. Navigieren Sie zu der standardmäßigen Konfigurationsdatei, die am folgenden Speicherort verfügbar ist:

   `/libs/fmdita/clientlibs/clientlibs/xmleditor/ui_config.json`

1. Erstellen Sie eine Kopie der Standardkonfigurationsdatei am folgenden Speicherort:

   `/apps/fmdita/xmleditor/ui_config.json`

1. Navigieren Sie zur `ui_config.json` und öffnen Sie sie im Knoten `apps` zur Bearbeitung.

1. Fügen Sie in der `ui_config.json`-Datei die Definition der neuen Funktion im Abschnitt Symbolleisten hinzu. In der Regel können Sie eine neue Gruppe von Symbolleistenschaltflächen erstellen und ihr eine oder mehrere Symbolleistenschaltflächen hinzufügen. Sie können auch eine neue Symbolleistenschaltfläche zu einer vorhandenen Symbolleistengruppe hinzufügen. Zum Erstellen einer neuen Symbolleistengruppe sind die folgenden Details erforderlich:

   - **type:**&#x200B;Geben Sie `blockGroup` als `type` an. Dieser Wert gibt an, dass Sie eine Blockgruppe erstellen, die eine oder mehrere Symbolleistengruppen enthalten würde.

   - **extraClass:** Name der Klasse(n), durch Leerzeichen getrennt.

   - **Elemente:** Geben Sie die Definition aller Gruppen in der Symbolleiste an. Jede Gruppe kann ein oder mehrere Symbolleistensymbole enthalten. Um Symbole innerhalb einer Symbolleistengruppe zu definieren, müssen Sie erneut das `type` Attribut innerhalb der `items` definieren und deren Wert auf `buttonGroup` festlegen. Geben Sie einen oder mehrere Klassennamen in der `extraclass` Eigenschaft an. Geben Sie den Funktionsnamen in der Eigenschaft `label` an. Der folgende Ausschnitt aus der `ui_config.json` zeigt die Definition für den Haupt-Symbolleistenblock, gefolgt von der `buttonGroup` Definition:

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

     Innerhalb der `items` müssen Sie die Definition für ein oder mehrere Symbolleistensymbole angeben.
Sie müssen die folgenden Eigenschaften definieren, um ein Symbolleistensymbol hinzuzufügen:

   - **type:** Geben Sie `button` als `type` an. Dieser Wert gibt an, dass Sie eine Symbolleistenschaltfläche hinzufügen.

   - **Symbol** Geben Sie den Namen des Coral-Symbols an, das Sie in der Symbolleiste verwenden möchten.

   - **variant:** Geben Sie `quiet` als `variant` an.

   - **title:** Geben Sie die QuickInfo für das Symbol an.

   - **on-click:** Geben Sie den Befehlsnamen an, der für die Funktion in der JavaScript-Datei definiert ist. Wenn für den Befehl Eingabeparameter erforderlich sind, geben Sie den Befehlsnamen wie folgt an:

     ```JavaScript
     "on-click": {"name": "AUTHOR_INSERT_ELEMENT", "args": "simpletable"}
     ```

   - **Einblenden oder ausblenden:** Wenn Sie die `show` Eigenschaft definieren, geben Sie die Modi an, in denen das Symbol angezeigt wird. Zu den möglichen Werten gehören - `@isAuthorMode`, `@isSourceMode`, `@isPreviewMode`, `true` \(Anzeige in allen Modi\) oder `false` \(Ausblenden in allen Modi\).

   Anstelle von `show` können Sie auch die Eigenschaft `hide` definieren. Die möglichen Werte sind dieselben wie in `show` Eigenschaft, mit dem einzigen Unterschied, dass das Symbol für den angegebenen Modus nicht angezeigt wird.

1. Erstellen Sie *Ordner &quot;*&quot; und fügen Sie Ihre JavaScript diesem Ordner hinzu.

1. Aktualisieren Sie die Kategorieneigenschaft des Ordners *clientlib* durch Zuweisen des Werts &quot;*.fmdita.xml\_editor.page\_overrides*.

1. Speichern Sie die *ui\_config.json*-Datei und laden Sie den Web-Editor neu.


**JavaScript-Code-Beispiele**

In diesem Abschnitt finden Sie zwei Beispiele für JavaScript-Code, die Ihnen bei den ersten Schritten beim Hinzufügen benutzerdefinierter Funktionen helfen. Das folgende Beispiel zeigt die AEM Guides-Versionsnummer, wenn ein Benutzer auf das Symbol Version anzeigen in der Symbolleiste klickt.

Fügen Sie den folgenden Code zu einer JavaScript-Datei hinzu:

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

Das folgende Beispiel zeigt, wie der Status eines Dokuments in einer aktiven Datei in „In Überprüfung“ geändert wird.

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

## Funktion aus der Symbolleiste entfernen

Manchmal möchten Sie vielleicht nicht alle derzeit im Web-Editor verfügbaren Funktionen bereitstellen. In diesem Fall können Sie die unerwünschte Funktion aus der Symbolleiste des Web-Editors entfernen.

Führen Sie die folgenden Schritte aus, um unerwünschte Funktionen aus der Symbolleiste zu entfernen:

1. Melden Sie sich bei AEM an und öffnen Sie den CRXDE Lite-Modus.

1. Navigieren Sie zu der standardmäßigen Konfigurationsdatei, die am folgenden Speicherort verfügbar ist: .

   `/libs/fmdita/clientlibs/clientlibs/xmleditor/ui_config.json`

1. Erstellen Sie eine Kopie der Standardkonfigurationsdatei am folgenden Speicherort:

   `/apps/fmdita/xmleditor/ui_config.json`

1. Navigieren Sie zur `ui_config.json` und öffnen Sie sie im Knoten `apps` zur Bearbeitung.
Die `ui_config.json`-Datei besteht aus drei Abschnitten:

- **Symbolleisten:** Dieser Abschnitt enthält die Definition aller in der Symbolleiste des Editors verfügbaren Funktionen, z. B. Einfügen/Entfernen einer nummerierten Liste, \(Datei\) Schließen, Speichern, Kommentare und mehr.

- **Tastaturbefehle** In diesem Abschnitt werden die Tastaturbefehle definiert, die einer bestimmten Funktion im Editor zugewiesen sind.

- **templates:** Dieser Abschnitt enthält die vordefinierte Struktur der DITA-Elemente, die Sie in Ihrem Dokument verwenden können. Standardmäßig enthält der Abschnitt Vorlagen Vorlagendefinitionen für einen Absatz, einfache Tabellen-, Tabellen- und Textelemente. Sie können eine Vorlagendefinition für ein beliebiges Element erstellen, indem Sie eine gültige XML-Struktur für das gewünschte Element hinzufügen. Wenn Sie beispielsweise zu jedem neuen `li`-Element in einer Liste ein `p`-Element hinzufügen möchten, können Sie zu diesem Zweck den folgenden Code am Ende des Abschnitts „Vorlagen“ hinzufügen:

```HTML
"li": "<li><p></p></li>"
```

1. Entfernen Sie aus dem Abschnitt Symbolleisten den Eintrag der Funktion, die Sie Ihren Benutzern nicht zur Verfügung stellen möchten.

1. Speichern Sie die *ui\_config.json*-Datei und laden Sie den Web-Editor neu.


**Übergeordnetes Thema:**&#x200B;[&#x200B; Anpassen des Web-Editors](conf-web-editor.md)
