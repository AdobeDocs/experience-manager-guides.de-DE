---
title: Versionshinweise | Adobe Experience Manager Guides as a Cloud Service, Version Oktober 2022
description: Oktober-Version von Adobe Experience Manager Guides as a Cloud Service
exl-id: 38638080-625c-49c3-9e54-56cc23831546
feature: Release Notes
role: Leader
source-git-commit: 6d8c01f20f7b59fed92c404561b647d9ebecb050
workflow-type: tm+mt
source-wordcount: '491'
ht-degree: 1%

---

# Oktober-Version von Adobe Experience Manager Guides as a Cloud Service

## Aktualisierung auf die Oktober-Version

Führen Sie die folgenden Schritte aus, um das aktuelle Adobe Experience Manager Guides-as a Cloud Service-Setup (später als *AEM Guides as a Cloud Service* bezeichnet) zu aktualisieren:
1. Sehen Sie sich den Git-Code des Cloud Service an und wechseln Sie zu der Verzweigung, die in der Cloud Service-Pipeline entsprechend der Umgebung konfiguriert ist, die Sie aktualisieren möchten.
1. Aktualisieren Sie die Eigenschaft `<dox.version>` in der Datei `/dox/dox.installer/pom.xml` Ihres Cloud Service-Git-Codes auf 2022.10.183.
1. Übertragen Sie die Änderungen und führen Sie die Cloud Service-Pipeline aus, um auf die Oktober-Version von AEM Guides as a Cloud Service zu aktualisieren.

## Kompatibilitätsmatrix

In diesem Abschnitt wird die Kompatibilitätsmatrix für die Softwareanwendungen aufgelistet, die von der AEM Guides as a Cloud Service-Version vom Oktober 2022 unterstützt werden.

### FrameMaker und FrameMaker Publishing Server

| FMPS | FrameMaker |
| --- | --- |
| Nicht kompatibel | Aktualisierung 4 und höher für 2020 |
| | |

*Die in AEM erstellten Grundlinien und Bedingungen werden in FMPS-Versionen ab 2020.2 unterstützt.

### Sauerstoffanschluss

| AEM Guides as a Cloud-Version | Sauerstoff Connector Windows | Sauerstoff Connector Mac | In Oxygen Windows bearbeiten | In Oxygen Mac bearbeiten |
| --- | --- | --- | --- | --- |
| 2022.10.0 | 2,7,13 | 2,7,13 | 2,3 | 2,3 |
|  |  |  |  |


## Neue Funktionen und Verbesserungen

AEM Guides as a Cloud Service bietet in der Oktober-Version Verbesserungen und neue Funktionen:


### Bereich &quot;Schnellgenerierung&quot;

Jetzt stellt AEM Guides das Bedienfeld **Quick Generate** bereit, mit dem Sie die Ausgabe für Vorgaben, die für Ihre DITA-Zuordnung erstellt wurden, schnell generieren und anzeigen können.

Symbol ![Schnellgenerierung](assets/quick-generate-icon.png)

Im Bedienfeld **Quick Generate** können Sie die Liste aller für Ihre DITA-Zuordnung erstellten Ausgabevorgaben anzeigen.

![Bedienfeld &quot;Schnellgenerierung&quot;](assets/quick-generate-panel.png)

Wählen Sie eine oder mehrere Vorgaben aus und generieren Sie schnell die Ausgabe. Sie können auch die für die Vorgaben generierte Ausgabe schnell anzeigen. Bei der Generierung der Ausgabe wird eine Erfolgsmeldung angezeigt. Wenn die Generierung der Ausgabe fehlschlägt, wird eine Fehlermeldung angezeigt. Sie können auch das Fehlerprotokoll anzeigen, um die Details des Fehlers anzuzeigen, der im Generierungsprozess aufgetreten ist.


## Behobene Probleme

Die in verschiedenen Bereichen behobenen Fehler sind unten aufgeführt:

* Native PDF | Beim Entfernen von Themen, die nur Ressourcen betreffen, aus der PDF-Ausgabe tritt ein Fehler auf. 10554)
* Native PDF | Leere Keyrefs werden in der PDF-Ausgabe angezeigt. (10553)
* Native PDF | `navtitle` für `topichead` wird nicht berücksichtigt. (10509)
* Native PDF | Unterstützung für Ad64 JDK-Versionen erforderlich. (10465)
* Native PDF | Es ist nicht möglich, Themen aus der Vorderseite aus dem Inhaltsverzeichnis auszublenden. (10355)
* Native PDF | Wenn Sie die Seitenzahl im Kapitel-Layout nach dem Zufallsprinzip neu starten, beginnt die Nummerierung am Ende des vorherigen Kapitels. (10154)
* Chrome-Browser | Beim Ziehen und Ablegen eines Elements aus der Benutzeroberfläche wird der Bildschirm leer. Beispielsweise beim Ziehen einer Bedingung aus dem Bedienfeld &quot;Bedingungen&quot;. (10524)
* Knoteneigenschaften werden nach dem Kopieren/Einfügen-Vorgang eines Assets entfernt. (10053)
* Beim Klicken auf **Schließen** wurden Benutzer zu Assets umgeleitet - das Erlebnis wurde korrigiert, um Benutzer zur AEM Homepage zu leiten. 9654
