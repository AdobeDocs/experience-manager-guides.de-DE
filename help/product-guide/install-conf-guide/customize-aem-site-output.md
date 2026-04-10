---
title: Einstellungen für die Ausgabegenerierung konfigurieren
description: Erfahren Sie, wie Sie Einstellungen für die Ausgabenerstellung konfigurieren
feature: Output Generation
role: Admin
level: Experienced
source-git-commit: 6f3f05419f4f5cdd45ab580cdee6fa869f20f01d
workflow-type: tm+mt
source-wordcount: '3098'
ht-degree: 1%

---


# Anpassen der AEM-Site-Ausgabe {#id166TG0B30WR}

AEM Guides unterstützt das Erstellen von Ausgaben in folgenden Formaten:

- AEM Site
- PDF
- HTML5
- EPUB
- Benutzerdefinierte Ausgabe über DITA-OT

Für die Ausgabe der AEM-Site können Sie verschiedene Design-Vorlagen mit verschiedenen Ausgabeaufgaben zuweisen. Diese Design-Vorlagen können den DITA-Inhalt in verschiedenen Layouts rendern. Sie können beispielsweise verschiedene Design-Vorlagen für interne und externe Zielgruppen angeben.

Mit dem AEM Guides können Sie auch benutzerdefinierte DITA Open Toolkit \(DITA-OT\)-Plug-ins verwenden. Sie können diese benutzerdefinierten DITA-OT-Plug-ins hochladen, um die PDF-Ausgabe auf eine bestimmte Weise zu generieren.

