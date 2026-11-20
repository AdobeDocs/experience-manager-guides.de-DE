---
title: Versionshinweise | Behobene Probleme in Adobe Experience Manager Guides Version 2026.11.0 Service Pack 1
description: Erfahren Sie mehr über die Fehlerbehebungen in der Version 2026.11.0 Service Pack 1 von Adobe Experience Manager Guides as a Cloud Service.
product_v2:
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
    internal-label: Experience Manager
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
    internal-label: Experience Manager Guides
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
source-git-commit: 8821e671951d83439688aa33f88ac1f91f0919eb
workflow-type: tm+mt
source-wordcount: '315'
ht-degree: 0%
---
# Es wurden Probleme in der Version 2026.11.0 von Service Pack 1 behoben

Dieser Artikel behandelt die Fehler, die in der Version 2026.11.0 Service Pack 1 von Adobe Experience Manager Guides as a Cloud Service behoben wurden.

## Publishing

Die folgenden Probleme treten bei der Veröffentlichung in AEM Sites auf (mit der Zuordnung zusammengesetzter Komponenten):

- Das erneute Generieren ausgewählter Themen oder einer Unterzuordnung mit `microservice-based` Veröffentlichung dauert etwa so lange wie das Generieren der vollständigen Zuordnung. (GUIDES-59322)
- Durch das erneute Generieren einer Unterzuordnung, die unterteilte Themen enthält, werden im Inhaltsverzeichnis falsche Titel und Links angezeigt. Jeder Themenblock-Eintrag zeigt den Titel des letzten Themenblocks an. (GUIDES-58650)

Die folgenden Probleme treten bei der Veröffentlichung in AEM Sites mit einer dynamischen Baseline auf, entweder Baseline (alt) oder Neue Baseline:

- Die Baseline wird während desselben Veröffentlichungsvorgangs mehrmals neu erstellt, was die Veröffentlichungszeit verlängert und in einigen Fällen dazu führt, dass die Wiederherstellung verzögert wird. Bei der neuen Baseline verwendet die inkrementelle Veröffentlichung auch eine veraltete Baseline anstelle der aktuellen, sodass die Ausgabe möglicherweise nicht den neuesten Inhalt widerspiegelt. (GUIDES-60189)
- Bei Verwendung des Zuordnungs -Dashboards treten einige Leistungsprobleme auf. (GUIDES-60189, GUIDES-55646)

## Bekannte Probleme

Adobe hat die folgenden bekannten Probleme in Version 2026.11.0 Service Pack 1 identifiziert:

- Bei Verwendung von Experience Manager Guides as a Cloud Service 2026.11.0 oder höher schlägt die Veröffentlichung mit einem Anwendungsfehler fehl, wenn AEM bestimmte interne Services während des Veröffentlichungsprozesses neu startet, z. B. beim Starten einer Server-Instanz. (GUIDES-60804)<br>**Problemumgehung:** Um das Problem zu beheben, wiederholen Sie die Veröffentlichung.
- Beim Generieren einer Ausgabe für mehrere AEM Sites-Vorgaben (unter Verwendung der Zuordnung zusammengesetzter Komponenten) oder native PDF-Vorgaben über **Zuordnungssammlung** oder API schlägt die Ausgabenerstellung mit einer `Rebuild the Baseline` Ausnahme fehl. <br>**Problemumgehung:** Veröffentlichen Sie die Vorgaben sequenziell anstatt gleichzeitig, um das Problem zu vermeiden.