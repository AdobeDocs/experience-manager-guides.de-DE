---
title: Versionshinweise zu | Upgrade-Anweisungen und behobene Probleme in Adobe Experience Manager Guides, Version September 2023
description: Erfahren Sie mehr über die Fehlerbehebungen und das Upgrade auf Version September 2023 von Adobe Experience Manager Guides as a Cloud Service
exl-id: 795b86a0-e763-404a-a4bb-35d3d2a42672
feature: Release Notes
role: Leader
source-git-commit: 6e23f52fc9124d0f07f8108da1b5fe574f553469
workflow-type: tm+mt
source-wordcount: '1485'
ht-degree: 0%

---

# Version September 2023 von Adobe Experience Manager Guides as a Cloud Service

Diese Versionshinweise enthalten die Upgrade-Anweisungen, die Kompatibilitätsmatrix und behobene Probleme in Version September 2023 von Adobe Experience Manager Guides (später als *AEM Guides as a Cloud Service* bezeichnet).

Weitere Informationen zu den neuen Funktionen und Verbesserungen finden Sie unter [Neue Funktionen in der Version September 2023 von AEM Guides as a Cloud Service](whats-new-2023-9-0.md).

## Upgrade auf Version September 2023

Führen Sie ein Upgrade Ihres aktuellen AEM Guides as a Cloud Service-Setups durch, indem Sie die folgenden Schritte ausführen:

1. Checken Sie den Git-Code der Cloud Services aus und wechseln Sie zu der Verzweigung, die in der Cloud Services-Pipeline konfiguriert ist und der Umgebung entspricht, die Sie aktualisieren möchten.
2. Aktualisieren Sie `<dox.version>` Eigenschaft in `/dox/dox.installer/pom.xml` Datei Ihres Cloud Services-Git-Codes auf 2023.9.0.359.
3. Übernehmen Sie die Änderungen und führen Sie die Cloud Services-Pipeline aus, um auf die Version September 2023 von AEM Guides as a Cloud Service zu aktualisieren.

## Schritte zum Aktivieren des Triggers eines Skripts über ein Servlet

(Nur bei Versionen vor der Version Juni 2023 von AEM Guides as a Cloud Service)

Nach Abschluss der Installation können Sie den Trigger drücken, um den Übersetzungsauftrag zu starten:

BEITRAG:

```
http://localhost:4503/bin/guides/script/start?jobType=translation-map-upgrade
```

Antwort:

```
{
"msg": "Job is successfully submitted and lock node is created for future reference",
"lockNodePath": "/var/dxml/executor-locks/translation-map-upgrade/1683190032886",
"status": "SCHEDULED"
}
```

In der vorherigen Antwort-JSON enthält der `lockNodePath` den Pfad zum Knoten , der im Repository erstellt wurde und auf den gesendeten Auftrag verweist. Sie wird automatisch gelöscht, sobald der Auftrag abgeschlossen ist. Bis dahin können Sie in diesem Knoten den aktuellen Status des Auftrags abrufen.

Warten Sie, bis dieser Vorgang abgeschlossen ist, bevor Sie mit den nächsten Schritten fortfahren.

>[!NOTE]
>
> Überprüfen Sie, ob der Knoten noch vorhanden ist, und den Status des Auftrags.

```
GET
http://<aem_domain>/var/dxml/executor-locks/translation-map-upgrade/1683190032886.json
```

## Schritte zur Nachbearbeitung des vorhandenen Inhalts, um den Bericht über fehlerhafte Links zu verwenden

(Nur bei Versionen vor der Version Juni 2023 von AEM Guides as a Cloud Service)

Führen Sie die folgenden Schritte aus, um den vorhandenen Inhalt nachzuverarbeiten und den neuen Bericht „Beschädigter Link“ zu verwenden:

1. (Optional) Wenn mehr als 100.000 DITA-Dateien im System vorhanden sind, aktualisieren Sie die `queryLimitReads` unter `org.apache.jackrabbit.oak.query.QueryEngineSettingsService` auf einen größeren Wert (einen beliebigen Wert, der größer ist als die Anzahl der vorhandenen Assets, z. B. 200.000) und stellen Sie dann erneut bereit.

   - Verwenden Sie die Anweisungen im Abschnitt *Konfigurationsüberschreibungen* unter Installieren und Konfigurieren von Adobe Experience Manager Guides
as a Cloud Service, um die Konfigurationsdatei zu erstellen.
   - Geben Sie in der Konfigurationsdatei die folgenden (Eigenschafts-)Details an, um die Option queryLimitReads zu konfigurieren:

     | PID | Eigenschaftsschlüssel | Eigenschaftswert |
     |---|---|---|
     | org.apache.jackrabbit.oak.query.QueryEngineSettingsService | queryLimitReads | Wert: 200000 Standardwert: 100000 |

1. Ausführen einer POST-Anfrage an den Server (mit korrekter Authentifizierung) - `http://<server:port>//bin/guides/reports/upgrade`.

