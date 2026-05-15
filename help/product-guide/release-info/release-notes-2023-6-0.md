---
title: Versionshinweise | Upgrade-Anweisungen und behobene Probleme in Adobe Experience Manager Guides, Version Juni 2023
description: Erfahren Sie mehr über die Fehlerbehebungen und das Upgrade auf die Version Juni 2023 von Adobe Experience Manager Guides as a Cloud Service
exl-id: df17ee33-9f50-4223-ab9f-a57a31097d22
feature: Release Notes
role: Leader
TQID: https://experienceleague.adobe.com/LIY9wVDmvusGD-K-kyjK-lmzpyxJELj0mWzn9YoP0vw
product_v2: id: fae5e35a-80c9-4b94-9352-1a060a6aab1did: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2: id: a3bd6397-2eb2-4908-a61c-226e26855dcaid: ab01a588-7dea-43f2-a699-0b3f128465d6id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0eid: d90290ec-3e61-4ebd-8649-bcafe0836803
subfeature_v2: id: ad602516-aca3-4247-9ae8-f393d958efa9id: d5ea0417-7932-4688-a3e2-4d3b2e7076a3id: f89f75b0-cf2e-4e96-aec8-fe8c39cbd0ef
role_v2: id: f8a45b24-4be7-4f1b-909b-60d06b483a20
topic_v2: id: a004cc84-67b9-4a33-a3a7-8ec7273ef4dc
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 1169
ht-degree: 3%

---

# Version Juni 2023 von Adobe Experience Manager Guides as a Cloud Service

Diese Versionshinweise enthalten die Upgrade-Anweisungen, die Kompatibilitätsmatrix und behobene Probleme in Version Juni 2023 von Adobe Experience Manager Guides (später *AEM Guides as a Cloud Service*).

Weitere Informationen zu den neuen Funktionen und Verbesserungen finden Sie unter [Neue Funktionen in der Version vom Juni 2023 von AEM Guides as a Cloud Service](whats-new-2023-6-0.md).

## Upgrade auf Version Juni 2023

Führen Sie ein Upgrade Ihres aktuellen AEM Guides as a Cloud Service-Setups durch, indem Sie die folgenden Schritte ausführen:

1. Checken Sie den Git-Code der Cloud Services aus und wechseln Sie zu der Verzweigung, die in der Cloud Services-Pipeline konfiguriert ist und der Umgebung entspricht, die Sie aktualisieren möchten.
2. Aktualisieren Sie `<dox.version>` Eigenschaft in `/dox/dox.installer/pom.xml` Datei Ihres Cloud Services-Git-Codes auf 2023.6.297.
3. Übernehmen Sie die Änderungen und führen Sie die Cloud Services-Pipeline aus, um auf die Version vom Juni 2023 von AEM Guides as a Cloud Service zu aktualisieren.

## Schritte zum Aktivieren des Triggers eines Skripts über ein Servlet

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

(Nur bei Versionen vor der Version September 2022 von AEM Guides as a Cloud Service)

Führen Sie die folgenden Schritte aus, um den vorhandenen Inhalt zu indizieren und den neuen Text „Suchen und Ersetzen“ auf Zuordnungsebene und in der Themenliste auf der Registerkarte „Berichte“ zu verwenden:

1. Führen Sie eine POST-Anfrage an den Server \(mit korrekter Authentifizierung\) - `http://<server:port\>/bin/guides/map-find/indexing` aus. (Optional: Sie können bestimmte Pfade der Zuordnungen übergeben, um sie zu indizieren. Standardmäßig werden alle Zuordnungen indiziert \|\|, zum Beispiel : `https://<Server:port\>/bin/guides/map-find/indexing?paths=<map\_path\_in\_repository\>`)

1. Sie können auch einen Stammordner übergeben, um die DITA-Zuordnungen eines bestimmten Ordners (und seiner Unterordner) zu indizieren. Beispiel: `http://<server:port\>/bin/guides/map-find/indexing?root=/content/dam/test`. Beachten Sie, dass nur der Pfadparameter berücksichtigt wird, wenn sowohl der Pfadparameter als auch der Stammparameter übergeben werden.

1. Die API gibt eine jobId zurück. Zur Überprüfung des Auftragsstatus können Sie eine GET-Anfrage mit Auftrags-ID an denselben Endpunkt senden - `http://<server:port\>/bin/guides/map-find/indexing?jobId=\{jobId\}`\(Beispiel: `http://localhost:8080/bin/guides/map-find/indexing?jobId=2022/9/15/7/27/7dfa1271-981e-4617-b5a4-c18379f11c42`\)


1. Sobald der Vorgang abgeschlossen ist, wird die vorherige GET-Anfrage erfolgreich beantwortet und es wird angegeben, ob Zuordnungen fehlgeschlagen sind. Die erfolgreich indizierten Zuordnungen können aus den Serverprotokollen bestätigt werden.

## Kompatibilitätsmatrix

