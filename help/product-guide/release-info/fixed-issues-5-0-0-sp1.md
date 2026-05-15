---
title: Versionshinweise | Behobene Probleme in Adobe Experience Manager Guides 5.0.0 Service Pack 1
description: Erfahren Sie mehr über die Fehlerbehebungen in Version 5.0.0 Service Pack 1 von Adobe Experience Manager Guides
role: Leader
exl-id: 1d0bc3d0-aedf-4f67-b6f7-2208facdee96
TQID: https://experienceleague.adobe.com/0qxye7ZUWt1iixHthjjTNJgtlOQX-C30jGi5zQlRJfA
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2:
  - id: a3bd6397-2eb2-4908-a61c-226e26855dca
  - id: ab01a588-7dea-43f2-a699-0b3f128465d6
role_v2:
  - id: f8a45b24-4be7-4f1b-909b-60d06b483a20
topic_v2:
  - id: a004cc84-67b9-4a33-a3a7-8ec7273ef4dc
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 288
ht-degree: 2%

---

# Es wurden Probleme in Version 5.0.0 Service Pack 1 (Juni 2025) behoben


Dieser Artikel behandelt die in verschiedenen Bereichen von Version 5.0.0 Service Pack 1 von Adobe Experience Manager Guides behobenen Fehler.

Erfahren Sie mehr über [Upgrade-Anweisungen für die Version 5.0.0 Service Pack 1](upgrade-instructions-5-0-0-sp1.md).

## Authoring

- Wenn Inhalte in ein `codeblock` eingefügt werden oder Leerzeichen im `codeblock` hinzugefügt werden und die Ansicht gewechselt wird, gehen die Leerzeichen verloren. (GUIDES-29347)
- Wenn ein XML-Kommentar innerhalb eines Elements in der Ansicht **Source** hinzugefügt wird, gehen die führenden und nachfolgenden Leerzeichen um den Kommentar verloren, wenn die Ansichten gewechselt werden. (HANDBÜCHER - 28188)

## Asset-Management

- Beim Öffnen eines Themas in der **Autoren**-Ansicht nach einer Browser-Aktualisierung werden zuvor angewendete Tags im Bedienfeld **Dateieigenschaften** nicht beibehalten, und das Hinzufügen neuer Tags überschreibt die vorhandenen, insbesondere wenn eine große Anzahl von Tags zur Auswahl verfügbar ist. (GUIDES-29078)
- Beim Generieren eines Metadatenberichts für eine DITA-Zuordnung, die eine große Anzahl von Assets enthält, reagiert die Schaltfläche **Verwalten** nicht mehr oder zeigt eine verzögerte Antwort an. (GUIDES-29778)

## Übersetzung

- Beim Senden von Assets zur Übersetzung aus Experience Manager Guides werden die Assets nicht zum Übersetzungsauftrag hinzugefügt, wodurch die Schaltfläche **Starten** nicht angezeigt wird und Sie den Übersetzungsauftrag nicht initiieren können. (GUIDES-28237)

## Publishing

- Beim Ändern der Einstellungen einer Ausgabevorgabe innerhalb des Ordnerprofils und Auswählen von **Vorgabenänderungen anwenden** werden die Änderungen nicht an die Ausgabevorgaben übertragen, die in der DITA-Zuordnung vorhanden sind. (GUIDES-26694)

## Überprüfung

- Beim Versuch, Prüfungsaufgaben über den AEM-Workflow zu erstellen, schlägt der Versuch beständig fehl, da der Prüfungsknoten nicht erstellt wird. (GUIDES-28214)
