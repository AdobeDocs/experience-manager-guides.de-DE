---
title: Versionshinweise | Behobene Probleme in Adobe Experience Manager Guides Version 2025.10.0
description: Erfahren Sie mehr über die Fehlerbehebungen in der Version 2025.10.0 von Adobe Experience Manager Guides as a Cloud Service.
exl-id: e9a97d74-5061-42b4-b9d3-6c8dc386e6fb
TQID: https://experienceleague.adobe.com/jaNCpM6p06stKTcuXlyMSaTgym-JWR9UP0RKFhkGFh0
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2:
  - id: a3bd6397-2eb2-4908-a61c-226e26855dca
  - id: ab01a588-7dea-43f2-a699-0b3f128465d6
subfeature_v2:
  - id: ad602516-aca3-4247-9ae8-f393d958efa9
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 743
ht-degree: 2%

---

# Es wurden Probleme in der Version 2025.10.0 behoben

Dieser Artikel behandelt die in verschiedenen Bereichen der Version 2025.10.0 von Adobe Experience Manager Guides as a Cloud Service behobenen Fehler.

Weitere Informationen zu den neuen Funktionen und Verbesserungen finden Sie unter [Neue Funktionen in Version 2025.10.0](whats-new-2025-10-0.md).

Erfahren Sie mehr [Upgrade-Anweisungen für die Version 2025.10.0](upgrade-instructions-2025-10-0.md).

## Authoring

- Wenn mehrere DITA-Zuordnungen oder -Themen geöffnet und eines der Themen geschlossen ist, wird die Schaltfläche **>>** , die alle offenen Registerkarten anzeigt, mit den verbleibenden offenen Registerkarten in der Registerkartenleiste überlagert. (GUIDES-31421)
- Wenn der **Genehmigungs** Workflow aktiviert ist, ist die Schaltfläche **Neue Version starten** in der Editor-Symbolleiste nicht sichtbar, wenn sowohl das linke Bedienfeld als auch das Bedienfeld Inhaltseigenschaften geöffnet sind. (GUIDES-29093)
- Wenn Snippet-Namen die Breite des Snippet-Bereichs überschreiten, werden sie falsch in die nächste Zeile eingeschlossen, was zu Überlappungen mit benachbarten Snippets führt und die Lesbarkeit beeinträchtigt. (GUIDES-22685)
- Wenn Sie dieselbe Referenz mehrmals zu einer DITA-Zuordnung hinzufügen, zeigt die **Map**-Ansicht den Titel nur für das letzte Vorkommen an, während die vorherigen die UUID der Referenz anzeigen. (GUIDES-9699)
- Die DITAVAL-Dateien bleiben bearbeitbar, auch wenn sie von einem anderen Benutzer gesperrt sind oder der Server **Bearbeitung deaktivieren, ohne die Datei zu sperren** aktiviert hat und die Datei im schreibgeschützten Modus geöffnet ist. (GUIDES-27754)
- Protokolle für fehlende Knoten werden aus internen Bereinigungsaufträgen generiert, die nicht erforderlich sind und fälschlicherweise als Fehler gekennzeichnet sind, was zu einer Überlastung der Protokolldateien führt. (GUIDES-31765)


## Publishing

- Beim Generieren von PDFs werden die Filterregeln in einer DITAVAL-Datei ignoriert, wenn ein Eigenschaftsname einen Punkt enthält. (GUIDES-33229)
- Die Salesforce-Veröffentlichung schlägt mit einem Anwendungsfehler fehl, wenn bereits ein Thema mit demselben Namen und derselben URL vorhanden ist. (HANDBÜCHER - 32390)
- Die Salesforce-Veröffentlichung zeigt in der Benutzeroberfläche den Status Erfolgreich an, auch wenn eine DITA-Zuordnung mit einem `topichead` die darin enthaltenen Themen nicht veröffentlichen kann. (GUIDES-32143)
- Für die HTML5-Ausgabevorgabe funktioniert die Suchfilterfunktion in AEM Assets nicht für die DITAVAL-Filterung, da die entsprechenden Dateien nicht angezeigt werden, wenn der DITAVAL-Filter ausgewählt ist. (GUIDES-28231)
- Wenn beim Generieren eines nativen PDF für eine DITA-Zuordnung mit mehreren Themen ein `fig` in einem `figgroup` zusammen mit einem `title` enthält, wird der `figgroup` fälschlicherweise als Kapiteltitel im Inhaltsverzeichnis gerendert. (GUIDES-23223)
- Beim Duplizieren von PDF-Vorlagen über die Benutzeroberfläche wird auch die UUID dupliziert, sodass Vorlagendateien gelöscht werden und PDF-Ausgaben falsch sind. (GUIDES-30456)
- Beim Generieren von nativem PDF für eine DITA-Zuordnung wird der Titel `example` Elements `h1` Überschriftenebene gerendert, was zu visueller Inkonsistenz und falscher Inhaltsverzeichnisstruktur führt. (GUIDES-19958)

## Übersetzung

- Beim Vergrößern des Bildschirms der Übersetzungs-Benutzeroberfläche bewegt sich die Schaltfläche **Zur Übersetzung senden** unter den Auslassungspunkten und wird aktiviert, auch ohne dass ein Asset ausgewählt wird. (GUIDES-33720)
- Bei der Auswahl von Dateien **Status** Nicht synchronisiert“ in der Übersetzungs-Benutzeroberfläche und eingeschränkter Bildschirmbreite aufgrund geöffneter linker und rechter Bedienfelder wird die Beschriftung **Zur Übersetzung senden** abgeschnitten. (GUIDES-33692)

## Überprüfung

- Wenn ein Reviewer eine Überprüfungsaufgabe abschließt oder der Initiator die Überprüfungsaufgabe aktualisiert, ohne Kommentare einzugeben, zeigt die gesendete Benachrichtigungs-E-Mail den letzten vorherigen Kommentar an. (GUIDES-33590)

## Bekannte Probleme

Adobe hat die folgenden bekannten Probleme in Version 2025.10.0 identifiziert:

- Beim Öffnen einer URL mit einem zuvor geöffneten DITA-Thema oder beim Aktualisieren eines geöffneten DITA-Themas kann das Thema nicht im Repository gefunden werden, obwohl die Einstellung **Dateien immer im Repository suchen** in den Benutzereinstellungen aktiviert ist. (GUIDES-35565)<br>**Problemumgehung**: Wählen Sie die Themenregisterkarte aus, um die Datei im Repository zu suchen.

- Beim Erstellen einer neuen Datei in der Autorenansicht mit mehreren bereits geöffneten Dateien kann der rechte Bereich nicht aktualisiert werden und zeigt falsche Daten an, wenn der Cursor auf einem Element-Tag in einer anderen Datei platziert wird. (GUIDES-35450)<br>**Problemumgehung**: Wechseln Sie die Registerkarten oder aktualisieren Sie die Seite, um das Problem zu beheben.

- Wenn Sie für ein neu geöffnetes Thema (das zunächst im Source-Modus geöffnet wird) von der Source-Ansicht zur Autorenansicht wechseln, wird der Themeninhalt leer. (GUIDES-35000)<br>**Problemumgehung**: Aktualisieren Sie die Seite oder öffnen Sie das Thema erneut, um das Problem zu beheben.

- Die Schaltfläche **Navigation aktualisieren** wird für DITA-Themendateien angezeigt, sollte jedoch nur für DITA-Karten, Buchkarten und Themenschemata verfügbar sein. (GUIDES-35452)
