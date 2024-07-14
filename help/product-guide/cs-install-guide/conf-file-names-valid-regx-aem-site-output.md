---
title: Gültige Dateinamen für AEM Site-Ausgabe konfigurieren
description: Erfahren Sie, wie Sie gültige Dateinamen für AEM Site-Ausgabe konfigurieren.
exl-id: 05215bec-653b-4563-83c6-a1bb16200469
feature: Filename Configuration
role: Admin
level: Experienced
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '146'
ht-degree: 1%

---

# Gültige Dateinamen für AEM Site-Ausgabe konfigurieren {#id214GK0X0KXA}

Ähnlich wie bei der Liste gültiger Dateinamenzeichen, die für DITA-Themen zulässig sind, können Sie auch eine Liste gültiger Dateinamenzeichen für AEM Site-Ausgabe konfigurieren. Einige der bekannten Zeichen, die in einer URL nicht zulässig sind, sind: ``'<>`@$``. Diese Zeichen werden so konfiguriert, dass sie beim Generieren AEM Site-Ausgabedateinamen automatisch in einen Unterstrich &quot;`_`&quot;umgewandelt werden.

Verwenden Sie die Anweisungen unter [Konfigurationsüberschreibungen](download-install-additional-config-override.md#) , um die Konfigurationsdatei zu erstellen. Geben Sie in der Konfigurationsdatei die folgenden \(Eigenschaft\)-Details an, um gültige Zeichen in AEM Site-Ausgabe festzulegen:

| PID | Eigenschaftenschlüssel | Eigenschaftswert |
|---|------------|--------------|
| `com.adobe.fmdita.common.SanitizeNodeNameImpl` | `aemsite.DisallowedFileNameChars` | Fügen Sie Zeichen hinzu, die Sie durch einen Unterstrich in den Namen der AEM Site-Ausgabedateien ersetzen möchten. <br> **Standardwert**: ``'<\>\`@$`` |

**Übergeordnetes Thema:**[ Dateinamen konfigurieren](conf-file-names.md)
