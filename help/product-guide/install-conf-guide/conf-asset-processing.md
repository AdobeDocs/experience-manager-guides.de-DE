---
title: Konfigurieren der Asset-Verarbeitung für Cloud Service
description: Erfahren Sie, wie Sie die Asset-Verarbeitung für Cloud Service konfigurieren
feature: Output Generation
role: Admin
level: Experienced
source-git-commit: 6f3f05419f4f5cdd45ab580cdee6fa869f20f01d
workflow-type: tm+mt
source-wordcount: '113'
ht-degree: 3%

---

# Asset-Verarbeitungsfunktion konfigurieren

Die folgenden Registerkarten enthalten Anweisungen zur Konfiguration der Asset-Verarbeitungsfunktion basierend auf Ihrer Experience Manager Guides-Einrichtung: Cloud Service oder On-Premise.

>[!BEGINTABS]

>[!TAB Cloud Service]

1. Verwenden Sie die Anweisungen unter [Konfigurationsüberschreibungen](download-install-config-override.md), um die Konfigurationsdatei zu erstellen.

1. Geben Sie in der Konfigurationsdatei die folgenden Details (Eigenschaft) an:

   | PID | Eigenschaftsschlüssel | Eigenschaftswert |
   |---|---|---|
   | `com.adobe.fmdita.config.ConfigManager` | `enable.asset.processing.scheduler` | **Standardwert:** „true“ |

>[!TAB On-Premise]

1. Öffnen Sie die Seite Konfiguration der Adobe Experience Manager-Web-Konsole .

   Die Standard-URL für den Zugriff auf die Konfigurationsseite lautet:

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Suchen Sie nach dem Bundle *com.adobe.fmdita.config.ConfigManager* und wählen Sie es aus.

1. Konfigurieren Sie die `Enable Guides asset processing scheduled job` gemäß Ihren Anforderungen. Standardmäßig ist die Einstellung aktiviert.

1. Wählen Sie **Speichern** aus.

>[!ENDTABS]