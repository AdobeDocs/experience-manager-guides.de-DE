---
title: B-Tree-Bereinigungsauftrag für Cloud-Services konfigurieren
description: B-Tree-Bereinigungsauftrag für Cloud-Services konfigurieren
feature: Output Generation
role: Admin
level: Experienced
source-git-commit: 6f3f05419f4f5cdd45ab580cdee6fa869f20f01d
workflow-type: tm+mt
source-wordcount: '235'
ht-degree: 3%

---

# Konfigurieren der B-Tree-Bereinigung

Richten Sie den B-Tree-Bereinigungsauftrag ein und verwalten Sie die `Guides BTree deletion`, um Ihr System optimiert und den Speicher sauber zu halten.

## B-Tree-Bereinigungsauftrag konfigurieren

Die folgenden Registerkarten enthalten Anweisungen zum Konfigurieren eines B-Tree-Bereinigungsauftrags basierend auf Ihrer Experience Manager Guides-Einrichtung: Cloud Service oder On-Premise.

>[!BEGINTABS]

>[!TAB Cloud Service]

1. Verwenden Sie die Anweisungen unter [Konfigurationsüberschreibungen](download-install-config-override.md), um die Konfigurationsdatei zu erstellen.

1. Geben Sie in der Konfigurationsdatei die folgenden Details (Eigenschaft) an:

   | PID | Eigenschaftsschlüssel | Eigenschaftswert |
   |---|---|---|
   | `com.adobe.guides.utils.schedulers.GuidesBTreesCleanupSchedulerJob` | `cronExpression` | **Standardwert:** „0 0 0 * * ?“ |

>[!TAB On-Premise]

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

>[!ENDTABS]

## Konfigurieren der Einstellungen für das Löschen von Handbüchern mit B-Baumstruktur

Die folgenden Registerkarten enthalten Anweisungen zum Aktivieren der Einstellung entsprechend Ihrer Experience Manager Guides-Einrichtung: Cloud Service oder On-Premise.

>[!BEGINTABS]

>[!TAB Cloud Service]

1. Verwenden Sie die Anweisungen unter [Konfigurationsüberschreibungen](download-install-config-override.md), um die Konfigurationsdatei zu erstellen.

1. Geben Sie in der Konfigurationsdatei die folgenden Details (Eigenschaft) an:

   | PID | Eigenschaftsschlüssel | Eigenschaftswert |
   |---|---|---|
   | `com.adobe.fmdita.config.ConfigManager` | `btree.deletion.enabled` | **Standardwert:** „true“ |

>[!TAB On-Premise]

1. Öffnen Sie die Seite Konfiguration der Adobe Experience Manager-Web-Konsole .

   Die Standard-URL für den Zugriff auf die Konfigurationsseite lautet:

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Suchen Sie nach dem Bundle *com.adobe.fmdita.config.ConfigManager* und wählen Sie es aus.
1. Aktivieren Sie die `Guides btree deletion enabled`.

   ![](assets/btree-cleanup-setting.png){align="left"}

1. Wählen Sie **Speichern** aus.

>[!ENDTABS]