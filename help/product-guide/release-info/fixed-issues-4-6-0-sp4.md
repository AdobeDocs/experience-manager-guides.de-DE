---
title: Versionshinweise | Behobene Probleme in Adobe Experience Manager Guides 4.6.0 Service Pack 4
description: Erfahren Sie mehr über die Fehlerbehebungen in Version 4.6.0 Service Pack 4 von Adobe Experience Manager Guides
role: Leader
exl-id: ad69ea47-7880-43d1-8567-cd608fedb462
TQID: https://experienceleague.adobe.com/4ILARUO5umX41xE3Lcie-FsP396sgSqfbrWlMqdjsQ4
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2:
  - id: a3bd6397-2eb2-4908-a61c-226e26855dca
  - id: ab01a588-7dea-43f2-a699-0b3f128465d6
subfeature_v2:
  - id: d6596f3f-92a7-43ec-b444-237db6adad05
role_v2:
  - id: f8a45b24-4be7-4f1b-909b-60d06b483a20
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 234
ht-degree: 4%

---

# Es wurden Probleme in Version 4.6.0 Service Pack 4 (April 2025) behoben


Dieser Artikel behandelt die in verschiedenen Bereichen von Version 4.6.0 Service Pack 4 von Adobe Experience Manager Guides behobenen Fehler.

Erfahren Sie mehr [Upgrade-Anweisungen für Version 4.6.0 Service Pack 4](upgrade-instructions-4-6-0-sp4.md).

## Authoring

- Durch Ziehen und Ablegen eines Bildes in einem Thema in **Autoren** Ansicht wird der Bildverweis beschädigt, was zu Datenverlust führt. (25769)
- Durch Ziehen und Ablegen einer `topicref` in einer Zuordnung in der **Autoren** Ansicht wird der beabsichtigte Vorgang nicht ausgeführt und die `topicref` neben der gezogenen `topicref` wird entfernt. (19460)
- Wenn JCR-Sitzungsverbindungen beim Aktualisieren oder Erstellen von Themen nicht geschlossen werden, führt dies zu Speicherlecks und Service-Ausfallzeiten. (26282)

## Publishing

- Die native PDF-Veröffentlichung wird auf unbestimmte Zeit fortgesetzt, wenn der DITA-Inhalt über einen Weblink verfügt, ohne dass der Umfang wie `external` vorhanden ist. (26434)
- Beim Erstellen einer neuen Baseline mit einer großen Anzahl von Kennzeichnungen schlägt das Kennzeichnungsladeprogramm fehl und verhindert, dass die Kennzeichnungen abgerufen werden. (16232)
- Die Veröffentlichung nativer PDFs und AEM-Sites verzögert sich und wird in die Warteschlange gestellt, wenn Fehler im Inhalt auftreten. (26516)

## Bekannte Probleme

Adobe hat das folgende bekannte Problem für diese Version erkannt:

- Die native PDF-Veröffentlichung unter Windows tritt auf, wenn der DITA-Inhalt einen externen Link enthält, der das `scope`-Attribut nicht enthält.
