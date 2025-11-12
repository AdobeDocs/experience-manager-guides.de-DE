---
title: API zum Starten der Massenverarbeitung für Assets
description: Erfahren Sie mehr über die API zum Starten der Massenverarbeitung für Assets
feature: Post-Processing Event Handler
role: Developer
level: Experienced
source-git-commit: e2eca63a5dd56e358aeea047b37f4b0f88dc720b
workflow-type: tm+mt
source-wordcount: '542'
ht-degree: 11%

---

# API zum Starten der Massenverarbeitung für Assets

Eine POST-Methode, die die Massenverarbeitung von Assets für einen angegebenen Pfad initiiert. Diese API unterstützt sowohl die JCR-basierte als auch die datenbankbasierte Asset-Verarbeitung. Dadurch wird ein asynchroner Auftrag gestartet, der alle Assets unter dem angegebenen Pfad und dessen Unterpfaden verarbeitet. Nach der Initiierung gibt die API eine eindeutige Verarbeitungs-ID zurück, mit der der Auftragsstatus verfolgt werden kann.

**URL-Anforderung**

`http://<aem-guides-server>:<port-number>/bin/guides/v1/assets/process`

**Anfrageparameter**

| Name | Typ | Erforderlich | Beschreibung |
|----|----|--------|-----------|
| `path` | Zeichenfolge | Ja | Absoluter Pfad des Ordners oder Assets im zu verarbeitenden AEM-Repository. |
| `excludedPaths` | Zeichenfolge | Nein | Liste der von der Verarbeitung auszuschließenden Pfade |
| `type` | Zeichenfolge | Ja | Art der durchzuführenden Verarbeitung. Beispiel: ASSET_PROCESSING. |

**Beispiel für eine Anfrage**

```JSON
{
  "path": "/content/dam/status-fetch1",
  "excludedPaths": [
    "content/dam/status-fetch1/excluded-folder"
  ],
  "type": "ASSET_PROCESSING"
}
```

**Antwortwerte**

processingId , um den Status des asynchronen Auftrags abzurufen.

```JSON
{
  "processingId": "akjhdfalkj1132"
}
```

**Antwort-Codes**

- 200 Erfolg
- 400 Ungültige Eingabe
- 401 Nicht autorisierter Zugriff
- 500 Interner Server-Fehler

## Überprüfen des Auftragsstatus

Eine GET-Methode, die den aktuellen Status eines zuvor gestarteten Asset-Verarbeitungsauftrags abruft.

**URL-Anforderung**

`http://<aem-guides-server>:<port-number>/bin/guides/v1/assets/process/status`

**Anfrageparameter**

| Name | Typ | Erforderlich | Beschreibung |
|----|----|--------|-----------|
| `processingId` | Zeichenfolge | Ja | Eindeutige ID des Auftrags, dessen Status abgefragt wird. |

**Beispiel für eine Antwort**

```JSON
{
  "processingId": "string",
  "path": "string",
  "excludedPaths": ["string"],
  "status": "WAITING",
  "triggeredCount": 0,
  "startedAt": 0,
  "completedAt": 0,
  "hasLogs": true,
  "createdBy": "string",
  "type": "ASSET_PROCESSING",
  "migrationSet": {
    "totalFiles": 0,
    "calculationStatus": "WAITING"
  },
  "eta": {
    "value": 0,
    "unit": "string"
  },
  "comments": "string",
  "restartable": true,
  "resumable": true,
  "cancellable": true
}
```

**Antwort-Codes**

- 200 Erfolg
- 400 Ungültige Eingabe
- 401 Nicht autorisierter Zugriff
- 500 Interner Server-Fehler

## Vorgangslogs anzeigen

Eine GET-Methode, die Protokolle für eine bestimmte Auftrags-ID abruft. Diese API ruft die Protokolle des Asset-Verarbeitungsauftrags ab. Die Verarbeitungs-ID ist obligatorisch. Die API stellt Versatz- und Begrenzungsparameter sowie eine Tailing-Strategie bereit.

**URL-Anforderung**

`http://<aem-guides-server>:<port-number>/bin/guides/v1/assets/process/logs`

**Anfrageparameter**

