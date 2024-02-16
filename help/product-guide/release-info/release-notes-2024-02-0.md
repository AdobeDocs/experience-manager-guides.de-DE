---
title: Versionshinweise | Aktualisierungsanweisungen und behobene Probleme in der Adobe Experience Manager-Version vom Februar 2024
description: Erfahren Sie mehr über die Fehlerbehebungen und wie Sie auf die Version von Adobe Experience Manager Guides vom Februar 2024 as a Cloud Service aktualisieren können.
source-git-commit: 6d8c01f20f7b59fed92c404561b647d9ebecb050
workflow-type: tm+mt
source-wordcount: '1311'
ht-degree: 1%

---

# Version der Adobe Experience Manager-Handbücher as a Cloud Service im Februar 2024

In diesem Versionshinweis werden die Upgrade-Anweisungen, die Kompatibilitätsmatrix und die in Version Februar 2024 der Adobe Experience Manager-Handbücher as a Cloud Service behobenen Probleme behandelt (später als *Experience Manager Guides as a Cloud Service*).

Weitere Informationen zu den neuen Funktionen und Verbesserungen finden Sie unter [Neue Funktionen in der Version von Experience Manager Guides as a Cloud Service vom Februar 2024](whats-new-2024-02-0.md).

## Aktualisierung auf Version Februar 2024

Führen Sie die folgenden Schritte aus, um die aktuelle as a Cloud Service Einrichtung der Experience Manager-Handbücher zu aktualisieren:

1. Sehen Sie sich den Git-Code des Cloud Service an und wechseln Sie zu der Verzweigung, die in der Cloud Service-Pipeline entsprechend der Umgebung konfiguriert ist, die Sie aktualisieren möchten.
2. Aktualisieren `<dox.version>` -Eigenschaft in `/dox/dox.installer/pom.xml` -Datei Ihres Cloud Service-Git-Codes auf 2024.02.0.15.
3. Übertragen Sie die Änderungen und führen Sie die Cloud Service-Pipeline aus, um auf die Experience Manager-Handbücher as a Cloud Service vom Februar 2024 zu aktualisieren.

## Schritte zum Aktivieren des Triggers eines Skripts über ein Servlet

(Nur wenn Sie eine Version vor der Version von Experience Manager Guides im Juni 2023 as a Cloud Service haben)

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

In der vorherigen Antwort JSON, der Schlüssel `lockNodePath` enthält den Pfad zum Knoten, der im Repository erstellt wurde und auf den gesendeten Auftrag verweist. Sobald der Auftrag abgeschlossen ist, wird er automatisch gelöscht. In diesem Knoten können Sie den Status des Auftrags nachlesen.

Warten Sie, bis dieser Auftrag abgeschlossen ist, bevor Sie mit den nächsten Schritten fortfahren.

>[!NOTE]
>
> Sie sollten überprüfen, ob der Knoten noch vorhanden ist, und den Status des Auftrags überprüfen.

```
GET
http://<aem_domain>/var/dxml/executor-locks/translation-map-upgrade/1683190032886.json
```

## Schritte zum Nachbearbeiten des vorhandenen Inhalts zur Verwendung des Berichts über einen fehlerhaften Link

(Nur wenn Sie eine Version vor der Version von Experience Manager Guides im Juni 2023 as a Cloud Service haben)

Führen Sie die folgenden Schritte für die Nachbearbeitung des vorhandenen Inhalts und die Verwendung des neuen Berichts über fehlerhafte Links aus:

1. (Optional) Wenn mehr als 100.000 DITA-Dateien im System vorhanden sind, aktualisieren Sie die `queryLimitReads` und `queryLimitInMemory` under `org.apache.jackrabbit.oak.query.QueryEngineSettingsService` auf einen größeren Wert (ein Wert, der größer ist als die Anzahl der vorhandenen Assets, z. B. 200.000), und dann erneut bereitgestellt werden.

   - Verwenden Sie die im Abschnitt *Konfigurationsüberschreibungen* im Abschnitt Adobe Experience Manager-Handbücher as a Cloud Service installieren und konfigurieren , um die Konfigurationsdatei zu erstellen.
   - Geben Sie in der Konfigurationsdatei die folgenden (Eigenschaft-)Details an, um die `queryLimitReads` und `queryLimitInMemory` Option:

     | PID | Eigenschaftenschlüssel | Eigenschaftswert |
     |---|---|---|
     | org.apache.jackrabbit.oak.query.QueryEngineSettingsService | queryLimitReads | Wert: 200000 Standardwert: 100000 |
     | org.apache.jackrabbit.oak.query.QueryEngineSettingsService | queryLimitInMemory | Wert: 200000 Standardwert: 100000 |

