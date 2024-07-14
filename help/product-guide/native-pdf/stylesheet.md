---
title: Native PDF Publish-Funktion | Arbeiten mit allgemeinen Inhaltsstilen
description: Erfahren Sie, wie Sie Stile für Ihren Inhalt erstellen und Stile erstellen.
exl-id: 42ba7347-d81d-45d9-9627-8d164e4f9539
feature: Output Generation
role: Admin
level: Experienced
source-git-commit: f98aa2b4b196ee0fd46542317894163b64b8a486
workflow-type: tm+mt
source-wordcount: '3778'
ht-degree: 1%

---

# Arbeiten mit allgemeinen Inhaltsstilen {#work-with-common-styles}

Ein Stylesheet enthält die Stildefinitionen für die Elemente, die in Ihrer PDF-Ausgabe verwendet werden. Sie können zwischen der Arbeit mit den Beispiel-Stylesheets oder der Erstellung neuer Stylesheets wählen. In den meisten Fällen hilft Ihnen das Erstellen einer Kopie des OOTB-Musterstylesheets beim schnellen Einstieg.

Der Stileditor ist ein WYSIWYG-Editor, der alle Komplexität eines CSS-Codes hinter der Benutzeroberfläche verbirgt. Mithilfe des Stileditors können Sie die Stile für die Elemente Ihrer Wahl einfach und schnell anpassen. Die Stile werden unter den folgenden Überschriften kategorisiert:

* Überschriftenstile
* Absatzformate
* Zeichenformate
* Hyperlink-Stile
* Bildstile
* Listenstile
* Tabellenstile
* Div Styles
* Seitenstile
* Weitere Stile

