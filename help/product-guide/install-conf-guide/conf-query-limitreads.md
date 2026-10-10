---
title: Konfigurieren der Anzahl der LimitReads für eine Abfrage
description: Erfahren Sie, wie Sie die Anzahl der LimitReads für eine Abfrage konfigurieren
feature: Web Editor Configuration
role: Admin
level: Experienced
exl-id: 53748636-f3d1-4b3b-a772-2730b78741cb
product_v2:
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
    internal-label: Experience Manager
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
    internal-label: Experience Manager Guides
feature_v2:
  - id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
    internal-label: Configuration
subfeature_v2:
  - id: b0521e56-a0b2-40b6-bf47-ebc98751f9ba
    internal-label: Web Editor configuration
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
level_v2:
  - id: d378ca77-2da1-4f39-ad92-1917fe974a38
    internal-label: Experienced
source-git-commit: 81a0e7f0736ba4970673dd87a888a4c60d3c1b4e
workflow-type: tm+mt
source-wordcount: '100'
ht-degree: 2%
---
# Konfigurieren der Anzahl der LimitReads für eine On-Premise-Abfrage

Um die Anzahl der Knoten zu erhöhen, die eine Abfrage gleichzeitig lesen kann, führen Sie die folgenden Schritte aus:

1. Öffnen Sie die JMX-Seite der Adobe Experience Manager-Web-Konsole.

   Die Standard-URL für den Zugriff auf die Konfigurationsseite lautet:

   ```http
   http://<server name>:<port>/system/console/jmx
   ```

1. Suchen Sie nach „QueryEngineSettings **und klicken Sie darauf**.

1. Ändern Sie den Attributwert für das Attribut **LimitReads**.

1. Klicken Sie auf **Speichern**.


Wenn Sie diesen Attributwert erhöhen, können Sie damit den Bericht für größere DITA-Zuordnungen erstellen.

**Übergeordnetes Thema:**[ Editor anpassen](customize-overview.md)
