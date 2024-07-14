---
title: Native PDF Publish-Funktion | Komponenten einer PDF-Vorlage
description: Erfahren Sie mehr über die verschiedenen Komponenten einer PDF-Vorlage und wie Sie diese anpassen und konfigurieren.
exl-id: 0ddb3b81-42ca-4a66-be7d-051a5175d53a
feature: Output Generation
role: Admin
level: Experienced
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '4975'
ht-degree: 0%

---

# Komponenten einer PDF-Vorlage {#components-pdf-template}

Eine PDF-Vorlage besteht aus vier Komponenten: Seitenlayouts, Stylesheets, Ressourcen und Einstellungen. Sie können eine Vorlage erstellen, indem Sie diese einzelnen Komponenten anpassen und die Vorlage beim Generieren einer PDF-Ausgabe mit einer Ausgabevorgabe verknüpfen. In den folgenden Abschnitten werden diese Komponenten und ihr Anpassungsprozess ausführlich beschrieben.


## Seitenlayouts erstellen und anpassen {#create-customize-page-layout}

Mit den Einstellungen in der Komponente Seitenlayouts können Sie die Struktur einer Seite entwerfen, indem Sie die Kopf- und Fußzeile sowie den Inhaltsbereich auf einer Seite definieren. Mit dem WYSIWYG-Seiten-Layout-Editor können Sie ein Seitenlayout für verschiedene Bereiche in einer PDF erstellen, wie z. B. die Vorder- und Rückseite, Kapitel, Tabelle von
Inhalt (Inhaltsverzeichnis), Index, leere Seite, Seiten mit Vorder-Materie, Seiten mit der Rückmeldung, Liste der Zahlen (LOF), Liste der Tabellen (LOT), Glossar oder erstellen Sie ein Layout für eine benutzerdefinierte Seite. In den PDF-Vorlageneinstellungen können Sie ein Seitenlayout mit verschiedenen Abschnitten innerhalb einer PDF zuweisen, die dann zum Generieren der PDF-Ausgabe verwendet werden.

### Neues Seitenlayout erstellen {#create-page-layout}

>[!NOTE]
>
>Es gibt Beispielseitenlayouts, die standardmäßig bereitgestellt werden. Sie können diese anpassen oder neue Seitenlayouts erstellen.

1. Gehen Sie im Web Editor zur Registerkarte **Ausgabe** .
1. Erweitern Sie die linke Seitenleiste und klicken Sie auf **Vorlagen**.
1. Öffnen Sie die Vorlage, mit der Sie arbeiten möchten.

   >[!NOTE]
   >
   >Sie können eine Vorlage öffnen, indem Sie auf ihren Namen doppelklicken oder auf das Symbol > neben ihrem Namen klicken.

1. Führen Sie einen der folgenden Schritte aus, um ein neues Seitenlayout zu erstellen:

   * Bewegen Sie den Mauszeiger über **Seitenlayouts**, klicken Sie auf das Symbol (*Optionen*) **...** und wählen Sie **Neues Seitenlayout**.


   * Klicken Sie im Bedienfeld **Vorlagen** auf das Symbol **+** neben **Vorlagen** und wählen Sie im Kontextmenü die Option **Seitenlayout** aus.


     Dadurch wird das Dialogfeld **Layout hinzufügen** geöffnet.

     <img src="assets/add-layout-2.png" alt="Dialogfeld &quot;Layout hinzufügen&quot;" width="250">

1. Geben Sie einen Namen für das neue Seitenlayout an.
   >[!NOTE]
   >
   >Vermeiden Sie die Verwendung von Sonderzeichen bei der Benennung eines Seitenlayouts. Ein Leerzeichen im Namen wird durch einen Unterstrich &quot;_&quot;ersetzt.

1. Klicken Sie auf **Fertig**.

   Das neue Layout wird unter Seitenlayouts erstellt und hinzugefügt.


### Duplizieren eines Seitenlayouts {#duplicate-page-layout}

1. Doppelklicken Sie im Abschnitt **Vorlagen** der Vorlage, die Sie duplizieren möchten, auf **Seitenlayouts** oder klicken Sie vor **Seitenlayouts** auf das Symbol **>** .

   Dadurch wird die Liste der Seitenlayouts in der Vorlage angezeigt.

1. Bewegen Sie den Mauszeiger über das Seitenlayout, das Sie duplizieren möchten, klicken Sie auf das Symbol (*Optionen* ) **...** und wählen Sie im Kontextmenü die Option **Duplizieren** aus.

1. Geben Sie im Dialogfeld _Layout duplizieren_ einen Namen für das Seitenlayout ein.

1. Klicken Sie auf **Fertig**.
Eine Kopie des ausgewählten Seitenlayouts wird erstellt und unter Seitenlayouts hinzugefügt.

### Seitenlayout anpassen {#customize-page-layout}

1. Doppelklicken Sie im Abschnitt **Vorlagen** der Vorlage, die Sie bearbeiten möchten, auf **Seitenlayouts** oder klicken Sie auf das Symbol **>** vor dem Symbol **Seitenlayouts**.

   Dadurch wird die Liste der Seitenlayouts in der Vorlage angezeigt.
1. Führen Sie einen der folgenden Schritte aus, um das Seitenlayout anzupassen:
   * Doppelklicken Sie auf ein beliebiges Seitenlayout.
   * Bewegen Sie den Mauszeiger über ein Seitenlayout, klicken Sie auf das Symbol (*Optionen*) **...** und wählen Sie im Kontextmenü die Option **Bearbeiten** aus.

   Dadurch wird der Seitenlayout-Editor zur Anpassung geöffnet.
1. Klicken Sie nach den gewünschten Änderungen auf *Alle speichern* (oder `Crl+S`).

   Weitere Informationen zum Definieren einzelner Layoutelemente wie Kopf- und Fußzeile, Seitenzahl, Titel und mehr finden Sie unter [Erstellen eines Seitenlayouts](design-page-layout.md).

## Verwenden von Stylesheets zum Anpassen von PDF {#stylesheet-customization}

