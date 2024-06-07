---
title: Versionshinweise | Fehlerkorrektur - Adobe Experience Manager-Handbücher, Version 2024.06.0 - jetzt verfügbar
description: Erfahren Sie mehr über die Fehlerbehebungen in der Version 2024.06.0 von Adobe Experience Manager Guides as a Cloud Service.
source-git-commit: dff625a841ea9fc758de83b1d830ddffa15646cd
workflow-type: tm+mt
source-wordcount: '784'
ht-degree: 3%

---


# Behobene Probleme in Version 2024.06.0

Dieser Artikel behandelt die Fehler, die in verschiedenen Bereichen der Version 2024.06.0 von Adobe Experience Manager Guides as a Cloud Service behoben wurden.

Weitere Informationen zu den neuen Funktionen und Verbesserungen finden Sie unter [Neue Funktionen in Version 2024.06.0](whats-new-2024-06-0.md).

Informationen zu [Upgrade-Anweisungen für die Version 2024.06.0](upgrade-instructions-2024-06-0.md).

## Authoring

- Beim Kopieren und Einfügen von Themen mit einer Größe von mehr als 15 KB tritt ein unerwarteter Fehler auf. (17171)
- Die Funktion zum Ändern des Dokumentstatus über die  **Dateieigenschaften** nicht ordnungsgemäß funktioniert und Änderungen an der *Entwurf* state. (17088)
- Wenn Sie die Einstellungen des XML-Editors mit einem benutzerdefinierten Ordnerprofil ändern, wird die `ui_config.json` wird mit einer falschen Datei aktualisiert. (17011)
- Im **Repository** -Bedienfeld, **Filter** Die Suche behält nicht den Wert von **Ausgecheckt von** beim erneuten Öffnen des Felds **Erweiterter Filter** Dialogfeld. (16935)
- Verknüpfte Bilder aus den Themen werden nach der Versionserstellung nicht in der Grundlinie angezeigt. (16931)
- Wiederverwendbare Inhaltsbedienfelder listen keine Elemente auf, wenn die **Benutzereinstellungen** werden festgelegt, um Dateien anzuzeigen, indem **Dateiname**. (16896)
- Unterelemente innerhalb des Tabellentitelelements werden im **Vorschau** -Modus von Experience Manager-Guides. (16691)
- Die Ausführung des Postprozessskripts schlägt aufgrund von **FileNotFoundException** Ausnahmefehler. (16517)
- Vimeo-Videos unterstützen die Vollbildfunktion in Experience Manager-Handbüchern nicht. (1596)
- Fügen Sie lange vorformatierte Textzeilen in `<pre>` oder `<codeblock>` -Elemente zu abgeschnittenem Text führen. (15859)
- Das Löschen von Inhalten erfolgt aufgrund doppelter GUIDs, wenn Vorlagen über Code installiert, aber nicht verarbeitet werden. (15858)
- Experience Manager-Guides können nicht dem **Verarbeitungsrolle** -Attribut in **Vorschau** -Modus. (15787)
- Der Editor löscht gelegentlich zusätzlichen Text, der über den ausgewählten Bereich hinausgeht.  (15708)
- Es ist nicht möglich, große Tabellen aus Word-Dokumenten oder HTML in den Web-Editor zu kopieren und einzufügen. (15369)
- Die **Kopieren** schlägt bei leeren Ordnern in den as a Cloud Service Experience Manager-Handbüchern fehl. (15353)
- Fehlende APIs oder Ereignisse zum Erfassen von Attributen, die zu einem Element hinzugefügt oder ein neues Element eingefügt werden. (15351)
- Hinzufügen nicht möglich `<data>` Tag in `<ol>` -Tag im Web-Editor. (15161)
- Wenn Unified Shell aktiviert ist, wird die **Versionsbeschriftung** Dialogfeld falsch angezeigt **Hauptinhalt** für Versionen ohne Beschriftungen. (15039)
- Große Dateien werden im Web Editor langsam geladen, mit einer Verzögerung von einigen Sekunden. (14958)
- Drücken Sie die **Eingabe** -Taste in einer Tabellenzelle innerhalb des Textes den Absatz nicht wie erwartet aufteilt. (14251)
- Der Experience Manager-DITA-Guide kann die **Speichern** nach Verwendung der Funktion für den automatischen Einzug. (16482)
- Prüfungsthemen werden nicht in der richtigen Reihenfolge angezeigt. (16319)
- Im **Autor** -Ansicht ein Problem beim Kopieren und Einfügen bei der Verwendung von geschützten Leerzeichen auftritt und zu einem Überlauf des Textes führt. (15541)

