---
title: REST-APIs für Konversions-Workflow
description: Erfahren Sie mehr über die REST-APIs für den Konversions-Workflow
exl-id: f091782e-ab54-4db4-9018-9bcbff9da7b2
feature: Rest API Conversion Workflow
role: Developer
level: Experienced
source-git-commit: bda1af0da134fce53b4a4118278fa1ef2fe34c69
workflow-type: tm+mt
source-wordcount: '391'
ht-degree: 3%

---

# REST-APIs für Konversions-Workflow {#id175UB30E05Z}

Mit den folgenden REST-APIs können Sie Word-, HTML- und InDesign-Dokumente in das DITA-Format konvertieren.

## Konvertieren von Word-Dokumenten

Eine GET, die Word-Dokumente in DITA-Format konvertiert.

**Anforderungs-URL**:
http://*&lt;aem-guides-server\>*: *&lt;port-number\>*/bin/fmdita/conversion

**Parameter**:

| Name | Typ | Erforderlich | Beschreibung |
|----|----|--------|-----------|
| ``operation`` | Zeichenfolge | Ja | Name des aufgerufenen Vorgangs. Der Wert dieses Parameters ist ``word2dita``. <br> **Hinweis:** Beim Wert wird nicht zwischen Groß- und Kleinschreibung unterschieden. |
| `inputFile` | Zeichenfolge | Ja | Absoluter Pfad der Word-Quelldateien in AEM Repository. |
| `destPath` | Zeichenfolge | Ja | Absoluter Pfad des Zielorts, an dem die konvertierten DITA-Dateien gespeichert werden. |
| `createRev` | Boolesch | Ja | Geben Sie an, ob eine Revision der Dateien \( `true`\) am angegebenen Ziel erstellt wird oder nicht \( `false`\). Dies wird nur berücksichtigt, wenn der Zielspeicherort eine vorhandene Version der konvertierten Dateien enthält. |
| `style2tagMap` | Zeichenfolge | Ja | Absoluter Pfad der Stilzuordnungsdatei, die für die Konvertierung verwendet wird. |

**Antwortwerte**:
Gibt eine HTTP-Antwort 200 \(Erfolgreich\) zurück.

## Konvertieren von HTML-Dokumenten

Eine GET-Methode, die HTML-Dokumente in das DITA-Format konvertiert.

**Anforderungs-URL**:
http://*&lt;aem-guides-server\>*: *&lt;port-number\>*/bin/fmdita/conversion

**Parameter**:
|Name|Typ|Erforderlich|Beschreibung|
|—|—|—|—|—|
|`operation`|String|Yes|Name des aufzurufenden Vorgangs. Der Wert dieses Parameters ist ``html2dita``. <br> **Hinweis:** Beim Wert wird nicht zwischen Groß- und Kleinschreibung unterschieden.|
|`inputFile`|String|Ja|Absoluter Pfad der HTML-Quelldateien im AEM Repository.|
|`destPath`|String|Ja|Absoluter Pfad des Zielorts, an dem die konvertierten DITA-Dateien gespeichert werden.|
|`createRev`|Boolesch|Ja|Geben Sie an, ob eine Revision der Dateien \( `true`\) am angegebenen Ziel erstellt wird oder nicht \( `false`\). Dies wird nur berücksichtigt, wenn der Zielspeicherort eine vorhandene Version der konvertierten Dateien enthält.|

**Antwortwerte**:
Gibt eine HTTP-Antwort 200 \(Erfolgreich\) zurück.

## Konvertieren von InDesign-Dokumenten

Eine GET-Methode, die InDesign-Dokumente in das DITA-Format konvertiert.

**Anforderungs-URL**:
http://*&lt;aem-guides-server\>*: *&lt;port-number\>*/bin/fmdita/conversion

**Parameter**:
|Name|Typ|Erforderlich|Beschreibung|
|—|—|—|—|—|
|``operation``|String|Yes|Name des aufzurufenden Vorgangs. Der Wert dieses Parameters ist ``idml2dita``. <br> **Hinweis:** Beim Wert wird nicht zwischen Groß- und Kleinschreibung unterschieden.|
|`inputFile`|String|Ja|Absoluter Pfad der InDesign-Quelldateien im AEM Repository.|
|`destPath`|String|Ja|Absoluter Pfad des Zielorts, an dem die konvertierten DITA-Dateien gespeichert werden.|
|`createRev`|Boolesch|Ja|Geben Sie an, ob eine Revision der Dateien \( `true`\) am angegebenen Ziel erstellt wird oder nicht \( `false`\). Dies wird nur berücksichtigt, wenn der Zielspeicherort eine vorhandene Version der konvertierten Dateien enthält.|

**Antwortwerte**:
Gibt eine HTTP-Antwort 200 \(Erfolgreich\) zurück.
