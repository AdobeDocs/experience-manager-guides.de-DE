---
title: Versionshinweise | Neue Funktionen in Adobe Experience Manager Guides, Version Juni 2023
description: Erfahren Sie mehr über die neuen und verbesserten Funktionen in der Adobe Experience Manager Guides as a Cloud Service-Version vom Juni 2023.
exl-id: 625f9702-2b91-4622-9fec-282f47f1d7a6
feature: What's New
role: Leader
source-git-commit: 6d8c01f20f7b59fed92c404561b647d9ebecb050
workflow-type: tm+mt
source-wordcount: '1212'
ht-degree: 0%

---

# Neue Funktionen in der Adobe Experience Manager Guides as a Cloud Service-Version vom Juni 2023

In diesem Artikel werden die neuen und verbesserten Funktionen in der Adobe Experience Manager Guides-Version vom Juni 2023 (später als *AEM Guides as a Cloud Service* bezeichnet) behandelt.

Weitere Informationen zu den Upgrade-Anweisungen, der Kompatibilitätsmatrix und den in dieser Version behobenen Problemen finden Sie unter [Versionshinweise](release-notes-2023-6-0.md).

## Bericht zu fehlerhaften Links im Web-Editor

Mit AEM Guides können Sie die Vollständigkeit Ihrer technischen Dokumente überprüfen und Berichte aus dem Web-Editor erstellen. AEM Guides bietet Ihnen jetzt in der Version vom Juni 2023 die Möglichkeit, fehlerhafte Links anzuzeigen und zu reparieren. Dies ist ein nützlicher Bericht, der Ihnen bei der Verwaltung Ihrer fehlerhaften Links hilft. Sie können die fehlerhaften Links in Ihrer DITA-Zuordnung einfach anzeigen und sie auch beheben.
![](assets/broken-link-report.png){width="800" align="left"}

Wenn Sie einen Link korrigieren, wird er nicht unter der Liste der fehlerhaften Links angezeigt.

