---
title: Konfigurieren der DITA Assets-Replikation für On-Premise-Services
description: Erfahren Sie, wie Sie die Replikation von DITA-Assets für On-Premise-Services konfigurieren
feature: Output Generation
role: Admin
level: Experienced
exl-id: 49fd9dfe-e1a5-4388-abbd-ec5d45669b45
hidefromtoc: true
source-git-commit: 3aadc59f5034828cf319992b7acb32d5a88eaf93
workflow-type: tm+mt
source-wordcount: '71'
ht-degree: 2%

---

# Konfigurieren der DITA-Asset-Replikation

Führen Sie die folgenden Schritte aus, um die Asset-Verarbeitungsfunktion zu konfigurieren:

1. Öffnen Sie die Seite Konfiguration der Adobe Experience Manager-Web-Konsole .

   Die Standard-URL für den Zugriff auf die Konfigurationsseite lautet:

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Suchen Sie nach dem Bundle *com.adobe.fmdita.config.ConfigManager* und wählen Sie es aus.

1. Konfigurieren Sie die `Replicate DITA assets` gemäß Ihren Anforderungen. Standardmäßig ist die Einstellung aktiviert.


   ![](assets/dita-assets-replication.png){width="350" align="left"}


1. Wählen Sie **Speichern** aus.