Beim Arbeiten mit strukturierten DITA-Inhalten ist die Stilzuordnung für die meisten DITA-Elemente im Standard-Stylesheet vorhanden. Wenn Sie mit standardmäßigen DITA-Elementen arbeiten, können Sie deren Erscheinungsbild ändern, indem Sie direkt Änderungen an der Stildefinition vornehmen. Diese Stildefinitionen sind unter der Kategorie &quot;Sonstige Stile&quot;verfügbar. Weitere Informationen finden Sie weiter unten in diesem Thema unter [Arbeiten mit anderen Stilen](#other-styles) .

In den folgenden Abschnitten werden die am häufigsten verwendeten Stileinstellungen in Form von Beispielen beschrieben.

>[!NOTE]
>
>In den folgenden Beispielen wird davon ausgegangen, dass Sie mit dem mit dem Produkt gelieferten Beispiel-Stylesheet arbeiten.

## Arbeiten mit Überschriftenstilen {#heading-styles}

Die Überschriftenstile enthalten alle Basisstile für die Überschriften, die in Ihrem Inhalt verwendet werden. OOTB erhalten Sie 6 grundlegende Überschriftenstile und einen Überschriftenstil für das Thema/Kapitel und die Überschrift des Anhangs. In einem strukturierten Dokument stellt H1 den Titel des Themas oder Kapitels dar und H2 bis H6 wird für Unterthemen oder Abschnitte innerhalb eines Themas/Kapitels verwendet. Diese Hierarchie von Überschriften wird automatisch auf Ihren Inhalt angewendet, sobald die entsprechende Überschrift gefunden wird.

>[!NOTE]
>
>Sie können eigene benutzerdefinierte Überschriftenstile erstellen und diese in Ihren Inhalten mit der Ausgabeklasse verwenden. Weitere Informationen finden Sie unter Schritt 4 im Beispiel [Seitenausrichtung und Anzeigenrotation verwenden](design-page-layout.md#page-orientation-rotation).

### Erstellen benutzerdefinierter Überschriften auf Kapitelebene {#create-chapter-level-heading}

In einem Buch (oder einer Bookmap) arbeiten Sie mit Kapiteln. Die grundlegenden Überschriftenstile werden so gestaltet, dass sie ohne Anpassungen auf Ihre Überschriften auf Kapitelebene angewendet werden. Wenn Sie jedoch spezielle Überschriften für Ihren Inhalt erstellen möchten, müssen Sie diese Überschriften erstellen. Beispielsweise wird die standardmäßige Überschrift `h1.chapter` auf den Titel Ihres Kapitels angewendet. Wenn Ihr Kapiteltitel in einem anderen Stil angezeigt werden soll, müssen Sie den Stil `h1.chapter` anpassen. Auf ähnliche Weise können Sie benutzerdefinierte Stile für Unterüberschriften in Ihrem Kapitel erstellen. Wenn Sie beispielsweise einen benutzerdefinierten Stil für alle Überschriften der Ebenen 2<sup>und 1} und 3<sup>rd</sup> in Ihrem Kapitel erstellen möchten, müssen Sie einen neuen Stil wie `h2.chatper` und `h3.chatper` erstellen.</sup>

Da die Funktion &quot;Native PDF-Veröffentlichung&quot;die grundlegenden Stildefinitionen für die gängigsten Stile enthält, wird der Standardstil auch dann auf den-Inhalt angewendet, wenn Sie versehentlich einen Stil löschen. Wenn beispielsweise in Ihrem Stylesheet keine Stildefinition für den h2-Stil vorhanden ist, wendet die Funktion Native PDF Publishing einen Basisstil auf H2-Inhalt an.

In diesem Beispiel erstellen wir einen Stil für Kapitel der zweiten Ebene:

1. Öffnen Sie das erforderliche Stylesheet zur Bearbeitung.
   >[!NOTE]
   >
   >Informationen zum Öffnen eines Stylesheets zur Anpassung oder Bearbeitung finden Sie unter Abschnitt [Vordefinierten oder neuen Stil anpassen](components-pdf-template.md#customize-style) .

1. Erweitern Sie in der Liste **Stile** die Liste **Überschriftenstile**.
1. Klicken Sie mit der rechten Maustaste auf den Stil **Überschriftenstile** und wählen Sie **Neuer Stil**.
1. Behalten Sie im Dialogfeld *Stil hinzufügen* den Namen **Tag** als `h2` bei und geben Sie `chapter` in das Namensfeld **Klasse** ein.
1. Klicken Sie auf **Fertig**.

Ein neuer Überschriftenstil mit dem Namen `h2.chapter` wird erstellt und unter der Liste &quot;Überschriftstile&quot;hinzugefügt.

Nachdem Sie einen Stil erstellt haben, können Sie die erforderlichen Eigenschaften des Stils mit dem Stileditor anpassen.

### Erstellen von Überschriften für automatische Nummern {#auto-number-heading}

Einer der am häufigsten verwendeten Ausgabeformate sind automatisch nummerierte Überschriften. Diese Überschriften stellen die Kapitelnummer, Themen und Unterthemennummern dar. Die Überschriften mit automatischer Nummer unterscheiden sich von den Listenstilen, bei denen einer Liste von Elementen innerhalb eines Themas automatische Zahlen zugewiesen werden.

In diesem Beispiel passen wir die Überschriften von Ebene 1 zu Ebene 3 an, um die automatischen Zahlen in verschiedenen Formaten zu verwenden.

1. Öffnen Sie das erforderliche Stylesheet zur Bearbeitung.

   >[!NOTE]
   >
   >Informationen zum Öffnen eines Stylesheets zur Anpassung oder Bearbeitung finden Sie unter Abschnitt [Vordefinierten oder neuen Stil anpassen](components-pdf-template.md#customize-style) .

1. Erweitern Sie in der Liste **Stile** die Liste **Überschriftenstile**.

1. Wählen Sie den Stil **h1** aus der Liste aus.
Die Eigenschaften für den h1-Stil werden zusammen mit der Vorschau im Bereich Eigenschaften angezeigt.

   >[!NOTE]
   >
   >Im Vorschaufenster erhalten Sie eine Echtzeitansicht aller Stilaktualisierungen, die Sie auf ein Element anwenden.

1. Wählen Sie die Eigenschaft **Autonumber** aus.

   Die Stile, die Sie auf die Liste der automatischen Nummern anwenden können, werden unter der Eigenschaft &quot;Autonummer&quot;angezeigt.

1. Legen Sie die folgenden Eigenschaften fest:
   * **Stil**: Wählen Sie aus einem breiten Spektrum an gebietsschemaspezifischen oder allgemeinen Nummerierungsstilen aus. Sie können Stile wie Arabisch-Indisch, Devanagari, Georgisch, Dezimal, Unteres Alpha und mehr auswählen. Wählen Sie für das aktuelle Beispiel `upper-alpha` aus.

   * **Format**: Das Standardformat ist auf `<x>` festgelegt, wobei der Wert `x` durch den Nummerierungsstil ersetzt wird, den Sie in der Eigenschaft &quot;Style&quot;ausgewählt haben. Wenn Sie beispielsweise den Stil `decimal` (1) ausgewählt haben, wird der Wert von `x` für jede Instanz des `h1` -Stils automatisch inkrementiert und als 2, 3 usw. verwendet. Sie können dem Feld auch benutzerdefinierten Text hinzufügen, um den Überschriftstil zu formatieren. Wenn Sie beispielsweise möchten, dass alle h1-Überschriften das Präfix `Chapter` aufweisen, müssen Sie dieses Feld auf `Chapter <x>` setzen.

   * **Zeichen einfügen**: Wenn Sie Sonderzeichen im Format hinzufügen möchten, klicken Sie auf &quot;Zeichen einfügen&quot;(<img src="./assets/insert-chars.png" width="25">). Wählen Sie das gewünschte Zeichen aus, das Sie im Stilformat hinzufügen möchten, und klicken Sie auf Einfügen. Es gibt verschiedene Arten von Sonderzeichen, die Sie aus der Dropdownliste Kategorie auswählen auswählen auswählen können. Wählen Sie für unser Beispiel in der Kategorie Interpunktion das Anführungszeichen für doppelte Winkel rechts aus.

     <img src="./assets/insert-special-chars.png" width="400">


   * **Nummerierung beginnen ab**: Wenn die Nummerierung von einer bestimmten Zahl beginnen soll, geben Sie diesen Wert an. Behalten Sie für unser Beispiel den Standardwert 1 bei.

   * **Einzug**: Wenn Sie die Überschrift einrücken möchten, müssen Sie den Einzugswert festlegen. Setzen Sie sie für unser Beispiel auf 0 Pixel.

     >[!NOTE]
     >
     >Sie können den Wert in Einheiten &quot;px&quot;(Pixel), &quot;pt&quot;(Punkte), &quot;rem&quot;, &quot;em&quot;, &quot;%&quot;(Prozent) oder &quot;in&quot;(Zoll) eingeben.

   * **Präfixbreite**: Dies ist der Bereich, der vom Format der automatischen Nummer belegt wird. Er wird automatisch auf eine Größe eingestellt, die das ausgewählte Stilformat einfach aufnehmen kann. Wenn Sie die Größe erhöhen möchten, können Sie den Standardwert ersetzen.

     Versuchen Sie beim manuellen Festlegen dieses Werts, die anderen Eigenschaften zu ändern, die sich auf die Breite auswirken. Ändern Sie beispielsweise die Schriftgröße, das Format mit Präfix (Kapitel) oder ein Suffix (:), legen Sie den Maximalwert in der Eigenschaft *Nummerierung beginnen von* fest und wählen Sie die verschiedenen Schrifteigenschaften aus, um die optimale Größe zu erhalten.

     Behalten Sie für unser Beispiel den Standardwert bei.

   * **Abstand**: Geben Sie den horizontalen und vertikalen Abstand an. Behalten Sie für unser Beispiel die Standardwerte bei.

     Mit den oben genannten Anpassungen wird der Stil wie unten gezeigt angepasst:

     <img src="./assets/h1-style-custmization.png" width="500">

   * **Formatierung anwenden auf**: Die Eigenschaften unter der Kategorie &quot;Autonummer&quot;helfen Ihnen bei der Definition des Nummerierungsstils. Um weitere Anpassungen am Nummerierungsstil oder am Inhalt des Überschriftenformats vorzunehmen, können Sie in diesem Feld Nummerierung oder Absatz auswählen. Wenn Sie &quot;Nummerierung&quot;wählen, werden Änderungen an &quot;Schrift&quot;, &quot;Rand&quot;, &quot;Layout&quot;und anderen Kategorien nur auf den Nummerierungsstil in der Überschrift angewendet. Wenn Sie jedoch &quot;Absatz&quot;auswählen, werden die Änderungen auf den Überschrifteninhalt und nicht auf den Nummerierungsstil angewendet.

   Verwenden Sie die folgenden Einstellungen, um eine Ausgabe zu generieren, die im folgenden Screenshot gezeigt wird:

   | **Überschriftenstil** | **Eigenschaft** | **Wert** | **Zusätzliche Kommentare** |
   | :- | :- | :- | :- |
   | h1 | Stil | Dezimalzahl | Diese Eigenschaften befinden sich unter der Kategorie &quot;Autonummer&quot; |
   |  | Format | `Capter <x>:` |  |
   |  | Präfixbreite | 160 px |  |
   |  | Schrift > Textausrichtung | Linksbündig | Stellen Sie sicher, dass &quot;Formatierung anwenden auf&quot;auf &quot;Nummerierung&quot;eingestellt ist. |
   | h2 | Stil | Dezimalzahl | Diese Eigenschaften befinden sich unter der Kategorie &quot;Autonummer&quot; |
   |  | Format | `Section <x>:` |  |
   |  | Präfixbreite | 125 px |  |
   |  | Schrift > Textausrichtung | Linksbündig | Stellen Sie sicher, dass &quot;Formatierung anwenden auf&quot;auf &quot;Nummerierung&quot;eingestellt ist. |
   | h3 | Stil | Dezimalzahl | Diese Eigenschaften befinden sich unter der Kategorie &quot;Autonummer&quot; |
   |  | Einfügeebene | 2 |  |
   |  | Format | `Section <2>.<x>:` |  |
   |  | Präfixbreite | 125 px |  |
   |  | Schrift > Textausrichtung | Linksbündig | Stellen Sie sicher, dass &quot;Formatierung anwenden auf&quot;auf &quot;Nummerierung&quot;eingestellt ist. |
   |  |

   <img src="./assets/auto-number-output.png" width="500">

## Arbeiten mit Absatzstilen {#paragraph-style}

Es kann ein Absatzstil erstellt werden, um eine spezielle Formatierung auf einen ganzen Absatz anzuwenden. Mit der Pseudo-Klasse können Sie jedoch einen Stil nur auf einen bestimmten Teil des Textes anwenden. Im folgenden Beispiel erstellen wir einen Absatzstil, um den Stil der Dropcap-Komponente zu verwenden.

### Erstellen des Dropcap-Stils {#drop-cap-style}

In Magazinen und literarischen Dokumenten wird ein Tropfendeckel (oder ein fallendes Kapital) verwendet, wobei das erste Zeichen eines Absatzes oder Abschnitts mit einem speziellen Stil versehen ist. Mit der Funktion &quot;Native PDF-Veröffentlichung&quot;können Sie denselben Effekt erzielen.

Im folgenden Beispiel erstellen wir einen Stil für die Dropdownliste:

1. Öffnen Sie das erforderliche Stylesheet zur Bearbeitung.

   >[!NOTE]
   >
   Informationen zum Öffnen eines Stylesheets zur Anpassung oder Bearbeitung finden Sie unter Abschnitt [Vordefinierten oder neuen Stil anpassen](components-pdf-template.md#customize-style) .

1. Erweitern Sie in der Liste **Stile** die Liste **Absatzstile**.

1. Klicken Sie mit der rechten Maustaste auf den **Absatzstil** und wählen Sie **Neuer Stil**.

1. Behalten Sie im Dialogfeld &quot;*Stil hinzufügen*&quot;den Namen &quot;**Tag**&quot;bei und wählen Sie im Feld &quot;**Pseudo** **Klasse**&quot;den Wert &quot;`::first-letter`&quot;.

1. Klicken Sie auf **Fertig**.

   Ein neuer Absatzstil mit dem Namen `::first-letter` wird erstellt und unter der Liste **Absatzstile** hinzugefügt.

1. Wählen Sie &quot;`::first-letter`&quot;unter dem p-Stil und legen Sie die folgenden Eigenschaften fest:

   * **Schriftart**: Legt die gewünschte Schriftart für den ersten Buchstaben in Ihrem Absatz fest. Legen Sie für unser Beispiel die Schriftfamilie auf &quot;Kursiv&quot;, die Schriftgröße auf 500, die Schriftgröße auf 30 pt fest und wählen Sie eine Schriftfarbe.

   * **Layout**: Legt die vertikale Ausrichtung des Texts um den Stil der Ablagefläche fest. Für unser Beispiel setzen wir die vertikale Ausrichtung auf &quot;Unten&quot;.

Da das Tag `p` dem Element `<p>` in DITA zugeordnet ist, müssen Sie diesen Stil nicht explizit mit dem Attribut outputclass hinzufügen. Wo immer in Ihrem Inhalt ein `<p>` -Element verwendet wird, wird automatisch der Stil der Dropcap-Komponente angewendet. Im folgenden Screenshot wurden die Elemente Kapiteltitel, Kurzbeschreibung und Definitionsliste nicht mit dem Stil der Dropcap-Komponente formatiert. Nur der Absatzstil ist mit dem Stil der Dropcap-Komponente formatiert:

<img src="./assets/char-style-drop-cap.png" width="500">

## Arbeiten mit Zeichenstilen {#char-style}

Mithilfe der Zeichenstile können Sie Stile zum Formatieren von Zeichen oder Wörtern in Ihrem Inhalt erstellen. Sie können beispielsweise einen Zeichenstil für Inline-Code oder Dateinamen erstellen oder einen Stil erstellen, der mehrere Formatierungsformate für ausgewählten Inhalt verwendet.

### Erstellen eines Inline-Zeichenstils {#inline-char-style}

Die Formatierung von Inline-Zeichen oder Wörtern in einem Absatz ist ein sehr häufiger Stil. Der Prozess der Erstellung eines Inline-Stils umfasst zwei Aufgaben: Erstellen Sie zunächst einen neuen Stil im Stylesheet und wenden Sie anschließend mithilfe des Attributs `outputclass` den Stil in Ihrem Inhalt an.

Im folgenden Beispiel wird ein Inline-Zeichenstil erstellt:

1. Öffnen Sie das erforderliche Stylesheet zur Bearbeitung.

   >[!NOTE]
   >
   Informationen zum Öffnen eines Stylesheets zur Anpassung oder Bearbeitung finden Sie unter Abschnitt [Vordefinierten oder neuen Stil anpassen](components-pdf-template.md#customize-style) .

1. Erweitern Sie in der Liste **Stile** die Liste **Zeichenstile**.

1. Klicken Sie mit der rechten Maustaste auf den **Zeichenstil** und wählen Sie **Neuer Stil**.

1. Behalten Sie im Dialogfeld &quot;Stil hinzufügen&quot;den Namen **Tag** als &quot;span&quot;bei und geben Sie im Feld **Klasse** den Wert `BoldItalic` ein.

   <img src="./assets/create-char-style.png" width="400">

1. Klicken Sie auf **Fertig**.

   Ein neuer Zeichenstil namens Code wird erstellt und unter der Liste &quot;Zeichenstile&quot;hinzugefügt.

1. Wählen Sie `span.BoldItalic` aus der Liste **Zeichenformat** und legen Sie die folgenden Eigenschaften fest:

   * **Schrift**: Alle Schrifteigenschaften können in diesem Abschnitt angepasst werden. Standardmäßig sind einige Schriftarten im Paket mit dem Produkt enthalten. Sie können die gewünschte Schriftart für den Zeichenstil auswählen. Legen Sie für unser Beispiel die Schriftfamilie auf &quot;*Serif,*&quot;fest und wählen Sie &quot;*Fett*&quot;und &quot;*Kursiv*&quot;in der Eigenschaft &quot;Font Style&quot;. Sie können auch andere Schrifteigenschaften anpassen, z. B. Schriftstärke (fett, heller), Textdekoration (z. B. Unterstreichung, Überstreichung), Schriftgröße, Schriftfarbe, Textausrichtung und mehr.

     >[!NOTE]
     >
     Sie können Ihrer Vorlage auch Schriftarten hinzufügen, die im Bereich Ressourcen Ihrer Vorlage gespeichert sind. Weitere Informationen zum Hinzufügen von Schriftarten und zum Arbeiten mit Ressourcen finden Sie unter [Arbeiten mit Ressourcen](components-pdf-template.md#work-with-resources).

   * **Layout**: Sie können die layoutbezogenen Eigenschaften wie Höhe und Breite, Rand, Abstand, Ausrichtung und mehr festlegen.

   * **Hintergrund**: Mit den Hintergrundeigenschaften können Sie die Hintergrundfarbe eines bestimmten Stils formatieren. Sie können die Hintergrundfarbe oder das Bild für einen beliebigen Stil definieren.

Nachdem Sie den Inline-Zeichenstil erstellt haben, müssen Sie ihn in Ihren Inhalt übernehmen. Um den Inline-Code-Stil anzuwenden, wechseln Sie zur Quellansicht und fügen Sie dem gewünschten Inhalt das Attribut `outputclass` hinzu:

`outputclass="BoldItalic"`

Das folgende Beispiel zeigt das Format &quot;Fett kursiv&quot;, das an verschiedenen Stellen im laufenden Text angewendet wird:

<img src="./assets/char-format-applied.png" width="500">

## Listenstil anpassen {#custom-list-style}

Die Listenstile enthalten die standardmäßigen Stileinstellungen für die sortierten und unsortierten Listen. Sie können diese Listenstile einfach an Ihre Dokumentationsanforderungen anpassen.

Im folgenden Beispiel wird der Stil einer nummerierten oder sortierten Liste angepasst:

1. Öffnen Sie das erforderliche Stylesheet zur Bearbeitung.

   >[!NOTE]
   >
   Informationen zum Öffnen eines Stylesheets zur Anpassung oder Bearbeitung finden Sie unter Abschnitt [Vordefinierten oder neuen Stil anpassen](components-pdf-template.md#customize-style) .

1. Erweitern Sie in der Liste **Stile** die Liste **Listenstile**.

1. Wählen Sie den Stil **ol** aus der Liste aus.

   Die Eigenschaften für den alten Stil werden zusammen mit der Vorschau im Bereich Eigenschaften angezeigt.

   <img src="./assets/list-style-default.png" width="500">

1. Wählen Sie die Option **Erweiterte Formatierung** aus.

   Eine Bestätigungsmeldung wird angezeigt.

1. Klicken Sie in der Meldung *Bestätigung* auf **Ja** , um die Eigenschaften für **Erweiterte Formatierung** zu öffnen.

   Die folgenden Eigenschaften sind standardmäßig verfügbar:

   * **Ebene**: Standardmäßig gibt es 6 Ebenen mit nummerierten Listen. Die Ebene, die Sie in dieser Dropdown-Liste auswählen, steuert die Stiländerungen auf der ausgewählten Ebene und auf allen nachfolgenden Ebenen. Wenn Sie beispielsweise Ebene 4 auswählen, werden alle von Ihnen angewendeten Stiländerungen auf die Ebenen 4, 5 und 6 festgelegt.

   * **Listenstiltyp**: Es gibt eine Reihe von Stilen für die Listennummerierung, aus denen Sie wählen können. Die Liste enthält gebietsschemaspezifische und allgemeine Nummerierungsstile, die zum Erstellen einer nummerierten Liste verwendet werden. Einige der Arten von Listenstilen sind Arabisch, Kambodschanisch, Devanagari, Äthiopisch, Hangul, Hebräisch, Japanisch, Koreanisch, Einfaches Chinesisch, Urdu und mehr.

   Außerdem können Sie mit den folgenden erweiterten Formatierungseigenschaften arbeiten:

   * **Zahlenformat**: Das Standardformat ist auf `<x>` festgelegt, wobei der Wert `x` durch den Nummerierungsstil ersetzt wird, den Sie in der Eigenschaft &quot;List Style Type&quot;ausgewählt haben. Wenn Sie beispielsweise den Stil `decimal` (1) ausgewählt haben, wird der Wert von `x` für jede Instanz des Listenelements automatisch inkrementiert und als 2, 3 usw. verwendet. Sie können dem Feld auch benutzerdefinierten Text hinzufügen, um den Listenstil zu formatieren. Wenn Sie beispielsweise möchten, dass alle Listenstile der ersten Ebene das Suffix &quot;`)`&quot;aufweisen, müssen Sie dieses Feld für den Listenstil der ersten Ebene auf &quot;`<x>)`&quot;setzen.

   * **Zeichen einfügen**: Wenn Sie Sonderzeichen im Zahlenformat hinzufügen möchten, klicken Sie auf &quot;Zeichen einfügen&quot;(<img src="./assets/insert-chars.png" width="25">). Wählen Sie das gewünschte Zeichen aus, das Sie im Stilformat hinzufügen möchten, und klicken Sie auf Einfügen. Es gibt verschiedene Arten von Sonderzeichen, die Sie aus der Dropdownliste Kategorie auswählen auswählen auswählen können.

   * **Ebene einfügen**: Sie können die Zahl aus einer der vorhergehenden Ebenen in Ihr Zahlenformat aufnehmen. Wenn Sie beispielsweise das Zahlenformat von 5. Ebene in das Format der 6. Ebene aufnehmen möchten, wählen Sie 5 in der Dropdown-Liste &quot;Einfügeebene&quot;. Beachten Sie, dass in der Dropdown-Liste &quot;Einfügeebene&quot;die Zahlen nur der vorhergehenden Ebenen und nicht der folgenden Ebene angezeigt werden. Wenn Sie sich beispielsweise auf Ebene 3 befinden, zeigt die Liste &quot;Einfügeebene&quot;nur die Ebenen 1 und 2 an.

     <img src="./assets/list-insert-level.png" width="400">

     Sie können auch das Zahlenformat ändern, um die Listenwerte nach Bedarf anzuzeigen. Wenn Sie beispielsweise einen verschachtelten Nummerierungsstil für Stufe 3 verwenden, können Sie ihn als &quot;`<2>.<x>))`&quot; formatieren. Daraufhin wird die Liste Nr. 2, gefolgt von einem Punkt, gefolgt von der Listennummer 3 und dann zwei Klammern als `2.3))` angezeigt.

   * **Einzug**: Wenn Sie die Liste einrücken möchten, müssen Sie den Einzugswert festlegen. Alle Änderungen im Einzug können im Vorschaufenster überprüft und angepasst werden.

     >[!NOTE]
     >
     Sie können den Wert in Einheiten &quot;px&quot;(Pixel), &quot;pt&quot;(Punkte), &quot;rem&quot;, &quot;em&quot;, &quot;%&quot;(Prozent) oder &quot;in&quot;(Zoll) eingeben.

   * **Präfixbreite**: Dies ist der Bereich, der vom Zahlenformat belegt wird. Er wird automatisch auf eine Größe eingestellt, die das ausgewählte Format einfach aufnehmen kann. Wenn Sie die Größe erhöhen möchten, können Sie den Standardwert ersetzen.

     Versuchen Sie beim manuellen Festlegen dieses Werts, die anderen Eigenschaften zu ändern, die sich auf die Breite auswirken. Ändern Sie beispielsweise die Schriftgröße, das Format mit dem Präfix oder dem Suffix und die verschiedenen Schrifteigenschaften, um die optimale Größe zu erhalten.

   * **Abstand**: Legen Sie den horizontalen Abstand zwischen dem Listennummernformat und dem Inhalt fest. Der vertikale Abstand steuert die Lücke zwischen den beiden Listenelementen.

     Der folgende Screenshot zeigt die angepasste geordnete Liste für jede Ebene:

     <img src="./assets/list-number-format-final.png" width="500">

## Arbeiten mit Tabellenstil {#table-styles}

Mithilfe der Stylesheets können Sie die Anzahl der Tabellenstile *n* entwerfen. Mithilfe der Tabellenstile können Sie entwerfen, wie die gesamte Tabelle, eine bestimmte Zeile oder Spalte dargestellt wird. Mit Steuerung auf Zellenebene können Sie sehr anschauliche Tabellenstile erstellen.

Im folgenden Beispiel sehen wir, wie Sie einen Tabellenstil und die verschiedenen Tabellenstil-Optionen erstellen, die Sie anpassen können:

1. Öffnen Sie das erforderliche Stylesheet zur Bearbeitung.

   >[!NOTE]
   >
   Informationen zum Öffnen eines Stylesheets zur Anpassung oder Bearbeitung finden Sie unter Abschnitt [Vordefinierten oder neuen Stil anpassen](components-pdf-template.md#customize-style) .

1. Klicken Sie in der Liste **Stile** mit der rechten Maustaste auf den **Tabellenstil** und wählen Sie **Neuer Stil**.

1. Behalten Sie im Dialogfeld *Stil hinzufügen* den Namen **Tag** als `table` bei und geben Sie `double-border` in das Namensfeld **Klasse** ein.

1. Klicken Sie auf **Fertig**.

   Ein neuer Tabellenstil mit dem Namen `table.double-border` wird erstellt und unter der Liste &quot;Tabellenstile&quot;hinzugefügt.

1. Wählen Sie `table.double-border` aus der Liste **Tabellenstile** und legen Sie die folgenden Eigenschaften fest:

   * **Formatierung anwenden auf**: Sie können die Stilformatierung auf die gesamte Tabelle, ungerade/gerade Zeilen oder Spalten oder die erste/letzte Zeile oder Spalte anwenden.

     >[!NOTE]
     >
     Die folgenden Einstellungen sind im Abschnitt **Allgemein** verfügbar, wenn **Formatierung anwenden auf** auf **Ganze Tabelle** gesetzt ist.

   * **Textumbruch**: Wählen Sie aus, wie Text um die Tabelle herum umschlossen werden soll. Dies ist nützlich, wenn sich die Tabelle in einem anderen Element auf Blockebene befindet und die Tabelle zusammen mit anderen Inhalten im Block-Element gerendert werden muss. Die Wrapping-Optionen sind *links*, *rechts* oder *none* ausgerichtet.

   * **Ränder reduzieren**: Wählen Sie das Erscheinungsbild des Tabellenrahmens aus. Wenn Sie &quot;Reduzieren&quot;auswählen, wird nur eine einzige Rahmenlinie zwischen den Tabellenzellen gezogen. Für einen separaten Stil ist der Rahmen jedoch um jede Zelle mit zusätzlichem Abstand sichtbar.

     <img src="./assets/table-style-collapse-separate.png" width="500">

   * **Rahmenabstand**: Diese Einstellung ist nur verfügbar, wenn &quot;Rahmenabweichung&quot;auf &quot;Separat&quot;gesetzt ist. Mit dieser Einstellung können Sie den vertikalen und horizontalen Abstand zwischen Zellenrahmen festlegen.

     <img src="./assets/table-border-spacing.png" width="500">

     >[!NOTE]
     >
     Die folgenden Einstellungen sind im Abschnitt **Zelle** verfügbar, wenn **Formatierung anwenden auf** auf **Ganze Tabelle** gesetzt ist.

   * **Abstand**: Geben Sie den Abstand zwischen den Tabellenzellen an. Sie können für die oberen, unteren, linken und rechten Seiten unterschiedliche Füllzeichenwerte festlegen.

   * **Vertikale Ausrichtung**: Geben Sie die vertikale Ausrichtung für den Zelleninhalt an. Die verfügbaren Optionen sind: oben, Mitte und unten.

   * **Rahmenseitig, Stil, Farbe, Breite, Radius:** Geben Sie die grenzbezogenen Eigenschaften an. Sie können festlegen, dass nur Rahmen auf bestimmten Seiten wie links oder rechts angezeigt werden. Im Rahmenstil werden die verfügbaren Randstile wie &quot;Durchgehend&quot;, &quot;Gestrichelt&quot;, &quot;Doppelt&quot;und mehr aufgeführt. Geben Sie die Rahmenfarbe über die Farbpalette an. Sie können die Rahmenbreite in Px, pt, rem, em, % und in Einheiten angeben. Der Radius definiert die Kurve, um kreisförmige Ecken zu bilden.

   Die anderen Eigenschaften unter &quot;Schriftart&quot;, &quot;Rand&quot;, &quot;Layout&quot;, &quot;Paginierung&quot;und &quot;Hintergrund&quot;werden unter anderen Beispielen in diesem Thema erläutert. Abhängig von Ihrer Auswahl in der Eigenschaft **Formatierung anwenden auf** können Sie diese Werte auf die gesamte Tabelle oder auf ausgewählte Zeilen oder Spalten anwenden.

   Nachfolgend finden Sie eine Vorschau einer Beispieltabelle mit verschiedenen Zeilen, die anders formatiert sind:

   <img src="./assets/table-final-design.png" width="500">

## Arbeiten mit anderen Stilen {#other-styles}

Wenn Sie mit strukturiertem (DITA-)Inhalt arbeiten, werden Sie feststellen, dass fast alle DITA-Elemente im Standard-Stylesheet über ein Stilmapping verfügen. Beispielsweise wird der Stil eines Elements `<shortdesc>` unter der Stildefinition **Sonstige Stile** > **.shortdesc** definiert. Sie können diese Stile einfach anpassen und sie werden automatisch in der PDF-Ausgabe angewendet, die aus Ihrem strukturierten Inhalt generiert wird. Das bedeutet, dass Sie im Gegensatz zu anderen benutzerdefinierten Stilen für diese Stile kein `outputclass` -Attribut für den Inhalt hinzufügen müssen.

Wenn Sie eine Stildefinition für ein Element erstellen möchten, das nicht standardmäßig verfügbar ist, oder wenn Sie ein benutzerdefiniertes Element haben, können Sie es einfach im Stylesheet erstellen. Der einzige Punkt, den Sie beachten müssen, ist die Erstellung des Stils mit demselben Namen wie der des strukturierten Elements.

Im folgenden Beispiel wird der Titel eines neuen Fensters (`wintitle`) erstellt:

1. Öffnen Sie das erforderliche Stylesheet zur Bearbeitung.

   >[!NOTE]
   >
   Informationen zum Öffnen eines Stylesheets zur Anpassung oder Bearbeitung finden Sie unter Abschnitt [Vordefinierten oder neuen Stil anpassen](components-pdf-template.md#customize-style) .

1. Erweitern Sie in der Liste **Stile** den Eintrag **Sonstige Stile**.

1. Klicken Sie mit der rechten Maustaste auf **Sonstige Stile** und wählen Sie **Neuer Stil**.

1. Behalten Sie im Dialogfeld *Stil hinzufügen* den Namen **Tag** als *leer* und geben Sie `wintitle` in das Namensfeld **Klasse** ein.

   Da `wintitle` ein erkannter DITA-Elementname ist, wird seine Stildefinition automatisch dem Element `<wintitle>` in Ihrer Quelle zugeordnet.

1. Klicken Sie auf **Fertig**.

   Ein neuer Stil mit dem Namen `.wintitle` wird erstellt und unter der Liste **Sonstige Stile** hinzugefügt.

1. Wählen Sie &quot;.wintitle&quot;aus der Liste **Sonstige Stile**&quot;und legen Sie die Eigenschaften nach Bedarf fest.

Der folgende Screenshot zeigt den wintitle-Stil, der auf den Text &quot;Primäre Kontrolle&quot;angewendet wird.

<img src="./assets/other-style-wintitle.png" width="500">


## Eindeutigen Stil für ein Einzelseitenlayout definieren

Beim Veröffentlichen der nativen PDF-Ausgabe werden alle Stile in der endgültigen PDF zusammengeführt. Es ist wichtig, jeder Vorlage in der CSS einen eindeutigen Stil zuzuweisen.
Verwenden Sie unterschiedliche CSS-Stilnamen, um bestimmte Schriftarten und Stile auf verschiedene Bereiche einer PDF anzuwenden. Sie können beispielsweise die gewünschte Schriftart für die Titelseite mithilfe des folgenden CSS definieren.

```css
...
[data-page-layout="Front"] * { 
    font-size: 18pt; 
}  
...
```


Der Rest des Dokuments verwendet die Standardschrift, die Sie für das Body-Tag in `content.css` oder `layout.css` angegeben haben. Dadurch wird sichergestellt, dass Stile nicht zusammengeführt werden und jeder Abschnitt sein beabsichtigtes Design behält. Wenn Sie unterschiedliche Schriftgrößen wünschen, erstellen Sie spezifische Stile für sie.

Sie können beispielsweise die folgenden Stile definieren, um die Schriftgröße 18 für die Titelseitenabsätze und die Schriftgröße 11 pt für die Titelseite zu definieren:

```css
[data-page-layout="Front"] p { //For all paragraphs inside Front page
  font-size: 18pt; 
} 
  
[data-page-layout="Back"] p { //For all paragraphs inside Back page
  font-size: 11pt; 
}
```

>[!NOTE]
>
Im vorherigen Beispiel sind &quot;Vorder&quot;und &quot;Zurück&quot;die Beispielnamen der Layout-Dateien, die Sie in den Vorlagen verwenden können.


## Definieren eines benutzerdefinierten CSS-Stils für Präfix- und Suffix-Inhalte

Wenn Sie die benutzerdefinierten CSS-Stile definieren, erhalten diese beim Generieren der nativen PDF-Ausgabe die erste Priorität.
Der folgende standardmäßige CSS-Stil blendet sowohl Präfix- als auch Suffix-Inhalt aus.

```css
...
.prefix-content, .suffix-content{
    display: none;
} 
...
```

Um diese Präfixe im Element `<note>` zuzulassen, fügen Sie die folgende CSS in Ihre `content.css` ein:

```css
...
.prefix-content{
    display: inline !important;
}
...
```

Das Element `<note>` generiert ein zusätzliches `<span>` mit dem Klassenpräfix-content, das seinem Typattribut entspricht. Diese CSS-Regel zielt auf die `.prefix-content` -Klasse innerhalb von `<note>` -Elementen mit einem type -Attribut ab, sodass Sie den Präfixinhalt nach Bedarf gestalten oder bearbeiten können.

