---
title: Konfigurieren Sie das Überspringen von Peer-Links für Baseline V1 in On-Premise
description: Erfahren Sie, wie Sie das Überspringen von Peer-Links für Baseline V1 in On-Premise aktivieren oder deaktivieren
feature: Configuration
role: Admin
level: Experienced
source-git-commit: 8d231bdbf00adb354bc31616e880495b00a3959c
workflow-type: tm+mt
source-wordcount: '101'
ht-degree: 1%

---

# Konfigurieren des Überspringens von Peer-Links für alte Baseline in On-Premise

Die folgenden Schritte erklären, wie Sie das Überspringen von Peer-Links für die alte Baseline in Ihrer On-Premise-Umgebung aktivieren.

1. Öffnen Sie die Seite Konfiguration der Adobe Experience Manager-Web-Konsole .

   Die Standard-URL für den Zugriff auf die Konfigurationsseite lautet:

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Suchen Sie nach dem Bundle **com.adobe.fmdita.config.ConfigManager** und wählen Sie es aus.

1. Aktivieren Sie die Einstellung **Peer-Links für Baseline V1 überspringen** (guides.baseline.v1.skip.peer.links). Standardmäßig ist diese Einstellung deaktiviert.

1. Wählen Sie **Speichern** aus.
