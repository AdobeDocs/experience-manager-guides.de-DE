---
title: Konfigurieren gültiger Dateinamen für die AEM-Site-Ausgabe
description: Erfahren Sie, wie Sie gültige Dateinamen für die AEM-Site-Ausgabe konfigurieren
exl-id: 05215bec-653b-4563-83c6-a1bb16200469
feature: Filename Configuration
role: Admin
level: Experienced
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '146'
ht-degree: 1%

---

# Konfigurieren gültiger Dateinamen für die AEM-Site-Ausgabe {#id214GK0X0KXA}

Ähnlich wie bei der Liste gültiger Dateinamenzeichen, die für DITA-Themen zulässig sind, können Sie auch eine Liste gültiger Dateinamenzeichen für die AEM-Site-Ausgabe konfigurieren. Zu den bekannten Zeichen, die in einer URL nicht zulässig sind, zählen: ``'<>`@$``. Diese Zeichen werden so konfiguriert, dass sie automatisch in einen Unterstrich &quot;`_`&quot; konvertiert werden, wenn sie beim Generieren von AEM Site-Ausgabedateinamen gefunden werden.

Verwenden Sie die Anweisungen unter [Konfigurationsüberschreibungen](download-install-additional-config-override.md#), um die Konfigurationsdatei zu erstellen. Geben Sie in der Konfigurationsdatei die folgenden \(property\)-Details an, um gültige Zeichen in der AEM-Site-Ausgabe festzulegen:

| PID | Eigenschaftsschlüssel | Eigenschaftswert |
|---|------------|--------------|
| `com.adobe.fmdita.common.SanitizeNodeNameImpl` | `aemsite.DisallowedFileNameChars` | Fügen Sie in den Ausgabedateinamen der AEM-Site Zeichen hinzu, die Sie durch einen Unterstrich ersetzen möchten. <br> **Standardwert**: ``'<\>\`@$`` |

**Übergeordnetes Thema:**&#x200B;[&#x200B; Dateinamen konfigurieren](conf-file-names.md)
