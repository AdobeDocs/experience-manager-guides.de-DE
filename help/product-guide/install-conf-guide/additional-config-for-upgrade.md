---
title: Zusätzliche Konfiguration für das Upgrade von Cloud Service
description: Erfahren Sie mehr über die zusätzliche Konfiguration zum Aktualisieren von Cloud Service
source-git-commit: 453da51a42984b912547570f2e1de70806b41171
workflow-type: tm+mt
source-wordcount: '849'
ht-degree: 0%

---

# Zusätzliche Konfiguration für das Upgrade von AEM Guides as a Cloud Service

>[!INFO]
>
>Dieser Artikel gilt, wenn Sie benutzerdefinierte Ordnerprofileinstellungen (`ui_config.json`) konfiguriert haben. Überprüfen und ändern Sie nach jedem Upgrade Ihre Einstellungen nach Bedarf, um die Kompatibilität mit den neuesten Änderungen sicherzustellen.

Je nach der Version, von der Sie ein Upgrade durchführen, sind möglicherweise zusätzliche Konfigurationsschritte erforderlich, um Änderungen zu integrieren, die in neueren Cloud Service-Versionen eingeführt wurden.

Einige Konfigurationen gelten nur für bestimmte Versionen. Stellen Sie sicher, dass Sie die Konfigurationsabschnitte unten lesen und die für Ihr Setup erforderlichen Konfigurationen anwenden.

## Schritte zum Anwenden von Suchfiltern auf DITAVAL-Dateien für alle Ausgabevorgaben

Um sicherzustellen, dass die Filter ordnungsgemäß funktionieren, aktualisieren Sie ui_config.json. Ändern Sie die unter **browseFilters** > **Nicht-DITA-Dateien** > **Ditaval-Dateien** aufgelisteten Eigenschaften wie unten dargestellt:

```
{
  "title": "Ditaval Files",
  "property": "LOWER_NAME",
  "operation": "like",
  "value": ".ditaval"
}
```

## Schritte zur Durchführung der B-Tree-Migration für Inhaltsfragmente

Wenn keine Verweise für Inhaltsfragmente angezeigt werden, können Sie den Migrationsvorgang ausführen:

BEITRAG:

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

In der vorherigen Antwort, JSON, enthält der `lockNodePath` den Pfad zu dem im Repository erstellten Knoten, der auf den gesendeten Auftrag verweist. Sie wird automatisch gelöscht, sobald der Vorgang abgeschlossen ist. Sie können auf diesem Knoten nach dem Status des Auftrags suchen.

Warten Sie, bis dieser Vorgang abgeschlossen ist, bevor Sie mit den nächsten Schritten fortfahren.

>[!NOTE]
>
>Überprüfen Sie, ob der Knoten noch vorhanden ist, und den Status des Auftrags.

GET:

```
http://<aem_domain>/var/dxml/executor-locks/cf-reference-store-btree-migration/1683190032886.json
```

## Schritte zum Umgang mit dem `'fmdita rewriter'`

