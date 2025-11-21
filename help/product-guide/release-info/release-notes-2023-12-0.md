---
title: Versionshinweise zu | Upgrade-Anweisungen und behobene Probleme in Adobe Experience Manager Guides, Version Dezember 2023
description: Erfahren Sie mehr über die Fehlerbehebungen und das Upgrade auf die Version Dezember 2023 von Adobe Experience Manager Guides as a Cloud Service.
feature: Release Notes
role: Leader
exl-id: 63efe42a-b817-49df-8f76-df8d7acf9194
source-git-commit: 6e23f52fc9124d0f07f8108da1b5fe574f553469
workflow-type: tm+mt
source-wordcount: '1319'
ht-degree: 1%

---

# Version Dezember 2023 von Adobe Experience Manager Guides as a Cloud Service

Diese Versionshinweise enthalten die Upgrade-Anweisungen, die Kompatibilitätsmatrix und behobene Probleme in Version Dezember 2023 von Adobe Experience Manager Guides as a Cloud Service (später als *Experience Manager Guides as a Cloud Service* bezeichnet).

Weitere Informationen zu den neuen Funktionen und Verbesserungen finden Sie unter [Neue Funktionen in der Experience Manager Guides as a Cloud Service-Version vom Dezember 2023](whats-new-2023-12-0.md).

## Upgrade auf Version Dezember 2023

Führen Sie ein Upgrade Ihres aktuellen Experience Manager Guides as a Cloud Service-Setups durch, indem Sie die folgenden Schritte ausführen:

1. Checken Sie den Git-Code der Cloud Services aus und wechseln Sie zu der Verzweigung, die in der Cloud Services-Pipeline konfiguriert ist und der Umgebung entspricht, die Sie aktualisieren möchten.
2. Aktualisieren Sie `<dox.version>` Eigenschaft in `/dox/dox.installer/pom.xml` Datei Ihres Cloud Services-Git-Codes auf 2023.12.0.16.
3. Übernehmen Sie die Änderungen und führen Sie die Cloud Services-Pipeline aus, um auf die Version Dezember 2023 von Experience Manager Guides as a Cloud Service zu aktualisieren.

## Schritte zum Aktivieren des Triggers eines Skripts über ein Servlet

(Nur bei Versionen vor der Version Juni 2023 von Experience Manager Guides as a Cloud Service)

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

In der vorherigen Antwort-JSON enthält der `lockNodePath` den Pfad zum Knoten , der im Repository erstellt wurde und auf den gesendeten Auftrag verweist. Sie wird automatisch gelöscht, sobald der Auftrag abgeschlossen ist, und Sie können in diesem Knoten den Status des Auftrags abrufen.

Warten Sie, bis dieser Vorgang abgeschlossen ist, bevor Sie mit den nächsten Schritten fortfahren.

>[!NOTE]
>
> Überprüfen Sie, ob der Knoten noch vorhanden ist, und den Status des Auftrags.

```
GET
http://<aem_domain>/var/dxml/executor-locks/translation-map-upgrade/1683190032886.json
```

## Schritte zur Nachbearbeitung des vorhandenen Inhalts, um den Bericht über fehlerhafte Links zu verwenden

(Nur bei Versionen vor der Version Juni 2023 von Experience Manager Guides as a Cloud Service)

Führen Sie die folgenden Schritte aus, um den vorhandenen Inhalt nachzuverarbeiten und den neuen Bericht „Beschädigter Link“ zu verwenden:

1. (Optional) Wenn mehr als 100.000 DITA-Dateien im System vorhanden sind, aktualisieren Sie die `queryLimitReads` und `queryLimitInMemory` unter `org.apache.jackrabbit.oak.query.QueryEngineSettingsService` auf einen größeren Wert (einen beliebigen Wert, der größer ist als die Anzahl der vorhandenen Assets, z. B. 200.000) und stellen Sie dann erneut bereit.

   - Verwenden Sie die Anweisungen im Abschnitt *Konfigurationsüberschreibungen* unter Installieren und Konfigurieren von Adobe Experience Manager Guides as a Cloud Service , um die Konfigurationsdatei zu erstellen.
   - Geben Sie in der Konfigurationsdatei die folgenden Details (Eigenschaft) zum Konfigurieren der `queryLimitReads`- und `queryLimitInMemory` an:

     | PID | Eigenschaftsschlüssel | Eigenschaftswert |
     |---|---|---|
     | org.apache.jackrabbit.oak.query.QueryEngineSettingsService | queryLimitReads | Wert: 200000 Standardwert: 100000 |
     | org.apache.jackrabbit.oak.query.QueryEngineSettingsService | queryLimitInMemory | Wert: 200000 Standardwert: 100000 |

