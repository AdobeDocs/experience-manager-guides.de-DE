---
title: Versionshinweise | Behobene Probleme in Adobe Experience Manager Guides, Version 2024.06.0
description: Erfahren Sie mehr über die Fehlerkorrekturen in der Version 2024.06.0 von Adobe Experience Manager Guides as a Cloud Service.
exl-id: 608e5b2c-72af-4498-9b63-935e698231d4
source-git-commit: d525775afeeb89754762ff514126b1c3a3307b3f
workflow-type: tm+mt
source-wordcount: '784'
ht-degree: 3%

---

# Behobene Probleme in Version 2024.06.0

Dieser Artikel behandelt die Fehler, die in verschiedenen Bereichen der Version 2024.06.0 von Adobe Experience Manager Guides as a Cloud Service behoben wurden.

Weitere Informationen zu den neuen Funktionen und Verbesserungen finden Sie unter [Neue Funktionen in Version 2024.06.0](whats-new-2024-06-0.md).

Erfahren Sie mehr über die [Upgrade-Anweisungen für die Version 2024.06.0](upgrade-instructions-2024-06-0.md).

## Authoring

- Beim Kopieren und Einfügen von Themen mit einer Größe von mehr als 15 KB tritt ein unerwarteter Fehler auf. (17171)
- Die Funktion zum Ändern des Dokumentstatus im Bedienfeld **Dateieigenschaften** funktioniert nicht ordnungsgemäß und ändert sich in den Status *Entwurf* . (17088)
- Wenn Sie die Einstellungen des XML-Editors mit einem benutzerdefinierten Ordnerprofil ändern, wird `ui_config.json` mit einer falschen Datei aktualisiert. (17011)
- Im Bereich **Repository** behält die Suche **Filter** den Wert des Felds **Ausgecheckt von** nicht bei, wenn das Dialogfeld **Erweiterter Filter** erneut geöffnet wird. (16935)
- Verknüpfte Bilder aus den Themen werden nach der Versionserstellung nicht in der Grundlinie angezeigt. (16931)
- In wiederverwendbaren Inhaltsbereichen werden Elemente nicht aufgelistet, wenn die **Benutzereinstellungen** so eingestellt sind, dass Dateien mit **Dateiname** angezeigt werden. (16896)
- Unterelemente innerhalb des Tabellentitelelements werden im Modus **Vorschau** von Experience Manager Guides nicht dargestellt. (16691)
- Die Ausführung des Postprozessskripts schlägt aufgrund der Ausnahme **FileNotFoundException** fehl. (16517)
- Vimeo-Videos unterstützen keine Vollbildfunktionalität in Experience Manager Guides. (1596)
- Das Einfügen langer vorformatierter Textzeilen in Elemente vom Typ `<pre>` oder `<codeblock>` führt zu abgeschnittenem Text. (15859)
- Das Löschen von Inhalten erfolgt aufgrund doppelter GUIDs, wenn Vorlagen über Code installiert, aber nicht verarbeitet werden. (15858)
- Experience Manager Guides hält im Modus **Vorschau** nicht das Attribut **Verarbeitungsrolle** ein. (15787)
- Der Editor löscht gelegentlich zusätzlichen Text, der über den ausgewählten Bereich hinausgeht.  (15708)
- Es ist nicht möglich, große Tabellen aus Word-Dokumenten oder HTML in den Web-Editor zu kopieren und einzufügen. (15369)
- Die Funktion **Kopieren** schlägt bei leeren Ordnern in Experience Manager Guides as a Cloud Service fehl. (15353)
- Fehlende APIs oder Ereignisse zum Erfassen von Attributen, die zu einem Element hinzugefügt oder ein neues Element eingefügt werden. (15351)
- Es ist nicht möglich, im Web Editor das Tag `<data>` innerhalb des Tags `<ol>` hinzuzufügen. (15161)
- Wenn Unified Shell aktiviert ist, wird im Dialogfeld **Verwaltung der Versionsbeschriftung** fälschlicherweise **Hauptinhalt** für Versionen ohne Beschriftungen angezeigt. (15039)
- Große Dateien werden im Web Editor langsam geladen, mit einer Verzögerung von einigen Sekunden. (14958)
- Wenn Sie die Taste **Enter** in einer Tabellenzelle innerhalb des Textes drücken, wird der Absatz nicht wie erwartet geteilt. (14251)
- Die Experience Manager-DITA-Anleitung kann die Funktion **Speichern** nach Verwendung der Funktion zum automatischen Einzug nicht Trigger werden. (16482)
- Prüfungsthemen werden nicht in der richtigen Reihenfolge angezeigt. (16319)
- In der Ansicht **Autor** tritt ein Problem beim Kopieren und Einfügen bei der Verwendung von geschützten Leerzeichen auf und führt zu einem Überlauf von Text. (15541)

