---
title: Konfigurieren der Ignorieren-Liste von Metadateneigenschaften
description: Erfahren Sie, wie Sie die Ignorieren-Liste für Metadateneigenschaften in AEM Guides konfigurieren.
feature: Web Editor Configuration
role: Admin
level: Experienced
source-git-commit: f74c71d6a4a293bfbae55e9e57c62b7478d0a88a
workflow-type: tm+mt
source-wordcount: '180'
ht-degree: 1%

---

# Konfigurieren der Ignorieren-Liste von Metadateneigenschaften

Wenn eine Datei bearbeitet wird, werden alle Änderungen an den Metadatenfeldern, die unter **Dateieigenschaften** verfügbar sind oder auf den Backend-Trigger angewendet werden, mit dem Sternchen (*) auf der Dokumentversion angezeigt. Um zu verhindern, dass systemgenerierte Metadatenaktualisierungen diese Anzeige beeinflussen, können Admins eine Ignorieren-Liste für Metadateneigenschaften konfigurieren.

Verwenden Sie die Anweisungen unter [Konfigurationsüberschreibungen](download-install-config-override.md#), um die Konfigurationsdatei zu erstellen. Geben Sie in der Konfigurationsdatei die folgenden Details (Eigenschaft) an, um die Option **Metadateneigenschaft für unsaubere Version ignorieren** zu konfigurieren:


| PID | Eigenschaftsschlüssel | Eigenschaftswert |
|---|------------|--------------|
| `com.adobe.fmdita.xmleditor.config.XmlEditorConfig` | `xmleditor.dirtychecker.ignoremetadata` | `<comma-separated list / array of metadata properties>` |

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

**Übergeordnetes Thema:**&#x200B;[&#x200B; Anpassen des Web-Editors](customize-overview.md)