1. Ausführen einer POST-Anfrage an den Server (mit korrekter Authentifizierung) - `http://<server>//bin/guides/reports/upgrade`.

1. Die API gibt eine jobId zurück. Um den Auftragsstatus zu überprüfen, können Sie eine GET-Anfrage mit Auftrags-ID an denselben Endpunkt senden - `http://<server>/bin/guides/reports/upgrade?jobId= {jobId}`
(Beispiel: `http://localhost:8080/bin/guides/reports/upgrade?jobId=2022/9/15/7/27/7dfa1271-981e-4617-b5a4-c18379f11c42_678`)

1. Sobald der Auftrag abgeschlossen ist, antwortet die vorherige GET-Anfrage erfolgreich. Wenn der Vorgang aus irgendeinem Grund fehlschlägt, kann der Fehler in den Serverprotokollen angezeigt werden.

1. Setzen Sie den Standardwert oder den vorherigen vorhandenen Wert von `queryLimitReads` zurück, wenn Sie ihn in Schritt 1 geändert haben.

## Schritte zum Indizieren des vorhandenen Inhalts, um die neue Themenliste „Suchen und Ersetzen“ auf der Registerkarte „Berichte“ zu verwenden:

(Nur bei Versionen vor der Version Juni 2023 von Experience Manager Guides as a Cloud Service)

Führen Sie die folgenden Schritte aus, um den vorhandenen Inhalt zu indizieren und den neuen Text „Suchen und Ersetzen“ auf Zuordnungsebene und in der Themenliste auf der Registerkarte „Berichte“ zu verwenden:

1. Ausführen einer POST-Anfrage an den Server (mit korrekter Authentifizierung) - `http://<server:port>/bin/guides/map-find/indexing`. (Optional: Sie können bestimmte Pfade der Zuordnungen übergeben, um sie zu indizieren. Standardmäßig werden alle Zuordnungen indiziert.|| Beispiel: `https://<Server:port>/bin/guides/map-find/indexing?paths=<map_path_in_repository>`)

1. Sie können auch einen Stammordner übergeben, um die DITA-Zuordnungen eines bestimmten Ordners (und seiner Unterordner) zu indizieren. Beispiel: `http://<server:port>/bin/guides/map-find/indexing?root=/content/dam/test`. Beachten Sie, dass nur der Pfadparameter berücksichtigt wird, wenn sowohl der Pfadparameter als auch der Stammparameter übergeben werden.

1. Die API gibt eine jobId zurück. Um den Auftragsstatus zu überprüfen, können Sie eine GET-Anfrage mit Auftrags-ID an denselben Endpunkt senden - `http://<server:port>/bin/guides/map-find/indexing?jobId={jobId}` (Beispiel: `http://localhost:8080/bin/guides/map-find/indexing?jobId=2022/9/15/7/27/7dfa1271-981e-4617-b5a4-c18379f11c42_678`)


1. Sobald der Auftrag abgeschlossen ist, antwortet die vorherige GET-Anfrage mit Erfolg und gibt an, ob Zuordnungen fehlgeschlagen sind. Die erfolgreich indizierten Zuordnungen können aus den Serverprotokollen bestätigt werden.

## Schritte zum Umgang mit dem `'fmdita rewriter'`

