---
title: Versionshinweise | Adobe Experience Manager Guides as a Cloud Service, Version März 2023
description: Version von Adobe Experience Manager Guides as a Cloud Service im März
exl-id: 6a0bba92-7d7d-4b20-ad46-0eacc91268da
feature: Release Notes
role: Leader
source-git-commit: 6d8c01f20f7b59fed92c404561b647d9ebecb050
workflow-type: tm+mt
source-wordcount: '561'
ht-degree: 0%

---

# Adobe Experience Manager Guides as a Cloud Service-Version vom März 2023

In diesem Versionshinweis werden die Aktualisierungsanweisungen, die Kompatibilitätsmatrix und die in Version März 2023 von Adobe Experience Manager Guides behobenen Probleme (später als *AEM Guides as a Cloud Service* bezeichnet) beschrieben.

Weitere Informationen zu den neuen Funktionen und Verbesserungen finden Sie unter [Neue Funktionen in der AEM Guides as a Cloud Service-Version vom März 2023](whats-new-2023-3-0.md).

## Aktualisierung auf Version März 2023

Führen Sie die folgenden Schritte aus, um Ihr aktuelles AEM Guides as a Cloud Service-Setup zu aktualisieren:

1. Sehen Sie sich den Git-Code des Cloud Service an und wechseln Sie zu der Verzweigung, die in der Cloud Service-Pipeline entsprechend der Umgebung konfiguriert ist, die Sie aktualisieren möchten.
1. Aktualisieren Sie die Eigenschaft `<dox.version>` in der Datei `/dox/dox.installer/pom.xml` Ihres Cloud Service-Git-Codes auf 2023.3.242.
1. Übertragen Sie die Änderungen und führen Sie die Cloud Service-Pipeline aus, um auf die Version von AEM Guides as a Cloud Service vom März 2023 zu aktualisieren.

## Schritte zum Indexieren des vorhandenen Inhalts (nur, wenn Sie eine Version vor der September-Version von AEM Guides as a Cloud Service verwenden)

Führen Sie die folgenden Schritte aus, um den vorhandenen Inhalt zu indizieren und den neuen Text auf Zuordnungsebene zu suchen und zu ersetzen:

* Führen Sie eine POST-Anfrage an den Server aus (mit der richtigen Authentifizierung) - `http://<server:port>/bin/guides/map-find/indexing`.
(Optional: Sie können bestimmte Pfade der Maps übergeben, um sie zu indizieren. Standardmäßig werden alle Maps indiziert || Beispiel : `https://<Server:port>/bin/guides/map-find/indexing?paths=<map_path_in_repository>`)

* Die API gibt eine jobId zurück. Um den Status des Auftrags zu überprüfen, können Sie eine GET-Anfrage mit Auftrags-ID an denselben Endpunkt senden - `http://<server:port>/bin/guides/map-find/indexing?jobId={jobId}`
(Beispiel: http://&lt;_localhost:8080_>/bin/guides/map-find/indexing?jobId=2022/9/15/7/27/7dfa1271-981e-4617-b5a4-c183 79f11c42_678)

* Nach Abschluss des Auftrags antwortet die obige GET-Anfrage mit Erfolg und gibt an, ob Zuordnungen fehlgeschlagen sind. Die erfolgreich indizierten Maps können über die Serverprotokolle bestätigt werden.

## Kompatibilitätsmatrix

In diesem Abschnitt wird die Kompatibilitätsmatrix für die Softwareanwendungen aufgelistet, die von der AEM Guides as a Cloud Service-Version vom März 2023 unterstützt werden.

### FrameMaker und FrameMaker Publishing Server

| AEM Guides as a Cloud-Version | FMPS | FrameMaker |
| --- | --- | --- |
| 2023,03,0 | Nicht kompatibel | 2022 oder höher |
| | | |


### Sauerstoffanschluss

| AEM Guides as a Cloud-Version | Sauerstoff Connector Windows | Sauerstoff Connector Mac | In Oxygen Windows bearbeiten | In Oxygen Mac bearbeiten |
| --- | --- | --- | --- | --- |
| 2023,03,0 | 2.9-uuid-2 | 2.9-uuid-2 | 2,3 | 2,3 |
|  |  |  |  |

## Behobene Probleme

Die in verschiedenen Bereichen behobenen Fehler sind unten aufgeführt:

* Der Download-PDF-Prozess funktioniert im Web-Editor nicht ordnungsgemäß. (11496)
* JSON-Ausgabe | Zuordnen von Metadaten mit dem Eigenschaftswert &quot;`"value in spaces and double quotes"`&quot; führt zu einem Veröffentlichungsfehler. (11438)
* Das Einfügen von Audio- und Video-Multimedia-Dateien schlägt im YouTube-Format unter dem Symbol &quot;**Multimedia einfügen**&quot;fehl. (11320)
* Der Validierungsfehler tritt auf, wenn eine Zuordnung mithilfe der Vorlage erstellt wird, die über ein spezielles Titelelement verfügt. (11212)
* Native PDF | Die in der Tabellenüberschrift vorhandene Fußnote führt zu fett und zentriert ausgerichtetem Text in der entsprechenden Fußzeile der PDF-Ausgabe. (10610)
>[!NOTE]
>
>Um die Änderung der nativen PDF widerzuspiegeln, löschen Sie den Ordner PDF unter /content/dam/dita-templates und aktualisieren Sie dann auf den neuesten Build. (10610)

### Bekanntes Problem mit Problemumgehung

Adobe hat das folgende bekannte Problem für die AEM Guides as a Cloud Service-Version vom März 2023 identifiziert.

* Benutzer können keine Version eines duplizierten Assets speichern oder erstellen.

**Problemumgehung**: Bevor Sie Änderungen am doppelten Asset vornehmen, verarbeiten Sie es über die Assets-Benutzeroberfläche erneut.