1. Führen Sie eine POST-Anfrage an den Server aus (mit der richtigen Authentifizierung) - `http://<server>//bin/guides/reports/upgrade`.

1. Die API gibt eine jobId zurück. Um den Status des Auftrags zu überprüfen, können Sie eine GET-Anfrage mit Auftrags-ID an denselben Endpunkt senden - `http://<server>/bin/guides/reports/upgrade?jobId= {jobId}`
(Beispiel: `http://localhost:8080/bin/guides/reports/upgrade?jobId=2022/9/15/7/27/7dfa1271-981e-4617-b5a4-c18379f11c42_678`)

1. Nach Abschluss des Auftrags antwortet die vorherige GET-Anfrage erfolgreich. Wenn der Auftrag aus irgendeinem Grund fehlschlägt, kann in den Serverprotokollen ein Fehler angezeigt werden.

1. Wiederherstellen des standardmäßigen oder vorherigen vorhandenen Werts von `queryLimitReads` wenn Sie es in Schritt 1 geändert haben.

## Schritte zum Indexieren des vorhandenen Inhalts zur Verwendung der neuen Suchen- und Ersetzen- und Themenliste auf der Registerkarte Berichte :

(Nur wenn Sie eine Version vor der Version von Experience Manager Guides im Juni 2023 as a Cloud Service haben)

Führen Sie die folgenden Schritte aus, um den vorhandenen Inhalt zu indizieren und den neuen Text auf Zuordnungs- und Themenliste auf der Registerkarte Berichte zu finden und zu ersetzen:

1. Führen Sie eine POST-Anfrage an den Server aus (mit der richtigen Authentifizierung) - `http://<server:port>/bin/guides/map-find/indexing`. (Optional: Sie können bestimmte Pfade der Maps übergeben, um sie zu indizieren. Standardmäßig werden alle Maps indiziert| Beispiel: `https://<Server:port>/bin/guides/map-find/indexing?paths=<path of the MAP in repository>`)

1. Die API gibt eine jobId zurück. Um den Status des Auftrags zu überprüfen, können Sie eine GET-Anfrage mit Auftrags-ID an denselben Endpunkt senden - `http://<server:port>/bin/guides/map-find/indexing?jobId={jobId}`(Beispiel: `http://localhost:8080/bin/guides/reports/upgrade?jobId=2022/9/15/7/27/7dfa1271-981e-4617-b5a4-c18379f11c42_678`)

1. Nach Abschluss des Auftrags antwortet die vorherige GET-Anfrage erfolgreich. Wenn der Auftrag aus irgendeinem Grund fehlschlägt, kann in den Serverprotokollen ein Fehler angezeigt werden.

1. Kehren Sie zum standardmäßigen oder vorherigen vorhandenen Wert von queryLimitReads zurück, wenn Sie ihn in Schritt 1 geändert haben.

## Schritte zum Verarbeiten der `'fmdita rewriter'` Konflikt

