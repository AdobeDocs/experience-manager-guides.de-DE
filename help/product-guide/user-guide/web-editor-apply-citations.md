---
title: Hinzufügen und Verwalten von Zitaten in Ihren Inhalten
description: Hinzufügen und Verwalten von Zitaten in AEM Guides. Erfahren Sie, wie Sie Zitate anwenden, importieren, filtern, suchen, den Zitatstil ändern, bearbeiten, in der Vorschau anzeigen, einfügen, löschen und die Inhaltsausgabe mit Zitaten generieren können.
exl-id: 685d747d-e017-4350-a6bf-822fd55c76e8
feature: Authoring, Features of Web Editor
role: User
source-git-commit: 6e23f52fc9124d0f07f8108da1b5fe574f553469
workflow-type: tm+mt
source-wordcount: '1890'
ht-degree: 0%

---

# Hinzufügen und Verwalten von Zitaten in Ihren Inhalten

Zitate sind Verweise auf die Quelle von Informationen, die Ihrem Inhalt hinzugefügt werden. Mithilfe von Zitaten können Sie den Autoren die Quellinformationen zuschreiben und den Lesern helfen, die Quellinformationen zu verfolgen. Das Hinzufügen von Zitaten macht Ihre Inhalte zuverlässiger und verhindert Plagiate. Sie ermöglichen es Ihnen auch, gut recherchierte Inhalte anzuzeigen.

In Adobe Experience Manager Guides können Sie Zitate hinzufügen, importieren und sie auf Ihre Inhalte anwenden. Sie können diese Zitate aus jeder Quelle von Büchern, Websites und Zeitschriften hinzufügen.


Mit Experience Manager Guides können Sie Ihre Zitate bearbeiten, in der Vorschau anzeigen und sortieren. Nachdem Sie Ihre Zitate zum Inhalt hinzugefügt haben, können Sie die Ausgabe mit dem nativen PDF generieren. Sie können die Bibliografie- oder Verweisseite auch in der nativen PDF-Ausgabe hinzufügen.

Experience Manager Guides unterstützt verschiedene Zitatstile, wie die Modern Language Association (MLA), die American Psychological Association (APA), Chicago, das Institute for Electrical and Electronics Engineers (IEEE) und die American Heart Association (AHA). Es wird empfohlen, diese klar und konsequent anzuwenden.


>[!NOTE]
>
>Derzeit unterstützt Experience Manager Guides nur native PDF für Zitate.


## Zitate hinzufügen

Gehen Sie wie folgt vor, um Zitate hinzuzufügen:

1. Wählen Sie **linken Bedienfeld** Symbol ![Zitate](images/citations-icon.svg) aus.

   Das **Zitate**-Bedienfeld wird geöffnet.

   ![](images/citation-panel.png){width="350" align="left"}

1. Wählen Sie im **Zitate**-Bedienfeld ![Symbol hinzufügen](images/Add_icon.svg) aus. Aus dem Dropdown-Menü können Sie ein neues Zitat hinzufügen oder ein Zitat importieren.

1. Wählen Sie **Neues Zitat** aus, um ein neues Zitat hinzuzufügen.

   Das **Zitat hinzufügen** wird geöffnet.

   ![Zitationsbereich im Web-Editor](images/citation-add.png) {width="300" align="left"}


