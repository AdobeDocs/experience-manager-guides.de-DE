---
title: Versionshinweise zu | Aktualisierungsanweisungen und behobene Probleme in Adobe Experience Manager Guides, Version vom November 2023
description: Erfahren Sie mehr über die Fehlerbehebungen und das Upgrade auf die Version vom November 2023 von Adobe Experience Manager Guides as a Cloud Service
exl-id: 80839890-075f-4187-a167-444c73215496
feature: Release Notes
role: Leader
source-git-commit: 6e23f52fc9124d0f07f8108da1b5fe574f553469
workflow-type: tm+mt
source-wordcount: '1673'
ht-degree: 1%

---

# Version vom November 2023 von Adobe Experience Manager Guides as a Cloud Service

Diese Versionshinweise enthalten die Upgrade-Anweisungen, die Kompatibilitätsmatrix und die behobenen Probleme in Version November 2023 von Adobe Experience Manager Guides as a Cloud Service (später als *Experience Manager Guides as a Cloud Service* bezeichnet).

Weitere Informationen zu den neuen Funktionen und Verbesserungen finden Sie unter [Neue Funktionen in der Version vom November 2023 von Experience Manager Guides as a Cloud Service](whats-new-2023-11-0.md).

## Upgrade auf Version November 2023

Führen Sie ein Upgrade Ihres aktuellen Experience Manager Guides as a Cloud Service-Setups durch, indem Sie die folgenden Schritte ausführen:

1. Checken Sie den Git-Code der Cloud Services aus und wechseln Sie zu der Verzweigung, die in der Cloud Services-Pipeline konfiguriert ist und der Umgebung entspricht, die Sie aktualisieren möchten.
2. Aktualisieren Sie `<dox.version>` Eigenschaft in `/dox/dox.installer/pom.xml` Datei Ihres Cloud Services-Git-Codes auf 2023.11.0.406.
3. Übernehmen Sie die Änderungen und führen Sie die Cloud Services-Pipeline aus, um auf die Version vom November 2023 von Experience Manager Guides as a Cloud Service zu aktualisieren.

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

In der vorherigen Antwort-JSON enthält der `lockNodePath` den Pfad zum Knoten , der im Repository erstellt wurde und auf den gesendeten Auftrag verweist. Sie wird automatisch gelöscht, sobald der Auftrag abgeschlossen ist. Sie können in diesem Knoten den Status des Auftrags abrufen.

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

1. Ausführen einer POST-Anfrage an den Server (mit korrekter Authentifizierung) - `http://<server:port>//bin/guides/reports/upgrade`.

1. Die API gibt eine jobId zurück. Um den Auftragsstatus zu überprüfen, können Sie eine GET-Anfrage mit Auftrags-ID an denselben Endpunkt senden - `http://<server:port>/bin/guides/reports/upgrade?jobId= {jobId}`
(Beispiel: `http://localhost:8080/bin/guides/map-find/indexing?jobId=2022/9/15/7/27/7dfa1271-981e-4617-b5a4-c18379f11c42_678`)

1. Sobald der Auftrag abgeschlossen ist, antwortet die vorherige GET-Anfrage erfolgreich. Wenn der Vorgang aus irgendeinem Grund fehlschlägt, kann der Fehler in den Serverprotokollen angezeigt werden.

1. Setzen Sie den Standardwert oder den vorherigen vorhandenen Wert von `queryLimitReads` zurück, wenn Sie ihn in Schritt 1 geändert haben.

## Schritte zum Indizieren des vorhandenen Inhalts, um die neue Themenliste „Suchen und Ersetzen“ auf der Registerkarte „Berichte“ zu verwenden:

(Nur bei Versionen vor der Version Juni 2023 von Experience Manager Guides as a Cloud Service)

Führen Sie die folgenden Schritte aus, um den vorhandenen Inhalt zu indizieren und den neuen Text „Suchen und Ersetzen“ auf Zuordnungsebene und in der Themenliste auf der Registerkarte „Berichte“ zu verwenden:

1. Ausführen einer POST-Anfrage an den Server (mit korrekter Authentifizierung) - `http://<server:port>/bin/guides/map-find/indexing`. (Optional) Sie können bestimmte Pfade der Karten übergeben, um sie zu indizieren. Standardmäßig werden alle Karten indiziert || Beispiel: `https://<Server:port>/bin/guides/map-find/indexing?paths=<map_path_in_repository>`)

1. Sie können auch einen Stammordner übergeben, um die DITA-Zuordnungen eines bestimmten Ordners (und seiner Unterordner) zu indizieren. Beispiel: `http://<server:port>/bin/guides/map-find/indexing?root=/content/dam/test`. Beachten Sie, dass nur der Pfadparameter berücksichtigt wird, wenn sowohl der Pfadparameter als auch der Stammparameter übergeben werden.

