---
title: Integrieren von Desktop-basierten XML-Editoren
description: Erfahren Sie, wie Sie Desktop-basierte XML-Editoren integrieren
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

Auf dem Markt sind viele XML-Editoren verfügbar, und Sie könnten bereits einen verwenden. Adobe FrameMaker ist einer der leistungsfähigsten XML-Editoren, der mit dem AEM-Connector geliefert wird. Mithilfe des AEM-Connectors in FrameMaker können Sie sich einfach mit dem AEM-Repository verbinden, Dateien ein- und auschecken und Dateien direkt in FrameMaker bearbeiten. Sie können Experience Manager Guides auch so konfigurieren, dass FrameMaker vom Web-Editor aus gestartet wird. Sobald die Datei auf FrameMaker geöffnet ist, können Sie sie bearbeiten und wieder in das AEM-Repository einchecken.

## Aktivieren der Dateibearbeitung im FrameMaker über den Web-Editor

Sie können FrameMaker oder einen anderen DITA-Editor verwenden, um DITA-Inhalte zu erstellen und zu aktualisieren. Wenn Ihr Unternehmen jedoch FrameMaker als DITA-Editor verwendet, können Sie Ihren Benutzenden die Möglichkeit geben, DITA-Dokumente direkt in FrameMaker über AEM zu öffnen.

Standardmäßig wird den Benutzenden die Schaltfläche **In FrameMaker öffnen** in der AEM-Symbolleiste nicht angezeigt. Führen Sie die folgenden Schritte aus, um diese Schaltfläche in der AEM-Symbolleiste hinzuzufügen:

1. Öffnen Sie die Seite Konfiguration der Adobe Experience Manager-Web-Konsole .

   Die Standard-URL für den Zugriff auf die Konfigurationsseite lautet:

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Suchen Sie nach dem Bundle **com.adobe.fmdita.xmeditor.config.XmlEditorConfig** und klicken Sie darauf.
   ![](assets/open-in-fm-config.png)

1. Wählen Sie die **Schaltfläche „Auf FrameMaker öffnen“**.

1. Wenn Sie Version 4.6 und FrameMaker Version September 2022 - Update 3 verwenden, müssen Sie die Konfiguration **FrameMaker Version 2022 Update 3 oder höher**, damit Ihre Benutzerinnen und Benutzer die Experience Manager Guides-Serverdetails an FrameMaker weitergeben können. Diese Option ist standardmäßig deaktiviert.


1. Klicken Sie auf **Speichern**.


Wenn Sie die Option **Auf FrameMaker öffnen** aktivieren, wird die Schaltfläche **Auf FrameMaker öffnen** angezeigt, wenn Sie eine beliebige DITA-Datei im AEM-Repository auswählen. Wenn diese Option *nicht aktiviert* wird die Schaltfläche **In FrameMaker öffnen** nur angezeigt, wenn Sie eine .fm- oder eine .book-Datei im Repository auswählen.