>[!TIP]
>
> Best Practices für die Erstellung *AEM-Site-Ausgabe finden Sie im Abschnitt* Best [&quot; zur Veröffentlichung der AEM-Site.](https://helpx.adobe.com/content/dam/help/en/xml-documentation-solution/cs-mar-22/Adobe-Experience-Manager-Guides_Best-Practices_EN.pdf)


## Anpassen der Design-Vorlage für die Generierung von Ausgaben {#customize_xml-add-on}

Der AEM Guides verwendet einen Satz vordefinierter Design-Vorlagen , um die Ausgabe der AEM-Site zu generieren. Sie können die AEM Guides-Design-Vorlagen anpassen, um die Ausgabe zu generieren, die Ihrem Unternehmensbranding entspricht. Eine Design-Vorlage ist eine Sammlung verschiedener Stile \(CSS\), Skripte \(Server- und Client-seitig\), Ressourcen \(Bilder, Logos und andere Assets\) und JCR-Knoten, die alle diese Ressourcen miteinander verbinden. Eine Design-Vorlage kann so einfach sein wie ein einzelnes Server-seitiges Skript mit nur einigen JCR-Knoten oder eine komplexe Kombination aus Stilen, Ressourcen und JCR-Knoten. Design-Vorlagen werden vom AEM Guides-Veröffentlichungs-Subsystem beim Generieren der AEM-Site-Ausgabe verwendet und steuern die Struktur, das Erscheinungsbild der generierten Ausgabe.

Es gibt keine Einschränkung bezüglich des Speicherorts der Ressourcen der Design-Vorlage auf dem Server, sie sind jedoch in der Regel gemäß ihrer Funktion logisch organisiert. Beispielsweise werden bei der Standardvorlage alle JavaScript- und CSS-Dateien im Ordner `/etc/designs/fmdita/clientlibs/siteoutput/default` gespeichert. Wo auch immer sich diese Dateien befinden, sie sind durch eine Sammlung von JCR-Knoten miteinander verknüpft. Zusammen bilden diese JCR-Knoten und die Dateien die gesamte Design-Vorlage.

Die mit der AEM Guides ausgelieferte Standard-Design-Vorlage ermöglicht die Anpassung der Komponenten der Landingpage, des Themas und der Suchseite. Sie können eine Kopie des Standarddesigns und der entsprechenden Referenzvorlagen erstellen und verschiedene Komponenten angeben, um die gewünschte Ausgabe zu generieren.

Die folgenden Registerkarten enthalten Anweisungen zum Angeben Ihrer eigenen Design-Vorlage, die für die Generierung der AEM-Site-Ausgabe basierend auf Ihrer Experience Manager Guides-Einrichtung verwendet werden soll: Cloud Service oder On-Premise.

>[!BEGINTABS]

>[!TAB Cloud Service]

1. Verwenden Sie den Package Manager , um die standardmäßige Design-Vorlage vom folgenden Speicherort herunterzuladen:

   /libs/fmdita/config/templates

1. Erstellen Sie eine Kopie der heruntergeladenen Dateien am folgenden Speicherort im Git-Repository von Cloud Manager:

   /apps/fmdita/config/templates

1. Sie müssen auch die referenzierten Vorlagen vom Standardvorlagenknoten herunterladen und kopieren. Die referenzierten Vorlagen befinden sich unter:

   /libs/fmdita/templates/default/cqtemplates

>[!TAB On-Premise]

1. Melden Sie sich bei AEM an und öffnen Sie den CRXDE Lite-Modus.

1. Navigieren Sie zum Knoten für die Standardentwurfsvorlage. Der standardmäßige Design-Vorlagenknoten befindet sich hier:

   `/libs/fmdita/config/templates/`

   ![](assets/templates-node.png){width="300" align="left"}

   >[!NOTE]
   >
   > Erstellen Sie eine Kopie der standardmäßigen Design-Vorlagen aus dem Ordner `libs` in den Ordner `apps` und nehmen Sie Änderungen im Ordner `apps` vor. Sie müssen auch Änderungen an den Vorlagen vornehmen, auf die vom Standardvorlagenknoten verwiesen wird. Die referenzierten Vorlagen werden unter `/libs/fmdita/templates/default/cqtemplates` Knoten platziert. Erstellen Sie eine Kopie der referenzierten Vorlagen im `apps` Ordner, bevor Sie Änderungen vornehmen.

1. Klicken Sie auf die *Standard*-Komponente im *Vorlagen*-Knoten, um auf ihre Eigenschaften zuzugreifen.

>[!ENDTABS]

Die Eigenschaften der AEM Guides-Design-Vorlage werden in der folgenden Tabelle beschrieben.

| Eigenschaft | Beschreibung |
|--------|-----------|
| `landingPageTemplate`, `searchPageTemplate`, `topicPageTemplate`, `shadowPageTemplate` | Geben Sie den `cq:Template` Knoten für die entsprechenden Seiten an \(Landing, Search und Topic\). Standardmäßig befindet sich der `cq:Template` Knoten für diese Seiten `/libs/fmdita/templates/default/cqtemplates` Knoten . Dieser Knoten definiert die Struktur und Eigenschaften der Landingpage, Suche und Themenseite.<br> Die `shadowPageTemplate` wird zur Optimierung des segmentierten Inhalts verwendet. Sie müssen den Wert dieser Eigenschaft auf Folgendes setzen: `fmdita/templates/default/cqtemplates/shadowpage` <br> **Hinweis** Sie müssen einen Wert für die `topicPageTemplate` angeben. `landingPageTemplate` und `searchPageTemplate` sind optionale Eigenschaften. Wenn Sie nicht möchten, dass die Such- und Landingpages generiert werden, geben Sie diese Eigenschaften nicht an. |
| `title` | Ein beschreibender Name Ihrer Design-Vorlage. |
| `topicContentNode` | Der Speicherort des Knotens, der den DITA-Inhalt auf einer Themenseite enthalten wird. Der Pfad ist relativ zur Themenseite. |
| `topicHeadNode` | Der Speicherort des Knotens, der die vom DITA-Inhalt abgeleiteten Kopfwerte \(oder Metadaten\) enthalten wird. Der Pfad ist relativ zur Themenseite. |
| `tocNode` | Der Speicherort des Knotens, der das Inhaltsverzeichnis enthalten wird. Der Pfad ist relativ zur Landingpage oder zum Zielpfad. |
| `basePathProp` | Der Eigenschaftsname zum Speichern des Pfads des Stamms der veröffentlichten Site. |
| `indexPathProp` | Der Eigenschaftsname zum Speichern des Pfads der Landingpage/Indexseite der veröffentlichten Site. |
| `pdfPathProp` | Der Eigenschaftsname zum Speichern des Themapfades für PDF, wenn die Themengenerierung für PDF aktiviert ist. |
| `pdfTypeProp` | Der Eigenschaftsname zum Speichern des Typs der PDF-Generierung. Derzeit enthält diese Eigenschaft immer „Thema“. |
| `searchPathProp` | Der Eigenschaftsname zum Speichern des Pfads der Suchseite, wenn die Vorlage eine Suchseite enthält. |
| `siteTitleProp` | Der Eigenschaftsname zum Speichern des Titels der veröffentlichten Site. Dieser Titel ist in der Regel identisch mit dem Titel der Karte, die veröffentlicht wird. |
| `sourcePathProp` | Der Eigenschaftsname zum Speichern des Pfads des DITA-Quellthemas für die aktuelle Seite. |
| `tocPathProp` | Der Eigenschaftsname zum Speichern des Pfads des Inhaltsverzeichnisstamms für die veröffentlichte Site. |


>[!NOTE]
>
> Nachdem Sie einen benutzerdefinierten Design-Vorlagenknoten erstellt haben, müssen Sie die Option Design in den AEM-Site-Ausgabevorgaben aktualisieren, um den benutzerdefinierten Design-Vorlagenknoten zu verwenden.

Weitere Informationen finden Sie unter [Erstellen der ersten Adobe Experience Manager-Website](https://experienceleague.adobe.com/docs/experience-manager-learn/getting-started-wknd-tutorial-develop/overview.html?lang=de) und [Grundlagen](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/developing/full-stack/develop-wknd-tutorial.html?lang=en) Entwicklung einer eigenen Website in AEM.

## Verwenden des Dokumenttitels zum Generieren der AEM-Site-Ausgabe

Beim Generieren der AEM-Site-Ausgabe spielt die Art und Weise, wie URLs generiert werden, eine wichtige Rolle für die Auffindbarkeit Ihrer Inhalte. Wenn Sie UUID-basierte Dateinamen verwenden, ist das Generieren von URLs, die auf der UUID Ihrer Dateien basieren, nicht suchfreundlich. Als Administrator oder Publisher haben Sie die Kontrolle darüber, wie Sie die URLs für die Ausgabe Ihrer AEM-Site generieren möchten. AEM Guides bietet eine Konfiguration, mit der Sie die URLs der AEM-Site-Ausgabe anhand des Dateinamens und nicht anhand der UUID-basierten Dateinamen generieren können. Standardmäßig ist diese Option für UUID-basierte Dateisysteme aktiviert. Dies bedeutet, dass beim Generieren der AEM-Site-Ausgabe für UUID-basierte Dateisysteme die Dateititel zum Generieren der URLs und nicht die UUIDs der Dateien verwendet werden.

Bei On-Premise-Setups mit nicht-UUID-basierten Dateisystemen wird die AEM-Site-Ausgabe anhand der Dateinamen und nicht anhand der Dateititel generiert. Standardmäßig ist diese Option deaktiviert. Dies bedeutet, dass beim Generieren der AEM-Site-Ausgabe die Dateinamen zum Generieren der URLs und nicht zum Generieren des Dateititels verwendet werden. Sie können die URLs anhand der Titel der Datei generieren, indem Sie diese Option aktivieren.

Die folgenden Registerkarten enthalten Anweisungen zum Konfigurieren der URL-Generierung in der AEM-Site-Ausgabe basierend auf Ihrer Experience Manager Guides-Einrichtung: Cloud Service oder On-Premise.

>[!NOTE]
>
> Sie können außerdem Regeln konfigurieren, um in den URLs einer AEM-Site-Ausgabe nur einen Zeichensatz zuzulassen. Weitere Informationen finden Sie unter [Konfigurieren von Regeln zur Bereinigung von Dateinamen zum Erstellen von Themen und Veröffentlichen der Ausgabe der AEM-Site](#id2164D0KD0XA).

>[!BEGINTABS]

>[!TAB Cloud Service]

Verwenden Sie die Anweisungen unter [Konfigurationsüberschreibungen](download-install-config-override.md#), um die Konfigurationsdatei zu erstellen. Geben Sie in der Konfigurationsdatei die folgenden \(property\)-Details an, um die URL-Generierung in der AEM-Site-Ausgabe zu konfigurieren:

| PID | Eigenschaftsschlüssel | Eigenschaftswert |
|---|------------|--------------|
| `com.adobe.fmdita.config.ConfigManager` | `aemsite.pagetitle` | Boolescher Wert \(true/false\). Falls Sie eine Ausgabe mithilfe des Seitentitels generieren möchten, setzen Sie diese Eigenschaft auf „true“. Standardmäßig ist festgelegt, dass der Dateiname verwendet wird.<br> **Standardwert**: false |


>[!TAB On-Premise]

1. Öffnen Sie die Seite Konfiguration der Adobe Experience Manager-Web-Konsole .

   Die Standard-URL für den Zugriff auf die Konfigurationsseite lautet:

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Suchen Sie nach dem Bundle **com.adobe.fmdita.config.ConfigManager** und klicken Sie darauf.

1. Wählen Sie die Option **Titel für AEM Site-Seitennamen verwenden** aus.

   >[!NOTE]
   >
   > Falls Sie eine Ausgabe mit den Dateinamen erzeugen möchten, deaktivieren Sie diese Option.

1. Klicken Sie auf **Speichern**.

>[!ENDTABS]

## Konfigurieren Sie die URL der Ausgabe der AEM-Site so, dass der Dokumenttitel verwendet wird (nur für Cloud Service)

Sie können die Dokumenttitel in der URL der Ausgabe der AEM-Site verwenden. Wenn der Dateiname nicht vorhanden ist oder alle Sonderzeichen enthält, können Sie das System so konfigurieren, dass die Sonderzeichen durch ein Trennzeichen in der URL der AEM-Site-Ausgabe ersetzt werden. Sie können auch so konfigurieren, dass sie durch den Namen des ersten untergeordneten Themas ersetzt werden.


Um die Seitennamen zu konfigurieren, führen Sie die folgenden Schritte aus:

1. Verwenden Sie die Anweisungen unter [Konfigurationsüberschreibungen](download-install-config-override.md#), um die Konfigurationsdatei zu erstellen.
1. Geben Sie in der Konfigurationsdatei die folgenden (Eigenschafts-)Details an, um die Seitennamen für die Themen zu konfigurieren.

| PID | Eigenschaftsschlüssel | Eigenschaftswert |
|---|------------|--------------|
| `com.adobe.fmdita.common.SanitizeNodeName` | `nodename.systemDefinedPageName` | Boolescher Wert (`true/false`). **Standardwert**: `false` |

Wenn beispielsweise *@navtitle* in `<topichead>` alle Sonderzeichen enthält und Sie die `aemsite.pagetitle`-Eigenschaft auf „true“ setzen, wird standardmäßig ein Trennzeichen verwendet. Wenn Sie die `nodename.systemDefinedPageName` auf „true“ setzen, wird der Name des ersten untergeordneten Themas angezeigt.


## Konfigurieren von Regeln zur Bereinigung von Dateinamen zum Erstellen von Themen und Veröffentlichen von Ausgaben in AEM Sites und anderen Formaten {#id2164D0KD0XA}

Als Admin können Sie eine Liste gültiger Sonderzeichen definieren, die in Dateinamen zulässig sind, welche schließlich die URL einer AEM Site-Ausgabe bilden. In früheren Versionen durften Benutzende Dateinamen definieren, die Sonderzeichen wie `@`, `$`, `>` und mehr enthalten. Diese Sonderzeichen führten zu einer kodierten URL bei der Erstellung von AEM Site-Seiten.

Ab Version 3.8 wurden Konfigurationen hinzugefügt, um eine Liste von Sonderzeichen zu definieren, die in den Dateinamen zulässig sind. Standardmäßig enthält die gültige Dateinamenkonfiguration &quot;`a-z A-Z 0-9 - _`&quot;. Dies bedeutet, dass Sie beim Erstellen einer Datei jedes Sonderzeichen im Titel der Datei haben können, aber intern wird es durch einen Bindestrich \(`-`\) im Dateinamen ersetzt. Beispielsweise können Sie den Titel der Datei als Einführung 1 oder Introduction@1 haben. Der entsprechende Dateiname, der für diese beiden Fälle generiert wird, wäre Einführung-1.

Beachten Sie beim Definieren einer Liste gültiger Zeichen, dass diese Zeichen &quot;`*/:[\]|#%{}?&<>"/+`&quot; und `a space` immer durch einen Bindestrich \(`-`\) ersetzt werden.

>[!NOTE]
>
> Wenn Sie die Liste der gültigen Sonderzeichen nicht konfigurieren, kann der Prozess der Dateierstellung zu unerwarteten Ergebnissen führen.

Die folgenden Registerkarten enthalten Anweisungen zum Konfigurieren der gültigen Sonderzeichen in Dateinamen und der AEM-Site-Ausgabe basierend auf Ihrer Experience Manager Guides-Einrichtung: Cloud Service oder On-Premise.

>[!BEGINTABS]

>[!TAB Cloud Service]

Verwenden Sie die Anweisungen unter [Konfigurationsüberschreibungen](download-install-config-override.md#), um die Konfigurationsdatei zu erstellen. Geben Sie in der Konfigurationsdatei die folgenden \(property\)-Details an, um die gültigen Sonderzeichen in Dateinamen und AEM Site-Ausgaben zu konfigurieren:

| PID | Eigenschaftsschlüssel | Eigenschaftswert |
|---|------------|--------------|
| `com.adobe.fmdita.common.SanitizeNodeNameImpl` | `aemsite.DisallowedFileNameChars` | Stellen Sie sicher, dass die Eigenschaft auf ``'<>`@$`` gesetzt ist. Sie können dieser Liste weitere Sonderzeichen hinzufügen. |

>[!NOTE]
> 
> Die obige Konfiguration gilt für alle Ausgabeformate. Das bedeutet, dass beim Generieren einer PDF-, HTML- oder benutzerdefinierten Ausgabe die konfigurierten Regeln zur Bereinigung von Dateinamen für die endgültige Ausgabe gelten.

Sie können auch die anderen Eigenschaften konfigurieren, z. B. Kleinbuchstaben in Dateinamen, Trennzeichen zur Verarbeitung ungültiger Zeichen und die maximale Anzahl von in den Dateinamen zulässigen Zeichen. Um diese Eigenschaften zu konfigurieren, fügen Sie die folgenden Schlüsselwertpaare in der Konfigurationsdatei hinzu:

| Eigenschaftsschlüssel | Eigenschaftswert |
|------------|--------------|
| `nodename.uselower` | Boolescher Wert \(true/false\).<br> **Standardwert**: true |
| `nodename.separator` | Beliebiges Zeichen. <br> **Standardwert**: \_ *\(Unterstrich\)* |
| `nodename.maxlength` | Ganzzahliger Wert.<br> **Standardwert**: 50 |

>[!TAB On-Premise]

1. Öffnen Sie die Seite Konfiguration der Adobe Experience Manager-Web-Konsole .

   Die Standard-URL für den Zugriff auf die Konfigurationsseite lautet:

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Suchen Sie nach dem Bundle *com.adobe.fmdita.common.SanitizeNodeNameImpl* und klicken Sie darauf.

1. Stellen Sie in der **Nicht zulässiger Zeichensatz für die Veröffentlichung in AEM Sites** sicher, dass die Eigenschaft auf ```'<>`@$``` festgelegt ist. Sie können dieser Liste weitere Sonderzeichen hinzufügen. Sie muss jedoch diese erforderlichen Sonderzeichen enthalten.

   >[!NOTE]
   >
   > Sie können auch die anderen Eigenschaften wie **Kleinbuchstaben verwenden** in Dateinamen, **Trennzeichen** zur Verarbeitung ungültiger Zeichen und **Maximale Zeichenanzahl** in den Dateinamen zulassen.

1. Klicken Sie auf **Speichern**.

1. Suchen Sie nach dem Bundle **com.adobe.fmdita.config.ConfigManager** und klicken Sie darauf.

1. Stellen Sie in **Eigenschaft „Regex für gültige**&quot; sicher, dass die Eigenschaft auf &quot;`[-a-zA-Z0-9_]`&quot; festgelegt ist. Sie können dieser Liste weitere Zeichen hinzufügen. Sie muss jedoch diese grundlegenden Zeichen enthalten und die Liste muss mit einem Bindestrich \(`-`\) beginnen.

   >[!NOTE]
   >
   > Diese Eigenschaft definiert die Liste der gültigen Zeichen, die zum Erstellen einer neuen Datei verwendet werden.

1. Klicken Sie auf **Speichern**.

>[!ENDTABS]

## Konfigurieren des Reduzierens der Knotenstruktur der AEM-Site

Wenn Sie die Ausgabe der AEM-Site generieren, wird intern ein Knoten für jedes Element in den Themen erstellt. Bei einer DITA-Zuordnung mit Tausenden von Themen kann diese Knotenstruktur zu tief werden. Dieser Typ einer tief verschachtelten Knotenstruktur kann bei größeren Sites zu Leistungsproblemen führen. Der folgende Schnappschuss zeigt eine tief verschachtelte Knotenstruktur für eine AEM Site-Ausgabe:

![](assets/deep-nested-aem-site-node-structure.png)

Beachten Sie, dass im obigen Schnappschuss für jedes `p` Element und seine nachfolgenden Unterelemente ein Knoten erstellt wird und für jedes andere Element, das im Thema verwendet wird, eine ähnliche Struktur erstellt wird.

Mit AEM Guides können Sie konfigurieren, wie die Knotenstruktur der AEM-Site-Ausgabe intern erstellt wird. Sie können die Knotenstruktur an bestimmten Elementen reduzieren, was bedeutet, dass Sie ein Element definieren können, das als Hauptelement betrachtet wird, und alle darin enthaltenen Unterelemente mit dem Hauptelement zusammengeführt werden. Wenn Sie sich beispielsweise entscheiden, das `p` zu reduzieren, werden alle Elemente, die im `p` Element erscheinen, mit dem `p` zusammengeführt. Für kein Unterelement im `p` wird eine separate Anmerkung erstellt. Die folgende Momentaufnahme zeigt die an `p` Element reduzierte Knotenstruktur:

![](assets/flattened-aem-site-node-structure.png)

Die folgenden Registerkarten enthalten Anweisungen zum Reduzieren der Knotenstruktur der AEM-Site basierend auf Ihrer Experience Manager Guides-Einrichtung: Cloud Service oder On-Premise.

>[!BEGINTABS]

>[!TAB Cloud Service]

1. Identifizieren Sie die Elemente, an denen Sie die Knotenstruktur reduzieren möchten:

1. Überlagern Sie den Knoten `libs` im Knoten `apps` und öffnen Sie die Datei elementmapping.xml.

1. Fügen Sie die `<flatten>true</flatten>` -Eigenschaft in der Definition des Elements hinzu, bei dem Sie die Knotenstruktur reduzieren möchten. Wenn Sie beispielsweise die Knotenstruktur am `p` reduzieren möchten, fügen Sie in der Definition `p` Elements das Attribut „flat“ hinzu, wie unten dargestellt:

   ```XML
   <ditaelement>
         <name>p</name>
         <class>- topic/p</class>
         <componentpath>fmdita/components/dita/wrapper</componentpath>
         <type>COMPOSITE</type>
         <target>para</target>
         <flatten>true</flatten>
         <wrapelement>div</wrapelement>
      </ditaelement>
   ```

   >[!NOTE]
   >
   > Standardmäßig wurde die Knoteneigenschaft „Reduzieren“ im `p` konfiguriert.

1. Verwenden Sie die Anweisungen unter [Konfigurationsüberschreibungen](download-install-config-override.md#), um die Konfigurationsdatei zu erstellen.
1. Geben Sie in der Konfigurationsdatei die folgenden \(property\)-Details an:

   | PID | Eigenschaftsschlüssel | Eigenschaftswert |
   |---|------------|--------------|
   | `com.adobe.dxml.flattening.FlatteningConfigurationService` | `flattening.enabled` | Boolescher Wert \(true/false\).<br> **Standardwert**: `false` |


Wenn Sie jetzt die Ausgabe der AEM-Site generieren, werden die Knoten im `p` reduziert und im `p` selbst gespeichert. Sie finden die neuen Reduzierungseigenschaften für das `p` in CRXDE.

![](assets/flatten-aem-site-note-props-crxde.png)

>[!TAB On-Premise]

1. Geben Sie das Element an, bei dem Sie die Knotenstruktur reduzieren möchten.

   1. Überlagern Sie den Knoten `libs` im Knoten `apps` und öffnen Sie die Datei elementmapping.xml.

   1. Fügen Sie die `<flatten>true</flatten>` -Eigenschaft in der Definition des Elements hinzu, bei dem Sie die Knotenstruktur reduzieren möchten. Wenn Sie beispielsweise die Knotenstruktur am `p` reduzieren möchten, fügen Sie in der Definition `p` Elements das Attribut „flat“ hinzu, wie unten dargestellt:

      ```XML
      <ditaelement>
          <name>p</name>
          <class>- topic/p</class>
          <componentpath>fmdita/components/dita/wrapper</componentpath>
          <type>COMPOSITE</type>
          <target>para</target>
          <flatten>true</flatten>
          <wrapelement>div</wrapelement>
      </ditaelement>
      ```

      >[!NOTE]
      >
      > Standardmäßig wurde die Knoteneigenschaft „Reduzieren“ im `p` konfiguriert.

1. Aktivieren Sie im configMgr die Konfiguration zum Reduzieren von Siteknoten .

   1. Öffnen Sie die Seite Konfiguration der Adobe Experience Manager-Web-Konsole .

      Die Standard-URL für den Zugriff auf die Konfigurationsseite lautet:

      ```http
      http://<server name>:<port>/system/console/configMgr
      ```

   1. Suchen Sie nach dem Bundle *com.adobe.dxml.flatting.FlattlingConfigurationService* und klicken Sie darauf.

   1. Wählen Sie die Option **Eigenschaft reduzieren.aktiviert** aus.

   1. Klicken Sie auf **Speichern**.


>[!IMPORTANT]
>
> Wenn Sie Änderungen an der Datei „elementmapping.xml“ vorgenommen haben, stellen Sie sicher, dass Sie den configMgr öffnen und alle Bundles speichern, damit Änderungen wirksam werden.

Wenn Sie jetzt die Ausgabe der AEM-Site generieren, werden die Knoten im `p` reduziert und im `p` selbst gespeichert. Sie finden die neuen Reduzierungseigenschaften für das `p` in CRXDE.

![](assets/flatten-aem-site-note-props-crxde.png){width="650" align="left"}

>[!ENDTABS]

**Suchen einer Zeichenfolge innerhalb des Inhalts in der Ausgabe der AEM-Site (nur für Cloud Service)**

Standardmäßig können Sie in den Titeln nur innerhalb der AEM-Site-Ausgabe nach einer Zeichenfolge suchen. Sie können das System so konfigurieren, dass sowohl in den Titeln als auch im Inhalt oder Hauptteil der AEM-Site-Ausgabe nach einer Zeichenfolge gesucht wird.

>[!NOTE]
>
> Manchmal funktioniert Ihre Suche möglicherweise für einige Elemente im Inhalt, aber Sie können sie so konfigurieren, dass sie für den gesamten Inhalt funktioniert.

![](assets/flatten-aem-site-note-props-crxde-search.png)

Um die Suche zu aktivieren, sollten Sie die Reduzierung der Knotenstruktur der AEM-Site konfigurieren.

VORSICHT:

Sie können bis zu 1 MB reduzierten Inhalt durchsuchen. Beispielsweise können Sie im vorherigen Screenshot suchen, ob der Inhalt unter dem Tag &lt;p\> &lt;= 1 MB beträgt.

>[!NOTE]
>
> Die Suche funktioniert nur dann für die Elemente, wenn das `<flatten>`Attribut auf „true“ gesetzt ist. Standardmäßig ist das `<flatten>`-Attribut von AEM Guides für häufig verwendete Textelemente wie &lt;p\> &lt;ul\> &lt;lI\> auf „true“ gesetzt. Wenn Sie jedoch einige benutzerdefinierte Elemente erstellt haben, sollten Sie das `<flatten>`-Attribut in der Datei elementmapping.xml auf „true“ setzen.

**Reduzieren der Knotenstruktur der AEM-Site verhindern**

Ähnlich wie bei Angabe des Knotens, der in der AEM-Site-Ausgabe reduziert werden soll, können Sie auch ein Element angeben, das Sie aus dieser Konfiguration ausschließen möchten. Wenn Sie beispielsweise Knoten an `body` Element reduzieren möchten, aber kein `table` Element in `body` reduzieren möchten, können Sie die Eigenschaft „exclude“ zur Definition des `table` hinzufügen.

Um das `table`-Element von der Reduzierung auszuschließen, fügen Sie die folgende Eigenschaft zur Definition des `table`-Elements hinzu:

`<preventancestorflattening>true|false</preventancestorflattening>`

## Konfigurieren der Versionierung für gelöschte Seiten in der AEM Site-Ausgabe

Beim Generieren der AEM-Site **Ausgabe mit der Option** Löschen und ****Erstellen) für die Einstellung Vorhandene Ausgabeseiten wird eine Version für die zu löschenden Seiten erstellt. Sie können das System so konfigurieren, dass die Erstellung einer Version vor dem Löschen gestoppt wird.

Die folgenden Registerkarten enthalten Anweisungen, um die Erstellung einer Version für die Seite(n) zu stoppen, die auf der Grundlage Ihrer Experience Manager Guides-Einrichtung gelöscht wird: Cloud Service oder On-Premise.

>[!BEGINTABS]

>[!TAB Cloud Service]

1. Verwenden Sie die Anweisungen unter [Konfigurationsüberschreibungen](download-install-config-override.md#), um die Konfigurationsdatei zu erstellen.
1. Geben Sie in der Konfigurationsdatei die folgenden \(property\)-Details an, um die Option **Keine Version für gelöschte Seiten erstellen** zu konfigurieren:

   | PID | Eigenschaftsschlüssel | Eigenschaftswert |
   |---|------------|--------------|
   | `com.adobe.fmdita.confi g.ConfigManager` | `no.version.creation.on.deletion` | Boolescher Wert \(true/false\).<br> **Standardwert**: `true` |

   >[!NOTE]
   >
   > Wenn diese Option aktiviert ist, können Benutzer alle Seiten direkt löschen, ohne eine Version für sie zu erstellen. Wenn die Option nicht ausgewählt ist, wird eine Version erstellt, bevor die Seite(n) gelöscht werden.

>[!TAB On-Premise]

1. Öffnen Sie die Seite Konfiguration der Adobe Experience Manager-Web-Konsole .

   Die Standard-URL für den Zugriff auf die Konfigurationsseite lautet:

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Suchen Sie nach dem Bundle *com.adobe.fmdita.config.ConfigManager* und klicken Sie darauf.

1. Wählen Sie **Option Keine Version für gelöschte Seiten erstellen**.

   >[!NOTE]
   >
   > Wenn diese Option aktiviert ist, können Benutzer alle Seiten direkt löschen, ohne eine Version für sie zu erstellen. Wenn die Option nicht ausgewählt ist, wird eine Version erstellt, bevor die Seite(n) gelöscht werden.

1. Klicken Sie auf **Speichern**.

>[!ENDTABS]

## Einrichten eines benutzerdefinierten Rewriters mit Experience Manager Guides (nur für Cloud Service) {#custom-rewriter}

Experience Manager Guides verfügt über ein benutzerdefiniertes Sling [**Rewriter**](https://sling.apache.org/documentation/bundles/output-rewriting-pipelines-org-apache-sling-rewriter.html)-Modul für die Verarbeitung der Links, die bei Kreuzzuordnungen (Verknüpfungen zwischen den Themen zweier verschiedener Zuordnungen) generiert werden. Diese Rewriter-Konfiguration wird unter dem folgenden Pfad installiert: <br> `/apps/fmdita/config/rewriter/fmdita-crossmap-link-patcher`.

Wenn Sie einen anderen benutzerdefinierten Sling Rewriter in Ihrer Codebasis haben, verwenden Sie einen `'order'` Wert größer als 50, da der Experience Manager Guides Sling Rewriter `'order'` 50 verwendet.  Um dies zu überschreiben, benötigen Sie einen Wert >50 . Weitere Informationen finden Sie unter [Output-Umschreibungs-Pipelines](https://sling.apache.org/documentation/bundles/output-rewriting-pipelines-org-apache-sling-rewriter.html).



