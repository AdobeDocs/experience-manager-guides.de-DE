---
title: Versionshinweise zu | Adobe Experience Manager Guides as a Cloud Service, Version März 2023
description: März-Version von Adobe Experience Manager Guides as a Cloud Service
exl-id: 6a0bba92-7d7d-4b20-ad46-0eacc91268da
feature: Release Notes
role: Leader
source-git-commit: 6d8c01f20f7b59fed92c404561b647d9ebecb050
workflow-type: tm+mt
source-wordcount: '561'
ht-degree: 0%

---

# Version März 2023 von Adobe Experience Manager Guides as a Cloud Service

Diese Versionshinweise enthalten die Upgrade-Anweisungen, die Kompatibilitätsmatrix und behobene Probleme in Version März 2023 von Adobe Experience Manager Guides (später als *AEM Guides as a Cloud Service* bezeichnet).

Weitere Informationen zu den neuen Funktionen und Verbesserungen finden Sie unter [Neue Funktionen in der Version vom März 2023 von AEM Guides as a Cloud Service](whats-new-2023-3-0.md).

## Upgrade auf Version März 2023

Führen Sie ein Upgrade Ihres aktuellen AEM Guides as a Cloud Service-Setups durch, indem Sie die folgenden Schritte ausführen:

1. Checken Sie den Git-Code der Cloud Service aus und wechseln Sie zu der Verzweigung, die in der Cloud Service-Pipeline konfiguriert ist und der Umgebung entspricht, die Sie aktualisieren möchten.
1. Aktualisieren Sie `<dox.version>` Eigenschaft in `/dox/dox.installer/pom.xml` Datei Ihres Cloud Service-Git-Codes auf 2023.3.242.
1. Übertragen Sie die Änderungen und führen Sie die Cloud Service-Pipeline aus, um auf die AEM Guides as a Cloud Service-Version vom März 2023 zu aktualisieren.

## Schritte zum Indizieren des vorhandenen Inhalts (nur bei Versionen vor der AEM Guides as a Cloud Service-Version September)

Führen Sie die folgenden Schritte aus, um den vorhandenen Inhalt zu indizieren und den neuen Text „Suchen und Ersetzen“ auf Zuordnungsebene zu verwenden:

* Ausführen einer POST-Anfrage an den Server (mit korrekter Authentifizierung) - `http://<server:port>/bin/guides/map-find/indexing`.
(Optional) Sie können bestimmte Pfade der Karten übergeben, um sie zu indizieren. Standardmäßig werden alle Karten indiziert || Beispiel : `https://<Server:port>/bin/guides/map-find/indexing?paths=<map_path_in_repository>`)

* Die API gibt eine jobId zurück. Um den Status des Auftrags zu überprüfen, können Sie eine GET-Anfrage mit Auftrags-ID an denselben Endpunkt senden - `http://<server:port>/bin/guides/map-find/indexing?jobId={jobId}`
(Beispiel: http://&lt;_localhost:8080_>/bin/guides/map-find/indexing?jobId=2022/9/15/7/27/7dfa1271-981e-4617-b5a4-c18379f11c42_678)

* Sobald der Vorgang abgeschlossen ist, antwortet die obige GET-Anfrage mit Erfolg und gibt an, ob Zuordnungen fehlgeschlagen sind. Die erfolgreich indizierten Zuordnungen können aus den Serverprotokollen bestätigt werden.

## Kompatibilitätsmatrix

In diesem Abschnitt finden Sie die Kompatibilitätsmatrix für die Softwareanwendungen, die von AEM Guides as a Cloud Service Version März 2023 unterstützt werden.

### FrameMaker und FrameMaker Publishing Server

| AEM Guides as a Cloud Service-Version | FMPS | FrameMaker |
| --- | --- | --- |
| 2 023,03,0 | Nicht kompatibel | 2022 oder höher |
| | | |


### Sauerstoffanschluss

| AEM Guides as a Cloud Service-Version | Fenster des Sauerstoffanschlusses | Oxygen Connector Mac | In Oxygen Windows bearbeiten | In Oxygen Mac bearbeiten |
| --- | --- | --- | --- | --- |
| 2 023,03,0 | 2.9-uuid-2 | 2.9-uuid-2 | 2,3 | 2,3 |
|  |  |  |  |

## Behobene Probleme

Die in verschiedenen Bereichen behobenen Fehler sind unten aufgeführt:

* Der Download-PDF-Prozess funktioniert im Web-Editor nicht ordnungsgemäß. 11496)
* JSON-Ausgabe | Zuordnen von Metadaten mit Eigenschaftswert als `"value in spaces and double quotes"` führt zu einem Veröffentlichungsfehler. 11438)
* Das Einfügen von Audio- und Videomultimediadateien schlägt im YouTube-Format unter dem Symbol **Multimedia einfügen** fehl. 11320)
* Ein Validierungsfehler tritt auf, wenn eine Zuordnung mithilfe der Vorlage erstellt wird, die über ein spezielles Titelelement verfügt. 11212)
* Native PDF | Eine in der Tabellenkopfzeile vorhandene Fußnote führt zu fett und zentriert ausgerichtetem Text in der entsprechenden Seitenfußzeile in der PDF-Ausgabe. 10610)
>[!NOTE]
>
>Um die native PDF-Änderung widerzuspiegeln, löschen Sie den Ordner &quot;PDF&quot; unter /content/dam/dita-templates und aktualisieren Sie dann auf den neuesten Build. 10610)

### Bekanntes Problem mit Problemumgehung

Adobe hat das folgende bekannte Problem bei AEM Guides as a Cloud Service Version März 2023 festgestellt.

* Benutzende können keine Version eines duplizierten Assets speichern oder erstellen.

**Problemumgehung**: Bevor Sie Änderungen am doppelten Asset vornehmen, verarbeiten Sie es über die Assets-Benutzeroberfläche erneut.
