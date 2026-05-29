---
title: Konfigurieren einer neuen Baseline für On-Premise
description: Erfahren Sie, wie Sie neue Baseline für On-Premise aktivieren oder deaktivieren
feature: Configuration
role: Admin
level: Experienced
source-git-commit: 8d231bdbf00adb354bc31616e880495b00a3959c
workflow-type: tm+mt
source-wordcount: '125'
ht-degree: 1%

---

# Konfigurieren einer neuen Baseline für On-Premise

>[!IMPORTANT]
>
> Stellen Sie Systemkonfigurationen über Code bereit, anstatt sie manuell in der Laufzeitumgebung anzuwenden.

Die folgenden Schritte erläutern, wie Sie die neue Baseline in Ihrer On-Premise-Umgebung aktivieren.

1. Öffnen Sie die Seite Konfiguration der Adobe Experience Manager-Web-Konsole .

   Die Standard-URL für den Zugriff auf die Konfigurationsseite lautet:

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Suchen Sie nach dem Bundle **com.adobe.fmdita.config.ConfigManager** und wählen Sie es aus.

1. Aktivieren Sie die Einstellung **Schnellere Baseline aktivieren (v2)**. Sie können auch nach dem genauen `enable.baseline.v2` für den Einstellungsnamen suchen.

1. Wählen Sie **Speichern** aus.

>[!NOTE]
>
>Nachdem Sie diese Funktion aktiviert haben, müssen Sie vorhandene Baselines zur neuen Baseline migrieren. Eine schrittweise Anleitung und ein Video mit einer exemplarischen Vorgehensweise finden Sie unter [Neue Grundlinie (Beta) in Experience Manager Guides](../user-guide/web-editor-baseline-v2.md).

