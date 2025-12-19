---
title: Migration von Nicht-UUID zu UUID-Inhalt
description: Erfahren Sie, wie Sie Nicht-UUID-Inhalte zu UUID-Inhalten migrieren
exl-id: f8b723bf-84c0-4fe6-936e-63970fb3e417
feature: Migration
role: Admin
level: Experienced
source-git-commit: 56f1bd81e74ad9b479b2dcbcf04e1ee82e9a9041
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

- [**4.3.1 Migration von Nicht-UUID-zu-4.3.2-UUID-Inhalten**](./migrate-non-uuid-4-3.md)
- [**4.6.0 Service Pack 4 Migration von Nicht-UUID-zu-4.6.1-UUID-Inhalten**](./migrate-non-uuid-uuid-4-6.md)



