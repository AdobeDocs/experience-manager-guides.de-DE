---
title: Versionshinweise | Upgrade-Anweisungen und behobene Probleme in Adobe Experience Manager Guides, Version 2024.06.0
description: Erfahren Sie mehr über die Kompatibilitätsmatrix und wie Sie auf die Version 2024.06.0 von Adobe Experience Manager Guides as a Cloud Service aktualisieren.
exl-id: 6895357a-cfd1-4e6a-aec1-8870db8054fb
source-git-commit: d525775afeeb89754762ff514126b1c3a3307b3f
workflow-type: tm+mt
source-wordcount: '1019'
ht-degree: 4%

---

# Upgrade-Anweisungen für die Version 2024.06.0

In diesem Artikel werden die Upgrade-Anweisungen und die Kompatibilitätsmatrix für die Version 2024.06.0 von Adobe Experience Manager Guides as a Cloud Service beschrieben.

Weitere Informationen zu den neuen Funktionen und Verbesserungen finden Sie unter [Neue Funktionen in Version 2024.06.0](whats-new-2024-06-0.md).

Eine Liste der in dieser Version behobenen Probleme finden Sie im Artikel [Behobene Probleme in Version 2024.06.0](fixed-issues-2024-06-0.md).

## Kompatibilitätsmatrix

In diesem Abschnitt wird die Kompatibilitätsmatrix für die Softwareanwendungen aufgelistet, die von der Experience Manager Guides-as a Cloud Services-Version 2024.06.0 unterstützt werden.

### FrameMaker und FrameMaker Publishing Server

| Experience Manager Guides as a Cloud-Version | FMPS | FrameMaker |
| --- | --- | --- |
| 2024,06,0 | Nicht kompatibel | 2022 oder höher |
| | | |


### Sauerstoffanschluss

| Experience Manager Guides as a Cloud-Version | Sauerstoff Connector Windows | Sauerstoff Connector Mac | In Oxygen Windows bearbeiten | In Oxygen Mac bearbeiten |
| --- | --- | --- | --- | --- |
| 2024,06,0 | 3.5-uuid 1 | 3.5-uuid 1 | 2,3 | 2,3 |
|  |  |  |  |


### Knowledgebase-Vorlagenversion

| Name des Komponentenpakets | Komponentenversion | Vorlagenversion |
|---|---|---|
| Experience Manager Guides Components Content Package for Cloud Service | dxml-components.all-1.2.2 | aem-site-template-dxml.all-1.0.16 |

## Aktualisierung auf Version 2024.06.0

Experience Manager Guides wird beim Upgrade der aktuellen (aktuellen) Version von Experience Manager as a Cloud Service automatisch aktualisiert.

>[!NOTE]
>
> Sobald Sie mit der Verwendung der aktuellen (neuesten) Version beginnen, vergleichen Sie alle überschriebenen Konfigurationen mit den neuesten, um die neuesten Funktionen zu erhalten:
>- ui_config.json (möglicherweise in Ordnerprofilen festgelegt)


Führen Sie die folgenden Schritte für Experience Manager Guides as a Cloud Service aus, wenn Sie es für Ihre bestehende Version noch nicht getan haben:

### Schritte zum Aktivieren des Triggers eines Skripts über ein Servlet

(Nur wenn Sie eine Version vor der Experience Manager Guides as a Cloud Service-Version vom Juni 2023 haben)

Nachdem Sie die Installation abgeschlossen haben, können Sie den Trigger drücken, um den Übersetzungsauftrag zu starten:

POST:

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

In der vorherigen Antwort-JSON enthält der Schlüssel `lockNodePath` den Pfad zum Knoten, der im Repository erstellt wurde und auf den gesendeten Auftrag verweist. Er wird automatisch gelöscht, sobald der Auftrag abgeschlossen ist. In diesem Knoten können Sie den Status des Auftrags nachlesen.

Warten Sie, bis dieser Auftrag abgeschlossen ist, bevor Sie mit den nächsten Schritten fortfahren.

>[!NOTE]
>
> Sie sollten überprüfen, ob der Knoten noch vorhanden ist, und den Status des Auftrags überprüfen.

```
GET
http://<aem_domain>/var/dxml/executor-locks/translation-map-upgrade/1683190032886.json
```

### Schritte zum Nachbearbeiten des vorhandenen Inhalts zur Verwendung des Berichts über einen fehlerhaften Link

(Nur wenn Sie eine Version vor der Experience Manager Guides as a Cloud Service-Version vom Juni 2023 haben)

Führen Sie die folgenden Schritte für die Nachbearbeitung des vorhandenen Inhalts und die Verwendung des neuen Berichts über fehlerhafte Links aus:

1. (Optional) Wenn mehr als 100.000 DITA-Dateien im System vorhanden sind, aktualisieren Sie die `queryLimitReads` und `queryLimitInMemory` unter `org.apache.jackrabbit.oak.query.QueryEngineSettingsService` auf einen größeren Wert (ein beliebiger Wert, der größer ist als die Anzahl der vorhandenen Assets, z. B. 200.000), und stellen Sie dann erneut bereit.

   - Verwenden Sie die Anweisungen im Abschnitt *Konfigurationsüberschreibungen* unter Installieren und Konfigurieren von Adobe Experience Manager Guides as a Cloud Service , um die Konfigurationsdatei zu erstellen.
   - Geben Sie in der Konfigurationsdatei die folgenden (Eigenschaft-)Details an, um die Optionen `queryLimitReads` und `queryLimitInMemory` zu konfigurieren:

     | PID | Eigenschaftenschlüssel | Eigenschaftswert |
     |---|---|---|
     | org.apache.jackrabbit.oak.query.QueryEngineSettingsService | queryLimitReads | Wert: 200000 Standardwert: 100000 |
     | org.apache.jackrabbit.oak.query.QueryEngineSettingsService | queryLimitInMemory | Wert: 200000 Standardwert: 100000 |