1. Füllen Sie die Felder im Dialogfeld **Zitat hinzufügen** aus.

   >[!NOTE]
   >
   >Sie können auch die ISBN-, DOI- oder PubMed-ID hinzufügen. AEM Guides füllt die anderen Felder automatisch aus.

   | Buch | Website | Journal |
   | --- | ---|---|
   | **Source** <br> Wählen Sie aus der Dropdown-Liste die Quelle des Zitats als Buch aus. | **Source**<br> Wählen Sie in der Dropdown-Liste die Quelle des Zitats als Website aus. | **Source** <br> Wählen Sie in der Dropdown-Liste die Quelle des Zitats als Journal aus. |
   | **Suchen nach** <br> Wählen Sie **ISBN** oder **DOI** aus der Dropdown-Liste aus, um nach der digitalen ID zu suchen, die mit dem Zitat verknüpft ist.  <br> DOI: Digitale Objektkennung <br> ISBN: Eindeutige numerische Buchkennung | **Suchen nach** <br> Wählen Sie **DOI** aus der Dropdown-Liste aus, um nach der digitalen ID zu suchen, die mit dem Zitat verknüpft ist. | **Suchen nach** <br> Wählen Sie **DOI** oder PubMed ID aus der Dropdown-Liste aus, um nach der digitalen ID zu suchen, die mit der Zitatangabe verknüpft ist. <br>  <br> |
   | **Autor** <br> Fügen Sie den Vor- und Nachnamen des Autors des Zitats hinzu. Wählen Sie ![](images/Add_icon.svg) aus, um weitere Namen hinzuzufügen. | **Autor** <br> Fügen Sie den Vor- und Nachnamen des Autors des Zitats hinzu. Wählen Sie ![](images/Add_icon.svg) aus, um weitere Namen hinzuzufügen. | **Autor** <br> Fügen Sie den Vor- und Nachnamen des Autors des Zitats hinzu. Wählen Sie ![](images/Add_icon.svg)aus, um weitere Namen hinzuzufügen. |
   | **Titel** <br> Fügen Sie den Titel des Buchs hinzu. | **Titel** <br> Fügen Sie den Titel der Web-Seite hinzu. | **Titel** <br> Fügen Sie den Titel des Artikels hinzu. |
   | **Editor** <br> Fügen Sie den Editor des Buchs hinzu. | **Website-Name** <br> Fügen Sie den Namen der Website hinzu. | **Journaltitel** <br> Fügen Sie den Titel des Werks hinzu, in dem der Artikel gefunden wird. |
   | **Edition** <br> Fügen Sie die Ausgabe des Buches hinzu. | **URL** <br> Fügen Sie den Weblink der Website hinzu, um den Inhalt zu durchsuchen. | **Jahr** <br> Fügen Sie das Jahr hinzu, in dem der Artikel veröffentlicht wird. |
   | **Stadt** <br> Fügen Sie die Stadt der Veröffentlichung hinzu. | **Zugriffsdatum**<br> Fügen Sie das Datum hinzu, an dem der Inhalt der Website aufgerufen wird. | **Volumen** <br> Fügen Sie das Volumen der Arbeit in der Reihe hinzu. |
   | **Publisher** <br> Fügen Sie den Namen des Herausgebers des Buchs hinzu. | **Veröffentlichungsdatum** <br> Fügen Sie das Datum hinzu, an dem der Inhalt der Website veröffentlicht wird. | **Number** <br> Fügen Sie die Nummer des Volumes innerhalb der Serie hinzu. |
   | **Year** <br> Fügen Sie das Jahr hinzu, in dem das Buch veröffentlicht wird. | **Aktualisierungsdatum** <br> Fügen Sie das Datum hinzu, an dem der Inhalt der Website aktualisiert wird. | **Seiten** <br> Fügen Sie die Seitennummer oder den Seitenbereich hinzu, in dem der Artikel gefunden wird. |
   | **Version** <br> Fügen Sie die Version des Buches hinzu. | **Eindeutige ID** <br> Fügen Sie eine eindeutige ID für die Zitierung hinzu. Eine eindeutige ID ist eine eindeutige Kennung für dieses Zitat. | **URL** <br>Fügen Sie den Weblink zum Protokoll hinzu. |
   | **Serie** <br>Fügen Sie die Serie des Buches hinzu. |  | **Eindeutige ID** <br> Fügen Sie eine eindeutige ID für das Zitat hinzu. Eine eindeutige ID ist eine eindeutige Kennung für dieses Zitat. |
   | **URL** <br> Fügen Sie den Weblink zum Buch hinzu. |  |  |
   | **Eindeutige ID** <br> Fügen Sie eine eindeutige ID für die Zitierung hinzu. Eine eindeutige ID ist eine eindeutige Kennung für dieses Zitat. |  |  |

