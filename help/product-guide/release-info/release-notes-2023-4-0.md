---
title: Versionshinweise zu | Adobe Experience Manager Guides as a Cloud Service, Version April 2023
description: Version April 2023 von Adobe Experience Manager Guides as a Cloud Service
exl-id: fa339eab-d3d0-4763-adbf-6411e39aa213
feature: Release Notes
role: Leader
source-git-commit: 6d8c01f20f7b59fed92c404561b647d9ebecb050
workflow-type: tm+mt
source-wordcount: '598'
ht-degree: 0%

---

# Version April 2023 von Adobe Experience Manager Guides as a Cloud Service

Diese Versionshinweise enthalten die Upgrade-Anweisungen, die Kompatibilitätsmatrix und behobene Probleme in Version April 2023 von Adobe Experience Manager Guides (später als *AEM Guides as a Cloud Service* bezeichnet).

Weitere Informationen zu den neuen Funktionen und Verbesserungen finden Sie unter [Neue Funktionen in der Version April 2023 von AEM Guides as a Cloud Service](whats-new-2023-4-0.md).

## Upgrade auf die Version April 2023

Führen Sie ein Upgrade Ihres aktuellen AEM Guides as a Cloud Service-Setups durch, indem Sie die folgenden Schritte ausführen:

1. Checken Sie den Git-Code der Cloud Service aus und wechseln Sie zu der Verzweigung, die in der Cloud Service-Pipeline konfiguriert ist und der Umgebung entspricht, die Sie aktualisieren möchten.
2. Aktualisieren Sie `<dox.version>` Eigenschaft in `/dox/dox.installer/pom.xml` Datei Ihres Cloud Service-Git-Codes auf 2023.4.249.
3. Übertragen Sie die Änderungen und führen Sie die Cloud Service-Pipeline aus, um auf die Version April 2023 von AEM Guides as a Cloud Service zu aktualisieren.

## Schritte zum Indizieren des vorhandenen Inhalts (nur bei Versionen vor der AEM Guides as a Cloud Service-Version September)

Führen Sie die folgenden Schritte aus, um den vorhandenen Inhalt zu indizieren und den neuen Text „Suchen und Ersetzen“ auf Zuordnungsebene zu verwenden:

* Ausführen einer POST-Anfrage an den Server (mit korrekter Authentifizierung) - `http://<server:port>/bin/guides/map-find/indexing`.
(Optional) Sie können bestimmte Pfade der Karten übergeben, um sie zu indizieren. Standardmäßig werden alle Karten indiziert || Beispiel : `https://<Server:port>/bin/guides/map-find/indexing?paths=<map_path_in_repository>`)

* Die API gibt eine jobId zurück. Um den Status des Auftrags zu überprüfen, können Sie eine GET-Anfrage mit Auftrags-ID an denselben Endpunkt senden - `http://<server:port>/bin/guides/map-find/indexing?jobId={jobId}`
(Beispiel: http://&lt;_localhost:8080_>/bin/guides/map-find/indexing?jobId=2022/9/15/7/27/7dfa1271-981e-4617-b5a4-c18379f11c42_678)

* Sobald der Vorgang abgeschlossen ist, antwortet die obige GET-Anfrage mit Erfolg und gibt an, ob Zuordnungen fehlgeschlagen sind. Die erfolgreich indizierten Zuordnungen können aus den Serverprotokollen bestätigt werden.

## Kompatibilitätsmatrix

In diesem Abschnitt finden Sie die Kompatibilitätsmatrix für die Softwareanwendungen, die von AEM Guides as a Cloud Service Version April 2023 unterstützt werden.

### FrameMaker und FrameMaker Publishing Server

| AEM Guides as a Cloud Service-Version | FMPS | FrameMaker |
| --- | --- | --- |
| 2 023,04,0 | Nicht kompatibel | 2022 oder höher |
| | | |


### Sauerstoffanschluss

| AEM Guides as a Cloud Service-Version | Fenster des Sauerstoffanschlusses | Oxygen Connector Mac | In Oxygen Windows bearbeiten | In Oxygen Mac bearbeiten |
| --- | --- | --- | --- | --- |
| 2 023,04,0 | 2.9-uuid-2 | 2.9-uuid-2 | 2,3 | 2,3 |
|  |  |  |  |



## Behobene Probleme

Die in verschiedenen Bereichen behobenen Fehler sind unten aufgeführt:

* Native PDF | Die Veröffentlichung von Inhalten mit einer Ausgabeklasse mit Brackets() führt zu einem Veröffentlichungsstopp. 11596)
* Problem tritt beim Verschieben (Ziehen und Ablegen) anstelle eines vorhandenen Listenelements auf, bei dem Änderungen nachverfolgen aktiviert ist. 11570)
* Problem beim Verschieben (Ziehen und Ablegen) als neues Listenelement mit aktiviertem „Änderungen verfolgen“. 11569)
* Ein- oder Ausrücken von Listenelementen funktioniert nicht wie erwartet, wenn Änderungen nachverfolgt werden. 11568)
* Beim Hinzufügen von Inhalten zu einer Zeile mit aktivierter Option „Änderungen verfolgen“ und beim Deaktivieren der Option „Änderungen verfolgen“ wird die Option nicht deaktiviert. 11567)
* Schwierigkeiten beim Ziehen und Ablegen eines Listenelements, Text wird anstelle des Listenelements verschoben. 11566)
* Abgeschlossene Überprüfung wird nicht im schreibgeschützten Modus geöffnet. 11387)
* Das Problem tritt bei der AEM-Site-Suche auf (funktioniert nicht über zwei- bis dreistufige Knoten hinaus). 11352)
* Beim Authoring im grün angezeigten Element (Änderungen verfolgen) wird der neue Inhalt als Tracking-Änderung angezeigt, obwohl die Track-Änderung deaktiviert ist. (7021)

### Bekanntes Problem mit Problemumgehung

Adobe hat das folgende bekannte Problem in AEM Guides as a Cloud Service Version April 2023 festgestellt.

* Native PDF | Die alten Metadaten werden erst ausgefüllt, wenn die Ausgabevorgabe explizit geöffnet wird.