1. Führen Sie eine POST-Anfrage an den Server aus (mit der richtigen Authentifizierung) - `http://<server>//bin/guides/reports/upgrade`.

1. Die API gibt eine jobId zurück. Um den Status des Auftrags zu überprüfen, können Sie eine GET-Anfrage mit Auftrags-ID an denselben Endpunkt senden - `http://<server>/bin/guides/reports/upgrade?jobId= {jobId}`
(Beispiel: `http://localhost:8080/bin/guides/reports/upgrade?jobId=2022/9/15/7/27/7dfa1271-981e-4617-b5a4-c18379f11c42_678`)

1. Nach Abschluss des Auftrags antwortet die vorherige GET-Anfrage erfolgreich. Wenn der Auftrag aus irgendeinem Grund fehlschlägt, kann der Fehler in den Serverprotokollen angezeigt werden.

1. Kehren Sie zurück zum standardmäßigen oder vorherigen vorhandenen Wert von `queryLimitReads` zurück, wenn Sie ihn in Schritt 1 geändert haben.

### Schritte zum Indexieren des vorhandenen Inhalts zur Verwendung der neuen Suchen- und Ersetzen- und Themenliste auf der Registerkarte Berichte :

(Nur wenn Sie eine Version vor der Experience Manager Guides as a Cloud Service-Version vom Juni 2023 haben)

Führen Sie die folgenden Schritte aus, um den vorhandenen Inhalt zu indizieren und den neuen Text auf Zuordnungs- und Themenliste auf der Registerkarte Berichte zu finden und zu ersetzen:

1. Führen Sie eine POST-Anfrage an den Server aus (mit der richtigen Authentifizierung) - `http://<server:port>/bin/guides/map-find/indexing`. (Optional: Sie können bestimmte Pfade der Maps übergeben, um sie zu indizieren. Standardmäßig sind alle Maps indiziert| Beispiel: `https://<Server:port>/bin/guides/map-find/indexing?paths=<path of the MAP in repository>`)

1. Sie können auch einen Stammordner übergeben, um die DITA-Maps eines bestimmten Ordners (und seiner Unterordner) zu indizieren. Beispiel: `http://<server:port\>/bin/guides/map-find/indexing?root=/content/dam/test`. Beachten Sie, dass nur der Pfadparameter berücksichtigt wird, wenn sowohl der Pfadparameter als auch der Stammparameter übergeben werden.

1. Die API gibt eine jobId zurück. Um den Auftragsstatus zu überprüfen, können Sie eine GET-Anfrage mit Auftrags-ID an denselben Endpunkt senden - `http://<server:port>/bin/guides/map-find/indexing?jobId={jobId}`(z. B. `http://localhost:8080/bin/guides/reports/upgrade?jobId=2022/9/15/7/27/7dfa1271-981e-4617-b5a4-c18379f11c42_678`)

1. Nach Abschluss des Auftrags antwortet die vorherige GET-Anfrage mit Erfolg und gibt an, ob Zuordnungen fehlgeschlagen sind. Die erfolgreich indizierten Maps können über Serverprotokolle bestätigt werden.

### Schritte zur Handhabung des `'fmdita rewriter'`-Konflikts

Experience Manager Guides verfügt über ein [**benutzerdefinierter Sling-Rewriter**](../cs-install-guide/conf-output-generation.md#custom-rewriter) -Modul für die Verarbeitung der im Fall von Querverweisen generierten Links (Links zwischen den Themen zweier verschiedener Maps).

Wenn Sie in Ihrer Codebasis über einen anderen benutzerdefinierten Sling-Rewriter verfügen, verwenden Sie einen `'order'` -Wert größer als 50, da der Experience Manager Guides Sling-Rewriter `'order'` 50 verwendet. Um dies zu überschreiben, benötigen Sie einen Wert > 50. Weitere Informationen finden Sie unter [Pipelines zum Neuschreiben der Ausgabe ](https://sling.apache.org/documentation/bundles/output-rewriting-pipelines-org-apache-sling-rewriter.html).

Da während dieses Upgrades der Wert `'order'` von 1000 auf 50 geändert wird, müssen Sie die vorhandene benutzerdefinierte Rewriter, falls vorhanden, mit `fmdita-rewriter` zusammenführen.



### Schritte zum Durchführen einer B-Tree-Migration für Inhaltsfragmente

Wenn für Inhaltsfragmente keine Verweise angezeigt werden, können Sie festlegen, dass auf den Trigger GEHT, um den Migrationsauftrag zu starten:

POST:

```
http://localhost:4503/bin/guides/script/start?jobType=cf-reference-store-btree-migration
```


Antwort:

```
{
"msg": "Job is successfully submitted and lock node is created for future reference",
"lockNodePath": "/var/dxml/executor-locks/cf-reference-store-btree-migration/1683190032886",
"status": "SCHEDULED"
}
```

In der vorherigen Antwort, JSON, enthält der Schlüssel `lockNodePath` den Pfad zum Knoten, der im Repository erstellt wurde und auf den gesendeten Auftrag verweist. Er wird automatisch gelöscht, sobald der Auftrag abgeschlossen ist. Sie können den Status des Auftrags in diesem Knoten nachlesen.

Warten Sie, bis dieser Auftrag abgeschlossen ist, bevor Sie mit den nächsten Schritten fortfahren.

>[!NOTE]
>
>Sie sollten überprüfen, ob der Knoten noch vorhanden ist, und den Status des Auftrags überprüfen.

GET:

```
http://<aem_domain>/var/dxml/executor-locks/cf-reference-store-btree-migration/1683190032886.json
```
