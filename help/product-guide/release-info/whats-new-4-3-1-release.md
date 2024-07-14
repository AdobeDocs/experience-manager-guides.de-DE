---
title: Versionshinweise | Neue Funktionen in Adobe Experience Manager Guides Version 4.3.1
description: Erfahren Sie mehr über die neuen und verbesserten Funktionen in Version 4.3.1 von Adobe Experience Manager Guides.
exl-id: 14db7453-ccc1-4709-903f-677f55c263b2
feature: What's New
role: Leader
source-git-commit: 5a444e88b0adba7fa3d498437df39b729b10b5eb
workflow-type: tm+mt
source-wordcount: '1127'
ht-degree: 0%

---

# Neue Funktionen in Version 4.3.1 von Adobe Experience Manager Guides (Oktober 2023)

Dieser Artikel behandelt die neuen und verbesserten Funktionen in Version 4.3.1 von Adobe Experience Manager Guides (später als *Experience Manager Guides* bezeichnet).

Weitere Informationen zu den Upgrade-Anweisungen, der Kompatibilitätsmatrix und den in dieser Version behobenen Problemen finden Sie unter [Versionshinweise](./release-notes-4-3-1.md).

## Herstellen einer Verbindung zu einer Datenquelle und Einfügen der Themen

Experience Manager Guides bietet vordefinierte Connectoren, mit denen Sie eine Verbindung zu Ihren Datenquellen herstellen können, sodass Experience Manager Guides ein echter Content-Hub wird. Dies bietet Ihnen den Vorteil, dass Sie Zeit und Mühe sparen, die andernfalls für das manuelle Hinzufügen oder die Replikation von Daten ausgegeben würden.

Neben den bereits vorhandenen nativen Connectoren wie JIRA und SQL (MySQL, PostgreSQL, SQL Server, SQLite) kann Ihr Administrator auch Connectoren für die Datenbanken MariaDB, H2DB, AdobeCommerce und Elasticsearch konfigurieren. Sie können auch andere Connectoren hinzufügen, indem sie die Standardschnittstellen erweitern.

Sie können die konfigurierten Connectoren im Web Editor im Bereich **Data Sources** anzeigen.

<img src="assets/data-sources.png" alt="Liste der Datenquellen im Bereich" width="300">

*Anzeigen der verbundenen Datenquellen.*

Sie können jetzt auch ein Thema aus einer verbundenen Datenquelle erstellen. Ein Thema kann Daten in verschiedenen Formaten wie Tabellen, Listen und Absätzen enthalten. Außerdem können Sie eine DITA-Zuordnung für alle Themen erstellen. Beim Abrufen aus einer Datenquelle können Sie dem Thema Metadaten zuordnen.

Weitere Informationen finden Sie unter [Daten aus Ihrer Datenquelle verwenden](../user-guide/web-editor-content-snippet.md).

## Konfigurieren eines Datenquellen-Connectors über die Benutzeroberfläche

Experience Manager Guides bietet jetzt auch ein **Data Sources**-Tool, mit dem Sie native Connectoren für Datenquellen konfigurieren können. Sie können die Connectoren für JIRA-, SQL- (MySQL-, PostgreSQL-, Microsoft SQL Server-, SQLite-, MariaDB-, H2DB-), AdobeCommerce- und Elasticsearch-Datenbanken einfach erstellen.

Sie können einen Datenquellen-Connector auch einfach bearbeiten, neu verbinden, duplizieren oder löschen. Erfahren Sie mehr darüber, wie Sie [einfach einen Datenquellen-Connector über die Benutzeroberfläche konfigurieren können](../install-guide/conf-data-source-connector-tools.md).

![Datenquellen-Connectoren, die im Bereich &quot;Datenquellen&quot;aufgelistet sind](assets/data-sources-create-window.png){width="550" align="left"}

*Erstellen und zeigen Sie die Datenquellen-Connectoren im Bereich &quot;Datenquellen&quot;an.*

## Anzeigen von Protokollen für den Themengenerator