1. Die API gibt eine jobId zurück. Um den Auftragsstatus zu überprüfen, können Sie eine GET-Anfrage mit Auftrags-ID an denselben Endpunkt senden - `http://<server:port>/bin/guides/reports/upgrade?jobId= {jobId}`
(Beispiel: `http://localhost:8080/bin/guides/map-find/indexing?jobId=2022/9/15/7/27/7dfa1271-981e-4617-b5a4-c18379f11c42_678`)

1. Sobald der Vorgang abgeschlossen ist, wird die vorherige GET-Anfrage erfolgreich beantwortet. Wenn der Vorgang aus irgendeinem Grund fehlschlägt, kann der Fehler in den Serverprotokollen angezeigt werden.

1. Kehren Sie zum Standardwert oder vorherigen vorhandenen Wert von `queryLimitReads` zurück, wenn Sie ihn in Schritt 1 geändert haben.

## Schritte zum Indizieren des vorhandenen Inhalts, um die neue Themenliste „Suchen und Ersetzen“ auf der Registerkarte „Berichte“ zu verwenden:

(Nur bei Versionen vor der Version Juni 2023 von AEM Guides as a Cloud Service)

Führen Sie die folgenden Schritte aus, um den vorhandenen Inhalt zu indizieren und den neuen Text „Suchen und Ersetzen“ auf Zuordnungsebene und in der Themenliste auf der Registerkarte „Berichte“ zu verwenden:

1. Führen Sie eine POST-Anfrage an den Server \(mit korrekter Authentifizierung\) - `http://<server:port\>/bin/guides/map-find/indexing` aus. (Optional) Sie können bestimmte Pfade der Zuordnungen übergeben, um sie zu indizieren. Standardmäßig werden alle Zuordnungen indiziert \|\| Beispiel: `https://<Server:port\>/bin/guides/map-find/indexing?paths=<map\_path\_in\_repository\>`)

1. Sie können auch einen Stammordner übergeben, um die DITA-Zuordnungen eines bestimmten Ordners (und seiner Unterordner) zu indizieren. Beispiel: `http://<server:port\>/bin/guides/map-find/indexing?root=/content/dam/test`. Beachten Sie, dass nur der Pfadparameter berücksichtigt wird, wenn sowohl der Pfadparameter als auch der Stammparameter übergeben werden.

1. Die API gibt eine jobId zurück. Zur Überprüfung des Auftragsstatus können Sie eine GET-Anfrage mit Auftrags-ID an denselben Endpunkt senden - `http://<server:port\>/bin/guides/map-find/indexing?jobId=\{jobId\}`\(Beispiel: `http://localhost:8080/bin/guides/map-find/indexing?jobId=2022/9/15/7/27/7dfa1271-981e-4617-b5a4-c18379f11c42`\)


1. Sobald der Vorgang abgeschlossen ist, wird die vorherige GET-Anfrage erfolgreich beantwortet und es wird angegeben, ob Zuordnungen fehlgeschlagen sind. Die erfolgreich indizierten Zuordnungen können aus den Serverprotokollen bestätigt werden.

## Kompatibilitätsmatrix

In diesem Abschnitt finden Sie die Kompatibilitätsmatrix für die Softwareanwendungen, die von AEM Guides as a Cloud Service Version September 2023 unterstützt werden.

### FrameMaker und FrameMaker Publishing Server

| AEM Guides as a Cloud Service-Version | FMPS | FrameMaker |
| --- | --- | --- |
| 2 023,09,0 | Nicht kompatibel | 2022 oder höher |
| | | |


### Sauerstoffanschluss

| AEM Guides as a Cloud Service-Version | Fenster des Sauerstoffanschlusses | Oxygen Connector Mac | In Oxygen Windows bearbeiten | In Oxygen Mac bearbeiten |
| --- | --- | --- | --- | --- |
| 2 023,09,0 | 3.1-uuid 17 | 3.1-uuid 17 | 2,3 | 2,3 |
|  |  |  |  |  |


### Version der Wissensdatenbankvorlage

| Paketname der Komponenten | Komponentenversion | Vorlagenversion |
|---|---|---|
| AEM Guides-Komponenten-Inhaltspaket für Cloud Service | dxml-components.all-1.2.2 | aem-site-template-dxml.all-1.0.15 |

## Behobene Probleme

Die in verschiedenen Bereichen behobenen Fehler sind unten aufgeführt:

### Authoring

- Die Themendatei wird nicht im Web-Editor entsperrt, obwohl die Optionen Datei entsperren und Nicht speichern ausgewählt sind. 12558)
- Eine Datei kann nicht im Web-Editor ausgecheckt werden, obwohl die Option NEIN ausgewählt wurde, um die Änderungen vor dem Einchecken zu verwerfen. 12557)
- Die QuickInfos für die Dateisymbole „Sperren und Entsperren“ in der Hauptsymbolleiste im Web-Editor stimmen nicht mit den in der Repository-Ansicht angezeigten Symbolen überein.12555)
- Die Option Auschecken abbrechen und Entsperren wird für eine Datei im Web-Editor angezeigt, die noch nicht in der Kartenansicht ausgecheckt wurde. 12556)
- Die PDF-Assets in den vorhandenen Links „topicref“ können nicht ausgewählt werden. (12477).
- In der Repository-Ansicht können die Themen oder Bilder nach Verwendung der Such-/Filterfunktion nicht verschoben werden. 12396)
- Suchergebnisse werden im Bedienfeld Suchen und Ersetzen deaktiviert, nachdem eine durchsuchte Datei geöffnet wurde. 12142)
- Die Zifferntaste „8“ auf der seitlichen Tastatur funktioniert im AEM Guides-Editor nicht. 12106)

