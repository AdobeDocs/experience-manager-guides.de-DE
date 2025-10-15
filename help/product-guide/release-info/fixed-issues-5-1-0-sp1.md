---
title: Versionshinweise zu | Es wurden Probleme in Adobe Experience Manager Guides 5.1.0 Service Pack 1 behoben
description: Erfahren Sie mehr über die Fehlerbehebungen in Version 5.1.0 Service Pack 1 von Adobe Experience Manager Guides
role: Leader
source-git-commit: 575488e1b378c17419add75876a8e7f7423d5116
workflow-type: tm+mt
source-wordcount: '148'
ht-degree: 1%

---

# Es wurden Probleme in Version 5.1.0 Service Pack 1 (Oktober 2025) behoben


Dieser Artikel behandelt die in verschiedenen Bereichen von Version 5.1.0 Service Pack 1 von Adobe Experience Manager Guides behobenen Fehler.

Erfahren Sie mehr über [Upgrade-Anweisungen für die Version 5.1.0 Service Pack 1](upgrade-instructions-5-1-0-sp1.md).


## Platform

- Wenn Sie bei der Migration von Nicht-UUID zu UUID und der Aktualisierung auf die neueste Version (5.0+) referenzierte Bilder zwischen Ordnern verschieben und dann die DITA-Dateien (wo diese Bilder referenziert wurden) auf frühere Versionen zurücksetzen, führt dies zu fehlerhaften Bildverweisen. (GUIDES-34315)

## Publishing

- Beim Veröffentlichen einer DITA-Zuordnung mit Baseline auf AEM Sites (mit veralteter Komponentenzuordnung) werden auch die Zuordnungselemente mit dem Attribut `processing-role = resource-only` veröffentlicht. (GUIDES-34298)