Weitere Informationen finden Sie unter [Anzeigen und Korrigieren von fehlerhaften Links](../user-guide/reports-web-editor.md#report-broken-links).

## Umbenennen und Verschieben von Dateien in der Repository-Ansicht

Jetzt können Sie eine Datei auch umbenennen oder aus dem Repository-Bereich verschieben. Diese Funktion ist praktisch und erleichtert die Verwaltung Ihrer Dateien über das Repository-Bedienfeld. Sie können eine Datei auswählen und sie über das Menü **Optionen** für die ausgewählte Datei umbenennen oder verschieben. AEM Guides zeigt eine Erfolgsmeldung an, wenn Sie eine Datei verschieben oder umbenennen.

![](assets/rename-move-assets.png){width="650" align="left"}

Weitere Informationen zum Menü &quot;Optionen&quot;einer Datei finden Sie in der Beschreibung der Funktion **Repository-Ansicht** im Abschnitt [Linkes Bedienfeld](../user-guide/web-editor-features.md#id2051EA0M0HS) .

## Native PDF-Verbesserungen

### Wasserzeichen zur PDF-Ausgabe für Entwürfe hinzufügen

Jetzt können Sie ein Wasserzeichen zur PDF-Ausgabe des Dokuments hinzufügen, das noch nicht genehmigt wurde. Dieses Wasserzeichen wird nicht angezeigt, wenn Sie die PDF für das Dokument im Dokumentstatus &quot;Genehmigt&quot;generieren. Sie können beispielsweise einen Wasserzeichenentwurf für Ihre PDF-Ausgabe hinzufügen.

Weitere Informationen finden Sie unter [Hinzufügen eines Wasserzeichens zur PDF-Ausgabe für Entwurfsdokumente](../native-pdf/use-javascript-content-style.md#watermark-draft-document).

### Unterstützung für Sprachvariablen

AEM Guides unterstützt Sprachvariablen. Sie können Sprachvariablen verwenden, um eine lokalisierte Version der vordefinierten Beschriftungen wie Hinweis, Vorsicht und Warnung oder statischen Text in der PDF-Ausgabe zu definieren.
Sie können die Sprachvariablen oder die lokalisierte Version der Titel den entsprechenden Abschnitten in Ihrer PDF-Ausgabe und in den Ausgabevorlagen hinzufügen.

#### Sprachvariablen in der PDF-Ausgabe

Sie können die Sprachvariablen verwenden, um lokalisierte Beschriftungen für Elemente wie Hinweis, Vorsicht und Warnung zu definieren. Sie können den Wert für diese Variablen in einer oder mehreren Sprachen aktualisieren und dann wird der lokalisierte Wert automatisch in der PDF-Ausgabe ausgewählt.
Beispielsweise können Sie die Beschriftung Notiz in Ihrer PDF-Ausgabe wie folgt darstellen:

* Englisch: Hinweis
* Französisch: Remarque
* Deutsch: Verweis

#### Sprachvariablen in den Ausgabevorlagen

Wenn Sie die PDF-Ausgabe in verschiedenen Sprachen erstellen wollten, mussten Sie für jede Sprache verschiedene PDF-Vorlagen mit lokalisiertem Text erstellen. Mit der Sprachvariablen-Funktion müssen Sie die Vorlage nur einmal erstellen. Anschließend können Sie für jeden statischen Text, den Sie lokalisieren müssen, entsprechende Sprachvariablen erstellen und in Ihrer Vorlage verwenden.
Sie können Sprachvariablen für längeren Text erstellen, z. B. einen ganzen Satz oder sogar einen Absatz. Sie können auch Stile anwenden und HTML Markup verwenden, um diese Sprachvariablen zu formatieren.

Weitere Informationen finden Sie unter [Unterstützung für Sprachvariablen](../native-pdf/native-pdf-language-variables.md).

### Möglichkeit zur Verwendung AEM Metadaten in PDF-Layouts

Metadaten sind die Beschreibung oder Definition Ihres Inhalts. Diese Metadaten werden in Ihrem Quell-DITA-Map-Inhalt gespeichert.

Jetzt können Sie in AEM Guides auch die Metadateneigenschaften Ihrer Assets auswählen und sie zum Seitenlayout hinzufügen. Anschließend wählt AEM Guides diese Metadateneigenschaften Ihrer Assets aus und veröffentlicht sie in Ihrer PDF-Ausgabe.


![](assets/native-pdf-metadata-asset.png){width="550" align="left"}

>[!NOTE]
>
> AEM Guides unterstützt auch die Metadateneigenschaften für Ihre DITA-Maps.

Weitere Informationen finden Sie unter [Felder und Metadaten hinzufügen](../native-pdf/design-page-layout.md#add-fields-metadata).


## Verbesserungen bei Schemata

### Verwenden Sie Berichtanweisungen zur Überprüfung auf Regeln in Schema

AEM Guides unterstützt nun auch die Berichtanweisungen mit dem Schema . Eine Berichtanweisung generiert eine Meldung, wenn eine Testanweisung als &quot;true&quot;ausgewertet wird. Wenn Sie beispielsweise eine Kurzbeschreibung von 150 Zeichen oder weniger wünschen, können Sie eine Berichtanweisung definieren, um die Themen zu überprüfen, bei denen die Kurzbeschreibung mehr als 150 Zeichen umfasst.

Weitere Informationen finden Sie unter [Verwenden Sie Assert- und Berichtanweisungen, um nach Regeln zu suchen](../user-guide/support-schematron-file.md#schematron-assert-report).

### Verwenden von Regex-Ausdrücken

Sie können auch Regex-Ausdrücke verwenden, um eine Regel mit der Funktion matches() zu definieren und dann mithilfe der Schematron-Datei eine Validierung durchzuführen.

Weitere Informationen finden Sie unter [Verwenden von Regex-Ausdrücken](../user-guide/support-schematron-file.md#schematron-assert-report).


### Abstrakte Muster definieren

AEM Guides unterstützt auch abstrakte Muster in Schematron. Sie können allgemeine abstrakte Muster definieren und diese abstrakten Muster wiederverwenden. Abstrakte Muster können Ihr Schema vereinfachen und Ihnen auch bei der Verwaltung und Aktualisierung Ihrer Validierungslogik helfen.


Weitere Informationen finden Sie unter [Definieren abstrakter Muster](../user-guide/support-schematron-file.md#schematron-abstract-patterns).

## Navigieren Sie vom Web Editor zur AEM Homepage .

Jetzt können Sie einfach vom Web-Editor zur AEM Homepage navigieren.

![](assets/web-editor-launch-page.png){width="800" align="left"}

* Klicken Sie auf das Symbol **Guides** (![](assets/aem-guides-icon.png) ), um zur AEM Navigationsseite zurückzukehren.


Weitere Informationen finden Sie unter [AEM Navigationsseite](../user-guide/web-editor-launch-editor.md#id2056BG00RZJ).

## Umgang mit hierarchischen Definitionen von Betreffdefinitionen und Auflistungen

AEM Guides verfügt über die leistungsstarke Funktion zum Erstellen von Themenschema-Karten, die eine spezielle Form von DITA-Maps sind, die zur Definition von taxonomischen Objekten und kontrollierten Werten verwendet werden. Jetzt können Sie mit AEM Guides auch die Definition des Betreffs in einer Zuordnung und die Auflistungsdefinitionen in einer anderen Zuordnung definieren. Anschließend können Sie die Zuordnungsreferenz hinzufügen und das Betreffschema verwenden.
Die Verweise auf die Betreffauflistung werden in derselben Zuordnung oder der referenzierten Zuordnung aufgelöst.

Weitere Informationen zum Umgang mit hierarchischen Definitionen von Betreffdefinitionen und Auflistungen finden Sie in der Beschreibung der Funktion **Betreff schema** im Abschnitt [Linkes Bedienfeld](../user-guide/web-editor-features.md#id2051EA0M0HS) .

## Unterstützung des XLIFF-Formats bei der Übersetzung

AEM Guides unterstützt auch das XLIFF-Format (XML Localization Interchange File Format) bei der Übersetzung. Jetzt können Sie auch **ein neues XLIFF-Übersetzungsprojekt erstellen** auswählen, um den XML-Inhalt in das XLIFF-Format zu konvertieren.
Mithilfe dieses Formats können Sie den Inhalt in das XLIFF-Format des Branchenstandards exportieren und dann den Übersetzungsanbietern dasselbe bereitstellen. Weitere Informationen finden Sie unter [Erstellen eines Übersetzungsprojekts](../user-guide/translate-documents-web-editor.md#create-translation-project).

![](assets/translation-project-types.png){width="350" align="left"}



## Verbessertes Bedienfeld &quot;Favoriten&quot;

Mit AEM Guides können Sie eine Sammlung oder Favoritenliste Ihrer Dateien und Ordner erstellen und diese einfach verwenden. Jetzt ist das Menü **Optionen** auch im Bedienfeld **Favoriten** verfügbar. Sie können die ausgewählte Sammlung umbenennen oder aus dem Menü **Optionen** löschen. Sie können die Option **Aktualisieren** auswählen, um eine neue Liste von Dateien oder Ordnern aus dem Repository abzurufen. Sie können den Ordnerinhalt auch in der Benutzeroberfläche von Assets anzeigen.

![](assets/favorites-options.png){width="650" align="left"}

>[!NOTE]
>
> Sie können die Liste auch mit dem Symbol **Aktualisieren** oben aktualisieren.

Weitere Informationen zum Menü **Optionen** einer Favoriten-Sammlung finden Sie in der Beschreibung der Funktion **Favoriten** im Abschnitt [Linkes Bedienfeld](../user-guide/web-editor-features.md#id2051EA0M0HS) .

## Wechseln Sie zum Systemdesign

Sie können jetzt auch das Gerätedesign verwenden. Mithilfe der **Benutzereinstellungen** können Sie AEM Guides so konfigurieren, dass basierend auf dem Design Ihres Geräts automatisch zwischen hellen und dunklen Designs gewechselt wird.

![](assets/device-theme-user-preferences.png){width="550" align="left"}

Weitere Informationen finden Sie in der Beschreibung der Funktion **Benutzereinstellungen** im Abschnitt [Hauptsymbolleiste](../user-guide/web-editor-features.md#id2051EA0G05Z) .
