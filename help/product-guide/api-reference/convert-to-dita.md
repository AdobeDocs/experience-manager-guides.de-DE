---
title: REST-APIs für Konvertierungs-Workflow
description: Erfahren Sie mehr über die REST-APIs für Konvertierungs-Workflows
exl-id: f091782e-ab54-4db4-9018-9bcbff9da7b2
feature: Rest API Conversion Workflow
role: Developer
level: Experienced
TQID: 'https://experienceleague.adobe.com/EG-ugDPVpviaEI1SXHOaFLPfChkzqQ8tSkPV-LZ-X3o'
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
    internal-label: Experience Manager Guides
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
    internal-label: Experience Manager
feature_v2:
  - id: a01bfd36-4ab8-4bf8-9dc0-5b45b890552e
    internal-label: APIs
  - id: c6d09140-3c91-45d3-b7ed-b681af752f43
    internal-label: APIs
subfeature_v2:
  - id: d3b388b7-b49d-4f87-b444-9b6f7fc2ef0c
    internal-label: REST API Conversion Workflow
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
level_v2:
  - id: d378ca77-2da1-4f39-ad92-1917fe974a38
    internal-label: Experienced
source-git-commit: 81a0e7f0736ba4970673dd87a888a4c60d3c1b4e
workflow-type: tm+mt
source-wordcount: '402'
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

http://*<aem-guides-server\>*: *<port-number\>*/bin/fmdita/conversion

**Parameter**:

| Name | Typ | Erforderlich | Beschreibung |
|----|----|--------|-----------|
| `operation` | Zeichenfolge | Ja | Name des aufzurufenden Vorgangs. Der Wert dieses Parameters ist ``html2dita``. <br> **Hinweis:** Beim Wert wird nicht zwischen Groß- und Kleinschreibung unterschieden. |
| `inputFile` | Zeichenfolge | Ja | Absoluter Pfad der HTML-Quelldateien im AEM-Repository. |
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
| `inputFile` | Zeichenfolge | Ja | Absoluter Pfad der InDesign-Quelldateien im AEM-Repository. |
| `destPath` | Zeichenfolge | Ja | Absoluter Pfad des Zielspeicherorts, an dem die konvertierten DITA-Dateien gespeichert werden. |
| `createRev` | Boolesch | Ja | Geben Sie an, ob eine Revision der Dateien \( `true`\) am angegebenen Ziel erstellt wird oder nicht \( `false`\). Dies wird nur berücksichtigt, wenn der Zielspeicherort eine vorhandene Version der konvertierten Dateien enthält. |

**Antwortwerte**:
Gibt eine HTTP-Antwort 200 \(erfolgreich\) zurück.
