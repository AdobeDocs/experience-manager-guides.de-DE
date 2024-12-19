---
title: Versionshinweise zu | Upgrade-Anweisungen und behobene Probleme in Adobe Experience Manager Guides, Version Juni 2023
description: Erfahren Sie mehr über die Fehlerbehebungen und das Upgrade auf die Version Juni 2023 von Adobe Experience Manager Guides as a Cloud Service
exl-id: df17ee33-9f50-4223-ab9f-a57a31097d22
feature: Release Notes
role: Leader
source-git-commit: 6d8c01f20f7b59fed92c404561b647d9ebecb050
workflow-type: tm+mt
source-wordcount: '1170'
ht-degree: 1%

---

# Version Juni 2023 von Adobe Experience Manager Guides as a Cloud Service

Diese Versionshinweise enthalten die Upgrade-Anweisungen, die Kompatibilitätsmatrix und behobene Probleme in Version Juni 2023 von Adobe Experience Manager Guides (später *AEM Guides as a Cloud Service*).

Weitere Informationen zu den neuen Funktionen und Verbesserungen finden Sie unter [Neue Funktionen in der Version vom Juni 2023 von AEM Guides as a Cloud Service](whats-new-2023-6-0.md).

## Upgrade auf Version Juni 2023

Führen Sie ein Upgrade Ihres aktuellen AEM Guides as a Cloud Service-Setups durch, indem Sie die folgenden Schritte ausführen:

1. Checken Sie den Git-Code der Cloud Service aus und wechseln Sie zu der Verzweigung, die in der Cloud Service-Pipeline konfiguriert ist und der Umgebung entspricht, die Sie aktualisieren möchten.
2. Aktualisieren Sie `<dox.version>` Eigenschaft in `/dox/dox.installer/pom.xml` Datei Ihres Cloud Service-Git-Codes auf 2023.6.297.
3. Übertragen Sie die Änderungen und führen Sie die Cloud Service-Pipeline aus, um auf die Version vom Juni 2023 von AEM Guides as a Cloud Service zu aktualisieren.

## Schritte zum Aktivieren des Triggers eines Skripts über ein Servlet

Nach Abschluss der Installation können Sie den Trigger drücken, um den Übersetzungsauftrag zu starten:

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

1. Die API gibt eine jobId zurück. Um den Status des Auftrags zu überprüfen, können Sie eine GET-Anfrage mit Auftrags-ID an denselben Endpunkt senden - `http://<server:port>/bin/guides/reports/upgrade?jobId= {jobId}`
(Beispiel: `http://localhost:8080/bin/guides/map-find/indexing?jobId=2022/9/15/7/27/7dfa1271-981e-4617-b5a4-c18379f11c42_678`)

1. Sobald der Auftrag abgeschlossen ist, antwortet die vorherige GET-Anfrage erfolgreich. Wenn der Vorgang aus irgendeinem Grund fehlschlägt, kann der Fehler in den Serverprotokollen angezeigt werden.

1. Kehren Sie zum Standardwert oder vorherigen vorhandenen Wert von `queryLimitReads` zurück, wenn Sie ihn in Schritt 1 geändert haben.

## Schritte zum Indizieren des vorhandenen Inhalts, um die neue Themenliste „Suchen und Ersetzen“ auf der Registerkarte „Berichte“ zu verwenden:

(Nur bei Versionen vor der Version September 2022 von AEM Guides as a Cloud Service)

Führen Sie die folgenden Schritte aus, um den vorhandenen Inhalt zu indizieren und den neuen Text „Suchen und Ersetzen“ auf Zuordnungsebene und in der Themenliste auf der Registerkarte „Berichte“ zu verwenden:

1. Ausführen einer POST-Anfrage an den Server \(mit richtiger Authentifizierung\) - `http://<server:port\>/bin/guides/map-find/indexing`. (Optional) Sie können bestimmte Pfade der Zuordnungen übergeben, um sie zu indizieren. Standardmäßig werden alle Zuordnungen indiziert \|\| Beispiel: `https://<Server:port\>/bin/guides/map-find/indexing?paths=<map\_path\_in\_repository\>`)

1. Sie können auch einen Stammordner übergeben, um die DITA-Zuordnungen eines bestimmten Ordners (und seiner Unterordner) zu indizieren. Beispiel: `http://<server:port\>/bin/guides/map-find/indexing?root=/content/dam/test`. Beachten Sie, dass nur der Pfadparameter berücksichtigt wird, wenn sowohl der Pfadparameter als auch der Stammparameter übergeben werden.

1. Die API gibt eine jobId zurück. Um den Auftragsstatus zu überprüfen, können Sie eine GET-Anfrage mit Auftrags-ID an denselben Endpunkt senden - `http://<server:port\>/bin/guides/map-find/indexing?jobId=\{jobId\}`\(Beispiel: `http://localhost:8080/bin/guides/map-find/indexing?jobId=2022/9/15/7/27/7dfa1271-981e-4617-b5a4-c18379f11c42`\)