- In `<othermeta>` -Element in `<topicmeta>`beim Hinzufügen einer `<conref>`an eine andere DITA-Zuordnung angehängt wird, wird auch die Zuordnungs-ID zusammen mit der ID des Elements angehängt. (15226)
- Die `<conref>` kann nicht aktualisiert werden über **Attribute** beim Vornehmen von Änderungen. (15209)
- Bei der Auswahl eines Bildes in einer Tabellenzelle wird die gesamte Zelle ausgewählt. (15188)

## Veröffentlichung


- Die Crossmap-Verknüpfung zeigt nicht alle übergeordneten Maps in den Veröffentlichungskontexteinstellungen für einen Link mit der `peer @scope`. (16700)
- Beim Hinzufügen neuer oder Entfernen vorhandener Attribute werden die alten Attribute im **Bedingungsvorgaben**. (15890)
- Der RTL-Sprachinhalt wird in der Ausgabe der nativen PDF-Veröffentlichung nicht korrekt verarbeitet. (15709)
- Die erste PDF wird nicht versioniert, wenn eine native PDF-Ausgabe generiert wird. (10305)
- In nativer PDF werden verschachtelte DITA-Themen im Inhaltsverzeichnis (Inhaltsverzeichnis) falsch angezeigt. (16742)
- Miniaturansichten, die von Dynamic Media für Videodateien generiert wurden, bleiben in der veröffentlichten Ausgabe nicht erhalten. (15656)
- Die Generierung der Ausgabe schlägt bei der nativen PDF-Veröffentlichung auf einem ARM64-Prozessor fehl. (16968)

## Verwaltung

- Beim Bearbeiten einer bestehenden Grundlinie und Auswählen einer bestimmten Version werden Anwendungsfehler Trigger. (14451)

## Übersetzung

- Bei Übersetzungsprojekten wird Adobe Experience Manager 6.5 SP18 mit der Experience Manager Guides-Version vom Oktober 2023 nicht um neue Sprachaufträge erweitert. (15398)

## Cloud Service

- Die Navigation der Adobe Experience Manager-Tools reagiert nicht. (17118)
- Die Build Transform-Phase in der Cloud Service-Implementierung schlägt mit Fehlern aus der DITA-Codebasis fehl. (14432)

## Berichte

- Die Ungenauigkeit **Themenliste** Zählungen in der Benutzeroberfläche von Experience Manager Guides aufgrund von nicht gepatchten Eigenschaften beim Kopieren von DITA-Assets wirken sich auf die für eine DTIA-Zuordnung generierten Berichte aus. (15529)
- Themen mit externen Verweisen mit *%20* in der URL werden fehlerhafte Dateiverweise angezeigt. (15347)


## Bekannte Probleme

Adobe hat die folgenden bekannten Probleme für die Version 2024.06.0 identifiziert:

- Die native PDF-Veröffentlichung schlägt fehl, wenn dem Thema Vimeo-Inhalte hinzugefügt werden.
- Die **Themeneigenschaften** werden nicht gemäß dem ausgewählten Format in den Metadatenfeldern eines Seitenlayouts angezeigt.
- `xrefs` nicht angeklickt werden können im **Assets** anzeigen, wenn Dynamic Media aktiviert ist.
