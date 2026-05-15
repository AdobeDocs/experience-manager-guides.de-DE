---
title: Versionshinweise | Behobene Probleme in Adobe Experience Manager Guides Version 2025.08.0
description: Erfahren Sie mehr über die Fehlerbehebungen in der Version 2025.08.0 von Adobe Experience Manager Guides as a Cloud Service.
exl-id: 05fe0e2c-ec65-4aec-a543-9b9a75c82f2c
TQID: https://experienceleague.adobe.com/7J25vfpTwwPyT3-qNF6-LLbPra8EePs5XaKqkAjEk5I
product_v2: id: fae5e35a-80c9-4b94-9352-1a060a6aab1did: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2: id: a3bd6397-2eb2-4908-a61c-226e26855dcaid: ab01a588-7dea-43f2-a699-0b3f128465d6
subfeature_v2: id: ad602516-aca3-4247-9ae8-f393d958efa9
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 713
ht-degree: 7%

---

# Es wurden Probleme in der Version 2025.08.0 behoben

Dieser Artikel behandelt die in verschiedenen Bereichen der Version 2025.08.0 von Adobe Experience Manager Guides as a Cloud Service behobenen Fehler.

Weitere Informationen zu den neuen Funktionen und Verbesserungen finden Sie unter [Neue Funktionen in Version 2025.08.0](whats-new-2025-08-0.md).

Erfahren Sie mehr [Upgrade-Anweisungen für die Version 2025.08.0](upgrade-instructions-2025-08-0.md).

## Authoring

- **CSS**- und **Seitenlayout**-Dateien in nativen PDF-Vorlagen weisen ein inkonsistentes Dateisperrverhalten auf, sodass sie auch dann bearbeitet werden können, wenn die Dateien gesperrt sind. (GUIDES-26688)
- Wenn Sie die Seite aktualisieren, nachdem Sie dem linken Bedienfeld benutzerdefinierte Schaltflächen hinzugefügt haben, werden doppelte Registerkarten erstellt. (GUIDES-30899)
- Wenn XML-Inhalte mit eckigen Klammern (z. B. &lt;/ oder />) innerhalb eines `code block` Elements in einem Thema hinzugefügt werden, wird das Code-Blockelement in der endgültigen Ausgabe leer angezeigt. (GUIDES-31007)
- Die Werte der globalen Variablen `canCheckIn` und `canCheckOut` werden nicht korrekt festgelegt, wenn eine Datei über die Editor-Symbolleiste aus- und eingecheckt wird. (GUIDES-29890)
- Beim Öffnen einer DITA-Map mit aktivierter Unified Shell wird der Editor gelegentlich aktualisiert. (GUIDES-26919)
- Wenn eine DITA-Zuordnung in der Kartenansicht ausgewählt wird, wird die Auswahlanzahl zunächst falsch angezeigt, da die untergeordneten Knoten der Zuordnung nicht ausgewählt sind. Die korrekte Anzahl der Auswahlen und die Einbeziehung aller untergeordneten Knoten wird erst bei der nachfolgenden Auswahl angezeigt. (GUIDES-25663)
- Markdown-Dateien werden nicht abgerufen, wenn im Repository-Bereich mit dem Filter **DITA-Thema** gesucht wird. Außerdem funktionieren **Suchen und Ersetzen** nicht für Markdown-Dateien und zugehörige Inhalte. (GUIDES-27133)
- Das **Menü-Dropdown-Menü** der Editor-Symbolleiste kann nicht mit dem Erweiterungs-Framework angepasst werden. Daher können Sie im Dropdown-Menü „Menü“ keine vorhandenen Schaltflächen ausblenden oder anzeigen bzw. neue Schaltflächen hinzufügen. (GUIDES-28748)

## Asset-Management

- Das Kopieren eines Ordners mit einer großen Anzahl von Assets aus der Assets-Benutzeroberfläche führt zu einer API-Zeitüberschreitung. Der Vorgang wird weiterhin im Backend ausgeführt und nach einiger Zeit abgeschlossen, aber in der Benutzeroberfläche wird keine Erfolgs- oder Fehlermeldung bzw. keine Benachrichtigung angezeigt. (GUIDES-30900)
- Ein Kopieren/Einfügen-Vorgang, der für einen Ordner in der Assets-Benutzeroberfläche ausgeführt wird, schlägt aufgrund von Nachbearbeitungsfehlern fehl. (GUIDES-30840)
- Das Kopieren und Einfügen schlägt für Ordner mit ebenenübergreifenden Assets (Assets mit Unter-Assets) in der Assets-Benutzeroberfläche fehl. (28107)
- Ordner mit einer großen Anzahl von Assets werden nicht ordnungsgemäß in das Repository geladen. (GUIDES-32500)
- Ordner-Knotennamen werden im Editor fälschlicherweise anstelle von Ordnertiteln angezeigt. (GUIDES-32402)
- Beim Hochladen von Assets mit nicht unterstützten oder unzulässigen Zeichen in den Dateinamen tritt ein Fehler auf. (GUIDES-28845)

## Publishing

- In der nativen PDF-Ausgabe wird die Indexliste (LOI) in nicht alphabetischer Reihenfolge angezeigt und verschachtelte Indexbegriffe werden nicht richtig gruppiert, was die Navigation innerhalb des Index erschwert. (GUIDES-29090)
- Die **Seitenvorlage zuordnen** und **Themenseitenvorlage** Dropdown-Liste auf der Seite „Ausgabevorgabe für die AEM Sites-Komponentenzuordnung“ wird leer angezeigt, wenn der Zielpfad eine Variable mit einem Doppelpunkt enthält. (GUIDES-28119)
- Wenn eine DITA-Zuordnung verschiedene Arten von Themenverweisen wie Konzept, Referenz oder Aufgabe enthält und mithilfe des `chunk=to-content`-Attributs zusammengeführt wird, um eine Einzelseitenausgabe in AEM Sites mit der Komponentenzuordnung zu generieren, wird der Inhalt aufgrund von Veröffentlichungsfehlern nicht ordnungsgemäß veröffentlicht. (GUIDES-28118)

## Grundlinie

- Beim Kopieren einer DITA-Zuordnung über die Assets-Benutzeroberfläche wird auch die angehängte Baseline in die neue Zuordnung kopiert. (GUIDES-11227)

## Startseite

- Die Startseite wird leer, wenn eine der im Widget **Letzte Dateien** aufgelisteten Dateien auf einer Vorlage basiert, deren Quellvorlage keine Miniaturansicht enthält. (GUIDES-31506)

## Bekannte Probleme

Adobe hat die folgenden bekannten Probleme in Version 2025.08.0 identifiziert:

- Wenn eine im Editor geöffnete Datei umbenannt oder verschoben wird, wird durch den Wechsel zwischen den Modi (**Author**, **Preview** usw.) der Inhalt im Bearbeitungsbereich aktualisiert, der aktive Modus wird jedoch nicht unten rechts hervorgehoben. (GUIDES-32719) <br> **Problemumgehung**: Aktualisieren Sie die Seite, um das Problem zu beheben.
- Bilder mit Leerzeichen in Dateinamen werden nicht in der Ausgabe angezeigt, wenn sie mit bedingten Attributen gekennzeichnet werden. (GUIDES-33858)
- Im Bedienfeld **Inhaltseigenschaften** wird das Feld Attribute automatisch geschlossen, wenn Sie versuchen, einen Verweis im Dialogfeld **Link aktualisieren** zu aktualisieren, wodurch verhindert wird, dass der Link aktualisiert wird. (GUIDES-17767)