Sie können jetzt auch die Protokolldatei zur Inhaltserstellung anzeigen. Mithilfe dieser Protokolldatei können Sie die Warnungen, Fehler und Ausnahmen überprüfen.  Erfahren Sie mehr darüber, wie Sie mit den [Optionen für einen Themengenerator](../user-guide/web-editor-content-snippet.md#options-for-a-topic-generator) die Themengeneratoren einfach generieren und verwalten können.

## Unterstützung für Velocity-Tools in den Datenquellenvorlagen

Sie können jetzt die Velocity-Tools in den Experience Manager Guides-Vorlagen verwenden. Mit diesen Tools können Sie verschiedene Funktionen auf die Daten anwenden, die Sie aus den Datenquellen abrufen. Sie können die Vorlagen beim Erstellen eines Inhaltsfragments oder eines Themas verwenden. Mit dieser Funktion sparen Sie Zeit und Mühe bei der manuellen Anwendung derselben Funktion auf jeden Datensatz.  Außerdem werden präzise Ergebnisse sichergestellt.
Beispielsweise können Sie das $mathematische Tool verwenden, um mathematische Funktionen auszuführen.
Erfahren Sie mehr darüber, wie Sie [Velocity-Tools in den Datenquellenvorlagen verwenden](../user-guide/web-editor-content-snippet.md#use-velocity-tools).


## Native PDF-Verbesserungen

Die folgenden nativen PDF-Verbesserungen wurden in der Version vom Oktober 2023 vorgenommen:

### Seitenzahl für die erste Seite eines Layouts zurücksetzen

In der nativen PDF-Ausgabe können Sie die Seitenzahlen neu starten und die Nummer angeben, ab der die Nummerierung beginnt. Jetzt können Sie die Nummerierung auch nur für das erste Vorkommen eines Abschnitts beginnen.
Erfahren Sie mehr darüber, wie Sie [mit den Seiteneigenschaften eines Seitenlayouts arbeiten](../native-pdf/design-page-layout.md#page-props-page-layout).


### Anzeigen von Kapiteln ohne automatische Zahlen im Inhaltsverzeichnis

Experience Manager Guides zeigt die Kapitelnummern zusammen mit den Kapitelnamen im Inhaltsverzeichnis an. Jetzt können Sie nur die Kapitelnamen ohne Kapitelnummern veröffentlichen. Sehen Sie sich weitere Informationen zum Konfigurieren der [erweiterten PDF-Einstellungen einer Vorlage](../native-pdf/components-pdf-template.md#advanced-pdf-settings) an.

## Herunterladen einer Karte vom Web-Editor

Jetzt können Sie nicht nur eine Karte in der Kartenansicht des Web-Editors bearbeiten, sondern sie auch herunterladen. Sie können die Karte mit einer bestimmten Grundlinie herunterladen. Sie können auch die Hierarchie reduzieren und alle Dateien und Ordner in einem Ordner speichern.

Weitere Informationen finden Sie in der Beschreibung der Funktion **Kartenansicht** im Abschnitt [Linkes Bedienfeld](../user-guide/web-editor-features.md#id2051EA0M0HS) .

![Optionsmenü einer Datei in der Repository-Ansicht](assets/options-menu-repo-view-file-level-2310.png){width="550" align="left"}

*Wählen Sie eine Datei in der Repository-Ansicht aus und wählen Sie die Option, um eine Aktion für die Datei durchzuführen.*


## Unterstützung für mehrere Themendefinitionen in einer einzelnen Auflistungsdefinition

Sie können jetzt eine oder mehrere Betreffdefinitionen in einer Zuordnung und die Auflistungsdefinitionen in einer anderen Zuordnung definieren und dann die Zuordnungsreferenz hinzufügen. Die Verweise auf die Betreffauflistung werden in derselben Zuordnung oder der referenzierten Zuordnung aufgelöst.

Sie können jetzt auch Bedingungen definieren und sie auf einige spezifische Elemente in einem Thema anwenden.  Die Bedingungen sind nur für diese spezifischen Elemente sichtbar, nicht für alle anderen Elemente.

Weitere Informationen zum Umgang mit hierarchischen Definitionen von Betreffdefinitionen und Auflistungen finden Sie in der Funktionsbeschreibung des Betreffschemas im Abschnitt [Linkes Bedienfeld](../user-guide/web-editor-features.md#id2051EA0M0HS) .




## Erweiterte Funktionen zur Vorschau im Kontextmenü

Verwenden Sie das Kontextmenü, um die Datei (dita, .xml, audio, video oder image) schnell in der Vorschau anzuzeigen, ohne sie zu öffnen. Sie können jetzt die Größe des Vorschaufensters ändern. Wenn der Inhalt einen Verweis-Link enthält, können Sie ihn auswählen, um ihn in einer neuen Registerkarte zu öffnen.

![Vorschaufenster ](assets/quick-preview_cs.png){width="800" align="left"}

*Zeigen Sie eine Vorschau der Datei im Bereich an.*

Weitere Informationen zum Kontextmenü finden Sie in der Beschreibung der Funktion **Optionen für eine Datei** im Abschnitt [Linkes Bedienfeld](../user-guide/web-editor-features.md#id2051EA0M0HS) .

## Bearbeiten einer Datei im Oxygen-Connector-Plug-in

Experience Manager Guides ermöglicht es Ihnen nun, eine Datei im Web Editor auszuwählen und die Datei dann im Oxygen Connector-Plugin zu bearbeiten. Diese Option ist im Rahmen der nativen Unterstützung nicht aktiviert.

Weitere Informationen finden Sie in der Beschreibung der **Optionen für eine Datei**-Funktion im Abschnitt [Linkes Bedienfeld](../user-guide/web-editor-features.md#id2051EA0M0HS) .

## Verwenden Sie Variablen für das aktuelle Datum und die aktuelle Uhrzeit in den Optionen &quot;Zielpfad&quot;, &quot;Site-Name&quot;oder &quot;Dateiname&quot;

Beim Generieren von Ausgaben in AEM Site oder PDF können Sie Variablen zum Festlegen der Optionen **Zielpfad**, **Site-Name** oder **Dateiname** verwenden. Sie können jetzt auch die Variablen `${system_date}`und `${system_time}` verwenden. Mithilfe dieser Variablen können Sie diesen Optionen das aktuelle Datum und die aktuelle Uhrzeit anhängen.

Erfahren Sie, wie Sie [Variablen zum Festlegen der Optionen &quot;Zielpfad&quot;, &quot;Site-Name&quot;oder &quot;Dateiname&quot;verwenden](../user-guide/generate-output-use-variables.md).


## Tastaturbefehle zum Verschieben des Cursors in den Web-Editor

Mit Experience Manager Guides können Sie jetzt auch Tastaturbefehle verwenden, um den Cursor im Web-Editor zu verschieben. Sie können die Tastaturbefehle verwenden, um ein Wort schnell nach links oder rechts zu verschieben. Mithilfe der Tastaturbefehle können Sie auch zum Anfang oder Ende der Zeile wechseln.

Erfahren Sie mehr über die [Tastaturbefehle im Web-Editor](../user-guide/web-editor-keyboard-shortcuts.md).
