---
title: Versionshinweise | Behobene Probleme in Adobe Experience Manager Guides 5.1.0 Service Pack 1
description: Erfahren Sie mehr über die Fehlerbehebungen in Version 5.1.0 Service Pack 1 von Adobe Experience Manager Guides
role: Leader
exl-id: 4b51085b-1f71-41e2-b0a9-88a12990fc97
TQID: https://experienceleague.adobe.com/HEWV5RxPUfqUYf6m6kQW-fU-LiAM0UFGbfzKjtOCZxk
product_v2: id: fae5e35a-80c9-4b94-9352-1a060a6aab1did: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2: id: a3bd6397-2eb2-4908-a61c-226e26855dca
role_v2: id: f8a45b24-4be7-4f1b-909b-60d06b483a20
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 144
ht-degree: 1%

---

# Es wurden Probleme in Version 5.1.0 Service Pack 1 (Oktober 2025) behoben


Dieser Artikel behandelt die in verschiedenen Bereichen von Version 5.1.0 Service Pack 1 von Adobe Experience Manager Guides behobenen Fehler.

Erfahren Sie mehr über [Upgrade-Anweisungen für die Version 5.1.0 Service Pack 1](upgrade-instructions-5-1-0-sp1.md).


## Platform

- Wenn Sie bei der Migration von Nicht-UUID zu UUID und der Aktualisierung auf die neueste Version (5.0+) referenzierte Bilder zwischen Ordnern verschieben und dann die DITA-Dateien (wo diese Bilder referenziert wurden) auf frühere Versionen zurücksetzen, führt dies zu fehlerhaften Bildverweisen. (GUIDES-34315)

## Publishing

- Beim Veröffentlichen einer DITA-Zuordnung mit Baseline auf AEM Sites (mit veralteter Komponentenzuordnung) werden auch die Zuordnungselemente mit dem Attribut `processing-role = resource-only` veröffentlicht. (GUIDES-34298)