Experience Manager Guides verfügt über [**Modul „Benutzerdefiniertes Sling Rewriter**](../cs-install-guide/conf-output-generation.md#custom-rewriter), in dem die Links verarbeitet werden, die bei Kreuzzuordnungen (Verknüpfungen zwischen den Themen zweier verschiedener Zuordnungen) generiert werden.

Wenn Sie einen anderen benutzerdefinierten Sling Rewriter in Ihrer Codebasis haben, verwenden Sie einen `'order'` Wert größer als 50, da der Experience Manager Guides Sling Rewriter `'order'` 50 verwendet.  Um dies zu überschreiben, benötigen Sie einen Wert >50. Weitere Informationen finden Sie unter [Output-Umschreibungs-Pipelines](https://sling.apache.org/documentation/bundles/output-rewriting-pipelines-org-apache-sling-rewriter.html).

Da während dieses Upgrades der `'order'` von 1000 auf 50 geändert wird, müssen Sie den vorhandenen benutzerdefinierten Rewriter (sofern vorhanden) mit `'fmdita-rewriter'` zusammenführen.


## Kompatibilitätsmatrix

In diesem Abschnitt finden Sie die Kompatibilitätsmatrix für die Softwareanwendungen, die von Experience Manager Guides as a Cloud Service Version Dezember 2023 unterstützt werden.

### FrameMaker und FrameMaker Publishing Server

| Experience Manager Guides as a Cloud Service-Version | FMPS | FrameMaker |
| --- | --- | --- |
| 2023.12.0 | Nicht kompatibel | 2022 oder höher |
| | | |


### Sauerstoffanschluss

| Experience Manager Guides as a Cloud Service-Version | Fenster des Sauerstoffanschlusses | Oxygen Connector Mac | In Oxygen Windows bearbeiten | In Oxygen Mac bearbeiten |
| --- | --- | --- | --- | --- |
| 2023.12.0 | 3.3-uuid.5 | 3.3-uuid.5 | 2,3 | 2,3 |
|  |  |  |  |  |


### Version der Wissensdatenbankvorlage

| Paketname der Komponenten | Komponentenversion | Vorlagenversion |
|---|---|---|
| Experience Manager Guides-Komponenten-Inhaltspaket für Cloud Service | dxml-components.all-1.2.2 | aem-site-template-dxml.all-1.0.15 |

## Behobene Probleme

Die in verschiedenen Bereichen behobenen Fehler sind unten aufgeführt:



### Authoring

- Der **Titel** auf der Registerkarte „Web-Editor“ wird nach einem Punkt (.) abgeschnitten. 14372)
- Die Fehlermeldung für doppelte Zuordnungsnamen in der Assets-Benutzeroberfläche wird nicht aktualisiert. 14320)
- Bei der Versionserstellungslogik tritt während des Drag-and-Drop von Assets ein Fehler auf. 14291)
- Wiederverwendbarer Inhalt überspringt die Element-IDs. 14213)
- Das Einstellungssteuerelement zum Ausblenden des **Sprachvariablen** Bedienfelds auf **Ausgabe**-Registerkarte fehlt. 14194)
- Der Web-Editor gibt Anwendungsfehler aus, wenn ein neuer Verweis oder ein neues Thema mit einem speziellen Schema in der Layout-Ansicht hinzugefügt wird. 14094)
- Ein Ankerlink zu `<dlentry>` oder `<dt>` Element zeigt den Link-Text nicht an. 13543)
- Die **Favoriten**-Sammlung im Web-Editor kann nicht geladen werden. 13495)
- Zitate zeigen nicht anklickbare Links an, wenn sie mit einer eindeutigen ID mit Leerzeichen erstellt wurden. 13447)
- In der **Layout**-Ansicht für eine Bookmap funktioniert die Verwendung von **Nach rechts verschieben**, um ein ausgewähltes Kapitel zu einem Unterelement zu machen, nicht. 12567)
- Das Vorschaufenster des XML-Editors ist in den Browsern Google Chrome und Microsoft Edge abgeschnitten. 10755)
- Dem Web-Editor fehlt die Fähigkeit, ein Element in die möglichen übergeordneten Elemente einzuschließen. (8791)

### Publishing

- FMDITA-Komponenten haben einen hartcodierten Pfad von `delegator.jsp`, der die Überlagerung von AEM Sites-Komponenten verhindert. 13993)
- Die getaggte Ansicht von PDF Reactor in der nativen PDF-Veröffentlichungsausgabe funktioniert nicht wie erwartet. 13622)
- Bei der AEM-Site-Veröffentlichung tritt beim Übertragen großer Zuordnungen mit Umfang und Peer-Links auf den Datenspeicher ein Problem auf. 13531)
- Eine Site kann nicht über das Dashboard für die Massenveröffentlichung in Experience Manager Guides aktiviert werden. 13439)
- Die Lokalisierung der Elementbeschriftungen funktioniert in der AEM Sites-Ausgabe nicht ordnungsgemäß. 12144)
- Fehlende Option **ditaval** in den über die Benutzeroberfläche des Web-Editors erstellten Ausgabevorgaben auf Ordnerprofilebene. 11903)

### Verwaltung

- In AEM-Cloud-Umgebungen tritt aufgrund großer Knoten eine MongoWrite-Ausnahme auf. 13509)

### Übersetzung

- Die Schaltflächen **Akzeptieren/Ablehnen** werden fälschlicherweise für die automatisch genehmigte menschliche Übersetzung angezeigt. 14318)
- Bei der Umwandlung nichtenglischer DITA-Dateien in AEM-Seiten treten Internationalisierungsprobleme (i18n) auf. 14286)
- Übersetzte Inhalte können nicht mit temporären Übersetzungsprojekten synchronisiert werden, und der DITA XML Editor-Übersetzungs-Assistent zeigt fälschlicherweise den Status **In Bearbeitung** für genehmigte Aufträge an. (9938)

### Barrierefreiheit

- Die Navigation durch die Benutzeroberfläche der Authoring-Arbeitsfläche ist nicht möglich, da der Fokus im Themen-Editor gefangen ist. 13517)

## Bekanntes Problem

Adobe hat das folgende bekannte Problem für die Version vom Dezember 2023 identifiziert:
- „Getting Invalid DTD Error“ tritt gelegentlich beim Upgrade auf die Version Dezember 2023 auf.
