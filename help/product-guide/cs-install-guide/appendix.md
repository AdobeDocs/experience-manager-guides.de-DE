---
title: Anhang
description: Erfahren Sie, wie Sie InDesign-Dokumente für die Migration vorbereiten
exl-id: 71b09039-b220-45f3-b334-c23f5b09dadc
feature: InDesign File Conversion, Troubleshooting
role: Admin
level: Experienced
hidefromtoc: true
source-git-commit: 564ee1731be2378744ffd2ed54a2fd423901a0b3
workflow-type: tm+mt
source-wordcount: '2852'
ht-degree: 0%

---

# Anhang {#id195AD0L60Y4}

## Fehlerbehebung bei AEM Guides

Nachdem Sie AEM Guides installiert und konfiguriert haben, können Sie die Probleme beheben.

## Verweise validieren

Sie können die angegebenen Skripte ausführen, um die Verweise zu überprüfen. Diese Skripte können Ihnen dabei helfen, die fehlerhaften Verweise zu identifizieren und sie dann zu korrigieren oder zu korrigieren.

- `/bin/fmdita/validatebtree?operation=validate` - meldet alle fehlerhaften Inhaltsreferenzen, behebt sie jedoch nicht.

- `/bin/fmdita/validatebtree?operation=patch` - Listet die fehlerhaften Inhaltsverweise auf und behebt sie oder behebt sie.


**Skript validieren**

Führen Sie die folgenden Schritte aus, um die Verweise mithilfe des im Produktpaket verfügbaren Validierungsskripts zu überprüfen:

1. Führen Sie das validate-Skript \[`/bin/fmdita/validatebtree?operation=validate`\] aus, um zu überprüfen, ob neue fehlerhafte Verweise vorhanden sind.
1. Falls das Skript „validate“ Fehler meldet, können Sie es mit dem Patch-Skript patchen.
1. Notieren Sie sich die unten angegebenen Details und teilen Sie sie bei Bedarf mit Ihrem Customer Success-Team:
1. 
   - Durch Validierungsskript ausgedruckte Protokolle
- Paket von &quot;`/content/fmdita/references`&quot;
- Alle anderen erforderlichen Details, abhängig vom gemeldeten Szenario

**Patch-Skript**

Führen Sie die folgenden Schritte aus, um fehlerhafte Verweise mithilfe des im Produktpaket verfügbaren Patch-Skripts zu reparieren:

1. Führen Sie das Patch-Skript `[/bin/fmdita/validatebtree?operation=patch]` aus, um die fehlerhaften Verweise zu beheben. Die Skriptausführung dauert einige Minuten und druckt die Protokolle im Verlauf. Nach Abschluss der Ausführung wird am Ende &quot;`Done`&quot; gedruckt.

>[!NOTE]
>
> Es wird empfohlen, die Protokolle zu Referenzzwecken zu kopieren und zu speichern.

1. Nachdem das Patch-Skript erfolgreich ausgeführt wurde, können Sie die folgenden Prüfungen durchführen:
1. 
   - Überprüfen Sie, ob der neue Knoten &quot;`references_backup_<timestamp>"`&quot; unter `/content/fmdita` erstellt wurde.
- Überprüfen, ob die Verweise korrigiert wurden

**Logger**

Sie können auch einen separaten Logger für diese Skriptausführung erstellen, wie im Folgenden beschrieben:

- Logger zur Klasse &quot;`adobe.fmdita.common.BTreeReferenceValidator`&quot; hinzufügen
- Setzen Sie ihn auf `DEBUG`

Die erstellte Protokolldatei zeichnet alle Informationen auf, die mit der Skriptausführung in Verbindung stehen. Sie ist nützlich, wenn im Browser Sitzungszeitüberschreitungen auftreten, während das Skript aus dem Browser ausgelöst wird.

## Vorbereiten von InDesign-Dateien für die Konvertierung {#id195DBF0045Z}

InDesign bietet Autorinnen und Autoren umfangreiche Funktionen zum Erstellen ansprechender und komplexer Dokumente. Dies bedeutet häufig, dass die verschiedenen Teile eines Dokuments visuell auf der Seite platziert werden, jedoch ohne dass versucht wird, einen Fluss zwischen diesen Textrahmen bereitzustellen. Wenn die &quot;*-Reihenfolge* der Textrahmen nicht definiert ist, enthält die IDML-Datei Storys, die möglicherweise keiner sinnvollen Reihenfolge folgen. Das Endergebnis ist ein oder mehrere DITA-Themen mit Absätzen, Tabellen und Grafiken in zufälliger Reihenfolge.

