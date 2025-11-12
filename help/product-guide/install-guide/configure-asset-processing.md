---
title: Konfigurieren der Asset-Verarbeitung für On-Premise-Services
description: Konfigurieren der Asset-Verarbeitung für On-Premise-Services
feature: Output Generation
role: Admin
level: Experienced
source-git-commit: e1b332b100cc8e3937557e4617d66352c1a0dc3c
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
