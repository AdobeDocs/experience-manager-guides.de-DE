---
title: Versionshinweise | Neue Funktionen in Adobe Experience Manager Guides, Version September 2023
description: Erfahren Sie mehr über die neuen und verbesserten Funktionen in der Adobe Experience Manager Guides as a Cloud Service-Version vom September 2023.
exl-id: d185d27f-0cbb-4ec6-ac65-cb69f7572c3f
feature: What's New
role: Leader
source-git-commit: 6d8c01f20f7b59fed92c404561b647d9ebecb050
workflow-type: tm+mt
source-wordcount: '1683'
ht-degree: 0%

---

# Neue Funktionen in der Adobe Experience Manager Guides as a Cloud Service-Version vom September 2023

In diesem Artikel werden die neuen und verbesserten Funktionen in der Adobe Experience Manager Guides-Version vom September 2023 (später als *AEM Guides as a Cloud Service* bezeichnet) behandelt.

Weitere Informationen zu den Upgrade-Anweisungen, der Kompatibilitätsmatrix und den in dieser Version behobenen Problemen finden Sie unter [Versionshinweise](release-notes-2023-9-0.md).

## Herstellen einer Verbindung zu einer Datenquelle und Einfügen der Themen

AEM Guides bietet vordefinierte Connectoren, mit denen Sie eine Verbindung zu Ihren Datenquellen herstellen können, sodass AEM Guides ein echter Content-Hub wird. Dies bietet Ihnen den Vorteil, dass Sie Zeit und Mühe sparen, die andernfalls für das manuelle Hinzufügen oder die Replikation von Daten ausgegeben würden.

Neben den bereits vorhandenen nativen Connectoren wie JIRA und SQL (MySQL, PostgreSQL, SQL Server, SQLite) kann Ihr Administrator auch Connectoren für die Datenbanken MariaDB, H2DB, AdobeCommerce und Elasticsearch konfigurieren. Sie können auch andere Connectoren hinzufügen, indem sie die Standardschnittstellen erweitern.

Sie können die konfigurierten Connectoren im Web Editor im Bereich **Data Sources** anzeigen.

<img src="assets/data-sources.png" alt="Liste der Datenquellen im Bereich" width="300">

*Anzeigen der verbundenen Datenquellen.*

Sie können jetzt auch ein Thema aus einer verbundenen Datenquelle erstellen. Ein Thema kann Daten in verschiedenen Formaten wie Tabellen, Listen und Absätzen enthalten. Außerdem können Sie eine DITA-Zuordnung für alle Themen erstellen. Beim Abrufen aus einer Datenquelle können Sie dem Thema Metadaten zuordnen.

Weitere Informationen finden Sie unter [Daten aus Ihrer Datenquelle verwenden](../user-guide/web-editor-content-snippet.md).

## Hinzufügen von Zitaten zu Ihrem Inhalt

Zitate sind Verweise auf die Informationsquelle, die zu Ihrem Inhalt hinzugefügt wird. Zitate helfen Ihnen dabei, Glaubwürdigkeit zu schaffen und Plagiatismus zu verhindern. Zitate helfen den Lesern, die Quelle zu finden und die im Text dargestellten Informationen zu überprüfen.

In AEM Guides können Sie Zitate hinzufügen oder importieren und auf Ihre Inhalte anwenden. Sie können diese Zitate aus jeder Quelle von Büchern, Websites und Zeitschriften hinzufügen.

Nachdem Sie Ihre Zitate in Ihre Themen eingefügt haben, können Sie sie im Web-Editor in der Vorschau anzeigen. Sie können auch Inhalte mit Zitaten mithilfe des nativen PDF veröffentlichen.

![In einem Bedienfeld aufgelistete Zitate](assets/citation-panel.png){width="300" align="left"}

*Zeigen Sie die Liste der Zitate im Fenster &quot;Zitate&quot;an.*

Weitere Informationen finden Sie unter [Zitate in Ihrem Inhalt hinzufügen und verwalten](../user-guide/web-editor-apply-citations.md).


## Publish in ein Inhaltsfragment

