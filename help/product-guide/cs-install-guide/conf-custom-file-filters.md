---
title: Filter für Dialogfeld "Dateisuche"konfigurieren
description: Erfahren Sie, wie Sie Filter für das Dialogfeld zum Durchsuchen von Dateien konfigurieren
exl-id: 1ef2cec8-2e77-40c1-9ed2-324048bf65fb
feature: Web Editor Configuration
role: Admin
level: Experienced
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '376'
ht-degree: 0%

---

# Filter für Dialogfeld &quot;Dateisuche&quot;konfigurieren {#id20CIL7009GN}

Bei der Arbeit im Web Editor müssen Sie das Dialogfeld zum Durchsuchen von Dateien verwenden, um Elemente wie Bilder, Verweise oder wichtige Verweise einzufügen. Das Standarddialogfeld zum Durchsuchen von Dateien bietet keine Filteroption für Dateien. Sie können eigene Filter hinzufügen, mit denen Sie schnell und einfach auf die gewünschten Dateien zugreifen können.

Führen Sie die folgenden Schritte aus, um Ihre benutzerdefinierten Dateifilteroptionen zum Dialogfeld &quot;Dateisuche&quot;hinzuzufügen:

1. Um die Benutzeroberflächenkonfigurationsdatei herunterzuladen, melden Sie sich als Administrator bei Adobe Experience Manager an.

1. Klicken Sie oben auf den Adobe Experience Manager-Link und wählen Sie **Tools** aus.
1. Wählen Sie **Handbücher** aus der Liste der Tools und klicken Sie auf **Ordnerprofile**.
1. Klicken Sie auf die Kachel **Globales Profil** .
1. Wählen Sie die Registerkarte **XML-Editor-Konfiguration** aus und klicken Sie oben auf das Symbol **Bearbeiten** .
1. Klicken Sie auf das Symbol **Download** , um die Datei ui\_config.json auf Ihr lokales System herunterzuladen. Anschließend können Sie Änderungen an der Datei vornehmen und diese dann hochladen.
1. Fügen Sie in der Datei `ui_config.json` die Definition der Filter hinzu, die Sie hinzufügen möchten.

   Das folgende Codefragment zeigt, wie zwei Filteroptionen hinzugefügt werden: DITA-Dateien und Bilddateien.

   ```
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

   Im obigen Codefragment ist der erste Filter für DITA-Dateien. Die Filterdefinition akzeptiert die folgenden Parameter:

   title
:   Der Anzeigename des Filters. Dieser Titel wird als Filteroption im Dialogfeld zum Durchsuchen von Dateien angezeigt.

   property
:   Die Eigenschaft, die in den Metadaten der Datei übereinstimmen soll. Um beispielsweise nur Dateien zuzulassen, deren Eigenschaft die Metadaten `dita_class` enthält, nimmt der Eigenschaftsfilter den Wert &quot;`jcr:content/metadata/dita_class`&quot;an.

   operation
:   Geben Sie &quot;`exists`&quot;an, damit der Wert, der im Eigenschaftsparameter angegeben ist, für die Existenz gefunden wird.

   Der zweite Filter ist für Bilddateien vorgesehen. Die Parameter ähneln dem ersten Filter mit Ausnahme des Parameters `value` . Der Parameter `value` verwendet ein Array von Bildtypen als Wert. Alle im Parameter value angegebenen Dateitypen werden gesucht und im Dialogfeld zum Durchsuchen von Dateien angezeigt. Alle anderen Dateitypen werden ignoriert.

1. Speichern Sie die Datei *ui\_config.json* und laden Sie sie hoch. Laden Sie dann den Web-Editor neu.

   Wenn Sie das Dialogfeld zum Durchsuchen der Datei starten, werden die in der Datei ui\_config.json konfigurierten Filteroptionen angezeigt.

   ![](assets/file-browse-custom-filters.png)


**Übergeordnetes Thema:**[ Web-Editor anpassen](conf-web-editor.md)
