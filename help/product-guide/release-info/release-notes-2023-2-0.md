---
title: Versionshinweise | Adobe Experience Manager Guides as a Cloud Service, Version Februar 2023
description: Februarversion von Adobe Experience Manager Guides as a Cloud Service
exl-id: c639b136-11ed-4a8b-a595-4bb5da879747
feature: Release Notes
role: Leader
TQID: https://experienceleague.adobe.com/KtMCjANUmaT-PaKIJltf0G72WaHR0JV94HyutN9DyFY
product_v2: id: fae5e35a-80c9-4b94-9352-1a060a6aab1did: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2: id: a3bd6397-2eb2-4908-a61c-226e26855dcaid: ab01a588-7dea-43f2-a699-0b3f128465d6
subfeature_v2: id: ad602516-aca3-4247-9ae8-f393d958efa9id: d5ea0417-7932-4688-a3e2-4d3b2e7076a3id: f89f75b0-cf2e-4e96-aec8-fe8c39cbd0ef
role_v2: id: f8a45b24-4be7-4f1b-909b-60d06b483a20
topic_v2: id: a004cc84-67b9-4a33-a3a7-8ec7273ef4dc
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 857
ht-degree: 4%

---

# Version Februar 2023 von Adobe Experience Manager Guides as a Cloud Service

Diese Versionshinweise enthalten die Upgrade-Anweisungen, die Kompatibilitätsmatrix und behobene Probleme in Version Februar 2023 von Adobe Experience Manager Guides (später *AEM Guides as a Cloud Service*).

Weitere Informationen zu den neuen Funktionen und Verbesserungen finden Sie unter [Neue Funktionen in der Version vom Februar 2023 von AEM Guides as a Cloud Service](whats-new-2023-2-0.md).

## Upgrade auf die Version Februar 2023

Führen Sie ein Upgrade Ihres aktuellen AEM Guides as a Cloud Service-Setups durch, indem Sie die folgenden Schritte ausführen:
1. Checken Sie den Git-Code der Cloud Services aus und wechseln Sie zu der Verzweigung, die in der Cloud Services-Pipeline konfiguriert ist und der Umgebung entspricht, die Sie aktualisieren möchten.
2. Aktualisieren Sie `<dox.version>` Eigenschaft in `/dox/dox.installer/pom.xml` Datei Ihres Cloud Services-Git-Codes auf 2023.2.235.
3. Übernehmen Sie die Änderungen und führen Sie die Cloud Services-Pipeline aus, um auf die Version vom Februar 2023 von AEM Guides as a Cloud Service zu aktualisieren.

## Schritte zum Indizieren des vorhandenen Inhalts (nur, wenn Sie eine Version vor der September-Version von AEM Guides as a Cloud Service verwenden)

Führen Sie die folgenden Schritte aus, um den vorhandenen Inhalt zu indizieren und den neuen Text „Suchen und Ersetzen“ auf Zuordnungsebene zu verwenden:

* Ausführen einer POST-Anfrage an den Server (mit korrekter Authentifizierung) - `http://<server:port>/bin/guides/map-find/indexing`.
(Optional: Sie können bestimmte Pfade der Zuordnungen übergeben, um sie zu indizieren. Standardmäßig werden alle Zuordnungen indiziert. | Beispiel: `https://<Server:port>/bin/guides/map-find/indexing?paths=<map_path_in_repository>`)

