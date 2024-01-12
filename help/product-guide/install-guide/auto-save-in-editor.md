---
title: Automatische Speicherung von Dateien im Web Editor konfigurieren
description: Erfahren Sie, wie Sie die automatische Speicherung von Dateien im Web Editor konfigurieren
exl-id: 23fe404c-c76d-43ba-9b28-c49ab1e524de
feature: Web Editor Configuration
role: Admin
level: Experienced
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '197'
ht-degree: 1%

---

# Automatische Speicherung von Dateien im Web Editor konfigurieren {#id199CC0J0M5Z}

Eine der häufigsten Funktionen im browserbasierten Editor ist die Möglichkeit, Daten nach einem bestimmten Zeitraum zu speichern. Der Web Editor der AEM Guides unterstützt auch das automatische Speichern von Themen- und Zuordnungsdateien im angegebenen Zeitintervall. Wenn diese Funktion ausgelöst wird, wird die Arbeitskopie des Themas oder der Zuordnung gespeichert. Eine neue Version des Themas oder der Zuordnung wird nicht erstellt. Um eine neue Version zu erstellen, müssen Sie in der Symbolleiste des Web-Editors auf das Symbol Revision speichern klicken.

Die Funktion zum automatischen Speichern ist nicht standardmäßig aktiviert und Sie müssen sie in der configMgr aktivieren. Führen Sie die folgenden Schritte aus, um die Funktion zum automatischen Speichern im Web-Editor zu aktivieren:

1. Öffnen Sie die Seite Adobe Experience Manager Web Console Configuration .

   Die Standard-URL für den Zugriff auf die Konfigurationsseite lautet:

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Suchen Sie nach und klicken Sie auf **com.adobe.fmdita.xmleditor.config.XmlEditorConfig** Bundle

1. Im *XmlEditorConfig* -Einstellungen, wählen Sie die **Automatisches Speichern** -Option.

1. Im **Automatisches Speichern-Intervall** geben Sie das Zeitintervall in Sekunden an, um die Funktion zum automatischen Speichern Trigger.

1. Klicken Sie auf **Speichern**.


**Übergeordnetes Thema:**[ Anpassen des Web-Editors](conf-web-editor.md)
