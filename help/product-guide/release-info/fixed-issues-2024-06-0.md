---
title: Versionshinweise | Behobene Probleme in Adobe Experience Manager Guides Version 2024.06.0
description: Erfahren Sie mehr über die Fehlerbehebungen in der Version 2024.06.0 von Adobe Experience Manager Guides as a Cloud Service.
exl-id: 608e5b2c-72af-4498-9b63-935e698231d4
TQID: https://experienceleague.adobe.com/PWXSeB-BhL9Gc104XoVpfqdWqywq7T6bphx8im92C4c
product_v2: id: fae5e35a-80c9-4b94-9352-1a060a6aab1did: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2: id: a01bfd36-4ab8-4bf8-9dc0-5b45b890552eid: a3bd6397-2eb2-4908-a61c-226e26855dcaid: ab01a588-7dea-43f2-a699-0b3f128465d6id: c6d09140-3c91-45d3-b7ed-b681af752f43id: d90290ec-3e61-4ebd-8649-bcafe0836803
subfeature_v2: id: ad602516-aca3-4247-9ae8-f393d958efa9id: d4f22c6d-7923-41e5-9da3-527ff8df4bc8id: d6596f3f-92a7-43ec-b444-237db6adad05id: f89f75b0-cf2e-4e96-aec8-fe8c39cbd0efid: fd6cc9e1-e5e5-494e-b7b1-a32f2d6cd7c9
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554
topic_v2: id: a004cc84-67b9-4a33-a3a7-8ec7273ef4dc
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 781
ht-degree: 8%

---

# Es wurden Probleme in der Version 2024.06.0 behoben

Dieser Artikel behandelt die in verschiedenen Bereichen der Version 2024.06.0 von Adobe Experience Manager Guides as a Cloud Service behobenen Fehler.

Weitere Informationen zu den neuen Funktionen und Verbesserungen finden Sie unter [Neue Funktionen in Version 2024.06.0](whats-new-2024-06-0.md).

Erfahren Sie mehr [Upgrade-Anweisungen für die Version 2024.06.0](upgrade-instructions-2024-06-0.md).

## Authoring

- Das Kopieren und Einfügen von Themen mit einer Größe von mehr als 15 KB schlägt mit einem unerwarteten Fehler fehl. (17171)
- Die Funktion zum Ändern des Dokumentstatus im Bedienfeld **Dateieigenschaften** funktioniert nicht ordnungsgemäß und ändert sich in den *Entwurf*. (17088)
- Beim Ändern der XML-Editor-Einstellungen mithilfe eines benutzerdefinierten Ordnerprofils wird der `ui_config.json` mit einer falschen Datei aktualisiert. (17011)
- Im Bedienfeld **Repository** behält die **Filter**-Suche beim erneuten Öffnen des Dialogfelds **Erweiterter Filter** den Wert **Ausgecheckt von** nicht bei. (16935)
- Verknüpfte Bilder aus den Themen werden nach der Erstellung der Version nicht in der Grundlinie angezeigt. (16931)
- Wiederverwendbare Inhaltsbedienfelder enthalten keine Elemente, wenn die **Benutzereinstellungen** so eingestellt sind, dass Dateien nach &quot;**&quot; angezeigt**. (16896)
- Unterelemente innerhalb des Tabellentitelelements können im **-Modus** Experience Manager Guides nicht gerendert werden. (16691)
- Die Ausführung des Nachbearbeitungs-Skripts schlägt aufgrund eines Ausnahmefehlers **FileNotFoundException** fehl. (16517)
- Vimeo-Videos unterstützen in Experience Manager Guides keine Vollbildfunktion. (15996)
- Das Einfügen langer vorformatierter Textsequenzen in `<pre>` oder `<codeblock>` führt zu abgeschnittenem Text. (15859)
- Das Löschen von Inhalten erfolgt aufgrund doppelter GUIDs, wenn Vorlagen über Code installiert werden, aber nicht verarbeitet werden. (15858)
- Experience Manager Guides erfüllt das Attribut **Verarbeitungsrolle** im Modus **Vorschau** nicht. (15787)
- Der Editor löscht gelegentlich zusätzlichen Text über den ausgewählten Bereich hinaus.  (15708)
- Es ist nicht möglich, große Tabellen aus Word-Dokumenten oder HTML zu kopieren und in den Web-Editor einzufügen. (15369)
- Die **Kopieren**-Funktion schlägt bei leeren Ordnern in Experience Manager Guides as a Cloud Service fehl. (15353)
- Fehlende APIs oder Ereignisse zur Erfassung des Hinzufügens eines Attributs zu einem Element oder zum Einfügen eines neuen Elements. (15351)
- Hinzufügen `<data>` Tags innerhalb `<ol>` Tags im Web-Editor nicht möglich. (15161)
- Wenn Unified Shell aktiviert ist, wird im Dialogfeld **Versionsbeschriftungsverwaltung** für Versionen ohne Beschriftung fälschlicherweise **Hauptinhalt** angezeigt. (15039)
- Große Dateien werden im Web-Editor mit einer Verzögerung von einigen Sekunden langsam geladen. (14958)
- Durch Drücken der **Eingabetaste** in einer Tabellenzelle innerhalb des Texts wird der Absatz nicht wie erwartet aufgeteilt. (14251)
- Das Experience Manager DITA-Handbuch kann die Funktion **Speichern** nach Verwendung der Funktion zum automatischen Einrücken nicht in Trigger bringen. (16482)
- Prüfungsthemen werden nicht in der richtigen Reihenfolge angezeigt. (16319)
- In der **Autoren** Ansicht tritt beim Verwenden von Leerzeichen ohne Unterbrechung ein Problem mit Kopieren und Einfügen auf, was zu einem Überlauf von Text führt. (15541)

