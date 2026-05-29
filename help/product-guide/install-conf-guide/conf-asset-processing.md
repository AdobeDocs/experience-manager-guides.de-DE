---
title: Konfigurieren der Asset-Verarbeitung für Cloud Service
description: Erfahren Sie, wie Sie die Asset-Verarbeitung für Cloud Service konfigurieren
feature: Output Generation
role: Admin
level: Experienced
exl-id: 0b66a515-d8f1-4ea6-913f-e152ae114698
source-git-commit: 5af3356dff3c42b8a93ed97b5ee20b23976769a4
workflow-type: tm+mt
source-wordcount: '121'
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

1. Konfigurieren Sie die Einstellung **Handbücher zur Asset-Verarbeitung für geplanten Auftrag aktivieren** (`enable.asset.processing.scheduler`) nach Ihren Anforderungen. Standardmäßig ist die Einstellung aktiviert.

1. Klicken Sie auf **Speichern**.

>[!ENDTABS]
