---
title: Versionshinweise zu | Neue Funktionen in Adobe Experience Manager Guides Version 4.3.0
description: Erfahren Sie mehr über die neuen und erweiterten Funktionen der Version 4.3.0 von Adobe Experience Manager Guides
exl-id: 36decbf0-ec9d-43e2-99b7-85b0f9a87bc1
feature: What's New
role: Leader
source-git-commit: 5a444e88b0adba7fa3d498437df39b729b10b5eb
workflow-type: tm+mt
source-wordcount: '2655'
ht-degree: 0%

---

# Neue Funktionen in Version 4.3.0 von Adobe Experience Manager Guides (Juli 2023)

Dieser Artikel behandelt die neuen und erweiterten Funktionen in Version 4.3.0 von Adobe Experience Manager Guides (später *AEM Guides*).

Weitere Informationen zu den Upgrade-Anweisungen, der Kompatibilitätsmatrix und den in dieser Version behobenen Problemen finden Sie unter [Versionshinweise](./release-notes-4-3.md).


## Herstellen einer Verbindung zu einer Datenquelle und Einfügen von Daten in die Themen

Jetzt können Sie mithilfe von vorkonfigurierten Connectoren von AEM Guides schnell eine Verbindung zu Ihren Datenquellen herstellen. Wenn Sie eine Verbindung zu einer Datenquelle herstellen, können Sie Ihre Informationen mit der Quelle synchronisieren. Alle Aktualisierungen der Daten werden automatisch übernommen, was AEM Guides zu einem echten Content-Hub macht. Mit dieser Funktion sparen Sie Zeit und Mühe beim manuellen Hinzufügen oder Kopieren der Daten.

AEM Guides ermöglicht es Ihrem Administrator, die vorkonfigurierten Connectoren für JIRA- und SQL-Datenbanken (MySQL, PostgreSQL, SQL Server, SQLite) zu konfigurieren. Sie können auch andere Connectoren hinzufügen, indem sie die Standardschnittstellen erweitern.
Nach dem Hinzufügen können Sie die konfigurierten Connectoren anzeigen, die im Web-Editor unter dem Bedienfeld „Datenquellen“ aufgeführt sind.

<img src="assets/data-sources.png" alt="Liste der Datenquellen im Bedienfeld" width="300">

Erstellen Sie ein Inhaltsfragment, um die Daten aus einer verbundenen Datenquelle abzurufen. Anschließend können Sie die Daten in Ihre Themen einfügen und bearbeiten. Nachdem Sie einen Inhaltsfragment-Generator erstellt haben, können Sie ihn wiederverwenden, um die Daten in ein beliebiges Thema einzufügen.

Jetzt können Sie auch ein Thema aus einer verbundenen Datenquelle erstellen. Ein Thema kann Daten in verschiedenen Formaten enthalten, z. B. Tabellen, Listen und Absätze. Außerdem können Sie eine DITA-Karte für alle Themen erstellen. Beim Abrufen aus einer Datenquelle können Sie dem Thema Metadaten zuordnen.

Weitere Informationen finden Sie unter [Verwenden von Daten aus Ihrer Datenquelle](../user-guide/web-editor-content-snippet.md).

## Hinzufügen von Zitaten zu Inhalten

Zitate sind Verweise auf die Quelle von Informationen, die Ihrem Inhalt hinzugefügt werden. Zitate helfen Ihnen dabei, Glaubwürdigkeit aufzubauen und Plagiate zu verhindern. Zitate helfen den Lesern, die Quelle zu finden und die Informationen im Text zu überprüfen.

In AEM Guides können Sie Zitate hinzufügen oder Zitate importieren und sie auf Ihre Inhalte anwenden. Sie können diese Zitate aus jeder Quelle von Büchern, Websites und Zeitschriften hinzufügen.

Nachdem Sie Ihre Zitate in Ihre Themen eingefügt haben, können Sie sie im Web-Editor in der Vorschau anzeigen. Sie können auch Inhalte mit Zitaten veröffentlichen, indem Sie natives PDF verwenden.

![In einem Bedienfeld aufgeführte Zitate](assets/citation-panel.png){width="300" align="left"}


Weitere Informationen finden Sie unter [Hinzufügen und Verwalten von Zitaten in Ihren Inhalten](../user-guide/web-editor-apply-citations.md).

## Publish zu einem Inhaltsfragment

