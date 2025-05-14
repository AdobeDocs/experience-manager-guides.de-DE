---
title: Versionshinweise zu | Neue Funktionen in Adobe Experience Manager Guides Version 2025.04.0
description: Erfahren Sie mehr über die neuen und erweiterten Funktionen der Version 2025.04.0 von Adobe Experience Manager Guides
role: Leader
exl-id: 5d28119b-641f-402b-833c-6f7554e7c273
source-git-commit: f4ed3c8b70c47beb1f97c6703ade4d4f49fa814e
workflow-type: tm+mt
source-wordcount: '569'
ht-degree: 2%

---

# Neue Funktionen in der Version 2025.04.0 (April 2025)

Dieser Artikel behandelt die neuen und erweiterten Funktionen, die mit der Version 2025.04.0 von Adobe Experience Manager Guides as a Cloud Service eingeführt wurden.

Eine Liste der in dieser Version behobenen Probleme finden Sie im Artikel [Behobene Probleme in Version 2025.04.0](fixed-issues-2025-04-0.md).

Erfahren Sie mehr [Upgrade-Anweisungen für die Version 2025.04.0](../release-info/upgrade-instructions-2025-04-0.md).

## Attribut &#39;Format&#39; für Referenz-Links hinzugefügt

Adobe Experience Manager Guides fügt jetzt ein **format**-Attribut für Referenz-Links im Editor hinzu. Dieses Attribut wird in der Ansicht **Source angezeigt** gibt den Dateityp deutlich an, z. B.:

- Für Dateien mit der Erweiterung **.pdf** wird das Format auf **pdf** festgelegt
- Für Dateien mit der Erweiterung **.** wird das Format auf &quot;**&quot;**
- Für Dateien mit den Dateien **.** oder **.** wird das Format auf **dita**

Darüber hinaus ist das Format von Dateien mit der **&#x200B;**.xml **ebenfalls auf dita** festgelegt. Bei Dateien ohne Erweiterung bleibt das Format leer. Darüber hinaus wird für alle Referenz-Links mit dem Bereich **extern** das Format auf **html** festgelegt, unabhängig von der Dateierweiterung in den Referenz-Links.


## Präzise Kommunikation für große Dateien im Editor

Experience Manager Guides informiert jetzt darüber, dass eine Datei als große Datei klassifiziert ist und bestimmte Funktionen wie Rückgängig, Wiederholen, der Gliederungsbereich und die unsaubere Markierung möglicherweise nicht wie erwartet funktionieren. Oben in der Benutzeroberfläche wird eine Warnmeldung für große Dateien angezeigt, wie im folgenden Ausschnitt dargestellt. Sie gibt die Anzahl der Elemente basierend auf dem Parameter **largeFileTagCount** in der Datei **uiconfig.**&quot; an.

Darüber hinaus wird die Anzahl der Tags in der unteren Leiste angezeigt, wobei eine QuickInfo angezeigt wird, wenn Sie den Mauszeiger darüber bewegen. Die Auswahl der Registerkarte **Weitere Informationen** enthält detaillierte Informationen zum Umgang mit großen Dateien. Dieser Warnhinweis ist nur für DITA-Dateien verfügbar und in allen Ansichten sichtbar: Author, Source und Layout.

Weitere Informationen finden Sie unter [Umgang mit großen Dateien im Editor](../user-guide/web-editor-other-features.md#handling-large-files-in-the-editor).

![](assets/add-toast-tag-count.png){width="800" align="left"}

## Exportierte Baseline enthält jetzt den Dokumentstatus

Die Funktion „Baseline exportieren“ enthält jetzt **Dokumentstatus** sowie wichtige Details wie Titel, Dateiname, Dateityp und Versionsnummer in der Baseline-Momentaufnahme. Diese Verbesserung verbessert das Baseline-Management, indem sie einen umfassenderen Überblick über die Baseline bietet.

Weitere Informationen finden Sie unter [Baselines in der Map-Konsole erstellen und verwalten](../user-guide/web-editor-baseline.md#manage-baselines).

## Verbessertes Sucherlebnis für das Bedienfeld „Wiederverwendbarer Inhalt“

Experience Manager Guides bietet ein verbessertes Sucherlebnis im Bedienfeld „Wiederverwendbarer Inhalt“. Mit diesem Update werden bei der Suche nach einem Keyword jetzt alle Dateien gescannt, die als wiederverwendbarer Inhalt hinzugefügt wurden, und nicht nur die offenen, um sicherzustellen, dass Sie die genaue Position des Keywords auf allen Vorkommen finden, unabhängig davon, ob die Container geöffnet oder reduziert sind. Wenn Sie die Suchleiste löschen, wird außerdem der Originalzustand aller Container beibehalten, was eine effizientere und benutzerfreundlichere Suchfunktion bietet.

Weitere Informationen finden Sie unter [Wiederverwendbare Inhalte](../user-guide/web-editor-features.md#reusable-content).


## Java-Versionsaktualisierung für Microservice-Container

Bei Cloud-Umgebungen, die für Microservices aktiviert sind, werden wir auf Java 21 umstellen, um sicherzustellen, dass die vorhandenen DITA-OT- und nativen PDF-Generierungsprozesse unbeeinflusst bleiben. Der vorhandene Workflow von DITA-OT 3 funktioniert weiterhin nahtlos mit Java 21.  Darüber hinaus ist DITA-OT 4 voll funktionsfähig, sodass Anwender PDFs mit DITA-OT und nativem PDF generieren sowie Ausgaben für native AEM-Sites und andere Formate erstellen können.