Es ist zwar möglich, den DITA-Inhalt in einem DITA-Editor in einer sinnvollen Reihenfolge zu bearbeiten, es ist jedoch viel einfacher, die InDesign-Datei zu reparieren, bevor die IDML-Datei erstellt wird. Dies kann ohne Änderung des Erscheinungsbildes des Quelldokuments erfolgen. Dies hat auch den Vorteil, dass das Quelldokument durch eine ordnungsgemäße Definition der Lesereihenfolge zugänglich wird.

***Threading von Textrahmen***

InDesign verwendet den Begriff *&#39;Threading&#39;* für den Prozess der Verknüpfung von einem Frame zu einem anderen. Weitere Informationen zum Einfädeln von Textrahmen finden Sie unter *[Einfädeln von Text](https://helpx.adobe.com/in/indesign/using/threading-text.html)* in der InDesign-Dokumentation.

***Überlappende Frames***

Einige InDesign-Dokumente verwenden aus Layout-Gründen überlappende Rahmen ohne Thread. Es kann sehr schwierig sein, diesen Inhalt mit dem Haupt-Thread zusammenzuführen. Die beste Option ist möglicherweise, das Ergebnis in der DITA-Umgebung zu bearbeiten.

***InDesign-Storys***

Jeder Inhaltsfluss in einem InDesign-Dokument wird als „Story *bezeichnet*. Um die bestmöglichen Ergebnisse zu erzielen, wird empfohlen, die Anzahl der Stories begrenzt zu halten. Es gibt jedoch einige Teile Ihres Dokuments, die in der DITA-Ausgabe möglicherweise nicht benötigt werden. Beispielsweise werden Seitenfußzeilen selten benötigt, können jedoch in der Mitte eines Themas angezeigt werden, wenn sie nicht sorgfältig gehandhabt werden.

Die einfachste Möglichkeit, Text auszuschließen, der im Dokument nicht erforderlich ist, besteht darin, ihm ein spezielles *Absatz-Tag* zu geben, das nur für den unerwünschten Inhalt verwendet wird. Anstatt beispielsweise einen *\[einfachen Absatz\]* für die Fußzeile wiederzuverwenden, erstellen Sie ein dediziertes *Fußzeilen*-Tag. Legen Sie dann in der MapStyle-Datei einfach die *Footer*-Absätze fest, die wie folgt eingefügt werden sollen:

```
<paraRule style="Footer" local="0" refactor="drop">
   <attributeRules createID="false"/>
</paraRule>
```

***Zuordnung zu DITA-Doctypes***

Es ist wichtig, dass Ihr Quelldokument mindestens einen Absatzstil oder ein Element enthält, der bzw. das den Beginn eines Themas markieren kann. Es ist üblich, dass Dokumente *Überschrift1* als Namen der Titel der obersten Ebene im Dokument verwenden. Anschließend können Sie eine Zuordnung von diesem Stil zu einem bestimmten DITA-Doctype erstellen. Wenn Ihr Dokument gut organisiert ist und die Verwendung von *Überschrift1* durchgängig konstant ist, erhalten Sie gute Ergebnisse.

***Mehrere DITA-Doctypes***

Wenn einige der *Überschrift1*-Absätze in verschiedene DITA-Doctypes konvertiert werden müssen, duplizieren Sie den Absatzstil in InDesign. Weisen Sie diesen Stilen einen leicht zu erkennenden Namen wie *Überschrift1\_genTask* oder *Überschrift1\_*) zu. Richten Sie dann die Datei „mapStyle“ wie unten gezeigt ein:

