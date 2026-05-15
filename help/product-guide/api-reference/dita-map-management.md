---
title: REST-API für DITA-Zuordnungen
description: Informationen zur REST-API für die Arbeit mit DITA-Karten
exl-id: 6277e52d-1b05-4dd7-8d2b-4b94f329e2d7
feature: Rest API DITA Map
role: Developer
level: Experienced
TQID: https://experienceleague.adobe.com/GT4JRw1nFV7M18tJX-0t0Gx-g0I9tA8XfXLGnnhvif0
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2:
  - id: a01bfd36-4ab8-4bf8-9dc0-5b45b890552e
  - id: c6d09140-3c91-45d3-b7ed-b681af752f43
subfeature_v2:
  - id: b7cb7f25-3b6d-4e58-beab-fe9279275fe4
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 626
ht-degree: 4%

---

# REST-API für DITA-Zuordnungen {#id175UB30E05Z}

Mit der folgenden REST-API können Sie mit DITA-Zuordnungen in AEM Guides arbeiten.

## DITA Map mit Angehörigen herunterladen

Eine GET-Methode, die eine DITA-Zuordnung mit allen abhängigen Elementen wie referenzierten Themen, Unterzuordnungen, Bildern und DTDs herunterlädt, die in der Zuordnung und in Themen verwendet werden.

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

Eine POST-Methode, die den Export für eine DITA-Zuordnung mit allen abhängigen Elementen wie referenzierten Themen, Unterkarten, Bildern und DTDs initiiert, die in der Zuordnung und in Themen verwendet werden. Der Status kann später abgefragt werden, und die Download-URL kann abgerufen werden, sobald er abgeschlossen ist.

**Anfrage-URL**:
http:*//&lt;aem-guides-server\>: &lt;port-number\>/bin/dxml/async-export*

**Parameter**:

| Name | Typ | Erforderlich | Beschreibung |
|----|----|--------|-----------|
| `ditamap` | Zeichenfolge | Ja | Absoluter Pfad der DITA-Zuordnungsdatei im AEM-Repository. |
| `baseline` | Zeichenfolge | Nein | Der Titel der Baseline, die zum Abrufen des versionierten Inhalts verwendet wird. <br> **Hinweis:** Beim Wert wird zwischen Groß- und Kleinschreibung unterschieden. |
| `flatFS` | Boolescher Wert | Nein | \(Optional\) Wenn auf „true“ gesetzt, wird eine flache Struktur von Dateien in der ZIP-Datei zurückgegeben. Wenn sich Ihre DITA-Zuordnung beispielsweise auf Inhalte in mehreren Ordnern bezieht, werden alle referenzierten Dateien in einen einzelnen Ordner gezogen. Wenn es Dateien mit demselben Namen gibt, werden diese Dateien durch Hinzufügen eines numerischen Suffix umbenannt. Alle Verweise \(in DITA-Map und Themen\) werden automatisch verarbeitet, da sie auf der Grundlage des neuen Speicherorts der Dateien in der flachen Ordnerstruktur aktualisiert werden. Wenn dies auf „false“ festgelegt ist, wird die Ordnerstruktur in der ZIP-Datei unverändert beibehalten. Wenn sich die DITA-Zuordnung auf Dateien aus mehreren Speicherorten bezieht, werden alle diese Speicherorte ebenfalls in der ZIP-Datei erstellt. Wenn Sie die ZIP-Datei wiederherstellen, wird die exakte Ordnerstruktur am Zielspeicherort erstellt. <br> Der Standardwert für diesen Parameter ist „false“. |

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
