---
title: Konvertieren von Nicht-UUID-Inhalten ohne Versionen in UUID-Inhalte
description: Erfahren Sie, wie Sie Nicht-UUID-Inhalte ohne Versionen migrieren.
exl-id: 44b5660d-9961-4463-9686-53085249fb05
feature: Migration
role: Admin
level: Experienced
hidefromtoc: 'yes'
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
source-wordcount: '88'
ht-degree: 0%
---
# Migrieren von nicht versionierten Inhalten

>[!IMPORTANT]
>
> Sie können diesen Migrationsansatz wählen, wenn Sie die Asset-Versionen ignorieren oder nicht migrieren möchten.


1. Herunterladen und Hochladen von Assets von der Nicht-UUID-Instanz in die UUID-Instanz direkt von der AEM Assets-Benutzeroberfläche mithilfe von Adobe-Tools wie dem AEM-Desktop-Programm.

1. Stellen Sie sicher, dass Sie den Workflow DAM-Update-Asset aktivieren und ihn für alle Assets ausführen, nachdem Sie den Inhalt für die GUID-Erstellung importiert haben.
