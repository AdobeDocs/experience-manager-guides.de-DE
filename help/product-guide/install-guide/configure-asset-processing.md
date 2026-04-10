---
title: Konfigurieren der Asset-Verarbeitung für On-Premise-Services
description: Konfigurieren der Asset-Verarbeitung für On-Premise-Services
feature: Output Generation
role: Admin
level: Experienced
exl-id: 9d771bba-aa90-4726-a75f-1cb7b804a192
hidefromtoc: true
source-git-commit: 3aadc59f5034828cf319992b7acb32d5a88eaf93
workflow-type: tm+mt
source-wordcount: '66'
ht-degree: 3%

---

# Asset-Verarbeitungsfunktion konfigurieren

Führen Sie die folgenden Schritte aus, um die Asset-Verarbeitungsfunktion zu konfigurieren:

1. Öffnen Sie die Seite Konfiguration der Adobe Experience Manager-Web-Konsole .

   Die Standard-URL für den Zugriff auf die Konfigurationsseite lautet:

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Suchen Sie nach dem Bundle *com.adobe.fmdita.config.ConfigManager* und wählen Sie es aus.

1. Konfigurieren Sie die `Enable Guides asset processing scheduled job` gemäß Ihren Anforderungen. Standardmäßig ist die Einstellung aktiviert.

1. Wählen Sie **Speichern** aus.
