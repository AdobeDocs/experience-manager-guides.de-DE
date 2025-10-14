---
title: Konfigurieren der automatischen Speicherung von Dateien im Web-Editor
description: Erfahren Sie, wie Sie die automatische Speicherung von Dateien im Web-Editor konfigurieren
exl-id: 4d99c3d8-cf6a-4cf3-aaec-9009a0376c1e
feature: Web Editor Configuration
role: Admin
level: Experienced
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '182'
ht-degree: 1%

---

# Konfigurieren der automatischen Speicherung von Dateien im Web-Editor {#id199CC0J0M5Z}

Eine der häufigsten Funktionen im Browser-basierten Editor ist die Möglichkeit, Daten nach einem bestimmten Zeitraum zu speichern. Der AEM Guides-Web-Editor unterstützt auch das automatische Speichern von Themen- und Zuordnungsdateien im angegebenen Zeitintervall. Wenn diese Funktion ausgelöst wird, wird die Arbeitskopie des Themas oder der Zuordnung gespeichert. Es wird keine neue Version des Themas oder der Zuordnung erstellt. Um eine neue Version zu erstellen, klicken Sie auf das Symbol Revision speichern in der Symbolleiste des Web-Editors.

Die Funktion zum automatischen Speichern ist nicht standardmäßig aktiviert. Sie müssen diese Funktion mithilfe der Konfigurationsdatei aktivieren.

Verwenden Sie die Anweisungen unter [Konfigurationsüberschreibungen](download-install-additional-config-override.md#), um die Konfigurationsdatei zu erstellen. Geben Sie in der Konfigurationsdatei die folgenden \(property\)-Details an, um das Zeitintervall für das automatische Speichern und das automatische Speichern der Datei zu konfigurieren:

| PID | Eigenschaftsschlüssel | Eigenschaftswert |
|---|------------|--------------|
| `com.adobe.fmdita.xmleditor.config.XmlEditorConfig` | `xmleditor.autosave` | Boolescher Wert \(true/false\).<br> **Standardwert**: false |
| `xmleditor.autosaveinterval` | Geben Sie das Zeitintervall in Sekunden an, in dem die Funktion für das automatische Speichern Trigger werden soll. |

**Übergeordnetes Thema:**&#x200B;[&#x200B; Anpassen des Web-Editors](conf-web-editor.md)
