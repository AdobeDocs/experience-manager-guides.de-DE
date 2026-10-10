---
title: Konfigurieren der automatischen Speicherung von Dateien im Editor
description: Erfahren Sie, wie Sie die automatische Speicherung von Dateien im Editor konfigurieren
feature: Web Editor Configuration
role: Admin
level: Experienced
exl-id: 142a588a-3d26-48ee-a3fe-23882922243c
product_v2:
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
    internal-label: Experience Manager
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
    internal-label: Experience Manager Guides
feature_v2:
  - id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
    internal-label: Configuration
subfeature_v2:
  - id: b0521e56-a0b2-40b6-bf47-ebc98751f9ba
    internal-label: Web Editor configuration
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
level_v2:
  - id: d378ca77-2da1-4f39-ad92-1917fe974a38
    internal-label: Experienced
source-git-commit: 81a0e7f0736ba4970673dd87a888a4c60d3c1b4e
workflow-type: tm+mt
source-wordcount: '275'
ht-degree: 1%
---
# Konfigurieren der automatischen Speicherung von Dateien im Editor {#id199CC0J0M5Z}

Eine der häufigsten Funktionen im Browser-basierten Editor ist die Möglichkeit, Daten nach einem bestimmten Zeitraum zu speichern. Der AEM Guides-Editor unterstützt auch das automatische Speichern von Themen- und Zuordnungsdateien im angegebenen Zeitintervall. Wenn diese Funktion ausgelöst wird, wird die Arbeitskopie des Themas oder der Zuordnung gespeichert. Es wird keine neue Version des Themas oder der Zuordnung erstellt. Um eine neue Version zu erstellen, klicken Sie auf das Symbol Revision speichern in der Symbolleiste des Editors.

Die Funktion zum automatischen Speichern ist nicht standardmäßig aktiviert. Sie müssen diese Funktion mithilfe der Konfigurationsdatei für Cloud Service und über die `configMgr` für On-Premise aktivieren.

Die folgenden Registerkarten enthalten Anweisungen zum Aktivieren der Funktion für das automatische Speichern im Editor basierend auf Ihrer Experience Manager Guides-Einrichtung: Cloud Service oder On-Premise.

>[!BEGINTABS]

>[!TAB Cloud Service]

Verwenden Sie die Anweisungen unter [Konfigurationsüberschreibungen](download-install-config-override.md#), um die Konfigurationsdatei zu erstellen. Geben Sie in der Konfigurationsdatei die folgenden \(property\)-Details an, um das Zeitintervall für das automatische Speichern und das automatische Speichern der Datei zu konfigurieren:

| PID | Eigenschaftsschlüssel | Eigenschaftswert |
|---|------------|--------------|
| `com.adobe.fmdita.xmleditor.config.XmlEditorConfig` | `xmleditor.autosave` | Boolescher Wert \(true/false\).<br> **Standardwert**: false |
| `xmleditor.autosaveinterval` | Geben Sie das Zeitintervall in Sekunden an, in dem die Funktion für das automatische Speichern Trigger werden soll. |  |

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
