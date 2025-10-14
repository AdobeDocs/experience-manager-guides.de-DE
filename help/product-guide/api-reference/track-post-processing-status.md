---
title: API zum Nachverfolgen der Verarbeitung für einen Ordner oder ein Asset
description: Erfahren Sie mehr über die API zum Nachverfolgen der Nachbearbeitung für einen Ordner oder ein Asset
feature: Post-Processing Event Handler
role: Developer
level: Experienced
source-git-commit: 558108650aeeeda440895972e460fa523b804bb2
workflow-type: tm+mt
source-wordcount: '150'
ht-degree: 13%

---

# API zum Nachverfolgen des Verarbeitungsstatus für einen Ordner oder ein Asset

Im Folgenden finden Sie eine POST-Methode, die einen asynchronen Auftrag startet, um den Status der Assets abzurufen.

## Status von Assets in Handbüchern suchen

**URL-Anforderung**

`http://<aem-guides-server>:<port-number>bin/guides/v1/assets/status `

**Parameter**

| Name | Typ | Erforderlich | Beschreibung |
|----|----|--------|-----------|
| `path` | Zeichenfolge | Ja | Ordner- oder Asset-Pfad, für den der Status abgerufen werden muss. |
| `excludedPaths` | Zeichenfolge | Nein | Ordnerpfade, die aus der obigen Liste ausgeschlossen werden sollen. |

```JSON
{ 

    "paths": [ 

        "/content/dam/status-fetch1", 

        "/content/dam/status-fetch2" 

    ], 

    "excludedPaths": [ 

        "content/dam/status-fetch1/excluded-folder" 

    ] 

} 
```

**Antwortwerte**
jobId, um den Status des asynchronen Auftrags abzurufen.

```JSON
{ 

  "jobId": "akjhdfalkj1132", 

  "status": "WAITING", 

 

} 
```

## Poller-API

Eine GET-Methode, die den Status eines asynchronen Auftrags abruft, der von der obigen API ausgeführt wird.

**URL-Anforderung**

`http://<aem-guides-server>:<port-number>bin/guides/v1/assets/status`

**Parameter**

| Name | Typ | Erforderlich | Beschreibung |
|----|----|--------|-----------|
| `jobId` | Zeichenfolge | Ja | Vorgangs-ID, die von der obigen API zurückgegeben wurde. |

**Antwortwerte**

Liste der Assets und deren Status.

```JSON
{ 

  "jobId": " akjhdfalkj1132", 

  "status": "SUCCESS", 

  "assets": [ 

    { 

      "path": "/content/dam/status-fetch1/a.dita", 

      "uuid": "GUID-1293914ansd", 

      "status": "SUCCESS", 

      "exists": true 

    }, 

    { 

      "path": "/content/dam/status-fetch1/b.dita", 

      "uuid": "GUID-1883241", 

      "status": "FAILURE", 

      "exists": true 

    } 

 

  ] 

} 
```

**Statuswerte:**, FEHLER, VERARBEITUNG, AUSSTEHEND
