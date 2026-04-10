---
title: Konfigurieren des UUID-Dateinamenmusters
description: Erfahren Sie, wie Sie das UUID-Dateinamenmuster konfigurieren
feature: Migration
role: Admin
level: Experienced
source-git-commit: 6f3f05419f4f5cdd45ab580cdee6fa869f20f01d
workflow-type: tm+mt
source-wordcount: '297'
ht-degree: 1%

---

# Konfigurieren des UUID-Dateinamenmusters

Beim Importieren von Inhalten ist es nicht erforderlich, dass Ihre Dateinamen auf der UUID basieren. In einem System, das UUID-basierte Dateinamen verwendet, ist es obligatorisch, dass alle Dateien mit ihren UUIDs und nicht mit ihren ursprünglichen Dateinamen referenziert werden. Wenn eine importierte Datei keine UUID-basierten Dateinamen hat, können Sie das System so konfigurieren, dass seiner Dateieigenschaft eine UUID hinzugefügt wird. Diese UUID wird dann verwendet, um auf solche Dateien zu verweisen, bei denen die UUID nicht für die Benennung der Dateien verwendet wird.

## Schritte zum Konfigurieren des UUID-Dateinamenmusters

Die folgenden Registerkarten enthalten Anweisungen zum Konfigurieren des UUID-Dateinamenmusters basierend auf Ihrer Experience Manager Guides-Einrichtung: Cloud Service oder On-Premise.

>[!BEGINTABS]

>[!TAB Cloud Service]

Verwenden Sie die Anweisungen unter [Konfigurationsüberschreibungen](download-install-config-override.md#), um die Konfigurationsdatei zu erstellen. Geben Sie in der Konfigurationsdatei die folgenden \(property\)-Details an, um das UUID-Dateinamenmuster zu konfigurieren:

| PID | Eigenschaftsschlüssel | Eigenschaftswert |
|---|------------|--------------|
| `com.adobe.fmdita.config.ConfigManager` | `uuid.regex` | Zeichenfolge, die den Regex für das UUID-Dateinamenmuster angibt. <br> Wenn eine Datei nicht dem angegebenen Muster folgt, wird eine UUID zur -Eigenschaft der Datei hinzugefügt und alle Verweise auf die Datei werden mit der der Datei zugewiesenen UUID aktualisiert. <br> **Standardwert**: `"^GUID-(?<id>.*)"` |

>[!TAB On-Premise]

Führen Sie die folgenden Schritte aus, um Dateinamen mit einem UUID-Muster zu vergleichen und Dateien ohne zugewiesene UUID UUID zuzuweisen:

1. Öffnen Sie die Seite Konfiguration der Adobe Experience Manager-Web-Konsole .

   Die Standard-URL für den Zugriff auf die Konfigurationsseite lautet:

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Suchen Sie nach dem Bundle *com.adobe.fmdita.config.ConfigManager* und wählen Sie es aus.

1. Geben **in der Eigenschaft** UUID-Dateinamenmuster“ ein Muster an, um die Namen der importierten Datei zu überprüfen.

   Wenn eine Datei nicht dem angegebenen Muster folgt, wird eine UUID zur -Eigenschaft der Datei hinzugefügt und alle Verweise auf die Datei werden mit der der Datei zugewiesenen UUID aktualisiert.

1. Wählen Sie **Speichern** aus.

>[!ENDTABS]





