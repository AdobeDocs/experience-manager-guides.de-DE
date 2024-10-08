---
title: Versionshinweise | Neue Funktionen in Adobe Experience Manager Guides Version 4.4.0
description: Erfahren Sie mehr über die neuen und verbesserten Funktionen in Version 4.4.0 von Adobe Experience Manager Guides
role: Leader
exl-id: 63a2e93b-b4cf-4423-88e4-b01c6a52a532
source-git-commit: 76c731c6a0e496b5b1237b9b9fb84adda8fa8a92
workflow-type: tm+mt
source-wordcount: '2308'
ht-degree: 0%

---

# Neue Funktionen in Version 4.4.0 (Januar 2024)

Dieser Artikel behandelt die neuen und verbesserten Funktionen in Version 4.4.0 von Adobe Experience Manager Guides.

Sehen Sie sich für die Liste der in dieser Version behobenen Probleme [Behobene Probleme in Version 4.4.0](../release-info/fixed-issues-4-4.md) an.

Erfahren Sie mehr über [Upgrade-Anweisungen für Version 4.4.0](../release-info/upgrade-instructions-4-4.md).



## Überarbeitete Funktion für den Versionsverlauf im Web-Editor

Jetzt bietet Experience Manager Guides eine erweiterte Funktion zum Versionsverlauf, mit der Sie die an einem Dokument vorgenommenen Änderungen im Zeitverlauf vergleichen können. In der neuen Seitenansicht können Sie den Inhalt und die Metadaten der aktuellen Version einfach mit einer früheren Version desselben Dokuments vergleichen. Sie können auch die Bezeichnungen und Kommentare für die verglichenen Versionen anzeigen. Als Administrator können Sie die Versionsmetadaten des Themas und deren Werte steuern, die im Dialogfeld **Versionsverlauf** angezeigt werden sollen.

![Dialogfeld &quot;Versionsverlauf&quot;](assets/version-history-dialog-web-editor.png){width="800" align="left"}
*Sehen Sie sich die Änderungen in den verschiedenen Versionen eines Themas in der Vorschau an.*

