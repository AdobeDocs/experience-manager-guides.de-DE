---
title: Konfigurieren der automatischen Speicherung von Dateien im Web-Editor
description: Erfahren Sie, wie Sie die automatische Speicherung von Dateien im Web-Editor konfigurieren
exl-id: 23fe404c-c76d-43ba-9b28-c49ab1e524de
feature: Web Editor Configuration
role: Admin
level: Experienced
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '197'
ht-degree: 1%

---

# Konfigurieren der automatischen Speicherung von Dateien im Web-Editor {#id199CC0J0M5Z}

Eine der häufigsten Funktionen im Browser-basierten Editor ist die Möglichkeit, Daten nach einem bestimmten Zeitraum zu speichern. Der Web-Editor von AEM Guides unterstützt auch das automatische Speichern von Themen- und Zuordnungsdateien im angegebenen Zeitintervall. Wenn diese Funktion ausgelöst wird, wird die Arbeitskopie des Themas oder der Zuordnung gespeichert. Es wird keine neue Version des Themas oder der Zuordnung erstellt. Um eine neue Version zu erstellen, klicken Sie auf das Symbol Revision speichern in der Symbolleiste des Web-Editors.

Die Funktion zum automatischen Speichern ist nicht standardmäßig aktiviert. Sie müssen diese Funktion über den configMgr aktivieren. Führen Sie die folgenden Schritte aus, um die Funktion zum automatischen Speichern im Web-Editor zu aktivieren:

1. Öffnen Sie die Seite Konfiguration der Adobe Experience Manager-Web-Konsole .

   Die Standard-URL für den Zugriff auf die Konfigurationsseite lautet:

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Suchen Sie nach dem Bundle **com.adobe.fmdita.xmeditor.config.XmlEditorConfig** und klicken Sie darauf.

1. Wählen Sie in *XmlEditorConfig*-Einstellungen die Option **Automatisches Speichern** aus.

1. Geben **im Feld „Intervall für** Speicherung“ das Zeitintervall in Sekunden an, in dem die Funktion für das automatische Speichern Trigger werden soll.

1. Klicken Sie auf **Speichern**.


**Übergeordnetes Thema:**&#x200B;[ Anpassen des Web-Editors](conf-web-editor.md)
