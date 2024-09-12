---
title: Publish eines Themas für eine AEM Sites-Seite
description: Publish eines Themas oder der Elemente innerhalb eines Themas in eine Adobe Experience Manager Sites-Ausgabe.  Erfahren Sie, wie Sie die Experience Manager Sites-Seite für ein Thema anzeigen und erneut veröffentlichen können.
feature: Publishing
role: User
source-git-commit: 05c3e5e6f3c6aea4b3e3f3a52af5810307f1f29b
workflow-type: tm+mt
source-wordcount: '638'
ht-degree: 0%

---

# Publish Adobe Experience Manager Sites-Seiten


Experience Manager Sites-Seite bezieht sich auf auf der Adobe Experience Manager-Website veröffentlichte Inhalte. Mit Experience Manager Guides können Sie ein eigenständiges Thema auf einer Sites-Seite veröffentlichen.

Mit dieser Funktion können Sie ein Thema und seine Elemente veröffentlichen, ohne eine DITA-Zuordnung und die Ausgabevorgaben zu erstellen. Sie können das Thema einfach aktualisieren, die Sites-Seite erneut veröffentlichen und es über verschiedene Webseiten hinweg wiederverwenden. Mithilfe dieser Funktion können Sie mühelos eigenständige Artikel oder Marketinginhalte veröffentlichen.





Um eine Sites-Seite zu generieren, führen Sie die folgenden Schritte aus:




1. Wählen Sie **Neue Ausgabe** ![ neues Ausgabesymbol](./images/Add_icon.svg) aus dem Abschnitt **Ausgaben** in den **Dateieigenschaften** eines Themas.
1. Wählen Sie **Sites page** aus.


1. Füllen Sie im Dialogfeld **Seiten erstellen** die folgenden Details aus:
   ![Fügen Sie die Pfad- und Vorlagendetails auf der Seite &quot;Sites generieren&quot;hinzu](images/aem-sites-page-generate.png){width="500" align="left"}

   *Fügen Sie die Pfad-, Titel-, Namen- und Vorlagendetails hinzu, um ein Thema oder seine Elemente als Siteseite zu veröffentlichen. *

   * **Pfad**: Durchsuchen Sie den Pfad des Ordners, in dem Sie die Seite &quot;Sites&quot;veröffentlichen möchten, und wählen Sie ihn aus.
   * **Titel**: Geben Sie den Titel der Seite &quot;Sites&quot;ein. Standardmäßig wird der Titel mit dem Titel des Themas gefüllt. Sie können sie bearbeiten. Dieser Titel wird verwendet, um den Namen der Seite &quot;Sites&quot;zu generieren.
   * **Name**: Geben Sie den Namen der Seite &quot;Sites&quot;ein. Standardmäßig wird der Name mit dem Thementitel ausgefüllt und nicht zulässige Zeichen wie Leerzeichen und Sonderzeichen werden durch &quot;_&quot;ersetzt. Beispiel: *sample_sites_page*. Sie können sie bearbeiten. Dieser Name wird verwendet, um die URL für die Sites-Seite zu generieren.
   * **Seitenvorlage**: Wählen Sie die Sites-Seitenvorlage aus, um Ihre Sites-Seite zu erstellen. Sie können die Vorlagen im Ordner auf dem von Ihnen ausgewählten Pfad anzeigen. Ihr Administrator kann auch benutzerdefinierte Vorlagen hochladen.


   * Sie können auch verschiedene Bedingungen auswählen, um den Inhalt zu veröffentlichen.  Wählen Sie eine der folgenden Optionen aus:


      * **None**: Wählen Sie diese Option, wenn Sie keine Bedingung auf die veröffentlichte Ausgabe anwenden möchten.
      * **DITAVAL verwenden**: Wählen Sie die DITAVAL-Datei aus, um personalisierte Inhalte zu generieren. Sie können die DITAVAL-Datei über das Dialogfeld &quot;Durchsuchen&quot;oder durch Eingabe des Dateipfads auswählen.
      * **Verwenden von Attributen**: Sie können Bedingungsattribute in Ihren DITA-Themen definieren. Wählen Sie dann das Bedingungsattribut aus, um den relevanten Inhalt zu veröffentlichen.

     >[!NOTE]
     > 
     >Bedingungen werden nur aktiviert, wenn im Thema Bedingungsattribute definiert sind.



1. Klicken Sie auf **Erzeugen** , um die Seite &quot;Sites&quot;zu veröffentlichen.
1. Sie können die Sites-Seite für ein Thema im Abschnitt **Ausgaben** in den **Dateieigenschaften** anzeigen. Die Sites-Seiten werden entsprechend dem Datum und der Uhrzeit ihrer Veröffentlichung angezeigt, wobei die neueste Seite die erste ist.

   ![Anzeigen der Sites-Seite für ein Thema](images/aem-sites-outputs.png){width=300 align=&quot;left&quot;}

   *Sehen Sie sich die Sites-Seite an, die für ein Thema vorhanden ist, und veröffentlichen Sie sie erneut.*




Nachdem Sie die Sites-Seite veröffentlicht haben, können Sie sie auch auf jeder Adobe Experience Manager-Site verwenden.


## Optionsmenü für eine Experience Manager Sites

Sie können auch die folgenden Aktionen für eine Experience Manager Sites über das Menü **Optionen** ausführen:

* **Generieren**: Veröffentlichen Sie die Sites-Seite erneut, um sie mit dem neuesten Inhalt aus dem DITA-Thema zu aktualisieren. Wenn Sie die Ausgabe neu generieren, ohne den Pfad, den Namen, den Titel, die Vorlage und die Bedingungen zu ändern, wird die Sites-Seite einfach mit dem neuesten Inhalt aktualisiert.

* **Duplizieren**: Duplizieren Sie eine Sites-Seite. Sie können den Pfad, den Namen, den Titel und die Vorlage ändern. Sie können beim Duplizieren einer Sites-Seite auch andere Bedingungen auswählen.

* **Entfernen**: Entfernt eine Sites-Seite aus der Ausgabeliste. Eine Bestätigungsaufforderung wird angezeigt. Nach der Bestätigung wird die Seite &quot;Sites&quot;aus der Liste **Ausgaben** entfernt. Die Seite &quot;Sites&quot;wird jedoch nicht dauerhaft gelöscht.

* **Ansicht**: Zeigen Sie den Seiten-Editor &quot;Sites&quot;an. Sie können auch Änderungen vornehmen und speichern.
