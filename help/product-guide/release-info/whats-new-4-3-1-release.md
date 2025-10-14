---
title: Versionshinweise zu | Neue Funktionen in Adobe Experience Manager Guides Version 4.3.1
description: Erfahren Sie mehr über die neuen und erweiterten Funktionen in Version 4.3.1 von Adobe Experience Manager Guides
exl-id: 14db7453-ccc1-4709-903f-677f55c263b2
feature: What's New
role: Leader
source-git-commit: 5a444e88b0adba7fa3d498437df39b729b10b5eb
workflow-type: tm+mt
source-wordcount: '1127'
ht-degree: 0%

---

# Neue Funktionen in Version 4.3.1 von Adobe Experience Manager Guides (Oktober 2023)

Dieser Artikel behandelt die neuen und erweiterten Funktionen in Version 4.3.1 von Adobe Experience Manager Guides (später *Experience Manager Guides*).

Weitere Informationen zu den Upgrade-Anweisungen, der Kompatibilitätsmatrix und den in dieser Version behobenen Problemen finden Sie unter [Versionshinweise](./release-notes-4-3-1.md).

## Herstellen einer Verbindung zu einer Datenquelle und Einfügen der Themen

Experience Manager Guides bietet vorkonfigurierte Connectoren, mit denen Sie eine Verbindung zu Ihren Datenquellen herstellen können, wodurch Experience Manager Guides zu einem echten Content-Hub wird. Dies bietet den Vorteil, dass Sie Zeit und Aufwand sparen, der andernfalls für das manuelle Hinzufügen oder die Replikation von Daten aufgewendet würde.

Neben den vorhandenen vorkonfigurierten Connectoren wie JIRA und SQL (MySQL, PostgreSQL, SQL Server, SQLite) kann Ihr Administrator auch Connectoren für MariaDB-, H2DB-, AdobeCommerce- und Elasticsearch-Datenbanken konfigurieren. Sie können auch andere Connectoren hinzufügen, indem sie die Standardschnittstellen erweitern.

Sie können die konfigurierten Connectoren unter dem Bedienfeld **Datenquellen** im Web-Editor anzeigen.

<img src="assets/data-sources.png" alt="Liste der Datenquellen im Bedienfeld" width="300">

*Anzeigen der verbundenen Datenquellen.*

Sie können jetzt auch ein Thema aus einer verbundenen Datenquelle erstellen. Ein Thema kann Daten in verschiedenen Formaten enthalten, z. B. Tabellen, Listen und Absätze. Außerdem können Sie eine DITA-Karte für alle Themen erstellen. Beim Abrufen aus einer Datenquelle können Sie dem Thema Metadaten zuordnen.

Weitere Informationen finden Sie unter [Verwenden von Daten aus Ihrer Datenquelle](../user-guide/web-editor-content-snippet.md).

## Konfigurieren eines Datenquellen-Connectors über die Benutzeroberfläche

Experience Manager Guides bietet jetzt auch ein **Datenquellen**-Tool, mit dem Sie vordefinierte Connectoren für Datenquellen konfigurieren können. Sie können auf einfache Weise Connectoren für JIRA-, SQL- (MySQL, PostgreSQL, Microsoft SQL Server, SQLite, MariaDB, H2DB), AdobeCommerce- und Elasticsearch-Datenbanken erstellen.

Sie können einen Datenquellen-Connector auch einfach bearbeiten, erneut verbinden, duplizieren oder löschen. Erfahren Sie mehr darüber, wie [einfach einen Datenquellen-Connector über die Benutzeroberfläche konfigurieren](../install-guide/conf-data-source-connector-tools.md).

![Im Datenquellenbedienfeld aufgelistete Datenquellen-Connectoren](assets/data-sources-create-window.png){width="550" align="left"}

*Erstellen und Anzeigen der Datenquellen-Connectoren im Bedienfeld „Datenquellen“.*

## Anzeigen von Protokollen für den Themengenerator

