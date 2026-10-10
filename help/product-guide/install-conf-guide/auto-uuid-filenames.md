---
title: Konfigurieren automatischer Dateinamen basierend auf UUID
description: Erfahren Sie, wie Sie automatische Dateinamen basierend auf der UUID konfigurieren
feature: Filename Configuration
role: Admin
level: Experienced
exl-id: 2b591ddc-173b-484a-995f-1b3322babbbd
product_v2:
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
    internal-label: Experience Manager
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
    internal-label: Experience Manager Guides
feature_v2:
  - id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
    internal-label: Configuration
subfeature_v2:
  - id: ccd46b93-df7f-4458-ba4c-90a3562d9ab0
    internal-label: Filename configuration
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
level_v2:
  - id: d378ca77-2da1-4f39-ad92-1917fe974a38
    internal-label: Experienced
source-git-commit: 81a0e7f0736ba4970673dd87a888a4c60d3c1b4e
workflow-type: tm+mt
source-wordcount: '325'
ht-degree: 1%
---
# Konfigurieren automatischer Dateinamen basierend auf UUID {#id205QG070D5Z}

Wenn ein Thema oder eine Zuordnungsdatei erstellt wird, haben Autoren standardmäßig die Möglichkeit, auch den Dateinamen anzugeben. Autoren können die Dateinamen gemäß ihren Anforderungen zuweisen. Dies kann jedoch zu Inkonsistenzen führen, und in einem großen Dokumentationssystem kann ein breites Spektrum von Dateinamen angezeigt werden. Als Admin können Sie Ihre Autoren daran hindern, den Dateien, die sie in Ihrem System erstellen, Dateinamen zuzuweisen. Für jede neue Themen- oder Zuordnungsdatei können Sie UUID-basierte Dateinamen automatisch zuweisen.

Die folgenden Registerkarten enthalten Anweisungen zum Konfigurieren automatischer Dateinamen basierend auf der UUID basierend auf Ihrer Experience Manager Guides-Einrichtung: Cloud Service oder On-Premise.


>[!BEGINTABS]

>[!TAB Cloud Service]

Verwenden Sie die Anweisungen unter [Konfigurationsüberschreibungen](download-install-config-override.md#), um die Konfigurationsdatei zu erstellen. Geben Sie in der Konfigurationsdatei die folgenden \(property\)-Details an, um automatische Dateinamen basierend auf der UUID zu konfigurieren:

| PID | Eigenschaftsschlüssel | Eigenschaftswert |
|---|------------|--------------|
| `com.adobe.fmdita.xmleditor.config.XmlEditorConfig` | `xmleditor.uniquefilenames` | Boolescher Wert \(true/false\).<br> **Standardwert**: false |

>[!NOTE]
>
> Wenn diese Option aktiviert ist, wird den Autoren beim Erstellen eines neuen Themas oder einer Zuordnungsdatei die Option zum Angeben des Dateinamens nicht angezeigt. Über die Assets-Benutzeroberfläche und den Editor kann eine neue Themen- oder Zuordnungsdatei erstellt werden.

>[!TAB On-Premise]

Führen Sie die folgenden Schritte aus, um den UUID-basierten Dateinamen automatisch für alle neuen Dateien zuzuweisen, die im System erstellt wurden:

1. Öffnen Sie die Seite Konfiguration der Adobe Experience Manager-Web-Konsole .

   Die Standard-URL für den Zugriff auf die Konfigurationsseite lautet:

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Suchen Sie nach dem Bundle *com.adobe.fmdita.xmeditor.config.XmlEditorConfig* und klicken Sie darauf.

1. Wählen Sie die **UUID-basierte Systemdateinamen verwenden**.

1. Klicken Sie auf **Speichern**.


>[!NOTE]
>
> Standardmäßig ist diese Option deaktiviert. Wenn diese Option aktiviert ist, wird den Autoren beim Erstellen eines neuen Themas oder einer Zuordnungsdatei die Option zum Angeben des Dateinamens nicht angezeigt. Über die Assets-Benutzeroberfläche und den Editor kann eine neue Themen- oder Zuordnungsdatei erstellt werden.

>[!ENDTABS]