Inhaltsfragmente sind separate Inhaltselemente in AEM. Es handelt sich um strukturierte Inhalte, die auf einem Inhaltsmodell basieren. Inhaltsfragmente sind reine Inhalte ohne Design- oder Layout-Informationen. Sie können unabhängig von den von AEM unterstützten Kanälen erstellt und verwaltet werden. Die Modularität und Wiederverwendbarkeit der Inhaltsfragmente führt zu mehr Flexibilität, Konsistenz, Effizienz und einfacherem Management.

AEM Guides bietet jetzt die Möglichkeit, ein Thema oder die Elemente innerhalb eines Themas in einem Inhaltsfragment zu veröffentlichen. Sie können eine JSON-basierte Zuordnung zwischen einem Thema und einem Inhaltsfragmentmodell erstellen. Verwenden Sie diese Zuordnung, um Inhalte, die in einigen oder allen Elementen innerhalb eines Themas vorhanden sind, in einem Inhaltsfragment zu veröffentlichen.

Nutzen Sie die Leistungsfähigkeit von AEM Guides und Inhaltsfragmenten und verwenden Sie Inhaltsfragmente auf jeder AEM-Site. Sie können die Details auch über APIs extrahieren, die von Inhaltsfragmenten unterstützt werden.

![Option zum Veröffentlichen des Inhaltsfragments](assets/content-fragment-publish.png){width="550" align="left"}


## Verbesserungen bei Überprüfungen

AEM Guides bietet jetzt eine verbesserte Überprüfungsfunktion mit den folgenden Funktionen:

### Überprüfungsbereich zur Präsentation von Überprüfungsprojekten und der aktiven Überprüfungsaufgaben

Jetzt macht AEM Guides Ihre Rezensionen nahtloser. Sie enthält das Bedienfeld Überprüfungen im Web-Editor. Im Bedienfeld Überprüfungen werden alle Überprüfungsprojekte und die aktiven Überprüfungsaufgaben innerhalb der Überprüfungsprojekte angezeigt, an denen Sie beteiligt sind.

