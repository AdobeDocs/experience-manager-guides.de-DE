---
title: Versionshinweise | Adobe Experience Manager Guides as a Cloud Service, Version März 2023
description: März-Version von Adobe Experience Manager Guides as a Cloud Service
exl-id: 6a0bba92-7d7d-4b20-ad46-0eacc91268da
feature: Release Notes
role: Leader
TQID: https://experienceleague.adobe.com/eIPiGBWr-vxglYwzI0zYT64a4orZXm42hWthchmcceU
product_v2: id: fae5e35a-80c9-4b94-9352-1a060a6aab1did: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2: id: a3bd6397-2eb2-4908-a61c-226e26855dca
subfeature_v2: id: d5ea0417-7932-4688-a3e2-4d3b2e7076a3
role_v2: id: f8a45b24-4be7-4f1b-909b-60d06b483a20
topic_v2: id: a004cc84-67b9-4a33-a3a7-8ec7273ef4dc
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 545
ht-degree: 2%

---

# Version März 2023 von Adobe Experience Manager Guides as a Cloud Service

Diese Versionshinweise enthalten die Upgrade-Anweisungen, die Kompatibilitätsmatrix und behobene Probleme in Version März 2023 von Adobe Experience Manager Guides (später als *AEM Guides as a Cloud Service* bezeichnet).

Weitere Informationen zu den neuen Funktionen und Verbesserungen finden Sie unter [Neue Funktionen in der Version vom März 2023 von AEM Guides as a Cloud Service](whats-new-2023-3-0.md).

## Upgrade auf Version März 2023

Führen Sie ein Upgrade Ihres aktuellen AEM Guides as a Cloud Service-Setups durch, indem Sie die folgenden Schritte ausführen:

1. Checken Sie den Git-Code der Cloud Services aus und wechseln Sie zu der Verzweigung, die in der Cloud Services-Pipeline konfiguriert ist und der Umgebung entspricht, die Sie aktualisieren möchten.
1. Aktualisieren Sie `<dox.version>` Eigenschaft in `/dox/dox.installer/pom.xml` Datei Ihres Cloud Services-Git-Codes auf 2023.3.242.
1. Übernehmen Sie die Änderungen und führen Sie die Cloud Services-Pipeline aus, um auf die Version vom März 2023 von AEM Guides as a Cloud Service zu aktualisieren.

## Schritte zum Indizieren des vorhandenen Inhalts (nur, wenn Sie eine Version vor der September-Version von AEM Guides as a Cloud Service verwenden)

Führen Sie die folgenden Schritte aus, um den vorhandenen Inhalt zu indizieren und den neuen Text „Suchen und Ersetzen“ auf Zuordnungsebene zu verwenden:

* Ausführen einer POST-Anfrage an den Server (mit korrekter Authentifizierung) - `http://<server:port>/bin/guides/map-find/indexing`.
(Optional: Sie können bestimmte Pfade der Zuordnungen übergeben, um sie zu indizieren. Standardmäßig werden alle Zuordnungen indiziert. | Beispiel: `https://<Server:port>/bin/guides/map-find/indexing?paths=<map_path_in_repository>`)

* Die API gibt eine jobId zurück. Um den Status des Auftrags zu überprüfen, können Sie eine GET-Anfrage mit Auftrags-ID an denselben Endpunkt senden - `http://<server:port>/bin/guides/map-find/indexing?jobId={jobId}`
(Beispiel: http://&lt;_localhost:8080_/bin/guides/map-find/indexing?jobId=2022/9/15/7/27/7dfa1271-981e-4617-b5a4-c18379f11c42_678)

* Sobald der Vorgang abgeschlossen ist, antwortet die obige GET-Anfrage mit Erfolg und gibt an, ob Zuordnungen fehlgeschlagen sind. Die erfolgreich indizierten Zuordnungen können aus den Serverprotokollen bestätigt werden.

## Kompatibilitätsmatrix

In diesem Abschnitt finden Sie die Kompatibilitätsmatrix für die Softwareanwendungen, die von AEM Guides as a Cloud Service Version März 2023 unterstützt werden.

### FrameMaker und FrameMaker Publishing Server

| AEM Guides as a Cloud Service-Version | FMPS | FrameMaker |
| --- | --- | --- |
| 2023.03.0 | Nicht kompatibel | 2022 oder höher |
| | | |


### Sauerstoffanschluss

| AEM Guides as a Cloud Service-Version | Fenster des Sauerstoffanschlusses | Oxygen Connector Mac | In Oxygen Windows bearbeiten | In Oxygen Mac bearbeiten |
| --- | --- | --- | --- | --- |
| 2023.03.0 | 2.9-uuid-2 | 2.9-uuid-2 | 2,3 | 2,3 |
|  |  |  |  |  |

## Behobene Probleme

Die in verschiedenen Bereichen behobenen Fehler sind unten aufgeführt:

* Der PDF-Download-Prozess funktioniert im Web-Editor nicht ordnungsgemäß. (11496)
* JSON-Ausgabe | Zuordnen von Metadaten mit Eigenschaftswert als `"value in spaces and double quotes"` führt zu einem Veröffentlichungsfehler. (11438)
* Das Einfügen von Audio- und Videomultimediadateien schlägt im YouTube-Format unter dem Symbol **Multimedia einfügen** fehl. (11320)
* Ein Validierungsfehler tritt auf, wenn eine Zuordnung mithilfe der Vorlage erstellt wird, die über ein spezielles Titelelement verfügt. (11212)
* Die native Fußnote in PDF | in der Tabellenkopfzeile führt zu fett und zentriert ausgerichtetem Text in der entsprechenden Fußzeile in der PDF-Ausgabe. (10610)
>[!NOTE]
>
>Um die native PDF-Änderung widerzuspiegeln, löschen Sie den PDF-Ordner unter /content/dam/dita-templates und aktualisieren Sie dann auf den neuesten Build. (10610)

### Bekanntes Problem mit Problemumgehung

Adobe hat das folgende bekannte Problem bei AEM Guides as a Cloud Service Version März 2023 identifiziert.

* Benutzende können keine Version eines duplizierten Assets speichern oder erstellen.

**Problemumgehung**: Bevor Sie Änderungen am doppelten Asset vornehmen, verarbeiten Sie es über die Assets-Benutzeroberfläche erneut.
