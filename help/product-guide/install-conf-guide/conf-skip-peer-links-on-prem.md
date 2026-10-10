---
title: Konfigurieren Sie das Überspringen von Peer-Links für Baseline V1 in On-Premise
description: Erfahren Sie, wie Sie das Überspringen von Peer-Links für Baseline V1 in On-Premise aktivieren oder deaktivieren
feature: Configuration
role: Admin
level: Experienced
product_v2:
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
    internal-label: Experience Manager
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
    internal-label: Experience Manager Guides
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
level_v2:
  - id: d378ca77-2da1-4f39-ad92-1917fe974a38
    internal-label: Experienced
source-git-commit: 81a0e7f0736ba4970673dd87a888a4c60d3c1b4e
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
