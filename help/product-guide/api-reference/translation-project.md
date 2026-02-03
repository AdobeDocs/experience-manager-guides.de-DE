---
title: Erstellen eines Übersetzungsprojekts
description: Erfahren Sie mehr über das Erstellen eines API-Übersetzungsprojekts
feature: Post-Processing Event Handler
role: Developer
level: Experienced
source-git-commit: 41dd3dee5f9d64fb5c58b5b302cc9759e48e3631
workflow-type: tm+mt
source-wordcount: '199'
ht-degree: 18%

---

# Erstellen eines Übersetzungsprojekts

Eine POST-Methode, mit der Sie ein Übersetzungsprojekt erstellen können, indem Sie die erforderlichen Projektdetails akzeptieren.

## Anfrage-URL

`http://<aem-guides-server>:<port-number>/bin/guides/v1/translation/project/create`

## Abfragetyp

POST

## Anfrageparameter

| Name | Typ | Beschreibung |
|----|----|-----------|
| `type` | Zeichenfolge | newTranslationProject, xliffTranslationProject, newMultiLingualTranslationProject, addToExistingProject, newScopingTranslationProject |
| `versionDetails`, `versionSelector` | Zeichenfolge | Baseline, neueste Version, versionAsOfDate |
| `language` | Zeichenfolge | Kommagetrennte Sprachen „de“, „fr“ |
| `map.id` | Zeichenfolge | GUID der zu übersetzenden Quellzuordnung |
| `map.path` | Zeichenfolge | Pfad der zu übersetzenden Quellzuordnung |
| `referenceType` | Zeichenfolge | Indirekt, direkt |
| `fileType` | Zeichenfolge | Karte, Thema, andere |
| `documentState` | Zeichenfolge | Kann eine der Listen sein, die vom Benutzer im Zuordnungsprofil zugewiesen werden |
| `translationStatus` | Zeichenfolge | Nicht synchronisiert, Synchronisiert, Aktuell, Veraltet, In Bearbeitung, Fehlende Kopie, KEINE, Nicht zutreffend |

>[!NOTE]
>
>Sie können beim Erstellen eines Übersetzungsprojekts entweder `map.id` oder `map.path` verwenden.

## Beispiel für eine Anfrage

```JSON
{
  "title": "Test Project 1 on Dec 5",
  "type": "newTranslationProject",
  "translationDetails": {
    "map": {
      "id": "GUID-06527014-062d-46dc-8fea-48b4b4497c51-en",
      "path": "/content/dam/ajay-test/lang/en/m2.ditamap"
    },
    "languages": ["de"],
    "versionDetails": {
      "versionSelector": "latestVersion"
    }
  },
  "filterDetails": [
    { "name": "referenceType", "values": [] },
    { "name": "fileType", "values": [] },
    { "name": "documentState", "values": [] },
    { "name": "translationStatus", "values": [] }
   ]
```

## Antwortwerte

```JSON
{
  "executionId": "5c13c571-3407-46d5-8f45-50ea9e05a212",
  "path": "/content/projects/test_project_1_ondec5"
}
```

**Antwort-Codes**

- 200 Erfolg
- 400 Ungültige Eingabe
- 401 Nicht autorisierter Zugriff
- 500 Interner Server-Fehler

## Beispielanfragen

### Zu vorhandenem Projekt hinzufügen

```json
{
  "title": "Add to existing Project",
  "type": "addToExistingProject",
  "path": "/content/projects/test_project_1_existing",
  "translationDetails": {
    "map": {
      "id": "GUID-06527014-062d-46dc-8fea-48b4b4497c51-en"
    },
    "languages": ["de"],
    "versionDetails": {
      "versionSelector": "versionAsOfDate",
      "version": "2025-12-05T10:30:00+01:30"
    }
  },
  "filterDetails": [
    { "name": "referenceType", "values": [] },
    { "name": "fileType", "values": [] },
    { "name": "documentState", "values": [] },
    { "name": "translationStatus", "values": [] }
  ]
}
```

### Zu vorhandenem Projekt mit Baseline hinzufügen

```json
{
  "title": "Add to existin project Project with baseline",
  "type": "addToExistingProject",
  "path": "/content/projects/existing_project_path",
  "translationDetails": {
    "map": {
      "id": "GUID-06527014-062d-46dc-8fea-48b4b4497c51-en"
    },
    "languages": ["de"],
    "versionDetails": {
      "versionSelector": "baseline",
      "version": "test1"
    }
  },
  "filterDetails": [
    { "name": "referenceType", "values": ["Direct"] },
    { "name": "fileType", "values": [] },
    { "name": "documentState", "values": [] },
    { "name": "translationStatus", "values": [] }
  ]
}
```

## Erstellungsstatus des Übersetzungsprojekts

Eine GET-API, die den Übersetzungsstatus für ein neu erstelltes Übersetzungsprojekt verfolgt.

## Anfrage-URL

`http://<aem-guides-server>:<port-number>/bin/guides/v1/translation/project/creationstatus`

## Abfragetyp

GET

## Anfrageparameter

| Name | Typ | Beschreibung |
|----|----|-----------|
| `path` | Zeichenfolge | Pfad des Projekts |
| `languageStatusMap` | Zeichenfolge | Gibt für jede angeforderte Sprache den Abschlussstatus zurück: In Bearbeitung, Abgeschlossen, Fehlgeschlagen, Übersprungen |


## Beispiel für eine Anfrage

```json
{
  "path": "/content/projects/test_project_1_ondec5",
  "languageStatusMap": {
    "de": "Completed"
  }
}
```



