---
title: Filter für das Dialogfeld zum Durchsuchen von Dateien konfigurieren
description: Erfahren Sie, wie Sie Filter für das Dialogfeld zum Durchsuchen von Dateien konfigurieren
exl-id: 1ef09820-3b18-4762-b177-4d40926e21f0
feature: Web Editor Configuration
role: Admin
level: Experienced
TQID: https://experienceleague.adobe.com/7AzojwFiEQkwYtDnwsHhmMOwSCG3vWgsZW5oXZRsTFw
product_v2: id: fae5e35a-80c9-4b94-9352-1a060a6aab1did: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2: id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
subfeature_v2: id: b0521e56-a0b2-40b6-bf47-ebc98751f9ba
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: a004cc84-67b9-4a33-a3a7-8ec7273ef4dc
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 325
ht-degree: 0%

---

# Filter für das Dialogfeld zum Durchsuchen von Dateien konfigurieren {#id20CIL7009GN}

Beim Arbeiten im Web-Editor müssen Sie das Dialogfeld zum Durchsuchen von Dateien verwenden, um Elemente wie Bilder, Verweise oder Schlüsselverweise einzufügen. Das Standarddialogfeld zum Durchsuchen von Dateien bietet keine Dateifilteroption. Sie können eigene Filter hinzufügen, mit denen Sie einfach und schnell auf die erforderlichen Dateien zugreifen können.

Führen Sie die folgenden Schritte aus, um Ihre benutzerdefinierten Dateifilteroptionen zum Dialogfeld zum Durchsuchen von Dateien hinzuzufügen:

1. Melden Sie sich bei AEM an und öffnen Sie den CRXDE Lite-Modus.

1. Navigieren Sie zu der standardmäßigen Konfigurationsdatei, die am folgenden Speicherort verfügbar ist:

   `/libs/fmdita/clientlibs/clientlibs/xmleditor/ui_config.json`

1. Erstellen Sie eine Kopie der Standardkonfigurationsdatei am folgenden Speicherort:

   `/apps/fmdita/xmleditor/ui_config.json`

1. Navigieren Sie zur `ui_config.json` und öffnen Sie sie im Knoten `apps` zur Bearbeitung.

1. Fügen Sie in der `ui_config.json`-Datei die Definition der Filter hinzu, die Sie hinzufügen möchten.

   Das folgende Codefragment zeigt, wie zwei Filteroptionen hinzugefügt werden: DITA-Dateien und Bilddateien.

   ```json
   "browseFilters": [
       {
         "title": "DITA Files",
         "property": "jcr:content/metadata/dita_class",
         "operation": "exists"
       },
       {
         "title": "Image Files",
         "property": "jcr:content/metadata/dc:format",
         "value": [        
           "image/jpeg",
           "image/gif",
           "image/png"
         ]
       }
   ]
   ```

   Im obigen Code-Snippet ist der erste Filter für DITA-Dateien. Die Filterdefinition akzeptiert die folgenden Parameter:

   - **title:** Der Anzeigename des Filters. Dieser Titel wird als Filteroption im Dialogfeld zum Durchsuchen von Dateien angezeigt.

   - **property:** Die Eigenschaft, die in den Metadaten der Datei abgeglichen werden soll. Um beispielsweise nur die Dateien zuzulassen, die die `dita_class` Metadaten in ihrer -Eigenschaft enthalten, nimmt der Eigenschaftsfilter &quot;`jcr:content/metadata/dita_class`&quot; als Wert.

   - **operation:** Geben Sie &quot;`exists`&quot; an, damit es mit dem im Eigenschaftsparameter angegebenen Wert übereinstimmt.

   Der zweite Filter betrifft Bilddateien. Die Parameter ähneln dem ersten Filter mit Ausnahme des `value`. Der `value`-Parameter akzeptiert ein Array von Bildtypen als Wert. Alle im Parameter value angegebenen Dateitypen werden gesucht und im Dialogfeld zum Durchsuchen von Dateien angezeigt. Alle anderen Dateitypen werden ignoriert.

1. Speichern Sie die *ui\_config.json*-Datei und laden Sie den Web-Editor neu.

   Wenn Sie das Dialogfeld zum Durchsuchen von Dateien aufrufen, werden die in der Datei ui\_config.json konfigurierten Filteroptionen angezeigt.

   ![](assets/file-browse-custom-filters.png){width="300"}
