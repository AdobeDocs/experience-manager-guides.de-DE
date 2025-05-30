---
title: Textfilter konfigurieren
description: Erfahren Sie, wie Sie Textfilter konfigurieren
exl-id: 180e4ab5-5259-4a00-ac3c-bb1d6814ce0d
feature: Web Editor Configuration
role: Admin
level: Experienced
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '367'
ht-degree: 0%

---

# Textfilter konfigurieren {#id21BPD0FK0XA}

AEM Guides bietet die Funktion, um in den Dateien, die sich im ausgewählten Pfad des AEM-Repositorys befinden, nach Text zu suchen. Sie können die Filtersuche verwenden, um Dateien im Repository-Bereich zu suchen oder Dateien zu durchsuchen. Beim Arbeiten im Web-Editor müssen Sie das Dialogfeld zum Durchsuchen von Dateien verwenden, um Elemente wie Bilder, Verweise oder Schlüsselverweise einzufügen.

Standardmäßig können Sie einige erweiterte Filter verwenden, um die Dateien im AEM-Repository zu durchsuchen. Sie können alle DITA-Dateien oder Nicht-DITA-Dateien filtern, die im ausgewählten Pfad vorhanden sind. Sie können auch in den Attributen von DITA-Elementen nach bestimmten Werten suchen. Sie können auch nach Dateien suchen, die vom angegebenen Benutzer ausgecheckt wurden.

>[!NOTE]
>
> Sie können auch das globale Profil konfigurieren und weitere Filter für die Suche hinzufügen.

Führen Sie die folgenden Schritte aus, um die Textfilter zu konfigurieren:

1. Melden Sie sich bei Adobe Experience Manager als Administrator an.
1. Klicken Sie oben auf den Link **Adobe Experience Manager** und wählen Sie &quot;**&quot;**.
1. Wählen Sie **Guides** aus der Liste der Tools aus und klicken Sie auf **Ordnerprofile**.
1. Klicken Sie auf die **Globales Profil**-Kachel.
1. Klicken Sie auf **XML-Editor-Konfiguration**.
1. Klicken Sie oben **auf** Bearbeiten“.
1. Laden Sie die Datei ui\_config.json herunter.
1. Konfigurieren Sie die Filter in der Datei . Sie können auch benutzerdefinierte Filter hinzufügen, wie im folgenden Beispiel gezeigt:

   Das folgende Codefragment zeigt, wie Sie Filteroptionen für DITA-Dateien, Nicht-DITA- und DITA-Elemente hinzufügen und durch Dateien ausgecheckt werden. Es enthält auch einen benutzerdefinierten Filter - Tags.

   ```json
   [
     {
       "title": "DITA files",
       "property": "jcr:content/metadata/dita_class",
       "operation": "like",
       "children": [
         {
           "title": "DITA Topics",
           "value": "- topic/topic",
           "checked": true
         },
         {
           "title": "DITA Maps",
           "value": "- map/map",
           "checked": true
         }
       ]
     },
     {
       "title": "DITA elements",
       "property": "jcr:content/ditameta",
       "widgetId": "dita_filter",
       "operation": "like"
     },
     {
       "title": "Checked out by",
       "property": "jcr:content/cq:drivelock",
       "operation": "like",
       "itemConfig": {
         "component": "textfield",
         "placeholder": "Checked out by"
       },
       "children": [
         {
           "title": "Check out"
         }
       ]
     },
     {
       "title": "Tags",
       "property": "jcr:content/metadata/cq:tags",
       "itemConfig": {
         "component": "textfield",
         "placeholder": "Enter Tag"
       },
       "children": [
         {
           "title": "Tags"
         }
       ]
     }
   ]
   ```

   Im obigen Code-Snippet ist der erste Filter für DITA-Dateien. Die Filterdefinition akzeptiert die folgenden Parameter:

   - **Titel:** Der Anzeigename des Filters. Dieser Titel wird als Filteroption im Dialogfeld zum Durchsuchen von Dateien angezeigt.

   - **Property:** Die Eigenschaft, die in den Metadaten der Datei abgeglichen werden soll. Um beispielsweise nur die Dateien zuzulassen, die die Metadaten „dita\_class“ in ihrer Eigenschaft enthalten, nimmt der Eigenschaftsfilter „jcr:content/metadata/dita\_class“ als Wert.

   - **Operation** Geben Sie „exists“ an, um mit dem Vorhandensein des im Eigenschaftsparameter angegebenen Werts abzugleichen

1. Laden Sie die aktualisierte Datei ui\_config.json hoch, die die hinzugefügten Filter enthält.

Die konfigurierten Filter sind im Bedienfeld Filter verfügbar.

**Übergeordnetes Thema:**&#x200B;[ Anpassen des Web-Editors](conf-web-editor.md)