Experience Manager Guides verfügt über [**Modul „Benutzerdefiniertes Sling Rewriter**](../install-conf-guide/conf-output-generation.md#custom-rewriter), in dem die Links verarbeitet werden, die bei Kreuzzuordnungen (Verknüpfungen zwischen den Themen zweier verschiedener Zuordnungen) generiert werden.

Wenn Sie einen anderen benutzerdefinierten Sling Rewriter in Ihrer Codebasis haben, verwenden Sie einen `'order'` Wert größer als 50, da der Experience Manager Guides Sling Rewriter `'order'` 50 verwendet. Um dies zu überschreiben, benötigen Sie einen Wert >50. Weitere Informationen finden Sie unter [Output-Umschreibungs-Pipelines](https://sling.apache.org/documentation/bundles/output-rewriting-pipelines-org-apache-sling-rewriter.html).

Da während dieses Upgrades der `'order'` von 1000 auf 50 geändert wird, müssen Sie den vorhandenen benutzerdefinierten Rewriter (sofern vorhanden) mit `fmdita-rewriter` zusammenführen.

## Konfigurationen, die für Versionen vor Juni 2023 gelten

Die folgenden Konfigurationen sind nur erforderlich, wenn Sie eine Version von Experience Manager Guides as a Cloud Service verwenden, die vor Juni 2023 veröffentlicht wurde. Erweitern Sie die folgenden relevanten Abschnitte, um die erforderlichen Einstellungen anzuwenden und die Kompatibilität mit erforderlichen Aktualisierungen sicherzustellen.

+++Schritte zum Indizieren des vorhandenen Inhalts, um die neue Themenliste „Suchen und Ersetzen“ auf der Registerkarte „Berichte“ zu verwenden
Führen Sie die folgenden Schritte aus, um den vorhandenen Inhalt zu indizieren und den neuen Text „Suchen und Ersetzen“ auf Zuordnungsebene und in der Themenliste auf der Registerkarte „Berichte“ zu verwenden:

1. Ausführen einer POST-Anfrage an den Server (mit korrekter Authentifizierung) - `http://<server:port>/bin/guides/map-find/indexing`. (Optional: Sie können bestimmte Pfade der Zuordnungen übergeben, um sie zu indizieren. Standardmäßig sind alle Zuordnungen indiziert.|| Beispiel: `https://<Server:port>/bin/guides/map-find/indexing?paths=<path of the MAP in repository>`)

1. Sie können auch einen Stammordner übergeben, um die DITA-Zuordnungen eines bestimmten Ordners (und seiner Unterordner) zu indizieren. Beispiel: `http://<server:port\>/bin/guides/map-find/indexing?root=/content/dam/test`. Beachten Sie, dass nur der Pfadparameter berücksichtigt wird, wenn sowohl der Pfadparameter als auch der Stammparameter übergeben werden.

1. Die API gibt eine jobId zurück. Um den Auftragsstatus zu überprüfen, können Sie eine GET-Anfrage mit Auftrags-ID an denselben Endpunkt senden - `http://<server:port>/bin/guides/map-find/indexing?jobId={jobId}` (Beispiel: `http://localhost:8080/bin/guides/reports/upgrade?jobId=2022/9/15/7/27/7dfa1271-981e-4617-b5a4-c18379f11c42_678`)

1. Sobald der Auftrag abgeschlossen ist, antwortet die vorherige GET-Anfrage mit Erfolg und gibt an, ob Zuordnungen fehlgeschlagen sind. Die erfolgreich indizierten Zuordnungen können über Serverprotokolle bestätigt werden.

+++

+++Schritte zur Nachbearbeitung des vorhandenen Inhalts, um den Bericht über fehlerhafte Links zu verwenden 
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

1. Kehren Sie zum Standardwert oder vorherigen vorhandenen Wert von `queryLimitReads` zurück, wenn Sie ihn in Schritt 1 geändert haben.

+++

+++Schritte zum Aktivieren des Triggers eines Skripts über ein Servlet
Nach Abschluss der Installation können Sie den Übersetzungsauftrag starten:

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

In der vorherigen Antwort-JSON enthält der `lockNodePath` den Pfad zum Knoten , der im Repository erstellt wurde und auf den gesendeten Auftrag verweist. Er wird automatisch gelöscht, sobald der Auftrag abgeschlossen ist, und Sie können in diesem Knoten den Status des Auftrags abrufen.

Warten Sie, bis dieser Vorgang abgeschlossen ist, bevor Sie mit den nächsten Schritten fortfahren.

>[!NOTE]
>
> Überprüfen Sie, ob der Knoten noch vorhanden ist, und den Status des Auftrags.

```
GET
http://<aem_domain>/var/dxml/executor-locks/translation-map-upgrade/1683190032886.json
```

+++
