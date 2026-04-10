---
title: Anpassen der DITA-Elementzuordnung mit AEM-Komponenten
description: Erfahren Sie, wie Sie die DITA-Elementzuordnung mit AEM-Komponenten anpassen
feature: Output Generation
role: Admin
level: Experienced
source-git-commit: 834959a6a0e22cd5d2b2c5d0e57ceb6d45c0c666
workflow-type: tm+mt
source-wordcount: '1268'
ht-degree: 1%

---


# Anpassen der DITA-Elementzuordnung mit AEM-Komponenten {#id1679J600HEL}

DITA-Elemente in AEM Guides werden den entsprechenden AEM-Komponenten zugeordnet. AEM Guides verwendet diese Zuordnung in Workflows wie Veröffentlichung und Überprüfung, um ein DITA-Element in eine entsprechende AEM-Komponente zu konvertieren. Die Zuordnung wird in der `elementmapping.xml`-Datei definiert, auf die über den Package Manager für die Cloud Service-Einrichtung und über die URL zugegriffen werden kann: `/libs/fmdita/config/elementmapping.xml` im CRXDE Lite-Modus für die On-Premise-Einrichtung.

>[!NOTE]
>
> Nehmen Sie keine Anpassungen in den Standardkonfigurationsdateien im Knoten ``libs`` vor. Sie müssen eine Überlagerung des Knotens ``libs`` im Knoten ``apps`` erstellen und die erforderlichen Dateien nur im Knoten ``apps`` aktualisieren.

Sie können die vordefinierten DITA-Elementzuordnungen verwenden oder DITA-Elemente Ihren benutzerdefinierten AEM-Komponenten zuordnen. Um Ihre benutzerdefinierten AEM-Komponenten verwenden zu können, müssen Sie mit der Struktur der `elementmapping.xml`-Datei vertraut sein.

## Struktur ElementMapping.xml

Im Folgenden wird ein allgemeiner Überblick über die `elementmapping.xml`-Struktur gegeben:

1. Jedes DITA-Element wird zunächst anhand des Elementnamens nach einer entsprechenden Komponentenzuordnung durchsucht. Beispiel:

   ```XML
   <ditaelement>     
      <name>**substeps**</name>  
      <class>- topic/ol task/substeps</class>  
      <componentpath>dita/components/ditaolist</componentpath>  
      <type>COMPOSITE</type>  
      <target>para</target>
   </ditaelement>
   ```

   Im obigen Beispiel werden alle `substeps` DITA-Elemente mithilfe der `dita/components/ditaolist`-Komponente gerendert.

1. Wenn ein DITA-Element keine Übereinstimmung basierend auf dem Namen findet, wird eine Übereinstimmung auf Grundlage der `class` durchgeführt. Beispiel:

   ```XML
   <ditaelement>  
      <name>topic</name>  
      <class>**- topic/topic**</class>  
      <componentpath>fmdita/components/dita/topic</componentpath>  
      <type>COMPOSITE</type>  
      <target>para</target>  
      <attributemap> 
         <attribute from="id" to="id" />  
      </attributemap>
   </ditaelement>
   ```

   Wenn im obigen Beispiel keine Zuordnung für das `task` Element definiert ist, wird das `task` Element der obigen Komponente zugeordnet, da `task` von der `topic` übernommen wird.

1. Wenn ein Element über eine entsprechende Komponentenzuordnung verfügt, wird die weitere Verarbeitung seiner untergeordneten Elemente durch `type` bestimmt. Beispiel:

   ```XML
   <ditaelement>  
      <name>title</name>  
      <class>- topic/title</class>  
      <componentpath>foundation/components/title</componentpath>  
      <type>**STANDALONE**</type>  
      <target>para</target>  
      <textprop>jcr:title</textprop>
   </ditaelement>
   ```

   `type` nimmt die folgenden Werte an:

   - COMPOSITE: Element zu Komponente *die Zuordnung wird auch für* Elemente fortgesetzt.

   - EIGENSTÄNDIG: Untergeordnete Elemente des aktuellen Elements werden *nicht weiter zugeordnet*.

   Wenn im obigen Beispiel das `<title>` untergeordnete Elemente enthält, werden diese keiner anderen Komponente zugeordnet. Die -Komponente für `<title>` -Element ist für das Rendern aller untergeordneten -Elemente innerhalb des `<title>`-Elements verantwortlich.

1. Wenn einem einzelnen DITA-Element mehrere Komponenten zugeordnet sind, wird die beste Übereinstimmung für das Element ausgewählt. Um die Komponente mit der besten Übereinstimmung auszuwählen, wird eine Domain- und strukturelle Spezialisierung von DITA-Elementen berücksichtigt.

   Wenn es DITA-Elemente mit Domain-Spezialisierung gibt und eine Komponente für Domain-Spezialisierung zugeordnet ist, erhält diese Komponente hohe Priorität.

   Wenn es DITA-Elemente mit struktureller Spezialisierung gibt und eine Komponente für strukturelle Spezialisierung zugeordnet ist, wird dieser Komponente ebenfalls hohe Priorität eingeräumt.

