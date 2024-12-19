---
title: Verwenden von Markdown in DITA AEM Guides
description: Migrieren und Markdown in DITA AEM Guides verwenden
author: Pulkit Nagpal(punagpal)
exl-id: a94c0129-df40-4b61-ac60-679b2ffe7e86
source-git-commit: f971be4be9e2d32618616727cd9c682941dd3fb2
workflow-type: tm+mt
source-wordcount: '256'
ht-degree: 0%

---

# Verwenden von Markdown in AEM Guides

## Verfügbare Optionen

Es gibt zwei Optionen zur Verwendung von Markdown-Dateien in AEM Guides :

- Option 1 : Importieren Sie einen vorhandenen Markdown in AEM Guides und verwenden Sie ihn direkt in Ditamap, um ihn zu veröffentlichen

- Option 2 : Konvertieren vorhandener Markdown-Dateien in DITA

Lassen Sie uns nun über die einzelnen Optionen sprechen:

### Option 1: Importieren Sie einen bestehenden Markdown in AEM Guides und verwenden Sie ihn direkt in Ditamap, um ihn zu veröffentlichen

Die Einrichtung ist einfacher und die Implementierung schneller. Eingeschränkte Funktionsnutzung von AEM Guides-Funktionen wie die Wiederverwendbarkeit von Inhalten.

Der Benutzer muss das Attribut `format="markdown" ` oder `format="mdita"` hinzufügen, damit die Publishing-Engines den Dateityp verstehen, und das Attribut entsprechend veröffentlichen.

Beispieldatei : [Markdown-](https://acrobat.adobe.com/id/urn:aaid:sc:AP:da31137e-be84-44fb-8974-d038eeff0283)

![Screenshot als Referenz](../../assets/authoring/markdown_map.png)


#### Publish zu PDF und Web-Ausgabe

AEM Guides bietet sowohl Web (HTML5/AEM-Site) als auch PDF (Native-PDF/DITA-OT) die Möglichkeit, Ditamap mit Markdown-Inhalten zu veröffentlichen

### Option 2 : Konvertieren des Markdown in das DITA-Format

Vollständige Nutzung der AEM Guides-Funktionen, wie Wiederverwendbarkeit von Inhalten, bedingte Verarbeitung, Übersetzung, Grundlinie usw. Es wären jedoch Vorarbeiten erforderlich, um `.md` in `.dita` Format zu konvertieren.

Markdown in DITA kann mithilfe von externen Tools wie Adobe FrameMaker und DITA-OT konvertiert werden.


Für Adobe FrameMaker siehe : [Import-Markdown](https://www.adobe.com/in/products/framemaker/features.html#import-markdown)

Für DITA-OT siehe : [Markdown als Eingabe](https://www.dita-ot.org/dev/topics/markdown-input.html)

Beispieldatei, die mit Adobe FrameMaker konvertiert wurde : [Beispiel für Markdown in DITA](https://acrobat.adobe.com/id/urn:aaid:sc:AP:874881f3-ba43-410c-abc6-2df899536d79)

#### Publish zu PDF und Web-Ausgabe

Sobald Markdown-Dateien in DITA konvertiert wurden, können Benutzerinnen und Benutzer die Ausgabe nahtlos in allen in AEM Guides verfügbaren Formaten veröffentlichen.

Verfügbare Formate in AEM Guides : [Ausgabeformate](../../../../user-guide/generate-output-understand-presets.md)
