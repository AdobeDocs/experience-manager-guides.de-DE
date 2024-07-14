---
title: Anhang
description: Erfahren Sie, wie Sie InDesign-Dateien für die Konvertierung vorbereiten.
exl-id: 02da0e61-7a73-4c4c-9bd7-2664d90fa728
feature: InDesign File Conversion
role: Admin
level: Experienced
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '2851'
ht-degree: 0%

---

# Anhang {#id195AD0L60Y4}

## Vorbereiten von InDesign-Dateien für die Konvertierung {#id195DBF0045Z}

InDesign bietet Autoren eine Vielzahl von Funktionen zur Erstellung attraktiver und komplexer Dokumente. Häufig bedeutet dies, dass die verschiedenen Teile eines Dokuments visuell auf der Seite platziert werden, ohne dass versucht wird, einen Fluss zwischen diesen Textrahmen bereitzustellen. Wenn die &#39;*Leserichtung*&#39; der Textrahmen nicht definiert ist, enthält die IDML-Datei Meldungen, die möglicherweise keiner aussagekräftigen Reihenfolge folgen. Das Endergebnis ist ein oder mehrere DITA-Themen mit Absätzen, Tabellen und Grafiken in zufälliger Reihenfolge.

Es ist zwar möglich, den DITA-Inhalt in einer vernünftigen Reihenfolge in einem DITA-Editor zu bearbeiten, es ist jedoch viel einfacher, die InDesign-Datei zu reparieren, bevor die IDML-Datei erstellt wird. Dies kann ohne Änderung des Erscheinungsbilds des Quelldokuments erfolgen. Sie hat auch den Vorteil, dass das Quelldokument durch die ordnungsgemäße Definition der Leserichtung zugänglich gemacht wird.

***Verschlüsseln von Textrahmen***

InDesign verwendet den Begriff *&#39;threading&#39;*, um einen Frame mit einem anderen zu verknüpfen. Weitere Informationen zum Threading von Textrahmen finden Sie unter Thema *[Threading-Text](https://helpx.adobe.com/in/indesign/using/threading-text.html)* in der InDesign-Dokumentation.

***Überschneidende Frames***

Einige InDesign-Dokumente verwenden aus Layoutgründen überlappende Rahmen ohne Thread. Es kann sehr schwierig sein, diesen Inhalt in den Haupt-Thread zusammenzuführen. Die beste Option kann sein, das Ergebnis in der DITA-Umgebung zu bearbeiten.

***InDesign stories***

Jeder mit einem Thread versehene Inhaltsfluss in einem InDesign-Dokument ist ein so genannter &quot;*story*&quot;. Um optimale Ergebnisse zu erzielen, wird empfohlen, die Anzahl der Meldungen zu begrenzen. Es gibt jedoch einige Teile Ihres Dokuments, die in der DITA-Ausgabe möglicherweise nicht benötigt werden. Seitenfußzeilen sind beispielsweise selten erforderlich, können jedoch in der Mitte eines Themas angezeigt werden, wenn sie nicht mit Vorsicht behandelt werden.

Die einfachste Möglichkeit, Text auszuschließen, der im Dokument nicht erforderlich ist, besteht darin, ihm ein spezielles *Absatz-Tag* zu geben, das nur für unerwünschte Inhalte verwendet wird. Anstatt beispielsweise einen &quot;*\[einfachen Absatz\]*&quot;für die Fußzeile wiederzuverwenden, erstellen Sie ein dediziertes &quot;*Fußzeile*&quot;-Tag. Legen Sie dann in der MapStyle-Datei einfach die *Footer*-Absätze fest, die wie folgt abgelegt werden sollen:

```XML
<paraRule style="Footer" local="0" refactor="drop">
   <attributeRules createID="false"/>
</paraRule>
```

***Mapping zu DITA-Doctypes***

Es ist wichtig, dass Ihr Quelldokument über mindestens einen Absatzstil oder ein Element verfügt, das bzw. das den Anfang eines Themas markieren kann. In Dokumenten wird üblicherweise *Überschrift1* als Name der Überschriften der obersten Ebene im Dokument verwendet. Anschließend können Sie eine Zuordnung von diesem Stil zu einem bestimmten DITA-Doctype erstellen. Wenn Ihr Dokument gut organisiert ist und die Verwendung von *Überschrift1* durchgängig konstant ist, erhalten Sie gute Ergebnisse.