```
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

InDesign hat eine lockere Beziehung zu XML. Während ein Dokument eine XML-DTD enthalten kann und die Hauptgeschichte für diese DTD gültig sein kann, ist es auch möglich, hybride Dokumente zu erstellen, bei denen ein Teil des Inhalts XML ist, aber keine DTD enthalten ist. Dies sind die unerwünschten Fälle für eine erfolgreiche Konvertierung in DITA. Wenn ein Dokument XML-Teile enthält, versuchen Sie, die Ausgabe in XML zu speichern und sehen Sie, ob die Ergebnisse akzeptabel sind. Ist dies nicht der Fall, enthält der DITA-Inhalt auch ungültige Inhalte oder kann vollständig fehlschlagen.

***Tabellenformatierung***

Die Konvertierung von InDesign-Tabellenformatierungsregeln in die entsprechende Tabellenformatierung in DITA ist ein komplexer Prozess. Dies liegt an den umfangreichen Formatierungsfunktionen, die in den Quelldateien im Vergleich zu den grundlegenden Optionen verfügbar sind, die vom Oasis \(CALS\)-Tabellenmodell bereitgestellt werden, das in DITA verwendet wird. Die vertikale und horizontale Textausrichtung wird bereitgestellt und liefert ähnliche Ergebnisse, obwohl Blocktext immer entsprechend der Textrichtung ausgerichtet ist, während InDesign „Linksbündig“ und „Rechtsbündig“ zulässt.

Die Handhabung von Spalten- und Zeilentrennzeichen durch InDesign ist wiederum weitaus leistungsfähiger als die grundlegenden Optionen des Oasis-Tabellenmodells. InDesign bietet vier Zellenrahmen: Rahmentyp \(einfarbig oder musterförmig\), Rahmenstärke, Rahmenfarbe, Rahmenfarbe, Rahmenabstandsfarbe, Rahmenabstandsfarbe und Rahmenabstandsfarbe. All diese Elemente müssen nach unten auf Rahmen rechts und unten jeder Zelle \(Einstiegselement\) abgebildet werden, wobei die einzigen Optionen 0 oder 1 sind - Rahmen ausblenden oder anzeigen.

Der Grenzvorbescheid in InDesign kann auf folgenden Ebenen angewendet werden:

- Tabellenstile
- Zellenstile
- Lokale Überschreibungen in jeder Zelle

Der Konvertierungsprozess von InDesign nach DITA wendet den Grenzvorbescheid wie folgt an:

- Tabellenstile werden dem `colspec/@colsep` für vertikale Regeln zugeordnet. Horizontale Regeln werden dem Attribut `row/@rowsep` zugeordnet. In beiden Fällen wird das Attribut nicht erstellt, wenn der Rahmen nicht definiert ist.
- Zellenstile werden den `entry/@colsep`- und `entry/@rowsep` zugeordnet. Diese Werte überschreiben alle von Tabellenstilen abgeleiteten Rahmenregeln.
- Lokale Überschreibungen wenden die Formatierung direkt auf die Zelle an und überschreiben Tabellenstile und Zellenstile.

***Wechselnde Muster***

InDesign-Tabellenstile ermöglichen es, Spalten- und Zellenregeln einem alternierenden Muster zu folgen. Diese Funktion wird zwar für die Konvertierung unterstützt, die Ergebnisse sind jedoch nur sichtbar, wenn eine Mustergruppe den Vorgangs-\(1\) anzeigt und die andere Mustergruppe den Vorgangs-\(0\) ausblendet.

## Zuordnungsdatei für die Migration von InDesign zu DITA vorbereiten {#id194AF0003HT}

Für die korrekte DITA-Konvertierung ist eine Zuordnungsdatei erforderlich, die mit dem Inhalt des Quelldokuments übereinstimmt. Für unstrukturierte InDesign-Dokumente bedeutet dies, dass alle verfügbaren Absatzformate und Zeichenstile zugeordnet werden müssen. Bei XML-strukturierten InDesign-Dokumenten müssen alle Elemente in der zugehörigen DTD zugeordnet werden.

Die Zuordnungsdateien für unstrukturierte und strukturierte InDesign-Dokumente unterscheiden sich. Dies liegt an den komplexeren Verarbeitungsanforderungen für die Konvertierung unstrukturierter Quellinhalte in DITA.

Ein Beispiel für die Zuordnungsdatei finden Sie unten:

```
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

Die Zuordnungsdatei ist eine XML-Datei mit einer einfachen Struktur, die alle Absatzformate und Zeichenstil-Codes auflistet. Der Dateiinhalt wird im Folgenden erläutert:

**Stilzuordnung**

Im `styleMap` können Sie zwei optionale Attribute angeben: `@map_date` und `@map_version` für die Aufzeichnung der Version der Zuordnungsdatei.

**Dokumenttyp**