1. Wählen Sie **Fertig** aus.

   Dem Zitatbereich wird ein neues Zitat hinzugefügt.

>[!NOTE]
>
> Das Hinzufügen einer eindeutigen ID für das Zitatfeld ist obligatorisch.  Sie können die eindeutige ID nicht mehr ändern, nachdem die Zitierung hinzugefügt wurde.

## Zitate importieren

Gehen Sie wie folgt vor, um Zitate zu importieren:

1. Wählen Sie im linken Bedienfeld die Option **Zitate** ![Zitationssymbol](images/citations-icon.svg) aus.

   Das **Zitate**-Bedienfeld wird geöffnet.

1. Wählen Sie **Bedienfeld** Zitate“ die Option ![Symbol hinzufügen](images/Add_icon.svg) und wählen Sie dann **Importieren** aus der Dropdown-Liste aus.
1. Durchsuchen Sie eine .bib-Datei aus Ihrem System und importieren Sie sie .

   >[!TIP]
   >
   > Eine Dateinamenerweiterung .bib ist eine BibTeX-Bibliografische Datenbankdatei. Es ist eine speziell formatierte Textdatei, die Referenzen zu einer bestimmten Informationsquelle auflistet.

   Nachdem die Datei erfolgreich importiert wurde, können Sie die Verweise im Bereich „Zitate“ anzeigen.

   >[!NOTE]
   > <ol><li> Experience Manager Guides importiert nur die Zitate, die eindeutig und noch nicht vorhanden sind.
    &gt; <li> Experience Manager Guides kann Zitate aus einem Buch, einem Journal oder einer Website importieren. Derzeit werden Zitate aus anderen Quellen nicht unterstützt.

## Zitate verwalten

Die Zitate werden im linken Bereich alphabetisch sortiert. Suchen Sie nach den Zitaten entsprechend den Quellen, die in Ihrem Thema verwendet werden sollen.

### Filter

Wählen Sie **Symbol** Filter![](images/filter-search-icon.svg) neben der Suchleiste aus und wählen Sie die Quelloptionen aus der Dropdown-Liste aus, um die Zitatliste zu filtern. Es ermöglicht sowohl eine einzelne als auch mehrere Auswahlen.

* **Alle Quellen**: Hier wird eine vollständige Liste der Zitate angezeigt, einschließlich aller Quellen.

* **Buch**: Es zeigt die Liste der Zitate aus Büchern.

* **Website**: Zeigt die Liste der Zitate von Websites an.

* **Journal**: Zeigt die Liste der Zitate aus Journalen an.

### Suchen

Suchen Sie die Zitierung für Ihren Inhalt.

1. Wählen Sie im linken Bedienfeld Zitate aus.
Das **Zitate**-Bedienfeld wird geöffnet.

1. Verwenden Sie die Suchleiste, um aus einer langen Liste nach dem entsprechenden Zitat zu suchen.

### Zitatstil ändern {#change-citation-style}

Ihr Systemadministrator kann den Stil der Zitate über das Dropdown **Zitate** auf der Registerkarte **Allgemein** in den **Einstellungen** ändern.
Diese Stile bestimmen, wie Zitate im Vorschaubereich oder in der nativen PDF-Ausgabe angezeigt werden.

Die folgenden Optionen sind in der Dropdown-Liste verfügbar:

| MLA | APA | Chicago | IEEE | AHA |
|---|---|---|---|---|
| Moderne <br> | American Psychological Association Stil | Chicago Manual of Style | Institut für Elektro- und Elektronikingenieure | American Heart Association-Stil |
| Beispiel: <br> Crawford, Claire, et al. *Emotional Content of Dark Memories*.Edited by Memory, Band 16, 2010, Amsterdam. | Beispiel: <br> Crawford, C., J., &amp; , C. (2010). *Emotional Content of Dark Memories* (505-16 ed.). 10.1080/ 09658210902067289 | Beispiel: <br> Crawford, Claire, et al. *Emotionaler Inhalt dunkler Erinnerungen*. 505-16, 2010. | Beispiel: <br> C. Crawford, J. und C. *Emotionaler Inhalt dunkler Erinnerungen*. Amsterdam, 2010. | Beispiel: <br> C. Crawford, J. und C. *Emotionaler Inhalt dunkler Erinnerungen*. Amsterdam, 2010. |


