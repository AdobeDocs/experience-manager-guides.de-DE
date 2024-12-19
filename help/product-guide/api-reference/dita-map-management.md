---
title: REST-API für DITA-Zuordnungen
description: Informationen zur REST-API für die Arbeit mit DITA-Karten
exl-id: 6277e52d-1b05-4dd7-8d2b-4b94f329e2d7
feature: Rest API DITA Map
role: Developer
level: Experienced
source-git-commit: 1843cae11aac38053abc3c50fa2d00c050520470
workflow-type: tm+mt
source-wordcount: '611'
ht-degree: 4%

---

# REST-API für DITA-Zuordnungen {#id175UB30E05Z}

Mit der folgenden REST-API können Sie mit DITA-Zuordnungen in AEM Guides arbeiten.

## DITA Map mit Angehörigen herunterladen

Eine GET-Methode, die eine DITA-Zuordnung mit allen abhängigen Elementen wie referenzierten Themen, Unterkarten, Bildern und DTDs herunterlädt, die in der Zuordnung und in Themen verwendet werden.

**Anfrage-URL**:
http://*&lt;aem-guides-server\>*: *&lt;port-number\>*/bin/fmdita/exportDitAmap

**Parameter**:

| Name | Typ | Erforderlich | Beschreibung |
|----|----|--------|-----------|
| `ditamap` | Zeichenfolge | Ja | Absoluter Pfad der DITA-Zuordnungsdatei im AEM-Repository. |
| `baseline` | Zeichenfolge | Nein | Der Titel der Baseline, die zum Abrufen des versionierten Inhalts verwendet wird. <br> **Hinweis:** Beim Wert wird zwischen Groß- und Kleinschreibung unterschieden. |

**Antwortwerte**:
Eine ZIP-Datei, deren Inhalt in den Ausgabestream der Antwort geschrieben wird.

## Export für DITA-Map mit abhängigen Elementen starten

Eine Exportmethode, die einen POST für eine DITA-Zuordnung mit allen abhängigen Elementen wie referenzierten Themen, Unterkarten, Bildern und DTDs initiiert, die in der Zuordnung und in Themen verwendet werden. Der Status kann später abgefragt werden, und die Download-URL kann abgerufen werden, sobald er abgeschlossen ist.

**Anfrage-URL**:
http:*//&lt;aem-guides-server\>: &lt;port-number\>/bin/dxml/async-export*

**Parameter**:

| Name | Typ | Erforderlich | Beschreibung |
|----|----|--------|-----------|
| `ditamap` | Zeichenfolge | Ja | Absoluter Pfad der DITA-Zuordnungsdatei im AEM-Repository. |
| `baseline` | Zeichenfolge | Nein | Der Titel der Baseline, die zum Abrufen des versionierten Inhalts verwendet wird. <br> **Hinweis:** Beim Wert wird zwischen Groß- und Kleinschreibung unterschieden. |
| `flatFS` | Boolesch | Nein | \(Optional\) Wenn auf „true“ gesetzt, wird eine flache Struktur von Dateien in der ZIP-Datei zurückgegeben. Wenn sich Ihre DITA-Zuordnung beispielsweise auf Inhalte in mehreren Ordnern bezieht, werden alle referenzierten Dateien in einen einzelnen Ordner gezogen. Wenn es Dateien mit demselben Namen gibt, werden diese Dateien durch Hinzufügen eines numerischen Suffix umbenannt. Alle Verweise \(in DITA-Map und Themen\) werden automatisch verarbeitet, da sie auf der Grundlage des neuen Speicherorts der Dateien in der flachen Ordnerstruktur aktualisiert werden. Wenn dies auf „false“ festgelegt ist, wird die Ordnerstruktur in der ZIP-Datei unverändert beibehalten. Wenn sich die DITA-Zuordnung auf Dateien aus mehreren Speicherorten bezieht, werden alle diese Speicherorte ebenfalls in der ZIP-Datei erstellt. Wenn Sie die ZIP-Datei wiederherstellen, wird die exakte Ordnerstruktur am Zielspeicherort erstellt. <br> Der Standardwert für diesen Parameter ist „false“. |

**Antwortwerte**:

| Element | Beschreibung |
|-------|-----------|
| `status` | Der Rückgabestatus für den ausgeführten Vorgang. Die möglichen Optionen sind: GESTARTET, FEHLGESCHLAGEN, IN BEARBEITUNG, ERFOLGREICH, FEHLT, GELÖSCHT |
| `jobId` | Die eindeutige ID des Vorgangs. Kann später verwendet werden, um den Status abzufragen. |
| errorMessage | Fehlermeldung des Vorgangs im Falle eines Fehlschlagens \(wenn der Status FEHLGESCHLAGEN, FEHLT oder GELÖSCHT ist\). |
| `filePath` | Der Dateipfad der ZIP. Sie ist nur vorhanden, wenn der Auftrag abgeschlossen ist und der Status ERFOLGREICH ist. Hiermit kann die ZIP-Datei heruntergeladen werden. |

## DITA-Zuordnungsstatus des Abfrageexports

Eine GET-Methode, die den Exportstatus für eine DITA-Zuordnung mit allen abhängigen Elementen abruft. Sie kann in einem Intervall abgefragt werden, ob der Status GESTARTET oder IN BEARBEITUNG ist, bis sie beendet ist \(erfolgreich oder mit einem Fehler\).

**Anfrage-URL**:
http:*//&lt;aem-guides-server\>: &lt;port-number\>/bin/dxml/async-export*

**Parameter**:

| Name | Typ | Erforderlich | Beschreibung |
|----|----|--------|-----------|
| `jobId` | Zeichenfolge | Ja | Die Auftrags-ID, die abgerufen wird, wenn der Exportvorgang initiiert wird. |

**Antwortwerte**:

| Element | Beschreibung |
|-------|-----------|
| `status` | Der Status des Exportvorgangs. Die möglichen Optionen sind: GESTARTET, FEHLGESCHLAGEN, IN BEARBEITUNG, ERFOLGREICH, FEHLT, GELÖSCHT |
| `jobId` | Die eindeutige ID des Vorgangs. Kann später verwendet werden, um den Status abzufragen. |
| `errorMessage` | Fehlermeldung des Vorgangs im Falle eines Fehlschlagens \(wenn der Status FEHLGESCHLAGEN, FEHLT oder GELÖSCHT ist\). |
| `filePath` | Der Dateipfad der ZIP. Sie ist nur vorhanden, wenn der Auftrag abgeschlossen ist und der Status ERFOLGREICH ist. Hiermit kann die ZIP-Datei heruntergeladen werden. |