1. Sobald der Vorgang abgeschlossen ist, wird die vorherige GET-Anfrage erfolgreich beantwortet und es wird angegeben, ob Zuordnungen fehlgeschlagen sind. Die erfolgreich indizierten Zuordnungen können aus den Serverprotokollen bestätigt werden.

## Kompatibilitätsmatrix

In diesem Abschnitt finden Sie die Kompatibilitätsmatrix für die Softwareanwendungen, die von AEM Guides as a Cloud Service Version Juni 2023 unterstützt werden.

### FrameMaker und FrameMaker Publishing Server

| AEM Guides as a Cloud Service-Version | FMPS | FrameMaker |
| --- | --- | --- |
| 2 023,06,0 | Nicht kompatibel | 2022 oder höher |
| | | |


### Sauerstoffanschluss

| AEM Guides as a Cloud Service-Version | Fenster des Sauerstoffanschlusses | Oxygen Connector Mac | In Oxygen Windows bearbeiten | In Oxygen Mac bearbeiten |
| --- | --- | --- | --- | --- |
| 2 023,06,0 | 2.9-uuid-2 | 2.9-uuid-2 | 2,3 | 2,3 |
|  |  |  |  |


## Behobene Probleme

Die in verschiedenen Bereichen behobenen Fehler sind unten aufgeführt:

### Authoring

- Navtitle wird aus content33 entfernt, wenn von der Layout-Ansicht zur Autoren- oder Quellansicht gewechselt wird. 12174)
- Manchmal tritt beim Klicken auf eine DITA-Zuordnung ein Anwendungsfehler auf. 11842)
- Web-Editor | Beim Bearbeiten eines Themas wird im XML-Editor ein Leerzeichen ohne Unterbrechung hinzugefügt. 11786)
- Asset-Benutzeroberfläche | In der Listenansicht können die überlagerten verfügbaren Spalten nicht zusammengeführt werden. 11528)
- Keyref wird in der Zuordnungsansicht nicht aufgelöst. 11490)
- Beim Navigieren durch den XML-Editor wird das obere Menü nicht angezeigt. 10868)
- `conref` in pH-Tag | Das angezeigte Dialogfeld zum Durchsuchen ist falsch. (9481)
- Lokale Links zu anderen Elementen werden im Web-Editor nicht aufgelöst. (8790)
- Die Funktion Matches() funktioniert nicht in der Schematron-Funktion. 11224)


### Verwaltung

- Die Registerkarte „Berichte“ in der Benutzeroberfläche des Web-Editors zeigt nicht die Themenliste alter DITA-Zuordnungen an, die vor dem Upgrade auf 4.2 erstellt wurden. 11708)

- Die Funktion Dateien hochladen , mit der auf die Schaltfläche „Dateien hochladen“ in der Assets-Benutzeroberfläche zugegriffen werden kann, funktioniert nicht mehr in Version 4.2. 11633)

### Veröffentlichung

- Das Veröffentlichen auf der AEM-Site schlägt fehl, wenn temporäre Dateien vom Pod gelesen werden, die möglicherweise aktualisiert oder neu gestartet wurden. 12113)
- Native PDF | Die Veröffentlichung von Inhalten mit einer Ausgabeklasse mit Brackets() führt zu einem Veröffentlichungsstopp. 11936)
- JSON-Ausgabe | Zuordnen von Metadaten mit Eigenschaftswert als `"value in spaces and double quotes"` führt zu einem Veröffentlichungsfehler. 11933)
- Web-Editor | Ausgabepfad und -vorlage können nicht in der AEM-Voreinstellung ausgewählt werden. 11530)
- Native PDF | Benutzerdefinierte Attribute werden nicht an eine temporäre HTML- oder PDF-Engine weitergegeben. (DXML-12005)
- Native PDF |  Java OutOfMemoryError tritt beim Veröffentlichen großer Inhalte auf. 11789)
- JSON-Ausgabe | Die `fmUuid` Eigenschaft im Knoten jcr:content von JSON unterscheidet sich von der „id“ in JSON. 11564)
- JSON-Ausgabe | Wenn Zuordnung und Thema mit demselben Dateinamen vorhanden sind, wird JSON für die Zuordnung entfernt. 11524)
- Native PDF | Xref druckt den Inhalt des href-Thementitels anstelle der Xref-Beschriftung. 11322)
- Native PDF | Die PDF-Vorlageneinstellungen können nicht gespeichert werden. 10751)
- Native PDF | Der Text überschreitet die Spaltenbreite, wenn mehrere XRefs eingeschlossen werden. 10876)
- Native PDF | `<note>``</note>` Element erzeugt keinen zusätzlichen span-Titel seines Typs. 10549)
- Native PDF | Die Sprachmetadaten können auf der generierten PDF nicht gemäß WCAG 2.0 festgelegt werden. 12296)



### Übersetzung

- Seit der Cloud-Version vom Februar (2302) werden alle Übersetzungsinhalte als nicht synchronisiert oder als fehlende Kopie angezeigt. 11834)

### Überprüfung

- Neue UI-Überprüfung | Die Bedingungen heben Arbeit in den Bereichen „Hervorheben“, „Anzeigen“ und „Ausblenden“ anders hervor als in der Funktionsweise im Web-Editor. 11628)