1. Die API gibt eine jobId zurück. Um den Auftragsstatus zu überprüfen, können Sie eine GET-Anfrage mit Auftrags-ID an denselben Endpunkt senden - `http://<server:port>/bin/guides/map-find/indexing?jobId={jobId}` (Beispiel: `http://localhost:8080/bin/guides/map-find/indexing?jobId=2022/9/15/7/27/7dfa1271-981e-4617-b5a4-c18379f11c42`)


1. Sobald der Auftrag abgeschlossen ist, antwortet die vorherige GET-Anfrage mit Erfolg und gibt an, ob Zuordnungen fehlgeschlagen sind. Die erfolgreich indizierten Zuordnungen können aus den Serverprotokollen bestätigt werden.

## Schritte zum Umgang mit dem `'fmdita rewriter'`

Experience Manager Guides verfügt über [**Modul „Benutzerdefiniertes Sling Rewriter**](../cs-install-guide/conf-output-generation.md#custom-rewriter), in dem die Links verarbeitet werden, die bei Kreuzzuordnungen (Verknüpfungen zwischen den Themen zweier verschiedener Zuordnungen) generiert werden.

Wenn Sie einen anderen benutzerdefinierten Sling Rewriter in Ihrer Codebasis haben, verwenden Sie einen `'order'` Wert größer als 50, da der Experience Manager Guides Sling Rewriter `'order'` 50 verwendet.  Um dies zu überschreiben, benötigen Sie einen Wert >50. Weitere Informationen finden Sie unter [Output-Umschreibungs-Pipelines](https://sling.apache.org/documentation/bundles/output-rewriting-pipelines-org-apache-sling-rewriter.html).

Da während dieses Upgrades der `'order'` von 1000 auf 50 geändert wird, müssen Sie den vorhandenen benutzerdefinierten Rewriter (sofern vorhanden) mit `'fmdita-rewriter'` zusammenführen.


## Kompatibilitätsmatrix

In diesem Abschnitt finden Sie die Kompatibilitätsmatrix für die Softwareanwendungen, die von Experience Manager Guides as a Cloud Service Version November 2023 unterstützt werden.

### FrameMaker und FrameMaker Publishing Server

| Experience Manager Guides Guides as a Cloud Service | FMPS | FrameMaker |
| --- | --- | --- |
| 2023.11.0 | Nicht kompatibel | 2022 oder höher |
| | | |


### Sauerstoffanschluss

| Experience Manager Guides as a Cloud Service-Version | Fenster des Sauerstoffanschlusses | Oxygen Connector Mac | In Oxygen Windows bearbeiten | In Oxygen Mac bearbeiten |
| --- | --- | --- | --- | --- |
| 2023.11.0 | 3.2-uuid 5 | 3.2-uuid 5 | 2,3 | 2,3 |
|  |  |  |  |  |


### Version der Wissensdatenbankvorlage

| Paketname der Komponenten | Komponentenversion | Vorlagenversion |
|---|---|---|
| Experience Manager Guides-Komponenten-Inhaltspaket für Cloud Service | dxml-components.all-1.2.2 | aem-site-template-dxml.all-1.0.15 |

## Behobene Probleme

Die in verschiedenen Bereichen behobenen Fehler sind unten aufgeführt:



### Authoring

- Leerzeichen nach dem conref`<ph>`Element verschwindet beim Speichern des Themas. 13642)
- Anwendungsfehler tritt auf, wenn versucht wird, DITA-Dateien zu speichern, bevor die Nachbearbeitung abgeschlossen ist. 13571)
- Wenn der Titel eines Themas einen Schrägstrich `/`, werden auf der Registerkarte im Editor nur die nachfolgenden Briefe angezeigt. 13455)
- Die Bildvorschau verschwindet nicht, nachdem die Vorschau im Editor angezeigt wurde. 13454)
- Das Popup-Fenster zum Einfügen von Keywords wird nicht angezeigt, wenn in anderen Themen Schlüssel verwendet werden, die für die Stammzuordnung definiert sind. 12950)
- Schließen-Symbole werden nicht angezeigt, wenn im Bedienfeld Versionsverlauf sehr hohe Grafiken in der Vorschau angezeigt werden. 12867)
- Die Zeitzone der Spalte **Version erstellt am** für die Baselines kann nicht geändert werden. 12711)
- Das **Versionsverlauf** in der Assets-Benutzeroberfläche zeigt einen falschen Zeitstempel für das Feld **Aktuell** an. 12624)
- Das Erstellen einer DITA-Datei aus einer Vorlage mit einem Dateinamen, der mit numerischen Zeichen beginnt, führt zu einem Namespace-Fehler. 12188)
- Im Web-Editor wird das Fenster **Schlüsselverweise** beim Einfügen des `varname`-Tags geöffnet. 10940)
- Zip-Dateien werden im Web-Editor nicht erkannt und können nicht per Drag-and-Drop eingefügt werden. 12709)
- Der Inhalt mit einigen darauf angewendeten Attributen wird im Autoren- oder Vorschaumodus nicht hervorgehoben. 11063)
- Wenn Sie ein Thema nach der Bearbeitung schließen, werden Sie zur AEM-Startseite weitergeleitet, anstatt zur Ordneransicht zurückzukehren. 13306)
- Eine Verzögerung tritt bei der Nachbearbeitung von Dateien auf, die kopiert und in die Cloud-Services eingefügt wurden. 12457)
- Die Rootmap-Einstellung bleibt im Web-Editor erhalten, auch wenn sie nicht explizit in den Benutzereinstellungen festgelegt wurde. 11551)


