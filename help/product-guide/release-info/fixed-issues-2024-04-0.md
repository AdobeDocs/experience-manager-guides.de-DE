---
title: Versionshinweise | Fehlerkorrektur - Adobe Experience Manager-Handbücher, Version 2024.4.0 - jetzt verfügbar
description: Erfahren Sie mehr über die Fehlerbehebungen in der Version 2024.04.0 von Adobe Experience Manager Guides as a Cloud Service.
source-git-commit: 4c7421391922d276ef82515fb4b1cbdc2397e4ce
workflow-type: tm+mt
source-wordcount: '578'
ht-degree: 0%

---


# Behobene Probleme in Version 2024.04.0

Dieser Artikel behandelt die Fehler, die in verschiedenen Bereichen der Version 2024.04.0 von Adobe Experience Manager Guides as a Cloud Service behoben wurden.

Weitere Informationen zu den neuen Funktionen und Verbesserungen finden Sie unter [Neue Funktionen in Version 2024.04.0](whats-new-2024-04-0.md).

Informationen zu [Upgrade-Anweisungen für die Version 2024.04.0](upgrade-instructions-2024-04-0.md).

## Authoring

- Die **Kopieren** -Funktion die leeren Ordner in Adobe Experience Manager as a Cloud Service nicht duplizieren kann. (15353)
- Der Web Editor kann keine PPTX-Dateien hochladen. (14837)
- Beim Suchen eines Textes im Web Editor kehrt der Cursor beim Drücken der Eingabetaste zum ersten Vorkommen des gesuchten Textes zurück. (14820)
- Das automatische Speichern verursacht mehrere Probleme, es positioniert den Cursor neu und erfordert manuelle Klicks im Dokument. (14253)
- Die Suchergebnisse werden deaktiviert, nachdem eine Datei geöffnet wurde, die über globale **Suchen und Ersetzen**. (12142)
- In der Quellansicht `</conbody>` wird gelegentlich an falschen Stellen eingefügt. (11305)
- Im XML-Editor kann die QuickInfo-Funktion das Quellfeld nicht aktualisieren. (15847)
- Die **UUID-Link freigeben** -Funktion für die Bilder in Adobe Experience Manager nicht funktioniert. (15598)
- Überschneidende Textprobleme treten in `<reltable>` und `<fig>` Tags. (15238)
- Flackernde Probleme treten im **Attribute** Bedienfeld. (15237)
- Beim Löschen eines Zeichens oder Worts im Inhalt springt der Cursor zwischen den Blockelementen. (15224)
- Die **Attribute** nicht in der Quellansicht des Web-Editors angezeigt. (14387)
- Beim Bearbeiten am Ende eines Tags im Web Editor werden unerwünschte, geschützten Leerzeichen hinzugefügt. (11786)
- Der Inhalt wird beim Korrigieren der Rechtschreibfehler in DITA-Dateien gelöscht. (11610)


## Veröffentlichung

- Die Generierung AEM Site-Ausgabe schlägt fehl, wenn **Orphan-Site löschen** aktiviert ist. (15896)
- Die Bearbeitungsfunktion funktioniert nicht, wenn Dateien zur Map Collection hinzugefügt werden. (15813)
- In der JSON-Ausgabe werden Metadaten aus der DITA-Zuordnung oder Themen nicht in die JSON-Ausgabedateien übertragen. (15713)
- Die native PDF-Veröffentlichung schlägt beim Umbenennen der Vorgabe fehl. (15662)
- Die **sourcePath** -Eigenschaft in der veröffentlichten AEM Site-Ausgabe falsch ist. (15502)
- Die Auswahl und Anpassung der Sprachvariablen funktioniert in der Nativen PDF-Ausgabevorgabe nicht ordnungsgemäß. (15399)
- Die native PDF-Erstellung schlägt fehl, wenn eine Vorlage mit einem großen Stylesheet oder Layout verwendet wird. (15344)
- Der Inhalt wird in der veröffentlichten Ausgabe nicht ordnungsgemäß gerendert, wenn `<conref>` wird mit einem absoluten Pfad verwendet.
- Die Verkürzung der AEM Sites-URL funktioniert aufgrund von Konflikten zwischen der `fmdita rewriter` und `ResourceResolver`. (14793)
- Die **processing-role=&quot;resource-only&quot;**, **search=&quot;no&quot;**, und **chunk=&quot;to-content&quot;** -Attribute werden in der AEM Sites-Ausgabe getrennt angezeigt. (14442)
- Wenn ein Ordner mit 2k-Maps im Ordnerpfad innerhalb eines Ordnerprofils festgelegt ist, schlagen die auf die Ausgabevorgabe angewendeten Änderungen fehl.(14852)

## Verwaltung

- Nicht geschlossen **Resource Resolver** verursacht steigende Sitzungsanzahl und PathNotFoundException-Fehler nach der as a Cloud Service Version der Experience Manager-Handbücher vom Oktober 2023. (15604)
- Feature Flag **fmdita.useapproval** funktioniert nicht wie erwartet. (15310)
- Das Erstellen einer Grundlinie mithilfe der Java-API funktioniert nicht mit der as a Cloud Service Version der Experience Manager-Handbücher vom Juni 2023. (14787)
- Die `/bin/fmdita/import` Die API bleibt in der ausstehenden Anfrage auf unbestimmte Zeit hängen, wenn das Hochladen von Assets 500 MB überschreitet. (14743)

## Überprüfung

- Das Löschen von Überprüfungsknoten beeinträchtigt die Möglichkeit, Kommentare in Adobe Experience Manager-Handbüchern zu öffnen und anzuzeigen. (15366)
- Im Web Editor wird das Überprüfungsbedienfeld langsam geladen. (14680)

## Übersetzung

- **Übersetzung akzeptieren** schlägt fehl, um die Übersetzung temporärer Dateien abzuschließen. (14665)


