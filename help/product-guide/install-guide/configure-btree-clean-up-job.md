---
title: Konfigurieren des B-Tree-Bereinigungsauftrags für On-Premise-Services
description: Konfigurieren des B-Tree-Bereinigungsauftrags für On-Premise-Services
feature: Output Generation
role: Admin
level: Experienced
exl-id: ff6f968c-3440-4757-882a-676711ad05c3
TQID: https://experienceleague.adobe.com/qvOHGtHbgKS3xUv0pEXKTqeWblIDj8JKJwik8heXwPo
product_v2: id: fae5e35a-80c9-4b94-9352-1a060a6aab1did: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2: id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 156
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

1. Klicken Sie auf **Speichern**.


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

1. Klicken Sie auf **Speichern**.
