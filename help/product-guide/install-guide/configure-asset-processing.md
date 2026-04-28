---
title: Konfigurieren der Asset-Verarbeitung für On-Premise-Services
description: Konfigurieren der Asset-Verarbeitung für On-Premise-Services
feature: Output Generation
role: Admin
level: Experienced
exl-id: 9d771bba-aa90-4726-a75f-1cb7b804a192
source-git-commit: ccaf2ead1a9a24ab822298c6b9ef6866a1c32e8c
workflow-type: tm+mt
source-wordcount: '68'
ht-degree: 2%

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

1. Klicken Sie auf **Speichern**.