Sie können jetzt auch die Protokolldatei für die Inhaltserstellung anzeigen. In dieser Protokolldatei können Sie die Warnungen, Fehler und Ausnahmen überprüfen.  Erfahren Sie mehr darüber, wie [Optionen für einen Themengenerator](../user-guide/web-editor-content-snippet.md#options-for-a-topic-generator) Ihnen helfen, die Themengeneratoren einfach zu generieren und zu verwalten.

## Unterstützung für Velocity-Tools in den Datenquellenvorlagen

Sie können jetzt die Velocity-Tools in den Experience Manager Guides-Vorlagen verwenden. Mit diesen Tools können Sie verschiedene Funktionen auf die Daten anwenden, die Sie aus den Datenquellen abrufen. Sie können die Vorlagen beim Erstellen eines Inhaltsausschnitts oder Themas verwenden. Mit dieser Funktion sparen Sie Zeit und Mühe bei der manuellen Anwendung derselben Funktion auf jeden Datensatz.  Außerdem werden präzise Ergebnisse erzielt.
Beispielsweise können Sie das $mathTool verwenden, um mathematische Funktionen auszuführen.
Erfahren Sie mehr über [&#x200B; Verwendung von Velocity-Tools in den Datenquellenvorlagen](../user-guide/web-editor-content-snippet.md#use-velocity-tools).


## Native PDF-Verbesserungen

Die folgenden nativen PDF-Verbesserungen wurden in der Version vom Oktober 2023 vorgenommen:

### Zurücksetzen der Seitennummer für die erste Seite eines Layouts

In der nativen PDF-Ausgabe können Sie die Seitenzahlen neu starten und die Zahl angeben, mit der die Nummerierung beginnt. Jetzt können Sie die Nummerierung auch nur für das erste Vorkommen eines Abschnitts starten.
Erfahren Sie mehr über [Arbeiten mit den Seiteneigenschaften eines Seiten-Layouts](../native-pdf/design-page-layout.md#page-props-page-layout).


### Kapitel ohne automatische Nummern im Inhaltsverzeichnis anzeigen

Experience Manager Guides zeigt die Kapitelnummern zusammen mit den Kapitelnamen im Inhaltsverzeichnis (Inhaltsverzeichnis) an. Jetzt können Sie festlegen, dass nur die Kapitelnamen ohne die Kapitelnummern veröffentlicht werden. Weitere Informationen zum Konfigurieren der [erweiterten PDF-Einstellungen einer Vorlage](../native-pdf/components-pdf-template.md#advanced-pdf-settings).

## Herunterladen einer Karte aus dem Web-Editor

Jetzt können Sie eine Karte nicht nur in der Kartenansicht des Web-Editors bearbeiten, sondern auch herunterladen. Sie können die Karte mit einer bestimmten Grundlinie herunterladen. Sie haben außerdem die Möglichkeit, die Hierarchie zu vereinfachen und alle Dateien und Ordner in einem einzigen Ordner zu speichern.

Weitere Informationen finden Sie in der Beschreibung der Funktion **Kartenansicht** im Abschnitt [Linkes Bedienfeld](../user-guide/web-editor-features.md#id2051EA0M0HS).

![Optionsmenü einer Datei in der Repository-Ansicht](assets/options-menu-repo-view-file-level-2310.png){width="550" align="left"}

*Wählen Sie eine Datei in der Repository-Ansicht aus und wählen Sie die Option aus, um eine Aktion mit der Datei durchzuführen.*


## Unterstützung mehrerer Betreffdefinitionen in einer einzelnen Auflistungsdefinition

Sie können jetzt eine oder mehrere Betreffdefinitionen in einer Zuordnung und die Auflistungsdefinitionen in einer anderen Zuordnung definieren und dann die Zuordnungsreferenz hinzufügen. Die Verweise auf die Auflistung des Subjekts werden in derselben Zuordnung oder in der referenzierten Zuordnung aufgelöst.

Sie können jetzt auch Bedingungen definieren und sie auf einige bestimmte Elemente in einem Thema anwenden.  Die Bedingungen sind nur für diese spezifischen Elemente sichtbar, nicht für alle anderen Elemente.

Weitere Informationen zum Umgang mit hierarchischen Definitionen von Betreffdefinitionen und Auflistungen finden Sie in der Beschreibung der Funktionen des Betreffschemas im Abschnitt [Linkes Bedienfeld](../user-guide/web-editor-features.md#id2051EA0M0HS).




## Verbesserte Vorschau über das Kontextmenü

Verwenden Sie das Kontextmenü, um die Datei (.dita, .xml, Audio, Video oder Bild) schnell in der Vorschau anzuzeigen, ohne sie zu öffnen. Sie können jetzt die Größe des Vorschaubereichs ändern. Wenn der Inhalt einen Verweis-Link enthält, können Sie ihn auswählen, um ihn in einer neuen Registerkarte zu öffnen.

![Vorschau-](assets/quick-preview_cs.png){width="800" align="left"}

*Vorschau der Datei im Fensterbereich anzeigen.*

Weitere Informationen zum Kontextmenü finden Sie in der **Optionen für eine Datei** Funktionsbeschreibung im Abschnitt [Linkes &#x200B;](../user-guide/web-editor-features.md#id2051EA0M0HS)).

## Bearbeiten einer Datei im Oxygen Connector-Plug-in

Mit Experience Manager Guides können Sie jetzt eine Datei im Web-Editor auswählen und dann die Datei im Plug-in „Oxygen-Connector“ bearbeiten. Diese Option ist nicht als Bestandteil der vordefinierten Unterstützung aktiviert.

Weitere Informationen finden Sie in der **Optionen für eine Datei** Funktionsbeschreibung im Abschnitt [Linkes Bedienfeld](../user-guide/web-editor-features.md#id2051EA0M0HS).

## Verwenden von Variablen für aktuelles Datum und aktuelle Uhrzeit in den Optionen Zielpfad, Site-Name oder Dateiname .

Beim Generieren von Ausgaben in AEM Site oder PDF können Sie Variablen verwenden, um die Optionen **Zielpfad**, **Site-Name** oder **Dateiname** festzulegen. Sie können jetzt auch die Variablen `${system_date}` und `${system_time}` verwenden. Mithilfe dieser Variablen können Sie das aktuelle Datum und die aktuelle Uhrzeit an diese Optionen anhängen.

Erfahren Sie, wie [Variablen zum Festlegen der Optionen Zielpfad, Site-Name oder Dateiname verwenden](../user-guide/generate-output-use-variables.md).


## Tastaturbefehle zum Verschieben des Cursors im Web-Editor

Experience Manager Guides ermöglicht jetzt auch die Verwendung von Tastaturbefehlen zum Verschieben des Cursors im Web-Editor. Sie können die Tastaturbefehle verwenden, um ein Wort schnell nach links oder rechts zu verschieben. Sie können auch mithilfe der Tastaturbefehle zum Anfang oder Ende der Zeile wechseln.

Erfahren Sie mehr über [Tastaturbefehle im Web-Editor](../user-guide/web-editor-keyboard-shortcuts.md).