Im `doctypes` Element sind die unterstützten DITA-Zuordnungen und Themenzuordnungen aufgeführt.

**Absatzregeln für Dokumenttyp zuordnen**

Das `mapDoctypeParaRule` ist obligatorisch. Die Attribute dieses Elements dürfen nicht bearbeitet werden, da das Stammelement der Quell-XML immer dem `map` der DITA-Zuordnung zugeordnet ist.

**Absatzregel vom Typ Dokument**

Das `doctypeParaRule` ist obligatorisch. Dadurch kann der Konvertierungsprozess den Beginn eines neuen Themas identifizieren. Normalerweise wird das Attribut `@style` allein verwendet, wobei das Attribut `@local` auf 0 gesetzt ist. Wenn es jedoch immer lokale Formatierungsüberschreibungen für den ausgewählten Stil gibt, müssen Sie eine Regel für jeden Stil plus die lokalen Überschreibungen hinzufügen. Dies ist einfach in der generierten Zuordnungsdatei zu erkennen, wo es möglich wäre, dies oder Ähnliches zu finden:

```
<paraRule style="Heading 1" local="0" mapTo="p">
   <attributeRules createID="true"/>
</paraRule>
<paraRule style="Heading 1" local="p[Italic|-|-|-|-|-|-|-]" mapTo="p">
   <attributeRules createID="true"/>
</paraRule>
```

Im obigen Beispiel gibt es zwei `paraRule` für `@style` = „Überschrift1“. Erstellen Sie einfach ein äquivalentes `doctypeParaRule`, wobei Sie das Attribut `@mapToDoctype` nach Bedarf festlegen.

Im Folgenden werden die in der `doctypeParaRule` verwendeten Attribute erläutert:

