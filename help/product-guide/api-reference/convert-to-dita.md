---
title: REST-APIs für Konvertierungs-Workflow
description: Erfahren Sie mehr über die REST-APIs für Konvertierungs-Workflows
exl-id: f091782e-ab54-4db4-9018-9bcbff9da7b2
feature: Rest API Conversion Workflow
role: Developer
level: Experienced
source-git-commit: 45ae1471fe0f0586764ede9dd96530b7f75f69ee
workflow-type: tm+mt
source-wordcount: '390'
ht-degree: 9%

---

# REST-APIs für Konvertierungs-Workflow {#id175UB30E05Z}

Mit den folgenden REST-APIs können Sie Word-, HTML- und InDesign-Dokumente in das DITA-Format konvertieren.

## Word-Dokumente konvertieren

Eine GET-Methode, die Word-Dokumente in das DITA-Format konvertiert.

**Anfrage-URL**:
http://*&lt;aem-guides-server\>*: *&lt;port-number\>*/bin/fmdita/conversion

| Name | Typ | Erforderlich | Beschreibung |
|----|----|--------|-----------|
| ``operation`` | Zeichenfolge | Ja | Name des aufzurufenden Vorgangs. Der Wert dieses Parameters ist ``word2dita``. <br> **Hinweis:** Beim Wert wird nicht zwischen Groß- und Kleinschreibung unterschieden. |
| `inputFile` | Zeichenfolge | Ja | Absoluter Pfad der Word-Quelldateien im AEM-Repository. |
| `destPath` | Zeichenfolge | Ja | Absoluter Pfad des Zielspeicherorts, an dem die konvertierten DITA-Dateien gespeichert werden. |
| `createRev` | Boolesch | Ja | Geben Sie an, ob eine Revision der Dateien \( `true`\) am angegebenen Ziel erstellt wird oder nicht \( `false`\). Dies wird nur berücksichtigt, wenn der Zielspeicherort eine vorhandene Version der konvertierten Dateien enthält. |
| `style2tagMap` | Zeichenfolge | Ja | Absoluter Pfad der Stilzuordnungsdatei, die für die Konvertierung verwendet wird. |

**Antwortwerte**:
Gibt eine HTTP-Antwort 200 \(erfolgreich\) zurück.

## HTML-Dokumente konvertieren

Eine GET-Methode, die HTML-Dokumente in das DITA-Format konvertiert.

**Anfrage-URL**:

http://*&lt;aem-guides-server\>*: *&lt;port-number\>*/bin/fmdita/conversion

**Parameter**:

| Name | Typ | Erforderlich | Beschreibung |
|----|----|--------|-----------|
| `operation` | Zeichenfolge | Ja | Name des aufzurufenden Vorgangs. Der Wert dieses Parameters ist ``html2dita``. <br> **Hinweis:** Beim Wert wird nicht zwischen Groß- und Kleinschreibung unterschieden. |
| `inputFile` | Zeichenfolge | Ja | Absoluter Pfad der Quell-HTML-Dateien im AEM-Repository |
| `destPath` | Zeichenfolge | Ja | Absoluter Pfad des Zielspeicherorts, an dem die konvertierten DITA-Dateien gespeichert werden. |
| `createRev` | Boolesch | Ja | Geben Sie an, ob eine Revision der Dateien \( `true`\) am angegebenen Ziel erstellt wird oder nicht \( `false`\). Dies wird nur berücksichtigt, wenn der Zielspeicherort eine vorhandene Version der konvertierten Dateien enthält. |

**Antwortwerte**:

Gibt eine HTTP-Antwort 200 \(erfolgreich\) zurück.

## InDesign-Dokumente konvertieren

Eine GET-Methode, die InDesign-Dokumente in das DITA-Format konvertiert.

**Anfrage-URL**:
http://*&lt;aem-guides-server\>*: *&lt;port-number\>*/bin/fmdita/conversion

**Parameter**:

| Name | Typ | Erforderlich | Beschreibung |
|----|----|--------|-----------|
| ``operation`` | Zeichenfolge | Ja | Name des aufzurufenden Vorgangs. Der Wert dieses Parameters ist ``idml2dita``. <br> **Hinweis:** Beim Wert wird nicht zwischen Groß- und Kleinschreibung unterschieden. |
| `inputFile` | Zeichenfolge | Ja | Absoluter Pfad der Quell-InDesign-Dateien im AEM-Repository |
| `destPath` | Zeichenfolge | Ja | Absoluter Pfad des Zielspeicherorts, an dem die konvertierten DITA-Dateien gespeichert werden. |
| `createRev` | Boolesch | Ja | Geben Sie an, ob eine Revision der Dateien \( `true`\) am angegebenen Ziel erstellt wird oder nicht \( `false`\). Dies wird nur berücksichtigt, wenn der Zielspeicherort eine vorhandene Version der konvertierten Dateien enthält. |

**Antwortwerte**:
Gibt eine HTTP-Antwort 200 \(erfolgreich\) zurück.