Weitere Informationen zur Beschreibung der Funktion **Versionsverlauf** finden Sie im Abschnitt [Linkes Bedienfeld (veraltet)](/help/legacy-product-guide/user-guide/web-editor-features.md#id2051EA0M0HS) .

## Verwalten von Bedingungsvorgaben

Sie können Bedingungsattribute in Ihren DITA-Themen definieren. Verwenden Sie dann die Bedingungsattribute in der Bedingungsvorgabe, um den Inhalt in einer DITA-Zuordnung zu veröffentlichen. Experience Manager Guides bietet jetzt auch ein erweitertes Erlebnis im Web-Editor, mit dem Sie Bedingungsvorgaben effizienter erstellen und verwalten können. Sie können sie auch einfach bearbeiten, duplizieren oder löschen.

![Bedingungsvorgaben auf der Registerkarte &quot;Verwalten&quot;des Web-Editors ](assets/web-editor-manage-condition-presets.png){width="550" align="left"}

Weitere Informationen finden Sie unter [Verwenden von Bedingungsvorgaben](../user-guide/generate-output-use-condition-presets.md).

## Umgestaltetes Erlebnis zur Bearbeitung der Attribute

Jetzt erhalten Sie ein überarbeitetes Erlebnis, um die Attribute für ein Element aus dem Bereich **Inhaltseigenschaften** im Web Editor hinzuzufügen oder zu bearbeiten.

![Bedienfeld &quot;Attribute&quot;](assets/attributes-multiple-properties.png){width="300" align="left"}

*Fügen Sie Attribute aus dem Bereich &quot;Inhaltseigenschaften&quot;hinzu.*

Sie können die Attribute auch einfach bearbeiten und löschen.
Weitere Informationen finden Sie in der Beschreibung der Funktion **Inhaltseigenschaften** im Abschnitt [Rechtes Bedienfeld](../user-guide/web-editor-features.md#id2051EB003YK) .

## Bearbeiten von Metadaten beim Authoring

Jetzt können Sie beim Authoring die Metadaten-Tags der Datei mithilfe des Dropdown-Menüs aus den **Dateieigenschaften** im rechten Bereich aktualisieren. Sie können auch &quot;**Weitere Eigenschaften bearbeiten**&quot;auswählen, um weitere Metadaten zu aktualisieren.

![file-properties](assets/file-properties-general.png){width="300" align="left"}

*Aktualisieren Sie die Metadaten und bearbeiten Sie die Dateieigenschaften im rechten Bereich.*

Weitere Informationen finden Sie in der Beschreibung der Funktion **Dateieigenschaften** im Abschnitt [Rechtes Bedienfeld](../user-guide/web-editor-features.md#id2051EB003YK) .

## Anzeigen von Schlüsselattributen in der Kartenansicht

Wenn Sie Schlüsselattribute für das Thema oder die Zuordnungsreferenzen definieren, können Sie auch den Titel, das entsprechende Symbol und den Schlüssel im linken Bereich anzeigen. Der Schlüssel wird als `key=<key-name>` angezeigt.

![Schlüssel in der Kartenansicht](assets/view-key-title-map-view.png) {width="300" align="left"}

*Zeigen Sie das Schlüsselattribut in der Kartenansicht an.*


Weitere Informationen finden Sie in der Beschreibung der Funktion **Kartenansicht** im Abschnitt [Linkes Bedienfeld](../user-guide/web-editor-features.md#id2051EA0M0HS) .

## Möglichkeit, eine Grundlinie basierend auf der Bezeichnung zu duplizieren

Experience Manager Guides bietet jetzt ein verbessertes Benutzererlebnis zum Erstellen der Grundlinien im Web-Editor.
Die Optionen **Manuelles Update** und **Automatisches Update** sind intuitiver und helfen Ihnen bei der Wahl zwischen der Erstellung einer statischen Grundlinie oder der automatischen Aktualisierung entsprechend den Beschriftungen.

![Erstellen neuer Grundlinien](assets/dynamic-baseline-4-4.png) {width="300" align="left"}
*Erstellen Sie eine Grundlinie aus dem Web-Editor.*

Außerdem können Sie damit eine Grundlinie basierend auf der Bezeichnung duplizieren. Die Referenzversion wird beim Duplizieren anhand der angegebenen Bezeichnung ausgewählt (sofern vorhanden) oder wählt die Version aus der duplizierten Grundlinie aus.


![Duplizieren einer Grundlinie ](assets/duplicate-baseline.png) {width="300" align="left"}

*Duplizieren Sie eine Grundlinie basierend auf einer Bezeichnung oder erstellen Sie eine exakte Kopie.*

Erfahren Sie mehr darüber, wie Sie mit dem Web Editor ](../user-guide/web-editor-baseline.md) Grundlinien erstellen und verwalten.[

## Verbessertes Landkartenkollektions-Dashboard

Experience Manager Guides bietet ein erweitertes Dashboard für die Zuordnungserfassung. In einer Zuordnungssammlung können Sie die Metadateneigenschaften für die DITA-Maps schnell stapelweise konfigurieren. Diese Funktion ist praktisch, da Sie die Metadateneigenschaften nicht für jede DITA-Zuordnung einzeln aktualisieren müssen.

Jetzt können Sie den Dateinamen der DITA-Map anzeigen. Sie können auch die Grundlinien anzeigen. Auf diese Weise können Sie schnell die für eine Vorgabe verwendete Grundlinie finden.

![Sammlungs-Dashboard zuordnen](assets/map-collection-dashboard.png){width="800" align="left"}

*Anzeigen, Bearbeiten und Generieren der Ausgabe aus dem Dashboard der Zuordnungssammlung.*

Erfahren Sie, wie Sie [die Kartensammlung für die Ausgabegenerierung verwenden](../user-guide/generate-output-use-map-collection-output-generation.md).

## Verbessertes Übersetzungsfenster

Das Bedienfeld **Übersetzung** wurde verbessert.  Sie können die Liste **Verfügbare Sprachen** anzeigen und schnell das Gebietsschema auswählen, in das Sie Ihr Projekt übersetzen möchten. Mit einer einzigen Auswahl können Sie auch **Alle auswählen** auswählen, um Ihr Projekt in alle verfügbaren Sprachen zu übersetzen.

![Übersetzungsbedienfeld](assets/translation-languages-4.4.png){width="300" align="left"}



*Wählen Sie die Gebietsschemata aus, in denen Sie Ihr Projekt übersetzen möchten. Wählen Sie die Standard-, Grundlinien- oder die neueste Version der zu übersetzenden Dateien aus.*

Erfahren Sie mehr darüber, wie Sie [Inhalte übersetzen](../user-guide/translation.md).

## Verbesserte Suchlogik im Dialogfeld &quot;Element einfügen&quot;

Sie können die Elemente jetzt einfach im Dialogfeld &quot;Element einfügen&quot;finden.  Sie können eine Zeichenfolge in das Suchfeld eingeben und eine Liste aller gültigen Elemente abrufen, die mit der eingegebenen Zeichenfolge beginnen.

Wenn Sie beispielsweise einen Absatz bearbeiten, den Sie einfügen möchten, können Sie nach dem Zeichen &#39;t&#39; suchen, um
alle gültigen Elemente, die mit &quot;t&quot;beginnen.


![Dialogfeld &quot;Einfügen&quot;](assets/insert-element.png){width="300" align="left"}

*Geben Sie ein Zeichen ein, um nach allen gültigen Elementen zu suchen, die mit dem Zeichen beginnen.*


Weitere Informationen finden Sie in der Beschreibung der Funktion **Element einfügen** im Abschnitt [Linkes Bedienfeld](../user-guide/web-editor-features.md#id2051EA0M0HS) .


## Möglichkeit, eine Liste auf derselben Ebene zu teilen

Jetzt können Sie Ihre Liste einfach im Web-Editor aufteilen. Wählen Sie im Kontextmenü eines Listenelements die Option **Aufspaltungsliste** aus, um die aktuelle Liste aufzuteilen. Auf derselben Ebene wird eine neue Liste erstellt, die mit dem Listenelement beginnt, das Sie für die Aufteilung ausgewählt haben.

![Übersetzungsbedienfeld](assets/context-menu-split-list.png){width="300" align="left"}

*Wählen Sie die Option zum Aufteilen der aktuellen Liste aus.*

Weitere Informationen finden Sie in der Beschreibung der Funktion **Liste einfügen** im Abschnitt [Linkes Bedienfeld](../user-guide/web-editor-features.md#id2051EA0M0HS) .

## DITA-Elemente einfach entpacken

Jetzt können Sie mit der Option im Kontextmenü eines Elements im Web Editor die Einbindung eines Elements einfach aufheben. Auf diese Weise können Sie den Text des Elements einfach mit seinem übergeordneten Element zusammenführen.
Weitere Informationen finden Sie im Abschnitt **Aufheben der Einbindung eines Elements** in den [anderen Funktionen im Web Editor](../user-guide/web-editor-other-features.md).

## Zugriff auf Dateieigenschaften im Quellmodus des Authoring

Jetzt können Sie in allen vier Modi oder Ansichten auf die Funktion **Dateieigenschaften** des rechten Bedienfelds zugreifen: Layout, Autor, Source und Vorschau.  Auf diese Weise können Sie die Eigenschaften Ihrer Datei anzeigen, selbst wenn Sie zwischen den verschiedenen Modi wechseln.

Weitere Informationen finden Sie in der Beschreibung der Funktion **Dateieigenschaften** im Abschnitt [Rechtes Bedienfeld](../user-guide/web-editor-features.md#id2051EB003YK) .


## Anzeigen von Dateien nach Titel oder Dateinamen

Sie können jetzt die Standardmethode zum Anzeigen der Dateien im Web-Editor wählen. Sie können die Liste der Dateien anhand der Titel oder Dateinamen aus den verschiedenen Bedienfeldern in der Autorenansicht anzeigen.

![Dialogfeld &quot;Benutzereinstellungen&quot;](assets/user-preferences-2311.png){width="550" align="left"}

*Ändern Sie die Standardmethode zum Anzeigen der Dateien im Dialogfeld **Benutzereinstellungen**.*


## Dateiregisterkarten beim Aktualisieren des Browsers wiederherstellen

Experience Manager Guides stellt beim Aktualisieren des Browsers den Status der geöffneten Dateiregisterkarten im Web Editor wieder her. Weitere Informationen finden Sie im Abschnitt **Browser beim Bearbeiten der Dateien aktualisieren** unter [Themen im Web-Editor bearbeiten](../user-guide/web-editor-edit-topics.md) .


## Navigieren mit den Tastaturbefehlen

Mit Experience Manager Guides können Sie jetzt auch Tastaturbefehle verwenden, um den Cursor im Web-Editor zu verschieben. Sie können die Tastaturbefehle verwenden, um ein Wort schnell nach links oder rechts zu verschieben. Mithilfe der Tastaturbefehle können Sie auch zum Anfang oder Ende der Zeile wechseln.
Jetzt können Sie auch Tastaturbefehle verwenden, um den Cursor an den Anfang des nächsten Elements oder an das Ende des vorherigen Elements zu verschieben.
Erfahren Sie mehr über die [Tastaturbefehle im Web-Editor](../user-guide/web-editor-keyboard-shortcuts.md).


## Auflösen von Cross-Map-Links in der Ausgabe der AEM Site

Cross-Map-Links (XREF mit Perimeter Peer), die in der AEM Site-Ausgabe gerendert werden, werden jetzt gemäß dem Dateinamen des Veröffentlichungskontexts aufgelöst, der für die generierte Zuordnung festgelegt wurde.


## URL der Ausgabe der AEM Site zur Verwendung des Dokumenttitels konfigurieren

Experience Manager Guides ermöglicht es Ihnen als Administrator, die URL der AEM Site-Ausgabe zu konfigurieren. Wenn der Dateiname nicht vorhanden ist oder alle Sonderzeichen enthält, können Sie konfigurieren, dass er in der URL der AEM Site-Ausgabe durch ein Trennzeichen ersetzt wird. Sie können sie auch durch den Namen des ersten untergeordneten Themas ersetzen. Erfahren Sie, wie Sie [die URL der AEM Site-Ausgabe für die Verwendung des Dokumenttitels konfigurieren](../cs-install-guide/conf-output-generation.md#configure-the-url-of-the-aem-site-output-to-use-the-document-title).


## Publish - Mehrere Ausgabevorgaben parallel

Experience Manager bietet die Möglichkeit, Grundlinien zu erstellen, indem die Themen automatisch entsprechend der auf sie angewendeten Bezeichnung ausgewählt werden. Jetzt können Sie auch nahtlos mehrere Ausgabevorgaben mit automatischen Grundlinien derselben DITA-Zuordnung veröffentlichen. Sie müssen nicht nur eine Vorgabe gleichzeitig veröffentlichen, sondern können mühelos mehrere Ausgabevorgaben gleichzeitig veröffentlichen.

Erfahren Sie mehr darüber, wie Sie mit dem Web Editor ](../user-guide/web-editor-baseline.md) Grundlinien erstellen und verwalten.[

## Native PDF-Verbesserungen

Die folgenden nativen PDF-Verbesserungen wurden in Version 4.4.0 vorgenommen:

### Variablen in der PDF-Ausgabe verwenden

Mithilfe von Variablen können Sie wiederverwendbare Informationen dynamisch einfügen und verwalten. Experience Manager Guides unterstützt Sie beim Erstellen, Bearbeiten und Anzeigen einer Vorschau von Variablen beim Generieren der PDF-Ausgabe. Sie können die Werte von Variablen schnell ändern und Ihre Dokumente portabel und einfach zu aktualisieren.

![native PDF-Variablen](assets/add-variable-default.png){width="800" align="left"}

*Erstellen und verwalten Sie Variablen im Web-Editor.*

Sie können auch Variablensätze erstellen, die die Standardwerte außer Kraft setzen und Ihren Variablen alternative Werte zuweisen. Fügen Sie diese Variablen in das Seitenlayout ein und verwenden Sie dasselbe PDF-Layout. Sie müssen nicht für jeden Wertesatz separate Layouts erstellen. Sie können beispielsweise für jede Produktversion einen Variablensatz erstellen. Dieser Variablensatz kann aus Variablen für verschiedene Produktdetails wie Produktname, Versionsnummer und Veröffentlichungsdatum bestehen. Anschließend können Sie für diese Variablen unterschiedliche Werte hinzufügen.

**Variable festgelegt 1: Adobe-set1**

* ProductName: Experience Manager Guides
* VersionNumber: 2311
* Releasedatum: 20.11.2023

**Variable festgelegt 2: Adobe-set2**

* ProductName: Experience Manager Guides
* VersionNumber: 2310
* ReleaseDate: 27.09.2023



<img src="./assets/native-pdf-variable-output.png" alt="Fußzeile in PDF-Ausgabe" width="500" border="2px">

*Generieren Sie die PDF-Ausgabe mithilfe von Variablen im PDF-Layout.*

Sie können Stile anwenden und HTML Markup verwenden, um die Variablen zu formatieren.  Sie können die Werte für alle Variablen bei Bedarf auch schnell aktualisieren und die Ausgabe neu generieren. Wenn Sie beispielsweise die Details für eine Version aktualisieren müssen, können Sie den Wert der Version in der Variablen VersionNumber bearbeiten und die Ausgabe neu generieren.


Erfahren Sie mehr über die Verwendung von [Variablen in der PDF-Ausgabe](../native-pdf/native-pdf-variables.md).


### Übertragen von Asset-Metadaten in die PDF-Ausgabe

Experience Manager bietet jetzt die Möglichkeit, die Metadateneigenschaften der Assets von der DITA-Zuordnung zur PDF-Ausgabe zu übertragen.
Aus der Ausgabevorgabe Native PDF können Sie die Metadaten auswählen, die Sie an den PDF-Veröffentlichungsprozess weiterleiten möchten. Sie können sowohl die benutzerdefinierten Eigenschaften als auch die Standardeigenschaften auswählen.  Die ausgewählten Metadateneigenschaften werden in die PDF-Datei übertragen, die mithilfe des nativen PDF erstellt wird.

Diese Funktion ist nützlich, da Sie damit Ihre Asset-Eigenschaften wie Autor, Erstellungsdatum oder Dokumenttitel konsistent halten können. Dies erleichtert die Organisation, Suche und Kategorisierung Ihrer Dokumente.

Weitere Informationen finden Sie in den Einstellungen für **Erweitert** in der Ausgabe [Publish-PDF](../web-editor/native-pdf-web-editor.md).

### Verwenden Sie die im Element `topicmeta` hinzugefügten Metadaten für die PDF-Ausgabe.

Die Metadatenfunktion im nativen PDF-Publishing hilft beim Content Management und bei der Suche nach Dateien im Internet.
<img src="assets/pdf-metadata-4-4.png" alt="Metadaten-Registerkarte" width="800">

*Wählen Sie eine Option zum Hinzufügen und Anpassen von Metadatenoptionen.*

Jetzt bietet Experience Manager Guides die Möglichkeit, die Metadaten zu verwenden, die Sie im Element `topicmeta` der DITA-Map hinzugefügt haben, um die Metadatenfelder der PDF-Ausgabe zu füllen. Standardmäßig ist diese Option aktiviert.

Diese Funktion hilft bei einer besseren Dokumentenverwaltung, sorgt für Konsistenz und macht Ihre Dokumente durchsuchbar.

Weitere Informationen finden Sie auf der Registerkarte **Metadaten** in der Ausgabe [Publish-PDF](../web-editor/native-pdf-web-editor.md).

### Verwenden und Duplizieren von nativen PDF-Vorlagen

Experience Manager Guides bietet vordefinierte oder werkseitige PDF-Vorlagen. Duplizieren Sie die werkseitigen PDF-Vorlagen, um die benutzerdefinierten PDF-Vorlagen zu erstellen.

Jetzt können Sie auch beim Erstellen und Duplizieren einer Vorlage eine Vorschau des Miniaturbilds für eine Vorlage anzeigen. Sie können dieses Bild auch bearbeiten oder löschen. Diese Funktion ist nützlich für das Branding oder die Unterscheidung von Vorlagen mit ähnlichen Namen.
Erfahren Sie mehr über die [PDF-Vorlage](../native-pdf/pdf-template.md).

![Dialogfeld &quot;PDF-Vorlage duplizieren&quot;](assets/duplicate-template.png){width="550" align="left"}

*Duplizieren Sie eine vorhandene PDF-Vorlage.*


### Ändern der Reihenfolge von Seiten und Veröffentlichen mehrerer Seiten pro Blatt

Sie können die Seiten nicht nur gemäß dem Quelldokument veröffentlichen, sondern auch die Seitenreihenfolge im PDF ändern, während Sie ein mehrseitiges Dokument veröffentlichen.  So können Sie die Seiten in verschiedenen Bestellungen veröffentlichen, wie z.B. alle ungeraden oder alle geraden Seiten zuerst. Sie können auch als Broschüre veröffentlichen und die Seiten wie ein Buch lesen. Sie können auch festlegen, wie viele Seiten Sie auf einem einzigen Blatt veröffentlichen möchten. Weitere Informationen finden Sie im Abschnitt [Seitenorganisation](../native-pdf/components-pdf-template.md#page-organization) .

### Sortieren Sie Glossarbegriffe basierend auf Sortierschlüsseln

Jetzt können Sie die Glossarbegriffe auch anhand von Sortierschlüsseln sortieren. Sie können das Tag &quot;sort-as&quot;verwenden, um einen Sortierschlüssel für die Glossarbegriffe zu definieren. Anschließend können Sie sie anhand von Sortierschlüsseln anstelle der Begriffe sortieren. Auf diese Weise können Sie die Glossarbegriffe nach Begriffen sortieren, die in verschiedenen Sprachen verwendet werden. Sie können auch einen einzigen Sortierschlüssel für einen Glossarbegriff mit einem Satz oder einer Wortgruppe definieren.
Weitere Informationen finden Sie unter [Erweiterte PDF-Einstellungen](../native-pdf/components-pdf-template.md#advanced-pdf-settings).


### Verbesserte Ressourcenverwaltung für native PDF-Vorlagen

Experience Manager Guides hat jetzt die Ressourcenverwaltung für native PDF-Vorlagen verbessert. Sie können jetzt Ressourcen wie Bilder, CSS-Dateien und Schriftartdateien für mehrere native PDF-Vorlagen freigeben und wiederverwenden. Durch diese Verbesserung ist die Verwaltung der Ressourcen für eine große Anzahl von Vorlagen wesentlich einfacher. Sie müssen keine doppelten Ressourcen für jede Vorlage erstellen und diese in einem freigegebenen Ordner speichern und in allen nativen PDF-Vorlagen verwenden.
Weitere Informationen finden Sie unter [PDF-Vorlage](../native-pdf/pdf-template.md).
