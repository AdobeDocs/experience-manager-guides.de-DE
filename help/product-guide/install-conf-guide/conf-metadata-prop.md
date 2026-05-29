---
title: Konfigurieren der Ignorieren-Liste von Metadateneigenschaften
description: Erfahren Sie, wie Sie die Ignorieren-Liste für Metadateneigenschaften in AEM Guides konfigurieren.
feature: Web Editor Configuration
role: Admin
level: Experienced
source-git-commit: 8e8b24bea8504ad9fcca1117bd9e7b400e757dff
workflow-type: tm+mt
source-wordcount: '251'
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

**Übergeordnetes Thema:**[ Anpassen des Web-Editors](customize-overview.md)
