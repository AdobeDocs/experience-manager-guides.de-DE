---
title: Konfigurieren der DITA Assets-Replikation
description: Erfahren Sie, wie Sie die Replikation von DITA-Assets konfigurieren
feature: Output Generation
role: Admin
level: Experienced
source-git-commit: 453da51a42984b912547570f2e1de70806b41171
workflow-type: tm+mt
source-wordcount: '109'
ht-degree: 3%

---

# Konfigurieren der DITA-Asset-Replikation

Die folgenden Registerkarten enthalten Anweisungen zur Konfiguration der DITA-Asset-Replikationsfunktion basierend auf Ihrer Experience Manager Guides-Einrichtung: Cloud Service oder On-Premise.

>[!BEGINTABS]

>[!TAB Cloud Service]

1. Verwenden Sie die Anweisungen unter [Konfigurationsüberschreibungen](../install-conf-guide/download-install-config-override.md), um die Konfigurationsdatei zu erstellen.

1. Geben Sie in der Konfigurationsdatei die folgenden Details (Eigenschaft) an:

   | PID | Eigenschaftsschlüssel | Eigenschaftswert |
   |---|---|---|
   | `com.adobe.fmdita.config.ConfigManager` | `publish.replicate` | **Standardwert:** „true“ |

>[!TAB On-Premise]

1. Öffnen Sie die Seite Konfiguration der Adobe Experience Manager-Web-Konsole .

   Die Standard-URL für den Zugriff auf die Konfigurationsseite lautet:

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Suchen Sie nach dem Bundle *com.adobe.fmdita.config.ConfigManager* und wählen Sie es aus.

1. Konfigurieren Sie die `Replicate DITA assets` gemäß Ihren Anforderungen. Standardmäßig ist die Einstellung aktiviert.


   ![](assets/dita-assets-replication.png){width="350" align="left"}


1. Wählen Sie **Speichern** aus.

>[!ENDTABS]