- Das Präfix wird im Vorschaumodus des Web-Editors dupliziert. 13133)
- `Choicetable` Zeilen werden nicht angezeigt oder können nicht ausgewählt werden. 12616)
- Der Web-Editor gibt bei der Erstellung eines Themas mithilfe eines benutzerdefinierten Schemas Validierungsfehler in bestimmten Szenarien aus. 12576)
- Die Verweise auf die ditavale Themenvorlage erstellen beim Erstellen einer Zuordnung aus der Zuordnungsvorlage keine Kopie im Inhaltsordner. 12150)
- Das Suchfeld in DITA-Karten verfügt über keine Schaltfläche zum Schließen. 11867)
- Beim Speichern langer Dateien im Web-Editor löst `DirtyChecker` eine Ausnahme mit einer langen Stapelablaufverfolgung aus und füllt die Protokolldateien. 11860)
- Zum Erstellen von DITA-Themen ist die Berechtigung Löschen für den entsprechenden Ordnerknoten erforderlich, obwohl die Zuordnung mit der Schreibberechtigung erstellt werden kann. 11706)
- Im Web-Editor wird ein falscher Titel angezeigt, wenn ein Schrägstrich vorhanden ist. 10949)


### Verwaltung

- Das Feld „Titel“ in den Metadateneigenschaften der DITA-Zuordnung wird durch `<title>` -Element für die Zuordnung überschrieben. 10702)
- Inhaltsreferenz ist fehlerhaft. Kopieren Sie DITA-Dateien, und fügen Sie sie ein, wenn die Themen-ID nicht mit der GUID übereinstimmt. 12614)
- Bei dynamischen Baselines wird die Beschriftungsliste nicht aus den direkten Referenzen der Arbeitskopie einer DITA-Zuordnung abgerufen. 11917)

### Publishing

- Die Veröffentlichung schlägt beim Umbenennen einer nativen PDF-Vorgabe fehl. 12564)
- Das Duplizieren einer nativen PDF-Vorlage wird am Standardvorlagenspeicherort anstelle des bereitgestellten benutzerdefinierten Vorlagenspeicherorts dupliziert. 12563)

- Native PDF | Das Einschließen mehrerer XRefs erweitert den Text über die Spaltenbreite hinaus. 13004)
- Native PDF | Wenn Thema und Titel dieselbe ID haben, führt dies zu einer fehlerhaften Generierung der PDF-Ausgabe. 12644)
- Native PDF | Beim Hinzufügen einer Output-Klasse zu einem übergeordneten `<topicref>` in einer DITA-Zuordnung und beim Anwenden eines benutzerdefinierten Stils auf die Output-Klasse wird der Stil auf Elemente innerhalb des Themenkörpers angewendet, einschließlich Abschnittstiteln.12166)
- Die inkrementelle Veröffentlichung funktioniert nicht, wenn eine DITA-Zuordnung mehrere ditavalrefs enthält. 12117)
- AEM Site | Beim Erstellen einer Zuordnung mit keydef, die auf ein Thema als Variable verweist, und beim Hinzufügen von processing-role=resource-only werden einige unerwartete Seiten erstellt. 12099)
- Wenn Assets aus dem DAM von AEM in einer anderen Ausgabe als der AEM-Site verwendet werden, spiegeln die Metadaten „jcr:createdBy&quot; weder den Namen des Herausgebers noch den Namen des Benutzers wider, der die DITA-Zuordnung oder das Thema zuletzt geändert hat. 12090)
- AEM Sites | DITA-Map mit topichead im navtitle (mit nicht unterstützten Zeichen) führt zu fehlerhaften Seiten-URLs. 11978)
- Native PDF | Probleme treten bei der Unterstützung von topichead / topicmeta / navtitle in Frontmatter und Backmatter auf. 11969)
- Native PDF | Das Generieren von PDFs für große Dokumente ist zeitaufwendig. 11955)
- Native PDF | Beim Umbenennen einer Vorgabe wird beim Generieren einer PDF-Ausgabe eine NullPointerException ausgelöst. 11889)
- Der `<conref>` Inhalt wird nicht in der PDF-Ausgabe angezeigt. 11131)
- In den `<div>` wird beim Umschalten zwischen der Authoring- und der Source-Ansicht im Seitenlayout-Editor ein zusätzlicher Leerraum hinzugefügt. 10750)
- Der auf AEM Cloud Manager replizierte Inhalt ist auf der Veröffentlichungsinstanz nicht sichtbar. (9564)

### Übersetzung

- Der Prozess zum Exportieren einer umbenannten Baseline für eine Übersetzung schlägt fehl. 12993)
- Der Titel der übersetzten Datei wird anstelle des Titels der Quelldatei angezeigt. 11630)
