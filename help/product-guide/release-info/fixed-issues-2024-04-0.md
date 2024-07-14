---
title: Versionshinweise | Behobene Probleme in Adobe Experience Manager Guides, Version 2024.4.0
description: Erfahren Sie mehr über die Fehlerkorrekturen in der Version 2024.04.0 von Adobe Experience Manager Guides as a Cloud Service.
exl-id: 35351d71-7739-4ad3-a063-67adf64906bf
source-git-commit: 5d99274da8fdacbd255d426fa4913b5773ca45f8
workflow-type: tm+mt
source-wordcount: '578'
ht-degree: 3%

---

# Behobene Probleme in Version 2024.04.0

Dieser Artikel behandelt die Fehler, die in verschiedenen Bereichen der Version 2024.04.0 von Adobe Experience Manager Guides as a Cloud Service behoben wurden.

Weitere Informationen zu den neuen Funktionen und Verbesserungen finden Sie unter [Neue Funktionen in Version 2024.04.0](whats-new-2024-04-0.md).

Erfahren Sie mehr über die [Upgrade-Anweisungen für die Version 2024.04.0](upgrade-instructions-2024-04-0.md).

## Authoring

- Die Funktion **Kopieren** kann die leeren Ordner in Adobe Experience Manager as a Cloud Service nicht duplizieren. (15353)
- Der Web Editor kann keine PPTX-Dateien hochladen. (14837)
- Beim Suchen eines Textes im Web Editor kehrt der Cursor beim Drücken der Eingabetaste zum ersten Vorkommen des gesuchten Textes zurück. (14820)
- Das automatische Speichern verursacht mehrere Probleme, es positioniert den Cursor neu und erfordert manuelle Klicks im Dokument. (14253)
- Die Suchergebnisse werden deaktiviert, nachdem eine Datei geöffnet wurde, die über globale **Suchen und Ersetzen** gefunden wurde. (12142)
- In der Quellansicht wird gelegentlich `</conbody>` an falschen Stellen eingefügt. (11305)
- Im XML-Editor kann die QuickInfo-Funktion das Source-Feld nicht aktualisieren. (15847)
- Die Funktion **UUID-Link freigeben** funktioniert nicht für die Bilder in Adobe Experience Manager. (15598)
- Überschneidende Textprobleme treten in den Tags `<reltable>` und `<fig>` auf. (15238)
- Flackernde Probleme treten im Bereich **Attribute** auf. (15237)
- Beim Löschen eines Zeichens oder Worts im Inhalt springt der Cursor zwischen den Blockelementen. (15224)
- Der Bereich **Attribute** wird nicht in der Source-Ansicht des Web Editors angezeigt. (14387)
- Beim Bearbeiten am Ende eines Tags im Web Editor werden unerwünschte, geschützten Leerzeichen hinzugefügt. (11786)
- Der Inhalt wird beim Korrigieren der Rechtschreibfehler in DITA-Dateien gelöscht. (11610)


## Veröffentlichung

- AEM Erzeugung der Site-Ausgabe schlägt fehl, wenn die Option **Orphan-Site löschen** aktiviert ist. (15896)
- Die Bearbeitungsfunktion funktioniert nicht, wenn Dateien zur Map Collection hinzugefügt werden. (15813)
- In der JSON-Ausgabe werden Metadaten aus der DITA-Zuordnung oder Themen nicht in die JSON-Ausgabedateien übertragen. (15713)
- Die native PDF-Veröffentlichung schlägt beim Umbenennen der Vorgabe fehl. (15662)
- Die Eigenschaft **sourcePath** ist in der Ausgabe der veröffentlichten AEM nicht korrekt. (15502)
- Die Auswahl und Anpassung der Sprachvariablen funktioniert in der Nativen PDF-Ausgabevorgabe nicht ordnungsgemäß. (15399)
- Die native PDF-Erstellung schlägt fehl, wenn eine Vorlage mit einem großen Stylesheet oder Layout verwendet wird. (15344)
- Der Inhalt wird in der veröffentlichten Ausgabe nicht ordnungsgemäß gerendert, wenn `<conref>` mit einem absoluten Pfad verwendet wird.
- Die Verkürzung der AEM Sites-URL funktioniert aufgrund von Konflikten zwischen `fmdita rewriter` und `ResourceResolver` nicht. (14793)
- Die Attribute **processing-role=&quot;resource-only&quot;**, **search=&quot;no&quot;** und **chunk=&quot;to-content&quot;** erscheinen in der AEM Sites-Ausgabe nicht bzw. nicht. (14442)
- Wenn ein Ordner mit 2k-Maps im Ordnerpfad innerhalb eines Ordnerprofils festgelegt ist, schlagen die auf die Ausgabevorgabe angewendeten Änderungen fehl.(14852)

## Verwaltung

- Nicht geschlossene **Ressourcen-Resolver** führen zu einer Erhöhung der Sitzungsanzahl und zu PathNotFoundException-Fehlern nach der Experience Manager Guides as a Cloud Service-Version vom Oktober 2023. (15604)
- Das Feature Flag **fmdita.useapproval** funktioniert nicht erwartungsgemäß. (15310)
- Das Erstellen einer Grundlinie mithilfe der Java-API funktioniert mit der Experience Manager Guides as a Cloud Service-Version vom Juni 2023 nicht. (14787)
- Die `/bin/fmdita/import` -API bleibt in ausstehender Anfrage unbegrenzt erhalten, wenn das Hochladen von Assets 500 MB überschreitet. (14743)

## Überprüfung

- Das Löschen von Überprüfungsknoten beeinträchtigt die Möglichkeit, Kommentare in Adobe Experience Manager Guides zu öffnen und anzuzeigen. (15366)
- Im Web Editor wird das Überprüfungsbedienfeld langsam geladen. (14680)

## Übersetzung

- **Accept Translation** kann die Übersetzung temporärer Dateien nicht abschließen. (14665)