***Mehrere DITA-Doctypes***

Wenn einige der Absätze *Überschrift1* in verschiedene DITA-Doctypes konvertiert werden müssen, duplizieren Sie den Absatzstil im InDesign. Geben Sie diesen Stilen einen leicht zu erkennenden Namen, z. B. *Überschrift1\_genTask* oder *Überschrift1\_Fehlerbehebung*. Richten Sie dann die Datei &quot;mapStyle&quot;wie unten gezeigt ein:

```XML
<doctypes>
   <doctypeParaRule style="Heading1" local="0" mapToDoctype="concept">
      <attributeRules createID="true"/>
   </doctypeParaRule>
   <doctypeParaRule style="Heading1_genTask" local="0" mapToDoctype=" generalTask">
      <attributeRules createID="true"/>
   </doctypeParaRule>
   <doctypeParaRule style="Heading1_troubleshooting" local="0"mapToDoctype=" troubleshooting">
      <attributeRules createID="true"/>
   </doctypeParaRule>
</doctypes>
```

***Strukturierte InDesign-Dokumente***

InDesign hat eine lockere Beziehung zu XML. Während ein Dokument eine XML-DTD enthalten kann und die Hauptgeschichte möglicherweise für diese DTD gültig ist, ist es auch möglich, hybride Dokumente zu erstellen, in denen ein Teil des Inhalts XML ist, aber keine DTD enthalten ist. Dies sind die unerwünschten Fälle für eine erfolgreiche Konvertierung in DITA. Wenn ein Dokument XML-Teile enthält, versuchen Sie, die Ausgabe in XML zu speichern und zu prüfen, ob die Ergebnisse akzeptabel sind. Andernfalls enthalten DITA-Inhalte auch ungültige Inhalte oder können vollständig fehlschlagen.

***Tabellenformatierung***

Die Konvertierung von InDesign-Tabellenformatierungsregeln in die entsprechende Tabellenformatierung in DITA ist ein komplexer Vorgang. Dies liegt an den umfangreichen Formatierungsfunktionen, die in den Quelldateien verfügbar sind, verglichen mit den grundlegenden Optionen, die vom Oasis \(CALS\)-Tabellenmodell bereitgestellt werden, das in DITA verwendet wird. Eine vertikale und horizontale Textausrichtung wird bereitgestellt und liefert ähnliche Ergebnisse, obwohl Rechtetext immer entsprechend der Textrichtung ausgerichtet ist, während InDesign die Option Linker Rechtshinweis und Rechtshinweis erlaubt.

Die Handhabung von Spalten- und Zeilentrennzeichen durch InDesign ist wiederum wesentlich leistungsfähiger als die grundlegenden Optionen des Oasis-Tabellenmodells. InDesign bietet vier Zellenrahmen: Rahmentyp \(solide oder Muster\), Rahmenstärke, Rahmenfarbe, Rahmenfarbe, Rahmentint, Rahmenlückenfarbe und Rahmenlückentint. Alle diese Elemente müssen den Rahmen rechts und unten in jeder Zelle (Einstiegselement\) zugeordnet werden, wobei die einzigen Optionen 0 oder 1 sind - Rahmen ausblenden oder Rahmen anzeigen.

Die Rahmenregelung in InDesign kann auf folgenden Ebenen angewendet werden:

- Tabellenstile
- Zellstile
- Lokale Überschreibungen für jede Zelle

Der InDesign zu DITA-Konvertierungsprozess wendet die Rahmenregel wie folgt an:

- Tabellenstile werden für vertikale Regeln dem Attribut `colspec/@colsep` zugeordnet. Horizontale Regeln werden dem Attribut `row/@rowsep` zugeordnet. Wenn der Rahmen nicht definiert ist, wird das Attribut in beiden Fällen nicht erstellt.
- Zellstile werden den Attributen `entry/@colsep` und `entry/@rowsep` zugeordnet. Diese Werte überschreiben alle von Tabellenformat abgeleiteten Begrenzungslinien.
- Lokale Überschreibungen wenden die Formatierung direkt auf die Zelle an und überschreiben Tabellenstile und Zellstile.