Inhaltsfragmente sind separate Inhaltsfragmente in AEM. Sie sind strukturierte Inhalte, die auf einem Inhaltsmodell basieren. Inhaltsfragmente sind reine Inhalte ohne Design- oder Layoutinformationen. Sie können unabhängig von den von AEM unterstützten Kanälen erstellt und verwaltet werden. Die Modularität und Wiederverwendbarkeit der Inhaltsfragmente führt zu mehr Flexibilität, Konsistenz, Effizienz und einfacherer Verwaltung.

Jetzt bietet AEM Guides die Möglichkeit, ein Thema oder die Elemente innerhalb eines Themas in einem Inhaltsfragment zu veröffentlichen. Sie können eine JSON-basierte Zuordnung zwischen einem Thema und einem Inhaltsfragmentmodell erstellen. Verwenden Sie diese Zuordnung, um Inhalte in einigen oder allen Elementen innerhalb eines Themas für ein Inhaltsfragment zu veröffentlichen.

Nutzen Sie die Leistungsfähigkeit von AEM Guides und Inhaltsfragmenten und verwenden Sie Inhaltsfragmente auf jeder AEM. Sie können die Details auch über APIs extrahieren, die von Inhaltsfragmenten unterstützt werden.

![Option zum Veröffentlichen des Inhaltsfragments](assets/content-fragment-publish.png){width="550" align="left"}

*Publish eines Themas für ein Inhaltsfragment.*

