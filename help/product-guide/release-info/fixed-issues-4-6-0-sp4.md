---
title: Versionshinweise zu | Es wurden Probleme in Adobe Experience Manager Guides 4.6.0 Service Pack 4 behoben
description: Erfahren Sie mehr über die Fehlerbehebungen in Version 4.6.0 Service Pack 4 von Adobe Experience Manager Guides
role: Leader
source-git-commit: f9a03ae620a362989a36ebaefb264ea28220a4b3
workflow-type: tm+mt
source-wordcount: '239'
ht-degree: 1%

---

# Es wurden Probleme in Version 4.6.0 Service Pack 4 (April 2025) behoben


Dieser Artikel behandelt die in verschiedenen Bereichen von Version 4.6.0 Service Pack 4 von Adobe Experience Manager Guides behobenen Fehler.

Erfahren Sie mehr [Upgrade-Anweisungen für Version 4.6.0 Service Pack 4](upgrade-instructions-4-6-0-sp4.md).

## Erstellung

- Durch Ziehen und Ablegen eines Bildes in einem Thema in **Autoren** Ansicht wird der Bildverweis beschädigt, was zu Datenverlust führt. 25769)
- Durch Ziehen und Ablegen einer `topicref` in einer Zuordnung in der **Autoren** Ansicht wird der beabsichtigte Vorgang nicht ausgeführt und die `topicref` neben der gezogenen `topicref` wird entfernt. 19460)
- Wenn JCR-Sitzungsverbindungen beim Aktualisieren oder Erstellen von Themen nicht geschlossen werden, führt dies zu Speicherlecks und Service-Ausfallzeiten. 26282)

## Veröffentlichung

- Die native PDF-Veröffentlichung wird auf unbestimmte Zeit fortgesetzt, wenn der DITA-Inhalt über einen Weblink verfügt, ohne dass der Umfang wie `external` vorhanden ist. 26434)
- Beim Erstellen einer neuen Baseline mit einer großen Anzahl von Kennzeichnungen schlägt das Kennzeichnungsladeprogramm fehl und verhindert, dass die Kennzeichnungen abgerufen werden. 16232)
- Die Veröffentlichung nativer PDFs und AEM-Sites verzögert sich und wird in die Warteschlange gestellt, wenn Fehler im Inhalt auftreten. 26516)

## Bekannte Probleme

Adobe hat das folgende bekannte Problem für diese Version erkannt:

- Die native PDF-Veröffentlichung unter Windows tritt auf, wenn der DITA-Inhalt einen externen Link enthält, der das `scope`-Attribut nicht enthält.
