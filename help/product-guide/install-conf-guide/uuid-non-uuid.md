---
title: Migration von Nicht-UUID zu UUID-Inhalt
description: Erfahren Sie, wie Sie Nicht-UUID-Inhalte zu UUID-Inhalten migrieren
feature: Migration
role: Admin
level: Experienced
exl-id: 20c977de-db01-4d1e-ba8c-7fffc2a54231
product_v2:
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
    internal-label: Experience Manager
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
    internal-label: Experience Manager Guides
feature_v2:
  - id: 5be0fc8f-1cff-5c3e-bb92-2903a56a3de6
    internal-label: Migration
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
level_v2:
  - id: d378ca77-2da1-4f39-ad92-1917fe974a38
    internal-label: Experienced
source-git-commit: 81a0e7f0736ba4970673dd87a888a4c60d3c1b4e
workflow-type: tm+mt
source-wordcount: '320'
ht-degree: 0%
---
# Migration von Nicht-UUID zu UUID-Inhalt {#id226TI0U20XA}


Sie können Nicht-UUID-Inhalte basierend auf der aktuellen Version von Experience Manager Guides, die Sie verwenden, zu UUID migrieren.

>[!IMPORTANT]
>
> Bevor Sie Inhalte zum UUID-Server migrieren, stellen Sie sicher, dass Sie einen Nicht-UUID-Server mit einer kompatiblen AEM Guides-Version darauf installiert haben.

## Kompatibilitätsmatrix

Verwenden Sie die folgende Matrix, um den richtigen Migrationspfad basierend auf Ihrer aktuellen Nicht-UUID-Version zu ermitteln. Dies gewährleistet einen reibungslosen Übergang nach der Migration.

| Für die Migration ist keine UUID-Version erforderlich | UUID-Version nach der Migration | Unterstützter Aktualisierungspfad nach der Migration |
|---|---|---|
| 4.3.1 non-UUID | 4.3.2 UUID | Nach der Migration auf Version 4.3.2 UUID müssen Sie 4.6.0 (UUID) direkt installieren. Wenn Sie Version 4.6.0 verwenden, aktualisieren Sie auf Version 5.1.0 und installieren Sie dann 5.1.0 Service Pack 3. |
| 4.6.0 Service Pack 4 non-UUID | 4.6.1 UUID | Nach der Migration auf Version 4.6.1 UUID müssen Sie direkt auf 5.1.0 (UUID) aktualisieren. Sobald das Upgrade abgeschlossen ist, installieren Sie Version 5.1.0 Service Pack 3. |

## Schätzung der Migrationszeit

Das Migrationsdienstprogramm verarbeitet Assets mit einer durchschnittlichen Rate von ~50 ms pro Asset. Die folgende Tabelle enthält Schätzungen der Migrationszeit für ein System, das mit 64 vCPUs, 128 GB RAM und SSD-gestütztem Speicher konfiguriert ist. Bei größeren Repositorys oder Assets mit vielen Ausgabedarstellungen oder hochauflösenden Binärdateien kann der Speicherbedarf steigen.

>[!NOTE]
>
> Die tatsächliche Migrationszeit kann je nach Hardware-Leistung, Speicherdurchsatz, gleichzeitigen AEM-Aktivitäten und Gesamtsystemlast variieren.


| **Asset-Anzahl** | **ca. Zeit** |
|-----------------|-------------------------|
| 10 K | ~8-9 Minuten |
| 50 K | ~42 Minuten |
| 100 K | ~1,4 Stunden |
| 250 K | ~3,5 Stunden |
| 500 K | ~7 Stunden |
| 750 K | ~10,5 Stunden |
| 1 Mio. | ~14 Stunden |
| 2 M | ~28 Stunden (~1,2 Tage) |
| 3 M | ~42 Stunden (~1,75 Tage) |
| 5m | ~69 Stunden (~2,9 Tage) |
| 10 M | ~139 Stunden (~5,8 Tage) |


Ausführliche Schritte zur Migration Ihrer Inhalte finden Sie in den folgenden Artikeln:

- [**4.3.1 Migration von Nicht-UUID-zu-4.3.2-UUID-Inhalten**](../install-conf-guide/non-uuid-4-3.md)
- [Migration von **4.6.0 Service Pack 4 non-UUID zu 4.6.1 UUID-Inhalten**](../install-conf-guide/non-uuid-uuid-4-6.md)