Mit den Einstellungen in der Komponente &quot;Stylesheets&quot;können Sie die Seitenlayoutkomponenten und DITA-Inhalte mit dem WYSIWYG-Editor gestalten oder direkt mit der CSS-Datei arbeiten. Sie können eigene Stile erstellen oder die Standardstileigenschaften anpassen. Der WYSIWYG-Editor bietet Ihnen Zugriff auf die meisten Eigenschaften, die Sie zum Gestalten Ihres Seitenlayouts oder DITA-Inhalts benötigen. Für erweiterte Anpassungen können Sie direkt in der Source-Ansicht arbeiten.

### Neues Stylesheet erstellen {#create-stylesheet}

Während CSS-Dateien für Inhalt und Layout bereitgestellt werden, können Sie ein neues Stylesheet erstellen, um mehrere Anpassungen auf einen bestimmten Stiltyp anzuwenden, der dann auf eine Zielkomponente angewendet werden kann. Standardmäßig werden Beispiel-CSS-Dateien innerhalb des Produkts gebündelt. Diese CSS-Dateien sollen Ihnen dabei helfen, Ihre Stilinformationen über Inhalte und Layouts hinweg zu organisieren. Sie können diese Stile in einer oder mehreren CSS-Dateien zusammenführen.

Jedes Mal, wenn Sie ein neues Seitenlayout erstellen, ist die Datei `layout.css` standardmäßig im neuen Seitenlayout enthalten. Wenn das Seitenlayout Stile aus einer anderen CSS-Datei enthalten soll, können Sie die gewünschte CSS-Datei einfach per Drag-and-Drop in den Inhaltsbearbeitungsbereich des neuen Seitenlayouts ziehen. Um zu überprüfen, ob die CSS-Datei in das Seitenlayout eingebettet wurde, wechseln Sie zur Source-Ansicht und Sie finden einen Link zur CSS-Datei im Element `<head>` .


Gehen Sie wie folgt vor, um ein Stylesheet zu erstellen:
1. Führen Sie im Bedienfeld **Vorlagen** einen der folgenden Schritte aus:
   * Bewegen Sie den Mauszeiger über die Registerkarte **Stylesheets**, klicken Sie auf das Symbol (*Optionen*) **...** und wählen Sie **Neues Stylesheet**.
   * Klicken Sie auf das Symbol **+** neben **Vorlagen** und wählen Sie **Stylesheet** aus dem Kontextmenü.

   Dadurch wird das Dialogfeld Stylesheet hinzufügen geöffnet.

   <img src="assets/add-stylesheet.png" alt="Stylesheet hinzufügen" width="250">
1. Geben Sie einen Namen für das neue Stylesheet an.
1. Klicken Sie auf **Fertig**.

   Ein neues Stylesheet wird unter dem Abschnitt Stylesheets erstellt und hinzugefügt.

### Neuen Stil erstellen {#create-style}

Standardmäßig enthalten die mit der Vorlage bereitgestellten CSS-Dateien Stile für Überschrift, Absatz, Zeichen, Hyperlink, Bild, Tabelle, div, Seite und andere Stile. Sie können das Standard-Stilformat überschreiben oder einen neuen Stil erstellen.


Sie können einen neuen Stil erstellen, um ihn im Seitenlayout der Vorlage zu verwenden, oder einen benutzerdefinierten Stil für ein DITA-Element anwenden. Um diese benutzerdefinierten Stile auf das DITA-Element anzuwenden, müssen Sie sicherstellen, dass der Klassenname des Stils mit dem Namen des DITA-Elements oder dem Attribut `outputclass` übereinstimmt.  Beispiel: `<div>` in DITA wird vom Attribut `.div {}` in CSS oder seinem Attribut `outputclass` verwaltet. Wenn Sie in DITA den Wert `<div outputclass="my-div">` anwenden, wird er in der CSS durch den Wert `.div {}` oder den Wert `.my-div {}` geregelt.



Gehen Sie wie folgt vor, um einen neuen Stil zu erstellen:
1. Erweitern Sie die linke Seitenleiste und doppelklicken Sie auf die Vorlage, in der Sie den Stil erstellen möchten.
1. Erweitern Sie den Abschnitt **Stylesheets** . Dadurch wird der Bereich **Stile** geöffnet, der alle Stiloptionen enthält.
1. Klicken Sie auf das Symbol + , um einen neuen Stil hinzuzufügen.

   Das Dialogfeld **Stil hinzufügen** wird geöffnet.


   <img src="assets/add-style.png" alt="Neuen Stil hinzufügen" width="500"/>

1. Geben Sie einen **Class**-Namen an. Um einen Stil auf das DITA-Element anzuwenden, stellen Sie sicher, dass der Klassenname des Stils mit dem Namen des DITA-Elements oder dem Attribut `outputclass` übereinstimmt.
1. Wählen Sie im Feld **Tag** (optional) ein Tag aus, für das Sie einen neuen Stil erstellen möchten.


1. Wählen Sie eine **Pseudo-Klasse** aus, um ein Element zu formatieren. Mit einer Pseudo-Klasse können Sie einen speziellen Status des Elements definieren. Verwenden Sie beispielsweise die Pseudo-Klasse, um ein Element zu formatieren, wenn Sie den Mauszeiger darüber bewegen oder wenn Sie den Fokus darauf legen. Sie können auch mehrere Pseudoklassen auswählen. Sie können beispielsweise die Pseudo-Klasse `a::visited {color: blue;}` verwenden, um die besuchten Links zu formatieren.