## Zitat bearbeiten

Gehen Sie wie folgt vor, um das Zitat zu bearbeiten:

1. Bewegen Sie den Mauszeiger über den Namen des Zitats in der Liste. Wählen Sie ![](images/options.svg) Symbol **Optionen** aus.

1. Wählen Sie **Bearbeiten** aus.

Das **Zitat bearbeiten** wird geöffnet.

1. Nehmen Sie die erforderlichen Änderungen vor. Wählen Sie **Fertig** aus.
Das ausgewählte Zitat wird bearbeitet.

>[!NOTE]
>
>Sie können die eindeutige ID nicht mehr ändern, nachdem die Zitierung hinzugefügt wurde.

## Vorschau eines Zitats anzeigen

Gehen Sie wie folgt vor, um eine Vorschau eines Zitats anzuzeigen:

Bewegen Sie den Mauszeiger über den Namen des Zitats in der Liste. Auswählen     ![](images/options.svg) Symbol **Optionen**.

1. Wählen Sie **Vorschau** aus.
Sie können den Inhalt und das Format des Zitats im Vorschaubereich in der Vorschau anzeigen.

   >[!NOTE]
   >
   >Die Vorschau basiert auf dem Zitatstil, den Ihr Administrator in den **Einstellungen** ausgewählt hat.

1. Wählen Sie eine beliebige Stelle auf dem Bildschirm aus, um das Vorschaufeld zu schließen.

   ![](images/citation-preview.png){width="550" align="left"}

>[!NOTE]
>
> Sie können ein in ein Thema eingefügtes Zitat auch über die Assets-Benutzeroberfläche oder die Registerkarte Vorschau des Editors in der Vorschau anzeigen.

## Zitate einfügen

Führen Sie die folgenden Schritte aus, um Zitate in ein Thema einzufügen:
1. Wählen Sie das Thema im Repository-Bereich aus und doppelklicken Sie dann darauf, um es im Bearbeitungsfenster zu öffnen.
1. Platzieren Sie den Cursor an der Position des Themas, an der das Zitat hinzugefügt werden soll.



Sie können Zitate zum Thema aus der Hauptsymbolleiste oder dem linken Bereich einfügen.

### In der Haupt-Symbolleiste

1. Wählen Sie das Symbol **Zitate** ![Zitate](images/citations-icon.svg) in der Hauptsymbolleiste aus.
1. Wählen Sie **Dialogfeld**Zitate“ das Zitat aus. Sie können auch mehrere Zitate auswählen.
   ![Zitierdialogfeld](images/citation-dialog-main-toolbar.png){width="300" align="left"}
1. Sie können Zitate filtern, indem Sie die ersten Buchstaben in das Suchfeld des Dialogfelds **Zitat** eingeben.

1. Wählen Sie **Fertig** aus.
Das ausgewählte Zitat wird an der Cursorposition im Thema hinzugefügt.


### Vom linken Bedienfeld

>[!NOTE]
> 
>Um das Symbol **Zitate** im linken Bereich anzuzeigen, muss Ihr Systemadministrator die Option **Zitate** auf der Registerkarte **Panels** in **Settings** aktivieren.

1. Wählen Sie **Zitate** ![Zitationssymbol ](images/citations-icon.svg) Symbol im linken Bedienfeld aus.
1. Ziehen Sie das Zitat aus dem Bedienfeld **Zitate** und legen Sie es an der entsprechenden Position im Thema ab.

   Sie können auch **Einfügen** unter ![](images/options.svg)**Optionen** auswählen, um ein Zitat einzufügen.

   ![Zitate einfügen](images/citation-panel-insert.png)
