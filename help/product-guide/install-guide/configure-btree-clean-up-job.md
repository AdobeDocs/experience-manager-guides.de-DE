---
title: Konfigurieren des B-Tree-Bereinigungsauftrags für On-Premise-Services
description: Konfigurieren des B-Tree-Bereinigungsauftrags für On-Premise-Services
feature: Output Generation
role: Admin
level: Experienced
source-git-commit: e1b332b100cc8e3937557e4617d66352c1a0dc3c
workflow-type: tm+mt
source-wordcount: '145'
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

   ![](assets/btree-cleanup-config.png){align="left"}

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

   ![](assets/btree-cleanup-setting.png){align="left"}

1. Wählen Sie **Speichern** aus.

