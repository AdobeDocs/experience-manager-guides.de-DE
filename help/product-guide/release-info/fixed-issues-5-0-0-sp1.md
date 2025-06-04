---
title: Versionshinweise zu | Es wurden Probleme in Adobe Experience Manager Guides 5.0.0 Service Pack 1 behoben
description: Erfahren Sie mehr über die Fehlerbehebungen in Version 5.0.0 Service Pack 1 von Adobe Experience Manager Guides
role: Leader
source-git-commit: 083a8e16b9d3cd6c3894d7eaa2fee489b1dc0bb8
workflow-type: tm+mt
source-wordcount: '293'
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
