---
title: Konfigurieren des B-Tree-Bereinigungsauftrags für On-Premise-Services
description: Konfigurieren des B-Tree-Bereinigungsauftrags für On-Premise-Services
feature: Output Generation
role: Admin
level: Experienced
exl-id: ff6f968c-3440-4757-882a-676711ad05c3
TQID: 'https://experienceleague.adobe.com/qvOHGtHbgKS3xUv0pEXKTqeWblIDj8JKJwik8heXwPo'
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
    internal-label: Experience Manager Guides
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
    internal-label: Experience Manager
feature_v2:
  - id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
    internal-label: Configuration
  - id: a3bd6397-2eb2-4908-a61c-226e26855dca
    internal-label: Publishing
subfeature_v2:
  - id: fd6cc9e1-e5e5-494e-b7b1-a32f2d6cd7c9
    internal-label: Output generation
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
level_v2:
  - id: d378ca77-2da1-4f39-ad92-1917fe974a38
    internal-label: Experienced
source-git-commit: 81a0e7f0736ba4970673dd87a888a4c60d3c1b4e
workflow-type: tm+mt
source-wordcount: '156'
ht-degree: 2%
---
# Konfigurieren der B-Tree-Bereinigung

Richten Sie den B-Tree-Bereinigungsauftrag ein und verwalten Sie die `Guides B-tree deletion`, um Ihr System optimiert und den Speicher sauber zu halten.

## B-Tree-Bereinigungsauftrag konfigurieren

Führen Sie die folgenden Schritte aus, um den Bereinigungsauftrag für die B-Baumstruktur zu konfigurieren:

1. Öffnen Sie die Seite Konfiguration der Adobe Experience Manager-Web-Konsole .

   Die Standard-URL für den Zugriff auf die Konfigurationsseite lautet:

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Suchen Sie nach dem Bundle *com.adobe.guides.utils.schedulers.GuidesBTreesCleanupSchedulerJob* und wählen Sie es aus.

1. Aktualisieren Sie den Cron-Ausdruck, um die Ausführungshäufigkeit des Auftrags für die B-Tree-Bereinigungsplanung einzurichten.

1. Konfigurieren Sie den Bereinigungs-Scheduler für die B-Baumstruktur wie unten gezeigt.

   ![](assets/btree-cleanup-config.png)

1. Wählen Sie **Speichern** aus.


## Konfigurieren der Einstellungen für das Löschen von Handbüchern mit B-Baumstruktur

Führen Sie folgende Schritte aus, um die Einstellung zu aktivieren:

1. Öffnen Sie die Seite Konfiguration der Adobe Experience Manager-Web-Konsole .

   Die Standard-URL für den Zugriff auf die Konfigurationsseite lautet:

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Suchen Sie nach dem Bundle *com.adobe.fmdita.config.ConfigManager* und wählen Sie es aus.
1. Aktivieren Sie die `Guides btree deletion enabled`.

   ![](assets/btree-cleanup-setting.png)

1. Wählen Sie **Speichern** aus.