Als Autor können Sie mit dieser Funktion die Prüfungsaufgaben einfach öffnen, die Kommentare anzeigen und die Kommentare schnell in einer zentralen Ansicht bearbeiten.
![](assets/active-review-task-comments.png){width="800" align="left"}
Weitere Informationen finden Sie in der **Funktionsbeschreibung** im Abschnitt [Linkes Bedienfeld](../user-guide/web-editor-features.md#id2051EA0M0HS).

### Prüfungsthemen suchen

Die Durchführung von Überprüfungen ist ein wichtiges Merkmal von AEM Guides. Dies hilft den Reviewern bei der Überprüfung der ihnen zugewiesenen Dokumente .
Jetzt können Sie nach einem Thema suchen, indem Sie einen Teil des Textes des Titels oder Dateipfads in die Suchleiste der Themenansicht des Review-Panels eingeben. Sie können auch alle Themen anzeigen oder Themen mit Kommentaren anzeigen. Standardmäßig können Sie alle in der Prüfungsaufgabe vorhandenen Themen anzeigen.


![Suchen in einem Bedienfeld mit Prüfungsthemen](assets/review-search-topic.png){width="800" align="left"}

Weitere Informationen finden Sie unter [Themen &#x200B;](../user-guide/review-topics.md).

## Handbücher zum Erweiterungs-Framework

Erstellen Sie benutzerdefinierte Pakete auf AEM Guides, um die Erweiterbarkeit mithilfe des AEM Guides-Erweiterungs-Frameworks zu gewährleisten. Diese Pakete sind für Entwickler und Berater nützlich und bieten ihnen Erweiterbarkeit für die Komponenten im Editor. Sie können Schaltflächen, Dialogfelder und Dropdown-Listen auswählen und benutzerdefinierte JavaScript hinzufügen, die einfach mit der AEM Guides-Benutzeroberfläche interagieren können.



## Native PDF-Verbesserungen

Die folgenden nativen PDF-Verbesserungen wurden in Version 4.3.0 vorgenommen, um AEM Guides zu einem robusteren Produkt zu machen:

### Unterstützung für Sprachvariablen

AEM Guides unterstützt Sprachvariablen. Sie können Sprachvariablen verwenden, um eine lokalisierte Version der vordefinierten Kennzeichnungen wie „Hinweis“, „Vorsicht“ und „Warnung“ oder „Statischer Text“ in der PDF-Ausgabe zu definieren.
Sie können die Sprachvariablen oder die lokalisierte Version der Kennzeichnungen den entsprechenden Abschnitten in Ihrer PDF-Ausgabe und in den Ausgabevorlagen hinzufügen.

#### Sprachvariablen in der PDF-Ausgabe

Sie können die Sprachvariablen verwenden, um lokalisierte Beschriftungen für Elemente wie „Hinweis“, „Vorsicht“ und „Warnung“ zu definieren. Sie können den Wert für diese Variablen in einer oder mehreren Sprachen aktualisieren, und dann wird der lokalisierte Wert automatisch in der PDF-Ausgabe ausgewählt.
Beispielsweise können Sie die Beschriftung Hinweis in Ihrer PDF-Ausgabe wie folgt darstellen:

* Englisch: Hinweis
* Französisch: Remarque
* Deutsch: Hinweis

#### Sprachvariablen in den Ausgabevorlagen

Wenn Sie die PDF-Ausgabe in verschiedenen Sprachen erstellen wollten, mussten Sie verschiedene PDF-Vorlagen erstellen, die lokalisierten Text für jede Sprache enthalten. Mit der Sprachvariablen-Funktion müssen Sie die Vorlage nur noch einmal erstellen. Anschließend können Sie für jeden statischen Text, den Sie lokalisieren müssen, entsprechende Sprachvariablen erstellen und in Ihrer Vorlage verwenden.
Sie können Sprachvariablen für längeren Text erstellen, z. B. einen ganzen Satz oder sogar einen Absatz. Sie können auch Stile anwenden und HTML-Markup verwenden, um diese Sprachvariablen zu formatieren.

Weitere Informationen finden Sie unter [Unterstützung für Sprachvariablen](../native-pdf/native-pdf-language-variables.md).

### Hinzufügen eines Wasserzeichens zum PDF der Ausgabe für Entwurfsdokumente

Jetzt können Sie der PDF-Ausgabe des noch nicht genehmigten Dokuments ein Wasserzeichen hinzufügen. Dieses Wasserzeichen wird nicht angezeigt, wenn Sie die PDF für das Dokument im Dokumentstatus „Genehmigt“ generieren. Sie können beispielsweise einen Wasserzeichenentwurf für Ihre PDF-Ausgabe hinzufügen.

Weitere Informationen finden Sie unter [Hinzufügen eines Wasserzeichens zur PDF-Ausgabe für Entwurfsdokumente](../native-pdf/use-javascript-content-style.md#watermark-draft-document).

### Verwendung von AEM-Metadaten in PDF-Layouts

Metadaten sind die Beschreibung oder Definition Ihres Inhalts. Diese Metadaten werden in Ihrem Quell-DITA-Map-Inhalt gespeichert.

Jetzt können Sie in AEM Guides auch die Metadateneigenschaften Ihrer Assets auswählen und sie zum Seiten-Layout hinzufügen. AEM Guides wählt diese Metadateneigenschaften Ihrer Assets aus und veröffentlicht sie in Ihrer PDF-Ausgabe.


![Hinzufügen von Metadaten für native PDF](assets/native-pdf-metadata-asset.png){width="300" align="left"}

>[!NOTE]
>
> AEM Guides unterstützt auch die Metadateneigenschaften für Ihre DITA-Zuordnungen.

Weitere Informationen finden Sie unter [Felder und Metadaten hinzufügen](../native-pdf/design-page-layout.md#add-fields-metadata).


### Sortieren von Seiten in der PDF-Ausgabe

Sie können die folgenden Abschnitte auf Ihrem PDF ein- oder ausblenden und auch die Reihenfolge festlegen, in der sie in der endgültigen PDF-Ausgabe angezeigt werden sollen:

* IHV
* Kapitel und Themen
* Abbildungsverzeichnis
* Liste der Tabellen
* Index
* Glossar
* Zitierung
* Seiten-Layouts

Wenn Sie einen bestimmten Abschnitt in Ihrer PDF-Ausgabe nicht anzeigen möchten, können Sie dies ausblenden, indem Sie den Umschalter ausschalten.

Weitere Informationen finden Sie unter [Seitenreihenfolge](../native-pdf/components-pdf-template.md#page-order).

### Zusammenführen von Seiten

Bei einer nativen PDF-Ausgabe beginnen standardmäßig alle Abschnitte auf einer neuen Seite. Jetzt können Sie einen Abschnitt mit seiner vorherigen Seite oder der nächsten Seite zusammenführen. Dadurch wird der Abschnitt in Fortsetzung mit der ausgewählten Seite in der PDF-Ausgabe veröffentlicht, und es gibt keinen Seitenumbruch dazwischen.

Weitere Informationen finden Sie in der Beschreibung der Funktion „Seiten zusammenführen“ im Abschnitt [Seitenreihenfolge](../native-pdf/components-pdf-template.md#page-order).

### Statische Seiten

Sie können auch benutzerdefinierte Seiten-Layouts erstellen und als statische Seiten in der PDF-Ausgabe veröffentlichen. Auf diese Weise können Sie beliebige statische Inhalte wie Anmerkungen oder leere Seiten hinzufügen.

Weitere Informationen finden Sie in der Beschreibung der Funktion für statische Seiten im Abschnitt [Seitenreihenfolge](../native-pdf/components-pdf-template.md#page-order).


### Variablen in Querverweisen

Sie können Variablen verwenden, um einen Querverweis zu definieren. Wenn Sie eine Variable verwenden, wird deren Wert aus den Eigenschaften ausgewählt.

Jetzt können Sie auch {figure} und {table} verwenden.
Verwenden {figure}, um einen Querverweis auf die Abbildungsnummer hinzuzufügen. Die Zahl wird aus den Stilen für automatische Zahlen ausgewählt, die Sie für „figcaption“ definiert haben.

Verwenden Sie {table} , um einen Querverweis zur Tabellennummer hinzuzufügen. Die Tabellennummer wird aus den automatischen Nummerierungsstilen ausgewählt, die Sie für Beschriftung definiert haben.

Weitere Informationen finden Sie unter [Querverweise](../native-pdf/components-pdf-template.md##cross-references).

### Beliebiges Kapitel von der aktuellen Seite starten

Sie können die grundlegenden Konfigurationseinstellungen für den Start eines Kapitels von einer ungeraden oder geraden Seite aus festlegen, die Inhaltsverzeichnisstruktur festlegen und das Format der Führungslinie für die Inhaltsverzeichniseinträge definieren.

Jetzt können Sie auch ein Kapitel von der aktuellen Seite aus starten. Wenn Sie dies wählen, werden alle Kapitel in Fortsetzung ohne Seitenumbrüche veröffentlicht. Wenn beispielsweise ein Kapitel in der Mitte von Seite 15 endet, beginnt das nächste Kapitel ebenfalls von der 15. Seite selbst.


### Zugriff auf temporäre HTML-Dateien beim Generieren der nativen PDF-Ausgabe

Jetzt können Sie mit AEM Guides die temporären HTML-Dateien herunterladen, die beim Generieren der nativen PDF-Ausgabe erstellt wurden. Wählen Sie in den Ausgabevorgabeneinstellungen die Option zum Herunterladen der temporären Dateien aus.  Mit AEM Guides können Sie dann die temporären Dateien herunterladen, die beim Generieren der Ausgabe mit dieser Vorgabe erstellt wurden.

Diese Funktion bietet bessere Einblicke in den Generierungsprozess mit Zugriff auf Zwischenstile und -Layouts und hilft Ihnen, Ihre CSS-Stile entsprechend Ihren Anforderungen zu korrigieren oder zu ändern.

![Das Dialogfeld „Erweiterte Einstellungen“ der nativen PDF-Datei](assets/native-pdf-advanced-settings.png){width="800" align="left"}

Weitere Informationen finden Sie unter [Erstellen einer PDF-Ausgabevorgabe](../web-editor/native-pdf-web-editor.md#create-output-preset).


### Neugestaltung des CSS-Editors

Jetzt wurde der CSS-Editor neu gestaltet, um das Benutzererlebnis mit Selektoren und Stileigenschaften zu verbessern.

#### Verbesserung des Dialogfelds „Stil hinzufügen“

Sie können jetzt benutzerdefinierte Selektoren verwenden, um komplexe Stile hinzuzufügen. Mit dem neuen Selektorfeld können Sie neben der Kombination aus Klasse, Tag und Pseudoklasse auch benutzerdefinierte Selektoren hinzufügen. Sie können beispielsweise `table a.link` Stil für alle Hyperlinks in einer Tabelle erstellen.

![Hinzufügen von Stilen in nativen PDF-Vorlagen](assets/add-styles-native-pdf.png){width="300" align="left"}

#### Stileigenschaften anpassen

Jetzt führt AEM Guides Sie in ein neues Eigenschaftenbedienfeld unter dem Vorschauabschnitt für Stile ein. Sie können die Eigenschaften der Stile effizienter und schneller über das Bedienfeld Eigenschaften bearbeiten.


## Umbenennen und Verschieben von Dateien in der Repository-Ansicht

Jetzt können Sie eine Datei auch über das Repository-Bedienfeld umbenennen oder verschieben. Diese Funktion ist praktisch und hilft bei der einfachen Verwaltung Ihrer Dateien über das Repository-Bedienfeld. Sie können eine Datei auswählen und sie über das Menü **Optionen** für die ausgewählte Datei umbenennen oder verschieben. AEM Guides zeigt eine Erfolgsmeldung an, wenn Sie eine Datei verschieben oder umbenennen.

![Optionsmenü einer Datei](assets/rename-move-assets.png){width="550" align="left"}

Weitere Informationen zum Optionen-Menü einer Datei finden Sie in der **Repository-Ansicht** Funktionsbeschreibung im Abschnitt [Linkes Bedienfeld](../user-guide/web-editor-features.md#id2051EA0M0HS).

## Bericht zu fehlerhaften Links im Web-Editor

Mit AEM Guides können Sie die Vollständigkeit Ihrer technischen Dokumente überprüfen und Berichte über den Web-Editor generieren. Ab jetzt Version Juni 2023 bietet Ihnen AEM Guides die Funktion zum Anzeigen und Beheben von fehlerhaften Links. Dies ist ein nützlicher Bericht, der Ihnen bei der Verwaltung Ihrer fehlerhaften Links hilft. Sie können die beschädigten Links in Ihrer DITA-Karte einfach anzeigen und auch beheben.
![Bericht zu fehlerhaften Links](assets/broken-link-report.png){width="800" align="left"}

Nachdem Sie einen Link korrigiert haben, wird er nicht mehr unter der Liste der fehlerhaften Links angezeigt.

Weitere Informationen finden Sie unter [Anzeigen und Beheben von fehlerhaften Links](../user-guide/reports-web-editor.md#report-broken-links).

## Verbesserungen am Schematron

### Verwenden Sie Berichtsanweisungen, um im Schematron nach Regeln zu suchen

AEM Guides unterstützt jetzt auch die Report Statements mit dem Schematron. Eine Berichtsanweisung erzeugt eine Meldung, wenn eine Testanweisung als „true“ ausgewertet wird. Wenn Sie beispielsweise möchten, dass die Kurzbeschreibung maximal 150 Zeichen lang ist, können Sie eine Berichtsanweisung definieren, um die Themen zu überprüfen, bei denen die Kurzbeschreibung mehr als 150 Zeichen lang ist.

Weitere Details finden Sie unter [Verwenden von Assert- und Report-Anweisungen, um nach Regeln zu suchen](../user-guide/support-schematron-file.md#schematron-assert-report).

### Verwenden von Regex-Ausdrücken

Sie können auch Regex-Ausdrücke verwenden, um eine Regel mit matches()-Funktion zu definieren und dann eine Validierung mithilfe der Schematron-Datei durchzuführen.

Weitere Informationen finden Sie unter [Verwenden von Regex-Ausdrücken](../user-guide/support-schematron-file.md#schematron-assert-report).


### Abstrakte Muster definieren

AEM Guides unterstützt auch abstrakte Muster in Schematron. Sie können generische abstrakte Muster definieren und diese abstrakten Muster wiederverwenden. Abstrakte Muster können Ihr Schematron-Schema vereinfachen und Ihnen auch dabei helfen, Ihre Validierungslogik zu verwalten und zu aktualisieren.


Weitere Details finden Sie unter [Definieren abstrakter Muster](../user-guide/support-schematron-file.md#schematron-abstract-patterns).

## Unterstützung des XLIFF-Formats bei der Übersetzung

AEM Guides unterstützt auch das XLIFF-Format (XML Localization Interchange File Format) bei der Übersetzung. Jetzt können Sie auch wählen, **Neues XLIFF-Übersetzungsprojekt erstellen**, um den XML-Inhalt in das XLIFF-Format zu konvertieren. AEM Guides unterstützt XLIFF Version 1.2.

Mithilfe dieses Formats können Sie die Inhalte in das standardmäßige XLIFF-Format exportieren und sie dann den Übersetzungsdienstleistern bereitstellen. Weitere Informationen finden Sie unter [Übersetzungsprojekt erstellen](../user-guide/translate-documents-web-editor.md#create-translation-project).

![Typen von Übersetzungsprojekten](assets/translation-project-types.png){width="350" align="left"}


## Verbesserungen der Zuordnungssammlung

Mit einer Zuordnungssammlung können Sie mehrere Zuordnungen organisieren und stapelweise veröffentlichen. An der Zuordnungssammlung wurden viele neue Verbesserungen vorgenommen:

* Jetzt können Sie einer Zuordnungssammlung native PDF-Ausgabevorgaben hinzufügen und diese zum Generieren der PDF-Ausgabe verwenden.
* Sie können die von Ihrem Administrator erstellten globalen und Ordnerprofilvorgaben anzeigen und sie zum Generieren der PDF-Ausgabe verwenden.
* Jetzt können Sie nicht nur eine einzelne Vorgabe auswählen, sondern auch alle Ordnerprofilvorgaben für eine DITA-Zuordnung in einem Schritt aktivieren.
  ![Bearbeiten einer Zuordnungssammlung](assets/edit-map-collection.png){width="800" align="left"}

Weitere Informationen finden Sie unter [Zuordnungssammlung für die Ausgabegenerierung verwenden](../user-guide/generate-output-use-map-collection-output-generation.md).

## Native PDF-Unterstützung im Publish-Dashboard für Massenspeicher


Mit der Massenaktivierungsfunktion von AEM Guides können Sie Ihre Inhalte schnell und einfach von der Autoren- zur Veröffentlichungsinstanz aktivieren. In die Massenaktivierungszuordnung können die native PDF-Ausgabevorgabe, die AEM-Site-, PDF-, HTML5-, benutzerdefinierte und JSON-Ausgabe einbezogen werden.
Weitere Informationen finden Sie unter [Massenaktivierung veröffentlichter Inhalte](../user-guide/conf-bulk-activation.md).

## Verbessertes Tool für Massenverschiebung

Als Administrator können Sie jetzt das verbesserte Tool zum Verschieben von Massen verwenden, um Ordner mit vielen Dateien von einem Speicherort an einen anderen zu verschieben.
Sie können das Dialogfeld Datei durchsuchen verwenden, um die Quellordner auszuwählen, die verschoben werden sollen. Sie können auch zum Zielspeicherort navigieren, um die Quellordner zu verschieben. Wählen Sie ![Informationssymbol](assets/info-icon.svg) {width="25" align="left"} neben einem Feld aus, um weitere Informationen dazu anzuzeigen.

Weitere Informationen finden Sie unter [Dateien stapelweise verschieben](../user-guide/authoring-file-management.md#move-files-bulk).

## Bedienfeld „Favoriten“ verbessert

Mit AEM Guides können Sie eine Sammlung oder Favoritenliste Ihrer Dateien und Ordner erstellen und diese einfach verwenden. Das **„Optionen** ist jetzt auch im Bedienfeld &quot;**&quot;**. Sie können die ausgewählte Sammlung umbenennen oder sie aus dem Menü **Optionen** löschen. Sie können die Option **Aktualisieren** auswählen, um eine neue Liste der Dateien oder Ordner aus dem Repository abzurufen. Sie können die Ordnerinhalte auch in der Benutzeroberfläche von Assets anzeigen.

![Das Bedienfeld Favoriten](assets/favorites-options.png){width="650" align="left"}

>[!NOTE]
>
> Sie können die Liste auch mithilfe des Symbols **Aktualisieren** oben aktualisieren.

Weitere Informationen zum Menü **Optionen** einer Favoritensammlung finden Sie in der **Favoriten** Funktionsbeschreibung im Abschnitt [Linkes Bedienfeld](../user-guide/web-editor-features.md#id2051EA0M0HS).

## Zum Systemdesign wechseln

Sie können jetzt auch das Geräte-Design verwenden. Unter **Benutzereinstellungen** können Sie AEM Guides so konfigurieren, dass je nach Design Ihres Geräts automatisch zwischen hellen und dunklen Designs gewechselt wird.

![Benutzervoreinstellungen](assets/device-theme-user-preferences.png){width="550" align="left"}

Weitere Informationen finden Sie in der Beschreibung der Funktion **Benutzereinstellungen** im Abschnitt [Hauptsymbolleiste](../user-guide/web-editor-features.md#id2051EA0G05Z).
