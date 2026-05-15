---
title: REST-APIs für Konvertierungs-Workflow
description: Erfahren Sie mehr über die REST-APIs für Konvertierungs-Workflows
exl-id: f091782e-ab54-4db4-9018-9bcbff9da7b2
feature: Rest API Conversion Workflow
role: Developer
level: Experienced
TQID: https://experienceleague.adobe.com/EG-ugDPVpviaEI1SXHOaFLPfChkzqQ8tSkPV-LZ-X3o
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2:
  - id: a01bfd36-4ab8-4bf8-9dc0-5b45b890552e
  - id: c6d09140-3c91-45d3-b7ed-b681af752f43
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 402
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
| `createRev` | Boolescher Wert | Ja | Geben Sie an, ob eine Revision der Dateien \( `true`\) am angegebenen Ziel erstellt wird oder nicht \( `false`\). Dies wird nur berücksichtigt, wenn der Zielspeicherort eine vorhandene Version der konvertierten Dateien enthält. |
| `style2tagMap` | Zeichenfolge | Ja | Absoluter Pfad der Stilzuordnungsdatei, die für die Konvertierung verwendet wird. |

**Antwortwerte**:
Gibt eine HTTP-Antwort 200 \(erfolgreich\) zurück.

## HTML-Dokumente konvertieren

Eine GET-Methode, die HTML-Dokumente in das DITA-Format konvertiert.

**Anfrage-URL**:

http://*<aem-guides-server\>*: *<port-number\>*/bin/fmdita/conversion

**Parameter**:

| Name | Typ | Erforderlich | Beschreibung |
|----|----|--------|-----------|
| `operation` | Zeichenfolge | Ja | Name des aufzurufenden Vorgangs. Der Wert dieses Parameters ist ``html2dita``. <br> **Hinweis:** Beim Wert wird nicht zwischen Groß- und Kleinschreibung unterschieden. |
| `inputFile` | Zeichenfolge | Ja | Absoluter Pfad der HTML-Quelldateien im AEM-Repository. |
| `destPath` | Zeichenfolge | Ja | Absoluter Pfad des Zielspeicherorts, an dem die konvertierten DITA-Dateien gespeichert werden. |
| `createRev` | Boolescher Wert | Ja | Geben Sie an, ob eine Revision der Dateien \( `true`\) am angegebenen Ziel erstellt wird oder nicht \( `false`\). Dies wird nur berücksichtigt, wenn der Zielspeicherort eine vorhandene Version der konvertierten Dateien enthält. |

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
| `inputFile` | Zeichenfolge | Ja | Absoluter Pfad der InDesign-Quelldateien im AEM-Repository. |
| `destPath` | Zeichenfolge | Ja | Absoluter Pfad des Zielspeicherorts, an dem die konvertierten DITA-Dateien gespeichert werden. |
| `createRev` | Boolescher Wert | Ja | Geben Sie an, ob eine Revision der Dateien \( `true`\) am angegebenen Ziel erstellt wird oder nicht \( `false`\). Dies wird nur berücksichtigt, wenn der Zielspeicherort eine vorhandene Version der konvertierten Dateien enthält. |

**Antwortwerte**:
Gibt eine HTTP-Antwort 200 \(erfolgreich\) zurück.