***Wechselnde Muster***

InDesign Tabellenstile ermöglichen es, dass Spalten- und Zellenausrichtung einem abwechselnden Muster folgen. Diese Funktion wird zwar für die Konvertierung unterstützt, die Ergebnisse sind jedoch nur dann offensichtlich, wenn eine Mustergruppe zugeordnet ist, um die Regel \(1\) anzuzeigen, und die andere Mustergruppe zugeordnet wird, um die Regel \(0\) auszublenden.

## Bereiten Sie die Zuordnungsdatei für die InDesign zu DITA-Migration vor. {#id194AF0003HT}

Für die korrekte DITA-Konvertierung ist eine Zuordnungsdatei erforderlich, die mit dem Inhalt des Quelldokuments übereinstimmt. Bei unstrukturierten InDesign-Dokumenten bedeutet dies, dass alle verfügbaren Absatzstile und Zeichenstile zugeordnet werden müssen. Bei XML-strukturierten InDesign-Dokumenten müssen alle Elemente in der zugehörigen DTD zugeordnet werden.

Die Zuordnungsdateien für unstrukturierte und strukturierte InDesign-Dokumente unterscheiden sich. Dies liegt an den komplexeren Verarbeitungsanforderungen für die Konvertierung von unstrukturierten Quellinhalten in DITA.

Nachfolgend finden Sie ein Beispiel für die Zuordnungsdatei:

```XML
<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE styleMap SYSTEM "mapStyle.dtd">
<styleMap xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:noNamespaceSchemaLocation="mapStyle.xsd" >
   <doctypes>
      <mapDoctypeParaRule root="itpx:stories" mapToDoctype="map">
         <attributeRules createID="true">
            <addNew name="outputclass" value="map"/>
         </attributeRules>
      </mapDoctypeParaRule>
      <doctypeParaRule style="Heading 1" local="0" mapToDoctype="concept">
         <attributeRules createID="true"/>
      </doctypeParaRule>
      <doctypeParaRule style="Heading A" local="0" mapToDoctype="topic">
         <attributeRules createID="true"/>
      </doctypeParaRule>
   </doctypes>
   <wrappingRules>
      <wrap elements="li+" context="number" wrapper="ol">
         <attributeRules createID="true"/>
      </wrap>
      <wrap elements="li+" context="bullet" wrapper="ul">
         <attributeRules createID="true"/>
      </wrap>
   </wrappingRules>
   <paragraphStyleRules>
      <paraRule style="Heading 2" local="0"  mapTo="p">
         <attributeRules createID="true"/>
      </paraRule>
      <paraRule style="Heading 3" local="0"  mapTo="p">
         <attributeRules createID="true"/>
      </paraRule>
      <paraRule style="List Paragraph" local="p[-|-|-|-|-|b|-|-]" context="bullet" mapTo="li">
         <attributeRules createID="true"/>
      </paraRule>
      <paraRule style="List Paragraph" local="p[-|-|-|-|-|n|-|-]" context="number" mapTo="li">
         <attributeRules createID="true"/>
      </paraRule>
      <paraRule style="List Paragraph" local="0" context="bullet" mapTo="li">
         <attributeRules createID="true"/>
      </paraRule>
      <paraRule style="Normal" local="0"  mapTo="p">
         <attributeRules createID="true"/>
      </paraRule>
      <paraRule style="Normal" local="p[-|-|-|-|-|b|-|-]" context="bullet" mapTo="li">
         <attributeRules createID="true"/>
      </paraRule>
      <paraRule style="Title" local="0"  mapTo="p">
         <attributeRules createID="true"/>
      </paraRule>
   </paragraphStyleRules>
   <characterStyleRules>
      <charRule style="Bold" local="0" mapTo="b">
         <attributeRules createID="false"/>
      </charRule>
      <charRule style="Code" local="0" mapTo="codeph">
         <attributeRules createID="false"/>
      </charRule>
      <charRule style="[No character style]" local="c[Bold|-|-|-|-|-|-|-]" mapTo="b">
         <attributeRules createID="false"/>
      </charRule>
      <charRule style="[No character style]" local="c[Italic|-|-|-|-|-|-|-]" mapTo="i">
         <attributeRules createID="false"/>
      </charRule>
   </characterStyleRules>
</styleMap>
```