1. Fügen Sie die Auswahl für den neuen Stil hinzu. Mit dem Feld **Selektor** können Sie benutzerdefinierte Selektoren neben der Kombination aus Klasse, Tag und Pseudo-Klasse hinzufügen. Sie können beispielsweise den Stil `table a.link` für alle Hyperlinks in einer Tabelle erstellen.

   Weitere Informationen zu CSS-Tags finden Sie unter [Siehe CSS-Stilgrammatik](https://www.w3.org/TR/CSS21/syndata.html#characters).

1. Klicken Sie auf **Fertig**.

   Ein neuer Stil wird erstellt und der Stilliste hinzugefügt.

### Vordefinierten oder neuen Stil anpassen {#customize-style}

Nachdem Sie eine neue CSS-Datei mit Standardstilen erstellt haben oder die Stile in einer vorhandenen CSS-Datei anpassen möchten, können Sie dazu den Stileditor verwenden.

Gehen Sie wie folgt vor, um einen Stil anzupassen:
1. Doppelklicken Sie auf **Stylesheets** oder klicken Sie auf das Symbol **>** vor **Stylesheets**.

   Dadurch werden die standardmäßigen (Inhalt und Layout) und benutzerdefinierten CSS-Dateien angezeigt.
1. Öffnen Sie ein Stylesheet zur Bearbeitung.

   Führen Sie einen der folgenden Schritte aus, um das Stylesheet zur Bearbeitung zu öffnen:
   * Doppelklicken Sie auf den Stylesheet-Namen.
   * Bewegen Sie den Mauszeiger über den Namen des Stylesheets und klicken Sie auf das Symbol Optionen ... und wählen Sie Bearbeiten.

   Dadurch wird das Stylesheet zur Bearbeitung geöffnet und die Liste der Stile im Bedienfeld &quot;Stile&quot;angezeigt.

   <img src="assets/customize-style.png" alt="Stil anpassen" width="800">

1. Um einen Stil anzupassen, wählen Sie den Stil aus, der angezeigt werden soll, und passen Sie ihn mithilfe des Stileditors an.


### Eigenschaften von Stilen

Im mittleren Bereich können Sie die Eigenschaften bearbeiten. Es kann jedoch schwierig sein, eine Momentaufnahme aller vorhandenen Werte zu erhalten.  Der Bereich **Eigenschaften** bietet einen schnellen Überblick über alle Attribute und Werte des Stils.

Im mittleren Bereich können Sie die häufig verwendeten Eigenschaften bearbeiten, jedoch nicht alle von CSS unterstützten Eigenschaften. Im Bereich **Eigenschaften** können Sie alle von CSS unterstützten Eigenschaften bearbeiten und eine Vorschau davon anzeigen. Sie müssen nicht zur Quellansicht wechseln, um Eigenschaften zu bearbeiten.


Erfahren Sie mehr über die Verwendung des Stileditors zum Arbeiten mit den gängigen Inhaltsstilen ](stylesheet.md).[

## Arbeiten mit Ressourcen {#work-with-resources}

Dies ist ein Container für alle Assets, die zum Entwerfen einer Vorlage verwendet werden. Sie können sich dies als Ordner vorstellen, der Assets wie Hintergrundbilder, benutzerdefinierte Schriftarten, Logos und mehr enthält. Jedes Mal, wenn Sie ein Asset in Ihrer Vorlage hinzufügen, wird es in den Asset-Ordner hochgeladen oder dort eingecheckt. Anschließend können Sie diese Assets verwenden, um Ihre PDF-Vorlagen anzupassen oder zu entwerfen.

Gehen Sie wie folgt vor, um eine Asset-Datei zum Ordner Ressourcen hinzuzufügen:

1. Bewegen Sie den Mauszeiger über die Registerkarte Ressourcen-Ordner , klicken Sie auf das Symbol Optionen ... und wählen Sie Importieren.

   Dadurch wird das Dialogfeld Assets hochladen geöffnet.

   <img src="assets/resources-import-assets.png" alt="Hochladen von Assets" width="300">

   Der Pfad, in den die Asset-Datei hochgeladen wird, wird im Feld **Asset-Ordner auswählen** angezeigt.
   >[!NOTE]
   >
   >Sie können den Pfad zum Hochladen von Assets nicht ändern. Standardmäßig werden alle Assets im Ordner &quot;`/content/dam/dita-templates/pdf/<PDF-template-name>`&quot;gespeichert.

1. Klicken Sie auf **Dateien auswählen** , um die Asset-Datei von Ihrem lokalen Computer aus zu durchsuchen.

1. Klicken Sie auf **Hochladen**.
Die ausgewählte Datei wird importiert und im Ordner Ressourcen aufgeführt.

## Erweiterte PDF-Einstellungen {#advanced-pdf-settings}

Verwenden Sie den Bereich Einstellungen , um das Layout der PDF zu konfigurieren, das PDF von ungeraden oder geraden Seiten zu starten, die Formate für die Querverweise zu konfigurieren und Druckmarken in der endgültigen PDF zu aktivieren, die generiert wird.
die Vorlage verwenden.

Klicken Sie zum Konfigurieren im Bereich **Vorlagen** auf **Einstellungen** , um die folgenden Optionen anzuzeigen:

### Allgemein

Legen Sie die grundlegenden Konfigurationseinstellungen für das Starten eines Kapitels von einer ungeraden oder geraden Seite, die TOC-Struktur fest und definieren Sie das Füllzeichenzeilenformat für die TOC-Einträge. Sie können die folgende Einstellung definieren:

* **Neues Kapitel von** starten: Ermöglicht die Definition, wie die einzelnen Kapitel im endgültigen PDF veröffentlicht werden. Sie können aus den Optionen **Neue Seite**, **Ungerade Seite**, **Gerade Seite** oder **Aktuelle Seite** auswählen. Wenn Sie ein neues Kapitel von einer ungeraden Seite aus beginnen möchten, wird nach einem Kapitel, das auf einer ungeraden Seite endet, eine leere Seite eingefügt. Wenn Ihr Kapitel beispielsweise auf Seite 15 endet, fügt der Veröffentlichungsprozess eine leere 16<sup>th</sup>-Seite ein, damit das neue Kapitel von der 17<sup>th</sup>-Seite aus beginnen kann.  Wenn Sie die Option **Aktuelle Seite** auswählen, werden alle Kapitel als Fortsetzung ohne Seitenumbrüche veröffentlicht. Wenn ein Kapitel beispielsweise in der Mitte von Seite 15 endet, wird das nächste Kapitel auch von der 15. Seite selbst aus gestartet.

* **Beginnen jedes Thema von einer neuen Seite**: Wenn jedes Thema in Ihrem Kapitel von einer neuen Seite aus beginnen soll, wählen Sie die Option **Jedes Thema von einer neuen Seite starten** . Wenn Sie Ihre Themen ohne Seitenlücken fortsetzen möchten, deaktivieren Sie diese Option.

* **TOC Structure**: Ermöglicht die Anpassung der Hierarchie des Inhaltsverzeichnisses. Es werden die folgenden zusätzlichen Einstellungen verwendet:

   * **Überschriften bis Ebene** verwenden: Mit dieser Option können Sie die Anzahl der Überschriftenebenen anpassen, die in der TOC-Struktur Ihrer PDF angezeigt werden sollen.
   * **Keine Seitenzahl für die erste Ebene im Inhaltsverzeichnis anzeigen**: Wählen Sie diese Option, um die entsprechenden Seitenzahlen für alle Kapitel auszublenden, die verschachtelte oder untergeordnete Themen enthalten. Betrachten Sie das folgende Beispiel, in dem eine Ausgabe erstellt wird, ohne diese Option auszuwählen.

  <img src="assets/page-number-in-toc.png" alt="Hochladen von Assets" width="250">

  Im obigen Beispiel sind Erweiterte PDF-Einstellungen, Anhang und rechtliche Themen die ersten Themenüberschriften oder Kapiteltitel. Allen diesen Überschriften wird eine Seitenzahl zugewiesen.

  Wenn Sie jetzt diese Option auswählen und die Ausgabe generieren, erhalten Sie das folgende Inhaltsverzeichnis:

  <img src="assets/page-number-missing-in-toc.png" alt="Hochladen von Assets" width="250">

  Hier können Sie bemerken, dass die erweiterten PDF-Einstellungen des ersten Kapitels keine Seitenzahl erhalten, da sie verschachtelte oder untergeordnete Themen haben. Eine Seitenzahl hingegen, wenn sie Anhang und Legal zugewiesen wird, da es sich um eigenständige Themen ohne untergeordnetes Thema handelt.

* **Kapitelnummer nicht im Inhaltsverzeichnis anzeigen** : Wählen Sie diese Option, um die Kapitelnamen ohne Kapitelnummern im Inhaltsverzeichnis anzuzeigen.   Standardmäßig werden die Kapitelnummern im TOC Ihrer PDF-Ausgabe angezeigt.
* **Füllzeichenformat**: Verwenden Sie die Dropdown-Liste, um die Füllzeichenlinien &quot;Gepunktet&quot;, &quot;Durchgehend&quot;oder &quot;Leerzeichen&quot;auszuwählen, um die Überschriftenebenen mit den entsprechenden Seitenzahlen zu verbinden.
Informationen zum Anwenden der TOC-Struktur und des Stils von Überschriftenebenen finden Sie unter [Hinzufügen eines Kapitel-TOC](design-page-layout.md#add-chapter-toc).

  >[!NOTE]
  >
  >Wenn Sie CSS-Entwickler sind, können Sie das Füllzeichenformat auch direkt in der CSS-Datei definieren.

* **Verwenden Sie die Tabellenfortsetzungsmarke**: Wählen Sie diese Option aus, um Markierungen für lange Tabellen zu definieren, die über mehrere Seiten verteilt sind.
Sie können den Text definieren, der vor und nach dem Umbruch angezeigt werden soll. Beispielsweise wird eine Tabelle auf Seite 5 umgebrochen und Sie definieren `<Continued on page %page-num%>` für **Text vor Umbruch**.  Im Text wird unten auf Seite 5 &quot;Fortsetzung auf Seite 6&quot;angezeigt.

  Verwenden Sie Sprachvariablen, um den Text für die Fortsetzung der Markierung vor und nach der Pause zu definieren. Abhängig von Ihrer ausgewählten Sprache wird der lokalisierte Wert automatisch in der PDF-Ausgabe ausgewählt. Sie können beispielsweise `Continued on page %page-num%` als Text in englischer Sprache und `Fortsetzung auf Seite %page-num%` in deutscher Sprache veröffentlichen.

  Bewegen <img src="./assets/info-details.svg" alt= "Infosymbol" width="25"> in der Nähe der Option, um weitere Details dazu anzuzeigen.
* **Verknüpfen Sie Glossarbegriffe mit der Glossarseite**: Wählen Sie diese Option, um die Glossarbegriffe als Hyperlinks im Inhalt anzuzeigen und sie mit den Begriffen auf der Glossarseite zu verknüpfen. Dies hilft den Lesern, die Definition eines Begriffs im Glossar schnell anzuzeigen.

  Um die Glossarbegriffe in Hyperlinks zu konvertieren, gehen Sie folgendermaßen vor:
   * Aktivieren Sie **Glossar** auf der Registerkarte **Seitenlayout-Reihenfolge** für eine DITA-Zuordnung.
   * Fügen Sie das Glossar in die &quot;Back Matter Pages&quot;für eine Buchkarte ein.

  Wenn Sie die Glossarseite nicht aktivieren, werden die Glossarbegriffe im Inhalt nicht in Hyperlinks in der PDF-Ausgabe konvertiert.
  <!--For more information on using table continuation markers, see Use table continuation markers.-->

### Seitenlayouts {#page-layouts}

Mit den Einstellungen für Seitenlayouts können Sie vollständig festlegen, welches Seitenlayout für einen bestimmten Abschnitt Ihres Dokuments verwendet werden soll. Um beispielsweise ein Layout für das Inhaltsverzeichnis auszuwählen, klicken Sie auf das Dropdown-Menü unter dem Feld Inhaltsverzeichnis und wählen Sie das Layout aus, das Sie zum Generieren des Inhaltsverzeichnisses entwickelt haben.

Beachten Sie, dass die Einstellungen für die Lesekarte Vorrang vor den Einstellungen für das Seitenlayout haben.

Die folgenden Einstellungen sind im Abschnitt Seitenlayout verfügbar:

<img src="assets/template-page-layout.png" alt="Seitenlayouts" width="550">


**Standardseitenlayout**: Wählen Sie ein Seitenlayout, das als Standardlayout für alle Seiten in Ihrer PDF dient. Dies ist das grundlegende Seitenlayout, das auf die Abschnitte oder Themen angewendet wird, in denen Sie kein dediziertes Seitenlayout erstellt haben.

**Seitenlayout für verschiedene Bereiche**: Sie können ein Seitenlayout den folgenden Abschnitten Ihrer PDF-Ausgabe zuordnen. Wenn Sie ein Seitenlayout für den zugehörigen Abschnitt entworfen haben, wählen Sie es aus der Dropdownliste aus. Wenn für bestimmte Abschnitte keine Seitenlayouts erstellt wurden, wird das standardmäßige Seitenlayout angewendet.

* **Kapitel und Themen**: Sie können das Seitenlayout für die Kapitel und Themen festlegen. Das ausgewählte Layout wird auf alle Kapitel und Themen angewendet.

* **TOC**: Wenn Sie das Seitenlayout für das Inhaltsverzeichnis entworfen haben, wählen Sie in der Dropdownliste die Option **TOC** aus, und alle TOC-Seiten in Ihrem Dokument haben das Layout für die Inhaltsverzeichnis-Seite.

* **Liste der Abbildungen und Tabellenliste**: Sie können auch das Seitenlayout für Zahlen und Tabellen festlegen. Das ausgewählte Layout wird auf alle Abbildungen und Tabellen angewendet.

* **Index**: Wenn Sie ein Indexseitenlayout entworfen haben, ordnen Sie es der Option Index zu. Mithilfe der Stylesheets können Sie verschiedene Indexelemente in der PDF-Ausgabe formatieren. Verwenden Sie die Indexstile `.idx-header`, `.idx-footer`, `.idx-body`, `.idx-title`, `.idx-keyword-group`, `.idx-unit`, `.idx-keyword`, `.idx-name`, `.idx-link` und `.idx-child`, um die Stile für die Elemente des Index anzupassen.

* **Glossar**: Wenn Sie ein Glossar-Seitenlayout haben, ordnen Sie es der Glossaroption zu.

  Die Begriffe im Glossar Ihrer PDF-Ausgabe werden immer in alphabetischer Reihenfolge sortiert.

  Sie können auch das Tag `sort-as` hinzufügen, um einen Sortierschlüssel für die Glossarbegriffe zu definieren. Experience Manager Guides verwendet dann den Sortierschlüssel, um die Glossarbegriffe anstelle der Glossarbegriffe zu sortieren. Wenn Sie den Sortierschlüssel nicht definiert haben, werden die Glossarbegriffe zum Sortieren verwendet. Sie können beispielsweise das Tag `sort-as` zum Tag `glossterm` hinzufügen und dessen Wert für den Begriff &quot;USB&quot;(z. B. `<glossterm>USB<sort-as>A</sort-as></glossterm>`) auf `A` setzen. Auf ähnliche Weise können Sie das Tag `sort-as` hinzufügen und seinen Wert für den Begriff &quot;Pen Drive&quot;auf `B` setzen. Wenn Sie diese Glossarbegriffe sortieren, erscheint der Sortierschlüssel `A` für den Glossarbegriff &quot;USB&quot; vor dem Sortierschlüssel `B` für den Glossarbegriff &quot;Pen Drive&quot;. In der PDF-Ausgabe kommt &quot;USB&quot; also vor &quot;Pen Drive&quot; auf der Glossarseite.

  Mithilfe der Stylesheets können Sie verschiedene Glossarelemente in der PDF-Ausgabe gestalten. Verwenden Sie die Glossarstile `.glo-header`, `.glo-footer`, `.glo-body`, `.glo-title`, `.glo-unit`, `.glo-link` und `.glo-term`, um die Stile für die Elemente des Glossars anzupassen.

  Erfahren Sie mehr über die Verwendung des Stileditors zum Arbeiten mit den gängigen Inhaltsstilen ](stylesheet.md).[

* **Seiten mit Vorder- und Rückmeldungen**: Diese Seitenlayouts definieren den Stil für Seiten mit Vorder- oder Rückbestandteilen in Ihrem Buch. Wenn Sie das Layout der Vorderseite entworfen haben, ordnen Sie es der Option **Seiten mit Vorder-Materie** zu. Wenn Sie das Layout der Vorderseite aus dem Dropdown-Menü auswählen, wird das Layout der Vorderseite auf alle in der Vorderseite vorhandenen Themen angewendet.

  Wenn Sie das Layout für die umgekehrte Materie entworfen haben, ordnen Sie es der Option **Rücken Matter Pages** zu. Wenn Sie das Layout für die Hintergrundmatte aus der Dropdown-Liste auswählen, wird das Layout für die Hintergrundmatte auf alle Themen angewendet, die in der Hintergrundmatte vorhanden sind.

  **Seiten mit Vordergrund** wird auch als Ausweichlayout für die Tabellen **TOC**, **Liste der Abbildungen** und &quot;Tabellenliste&quot;verwendet.  Gleichermaßen wird **Back Matter Pages** auch als Ausweichlayout für die Layouts **Index** und **Glossar** verwendet. Wenn Sie das Layout für diese Seiten nicht ausgewählt haben, wird das ausgewählte Seiten-Layout &quot;Vorder-&quot;und &quot;RückMatter-Seiten&quot;angewendet.  Wenn Sie das Layout Seiten mit Vorder- oder RückMaterie nicht ausgewählt haben, wird das standardmäßige Seitenlayout auf sie angewendet.

* **Seitenlayout für leere Seiten**:    Sie können auch das Seitenlayout für leere Seiten festlegen. Das ausgewählte Layout wird auf alle leeren Seiten angewendet. Wenn Sie beispielsweise ein leeres Seitenlayout für alle leeren Seiten entworfen haben, wählen Sie in der Dropdown-Liste die Option &quot;**Leer**&quot;, und alle leeren Seiten in Ihrem Dokument haben das Layout &quot;Leere Seite&quot;.

* **Titelseite und Rückseite**: Wenn Sie ein Titelseitenlayout entworfen haben, ordnen Sie es der Option **Titelseite** zu. Wenn Sie ein Layout für die Rückseite haben, ordnen Sie es der Option **Zurück-Seite** zu. Wenn keine Deckblatt- oder Rückseite-Layouts erstellt wurden, wird das standardmäßige Seitenlayout angewendet.



Weitere Informationen zu Seitenlayouts finden Sie unter [Erstellen eines Seitenlayouts](design-page-layout.md).

### Seitenlayout-Reihenfolge {#page-order}

Sie können die folgenden Bereiche in Ihrer PDF ein- oder ausblenden und auch die Reihenfolge anordnen, in der sie in Ihrer endgültigen PDF-Ausgabe angezeigt werden sollen:



* IHV
* Kapitel und Themen
* Bildliste
* Tabellenliste
* Index
* Glossar
* Zitat

  <img src="assets/page-order-advance-settings.png" alt="Seitenlayoutreihenfolge" width="550">

  Wenn Sie in Ihrer PDF-Ausgabe keinen bestimmten Bereich anzeigen möchten, können Sie dies verbergen, indem Sie den Umschalter ausschalten.

  Sie können auch die Reihenfolge definieren, in der diese unterschiedlichen Bereiche in Ihrer PDF erstellt werden. Um die Standardreihenfolge dieser Abschnitte zu ändern, wählen Sie die gepunkteten Balken aus, um die Abschnitte per Drag-and-Drop an die gewünschte Position zu ziehen.

  >[!NOTE]
  >
  > Die Einstellungen für Reihenfolge und Einbindung gelten nur für eine DITA-Zuordnung. Bei einer Lesekarte sind diese Einstellungen nicht anwendbar. Die Seiten in einer Lesekarte werden gemäß der Reihenfolge der Abschnitte in der Lesekarte angezeigt.


.
Das Layout **Kapitel und Themen** ist standardmäßig immer aktiviert. Sie können sie nicht umschalten.

**Seiten zusammenführen**

Standardmäßig beginnen alle Abschnitte auf einer neuen Seite. Wählen Sie die Option **Vorherige Seite** oder **Nächste Seite** aus dem Dropdown-Menü **Zusammenführen mit** aus, um einen Abschnitt mit einer vorherigen oder nächsten Seite zusammenzuführen. Dadurch wird der Abschnitt in Weiterführung mit der ausgewählten Seite in der PDF-Ausgabe veröffentlicht. Dadurch gibt es keinen Seitenumbruch dazwischen.

>[!NOTE]
>
> Diese Einstellung gilt nur für den Abschnitt und nicht für dessen Komponenten.  Wenn Sie beispielsweise die Option **Vorherige Seite** für **Kapitel und Themen** auswählen, wird der Abschnitt **Kapitel und Themen** mit der vorherigen Seite zusammengeführt. Die verschiedenen Kapitel und Themen werden gemäß den Einstellungen für **Allgemein** veröffentlicht. Wenn Sie z. B. in **Ein neues Kapitel über die Einstellung** beginnen, wählen Sie **Ungerade Seite** aus, wird nach einem Kapitel, das auf einer ungeraden Seite endet, eine leere Seite eingefügt.

Wenn Sie einen Abschnitt mit der vorherigen Seite oder der nächsten Seite zusammenführen, wird der Inhalt zusammengeführt und der Stil des Zielabschnitts, in dem der Inhalt zusammengeführt wird, wird angewendet.

Wenn Sie beispielsweise &quot;**TOC**&quot;und &quot;**Kapitel und Themen**&quot;aktivieren und &quot;**Nächste Seite**&quot;für &quot;**TOC**&quot;auswählen, wird &quot;**TOC**&quot;mit dem nächsten Abschnitt zusammengeführt, nämlich dem Abschnitt &quot;**Kapitel und Themen**&quot;. Der Stil des Abschnitts **Kapitel und Themen** wird auf den zusammengeführten Inhalt beider Abschnitte angewendet.

Die Zusammenführungsoption funktioniert nacheinander. Wenn Sie also für mehrere fortlaufende Abschnitte **Nächste Seite** ausgewählt haben, werden alle mit dem ersten Abschnitt (in die nächste Richtung) zusammengeführt, für den diese Eigenschaft nicht festgelegt ist. Sie aktivieren beispielsweise **TOC**, **Kapitel und Themen**, **Liste der Abbildungen** und **Index**. Wenn Sie dann **Nächste Seite** für **TOC**, **Kapitel und Themen**, **Liste der Abbildungen** und **Keine** für **Index** festlegen, werden alle mit **Index** zusammengeführt.


**Statische Seiten**

Die verschiedenen Seitenlayouts helfen Ihnen dabei, die Ausgabe der verschiedenen Abschnitte zu entwerfen. Diese Abschnitte werden beim Veröffentlichen der Ausgabe aus der DITA-Zuordnung generiert.
Sie können auch benutzerdefinierte Seitenlayouts erstellen und diese als statische PDF-Seiten veröffentlichen. Auf diese Weise können Sie statischen Inhalt wie Notizen oder leere Seiten hinzufügen.

Führen Sie die folgenden Schritte aus, um ein benutzerdefiniertes Seitenlayout hinzuzufügen:

1. Wählen Sie **Hinzufügen** ![](assets/add-icon.svg) aus, um ein neues Seitenlayout hinzuzufügen. Das Bedienfeld &quot;Seitenlayout hinzufügen&quot;wird geöffnet.
2. Wählen Sie das Seitenlayout aus der Liste aus und klicken Sie auf Hinzufügen. Das neue Seitenlayout wird der Liste der Seitenlayouts hinzugefügt.


Sie können auch die folgenden Aktionen durchführen:

* Wählen Sie die gepunkteten Balken aus, um das Seitenlayout an die gewünschte Position zu ziehen.

* Wählen Sie **Layout entfernen** ![](assets/delete-icon.svg) aus, um ein Layout zu entfernen.

* Sie können auch eine statische Seite mit der vorherigen oder der nächsten Seite zusammenführen.

* Sie können auch ein benutzerdefiniertes Layout mehrmals hinzufügen und sortieren. Auf diese Weise können Sie statischen Inhalt entsprechend veröffentlichen.

  Beispielsweise können Sie ein benutzerdefiniertes Layout verwenden, um eine statische Warnung mehrmals in der PDF-Ausgabe zu veröffentlichen.



### Seitenorganisation

Die Seiten in einem PDF-Dokument werden in der Regel entsprechend dem Inhalt in der DITA-Map- oder Bookmap-Datei veröffentlicht. Sie können jedoch auch die Reihenfolge der Seiten im PDF-Dokument ändern. Sie können beispielsweise ein mehrseitiges Dokument als Booklet drucken. Wenn Sie die Blätter zusammenkleben, falten und stapeln, ist das Ergebnis ein einzelnes Buch mit der richtigen Seitenreihenfolge.  Sie können dann die veröffentlichte Broschüre wie ein Buch lesen.

<img src="assets/template-page-organization.png" alt="Seitenorganisation" width="550">


Die folgenden Einstellungen sind im Abschnitt **Seitenorganisation** verfügbar:

#### Seitenreihenfolge

Wählen Sie eine Seitenreihenfolge aus, die die Reihenfolge der Seiten in Ihrem PDF-Dokument bestimmt. Sie können die folgenden Optionen aus der Dropdown-Liste auswählen:

* **Standard**: Die Standardreihenfolge der Seiten gemäß der Quelldatei.
* **Ungerade Seiten zuerst hinzufügen**: Alle ungeraden Seiten werden vor allen geraden Seiten verschoben.
* **Gerade Seiten zuerst**: Alle geraden Seiten werden vor allen ungeraden Seiten verschoben.
* **Umkehren**: Die Seitenreihenfolge wird umgekehrt.
* **Lesezeichen**: Alle Seiten werden wie in einem Lesezeichen angeordnet.
* **Rechts nach links Lesezeichen**: Alle Seiten befinden sich in der Lesezeichenreihenfolge von rechts nach links.
* **Benutzerdefiniert**: Definieren Sie eine benutzerdefinierte Reihenfolge der Seiten anstelle einer vordefinierten Reihenfolge.
   * &quot;a..b&quot;— Alle aufeinander folgenden Seiten von a bis b.
   * &quot;a,b,c&quot; — Neue Seitenreihenfolge a, b, c.
   * &quot;a*b&quot;- Die Seite a wird wiederholt.
   * &quot;-a&quot;- Negative Seitenzahlen zählen rückwärts ab der letzten Seite und können mit anderen benutzerdefinierten Bestellungen kombiniert werden.
   * &quot;X&quot;— Alle Seiten des Dokuments. Gleiches Ergebnis wie &quot;1..-1&quot;.

Sie können beispielsweise eine benutzerdefinierte Reihenfolge wie &quot;2,3,5*2,7.10,-1,-2&quot;festlegen.
Die angegebene Seitenreihenfolge führt dazu, dass ein PDF die folgenden Seitenzahlen aus dem Originaldokument hat, vorausgesetzt, es enthält insgesamt 25 Seiten: 2, 3, 5, 5, 7, 8, 9, 10, 25, 24.

#### Mehr als eine Seite pro Blatt konfigurieren

Wählen Sie diese Option, um mehrere Seiten auf einem einzelnen Blatt Papier zu veröffentlichen.  Wählen Sie dann die Anzahl der Zeilen und Spalten aus und veröffentlichen Sie die Seiten wie ein Raster auf einem einzigen Blatt. Beispielsweise können Sie die Seiten als Raster aus 2 Zeilen und 4 Spalten veröffentlichen.

Definieren Sie die Größe des Zielblatts und die Ausrichtung, in der Sie das Blatt veröffentlichen möchten. Sie können auch die Ränder- und Abstandseigenschaften des Blatts angeben.




### Druck

Konfigurieren Sie die Druckproduktionseinstellungen, um Druckermarkierungen zuzuweisen, Farbmodelle auszuwählen und Eigenschaften für den Druck Ihrer PDF-Ausgabe anzugeben.

* **Druckermarkierungen**: Wenn Sie ein Dokument für die Druckproduktion vorbereiten, werden den Seitengrenzen Druckmarkierungen hinzugefügt, um die korrekte Ausrichtung, Beschneidung und Farbauswahl beim Drucken zu unterstützen. Durch Auswahl eines Druckerzeichens wird die Seitenbegrenzung erweitert, um die Markierung aufzunehmen, die beim Drucken abgeschnitten wird. Sie können die folgenden Druckermarkierungen in Ihrer PDF-Ausgabe anzeigen lassen:
   * **Schnittmarkierungen**: Wählen Sie die Option, um an jeder Ecke des Zuschnittbereichs eine Markierung zu platzieren, um anzugeben, wo das Papier nach dem Drucken beschnitten werden soll.
   * **Anschnittmarkierungen**: Wählen Sie diese Option aus, um eine Markierung an jeder Ecke des Anschnittrahmens zu platzieren, um den Schnittbereich für das erweiterte Bild anzugeben.
   * **Registrierungszeichen**: Wählen Sie diese Option aus, um eine Markierung außerhalb des Zuschnittbereichs zu platzieren, um die verschiedenen Trennlinien in einem Farbdokument auszurichten.
   * **Farbbalken**: Wählen Sie diese Option, um einen Farbstreifen außerhalb des Schnittbereichs hinzuzufügen, um die Farbkonsistenz zu wahren und die Farbdichte beim Drucken anzupassen.

  Legen Sie Dimensionen für die ausgewählten Druckermarkierungen mithilfe der Optionen **Linienbreite**, **Linienfarbe** und **Breite des Anschnittrahmens** fest.

* **Medienfeldgröße**: Dies ist die Gesamtseitengröße einschließlich des erweiterten Bereichs, der von Druckermarkierungen belegt wird. Verwenden Sie die Dropdown-Option, um die Seitengröße für Ihre PDF-Ausgabe auszuwählen oder eine eigene benutzerdefinierte Größe zu erstellen.

* **Farbraum**: Sie können zwischen RGB- oder CMYK-Farbräumen wählen, um Ihr PDF-Dokument zu drucken. Wählen Sie RGB aus, um die generierte PDF digital und CMYK für den physischen Druck anzuzeigen. Die im Dokument definierten Farben werden in den ausgewählten Farbraum konvertiert.
  >[!NOTE]
  >
  >Für die Erstellung von PDF/A ist bei Verwendung des CMYK-Farbraums ein ICC-Farbprofil erforderlich.

  <!--For more information on applying these print settings, see *Printing preferences*.-->

### Querverweise {#cross-references}

Verwenden Sie die Registerkarte **Querverweis** , um festzulegen, wie die Querverweise auf der PDF veröffentlicht werden. Sie können die Querverweise für Thementitel, Tabellen, Zahlen und mehr formatieren.

>[!NOTE]
>
> Wenn Sie den Link-Text beim Einfügen des Querverweises definiert haben, hat er Vorrang vor dem in der Vorlage Native PDF definierten Querverweisformat.

Sie können auch Variablen verwenden, um einen Querverweis zu definieren.  Wenn Sie eine Variable verwenden, wird ihr Wert aus den Eigenschaften ausgewählt. Sie können eine einzelne oder eine Kombination von Variablen verwenden, um einen Querverweis zu definieren. Sie können auch eine Kombination aus Zeichenfolge und Variable verwenden.

Sie können beispielsweise `View details on {chapter}` verwenden. Wenn der Kapitelname &quot;Allgemeine Einstellungen&quot;lautet, lautet der Querverweis in der Ausgabe &quot;Siehe Details zu den allgemeinen Einstellungen&quot;.

AEM Guides bietet die folgenden nativen Variablen:

* {title}: Erstellt einen Querverweis zum Titel des Themas. Siehe beispielsweise Nützliche Links auf Seite 2.
* {page} Fügt einen Querverweis zu den Seitenzahlen hinzu. Siehe beispielsweise auf Seite 1.
* {description}: Fügt einen Querverweis zum Text der Beschreibung hinzu. Siehe beispielsweise die Details zu AEM Guides.
* {chapter}: Fügt einen Querverweis zu den Kapitelnummern hinzu. Siehe beispielsweise Kapitel 1.
* {bookmarkText}: Erstellt einen Querverweis auf den mit Lesezeichen versehenen Text. Siehe beispielsweise stop_words auf Seite 5.
* {captionText}: Erstellt einen Querverweis zur Beschriftung der Abbildung oder Tabelle in Ihrem Thema. Siehe zum Beispiel Flugfluss auf Seite 2.
* {figure}: Fügt einen Querverweis zur Zahl hinzu. Wählt die Zahl aus den automatischen Nummernstilen aus, die Sie für die Beschriftung definiert haben.  Sie können beispielsweise &quot;Siehe {figure} auf Seite {page}&quot;verwenden. Der Querverweis in der Ausgabe enthält die automatisch generierte Zahlen- und Seitenzahl &quot;Siehe Abbildung 1 auf Seite 5&quot;.
* {table}: Fügt einen Querverweis zur Tabellennummer hinzu. Wählt die Tabellennummer aus den automatischen Nummernstilen aus, die Sie für die Beschriftung definiert haben. Sie können beispielsweise &quot;Siehe {table} auf Seite {page}&quot;verwenden. Der Querverweis in der Ausgabe enthält die automatisch generierte Tabellennummer und die zugehörige Seitenzahl &quot;Siehe Tabelle 1 auf Seite 5&quot;.



  >[!NOTE]
  >
  >Sie können für Beschriftungs- und Beschriftungs-Tags einen automatischen Nummernstil erstellen.

#### Standard-Querverweisformat

Wenn Sie das Textfeld leer lassen und den Link-Text beim Einfügen eines Querverweises nicht definiert haben, fügt Experience Manager Guides die folgenden Variablen für die entsprechenden Querverweise hinzu:

* **Titel**: `{title}`
* **Beschreibung**: `{description}`
* **Absatz**: `{bookmarkText}`
* **Lesezeichen**: `{bookmarkText}`
* **Abbildung**: `{captionText}`
* **Tabelle**: `{captionText}`

Die Rangfolge für Querverweise lautet:
* Link-Text, der in den Querverweisen hinzugefügt wird
* In der nativen PDF-Vorlage definiertes Querverweisformat
* Standard-Querverweisformat


#### Sprachvariablen in Querverweisen

Sie können auch Sprachvariablen verwenden, um lokalisierte Querverweise zu definieren. Abhängig von Ihrer ausgewählten Sprache wird der lokalisierte Wert automatisch in der PDF-Ausgabe ausgewählt.

Beispielsweise können Sie eine Sprachvariable &quot;reference-label&quot;hinzufügen und die Werte in Englisch und Deutsch definieren.

* Englisch - &quot;Auf Seite anzeigen {page}&quot;
* Deutsch - &quot;finden Sie auf der Seite&quot;{page}


Wenn Sie dem Abschnitt &quot;Absatz&quot;den Wert &quot;`${lng:<variable name>}`&quot;hinzufügen, enthalten die Querverweise in den Absätzen der Ausgabe den lokalisierten Text und die Seitennummer.\
Beispielsweise zeigen die folgenden Screenshots die Querverweise &quot;View on the Page 1&quot; auf Englisch und &quot;View auf der Seite 1&quot; auf Deutsch.

<img src="./assets/english-output-corss-reference.png" alt="Englische Ausgabe eines Querverweises in einer Schreibweise" width ="800" border="2px">

*Ein Querverweis innerhalb eines Absatzes, wenn er in englischer Sprache veröffentlicht wird.*

<img src="./assets/german-output-corss-reference.png" alt="Ausgabe eines Querverweises in einer Schreibweise" width ="800" border="2px">


*Ein Querverweis innerhalb eines Absatzes, wenn er in deutscher Sprache veröffentlicht wird.*

<!--For more information, see *Format cross-references*.-->
