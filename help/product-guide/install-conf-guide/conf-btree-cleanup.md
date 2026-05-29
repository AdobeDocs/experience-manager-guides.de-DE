---
title: Konfigurieren des Bereinigungsauftrags für den Referenzspeicher
description: Konfigurieren des Bereinigungsauftrags für den Referenzspeicher
feature: Output Generation
role: Admin
level: Experienced
exl-id: 58f98313-fc91-43b3-9553-aa5ab4946925
source-git-commit: 370a28a06a37b632873a79c9b83b8660a0221dd8
workflow-type: tm+mt
source-wordcount: '247'
ht-degree: 3%

---

# Konfigurieren der Bereinigung des Referenzspeichers

Richten Sie den Auftrag zur Bereinigung des Referenz-Stores ein und verwalten Sie die `Guides BTree deletion`, um Ihr System optimiert und den Speicher sauber zu halten.

## Konfigurieren des Bereinigungsauftrags für den Referenzspeicher

Die folgenden Registerkarten enthalten Anweisungen zum Konfigurieren des Bereinigungsauftrags für den Referenzspeicher basierend auf Ihrer Experience Manager Guides-Einrichtung: Cloud Service oder On-Premise.

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

1. Aktualisieren Sie den Cron-Ausdruck, um die Ausführungshäufigkeit des Auftrags für die Planung der Referenz-Store-Bereinigung einzurichten.

1. Konfigurieren Sie den Zeitplan für die Bereinigung des Referenzspeichers wie unten dargestellt.

   ![](assets/btree-cleanup-config.png)

1. Klicken Sie auf **Speichern**.

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
1. Aktivieren Sie die Einstellung **Guides btree delete enabled** (btree.delete.enabled).

   ![](assets/btree-cleanup-setting.png)

1. Wählen Sie **Speichern** aus.

>[!ENDTABS]