Die Zuordnungsdatei ist eine XML-Datei mit einer einfachen Struktur, die alle Quellabsatzstile und Zeichenstilcodes auflistet. Der Dateiinhalt wird nachfolgend erläutert:

**Stilzuordnung**

Im Element `styleMap` können Sie zwei optionale Attribute festlegen - `@map_date` und `@map_version` für die Aufzeichnung der Version der Zuordnungsdatei.

**Dokumenttyp**

Das Element `doctypes` listet die unterstützten DITA-Mappings und Themenzuordnungen auf.

**Absatzregeln für Dokumenttyp zuordnen**

Das Element `mapDoctypeParaRule` ist obligatorisch. Die Attribute dieses Elements dürfen nicht bearbeitet werden, da das Stammelement der Quell-XML immer dem Stamm-Element `map` der DITA-Map zugeordnet ist.

**Absatzregel für Dokumenttyp**

Das Element `doctypeParaRule` ist obligatorisch. Dadurch kann der Konvertierungsprozess den Beginn eines neuen Themas identifizieren. Normalerweise wird das Attribut `@style` allein verwendet, wobei das Attribut `@local` auf 0 gesetzt ist. Wenn jedoch immer lokale Formatierungsüberschreibungen für den ausgewählten Stil vorhanden sind, müssen Sie eine Regel für jeden Stil und dessen lokale Überschreibungen hinzufügen. Dies ist in der generierten Mapping-Datei einfach zu erkennen, wo dies oder Ähnliches gefunden werden könnte:

```XML
<paraRule style="Heading 1" local="0" mapTo="p">
   <attributeRules createID="true"/>
</paraRule>
<paraRule style="Heading 1" local="p[Italic|-|-|-|-|-|-|-]" mapTo="p">
   <attributeRules createID="true"/>
</paraRule>
```

Im obigen Beispiel gibt es zwei `paraRule` -Elemente für `@style` = &quot;Überschrift1&quot;. Erstellen Sie einfach ein äquivalentes `doctypeParaRule` -Element, wobei das `@mapToDoctype` -Attribut nach Bedarf festgelegt ist.

Die in `doctypeParaRule` verwendeten Attribute werden nachfolgend erläutert:

