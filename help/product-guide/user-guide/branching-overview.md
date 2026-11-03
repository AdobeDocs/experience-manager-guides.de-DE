---
title: Verzweigung in AEM Guides | Adobe Experience Manager Guides`
description: Erfahren Sie, wie Sie Verzweigungen einer DITA-Zuordnung in AEM Guides erstellen und verwalten, um paralleles Authoring, unabhängige Veröffentlichung und das Zusammenführen von Dokumentationsänderungen zu unterstützen.
TQID: https://experienceleague.adobe.com/pg9zeEg8m3NeDbN-j945SqPbaMX0GgBmuquAsQcrjOM
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
    internal-label: Experience Manager Guides
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
    internal-label: Experience Manager
feature_v2:
  - id: ab01a588-7dea-43f2-a699-0b3f128465d6
    internal-label: Authoring
  - id: ec4263d9-bf7c-44c7-b3f1-3e664861c8f2
    internal-label: Generative AI
subfeature_v2:
  - id: ad602516-aca3-4247-9ae8-f393d958efa9
    internal-label: Editor
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
topic_v2:
  - id: d095671a-1355-40aa-8b5f-06c33c68080b
    internal-label: Security
  - id: f5c2a4bb-71ca-4d7e-8efd-442250e6ba48
    internal-label: Content reuse
source-git-commit: 3f0d8e31537ade58a4eab5ddf73eb6d263d3dd96
workflow-type: tm+mt
source-wordcount: '747'
ht-degree: 0%
---
# Überblick

>[!NOTE]
>
> Die Verzweigungs- und Zusammenführungsfunktion wurde mit der Version 2026.11.0 von Experience Manager Guides as a Cloud Service eingeführt und ist standardmäßig deaktiviert. Wenden Sie sich an Ihr Customer Success-Team, um die Funktion für Ihre Umgebung zu aktivieren.

Mit Verzweigungen in Adobe Experience Manager Guides können Sie mehrere Verzweigungen außerhalb der **erstellen und verwalten** damit eine DITA-Zuordnung parallel an verschiedenen Dokumentationsversionen arbeiten kann. Jede Verzweigung ermöglicht es Autorinnen und Autoren, Inhaltsänderungen unabhängig zu verwalten, ohne den entsprechenden Inhalt in anderen Verzweigungen zu beeinflussen.

Mit Verzweigungen können mehrere Teams gleichzeitig an verschiedenen Versionen, Funktionen oder Fehlerbehebungen arbeiten, die mit derselben DITA-Zuordnung verknüpft sind. Sie können Änderungen aus einer Verzweigung mit der Standardverzweigung (`main`) zusammenführen, wenn die Aktualisierungen fertig sind.

## Funktionsweise von Verzweigungen

Sie können eine Verzweigung aus der **Haupt** oder einer vorhandenen Verzweigung einer DITA-Zuordnung erstellen. Nachdem Sie eine Verzweigung erstellt haben, können Sie zu ihr wechseln und mit der Bearbeitung der Karte und ihres Inhalts beginnen. Sie können auch Inhalte aus der ausgewählten Verzweigung veröffentlichen oder Änderungen in `main` zusammenführen, wenn sie bereit sind.

Nehmen wir zum Beispiel eine DITA-Zuordnung mit dem Namen `install-the-lift.ditamap`, die Installationsanweisungen für ein Produkt enthält. Ihr Dokumentations-Team kann zwei Verzweigungen dieser Zuordnung aus `main` erstellen:

- **Version 1:** Team A pflegt bestehende Installationsanweisungen und behandelt Fehlerbehebungen.
- **Version 2:** Team B entwickelt Installationsanweisungen für neue Funktionen.

Beide Teams können unabhängig voneinander an ihren jeweiligen Zuordnungsverzweigungen arbeiten, ohne die Änderungen der anderen zu beeinflussen.

>[!NOTE]
>
>Basierend auf einer DITA-Zuordnung wird eine Verzweigung erstellt. Sie können auch Themen hinzufügen und bearbeiten, die nicht von der Zuordnung innerhalb der ausgewählten Verzweigung referenziert werden. Weitere Informationen finden Sie unter [Themen außerhalb der aktuellen Karte öffnen oder bearbeiten](./create-manage-branch.md#open-or-edit-topics-outside-the-current-map-context).

Wenn Sie eine Verzweigung einer DITA-Zuordnung erstellen, kopiert Experience Manager Guides die referenzierten Themen der Zuordnung nicht automatisch in die neue Verzweigung. Unveränderte Themen werden aus dem Quellzweig oder dem Standardzweig (Main) gelesen. Ein Thema wird nur dann in die neue Verzweigung kopiert, wenn Sie es bearbeiten und in dieser Verzweigung speichern.

Beispielsweise verweist eine DITA-Zuordnung auf 100 Themen, und das Repository enthält 50 zusätzliche Themen, auf die die Zuordnung nicht verweist. Wenn Sie eine neue Verzweigung erstellen (Version 1.0), werden alle 100 referenzierten Themen automatisch Teil von Version 1.0, auch wenn keines von ihnen bearbeitet wird. Die 50 nicht referenzierten Themen werden nicht automatisch Teil der neuen Verzweigung. Wenn Sie 10 davon bearbeiten, werden nur diese 10 Teil von Version 1.0. Die verbleibenden 40 unveränderten Themen werden weiterhin von der Standardverzweigung (Hauptverzweigung) aus verwendet.

>[!NOTE]
>
> Die Themenversionierung funktioniert weiterhin mit Verzweigungen. Sie können Versionen von Themen innerhalb einer ausgewählten Verzweigung einer DITA-Zuordnung erstellen und verwalten. Jede Verzweigung verwaltet ihren eigenen Versionsverlauf, unabhängig von anderen Verzweigungen.

## Die wichtigsten Vorteile

Das Arbeiten mit einer Verzweigung in Experience Manager Guides bietet die folgenden Vorteile:

- **Isolierte Bearbeitung** Nehmen Sie Änderungen innerhalb einer ausgewählten Zuordnungsverzweigung vor, ohne den entsprechenden Inhalt in anderen Verzweigungen zu beeinflussen.
- **Paralleles Authoring** Ermöglichen Sie es mehreren Teams, gleichzeitig an verschiedenen Versionen, Funktionen oder Fehlerbehebungen in ihren jeweiligen Zuordnungszweigen zu arbeiten.
- **Unabhängige Veröffentlichung** Veröffentlichen Sie die Dokumentation aus einzelnen Kartenzweigen, ohne auf den Abschluss von Änderungen in anderen Zweigen zu warten.
- **Kontrolliertes Zusammenführen** Zusammenführen von Änderungen von einer Zuordnungsverzweigung in die Standardverzweigung (`main`) mit der Möglichkeit, Konflikte zu überprüfen und zu lösen.

## Verzweigung vs. Baselines

>[!NOTE]
>
> Grundlinien und Verzweigungen schließen sich gegenseitig aus. Wenn die Verzweigung aktiviert ist, ist die Grundlinie nicht mehr verfügbar. Vorhandene Baselines bleiben jedoch intakt und werden nicht gelöscht. Wenn die Verzweigung später deaktiviert wird, werden die vorhandenen Baselines wieder verfügbar und können verwendet werden.

Eine **Baseline** identifiziert eine bestimmte Kombination von Themenversionen für eine DITA-Zuordnung, sodass Sie mithilfe dieser ausgewählten Versionen eine Ausgabe generieren können.

Eine **Verzweigung** bietet eine separate Bearbeitungsumgebung für eine DITA-Zuordnung und deren Inhalt, sodass Autoren Änderungen vornehmen können, ohne andere Verzweigungen derselben Zuordnung zu beeinflussen.

| Baselines | Verzweigung |
|---|---|
| Auswahl bestimmter Versionen von Themen in einer DITA-Zuordnung. | Erstellen Sie separate Verzweigungen einer DITA-Zuordnung, um Änderungen unabhängig zu verwalten. |
| Wird verwendet, um bestimmte Kombinationen von Themenversionen zu veröffentlichen. | Wird verwendet, um verschiedene Versionen parallel zu entwickeln und zu veröffentlichen. |
| Geben Sie keine isolierten Bearbeitungskontexte an. | Unterstützt isoliertes Bearbeiten und Zusammenführen. |

## Künftige Funktionen

Die folgenden Funktionen werden derzeit nur im Standardzweig (`main`) unterstützt und sollen in zukünftigen Versionen von Experience Manager Guides auch in anderen Zweigen einer DITA-Zuordnung unterstützt werden:

- Suchen
- Suchen und Ersetzen
- Überprüfen von Workflows

