---
title: Versionshinweise | Neue Funktionen in Adobe Experience Manager Guides, Version Oktober 2023
description: Erfahren Sie mehr über die neuen und verbesserten Funktionen in der Adobe Experience Manager Guides as a Cloud Service-Version vom Oktober 2023.
exl-id: 41bfed0d-5901-4ada-b6d7-a5be93b25ba8
feature: What's New
role: Leader
source-git-commit: 6d8c01f20f7b59fed92c404561b647d9ebecb050
workflow-type: tm+mt
source-wordcount: '623'
ht-degree: 0%

---

# Neue Funktionen in der Adobe Experience Manager Guides as a Cloud Service-Version vom Oktober 2023

Dieser Artikel behandelt die neuen und verbesserten Funktionen in der Version Oktober 2023 von Adobe Experience Manager Guides (später als *AEM Guides as a Cloud Service* bezeichnet).

Weitere Informationen zu den Upgrade-Anweisungen, der Kompatibilitätsmatrix und den in dieser Version behobenen Problemen finden Sie unter [Versionshinweise](release-notes-2023-10-0.md).


## Konfigurieren eines Datenquellen-Connectors über die Benutzeroberfläche

Experience Manager Guides bietet jetzt ein **Data Sources**-Tool, mit dem Sie native Connectoren für Datenquellen konfigurieren können. Sie können die Connectoren für JIRA-, SQL- (MySQL-, PostgreSQL-, Microsoft SQL Server-, SQLite-, MariaDB-, H2DB-), AdobeCommerce- und Elasticsearch-Datenbanken einfach erstellen.

Sie können einen Datenquellen-Connector auch einfach bearbeiten, neu verbinden, duplizieren oder löschen. Erfahren Sie, wie Sie [ einfach einen Datenquellen-Connector über die Benutzeroberfläche konfigurieren können.](../cs-install-guide/conf-data-source-connector-tools.md)

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

## Bearbeiten einer Datei im Oxygen-Connector-Plug-in

Experience Manager Guides ermöglicht es Ihnen nun, eine Datei im Web Editor auszuwählen und die Datei dann im Oxygen Connector-Plugin zu bearbeiten. Diese Option ist im Rahmen der nativen Unterstützung nicht aktiviert.

Weitere Informationen finden Sie in der Beschreibung der **Optionen für eine Datei**-Funktion im Abschnitt [Linkes Bedienfeld](../user-guide/web-editor-features.md#id2051EA0M0HS) .