- `@style`: Der Name eines Stils im InDesign-Quelldokument.
- `@local`: Siehe [\#id194CG0V005Z](#id194CG0V005Z).
- `@mapToDoctype`: Der Name eines DITA-Thementyps aus einer Aufzählungsliste aller gültigen `doctypes`.

**Umbruchregeln für Elemente**

Die Elementumbruchregeln definieren die Möglichkeiten, Elemente im eingehenden Dokument gemäß einem Satz von Attributwerten in ein vordefiniertes Element einzuschließen oder zu verschieben.

***`wrap`element***

Dies ist ein optionales Element. Das Element `wrap` listet die Elemente auf, die umschlossen oder verschoben werden. Umbruch wird normalerweise verwendet, wenn einer Reihe von Elementen ein gemeinsames übergeordnetes Element zugewiesen werden muss. Beispielsweise mehrere `li` -Elemente, die in ein `ol` -Element eingeschlossen sind. Außerdem kann `wrap` zum Verschieben von Elementen wie Titeln für Zahlen und Tabellen verwendet werden.

Die in `wrap` verwendeten Attribute werden nachfolgend erläutert:

- `@element`: Ein Pluszeichen nach einem Elementnamen zeigt, dass alle benachbarten Elemente mit demselben Namen in das Element mit dem Namen im Attribut `@wrapper` eingeschlossen werden.
- `@wrapper`: Der Name des einschließenden Elements.
- `@context`: Bietet eine Möglichkeit, die Art und Weise, wie ein bestimmtes Element umschlossen wird, weiter zu verfeinern. Das folgende Beispiel zeigt eine Möglichkeit, eine Reihe von `li` -Elementen entweder in einer geordneten Liste `ol` oder in einer ungeordneten Liste `ul` gemäß dem Wert `@context` zuzuordnen \(der Kontext wird für das Element `paraRule` definiert\):

  ```XML
  <wrap elements="li+" context="number" wrapper="ol">
     <attributeRules createID="true"/>
  </wrap>
  <wrap elements="li+" context="bullet" wrapper="ul">
     <attributeRules createID="true"/>
  </wrap>
  ```


Das folgende Beispiel zeigt, wie ein `fig` -Element aus einem `title` - und einem `image` -Element erstellt wird:

- `@elements`: Die Elemente, die aufgelistet und durch ein Komma getrennt sind, werden in das Element mit dem Namen im Attribut `@wrapper` eingeschlossen. Aufgrund der gängigen Praxis, Bildtitel unter das Bild zu setzen, ist der Titel das Element `title` unmittelbar nach dem Element `image`.

  Die folgende Umbruchregel:

  ```XML
  <wrap elements="title, image" context="FigTitle" wrapper="fig">
     <attributeRules createID="true"/>
  </wrap>
  ```

  Konvertiert die folgende XML-Zwischendatei:

  ```XML
  <image href="Links/myImage.png" scale="59">
     <title>IDML2DITA workflow</title>
  ```

  In die folgende gültige DITA-Zielleistenstruktur:

  ```XML
  <fig id="id397504">
     <title>IDML2DITA workflow</title>
     <image href="Links/myImage.png" scale="59">
  </fig>
  ```

- `@wrapper`: Der Name des einschließenden Elements.
- `@context`: Bietet eine Möglichkeit, weiter einzugrenzen, wie ein bestimmtes Element umschlossen wird \(der Kontext ist für das Element `paraRule` definiert\).

Das folgende Beispiel zeigt, wie Sie einen `title` in einen `table` verschieben:

- `@elements`: Das Element `title`, das sich unmittelbar vor oder unmittelbar nach einer `table` befindet, wird in das Element mit dem Namen im Attribut `@wrapper` eingeschlossen. Ein XPath-Prädikat kann die Position des Titelelements als `[before]` oder `[after]` identifizieren.

  Beispiel: Die folgende Umbruchregel:

  ```XML
  <wrap elements="title[before]" context="TableTitle" wrapper="table">
     <attributeRules createID="true"/>
  </wrap>
  ```

  Konvertiert die folgende XML-Zwischendatei:

  ```XML
  <title>IDML2DITA workflow</title>
  <table id="id289742" outputclass="BasicTable">
     <tgroup cols="2">
        <colspec colname="0" colwidth="0.7*">
           <colspec colname="1" colwidth="0.3*">
  ```

  In diese gültige DITA-Ziffernstruktur:

  ```XML
  <table id="id289742" outputclass="BasicTable">
     <title>IDML2DITA workflow</title>
     <tgroup cols="2">
        <colspec colname="0" colwidth="0.7*">
           <colspec colname="1" colwidth="0.3*">
  ```

- `@wrapper`: Der Name des einschließenden Elements.

- `@context`: Bietet eine Möglichkeit, weiter einzugrenzen, wie ein bestimmtes Element umschlossen wird \(der Kontext ist für das Element `paraRule` definiert\).


**Absatzstilregeln**

Die `<paragraphStyleRule>` -Elemente werden im Folgenden beschrieben:

***`paraRule`element***

Das Element `paraRule` ist obligatorisch. Dadurch werden die Zuordnungsregeln für alle Absatzstile festgelegt. In einem InDesign-Dokument ist der gesamte Text in der Unterstruktur von Absatzstilen enthalten, selbst Absätze ohne Stil haben den Namen `[No paragraph style]`. Die eckigen Klammern geben einen eingebauten InDesign-Stilnamen an.

>[!NOTE]
>
> Die eckigen Klammern geben einen integrierten InDesign-Stilnamen an.

Die in `paraRule` verwendeten Attribute werden nachfolgend erläutert:

- `@style`: Der Name eines Stils im InDesign-Quelldokument.
- `@local`: Siehe [\#id194CG0V005Z](#id194CG0V005Z).
- `@mapTo`: Der Name eines DITA-Zielelements.

- `@context`: Dieses Attribut wird verwendet, um eine Verknüpfung zu einer bestimmten **wrap** -Regel herzustellen, wenn mehr als eine Wrapper-Auswahl verfügbar ist. Beispiel: Das Element `li` kann entweder in ein Element `ol` oder in ein Element `ul` eingeschlossen sein. Um die verschiedenen Listentypen zu identifizieren, können Sie einen bestimmten Stilnamen oder das Attribut `@local` verwenden, das Folgendes anzeigen kann:
   - `local="p[-|-|-|-|-|b|-|-]"` Wobei &quot;`b`&quot; in Feld 6 ein Listenelement mit Aufzählungszeichen angibt. Setzen Sie in diesem Fall `@context` auf &#39;`bullet`&#39;.
   - `local="p[-|-|-|-|-|n|-|-]"` Wobei &quot;`n`&quot; in Feld 6 ein nummeriertes Listenelement angibt. Setzen Sie in diesem Fall `@context` auf &#39;`number`&#39;.

- `@commentOut`: Dieses Attribut ermöglicht das Umbrechen des Zielelements in XML-Kommentare, sodass die Informationen nicht verloren gehen, sondern vom Benutzer manuell verarbeitet werden können. Dies ist nützlich, wenn der Quellinhalt nicht gezwungen werden kann, die DITA-Strukturregeln einzuhalten.

- `@refactor`: Dieses optionale Attribut hat zwei Werte:

- `unwrap`: Das übereinstimmende Element wird entfernt, während der Inhalt beibehalten wird.

- `drop`: Das übereinstimmende Element und alle zugehörigen Inhalte werden entfernt.


**Zeichenstilregeln**

Die `charRule` -Elemente werden im Folgenden beschrieben:

>[!NOTE]
>
> Es gibt keine Zuordnung für den integrierten Zeichenstil `[No character style]` bei `local="0"`, da sie während der Vorverarbeitung entfernt werden.

***`charRule`element***

Dies ist ein optionales Element.

Dies sind die Zuordnungsregeln für alle Zeichenstile. In einem InDesign-Dokument ist der gesamte Text in untergeordneten Elementen von Zeichenstilen enthalten.

Die in `charRule` verwendeten Attribute werden nachfolgend erläutert:

- `@style`: Der Name eines Stils im InDesign-Quelldokument.
- `@local`: Siehe [\#id194CG0V005Z](#id194CG0V005Z).
- `@mapTo`: Der Name eines DITA-Zielelements.
- `@refactor`: Dieses optionale Attribut hat zwei Werte:
   - `unwrap`: Das übereinstimmende Element wird entfernt, während der Inhalt beibehalten wird.

   - `drop`: Das übereinstimmende Element und alle zugehörigen Inhalte werden entfernt.


**Attributregeln**

Dieses Element kann ein untergeordnetes Element der folgenden Elementkontexte sein:

- `mapDoctypeParaRule`
- `mapDoctypeElemRule`
- `doctypeParaRule`
- `doctypeElemRule`
- `paraRule`
- `charRule`
- `elementRule`

Attributregeln dienen dazu, die Attribute für die übereinstimmenden Elemente zu verwalten.

Je nach Kontext sind die folgenden Attribute für das Element `attributeRules` verfügbar:

- `@createID`: Generiert eine eindeutige ID für die entsprechenden Elemente. Zulässige Werte `true` oder `false`. In allen Kontexten verfügbar.
- `@copyAll`: Kopiert alle Attribute nur aus dem XML-Quellinhalt für strukturierte Quelldateien. Zulässige Werte sind `true` oder `false`. Verfügbar für die Kontexte `mapDoctypeParaRule`, `mapDoctypeElemRule`, `doctypeElemRule` und `elementRule`.


Die in `attributeRules` verwendeten Attribute werden nachfolgend erläutert:

>[!NOTE]
>
> Dieses Element kann mehrere untergeordnete Elemente enthalten.

- `addNew`: Fügt dem übereinstimmenden Element ein neues Attribut hinzu. Verfügbar für alle Kontexte. Es hat zwei Attribute:
   - `@name`: Muss ein offizieller XML-Name sein, vorzugsweise gültig für den DITA-Kontext.
   - `@value`: Kann Literaltext oder ein einfacher XPath-Ausdruck sein.
- `copyAtt`: Kopiert ein einzelnes Attribut in das Ziel, während es optional im Prozess umbenannt wird. Der Wert wird nicht geändert. Verfügbar für die Kontexte `mapDoctypeParaRule`, `mapDoctypeElemRule`, `doctypeElemRule` und `elementRule`. Wenn dieses Element vorhanden ist, wird der Wert `@copyAllAtts` als `false` angenommen. Es hat zwei Attribute:
   - `@name`: Muss der Name eines Attributs sein, das im XML-Quellelement vorhanden ist.
   - `@mapTo`: Muss ein offizieller XML-Name sein, vorzugsweise gültig für den DITA-Kontext.

**Lokale Formatierungscodes**

In jedem InDesign-Dokument ist es möglich, dass Absatzstile und Zeichenstile mehrere Hundert verschiedene Formatierungsüberschreibungen enthalten. Die meisten dieser Eigenschaften bieten keine nützliche Rolle im Konvertierungsprozess. Wir haben jedoch eine Reihe von Formatierungsfunktionen ermittelt, die sich auf die Semantik des Dokuments auswirken und den Konvertierungsprozess beeinflussen müssen.

Die Attribute `@local` werden als spezielles, durch Trennzeichen getrenntes Format angezeigt, in dem acht Felder zusammen mit einem Präfix bereitgestellt werden, um die Art der Formatierung zu überschreiben. Die Felder für Formatierungscodes sind unten aufgeführt:

- Präfix **p** für die lokale Überschreibung im para-Stil oder **c** für die lokale Überschreibung des Zeichenstils.
- **Schriftstil**: Familienname und Eigenschaften wie &quot;***Fett Zusammengefasst Kursiv***&quot;.
- **Schriftgröße** in Punkten.
- **Zeichenposition** für Hochgestellt oder Tiefgestellt.
- **Unter** für den Unterstrich.
- **Strike** für Durchstreichen.
- **Listencode** zur Identifizierung des Listentyps mit Aufzählungszeichen oder Nummeriert - wird nicht immer von InDesign verwendet.
- Der Aufzählungscode **listet alle definierten Aufzählungstypen im Dokument auf.**
- **Zahlencode** listet alle definierten Nummerierungsstile im Dokument auf.

Eine sorgfältige Verwendung dieser Funktion ermöglicht andernfalls verloren gegangene lokale Formatierung und kann dazu beitragen, die Qualität einer Übertragung von formatierten Inhalten in DITA zu verbessern. Dieses Beispiel kann so aufgelöst werden, dass es kursiv 16 pt Text in einer Liste mit Aufzählungszeichen bedeutet: `p[Italic|16|-|-|-|b|-|-]`.

**Strukturzuordnung**

Die Strukturzuordnungsdatei ähnelt der Stilzuordnungsdatei mit einer einfachen Struktur, die alle Quellelemente und relevanten Attributtypen auflistet. Für die Aufzeichnung der Version der zu verwendenden Zuordnungsdatei werden zwei Attribute bereitgestellt: `@map_date` und `@map_version`.

**Dokumenttyp**

Das Element `doctypes` listet die unterstützten DITA-Mappings und Themenzuordnungen auf.

**Zuordnen von Dokumenttyp-Elementregeln**

Das Element `mapDoctypeElemRule` ist obligatorisch. Die Attribute dieses Elements dürfen nicht bearbeitet werden, da das Stammelement der Quell-XML immer dem Stamm-Element `map` der DITA-Map zugeordnet ist.

**Umbruchregeln für Elemente**

**`elementRules`element** Diese Liste listet alle Elemente auf.

**`elementRule`element** Das Element `elementRule` ist obligatorisch. Dies sind die Zuordnungsregeln für alle Quellelemente. Während ein InDesign-Dokument nicht strukturierte Stilelemente enthält, werden diese bei strukturierten-Inhalten ignoriert, es sei denn, die Verarbeitung des &#39;***Hybridmodus***&#39; ist aktiviert.

Die in `elementRule` verwendeten Attribute werden nachfolgend erläutert:

- `@elementName`: Der Name eines Elements im InDesign-Quelldokument.

- `@local`: Siehe [\#id194CG0V005Z](#id194CG0V005Z). \(Nur bei Hybriddokumenten nützlich\).

- `@mapTo`: Der Name eines DITA-Zielelements.

- `@refactor`: Dieses optionale Attribut hat zwei Werte:

   - `unwrap`: Das übereinstimmende Element wird entfernt, während der Inhalt beibehalten wird.

   - `drop`: Das übereinstimmende Element und alle zugehörigen Inhalte werden entfernt.

- `@context`: Dieses Attribut wird verwendet, um eine Verknüpfung zu einer bestimmten Wrapper-Regel herzustellen, wenn mehr als eine Wrapper-Auswahl verfügbar ist. Beispiel: Das Element `li` kann entweder in ein Element `ol` oder in ein Element `ul` eingeschlossen sein.

- `@commentOut`: Dieses Attribut ermöglicht das Umbrechen des Zielelements in XML-Kommentare, sodass die Informationen nicht verloren gehen, sondern vom Benutzer manuell verarbeitet werden können. Dies ist nützlich, wenn der Quellinhalt nicht gezwungen werden kann, die DITA-Strukturregeln einzuhalten.


## Fehlerbehebung in AEM Guides

Nachdem Sie AEM Guides installiert und konfiguriert haben, können Sie die Probleme beheben.

## Validieren von Verweisen

Sie können die angegebenen Skripte ausführen, um die Verweise zu überprüfen. Diese Skripte können Ihnen dabei helfen, die fehlerhaften Verweise zu identifizieren und sie dann zu patchen oder zu beheben.

- `/bin/fmdita/validatebtree?operation=validate` - meldet fehlerhafte Inhaltsverweise, behebt sie jedoch nicht.
- `/bin/fmdita/validatebtree?operation=patch` - listet die fehlerhaften Inhaltsreferenzen auf und behebt sie oder behebt sie.

**Skript überprüfen**

Führen Sie die folgenden Schritte aus, um die Verweise mithilfe des im Produktpaket verfügbaren Überprüfungsskripts zu überprüfen:

1. Führen Sie das Überprüfungsskript \[`/bin/fmdita/validatebtree?operation=validate`\] aus, um zu überprüfen, ob neue fehlerhafte Verweise vorhanden sind.
1. Falls das Überprüfungsskript Fehler meldet, können Sie diese mithilfe des Patch-Skripts patchen.
1. Notieren Sie sich die unten aufgeführten Details und geben Sie sie bei Bedarf für Ihr Customer Success Team frei:
1. 
   - Von Überprüfungsskript gedruckte Protokolle
- Paket von &quot;`/content/fmdita/references`&quot;
- Alle anderen erforderlichen Details, je nach gemeldetem Szenario

**Patch-Skript**

Führen Sie die folgenden Schritte aus, um fehlerhafte Verweise mithilfe des im Produktpaket verfügbaren Patch-Skripts zu patchen:

1. Führen Sie das Patch-Skript `[/bin/fmdita/validatebtree?operation=patch]` aus, um die fehlerhaften Verweise zu beheben. Die Ausführung des Skripts dauert einige Minuten und druckt die Protokolle im Laufe des Prozesses. Sobald die Ausführung abgeschlossen ist, wird am Ende &quot;`Done`&quot; gedruckt.

   **Hinweis:* Es wird empfohlen, die Protokolle zu Referenzzwecken zu kopieren und zu speichern.

1. Nachdem das Patch-Skript erfolgreich ausgeführt wurde, können Sie die folgenden Prüfungen durchführen:
1. 
   - Überprüfen Sie, ob ein neuer Knoten &quot;`references_backup_<timestamp>"`&quot;unter `/content/fmdita` erstellt wurde.
- Überprüfen, ob die Verweise korrigiert wurden

**Logger**

Sie können für diese Skriptausführung auch einen separaten Logger erstellen, wie im Folgenden beschrieben:

- Logger für Klasse &quot;`adobe.fmdita.common.BTreeReferenceValidator`&quot; hinzufügen
- Setzen Sie es auf `DEBUG`

Die erstellte Protokolldatei zeichnet alle Informationen auf, die mit der Skriptausführung zusammenhängen, und ist nützlich für den Fall, dass bei der Browsersitzung ein Timeout auftritt, während das Skript vom Browser ausgelöst wird.
