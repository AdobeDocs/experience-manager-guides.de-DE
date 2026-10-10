---
title: Konfigurieren der Ignorieren-Liste von Metadateneigenschaften
description: Erfahren Sie, wie Sie die Ignorieren-Liste für Metadateneigenschaften in AEM Guides konfigurieren.
feature: Web Editor Configuration
role: Admin
level: Experienced
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
source-wordcount: '250'
ht-degree: 0%
---
# Konfigurieren der Ignorieren-Liste von Metadateneigenschaften

Wenn eine Datei bearbeitet wird, werden alle Änderungen an den Metadatenfeldern, die unter **Dateieigenschaften** verfügbar sind oder auf den Backend-Trigger angewendet werden, mit dem Sternchen (*) auf der Dokumentversion angezeigt. Um zu verhindern, dass systemgenerierte Metadatenaktualisierungen diese Anzeige beeinflussen, können Admins eine Ignorieren-Liste für Metadateneigenschaften konfigurieren.

>[!BEGINTABS]

>[!TAB Cloud Service]

Verwenden Sie die Anweisungen unter [Konfigurationsüberschreibungen](download-install-config-override.md#), um die Konfigurationsdatei zu erstellen. Geben Sie in der Konfigurationsdatei die folgenden Details (Eigenschaft) an, um die Option **Metadateneigenschaft für unsaubere Version ignorieren** zu konfigurieren.


| PID | Eigenschaftsschlüssel | Eigenschaftswert |
|---|------------|--------------|
| `com.adobe.fmdita.xmleditor.config.XmlEditorConfig` | `xmleditor.dirtychecker.ignoremetadata` | `<comma-separated list / array of metadata properties>` |

>[!TAB On-Premise]

1. Öffnen Sie die Seite Konfiguration der Adobe Experience Manager-Web-Konsole .

   Die Standard-URL für den Zugriff auf die Konfigurationsseite lautet:

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Suchen Sie nach dem Bundle **com.adobe.fmdita.xmeditor.config.XmlEditorConfig** und klicken Sie darauf.

1. Navigieren Sie in *XmlEditorConfig*-Einstellungen zur Option **Metadateneigenschaft für unsaubere Version ignorieren** .

   Überprüfen Sie die Liste der derzeit konfigurierten Standard-Metadateneigenschaften, die ignoriert werden sollen.

1. Fügen Sie Metadateneigenschaften gemäß den Anforderungen hinzu oder entfernen Sie sie.
1. Wählen **Speichern**, um die aktualisierte Konfiguration zu speichern.


>[!ENDTABS]

## Standard-Metadateneigenschaften in der Ignorieren-Liste

AEM Guides enthält einen Standardsatz von Metadateneigenschaften in der Ignorieren-Liste. Sie können diese Liste nach Bedarf ändern, um Metadateneigenschaften hinzuzufügen oder zu entfernen.

* „jcr:mixinTypes&quot;,
* „jcr:primaryType&quot;,
* „jcr:frozenMixinTypes&quot;,
* „jcr:frozenPrimaryType&quot;,
* „jcr:frozenUuid&quot;,
* „jcr:uuid&quot;,
* „dam:extracted&quot;,
* „jcr:lastModified&quot;,
* „jcr:lastModifiedBy&quot;,
* „dc:modified&quot;,
* „dam:sha1&quot;,
* „dam:size&quot;,
* „Handbücher:wordCount&quot;,
* „dam:scene7UploadTimeStamp&quot;,
* „dam:scene7LastModified&quot;

Nur die Metadateneigenschaften, die nicht in der Ignorieren-Liste enthalten sind, werden für das Markieren der Version eines Dokuments als falsch erachtet.

**Übergeordnetes Thema:**[ Editor anpassen](customize-overview.md)
