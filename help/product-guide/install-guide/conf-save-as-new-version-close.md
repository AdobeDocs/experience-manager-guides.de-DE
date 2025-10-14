---
title: Eingabeaufforderung zum Speichern als neue Version beim Schließen konfigurieren
description: Erfahren Sie, wie Sie die Eingabeaufforderung konfigurieren, um beim Schließen als neue Version zu speichern
exl-id: 1b8c3eaa-a654-4563-9541-18a59b7d306c
feature: Web Editor Configuration
role: Admin
level: Experienced
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '214'
ht-degree: 0%

---

# Eingabeaufforderung zum Speichern als neue Version beim Schließen konfigurieren {#id222HBI00XXA}

Wenn der/die Benutzende versucht, eine Datei zu schließen, die im Web-Editor mit der Schaltfläche **Schließen** auf der Registerkarte der Datei oder der Option **Schließen** im Menü Optionen geöffnet wurde, wird ein Dialogfeld angezeigt, wenn die Datei ungespeicherte Daten oder eine ungespeicherte Version enthält. Der/die Benutzende wird aufgefordert, die Datei als neue Version zu speichern, wenn die Version nicht gespeichert wurde.

Das **Als neue Version speichern**-Kontrollkästchen ist nicht standardmäßig aktiviert. Sie müssen es daher im configMgr aktivieren. Führen Sie die folgenden Schritte aus, um die Option im Web-Editor standardmäßig zu aktivieren:

1. Öffnen Sie die Seite Konfiguration der Adobe Experience Manager-Web-Konsole .

   Die Standard-URL für den Zugriff auf die Konfigurationsseite lautet:

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Suchen Sie nach dem Bundle **com.adobe.fmdita.xmeditor.config.XmlEditorConfig** und klicken Sie darauf.

1. Wählen Sie die Option **Beim Schließen nach neuer Version**.

1. Klicken Sie auf **Speichern**.


Wenn diese Option ausgewählt ist **ist das Kontrollkästchen** Als neue Version speichern“ im Dialogfeld standardmäßig aktiviert.

Weitere Informationen finden Sie *Abschnitt „Schließen und Speichern von Dateien* im Handbuch Verwenden von Adobe Experience Manager Guides as a Cloud Service .

**Übergeordnetes Thema:**&#x200B;[&#x200B; Anpassen des Web-Editors](conf-web-editor.md)