* Die API gibt eine jobId zurück. Um den Status des Auftrags zu überprüfen, können Sie eine GET-Anfrage mit Auftrags-ID an denselben Endpunkt senden - `http://<server:port>/bin/guides/map-find/indexing?jobId={jobId}`
(Beispiel: http://&lt;_localhost:8080_/bin/guides/map-find/indexing?jobId=2022/9/15/7/27/7dfa1271-981e-4617-b5a4-c18379f11c42_678)

* Sobald der Vorgang abgeschlossen ist, antwortet die obige GET-Anfrage mit Erfolg und gibt an, ob Zuordnungen fehlgeschlagen sind. Die erfolgreich indizierten Zuordnungen können aus den Serverprotokollen bestätigt werden.

## Kompatibilitätsmatrix

In diesem Abschnitt finden Sie die Kompatibilitätsmatrix für die Softwareanwendungen, die von AEM Guides as a Cloud Service Version Februar 2023 unterstützt werden.

### FrameMaker und FrameMaker Publishing Server

| AEM Guides as a Cloud Service-Version | FMPS | FrameMaker |
| --- | --- | --- |
| 2023.02.0 | Nicht kompatibel | 2022 oder höher |
| | | |

*Die in AEM erstellten Grundlinien und Bedingungen werden ab 2020.2 in FMPS-Versionen unterstützt.

### Sauerstoffanschluss

| AEM Guides as a Cloud Service-Version | Fenster des Sauerstoffanschlusses | Oxygen Connector Mac | In Oxygen Windows bearbeiten | In Oxygen Mac bearbeiten |
| --- | --- | --- | --- | --- |
| 2023.02.0 | 2.8-uuid-8 | 2.8-uuid-8 | 2,3 | 2,3 |
|  |  |  |  |  |

## Behobene Probleme

Die in verschiedenen Bereichen behobenen Fehler sind unten aufgeführt:

### Authoring

* Änderungen im HTML-Editor des Web-Editors führen zu Problemen mit `<dl>` und `<dlentry>`. (11024)
* Einige Attribute werden nicht als bedingt behandelt und verursachen Probleme. (10895)
* Mindestens drei Ebenen verschachtelter `<indexterm>` sind nicht im nativen PDF-Export verschachtelt. (10799)
* Der Inhalt verschwindet beim Wechsel von der Authoring- zur Source-Ansicht im Hauptteil einer Aufgabe. (10735)
* Überprüfungskommentare werden in einer Überprüfungsaufgabe verlegt. (10625)
* **Rückgängig** oder **Wiederholen** funktioniert bei einigen Dateien nicht ordnungsgemäß. (10373)
* Benutzerdefinierte Metadaten werden beim Kopieren und Einfügen nicht beibehalten. (10367)
* Die Option „Rückgängig machen“ im XML-Editor führt den Benutzer zum Seitenanfang. (10091)
* Knoteneigenschaften werden nach dem Kopieren und Einfügen eines Assets entfernt. (10053)
* mimeType ist für die Erstellung und Aktualisierung von DITA-Assets hartcodiert. (8979)
* Der Name des Versionserstellers im Versionsverlauf lautet „fmdita-serviceuser“ für die Dateien, die über die Assets-Benutzeroberfläche hochgeladen wurden. (8910)
* Inhaltsfragmente können nicht kopiert und eingefügt werden, wenn AEM Guides in der Cloud installiert ist. (11315)
* Der Browser (Web-Editor) friert das Laden von Inhalten mit benutzerdefiniertem Schema ein. (11211)

### Verwaltung

* Das Kopieren eines DITA Map-Assets (über die Asset-Benutzeroberfläche ) verursacht fehlerhafte Baselines im kopierten Asset. (11218)
* Beim Hochladen einer Datei, die den in AEM zulässigen Grenzwert (standardmäßig 2 GB) überschreitet, wird keine Warnmeldung angezeigt. (10817)
* Web-Editor-Baseline | Das Verhalten der letzten Spalte im neuen Baseline-Dashboard im Web-Editor ist anders. (10808)
* Übersetzung | Übersetzungsauftrag wird aufgrund von ungültigem /libs/fmdita/i18n/ja.json nicht gestartet. (10543)
* Übersetzung | In einem Umfangübersetzungsprojekt, das über das Übersetzungs-Dashboard (Menschliche Übersetzung) erstellt wurde, tritt ein Fehler auf. (10526)
* Übersetzung | Nachbearbeitung wird für den gesamten Sprachordner blockiert, dessen Assets in einem aktiven Übersetzungsprojekt vorhanden sind. (10332)
* Für jedes Asset werden mehrere Popups angezeigt, wenn die Version geändert und im Baseline-Editor gespeichert wird. (10399)
* Sitzungsleck am `com.day.cq.search.impl.builder.QueryBuilderImpl.createResourceResolver(QueryBuilderImpl.java:210)`. (10279)

### Publishing

* Die Themenregenerierung funktioniert in einigen Szenarien nicht. (10635)
* Der PublishListener zeigt die angeforderten Daten nicht in Informationsprotokollen an und enthält auch einige Junk-Protokolle.( 10567)
* Native PDF | Beim Erstellen einer Ausgabevorgabe mit der Option „Zu Ordnerprofil hinzufügen“ schlägt die PDF-Generierung mit einer Null Pointer-Ausnahme fehl. (10950)
* Natives PDF | Probleme treten beim Drehen der Tabellenkopfzeile auf. (10555)
* Native PDF | Verschachtelte `<indexterm>` werden nicht im nativen PDF-Export verschachtelt. (10521)
* Native PDF | Verschachtelte topicref in den Anhängen werden im temporären HTML alle in h1 umgewandelt. (10454)
* Die Baseline-Veröffentlichung schlägt für PDF fehl, das mit FrameMaker Publishing Server 2020 generiert wurde. (10551)
* Native PDF | Beim Hinzufügen von `xref` zu einem Bild wird das Bild auf der generierten PDF nicht gerendert. (11346)
* Das native Tag &quot;PDF | Image“ fügt allen Bildern das Attribut „display-inline“ hinzu. (10653)
* Native PDF | Entwurfskommentare sind in der generierten Ausgabe standardmäßig ausgeblendet. (10560)
* Native PDF | navtitle wird nicht für Topichead geehrt. (10509)
