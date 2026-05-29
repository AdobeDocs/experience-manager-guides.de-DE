---
title: Neuen Editor konfigurieren
description: Erfahren Sie, wie Sie den neuen Editor aktivieren oder deaktivieren
feature: Configuration
role: Admin
level: Experienced
source-git-commit: 8d231bdbf00adb354bc31616e880495b00a3959c
workflow-type: tm+mt
source-wordcount: '79'
ht-degree: 2%

---

# Konfigurieren des neuen Editors für On-Premise

>[!IMPORTANT]
>
> Stellen Sie Systemkonfigurationen über Code bereit, anstatt sie manuell in der Laufzeitumgebung anzuwenden.

In den folgenden Schritten wird erläutert, wie Sie den neuen Editor in Ihrer On-Premise-Umgebung aktivieren.

1. Öffnen Sie die Seite Konfiguration der Adobe Experience Manager-Web-Konsole .

   Die Standard-URL für den Zugriff auf die Konfigurationsseite lautet:

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Suchen Sie nach dem Bundle **com.adobe.fmdita.config.ConfigManager** und wählen Sie es aus.

1. Aktivieren Sie die Einstellung **Editor 2.0 aktivieren** (`enable.markup.editor`).

1. Wählen Sie **Speichern** aus.

