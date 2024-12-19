---
title: Versionshinweise zu | Upgrade-Anweisungen und behobene Probleme in Adobe Experience Manager Guides, Version Juli 2023
description: Erfahren Sie mehr über die Fehlerbehebungen und das Upgrade auf Version Juli 2023 von Adobe Experience Manager Guides as a Cloud Service
exl-id: f1765c6a-cb8e-4a06-a6f4-f5c225b6bc88
feature: Release Notes
role: Leader
source-git-commit: 6d8c01f20f7b59fed92c404561b647d9ebecb050
workflow-type: tm+mt
source-wordcount: '926'
ht-degree: 1%

---

# Version Juli 2023 von Adobe Experience Manager Guides as a Cloud Service

Diese Versionshinweise enthalten die Upgrade-Anweisungen, die Kompatibilitätsmatrix und behobene Probleme in Version Juli 2023 von Adobe Experience Manager Guides (später als *AEM Guides as a Cloud Service* bezeichnet).

Weitere Informationen zu den neuen Funktionen und Verbesserungen finden Sie unter [Neue Funktionen in der Version Juli 2023 von AEM Guides as a Cloud Service](whats-new-2023-7-0.md).

## Upgrade auf Version Juli 2023

Führen Sie ein Upgrade Ihres aktuellen AEM Guides as a Cloud Service-Setups durch, indem Sie die folgenden Schritte ausführen:

1. Checken Sie den Git-Code der Cloud Service aus und wechseln Sie zu der Verzweigung, die in der Cloud Service-Pipeline konfiguriert ist und der Umgebung entspricht, die Sie aktualisieren möchten.
2. Aktualisieren Sie `<dox.version>` Eigenschaft in `/dox/dox.installer/pom.xml` Datei Ihres Cloud Service-Git-Codes auf 2023.7.0.314.
3. Übertragen Sie die Änderungen und führen Sie die Cloud Service-Pipeline aus, um auf die AEM Guides as a Cloud Service-Version vom Juli 2023 zu aktualisieren.

## Schritte zum Aktivieren des Triggers eines Skripts über ein Servlet

(Nur bei Versionen vor der Version Juni 2023 von AEM Guides as a Cloud Service)

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

(Nur bei Versionen vor der Version Juni 2023 von AEM Guides as a Cloud Service)

Führen Sie die folgenden Schritte aus, um den vorhandenen Inhalt zu indizieren und den neuen Text „Suchen und Ersetzen“ auf Zuordnungsebene und in der Themenliste auf der Registerkarte „Berichte“ zu verwenden:

1. Ausführen einer POST-Anfrage an den Server \(mit richtiger Authentifizierung\) - `http://<server:port\>/bin/guides/map-find/indexing`. (Optional) Sie können bestimmte Pfade der Zuordnungen übergeben, um sie zu indizieren. Standardmäßig werden alle Zuordnungen indiziert \|\| Beispiel: `https://<Server:port\>/bin/guides/map-find/indexing?paths=<map\_path\_in\_repository\>`)

1. Sie können auch einen Stammordner übergeben, um die DITA-Zuordnungen eines bestimmten Ordners (und seiner Unterordner) zu indizieren. Beispiel: `http://<server:port\>/bin/guides/map-find/indexing?root=/content/dam/test`. Beachten Sie, dass nur der Pfadparameter berücksichtigt wird, wenn sowohl der Pfadparameter als auch der Stammparameter übergeben werden.

1. Die API gibt eine jobId zurück. Um den Auftragsstatus zu überprüfen, können Sie eine GET-Anfrage mit Auftrags-ID an denselben Endpunkt senden - `http://<server:port\>/bin/guides/map-find/indexing?jobId=\{jobId\}`\(Beispiel: `http://localhost:8080/bin/guides/map-find/indexing?jobId=2022/9/15/7/27/7dfa1271-981e-4617-b5a4-c18379f11c42`\)


1. Sobald der Vorgang abgeschlossen ist, wird die vorherige GET-Anfrage erfolgreich beantwortet und es wird angegeben, ob Zuordnungen fehlgeschlagen sind. Die erfolgreich indizierten Zuordnungen können aus den Serverprotokollen bestätigt werden.

## Kompatibilitätsmatrix

In diesem Abschnitt finden Sie die Kompatibilitätsmatrix für die Softwareanwendungen, die von AEM Guides as a Cloud Service Version Juli 2023 unterstützt werden.

### FrameMaker und FrameMaker Publishing Server

| AEM Guides as a Cloud Service-Version | FMPS | FrameMaker |
| --- | --- | --- |
| 2 023,07,0 | Nicht kompatibel | 2022 oder höher |
| | | |


### Sauerstoffanschluss

| AEM Guides as a Cloud Service-Version | Fenster des Sauerstoffanschlusses | Oxygen Connector Mac | In Oxygen Windows bearbeiten | In Oxygen Mac bearbeiten |
| --- | --- | --- | --- | --- |
| 2 023,07,0 | 2.9-uuid-2 | 2.9-uuid-2 | 2,3 | 2,3 |
|  |  |  |  |


## Behobene Probleme

Die in verschiedenen Bereichen behobenen Fehler sind unten aufgeführt:

### Authoring

- Inline-/Anzeigeattribute werden in der Layout-Ansicht des Web-Editors nicht angezeigt. 12498)
- Das Hochladen von Dateien im Oxygen Plugin für AEM Guides funktioniert nicht in Cloud Services, wenn Sie ! im Dateinamen. 12207)
- DITA Map Publishing ist bei bearbeitbaren Vorlagen sehr langsam. 12075)
- Die Konfiguration der globalen Profilbenutzeroberfläche stimmt nicht mit der Konfiguration des Ordnerprofils überein. 11970)
- Inhaltsreferenzen sind fehlerhaft, wenn DITA-Dateien kopiert und eingefügt werden. 11959)
- Inhaltsfragment kann nicht in der Spaltenansicht bearbeitet werden, wenn AEM Guides installiert ist. (7342)
- Der Inhalt geht verloren, wenn sich eine entpackte XRef unter einem Unterelement-Tag befindet. 12532)

### Veröffentlichung

- Der Genehmigungs-Workflow funktioniert nicht, wenn der Dokumentstatus in den Dateieigenschaften des rechten Bedienfelds in den „Endstatus“ geändert wird. 11026)
