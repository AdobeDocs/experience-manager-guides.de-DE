---
title: Versionshinweise | Adobe Experience Manager Guides as a Cloud Service, Version Februar 2023
description: Februar-Version von Adobe Experience Manager Guides as a Cloud Service
exl-id: c639b136-11ed-4a8b-a595-4bb5da879747
feature: Release Notes
role: Leader
source-git-commit: 6d8c01f20f7b59fed92c404561b647d9ebecb050
workflow-type: tm+mt
source-wordcount: '870'
ht-degree: 1%

---

# Version von Adobe Experience Manager Guides as a Cloud Service vom Februar 2023

In diesem Versionshinweis werden die Aktualisierungsanweisungen, die Kompatibilitätsmatrix und die in Version Februar 2023 von Adobe Experience Manager Guides behobenen Probleme (später als *AEM Guides as a Cloud Service* bezeichnet) beschrieben.

Weitere Informationen zu den neuen Funktionen und Verbesserungen finden Sie unter [Neue Funktionen in der AEM Guides as a Cloud Service-Version vom Februar 2023](whats-new-2023-2-0.md).

## Aktualisierung auf die Version vom Februar 2023

Führen Sie die folgenden Schritte aus, um Ihr aktuelles AEM Guides as a Cloud Service-Setup zu aktualisieren:
1. Sehen Sie sich den Git-Code des Cloud Service an und wechseln Sie zu der Verzweigung, die in der Cloud Service-Pipeline entsprechend der Umgebung konfiguriert ist, die Sie aktualisieren möchten.
2. Aktualisieren Sie die Eigenschaft `<dox.version>` in der Datei `/dox/dox.installer/pom.xml` Ihres Cloud Service-Git-Codes auf 2023.2.235.
3. Nehmen Sie die Änderungen vor und führen Sie die Cloud Service-Pipeline aus, um auf die AEM Guides as a Cloud Services-Version vom Februar 2023 zu aktualisieren.

## Schritte zum Indexieren des vorhandenen Inhalts (nur, wenn Sie eine Version vor der September-Version von AEM Guides as a Cloud Service verwenden)

Führen Sie die folgenden Schritte für die Indizierung des vorhandenen Inhalts aus und verwenden Sie den neuen Suchen- und Ersetzen-Text auf Zuordnungsebene:

* Führen Sie eine POST-Anfrage an den Server aus (mit der richtigen Authentifizierung) - `http://<server:port>/bin/guides/map-find/indexing`.
(Optional: Sie können bestimmte Pfade der Maps übergeben, um sie zu indizieren. Standardmäßig werden alle Maps indiziert || Beispiel : `https://<Server:port>/bin/guides/map-find/indexing?paths=<map_path_in_repository>`)

