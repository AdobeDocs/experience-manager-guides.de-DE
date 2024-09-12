---
title: Integrieren von Desktop-basierten XML-Editoren
description: Erfahren Sie, wie Sie Desktop-basierte XML-Editoren integrieren.
exl-id: 268e8613-bb3b-4577-96fb-a588dabfd834
feature: Publishing FrameMaker Documents
role: Admin
level: Experienced
source-git-commit: 434d7efd24147af23b4c65aeebf4c144ce3adda7
workflow-type: tm+mt
source-wordcount: '317'
ht-degree: 2%

---

# Integrieren von Desktop-basierten XML-Editoren {#id181GB01G0HS}

Es gibt viele XML-Editoren, die auf dem Markt verfügbar sind, und Sie könnten bereits einen verwenden. Adobe FrameMaker ist einer der leistungsfähigsten XML-Editoren, die mit AEM Connector geliefert werden. Über den AEM-Connector in FrameMaker können Sie einfach eine Verbindung zum AEM-Repository herstellen, Dateien auschecken und einchecken und Dateien direkt in FrameMaker bearbeiten. Sie können Experience Manager Guides auch so konfigurieren, dass FrameMaker über den Web-Editor gestartet wird. Nachdem Sie die Datei in FrameMaker geöffnet haben, können Sie sie bearbeiten und wieder in das AEM Repository einchecken.

## Aktivieren Sie die Dateibearbeitung im FrameMaker über den Web Editor

Sie können FrameMaker oder einen anderen DITA-Editor verwenden, um DITA-Inhalte zu erstellen und zu aktualisieren. Wenn Ihr Unternehmen jedoch FrameMaker als DITA-Editor verwendet, können Sie Ihren Benutzern die Möglichkeit geben, DITA-Dokumente direkt unter FrameMaker von AEM aus zu öffnen.

Standardmäßig wird Ihren Benutzern die Schaltfläche **In FrameMaker öffnen** in der AEM-Symbolleiste nicht angezeigt. Führen Sie die folgenden Schritte aus, um diese Schaltfläche in der AEM-Symbolleiste hinzuzufügen:

1. Öffnen Sie die Seite Adobe Experience Manager Web Console Configuration .

   Die Standard-URL für den Zugriff auf die Konfigurationsseite lautet:

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Suchen Sie nach dem Bundle **com.adobe.fmdita.xmleditor.config.XmlEditorConfig** und klicken Sie darauf.
   ![](assets/open-in-fm-config.png)

1. Wählen Sie die Option **Öffnungen in FrameMaker-Schaltfläche anzeigen** aus.

1. Wenn Sie Version 4.6 und FrameMaker Version 2022 vom September - Update 3 verwenden, müssen Sie die Konfiguration **FrameMaker Version 2022 Update 3 oder höher** aktivieren, damit Ihre Benutzer die Experience Manager Guides-Serverdetails an FrameMaker weitergeben können. Diese Option ist standardmäßig deaktiviert.


1. Klicken Sie auf **Speichern**.


Wenn Sie die Option **Im FrameMaker-Button öffnen anzeigen** aktivieren, wird bei der Auswahl einer beliebigen DITA-Datei im AEM-Repository die Schaltfläche **In FrameMaker öffnen** angezeigt. Wenn diese Option *nicht aktiviert* ist, wird die Schaltfläche **In FrameMaker öffnen** nur angezeigt, wenn Sie eine FM- oder eine .book-Datei im Repository auswählen.