1. Sie können `<attributemap>` in der Elementzuordnung verwenden, um Attributwerte den entsprechenden Knoteneigenschaften zuzuordnen.
1. `textprop` kann zum Serialisieren des Textinhalts eines DITA-Elements in eine Knoteneigenschaft verwendet werden. Darüber hinaus kann es mehrmals in einem -Element-Tag verwendet werden, um den Textinhalt an mehreren Stellen in der veröffentlichten Hierarchie zu serialisieren. Sie können auch den Speicherort und den Namen der Zieleigenschaft anpassen. Beispiel:

   ```XML
   <ditaelement>
      <name>title</name>
      <componentpath>foundation/components/title</componentpath>
      <type>STANDALONE</type>
      <target>para</target>
       <textprop>**jcr:title**</textprop>
   </ditaelement>
   ```

   Die obige Elementzuordnung gibt an, dass der Textinhalt `<title>` Elements als Wert einer Eigenschaft mit dem Namen &quot;`jcr:title`&quot; auf dem Ausgabeknoten gespeichert wird.

1. `xmlprop` kann zum Serialisieren der gesamten XML für ein bestimmtes Element in eine Knoteneigenschaft verwendet werden. Die Komponente kann dann diese Knoteneigenschaft lesen und benutzerdefinierte Darstellungen durchführen. Beispiel:

   ```XML
   <ditaelement>
       <name>svg-container</name>
      <class>+ topic/foreign svg-d/svg-container</class>
       <componentpath>fmdita/components/dita/svg</componentpath>
       <type>STANDALONE</type>
       <target>para</target>
      <xmlprop>**data**</xmlprop>
   </ditaelement>
   ```

   Die obige Elementzuordnung gibt an, dass das gesamte XML-Markup für Element `<svg-container>` als Wert einer Eigenschaft mit dem Namen `data` im Ausgabeknoten gespeichert wird.

1. Es gibt eine spezielle Attributzuordnung , um die Pfadauflösung beim Prozess der Ausgabegenerierung zu handhaben. Beispiel:

   ```XML
   <attributemap>
      <attribute from="href" to="fileReference" ispath="true" rel="source" />
      <attribute from="height" to="height" />
       <attribute from="width" to="width" />
   </attributemap>
   ```

   Für die obige `attributemap` wird das `href`-Attribut in Ihrem DITA-Element einer Knoteneigenschaft mit dem Namen `fileReference` zugeordnet. Da `ispath` nun auf `true` gesetzt ist, löst der Prozess der Ausgabegenerierung diesen Pfad auf und legt ihn dann in `fileReference` Knoteneigenschaft fest.

   Wie diese Auflösung geschieht, wird anhand des Werts des `rel` Attributs in der Attributzuordnung bestimmt.

   - Wenn `rel=source`, wird der Wert von `href` in Bezug auf die DITA-Quelldatei aufgelöst, die derzeit verarbeitet wird. Der Wert von `href` wird aufgelöst und im Wert `fileReference` Eigenschaft platziert.

   - Wenn `rel=target`, wird der Wert von `href` in Bezug auf den Stamm-Veröffentlichungsspeicherort aufgelöst. Der Wert von `href` wird aufgelöst und im Wert `fileReference` Eigenschaft platziert.

   Wenn keine Vorverarbeitung oder Auflösung für Pfadattribute erfolgen soll, müssen Sie das Attribut `ispath` nicht angeben. Der Wert wird unverändert kopiert und die Komponente kann die erforderliche Auflösung vornehmen.


## DITA-Element-Schema

Im Folgenden finden Sie ein Beispiel für das DITA-Elementschema in `elementmapping.xml` Datei :

```XML
<ditaelement>        
    <name>element_name</name>    
    <class>element_class</class>    
    <componentpath>fmdita/components/dita/component_name</componentpath>    
    <type>COMPOSITE|STANDALONE</type>     
    <attributeprop>propname_a</attributeprop>      
    <textprop>propname_t</textprop>    
    <xmlprop>propname_x</xmlprop>     
    <xpath>xpath expression string</xpath>     
    <target>head|para</target>     
    <wrapelement>div</wrapelement>     
    <wrapclass>class_name</wrapclass>     
    <attributemap>         
        <attribute from="attrname"         to="propname"         ispath="true|false"         rel="source|target" />    
    </attributemap>    
    <skip>true|false</skip> 
</ditaelement>
```

In der folgenden Tabelle werden die Elemente im DITA-Elementschema beschrieben:

