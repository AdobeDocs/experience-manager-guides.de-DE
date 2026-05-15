---
title: Verwenden von Markdown in DITA AEM Guides
description: Migrieren und Markdown in DITA AEM Guides verwenden
author: Pulkit Nagpal(punagpal)
exl-id: a94c0129-df40-4b61-ac60-679b2ffe7e86
TQID: https://experienceleague.adobe.com/z41KjrBkAeDaH-iKXOFLH44qOQElziip1FqcRhnKaUI
product_v2: id: fae5e35a-80c9-4b94-9352-1a060a6aab1did: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2: id: a3bd6397-2eb2-4908-a61c-226e26855dcaid: ab01a588-7dea-43f2-a699-0b3f128465d6
subfeature_v2: id: ad602516-aca3-4247-9ae8-f393d958efa9
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 281
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


#### In PDF veröffentlichen und Web-Ausgabe

AEM Guides bietet sowohl Web (HTML5/AEM-Site) als auch PDF (Native-PDF/DITA-OT) die Möglichkeit, Ditamap mit Markdown-Inhalten zu veröffentlichen

### Option 2 : Konvertieren des Markdown in das DITA-Format

Vollständige Nutzung der AEM Guides-Funktionen, wie Wiederverwendbarkeit von Inhalten, bedingte Verarbeitung, Übersetzung, Grundlinie usw. Es wären jedoch Vorarbeiten erforderlich, um `.md` in `.dita` Format zu konvertieren.

Markdown in DITA kann mithilfe von externen Tools wie Adobe FrameMaker und DITA-OT konvertiert werden.


Für Adobe FrameMaker siehe : [Import-Markdown](https://www.adobe.com/in/products/framemaker/features.html#import-markdown)

Für DITA-OT siehe : [Markdown als Eingabe](https://www.dita-ot.org/dev/topics/markdown-input.html)

Beispieldatei, die mit Adobe FrameMaker konvertiert wurde : [Beispiel für Markdown in DITA](https://acrobat.adobe.com/id/urn:aaid:sc:AP:874881f3-ba43-410c-abc6-2df899536d79)

#### In PDF veröffentlichen und Web-Ausgabe

Sobald Markdown-Dateien in DITA konvertiert wurden, können Benutzerinnen und Benutzer die Ausgabe nahtlos in allen in AEM Guides verfügbaren Formaten veröffentlichen.

Verfügbare Formate in AEM Guides : [Ausgabeformate](../../../../user-guide/generate-output-understand-presets.md)
