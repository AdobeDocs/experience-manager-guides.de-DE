---
title: B-Tree-Bereinigungsauftrag für Cloud-Services konfigurieren
description: B-Tree-Bereinigungsauftrag für Cloud-Services konfigurieren
feature: Output Generation
role: Admin
level: Experienced
exl-id: de464e92-f17b-4c99-98f2-fdba8d214129
TQID: https://experienceleague.adobe.com/-n4Winzqo-HNb2FDH6RI223UT9uvuOc8-OT7mgXjblc
product_v2: id: fae5e35a-80c9-4b94-9352-1a060a6aab1did: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2: id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 132
ht-degree: 3%

---

# Konfigurieren der B-Tree-Bereinigung

Richten Sie den B-Tree-Bereinigungsauftrag ein und verwalten Sie die `Guides BTree deletion`, um Ihr System optimiert und den Speicher sauber zu halten.

## B-Tree-Bereinigungsauftrag konfigurieren

Führen Sie die folgenden Schritte aus, um den Bereinigungsauftrag für die B-Baumstruktur zu konfigurieren:

1. Verwenden Sie die Anweisungen unter [Konfigurationsüberschreibungen](../cs-install-guide/download-install-additional-config-override.md), um die Konfigurationsdatei zu erstellen.

1. Geben Sie in der Konfigurationsdatei die folgenden Details (Eigenschaft) an:

   | PID | Eigenschaftsschlüssel | Eigenschaftswert |
   |---|---|---|
   | `com.adobe.guides.utils.schedulers.GuidesBTreesCleanupSchedulerJob` | `cronExpression` | **Standardwert:** „0 0 0 * * ?“ |


## Konfigurieren der Einstellungen für das Löschen von Handbüchern mit B-Baumstruktur

Führen Sie folgende Schritte aus, um die Einstellung zu aktivieren:

1. Verwenden Sie die Anweisungen unter [Konfigurationsüberschreibungen](../cs-install-guide/download-install-additional-config-override.md), um die Konfigurationsdatei zu erstellen.

1. Geben Sie in der Konfigurationsdatei die folgenden Details (Eigenschaft) an:

   | PID | Eigenschaftsschlüssel | Eigenschaftswert |
   |---|---|---|
   | `com.adobe.fmdita.config.ConfigManager` | `btree.deletion.enabled` | **Standardwert:** „true“ |