* Die API gibt eine jobId zurück. Um den Status des Auftrags zu überprüfen, können Sie eine GET-Anfrage mit Auftrags-ID an denselben Endpunkt senden - `http://<server:port>/bin/guides/map-find/indexing?jobId={jobId}`
(Beispiel: http://&lt;_localhost:8080_>/bin/guides/map-find/indexing?jobId=2022/9/15/7/27/7dfa1271-981e-4617-b5a4-c183 79f11c42_678)

* Nach Abschluss des Auftrags antwortet die obige GET-Anfrage mit Erfolg und gibt an, ob Zuordnungen fehlgeschlagen sind. Die erfolgreich indizierten Maps können über die Serverprotokolle bestätigt werden.

## Kompatibilitätsmatrix

In diesem Abschnitt wird die Kompatibilitätsmatrix für die Softwareanwendungen aufgelistet, die von der AEM Guides as a Cloud Service-Version vom Februar 2023 unterstützt werden.

### FrameMaker und FrameMaker Publishing Server

| AEM Guides as a Cloud-Version | FMPS | FrameMaker |
| --- | --- | --- |
| 2023.02.0 | Nicht kompatibel | 2022 oder höher |
| | | |

*Die in AEM erstellten Grundlinien und Bedingungen werden in FMPS-Versionen ab 2020.2 unterstützt.

### Sauerstoffanschluss

| AEM Guides as a Cloud-Version | Sauerstoff Connector Windows | Sauerstoff Connector Mac | In Oxygen Windows bearbeiten | In Oxygen Mac bearbeiten |
| --- | --- | --- | --- | --- |
| 2023.02.0 | 2.8-uuid-8 | 2.8-uuid-8 | 2,3 | 2,3 |
|  |  |  |  |

## Behobene Probleme

Die in verschiedenen Bereichen behobenen Fehler sind unten aufgeführt:

### Authoring

* Änderungen am HTML-Code des Web Editors verursachen Probleme mit `<dl>` und `<dlentry>`. (11024)
* Einige Attribute werden nicht als bedingt behandelt und verursachen Probleme. (10895)
* Drei Ebenen oder mehr verschachtelte `<indexterm>` sind im nativen PDF-Export nicht verschachtelt. (1079)
* Der Inhalt verschwindet beim Wechsel von der Autorenansicht zur Source-Ansicht im Hauptteil einer Aufgabe. (10735)
* Überprüfungskommentare werden in einer Prüfungsaufgabe nicht platziert. (10625)
* **Rückgängig** oder **Wiederholen** funktioniert bei einigen Dateien nicht ordnungsgemäß. (10373)
* Benutzerdefinierte Metadaten werden beim Kopieren und Einfügen nicht beibehalten. (10367)
* Die Option &quot;Rückgängig&quot;im XML-Editor bringt den Benutzer zum Anfang der Seite. (10091)
* Knoteneigenschaften werden nach dem Kopieren und Einfügen eines Assets entfernt. (10053)
* mimeType ist für die Erstellung und Aktualisierung von DITA-Assets hartcodiert. (8979)
* Der Name des Erstellers der Version im Versionsverlauf ist &quot;fmdita-service-user&quot;für die Dateien, die über die Assets-Benutzeroberfläche hochgeladen wurden. (8910)
* Inhaltsfragmente können nicht kopiert und eingefügt werden, wenn AEM Guides in Cloud installiert ist. (11315)
* Der Browser (Web Editor) friert beim Laden von Inhalten mit benutzerdefiniertem Schema ein. (1121)

### Verwaltung

* Das Kopieren eines DITA-Map-Assets (aus der Asset-Benutzeroberfläche ) verursacht fehlerhafte Grundlinien im kopierten Asset. (11218)
* Beim Hochladen einer Datei, die die in AEM zulässige Größe überschreitet, wird keine Warnmeldung angezeigt (standardmäßig 2 GB). (10817)
* Web Editor-Grundlinie | Das Verhalten der Spalte &quot;Neueste&quot;unterscheidet sich im neuen Dashboard für die Grundlinie im Web Editor. (10808)
* Übersetzung | Der Übersetzungsauftrag wird aufgrund von ungültigen /libs/fmdita/i18n/ja.json nicht gestartet. (10543)
* Übersetzung | In einem Scoping-Übersetzungsprojekt, das über das Übersetzungs-Dashboard (Menschliche Übersetzung) erstellt wurde, tritt ein Fehler auf. (10526)
* Übersetzung | Die Verarbeitung von Post ist für den gesamten Sprachordner blockiert, dessen Assets in einem aktiven Übersetzungsprojekt vorhanden sind. (10332)
* Für jedes Asset werden mehrere Popups angezeigt, wenn die Version geändert und im Baseline-Editor gespeichert wird. (10399)
* SitzungsLeak tritt bei `com.day.cq.search.impl.builder.QueryBuilderImpl.createResourceResolver(QueryBuilderImpl.java:210)` auf. (10279)

### Veröffentlichung

* Die Themenregenerierung funktioniert in einigen Szenarien nicht. (10635)
* Der Herausgeber zeigt die angeforderten Daten nicht in den Infoprotokollen an und enthält auch einige Junk-Protokolle.(10567)
* Native PDF | Beim Erstellen einer Ausgabevorgabe mit der Option &quot;Zum Ordnerprofil hinzufügen&quot;schlägt die PDF-Erstellung mit einer Nullzeiger-Ausnahme fehl. (10950)
* Native PDF | Beim Drehen der Tabellenüberschrift treten Probleme auf. (10555)
* Native PDF | Verschachtelte `<indexterm>` werden im nativen PDF-Export nicht verschachtelt. (10521)
* Native PDF | Verschachtelte topicref in Anhängen werden alle in der temporären HTML in h1 umgewandelt. 10454
* Grundlegende Veröffentlichung schlägt bei PDF fehl, die mit FrameMaker Publishing Server 2020 erstellt wurde. (10551)
* Native PDF | Durch Hinzufügen von `xref` zu einem Bild wird das Bild nicht auf der generierten PDF gerendert. (11346)
* Native PDF | Das Bild-Tag fügt allen Bildern das Attribut display-inline hinzu. (10653)
* Native PDF | Entwurfskommentare sind standardmäßig in der generierten Ausgabe ausgeblendet. (10560)
* Native PDF | navtitle wird für topichead nicht geehrt. (10509)