| Name | Typ | Erforderlich | Beschreibung |
|----|----|--------|-----------|
| `processingId` | Zeichenfolge | Ja | Eindeutige ID des Auftrags, dessen Protokolle angezeigt werden sollen. |
| `offset` | Ganzzahl | Nein | Der Ausgangspunkt (Zeilennummer), von dem die Protokolle gelesen werden sollen. Wird für die Paginierung verwendet, um die ersten N Zeilen zu überspringen. |
| `limit` | Ganzzahl | Nein | Die maximale Anzahl der abzurufenden Protokollzeilen. |
| `tail` | Ganzzahl | Nein | Anzahl der Protokollzeilen, die vom Ende abgerufen werden sollen. |


**Beispiel für eine Antwort**

```JSON
{
  "lines": [
    "string"
  ],
  "limit": 0,
  "offset": 0,
  "hasMore": true
}
```

**Antwort-Codes**

- 200 Erfolg
- 400 Ungültige Eingabe
- 401 Nicht autorisierter Zugriff
- 500 Interner Server-Fehler


## Vorgangslogs herunterladen

Eine GET-Methode, die die Protokolldatei für einen bestimmten Auftrag als ZIP herunterlädt.

**URL-Anforderung**

`http://<aem-guides-server>:<port-number>/bin/guides/v1/assets/process/logs/download`

**Anfrageparameter**

| Name | Typ | Erforderlich | Beschreibung |
|----|----|--------|-----------|
| `processingId` | Zeichenfolge | Ja | Eindeutige ID des Auftrags, dessen Protokolldatei heruntergeladen werden muss. |


**Beispiel für eine Antwort**

```JSON
{
  "logFilePaths": [
    "string"
  ]
}
 
```

**Antwort-Codes**

- 400 Ungültige Eingabe
- 401 Nicht autorisierter Zugriff
- 500 Interner Server-Fehler

## Auftrag abbrechen

Eine POST-API, die eine laufende Massen-Asset-Verarbeitungsanfrage abbricht. Wenn der Auftrag nicht gefunden wird, gibt die API einen Fehler zurück.

**URL-Anforderung**

`http://<aem-guides-server>:<port-number>/bin/guides/v1/assets/process/cancel`

**Anfrageparameter**

| Name | Typ | Erforderlich | Beschreibung |
|----|----|--------|-----------|
| `processingId` | Zeichenfolge | Ja | Eindeutige ID des Auftrags, dessen Status abgefragt wird. |


**Antwort-Codes**

- 200 Erfolg
- 400 Ungültige Eingabe
- 401 Nicht autorisierter Zugriff
- 500 Interner Server-Fehler


## Vorgang fortsetzen

Eine POST-API, die eine zuvor abgebrochene oder fehlgeschlagene Massen-Asset-Verarbeitungsanfrage neu startet. Die Verarbeitung wird am letzten Checkpoint fortgesetzt. Wenn der Auftrag nicht gefunden wird oder gerade ausgeführt wird, gibt die API einen Fehler zurück.

**URL-Anforderung**

`http://<aem-guides-server>:<port-number>/bin/guides/v1/assets/process/resume`

**Anfrageparameter**

| Name | Typ | Erforderlich | Beschreibung |
|----|----|--------|-----------|
| `processingId` | Zeichenfolge | Ja | Eindeutige ID des Auftrags, dessen Status abgefragt wird. |


**Antwort-Codes**

- 200 Erfolg
- 400 Ungültige Eingabe
- 401 Nicht autorisierter Zugriff
- 500 Interner Server-Fehler

## Vorgangsverlauf anzeigen

Eine GET-API, die die letzten N Ausführungen der Asset-Nachbearbeitung zurückgibt.

**URL-Anforderung**

`http://<aem-guides-server>:<port-number>/bin/guides/v1/assets/process/history`

**Anfrageparameter**

Ohne. Diese GET-Anfrage ruft den Auftragsverlauf ab, ohne dass Eingabeparameter erforderlich sind.

**Beispiel für eine Antwort**

```JSON
{
  "executionHistory": [
    {
      "processingId": "165f1de6-68c4-4dcd-9223-2b7242b62306",
      "path": "/content/dam/22858",
      "status": "SUCCESS",
      "triggeredCount": 6,
      "startedAt": 1761291362776,
      "completedAt": 1761291364026,
      "hasLogs": true,
      "createdBy": "user",
      "type": "ASSET_PROCESSING",
      "migrationSet": {
        "totalFiles": 6,
        "calculationStatus": "SUCCESS"
      },
      "eta": {
        "value": 0,
        "unit": "SECONDS"
      },
      "comments": "",
      "filter": {
        "fileTypes": [],
        "filterProcessedAssets": false
      },
      "cancellable": false,
      "resumable": false,
      "restartable": true
    }
  ]
}
```