Experience Manager-Handbücher verfügen über eine [**benutzerdefinierte Sling-Rewriter**](../cs-install-guide/conf-output-generation.md#custom-rewriter) -Modul zur Behandlung der im Fall von Querkarten generierten Links (Verknüpfungen zwischen den Themen zweier verschiedener Karten).

Wenn Sie einen anderen benutzerdefinierten Sling-Rewriter in Ihrer Codebase haben, verwenden Sie eine `'order'` Wert größer als 50, da der Experience Manager Guides Sling Rewriter verwendet `'order'` 50.  Um dies zu überschreiben, benötigen Sie einen Wert > 50. Weitere Informationen finden Sie unter [Pipelines zum Neuschreiben der Ausgabe](https://sling.apache.org/documentation/bundles/output-rewriting-pipelines-org-apache-sling-rewriter.html).

Während dieses Upgrades, seit der `'order'` -Wert von 1000 auf 50 geändert wird, müssen Sie die vorhandene benutzerdefinierte Rewriter, sofern vorhanden, mit `'fmdita-rewriter'`.


## Kompatibilitätsmatrix

In diesem Abschnitt wird die Kompatibilitätsmatrix für die Softwareanwendungen aufgelistet, die von der Experience Manager-Guides-Version vom as a Cloud Service Februar 2024 unterstützt werden.

### FrameMaker und FrameMaker Publishing Server

| Experience Manager-Handbücher für as a Cloud | FMPS | FrameMaker |
| --- | --- | --- |
| 2024.02.0 | Nicht kompatibel | 2022 oder höher |
| | | |


### Sauerstoffanschluss

| Experience Manager-Handbücher für as a Cloud | Sauerstoff Connector Windows | Sauerstoff Connector Mac | In Oxygen Windows bearbeiten | In Oxygen Mac bearbeiten |
| --- | --- | --- | --- | --- |
| 2024.02.0 | 3.1-uuid.17 | 3.1-uuid.17 | 2,3 | 2,3 |
|  |  |  |  |


### Knowledgebase-Vorlagenversion

| Name des Komponentenpakets | Komponentenversion | Vorlagenversion |
|---|---|---|
| Experience Manager Guides-Komponenteninhaltspaket für Cloud Service | dxml-components.all-1.2.2 | aem-site-template-dxml.all-1.0.15 |

## Behobene Probleme

Die in verschiedenen Bereichen behobenen Fehler sind unten aufgeführt:

### Authoring

- Die Rechtschreibprüfung im Editor lässt die Auswahl von Vorschlägen nicht zu. (15045)
- Die globale Navigationsschaltfläche funktioniert nicht und das Dashboard kann nicht geladen werden. (14968)
- Im Web Editor kann die Download-Zuordnungsfunktion keine Popup-Benachrichtigung Trigger werden, wenn sie zum Herunterladen bereit ist. (14626)
- Im Web Editor kann die Funktion zum Herunterladen von Landkarten keine Landkarte mit Grundlinie herunterladen. (14622)
- Ungültiger DTD-Fehler in der as a Cloud Service Version 2310 des Experience Manager Guides. (14482)
- Wenn Sie ein Glossarthema aus dem Repository in eine Glossarzuordnung ziehen, wird `topicref`. (10767)
- Der Web Editor wird nach der Neuinstallation von Adobe Experience Manager Guides Version 4.3.1 deinstalliert. (14519)
- Beim Installationsprogramm von Version 4.3.1 tritt ein Filterkonflikt auf, der dazu führt, dass `apps/cq/core/content/projects/properties`. (14517)
- Der Vorschaubildschirm für Snippets ist gesperrt. (14840)

### Veröffentlichung

- Bei der nativen PDF-Veröffentlichung funktionieren benutzerdefinierte Attribute innerhalb von Bedingungsvorgaben nicht für die native PDF-Veröffentlichung. (14943)
- Benutzerdefinierte Vorlage kann nicht aus der **Ausgaben** im Editor. (14846)
- **AEM Site** aufgrund eines leeren Vorlagenpfads nicht funktioniert. (14804)
- AEM Neuerstellung der Site schlägt bei DITA-Maps mit Themen fehl, die MathML-Gleichungen enthalten. (14790)
- Bei nativer PDF-Veröffentlichung gibt die PDF-Generierung Fehler beim Abrufen von Abhängigkeiten für aus `Node.js` Publishing. (14445)
- AEM Vorgabe erlaubt die Auswahl einer Vorlage außerhalb der `/content` Hierarchie im Web-Editor. (14260)
- In der AEM Sites-Ausgabe gingen der Stil oder die Zeilenumbrüche für die `<lines>` -Element mit Unterelementen .(12542)
- Benutzerdefinierte Metadaten sind in der endgültigen Ausgabe nicht verfügbar. (12116)
- Beim Upgrade auf Version 4.3.1 treten im Knoten Native PDF einige Ausnahmen auf. (14492)


### Verwaltung

- **Baseline-Filter** -Dateien funktionieren nicht mit dem Dateinamen im Web-Editor. (13486)
- Die Deaktivierung der Indizierung der übergeordneten DITA-Zuordnung, um eine bessere Leistung zu erzielen, kann sich auf die Funktionalität bestimmter Funktionen auswirken.(12213)
- Beschriftungen aus der `labels.json` -Datei in zufälliger Reihenfolge im Web-Editor angezeigt. (10508)

### Überprüfung

- Kontextmenü mit Rechtsklick funktioniert nicht für **Accept** oder **Ablehnen** Änderungen verfolgen. (14607)
- Das Umschalten zum Schließen von DITA-Themen im Überprüfungsbildschirm funktioniert in Version 4.3.1 der Adobe Experience Manager-Handbücher nicht. (14537)
- Das Anpassen von E-Mail-Vorlagen für den Review-Workflow funktioniert nicht mit Überlagerungen. (13954)

## Bekanntes Problem

Adobe hat das folgende bekannte Problem für die Version Februar 2024 identifiziert:

- Version 1.0 wird nicht auf der Benutzeroberfläche für die duplizierte DITA-Datei angezeigt.
