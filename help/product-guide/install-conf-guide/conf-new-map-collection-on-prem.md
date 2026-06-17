---
title: Konfigurieren einer neuen Zuordnungssammlung für On-Premise
description: Erfahren Sie, wie Sie eine neue Zuordnungssammlung für On-Premise konfigurieren
feature: Configuration
role: Admin
level: Experienced
source-git-commit: da97ff167c70034dc1801792e7ccdf82d733c688
workflow-type: tm+mt
source-wordcount: '75'
ht-degree: 2%

---

# Konfigurieren einer neuen Zuordnungssammlung für On-Premise

Die folgenden Schritte erläutern, wie Sie die neue Zuordnungssammlung in Ihrer On-Premise-Umgebung aktivieren.

1. Öffnen Sie die Seite Konfiguration der Adobe Experience Manager-Web-Konsole .

   Die Standard-URL für den Zugriff auf die Konfigurationsseite lautet:

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Suchen Sie nach dem Bundle **com.adobe.fmdita.config.ConfigManager** und wählen Sie es aus.

1. Aktivieren Sie die Einstellung **Neue Zuordnungssammlungen aktivieren** (enable.new.map.collections).

   ![](assets/new-map-collection.png){width="800"}

1. Wählen Sie **Speichern** aus.