| Element | Beschreibung |
|-------|-----------|
| `<ditaelement>` | Der Knoten der obersten Ebene für jedes Zuordnungselement. |
| `<class>` | Das Klassenattribut des Ziel-DITA-Elements, für das Sie die Komponente schreiben.<br> Das Klassenattribut für das DITA-Thema lautet beispielsweise: <br> `- topic/topic` |
| `<componentpath>` | Der CRXDE-Pfad der zugeordneten AEM-Komponente. |
| `<type>` | Mögliche Werte:<br> -   **COMPOSITE**: Verarbeiten Sie auch untergeordnete Elemente <br> -   **STANDALONE**: Überspringt die Verarbeitung von untergeordneten Elementen |
| `<attributeprop>` | Wird für die Zuordnung serialisierter DITA-Attribute und -Werte zu AEM-Knoten als Eigenschaft verwendet. Wenn Sie beispielsweise über `<note type="Caution">` Element verfügen und die Komponente, die für dieses Element zugeordnet ist, über `<attributeprop>attr_t</ attributeprop>` verfügt, werden das Attribut und der Wert des Knotens in `attr_t` Eigenschaft des entsprechenden AEM-Knotens \( `attr_t->type="caution"`\) serialisiert. |
| `<textprop>propname_t</textprop>` | Speichern Sie die `getTextContent()` Ausgabe in der Eigenschaft, die durch `propname_t.` <br> definiert ist **Hinweis:** Dies ist eine optimierte Eigenschaft. |
| `<xmlprop>propname_x </xmlprop>` | Speichern Sie die serialisierte XML dieses Knotens in der Eigenschaft `propname_x.<br> `**Hinweis:** Dies ist eine optimierte Eigenschaft. |
| `<xpath>` | Wenn in der Elementzuordnung ein XPath-Element angegeben ist, sollte neben dem Elementnamen und der Klasse auch die XPath-Bedingung erfüllt sein, damit die Komponentenzuordnung verwendet werden kann. |
| `<target>` | Platzieren Sie das DITA-Element im CRX-Repository an einem bestimmten Speicherort.<br> Mögliche Werte: <br> - **head**: Unter dem Kopfknoten <br> - **text**: Unter dem Absatzknoten |
| `<wrapelement>` | Das HTML-Element, in das der Inhalt eingeschlossen werden soll. |
| `<wrapclass>` | Der Elementwert zur `wrapclass.` |
| `<attributemap>` | Container-Knoten, der einen oder mehrere `<attribute>`-Knoten enthält. |
| `<attribute from="attrname" to="propname" ispath="true\|false" rel="source\|target" />` | Ordnet die DITA-Attribute AEM-Eigenschaften zu: <br> -   **`from`**: DITA-Attributname <br> -   **`to`**: Eigenschaftsname der AEM-Komponente <br> -   **`ispath`**: Wenn das Attribut ein Pfadwert ist \(z. B.: *image*\) <br> -   **`rel`**: Wenn der Pfad die Quell- oder <br> ist **Hinweis:** Wenn `attrname` mit `%` beginnt, dann ordnen Sie `attrname minus '%'` der Eigenschaft &#39; `propname`&#39; zu. |

**Zusätzliche Hinweise**

- Wenn Sie die standardmäßige Elementzuordnung überschreiben möchten, wird empfohlen, die Änderungen nicht in der `elementmapping.xml` vorzunehmen. Sie sollten eine neue XML-Zuordnungsdatei erstellen und die Datei an einem anderen Speicherort ablegen, vorzugsweise im Ordner für benutzerdefinierte Programme, den Sie erstellen.

- In der `elementmapping.xml`-Datei gibt es viele Zuordnungseinträge, die auf die fmdita/components/dita/wrapper-Komponente verweisen. Wrapper ist eine generische Komponente, die relativ einfache DITA-Konstrukte mithilfe von Eigenschaften auf ihrem Site-Knoten rendert, um relevante HTML zu generieren. Sie verwendet die `wrapelement`-Eigenschaft zum Generieren umschließender Tags und delegiert das untergeordnete Rendering an die entsprechenden Komponenten. Dies ist nützlich, wenn Sie nur eine Container-Komponente benötigen. Anstatt eine neue Komponente zu erstellen, die ein bestimmtes Container-Tag wie `div` oder `p` rendert, können Sie die Wrapper-Komponente mit den Eigenschaften `wrapelement` und `wrapclass` verwenden, um denselben Effekt zu erzielen.

- Es wird nicht empfohlen, große Textmengen in den JCR-Eigenschaften von String zu speichern. Durch die Berechnung des optimierten Eigenschaftstyps bei der Ausgabegenerierung wird sichergestellt, dass kein großer Textinhalt als String-Typ gespeichert wird. Wenn stattdessen Inhalte gespeichert werden müssen, die größer als ein bestimmter Schwellenwert sind, wird der Typ der Eigenschaft in „binär“ geändert. Dieser Schwellenwert ist standardmäßig auf 512 Byte konfiguriert, kann jedoch im Konfigurations-Manager \(*com.adobe.fmdita.config.ConfigManager*\) geändert werden, indem die Einstellung **Als binärer Schwellenwert speichern** geändert wird.

- Wenn Sie planen, einige \(und nicht alle\) der Elementzuordnungen zu überschreiben, müssen Sie nicht die gesamte `elementmapping.xml` replizieren. Sie müssen eine neue XML-Zuordnungsdatei erstellen und nur die Elemente definieren, die Sie überschreiben.

- Nachdem Sie die XML-Datei am benutzerdefinierten Speicherort erstellt haben, aktualisieren Sie die `Override Element Mapping` im `com.adobe.fmdita.config.ConfigManager`.