Weitere Informationen finden Sie unter [Publish zu einem Inhaltsfragment](../user-guide//publish-content-fragment.md).

## Verbesserungen überprüfen

AEM Guides bietet jetzt eine verbesserte Überprüfungsfunktion mit den folgenden Funktionen:

### Suchüberprüfungsthemen

Die Durchführung von Überprüfungen ist ein wichtiges Merkmal von AEM Guides. Es hilft den Validierungsverantwortlichen, die ihnen zugewiesenen Dokumente zu überprüfen.
Jetzt können Sie nach einem Thema suchen, indem Sie einen Teil des Textes des Titels oder Dateipfads in die Suchleiste der Themenansicht des Prüfungsbereichs eingeben. Sie können auch alle Themen anzeigen oder Themen mit Kommentaren anzeigen. Standardmäßig können Sie alle in der Prüfungsaufgabe vorhandenen Themen anzeigen. Weitere Informationen finden Sie unter [Prüfungsthemen](../user-guide/review-topics.md).

![Suchen in einem Prüfungsthemen-Bereich](assets/review-search-topic.png){width="800" align="left"}

*Suchen Sie ein Prüfungsthema im Prüfungsbereich.*



## Guides Extension Framework

Erstellen Sie benutzerdefinierte Pakete zusätzlich zu AEM Guides, um die Erweiterbarkeit mithilfe des AEM Guides Extension Framework bereitzustellen. Diese Pakete sind für Entwickler und Berater nützlich und bieten ihnen Erweiterbarkeit für die Komponenten im Editor. Sie können Schaltflächen, Dialogfelder und Dropdown-Menüs auswählen und benutzerdefinierte JavaScript hinzufügen, die einfach mit der AEM Guides-Benutzeroberfläche interagieren können.



## Native PDF-Verbesserungen

Die folgenden nativen PDF-Verbesserungen wurden in der Version vom September 2023 vorgenommen, um AEM Guides zu einem robusteren Produkt zu machen:



### Sortieren von Seiten in der PDF-Ausgabe

Sie können die folgenden Bereiche in Ihrer PDF ein- oder ausblenden und auch die Reihenfolge anordnen, in der sie in Ihrer endgültigen PDF-Ausgabe angezeigt werden sollen:

* IHV
* Kapitel und Themen
* Bildliste
* Tabellenliste
* Index
* Glossar
* Zitat
* Seitenlayouts

Wenn Sie in Ihrer PDF-Ausgabe keinen bestimmten Bereich anzeigen möchten, können Sie dies verbergen, indem Sie den Umschalter ausschalten.

Weitere Informationen finden Sie unter [Seitenreihenfolge](../native-pdf/components-pdf-template.md#page-order).

### Seiten zusammenführen

In einer nativen PDF-Ausgabe beginnen standardmäßig alle Bereiche auf einer neuen Seite. Jetzt können Sie einen Abschnitt mit der vorherigen Seite oder der nächsten Seite zusammenführen. Dadurch wird der -Abschnitt in Weiterführung mit der ausgewählten PDF-Ausgabe veröffentlicht und es gibt keinen Seitenumbruch dazwischen.

Weitere Informationen finden Sie in der Funktionsbeschreibung für die Funktion **Seiten zusammenführen** im Abschnitt [Seitenreihenfolge](../native-pdf/components-pdf-template.md#page-order) .

### Jedes Kapitel von der aktuellen Seite aus starten

Sie können die grundlegenden Konfigurationseinstellungen für den Start eines Kapitels von einer ungeraden oder geraden Seite, die TOC-Struktur und das Füllzeichenzeilenformat für die TOC-Einträge festlegen.

Jetzt können Sie auch ein Kapitel von der aktuellen Seite aus starten. Wenn Sie sich dafür entscheiden, werden alle Kapitel als Fortsetzung und ohne Seitenumbrüche veröffentlicht. Wenn ein Kapitel beispielsweise mitten auf Seite 15 endet, beginnt das nächste Kapitel auch auf der 15. Seite selbst.

Weitere Informationen finden Sie in der Beschreibung der Registerkarte **Allgemein** unter [Erweiterte PDF-Einstellungen](../native-pdf/components-pdf-template.md#advanced-pdf-settings-advanced-pdf-settings).

### Statische Seiten

Sie können auch benutzerdefinierte Seitenlayouts erstellen und diese als statische PDF-Seiten veröffentlichen. Auf diese Weise können Sie statischen Inhalt wie Notizen oder leere Seiten hinzufügen.

Weitere Informationen finden Sie in der Beschreibung der Funktion **Statische Seiten** im Abschnitt [Seitenreihenfolge](../native-pdf/components-pdf-template.md#page-order) .


### Variablen in Querverweisen

Sie können Variablen verwenden, um einen Querverweis zu definieren. Wenn Sie eine Variable verwenden, wird ihr Wert aus den Eigenschaften ausgewählt.

Jetzt können Sie auch {figure} und {table} verwenden.
Verwenden Sie {figure}, um der Zahl einen Querverweis hinzuzufügen. Sie wählt die Zahl aus den automatischen Nummernstilen aus, die Sie für die Beschriftung definiert haben.

Verwenden Sie {table} , um der Tabellennummer einen Querverweis hinzuzufügen. Die Tabellennummer wird aus den automatischen Nummernstilen ausgewählt, die Sie für die Beschriftung definiert haben.

Weitere Informationen finden Sie unter [Querverweise](../native-pdf/components-pdf-template.md##cross-references).



### Neugestaltung des CSS-Editors

Jetzt wurde der CSS-Editor für ein besseres Benutzererlebnis mit Selektoren und Stileigenschaften neu gestaltet.

#### Verbesserung des Dialogfelds &quot;Stil hinzufügen&quot;

Sie können jetzt benutzerdefinierte Selektoren verwenden, um komplexe Stile hinzuzufügen. Mit dem neuen Selektor-Feld können Sie benutzerdefinierte Selektoren neben der Kombination aus Klasse, Tag und Pseudo-Klasse hinzufügen. Sie können beispielsweise den Stil `table a.link` für alle Hyperlinks in einer Tabelle erstellen.

![Hinzufügen von Stilen in den nativen PDF-Vorlagen](assets/add-styles-native-pdf.png){width="300" align="left"}

*Fügen Sie die Details für den neuen Stil hinzu.*

#### Anpassen von Stileigenschaften

AEM Guides stellt Ihnen jetzt ein neues Eigenschaftenbedienfeld unter dem Vorschauabschnitt für Stile vor. Sie können die Eigenschaften der Stile effizienter und schneller im Eigenschaftenbereich bearbeiten.


## Unterstützung für mehrere Themendefinitionen in einer einzelnen Auflistungsdefinition

Sie können jetzt eine oder mehrere Betreffdefinitionen in einer Zuordnung und die Auflistungsdefinitionen in einer anderen Zuordnung definieren und dann die Zuordnungsreferenz hinzufügen. Die Verweise auf die Betreffauflistung werden in derselben Zuordnung oder der referenzierten Zuordnung aufgelöst.

Sie können jetzt auch Bedingungen definieren und sie auf einige spezifische Elemente in einem Thema anwenden.  Die Bedingungen sind nur für diese spezifischen Elemente sichtbar, nicht für alle anderen Elemente.

Weitere Informationen zum Umgang mit hierarchischen Definitionen von Betreffdefinitionen und Auflistungen finden Sie in der Funktionsbeschreibung des Betreffschemas im Abschnitt [Linkes Bedienfeld](../user-guide/web-editor-features.md#id2051EA0M0HS) .





## Auswählen aller Vorgaben in einer Map Collection

Sie können nicht nur eine einzelne Vorgabe und alle Ordnerprofilvorgaben aktivieren, sondern auch alle Vorgaben für eine DITA-Zuordnung in einem Schritt aktivieren.
![Bearbeiten einer Zuordnungssammlung](assets/edit-map-collection-cs.png){width="800" align="left"}\
*Wählen Sie alle Vorgaben in einer Zuordnungssammlung aus.*

Weitere Informationen finden Sie unter [Verwenden der Zuordnungssammlung für die Ausgabegenerierung](../user-guide/generate-output-use-map-collection-output-generation.md).


## Native PDF-Unterstützung im Bulk Publish Dashboard


Mit der Massenaktivierungsfunktion von AEM Guides können Sie Ihre Inhalte schnell und einfach von der Inhaltserstellung bis zur Veröffentlichungsinstanz aktivieren. Auf der Massen-Aktivierungskarte können Sie die native PDF-Ausgabevorgabe, die AEM-Site, PDF, HTML5, benutzerdefinierte und JSON-Ausgabe einbeziehen.
Weitere Informationen finden Sie unter [Massenaktivierung veröffentlichter Inhalte](../user-guide/conf-bulk-activation.md).

## Verbessertes Werkzeug zum Verschieben von Stapeln

Als Administrator können Sie jetzt das verbesserte Werkzeug zum Verschieben von Massen-Dateien verwenden, um Ordner mit vielen Dateien von einem Speicherort zum anderen zu verschieben.
Sie können das Dialogfeld Datei durchsuchen verwenden, um die Quellordner auszuwählen, die Sie verschieben möchten. Sie können auch nach dem Zielspeicherort suchen, um die Quellordner zu verschieben. Wählen Sie ![Infosymbol](assets/info-icon.svg) {width="25" align="left"} neben einem Feld, um weitere Informationen dazu anzuzeigen.

Weitere Informationen finden Sie unter [Verschieben von Dateien in großen Mengen](../user-guide/authoring-file-management.md#move-files-bulk).


## Erweiterte Funktionen zur Vorschau im Kontextmenü

Verwenden Sie das Kontextmenü, um die Datei (dita, .xml, audio, video oder image) schnell in der Vorschau anzuzeigen, ohne sie zu öffnen. Sie können jetzt die Größe des Vorschaufensters ändern. Wenn der Inhalt einen Verweis-Link enthält, können Sie ihn auswählen, um ihn in einer neuen Registerkarte zu öffnen.

![Vorschaufenster ](assets/quick-preview_cs.png){width="800" align="left"}

*Zeigen Sie eine Vorschau der Datei im Bereich an.*

Weitere Informationen zum Kontextmenü finden Sie in der Beschreibung der Funktion **Optionen für eine Datei** im Abschnitt [Linkes Bedienfeld](../user-guide/web-editor-features.md#id2051EA0M0HS) .


## Verwenden Sie Variablen für das aktuelle Datum und die aktuelle Uhrzeit in den Optionen &quot;Zielpfad&quot;, &quot;Site-Name&quot;oder &quot;Dateiname&quot;

Beim Generieren von Ausgaben in AEM Site oder PDF können Sie Variablen zum Festlegen der Optionen **Zielpfad**, **Site-Name** oder **Dateiname** verwenden. Sie können jetzt auch die Variablen `${system_date}`und `${system_time}` verwenden. Mithilfe dieser Variablen können Sie diesen Optionen das aktuelle Datum und die aktuelle Uhrzeit anhängen.

Erfahren Sie, wie Sie [Variablen zum Festlegen der Optionen &quot;Zielpfad&quot;, &quot;Site-Name&quot;oder &quot;Dateiname&quot;verwenden](../user-guide/generate-output-use-variables.md).
