---
title: Konfigurieren der automatischen Speicherung von Dateien im Web-Editor
description: Erfahren Sie, wie Sie die automatische Speicherung von Dateien im Web-Editor konfigurieren
feature: Web Editor Configuration
role: Admin
level: Experienced
source-git-commit: 6f3f05419f4f5cdd45ab580cdee6fa869f20f01d
workflow-type: tm+mt
source-wordcount: '266'
ht-degree: 1%

---

# Konfigurieren der automatischen Speicherung von Dateien im Web-Editor {#id199CC0J0M5Z}

Eine der häufigsten Funktionen im Browser-basierten Editor ist die Möglichkeit, Daten nach einem bestimmten Zeitraum zu speichern. Der AEM Guides-Web-Editor unterstützt auch das automatische Speichern von Themen- und Zuordnungsdateien im angegebenen Zeitintervall. Wenn diese Funktion ausgelöst wird, wird die Arbeitskopie des Themas oder der Zuordnung gespeichert. Es wird keine neue Version des Themas oder der Zuordnung erstellt. Um eine neue Version zu erstellen, klicken Sie auf das Symbol Revision speichern in der Symbolleiste des Web-Editors.

Die Funktion zum automatischen Speichern ist nicht standardmäßig aktiviert. Sie müssen diese Funktion mithilfe der Konfigurationsdatei für Cloud Service und über die `configMgr` für On-Premise aktivieren.

Die folgenden Registerkarten enthalten Anweisungen zum Aktivieren der Funktion für das automatische Speichern im Web-Editor je nach Experience Manager Guides-Einrichtung: Cloud Service oder On-Premise.

>[!BEGINTABS]

>[!TAB Cloud Service]

Verwenden Sie die Anweisungen unter [Konfigurationsüberschreibungen](download-install-config-override.md#), um die Konfigurationsdatei zu erstellen. Geben Sie in der Konfigurationsdatei die folgenden \(property\)-Details an, um das Zeitintervall für das automatische Speichern und das automatische Speichern der Datei zu konfigurieren:

| PID | Eigenschaftsschlüssel | Eigenschaftswert |
|---|------------|--------------|
| `com.adobe.fmdita.xmleditor.config.XmlEditorConfig` | `xmleditor.autosave` | Boolescher Wert \(true/false\).<br> **Standardwert**: false |
| `xmleditor.autosaveinterval` | Geben Sie das Zeitintervall in Sekunden an, in dem die Funktion für das automatische Speichern Trigger werden soll. |

>[!TAB On-Premise]

1. Öffnen Sie die Seite Konfiguration der Adobe Experience Manager-Web-Konsole .

   Die Standard-URL für den Zugriff auf die Konfigurationsseite lautet:

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Suchen Sie nach dem Bundle **com.adobe.fmdita.xmeditor.config.XmlEditorConfig** und klicken Sie darauf.

1. Wählen Sie in *XmlEditorConfig*-Einstellungen die Option **Automatisches Speichern** aus.

1. Geben **im Feld „Intervall für** Speicherung“ das Zeitintervall in Sekunden an, in dem die Funktion für das automatische Speichern Trigger werden soll.

1. Klicken Sie auf **Speichern**.

>[!ENDTABS]