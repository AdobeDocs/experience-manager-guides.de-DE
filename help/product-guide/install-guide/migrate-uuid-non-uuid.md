---
title: Migration von Nicht-UUID zu UUID-Inhalt
description: Erfahren Sie, wie Sie Nicht-UUID-Inhalte zu UUID-Inhalten migrieren
exl-id: f8b723bf-84c0-4fe6-936e-63970fb3e417
feature: Migration
role: Admin
level: Experienced
source-git-commit: 6e23f52fc9124d0f07f8108da1b5fe574f553469
workflow-type: tm+mt
source-wordcount: '205'
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
| 4.3.1 non-UUID | 4.3.2 UUID | Nach der Migration auf Version 4.3.2 UUID können Sie 4.6.0 (UUID) direkt installieren. Wenn Sie Version 4.6.0 verwenden, aktualisieren Sie auf Version 5.1.0 und installieren Sie dann 5.1.0 Service Pack 1. |
| 4.6.0 Service Pack 4 non-UUID | 4.6.1 UUID | Nach der Migration auf Version 4.6.1 UUID können Sie direkt auf 5.1.0 (UUID) aktualisieren. Sobald das Upgrade abgeschlossen ist, installieren Sie Version 5.1.0 Service Pack 1. |

Ausführliche Schritte zur Migration Ihrer Inhalte finden Sie in den folgenden Artikeln:

- [**4.3.1 Migration von Nicht-UUID-zu-4.3.2-UUID-Inhalten**](./migrate-non-uuid-4-3.md)
- [**4.6.0 Service Pack 4 Migration von Nicht-UUID-zu-4.6.1-UUID-Inhalten**](./migrate-non-uuid-uuid-4-6.md)



