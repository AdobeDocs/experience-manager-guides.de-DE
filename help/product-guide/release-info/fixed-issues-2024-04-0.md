---
title: Versionshinweise | Behobene Probleme in Adobe Experience Manager Guides Version 2024.4.0
description: Erfahren Sie mehr über die Fehlerbehebungen in der Version 2024.04.0 von Adobe Experience Manager Guides as a Cloud Service.
exl-id: 35351d71-7739-4ad3-a063-67adf64906bf
TQID: https://experienceleague.adobe.com/cHKuFCElWbjxik0EHgoTrtlq2t3I62LQ5zUArzBoMqk
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2:
  - id: a3bd6397-2eb2-4908-a61c-226e26855dca
  - id: ab01a588-7dea-43f2-a699-0b3f128465d6
subfeature_v2:
  - id: ad602516-aca3-4247-9ae8-f393d958efa9
  - id: d6596f3f-92a7-43ec-b444-237db6adad05
  - id: f89f75b0-cf2e-4e96-aec8-fe8c39cbd0ef
  - id: fd6cc9e1-e5e5-494e-b7b1-a32f2d6cd7c9
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
topic_v2:
  - id: a004cc84-67b9-4a33-a3a7-8ec7273ef4dc
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 577
ht-degree: 8%

---

# Es wurden Probleme in der Version 2024.04.0 behoben

Dieser Artikel behandelt die in verschiedenen Bereichen der Version 2024.04.0 von Adobe Experience Manager Guides as a Cloud Service behobenen Fehler.

Weitere Informationen zu den neuen Funktionen und Verbesserungen finden Sie unter [Neue Funktionen in Version 2024.04.0](whats-new-2024-04-0.md).

Erfahren Sie mehr [Upgrade-Anweisungen für die Version 2024.04.0](upgrade-instructions-2024-04-0.md).

## Authoring

- Die **Kopieren**-Funktion kann die leeren Ordner in Adobe Experience Manager as a Cloud Service nicht duplizieren. (15353)
- Der Web-Editor kann keine PPTX-Dateien hochladen. (14837)
- Beim Suchen eines Textes im Web-Editor kehrt der Cursor beim Drücken der Eingabetaste zum ersten Vorkommen des gesuchten Textes zurück. (14820)
- Das automatische Speichern verursacht mehrere Probleme, positioniert den Cursor neu und erfordert manuelle Klicks im Dokument. (14253)
- Die Suchergebnisse werden nach dem Öffnen einer Datei, die über global (Suchen **Ersetzen) gefunden wurde,**. (12142)
- In der Quellansicht wird `</conbody>` gelegentlich an falschen Stellen eingefügt. (11305)
- Im XML-Editor kann das Source-Feld mit der QuickInfo-Funktion nicht aktualisiert werden. (15847)
- Die Funktion **UUID-Link freigeben** funktioniert nicht für die Bilder in Adobe Experience Manager. (15598)
- Überschneidende Textprobleme treten bei `<reltable>` und `<fig>` Tags auf. (15238)
- Flimmernde Probleme treten im Bedienfeld &quot;**&quot;**. (15237)
- Beim Löschen eines Zeichens oder Worts innerhalb des Inhalts springt der Cursor zwischen den Blockelementen. (15224)
- Das **Attribute**-Bedienfeld wird in der Source-Ansicht des Web-Editors nicht angezeigt. (14387)
- Unerwünschte, nicht umbrechende Leerzeichen werden beim Bearbeiten am Ende eines Tags im Web-Editor hinzugefügt. (11786)
- Der Inhalt wird beim Korrigieren der Rechtschreibfehler in DITA-Dateien gelöscht. (11610)


## Publishing

- Die Generierung der AEM-Site-Ausgabe schlägt fehl, wenn **Option „Verwaiste Site löschen** aktiviert ist. (15896)
- Die Bearbeitungsfunktion funktioniert nicht, wenn Dateien zur Zuordnungssammlung hinzugefügt werden. (15813)
- In der JSON-Ausgabe können Metadaten aus DITA-Zuordnungen oder Themen nicht an die JSON-Ausgabedateien übertragen werden. (15713)
- Die native Veröffentlichung von PDF schlägt beim Umbenennen der Vorgabe fehl. (15662)
- Die **sourcePath**-Eigenschaft ist in der veröffentlichten AEM-Site-Ausgabe falsch. (15502)
- Die Auswahl und Anpassung von Sprachvariablen funktioniert in der nativen PDF-Ausgabevorgabe nicht ordnungsgemäß. (15399)
- Die native PDF-Generierung schlägt bei der Verwendung einer Vorlage mit einem großen Stylesheet oder Layout fehl. (15344)
- Inhalte werden in der veröffentlichten Ausgabe nicht richtig gerendert, wenn `<conref>` mit einem absoluten Pfad verwendet wird.
- Die AEM Sites-URL-Verkürzung funktioniert aufgrund von Konflikten zwischen dem `fmdita rewriter` und dem `ResourceResolver` nicht. (14793)
- Die **processing-role=„resource-only“**, **search=„no“** und **chunk=„to-content“** werden unabhängig in der AEM Sites-Ausgabe angezeigt. (14442)
- Wenn ein Ordner, der 2K-Zuordnungen enthält, im Ordnerpfad innerhalb eines Ordnerprofils festgelegt ist, schlagen die auf die Ausgabevorgabe angewendeten Änderungen fehl.(14852)

## Verwaltung

- Nicht geschlossene **Resource Resolver** verursachen nach der Experience Manager Guides as a Cloud Service-Version vom Oktober 2023 zunehmende Fehler in der Sitzungsanzahl und in der PathNotFoundException. (15604)
- Das Feature Flag **fmdita.useapproval** funktioniert nicht erwartungsgemäß. (15310)
- Das Erstellen einer Grundlinie mit der Java-API funktioniert nicht mit der Experience Manager Guides as a Cloud Service-Version vom Juni 2023. (14787)
- Die `/bin/fmdita/import`-API bleibt unbegrenzt in der ausstehenden Anfrage hängen, wenn das Hochladen von Assets 500 MB überschreitet. (14743)

## Überprüfung

- Durch das Löschen von Prüfungsknoten wird die Möglichkeit zum Öffnen und Anzeigen von Kommentaren in Adobe Experience Manager Guides beeinträchtigt. (15366)
- Im Web-Editor wird das Überprüfungsfeld langsam geladen. (14680)

## Übersetzung

- **Übersetzung akzeptieren** kann die Übersetzung von temporären Dateien nicht abschließen. (14665)
