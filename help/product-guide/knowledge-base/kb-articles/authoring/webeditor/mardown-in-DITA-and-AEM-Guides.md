---
title: Markdown in DITA AEM Guides verwenden
description: Migrieren und Verwenden von Markdown in DITA AEM Guides
source-git-commit: dfda0ec4fe7301182299f6ab46d2772629ab6df7
workflow-type: tm+mt
source-wordcount: '256'
ht-degree: 0%

---

# Markdown in AEM Guides verwenden

## Verfügbare Optionen

Es gibt 2 Optionen für die Verwendung von Markdown-Dateien in AEM Guides :

- Option 1: Importieren Sie vorhandenes Markdown in AEM Guides und verwenden Sie es direkt in der DTM-Map zum Veröffentlichen

- Option 2 : Vorhandene Markdown-Dateien in DITA konvertieren

Hier werden die einzelnen Optionen beschrieben:

### Option 1: Importieren Sie vorhandenes Markdown in AEM Guides und verwenden Sie es direkt in der DTM-Map zum Veröffentlichen

Es bietet einfachere Einrichtung und schnellere Implementierung. Die eingeschränkte Nutzung von AEM Guides-Funktionen wie die Wiederverwendbarkeit von Inhalten jedoch.

Der Benutzer muss das Attribut `format="markdown" ` oder `format="mdita"` hinzufügen, damit die Publishing-Engines den Dateityp verstehen und entsprechend veröffentlichen können.

Beispieldatei : [Markdown-Ditamap](https://acrobat.adobe.com/id/urn:aaid:sc:AP:da31137e-be84-44fb-8974-d038eeff0283)

![Screenshot für Referenz](../../assets/authoring/markdown_map.png)


#### Ausgabe von Publish zu PDF und Web

AEM Guides bietet sowohl die Option Web (HTML5/AEM Site) als auch PDF (Native-PDF/DITA-OT), um die DTM-App mit Markdown-Inhalten zu veröffentlichen.

### Option 2: Markdown in DITA-Format konvertieren

Vollständige Nutzung der AEM Guides-Funktionen, die Wiederverwendbarkeit von Inhalten, Übersetzung von bedingten Verarbeitungsvorgängen, Grundlinie usw. Es wären jedoch im Voraus Bemühungen erforderlich, um das Format `.md` in das Format `.dita` zu konvertieren.

Markdown in DITA kann mit externen Tools wie Adobe FrameMaker und DITA-OT konvertiert werden.


Informationen zu Adobe FrameMaker finden Sie unter: [Markdown importieren](https://www.adobe.com/in/products/framemaker/features.html#import-markdown)

Für DITA-OT siehe: [Markdown als Eingabe](https://www.dita-ot.org/dev/topics/markdown-input.html)

Beispieldatei, die mit Adobe FrameMaker konvertiert wurde: [Markdown in DITA-Beispiel](https://acrobat.adobe.com/id/urn:aaid:sc:AP:874881f3-ba43-410c-abc6-2df899536d79)

#### Ausgabe von Publish zu PDF und Web

Sobald Markdown-Dateien in DITA konvertiert wurden, kann der Benutzer die Ausgabe nahtlos in allen in AEM Guides verfügbaren Formaten veröffentlichen.

Verfügbare Formate in AEM Guides: [Ausgabeformate](../../../../user-guide/generate-output-understand-presets.md)