1. Um mehrere Zitate auszuwählen, klicken Sie mit der rechten Maustaste auf ein Zitat im Thema und wählen **Zitat ändern** aus dem Kontextmenü aus.
1. Wählen Sie die Zitate, die Sie einfügen möchten, im Dialogfeld **Zitat** aus.
1. Wählen Sie **Fertig** aus, um sie zum Thema hinzuzufügen.

Nachdem Sie Zitate in das Thema eingefügt haben, können Sie sie im Web-Editor in der Vorschau anzeigen. Sie können auch Inhalte mit Zitaten veröffentlichen, indem Sie die native PDF verwenden.



## Zitat löschen

Sie können Zitate aus dem Zitationsbedienfeld oder aus einem Thema löschen, in das Sie eingefügt haben.

### Löschen eines Zitats aus dem Zitatbereich

Gehen Sie wie folgt vor, um ein Zitat aus dem Zitationsbereich zu löschen:

1. Bewegen Sie den Mauszeiger über den Namen des Zitats in der Liste.
1. Wählen Sie das Symbol ![](images/options.svg) **Optionen** aus.
1. Wählen Sie die   **Löschen** ![](images/Delete_icon.svg).
Das Bestätigungsdialogfeld wird geöffnet.
1. Wählen Sie **Ja** aus.
Das ausgewählte Zitat wird aus dem Zitatbereich gelöscht.



### Löschen eines Zitats aus einem Thema

Gehen Sie wie folgt vor, um ein bereits im Thema verwendetes Zitat zu löschen:

Platzieren Sie im Thema den Cursor am Ende des Zitats.

1. Klicken Sie mit der rechten Maustaste auf ein Zitat im Thema und wählen **Zitat ändern** aus dem Kontextmenü. Das Dialogfeld „Zitat“ wird geöffnet.
   ![Kontextmenü eines Zitats](./images/modify-citation.png)

1. Sie können die Zitate auswählen, die Sie in das Dokument einfügen möchten.

   >[!NOTE]
   >
   >Die bereits im Thema verwendeten Zitate werden durch die Zitate ersetzt, die Sie im Dialogfeld auswählen.


1. Wählen Sie **Fertig** aus.

## Generieren der Ausgabe von Inhalten mit Zitaten

Nachdem Sie Zitate in das Thema eingefügt haben, können Sie Inhalte mit Zitaten mithilfe von nativem PDF veröffentlichen.

In der nativen PDF-Ausgabe werden die Zitate innerhalb des Inhalts angezeigt, in den Sie sie eingefügt haben. Sie können auch eine Bibliografie-Seite erstellen. Wenn Sie ein Zitat auswählen, werden Sie zur Seite „Bibliografie“ weitergeleitet.

Erstellen Sie ein **Zitate**-Seitenlayout in den PDF-Vorlagen und schließen Sie es in Ihr Dokument ein. Alle im Buch verwendeten Zitate werden auf einer Seite aufgelistet, die in der PDF-Ausgabe angezeigt wird. Weitere Informationen zum Erstellen eines Seiten-Layouts finden Sie unter [Erstellen eines Seiten-Layouts](../native-pdf/components-pdf-template.md#create-page-layout).


Um die Ansicht und das Erscheinungsbild der Zitatseite zu ändern, rufen Sie [PDF-Vorlagen anpassen](../native-pdf/pdf-template.md) auf.


### Anwenden eines Inhaltsstils auf ein Zitat

Formatieren Sie das Zitat, wenn Sie es zum Thema hinzufügen.

1. Wählen Sie **Stylesheets** im **Vorlagen**-Bereich einer nativen PDF-Ausgabevorgabe aus.   Dadurch wird das **STYLES**-Bedienfeld geöffnet, das alle Stiloptionen enthält.

1. Suchen Sie im Suchbereich nach `<cite>`.

Weitere Informationen zu Stilen finden Sie unter [Arbeiten mit den allgemeinen Inhaltsstilen](../native-pdf/stylesheet.md).