In diesem Abschnitt finden Sie die Kompatibilitätsmatrix für die Softwareanwendungen, die von AEM Guides as a Cloud Service Version Juni 2023 unterstützt werden.

### FrameMaker und FrameMaker Publishing Server

| AEM Guides as a Cloud Service-Version | FMPS | FrameMaker |
| --- | --- | --- |
| 2023.06.0 | Nicht kompatibel | 2022 oder höher |
| | | |


### Sauerstoffanschluss

| AEM Guides as a Cloud Service-Version | Fenster des Sauerstoffanschlusses | Oxygen Connector Mac | In Oxygen Windows bearbeiten | In Oxygen Mac bearbeiten |
| --- | --- | --- | --- | --- |
| 2023.06.0 | 2.9-uuid-2 | 2.9-uuid-2 | 2,3 | 2,3 |
|  |  |  |  |  |


## Behobene Probleme

Die in verschiedenen Bereichen behobenen Fehler sind unten aufgeführt:

### Authoring

- Navtitle wird aus content33 entfernt, wenn von der Layout-Ansicht zur Autoren- oder Quellansicht gewechselt wird. (12174)
- Manchmal tritt beim Klicken auf eine DITA-Zuordnung ein Anwendungsfehler auf. (11842)
- Webeditor | Im XML-Editor wird beim Bearbeiten eines Themas ein Leerzeichen ohne Unterbrechung hinzugefügt. (11786)
- Asset-Benutzeroberfläche | In der Listenansicht können die überlagerten verfügbaren Spalten nicht zusammengeführt werden. (11528)
- Keyref wird in der Zuordnungsansicht nicht aufgelöst. (11490)
- Beim Navigieren durch den XML-Editor wird das obere Menü nicht angezeigt. (10868)
- `conref` in PH-Tag | Das angezeigte Dialogfeld zum Durchsuchen ist falsch. (9481)
- Lokale Links zu anderen Elementen werden im Web-Editor nicht aufgelöst. (8790)
- Die Funktion Matches() funktioniert nicht in der Schematron-Funktion. (11224)


### Verwaltung

- Die Registerkarte „Berichte“ in der Benutzeroberfläche des Web-Editors zeigt nicht die Themenliste alter DITA-Zuordnungen an, die vor dem Upgrade auf 4.2 erstellt wurden. (11708)

- Die Funktion Dateien hochladen , mit der auf die Schaltfläche „Dateien hochladen“ in der Assets-Benutzeroberfläche zugegriffen werden kann, funktioniert nicht mehr in Version 4.2. (11633)

### Publishing

- Das Veröffentlichen auf der AEM-Site schlägt fehl, wenn temporäre Dateien vom Pod gelesen werden, die möglicherweise aktualisiert oder neu gestartet wurden. (12113)
- Native PDF | Veröffentlichung von Inhalten mit einer Ausgabeklasse mit Brackets() führt zu einem Veröffentlichungsstopp. (11936)
- JSON-Ausgabe | Zuordnen von Metadaten mit Eigenschaftswert als `"value in spaces and double quotes"` führt zu einem Veröffentlichungsfehler. (11933)
- Web-Editor | Ausgabepfad und Vorlage können in der AEM-Voreinstellung nicht ausgewählt werden. (11530)
- Native PDF | Benutzerdefinierte Attribute werden nicht an die temporäre HTML- oder PDF-Engine weitergegeben. (DXML-12005)
- Der native PDF | Java OutOfMemoryError tritt beim Veröffentlichen großer Inhalte auf. (11789)
- JSON-Ausgabe | Die `fmUuid` Eigenschaft im jcr:content-Knoten von JSON unterscheidet sich von der „id“ in JSON. (11564)
- JSON-Ausgabe | Wenn die Zuordnung und das Thema mit demselben Dateinamen vorhanden sind, wird JSON für die Zuordnung entfernt. (11524)
- Native PDF | Xref druckt den Inhalt des href-Thementitels anstelle der Xref-Beschriftung. (11322)
- Native PDF | Die PDF-Vorlageneinstellungen können nicht gespeichert werden. (10751)
- Native PDF | Der Text überschreitet die Spaltenbreite, wenn mehrere XRefs eingeschlossen werden. (10876)
- Das native PDF | `<note>``</note>`-Element generiert keinen zusätzlichen span-Titel seines Typs. (10549)
- Nativer PDF | Die Sprach-Metadaten können in der generierten PDF nicht auf WCAG 2.0 eingestellt werden. (12296)



### Übersetzung

- Seit der Cloud-Version vom Februar (2302) werden alle Übersetzungsinhalte als nicht synchronisiert oder als fehlende Kopie angezeigt. (11834)

### Überprüfung

- Neue Überprüfungs-Benutzeroberfläche | Die Bedingungen heben Arbeit im Web-Editor hervor, zeigen und blenden sich anders aus als in der Funktionsweise. (11628)
