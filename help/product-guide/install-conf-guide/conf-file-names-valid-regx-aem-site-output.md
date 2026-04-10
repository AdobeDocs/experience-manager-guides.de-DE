---
title: Konfigurieren gültiger Dateinamen für die AEM Site-Ausgabe
description: Erfahren Sie, wie Sie gültige Dateinamen für die AEM Site-Ausgabe konfigurieren
feature: Filename Configuration
role: Admin
level: Experienced
source-git-commit: 6f3f05419f4f5cdd45ab580cdee6fa869f20f01d
workflow-type: tm+mt
source-wordcount: '217'
ht-degree: 0%

---

# Konfigurieren gültiger Dateinamen für die AEM Site-Ausgabe {#id214GK0X0KXA}

Ähnlich wie bei der Liste der gültigen Dateinamenzeichen, die für DITA-Themen zulässig sind, können Sie auch eine Liste gültiger Dateinamenzeichen für die AEM Site-Ausgabe konfigurieren. Zu den bekannten Zeichen, die in einer URL nicht zulässig sind, zählen: ``'<>`@$``. Diese Zeichen werden so konfiguriert, dass sie beim Generieren von AEM Site-Ausgabedateinamen automatisch in einen Unterstrich &quot;`_`&quot; konvertiert werden.

Die folgenden Registerkarten enthalten Anweisungen zum Konfigurieren gültiger Dateinamen für die AEM-Site-Ausgabe basierend auf Ihrer Experience Manager Guides-Einrichtung: Cloud Service oder On-Premise.

>[!BEGINTABS]

>[!TAB Cloud Service]

Verwenden Sie die Anweisungen unter [Konfigurationsüberschreibungen](download-install-config-override.md#), um die Konfigurationsdatei zu erstellen. Geben Sie in der Konfigurationsdatei die folgenden \(property\)-Details an, um gültige Zeichen in der AEM Site-Ausgabe festzulegen:

| PID | Eigenschaftsschlüssel | Eigenschaftswert |
|---|------------|--------------|
| `com.adobe.fmdita.common.SanitizeNodeNameImpl` | `aemsite.DisallowedFileNameChars` | Fügen Sie in den Ausgabedateinamen der AEM-Site Zeichen hinzu, die Sie durch einen Unterstrich ersetzen möchten. <br> **Standardwert**: ``'<\>\`@$`` |

>[!TAB On-Premise]

Die Konfiguration, mit der Sie gültige Zeichen in der AEM-Site-Ausgabe festlegen können, ist im `com.adobe.fmdita.common.SanitizeNodeNameImpl`-Bundle vorhanden. **Legen Sie die Einstellung Nicht zulässiger Zeichensatz für die Veröffentlichung in AEM Sites fest** um Zeichen einzuschließen, die Sie in den Ausgabedateinamen der AEM-Site durch einen Unterstrich ersetzen möchten.

>[!ENDTABS]