- In `<othermeta>` Element in `<topicmeta>` wird beim Hinzufügen von `<conref>`zu einer anderen DITA-Zuordnung auch die Zuordnungs-ID zusammen mit der ID des Elements angehängt. (15226)
- Die `<conref>` kann nicht über das Bedienfeld **Attribute** aktualisiert werden, wenn Änderungen vorgenommen werden. (15209)
- Bei der Auswahl eines Bildes in einer Tabellenzelle wird die gesamte Zelle ausgewählt. (15188)

## Publishing


- Bei der Crossmap-Verknüpfung werden nicht alle übergeordneten Zuordnungen in den Einstellungen des Veröffentlichungskontexts für einen Link mit dem `peer @scope` angezeigt. (16700)
- Beim Hinzufügen neuer oder Entfernen vorhandener Attribute werden die alten Attribute in den &quot;**&quot;**. (15890)
- Der Inhalt der RTL-Sprache wird in der nativen PDF-Veröffentlichungsausgabe nicht korrekt verarbeitet. (15709)
- Die erste PDF wird nicht versioniert, wenn eine native PDF-Ausgabe generiert wird. (10305)
- In nativem PDF werden verschachtelte DITA-Themen im Inhaltsverzeichnis (TOC) falsch angezeigt. (16742)
- Miniaturansichten, die von Dynamic Media für Videodateien generiert werden, bleiben in der veröffentlichten Ausgabe nicht erhalten. (15656)
- Die Ausgabegenerierung schlägt für die native PDF-Veröffentlichung auf einem ARM64-Prozessor fehl. (16968)

## Verwaltung

- Bearbeiten einer bestehenden Baseline und Auswählen einer bestimmten Version Trigger-Anwendungsfehler. (14451)

## Übersetzung

- Übersetzungsprojekte können mit der Experience Manager Guides-Version vom Oktober 2023 keine neuen Sprachaufträge zu Adobe Experience Manager 6.5 SP18 hinzufügen. (15398)

## Cloud Service

- Die Adobe Experience Manager Tools-Navigation reagiert nicht. (17118)
- Die Build-Transformationsphase in der Cloud Services-Bereitstellung schlägt mit Fehlern aus der DITA-Code-Basis fehl. (14432)

## Berichte

- Die ungenaue **Themenliste** in der Experience Manager Guides-Benutzeroberfläche aufgrund nicht gepatchter Eigenschaften beim Kopieren von DITA-Assets wirkt sich auf die für eine DTIA-Zuordnung generierten Berichte aus. (15529)
- Themen mit externen Verweisen mit *%20* in der URL zeigen beschädigte Dateiverweise an. (15347)


## Bekannte Probleme

Adobe hat die folgenden bekannten Probleme in Version 2024.06.0 identifiziert:

- Die native Veröffentlichung von PDF schlägt fehl, wenn dem Thema Vimeo-Inhalte hinzugefügt werden.
- Die **Themeneigenschaften** werden nicht entsprechend dem ausgewählten Format in den Metadatenfeldern eines Seiten-Layouts angezeigt.
- `xrefs` sind in der Ansicht **Assets** nicht klickbar, wenn Dynamic Media aktiviert ist.