- `@style`: Der Name eines Stils im InDesign-Quelldokument.
- `@local`: Siehe [\#id194CG0V005Z](#id194CG0V005Z).
- `@mapToDoctype`: Der Name eines DITA-Thementyps aus einer Aufzählungsliste aller gültigen `doctypes`.

**Regeln für Elementumbruch**

Die Regeln für den Elementumbruch definieren die Möglichkeiten zum Umbrechen oder Verschieben von Elementen im eingehenden Dokument in ein vordefiniertes Element entsprechend einem Satz von Attributwerten.

***`wrap`Element***

Dies ist ein optionales Element. Das `wrap` Element listet die Elemente auf, die umschlossen oder verschoben werden. Der Umbruch wird normalerweise verwendet, wenn einer Reihe von Elementen ein gemeinsames übergeordnetes Element zugewiesen werden muss. Beispielsweise werden mehrere `li` Elemente in ein `ol` Element eingeschlossen. Darüber hinaus können `wrap` zum Verschieben von Elementen verwendet werden, z. B. Titel für Abbildungen und Tabellen.

Im Folgenden werden die in der `wrap` verwendeten Attribute erläutert:

- `@element`: Ein Pluszeichen nach einem Elementnamen zeigt an, dass alle benachbarten Elemente mit demselben Namen in das Element mit dem Namen im `@wrapper`Attribut eingeschlossen werden.
- `@wrapper`: Der Name des Wrapping-Elements.
- `@context`: Bietet eine Möglichkeit, den Wrapper für ein bestimmtes Element weiter zu verfeinern. Im folgenden Beispiel wird gezeigt, wie eine Reihe von `li`-Elementen entweder in einer sortierten `ol` oder in einer nicht sortierten Liste `ul` dem `@context` \ (der Kontext wird im `paraRule` definiert\) zugeordnet werden kann:

  ```
  <wrap elements="li+" context="number" wrapper="ol">
     <attributeRules createID="true"/>
  </wrap>
  <wrap elements="li+" context="bullet" wrapper="ul">
     <attributeRules createID="true"/>
  </wrap>
  ```


Das folgende Beispiel zeigt, wie ein `fig`-Element aus einem `title` und einem `image`-Element erstellt wird:

- `@elements`: Die aufgelisteten und durch ein Komma getrennten Elemente werden in das Element namens im `@wrapper` eingeschlossen. Aufgrund der gängigen Praxis, Bildtitel unter dem Bild einzufügen, ist der Titel das `title` Element, das unmittelbar auf die `image` folgt.

  Die folgende Wrap-Regel:

  ```
  <wrap elements="title, image" context="FigTitle" wrapper="fig">
     <attributeRules createID="true"/>
  </wrap>
  ```

  Konvertiert die folgende Zwischen-XML:

  ```
  <image href="Links/myImage.png" scale="59">
     <title>IDML2DITA workflow</title>
  ```

  In die folgende gültige DITA-Figurenstruktur:

  ```
  <fig id="id397504">
     <title>IDML2DITA workflow</title>
     <image href="Links/myImage.png" scale="59">
  </fig>
  ```

- `@wrapper`: Der Name des Wrapping-Elements.
- `@context`: Bietet eine Möglichkeit, die Art und Weise weiter zu verfeinern, wie ein bestimmtes Element umschlossen wird \(der Kontext wird im `paraRule` Element definiert\).

Das folgende Beispiel zeigt, wie ein `title` in ein `table` verschoben wird:

- `@elements`: Das `title` Element, das sich entweder unmittelbar vor oder unmittelbar nach einem `table` befindet, wird in das Element mit dem Namen im `@wrapper` eingeschlossen. Eine Eigenschaft im XPath-Stil kann die Position des title-Elements als `[before]` oder `[after]` identifizieren.

  Beispiel: Die folgende Wrap-Regel:

  ```
  <wrap elements="title[before]" context="TableTitle" wrapper="table">
     <attributeRules createID="true"/>
  </wrap>
  ```

  Konvertiert die folgende Zwischen-XML:

  ```
  <title>IDML2DITA workflow</title>
  <table id="id289742" outputclass="BasicTable">
     <tgroup cols="2">
        <colspec colname="0" colwidth="0.7*">
           <colspec colname="1" colwidth="0.3*">
  ```

  In diese gültige DITA-Figurenstruktur:

  ```
  <table id="id289742" outputclass="BasicTable">
     <title>IDML2DITA workflow</title>
     <tgroup cols="2">
        <colspec colname="0" colwidth="0.7*">
           <colspec colname="1" colwidth="0.3*">
  ```

- `@wrapper`: Der Name des Wrapping-Elements.

- `@context`: Bietet eine Möglichkeit, die Art und Weise weiter zu verfeinern, wie ein bestimmtes Element umschlossen wird \(der Kontext wird im `paraRule` Element definiert\).


**Absatzstilregeln**

Die `paragraphStyleRule` Elemente werden nachfolgend beschrieben:

** `paraRule` Element**

Das `paraRule` ist obligatorisch. Dies legt die Zuordnungsregeln für alle Absatzformate fest. In einem InDesign-Dokument ist der gesamte Text in der Unterstruktur von Absatzformaten enthalten, auch Absätze ohne Stil werden `\[No paragraph style\]` genannt. Die eckigen Klammern geben einen integrierten Namen im InDesign-Stil an.

>[!NOTE]
>
> Die eckigen Klammern zeigen einen integrierten Namen im InDesign-Stil an.

Im Folgenden werden die in der `paraRule` verwendeten Attribute erläutert:

- `@style`: Der Name eines Stils im InDesign-Quelldokument.
- `@local`: Siehe [\#id194CG0V005Z](#id194CG0V005Z).
- `@mapTo`: Der Name eines DITA-Zielelements.

- `@context`: Dieses Attribut wird verwendet, um eine Verknüpfung zu einer bestimmten **Wrap**-Regel herzustellen, wenn mehr als eine Wrapper-Auswahl verfügbar ist. Beispiel: Das `li` Element kann entweder in ein `ol` oder in ein `ul` Element eingeschlossen sein. Um die verschiedenen Listentypen zu identifizieren, können Sie einen bestimmten Stilnamen oder das `@local`-Attribut verwenden, das Folgendes anzeigen kann:
   - `local="p[-|-|-|-|-|b|-|-]"` Wobei &quot;`b`&quot; in Feld 6 ein Aufzählungslistenelement anzeigt. Legen Sie in diesem Fall `@context` auf &quot;`bullet`&quot; fest.
   - `local="p[-|-|-|-|-|n|-|-]"` Wobei &quot;`n`&quot; in Feld 6 ein nummeriertes Listenelement angibt. Legen Sie in diesem Fall `@context` auf &quot;`number`&quot; fest.

- `@commentOut`: Dieses Attribut ermöglicht das Umschließen des Zielelements in XML-Kommentaren, sodass die Informationen nicht verloren gehen, sondern vom Benutzer manuell verarbeitet werden können. Dies ist nützlich, wenn der Quellinhalt nicht gezwungen werden kann, den DITA-Strukturregeln zu entsprechen.

- `@refactor`: Für dieses optionale Attribut stehen zwei Werte zur Auswahl:

- `unwrap`: Das übereinstimmende Element wird entfernt, während sein Inhalt beibehalten wird.

- `drop`: Das übereinstimmende Element und sein gesamter Inhalt werden entfernt.


**Zeichenstilregeln**

Die `charRule` Elemente werden nachfolgend beschrieben:

>[!NOTE]
>
> Für die integrierte `[No character style]` gibt es bei der `local="0"` keine Zuordnung, da sie während der Vorverarbeitung entfernt werden.

***`charRule`Element***

Dies ist ein optionales Element.

Dies sind die Zuordnungsregeln für alle Zeichenstile. In einem InDesign-Dokument ist der gesamte Text in untergeordneten Elementen der Zeichenformate enthalten.

Im Folgenden werden die in der `charRule` verwendeten Attribute erläutert:

- `@style`: Der Name eines Stils im InDesign-Quelldokument.
- `@local`: Siehe [\#id194CG0V005Z](#id194CG0V005Z).
- `@mapTo`: Der Name eines DITA-Zielelements.
- `@refactor`: Für dieses optionale Attribut stehen zwei Werte zur Auswahl:
   - `unwrap`: Das übereinstimmende Element wird entfernt, während sein Inhalt beibehalten wird.

   - `drop`: Das übereinstimmende Element und sein gesamter Inhalt werden entfernt.


**Attributregeln**

Dieses Element kann ein untergeordnetes Element der folgenden Elementkontexte sein:

- `mapDoctypeParaRule`
- `mapDoctypeElemRule`
- `doctypeParaRule`
- `doctypeElemRule`
- `paraRule`
- `charRule`
- `elementRule`

Attributregeln dienen zur Verwaltung der Attribute für die übereinstimmenden Elemente.

Je nach Kontext sind die folgenden Attribute für das `attributeRules` verfügbar:

- `@createID`: Generiert eine eindeutige ID für die übereinstimmenden Elemente. Zulässige Werte `true` oder `false`. In allen Kontexten verfügbar.
- `@copyAll`: Kopiert alle Attribute aus dem Quell-XML-Inhalt nur für strukturierte Quelldateien. Zulässige Werte sind `true` oder `false`. Verfügbar für Kontexte `mapDoctypeParaRule`, `mapDoctypeElemRule`, `doctypeElemRule` und `elementRule`.


Im Folgenden werden die in der `attributeRules` verwendeten Attribute erläutert:

>[!NOTE]
>
> Dieses Element kann mehrere untergeordnete Elemente enthalten.

- `addNew`: Fügt dem übereinstimmenden Element ein neues Attribut hinzu. Verfügbar für alle Kontexte. Sie weist zwei Attribute auf:
   - `@name`: Muss ein gültiger XML-Name sein, vorzugsweise gültig für den DITA-Kontext.
   - `@value`: Kann ein literaler Text oder ein einfacher XPath-Ausdruck sein.
- `copyAtt`: Kopiert ein einzelnes Attribut in das Ziel, wobei es optional im Prozess umbenannt wird. Der Wert wird nicht geändert. Verfügbar für Kontexte `mapDoctypeParaRule`, `mapDoctypeElemRule`, `doctypeElemRule` und `elementRule`. Wenn dieses Element vorhanden ist, wird davon ausgegangen, dass der `@copyAllAtts` Wert `false` ist. Sie weist zwei Attribute auf:
   - `@name`: Muss der Name eines Attributs sein, das im XML-Quellelement vorhanden ist.
   - `@mapTo`: Muss ein gültiger XML-Name sein, vorzugsweise gültig für den DITA-Kontext.

**Lokale Formatierungscodes**

In jedem InDesign-Dokument können Absatzformate und Zeichenstile mehrere Hundert verschiedene Formatierungsüberschreibungen enthalten. Die meisten dieser Eigenschaften spielen keine nützliche Rolle im Konvertierungsprozess. Wir haben jedoch eine Reihe von Formatierungsfunktionen identifiziert, die sich auf die Semantik des Dokuments auswirken und den Konvertierungsprozess beeinflussen müssen.

Die `@local` Attribute werden als spezielles, durch Trennzeichen getrenntes Format angezeigt, bei dem acht Felder zusammen mit einem Präfix bereitgestellt werden, um den Typ der Formatierungsüberschreibungen anzuzeigen. Die Felder Formatierungscodes sind unten aufgeführt:

- Präfix **p** für lokale parastile Überschreibung oder **c** für lokale Überschreibung im Zeichenstil.
- **Schriftstil** der Familienname und Eigenschaften wie &quot;***Bold Condensed Italic***&quot;.
- **Schriftgröße** in Punkt.
- **Zeichenposition** für hochgestellte oder tiefgestellte Zeichen.
- **Unter** für Unterstrich.
- **Strike** für Durchstreichen.
- **Listencode** zur Identifizierung des Listentyps als Aufzählungszeichen oder nummeriert - wird nicht immer von InDesign verwendet.
- **Aufzählungscode** listet alle definierten Aufzählungstypen im Dokument auf.
- **Zahlencode** listet alle definierten Nummerierungsstile im Dokument auf.

Durch sorgfältige Verwendung dieser Funktion gehen ansonsten verloren gegangene lokale Formatierungen verloren. Dies kann dazu beitragen, die Qualität der Übertragung von formatierten Inhalten in DITA zu verbessern. Dieses Beispiel kann aufgelöst werden, sodass es kursiv, 16 pt Text in einer Aufzählungsliste bedeutet: `p[Italic|16|-|-|-|b|-|-]`.

**Strukturzuordnung**

Die Strukturzuordnungsdatei ähnelt der Stilzuordnungsdatei mit einer einfachen Struktur, die alle Quellelemente und relevanten Attributtypen auflistet. Für die Aufzeichnung der zu verwendenden Version der Zuordnungsdatei werden zwei Attribute, `@map_date` und `@map_version`, bereitgestellt.

**Dokumenttyp**

Im `doctypes` Element sind die unterstützten DITA-Zuordnungen und Themenzuordnungen aufgeführt.

**Elementregeln für Dokumenttyp zuordnen**

Das `mapDoctypeElemRule` ist obligatorisch. Die Attribute dieses Elements dürfen nicht bearbeitet werden, da das Stammelement der Quell-XML immer dem `map` der DITA-Zuordnung zugeordnet ist.

**Regeln für Elementumbruch**

Siehe [\#id194CG600NY4](#id194CG600NY4).

**`elementRules`Element**

Hier werden alle [\#id194CGC00SHS](#id194CGC00SHS)Elemente aufgelistet.

**`elementRule`Element**

Das `elementRule` ist obligatorisch. Dies sind die Zuordnungsregeln für alle Quellelemente. Ein InDesign-Dokument enthält zwar nicht strukturierte Stilelemente, diese werden jedoch für strukturierte Inhalte ignoriert, es sei denn, die Verarbeitung ***Hybridmodus*** ist aktiviert.

Im Folgenden werden die in der `elementRule` verwendeten Attribute erläutert:

- `@elementName`: Der Name eines Elements im InDesign-Quelldokument.

- `@local`: Siehe [\#id194CG0V005Z](#id194CG0V005Z). \(Nur für hybride Dokumente nützlich\).

- `@mapTo`: Der Name eines DITA-Zielelements.

- `@refactor`: Für dieses optionale Attribut stehen zwei Werte zur Auswahl:

   - `unwrap`: Das übereinstimmende Element wird entfernt, während sein Inhalt beibehalten wird.

   - `drop`: Das übereinstimmende Element und sein gesamter Inhalt werden entfernt.

- `@context`: Dieses Attribut wird verwendet, um eine Verknüpfung zu einer bestimmten Wrapper-Regel herzustellen, wenn mehr als eine Wrapper-Auswahl verfügbar ist. Beispiel: Das `li` Element kann entweder in ein `ol` oder in ein `ul` Element eingeschlossen sein.

- `@commentOut`: Dieses Attribut ermöglicht das Umschließen des Zielelements in XML-Kommentaren, sodass die Informationen nicht verloren gehen, sondern vom Benutzer manuell verarbeitet werden können. Dies ist nützlich, wenn der Quellinhalt nicht gezwungen werden kann, den DITA-Strukturregeln zu entsprechen.
