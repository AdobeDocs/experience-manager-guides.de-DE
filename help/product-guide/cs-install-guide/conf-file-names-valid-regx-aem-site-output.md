---
title: Konfigurieren gültiger Dateinamen für die AEM Site-Ausgabe
description: Erfahren Sie, wie Sie gültige Dateinamen für die AEM Site-Ausgabe konfigurieren
exl-id: 05215bec-653b-4563-83c6-a1bb16200469
feature: Filename Configuration
role: Admin
level: Experienced
TQID: 'https://experienceleague.adobe.com/hhc9Q8A-Eq3e8PAHHDXf1jXf8qVb-p4sU3Cum53ra9M'
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
    internal-label: Experience Manager Guides
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
    internal-label: Experience Manager
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
source-wordcount: '145'
ht-degree: 1%
---
# Konfigurieren gültiger Dateinamen für die AEM Site-Ausgabe {#id214GK0X0KXA}

Ähnlich wie bei der Liste der gültigen Dateinamenzeichen, die für DITA-Themen zulässig sind, können Sie auch eine Liste gültiger Dateinamenzeichen für die AEM Site-Ausgabe konfigurieren. Zu den bekannten Zeichen, die in einer URL nicht zulässig sind, zählen: ``'<>`@$``. Diese Zeichen werden so konfiguriert, dass sie beim Generieren von AEM Site-Ausgabedateinamen automatisch in einen Unterstrich &quot;`_`&quot; konvertiert werden.

Verwenden Sie die Anweisungen unter [Konfigurationsüberschreibungen](download-install-additional-config-override.md#), um die Konfigurationsdatei zu erstellen. Geben Sie in der Konfigurationsdatei die folgenden \(property\)-Details an, um gültige Zeichen in der AEM Site-Ausgabe festzulegen:

| PID | Eigenschaftsschlüssel | Eigenschaftswert |
|---|------------|--------------|
| `com.adobe.fmdita.common.SanitizeNodeNameImpl` | `aemsite.DisallowedFileNameChars` | Fügen Sie in den Ausgabedateinamen der AEM-Site Zeichen hinzu, die Sie durch einen Unterstrich ersetzen möchten. <br> **Standardwert**: ``'<\>\`@$`` |

**Übergeordnetes Thema:**[ Dateinamen konfigurieren](conf-file-names.md)