- Beim Hinzufügen von `<conref>` zu einer anderen DITA-Zuordnung in `<othermeta>` -Element innerhalb von `<topicmeta>` wird die Zuordnungs-ID ebenfalls an die ID des Elements angehängt. (15226)
- Der `<conref>` kann nicht über das Bedienfeld **Attribute** aktualisiert werden, wenn Änderungen vorgenommen werden. (15209)
- Bei der Auswahl eines Bildes in einer Tabellenzelle wird die gesamte Zelle ausgewählt. (15188)

## Veröffentlichung


- Bei der Zuordnung von Zuordnungen zu Zuordnungen werden nicht alle übergeordneten Zuordnungen in den Einstellungen des Veröffentlichungskontexts für einen Link mit dem Wert `peer @scope` angezeigt. (16700)
- Beim Hinzufügen neuer oder Entfernen vorhandener Attribute werden die alten Attribute in den **Bedingungsvorgaben** beibehalten. (15890)
- Der RTL-Sprachinhalt wird in der Ausgabe der nativen PDF-Veröffentlichung nicht korrekt verarbeitet. (15709)
- Die erste PDF wird nicht versioniert, wenn eine native PDF-Ausgabe generiert wird. (10305)
- In nativer PDF werden verschachtelte DITA-Themen im Inhaltsverzeichnis (Inhaltsverzeichnis) falsch angezeigt. (16742)
- Miniaturansichten, die von Dynamic Media für Videodateien generiert wurden, bleiben in der veröffentlichten Ausgabe nicht erhalten. (15656)
- Die Generierung der Ausgabe schlägt bei der nativen PDF-Veröffentlichung auf einem ARM64-Prozessor fehl. (16968)

## Verwaltung

- Beim Bearbeiten einer bestehenden Grundlinie und Auswählen einer bestimmten Version werden Anwendungsfehler Trigger. (14451)

## Übersetzung

- Bei Übersetzungsprojekten werden mit der Experience Manager Guides-Version vom Oktober 2023 keine neuen Sprachaufträge zu Adobe Experience Manager 6.5 SP18 hinzugefügt. (15398)

## Cloud Service

- Die Navigation der Adobe Experience Manager-Tools reagiert nicht. (17118)
- Die Build Transform-Phase in der Cloud Service-Implementierung schlägt mit Fehlern aus der DITA-Codebasis fehl. (14432)

## Berichte

- Die ungenaue **Themenliste** wird in der Experience Manager Guides-Benutzeroberfläche aufgrund nicht gepatchter Eigenschaften beim Kopieren von DITA-Assets gezählt, was sich auf die für eine DTIA-Zuordnung generierten Berichte auswirkt. (15529)
- Themen mit externen Verweisen mit *%20* in der URL zeigen fehlerhafte Dateiverweise an. (15347)


## Bekannte Probleme

Adobe hat die folgenden bekannten Probleme für die Version 2024.06.0 identifiziert:

- Die native PDF-Veröffentlichung schlägt fehl, wenn dem Thema Vimeo-Inhalte hinzugefügt werden.
- Die **Themeneigenschaften** werden nicht gemäß dem ausgewählten Format in den Metadatenfeldern eines Seitenlayouts angezeigt.
- `xrefs` kann in der Ansicht **Assets** nicht angeklickt werden, wenn Dynamic Media aktiviert ist.