### Publishing

- Die Funktion „Als Inhaltsfragment veröffentlichen“ funktioniert nicht für Dateien, die in Suchergebnissen aufgelistet sind. 14090)
- In der nativen PDF-Veröffentlichung erfordert die Hintergrundfarbauswahl im Vorlagen-Layout ein erneutes Laden der Seite, wenn auf `None` zurückgesetzt wird. 13621)
- Problem beim Übertragen von Daten in den Datenspeicher für eine große DITA-Zuordnung mit Umfang und Peer-Links in der AEM-Site-Veröffentlichung. 13530)
- In der nativen PDF-Veröffentlichung ist die Barrierefreiheit gefährdet, da Bilder in Kopf- und Fußzeile keinen Alternativtext anzeigen. 12829)
- Das Duplizieren des Seiten-Layouts im nativen PDF funktioniert nicht, wenn automatisch keine Erweiterung hinzugefügt wird. 12534)
- Beim Generieren der PDF-Ausgabe mit nativer PDF-Veröffentlichung wird der Dateiname nach einem Zeitraum abgeschnitten. 13620)
- In der Symbolleiste Seitenlayouts der Vorlagen, **in der nativen Veröffentlichung von PDF verwendet werden, werden für die Option Inhalt bearbeiten** ein falsches Symbol und eine falsche QuickInfo angezeigt. 13492)
- Benutzerdefinierte Metadaten sind in der endgültigen Ausgabe nicht verfügbar. 12116)
- fmdita rewriter steht in Konflikt mit der Rewriter-Konfiguration des Benutzers und führt zur Anzeige langer URLs anstelle der Links. 12076)
- In der AEM-Site-Voreinstellung ist die Option **Für jedes Thema separate PDF generieren** nicht funktionsfähig. 11555)
- Die native PDF-Veröffentlichung bietet keine Unterstützung für die CMYK-Farbraumkonvertierung. 10754)
- Dynamische Baseline-Aufrufe verwenden den Namen anstelle des Titels, was dazu führt, dass die Export-DITA-Zuordnungs-API fehlschlägt. 14268)

### Verwaltung

- Der Inhaltsverweis ist beim Kopieren und Einfügen der DITA-Dateien mit Selbstverweis-Links ohne GUID fehlerhaft. 13540)
- Im Web-Editor zeigt die Grundlinie den Titel für die vorherige Version anstelle der ausgewählten Version der DITA-Datei an. 13444)
- Die Registerkarte **Berichte** in der Benutzeroberfläche des Web-Editors zeigt nicht die Themenliste für alte DITA-Zuordnungen an, die vor dem Upgrade von Experience Manager Guides as a Cloud Service im Juli 2023 erstellt wurden. 11852)
- Bedingungsvorgaben für eine große DITA-Karte werden nicht erstellt. 10936)
- Unter der Liste der fehlerhaften Links in Berichten wird ein Selbstverweis-Link angezeigt. 13539)

### Überprüfung

- In der Experience Manager Guides as a Cloud Service-Version vom Oktober 2023 sind die Review-Bedienfelder, die im Web-Editor nebeneinander angezeigt werden, nicht korrekt. 14156)
- Die Anpassung von E **Mail-Vorlagen für** Review) funktioniert nicht, wenn sich die Knoten überlagern. 13954)
- Die Schaltfläche **Schließen** auf der Überprüfungsseite in der Experience Manager Guides bringt Benutzende zur AEM-Homepage. 13535)
- Beim Erstellen der Snippets in koreanischer Sprache werden fehlerhafte Zeichen angezeigt. 13489)
- Koreanische Anhänge im Experience Manager Guides-Überprüfungsbildschirm sind nicht anklickbar. 13436)
- Der Map-Titel wird im Bildschirm Überprüfung und Zusammenarbeit abgeschnitten, ohne Option zum Anzeigen des vollständigen Titels. 13012)

### Übersetzung

- Die automatische Genehmigung funktioniert manchmal nicht und es treten Ausnahmen auf, wenn ein falscher Wert für „Übersetzungsstatus **festgelegt**. 13607)
- Die vom Übersetzungs-Dashboard exportierte Baseline schlägt fehl und wird nicht in der Zielsprache geöffnet. 12993)

## Bekanntes Problem

Adobe hat das folgende bekannte Problem für die Version vom November 2023 identifiziert.

- Die selektive Themenregenerierung für die AEM-Site-Ausgabe schlägt fehl.
