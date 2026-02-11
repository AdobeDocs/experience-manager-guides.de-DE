---
title: Migrieren von Nicht-DITA-Inhalten
description: Erfahren Sie, wie Sie Nicht-DITA-Inhalte migrieren
exl-id: 4597d1be-5426-4eba-8490-e42d0e565427
feature: Migration
role: Admin
level: Experienced
source-git-commit: d3b156b8617cab8cf0702a483aef0fde7889e6a7
workflow-type: tm+mt
source-wordcount: '2351'
ht-degree: 0%

---

# Migrieren von Nicht-DITA-Inhalten {#id181AH0R02HT}

Dieser Abschnitt führt Sie durch den Migrationsprozess, um Nicht-DITA-Dokumente in das DITA-Format zu migrieren. AEM Guides ermöglicht die Migration aus den folgenden Quellen:

- [Microsoft Word](#id1949B040Z5Z)

- [InDesign-Dokumente](#id195AD0B0K5Z)

- [XHTML](#id1949B04L0Y4)

- [Nicht strukturierte FrameMaker-Dokumente](#id1949B050VUI)

- [Alle anderen strukturierten Dokumente](#id1949B0590YK)


## Migrieren von Microsoft Word-Dokumenten {#id1949B040Z5Z}

Mit AEM Guides können Sie Ihre vorhandenen Word-Dokumente \(`.docx`\) in DITA-Themendokumente migrieren. Sie müssen die Speicherorte der Eingabe- und Ausgabeordner zusammen mit anderen Parametern angeben, und das Dokument wird in ein DITA-Dokument konvertiert. Je nach Inhalt können Sie über eine DITA-Datei und eine DITAMAP-Datei verfügen.

Um ein Word-Dokument erfolgreich konvertieren zu können, sollte Ihr Dokument gut strukturiert sein. Ihr Dokument sollte beispielsweise einen Titel haben, gefolgt von Überschrift 1, Überschrift 2 usw. Jede der Überschriften sollte etwas Inhalt enthalten. Wenn Ihr Dokument nicht gut strukturiert ist, funktioniert der Prozess möglicherweise nicht wie erwartet.

Standardmäßig verwendet AEM Guides das [Word-to-DITA \(Word2DITA\)-](http://www.dita4publishers.org/docs/repo/org.dita4publishers.word2dita/word2dita/word2dita-intro.html). Diese Umwandlung hängt von der Konfigurationsdatei [style-to-tag-](http://www.dita4publishers.org/docs/repo/org.dita4publishers.word2dita/word2dita/style-to-tag-map-overview.html)&quot; ab. Um die Word2DITA-Transformation erfolgreich verwenden zu können, müssen Sie die folgenden Richtlinien beachten, um Ihr Word-Dokument für die Konvertierung vorzubereiten:

>[!NOTE]
>
> Wenn Sie Änderungen an der standardmäßigen Stil-zu-Tag-Zuordnungskonfigurationsdatei vornehmen, müssen Sie die Richtlinien aktualisieren und verwenden, um Ihre aktualisierte Stilzuordnung zu bestätigen.

- Stellen Sie sicher, dass Ihr Dokument mit einem Titel beginnt. Dieser Titel wird dem DITA-Zuordnungstitel zugeordnet. Außerdem muss auf den Titel ein regulärer Inhalt folgen.

- Nach dem Titel sollte es Überschrift 1, Überschrift 2 usw. geben. Jede Überschrift muss etwas Inhalt enthalten. Die Überschriften werden in neue Themen vom Typ Konzept konvertiert. Die Hierarchie der generierten Themen entspricht den Überschriftenebenen im Dokument, z. B. wird Überschrift 1 Überschrift 2 und Überschrift 2 dem Inhalt der Überschrift 3 vorangestellt.

- Das Dokument muss mindestens einen Überschrifttyp-Inhalt haben.

- Stellen Sie sicher, dass Sie keine Bilder gruppiert haben. Heben Sie die Gruppierung aller Bilder auf, falls Sie diese Bilder im Dokument gruppiert haben.

- Entfernen Sie alle Kopf- und Fußzeilen.

- Inline-Stile wie fett, kursiv und unterstrichen werden in `b`-, `i`- und `u`-Elemente konvertiert.

- Alle sortierten und nicht sortierten Listen werden in `ol` und `ul` Elemente konvertiert. Dies gilt auch für verschachtelte Listen, Listen in Tabellen, Notizen oder Fußnoten.

- Alle Hyperlinks werden in `xref` umgewandelt.

- Der Dateiname der konvertierten Dateien basiert auf dem Überschrifttext gefolgt von einer Dateinummer. Die Dateinummer ist eine sequenzielle Zahl, die auf der Position des Überschriftentextes im Dokument basiert. Wenn beispielsweise ein Überschrifttext „Beispielüberschrift“ lautet und im Dokument die zehnte Überschrift ist, ähnelt der resultierende Dateiname für dieses Thema Sample\_Heading\_10.dita.


Führen Sie die folgenden Schritte aus, um Ihre vorhandenen Word-Dokumente in ein Dokument vom Typ DITA-Thema zu konvertieren:

1. Melden Sie sich bei AEM an und öffnen Sie den CRXDE Lite-Modus.

1. Navigieren Sie zu der standardmäßigen Konfigurationsdatei, die am folgenden Speicherort verfügbar ist:

   `/libs/fmdita/config/w2d_io.xml`

1. Erstellen Sie einen Überlagerungsknoten des `config` Ordners im `apps`.

1. Navigieren Sie zu der Konfigurationsdatei, die im Knoten `apps` verfügbar ist:

   `/apps/fmdita/config/w2d_io.xml`

   Die `w2d_io.xml`-Datei enthält die folgenden konfigurierbaren Parameter:

   - Geben Sie im `inputDir`-Element den Speicherort des Eingabeordners an, in dem Ihre Word-Quelldokumente verfügbar sind. Wenn Ihre Word-Dokumente beispielsweise in einem Ordner mit dem Namen `wordtodita` in `projects` Ordner gespeichert sind, geben Sie den Speicherort wie folgt an: `/content/dam/projects/wordtodita/`

   - Geben `outputDir` im Element den Speicherort des Ausgabeordners an oder behalten Sie den standardmäßigen Ausgabespeicherort bei, um das konvertierte DITA-Dokument zu speichern. Wenn der angegebene Ausgabeordner nicht in DAM vorhanden ist, erstellt der Konvertierungs-Workflow den Ausgabeordner.

   - Geben Sie für das `createRev` an, ob eine neue Version des konvertierten DITA-Themas erstellt werden soll \(`true`\) oder nicht \(`false`\).

   - Geben Sie im `s2tMap`-Element den Speicherort der Zuordnungsdatei an, die Zuordnungen von Word-Dokumentstilen zu DITA-Elementen enthält. Die Standardzuordnung wird in der Datei gespeichert, die sich unter befindet:

     ```XML
     /libs/fmdita/word2dita/word-builtin-styles-style2tagmap.xml
     ```

     >[!NOTE]
     >
     > Weitere Informationen zur Struktur `word-builtin-styles-style2tagmap.xml` Datei und dazu, wie Sie sie anpassen können, finden Sie unter [Stil für Tag-](http://www.dita4publishers.org/docs/repo/org.dita4publishers.word2dita/word2dita/style-to-tag-map-overview.html)&quot; im *DITA für Herausgeber-Benutzerhandbuch*.

   - Geben Sie im props2propagate-Element die Eigenschaften an, die an die DITA-Zuordnung übergeben werden sollen. Diese Eigenschaft ist erforderlich, um die Standard-Metadaten wie dc:title,dc:subject,dam:keywords,dam:category von Dokumentmetadaten an konvertierte DITA-Assets zu übergeben.

1. Speichern Sie die `w2d_io.xml`-Datei.

1. Melden Sie sich nach dem Konfigurieren der erforderlichen Parameter in der `w2d_io.xml` bei AEM an und öffnen Sie die Assets-Benutzeroberfläche.

1. Navigieren Sie zum Speicherort des Eingabeordners \(`wordtodita`\).

1. Laden Sie die Word-Quelldokumente in diesen Ordner hoch. Informationen zum Hochladen von Inhalten in DAM finden Sie unter [Vorhandenen DITA-Inhalt hochladen](migrate-content-upload-existing-dita-content.md#).


Mit dem `config` `/config` können Sie einen oder mehrere Konfigurationsblöcke für die Konvertierung definieren. Der Konvertierungs-Workflow wird ausgeführt und die endgültige Ausgabe in Form eines DITA-Themas wird an dem im `outputDir` angegebenen Speicherort gespeichert.

## Migrieren von Adobe InDesign-Dokumenten {#id195AD0B0K5Z}

Mit AEM Guides können Sie InDesign-Dokumente konvertieren. Ähnlich wie FrameMaker ermöglicht InDesign auch die Erstellung unstrukturierter und strukturierter Dokumente. Die unstrukturierten Dokumente verwenden die Absatz- und Zeichenstile zum Formatieren von Inhalten. Das strukturierte Dokument verwendet Elemente und die entsprechenden Attribute.

Für den Konvertierungsprozess müssen die Absatz- und Zeichenformate den entsprechenden DITA-Elementen zugeordnet werden. Ebenso enthält die Zuordnungsdatei bei strukturierten Dokumenten eine Eins-zu-eins-Zuordnung von InDesign-Elementen und -Attributen zu DITA-Elementen und -Attributen.

Der Konvertierungsprozess umfasst die folgenden Aktionen im Backend:

- Die Datei *InDesign Markup Language* \(IDML\) wird in ein Arbeitsverzeichnis entpackt.
- Die Datei „designmap.xml“ wird gelesen, um die einzelnen InDesign-Storys zu finden.
- Alle Storys werden in einer einzigen XML-Instanz zusammengeführt, „leere“ Storys werden verworfen.
- Alle eingebetteten Grafiken werden exportiert.
- Vorkonvertierung von Standardstrukturen wie Tabellen und Grafiken in das DITA-Format.
- Stil- oder Strukturzuordnung zur endgültigen Ausgabe basierend auf der Zuordnungsdatei.
- Erstellung und Validierung einzelner DITA-Themen und DITA-Zuordnungsdateien.
- Löschen temporärer Dateien.

Im Allgemeinen erfordert der Konvertierungsprozess, dass Sie [InDesign-Dateien für die Konvertierung vorbereiten](appendix.md#id195DBF0045Z) und [die Zuordnungsdatei für die Migration von InDesign zu DITA vorbereiten](appendix.md#id194AF0003HT) dann müssen Sie das angegebene Verfahren zum Ausführen des Konvertierungsprozesses befolgen.

Führen Sie die folgenden Schritte aus, um Ihre bestehenden InDesign-Dokumente in ein Dokument vom Typ DITA-Thema zu konvertieren:

1. Melden Sie sich bei AEM an und öffnen Sie den CRXDE Lite-Modus.

1. Navigieren Sie zu der standardmäßigen Konfigurationsdatei, die am folgenden Speicherort verfügbar ist:

   `/libs/fmdita/config/idml2dita_io.xml`

1. Um eine benutzerdefinierte Konfiguration entsprechend Ihren Anforderungen zu erstellen, erstellen Sie einen Überlagerungsknoten des `config` im `apps`.

1. Kopieren Sie die folgenden Dateien oder Ordner aus dem Ordner &quot;`libs`&quot; in den Ordner „Programme“:

   - `/fmdita/config/idml2dita_io.xml`
   - `/fmdita/idml2dita/config`
   - `/fmdita/idml2dita/xsl`

1. Navigieren Sie zu der Konfigurationsdatei, die im Knoten `apps` verfügbar ist:

   `/apps/fmdita/config/idml2dita_io.xml`

1. Fügen Sie in der `idml12dita`-Datei die Zuordnung der Konfigurationen hinzu, die im Ordner `idml2dita_io.xml` vorhanden sind.
1. Fügen Sie in `idml2dita_io.xml` Datei die folgenden Eigenschaften hinzu:

   ```
   <entry key="idml2DitaConfig">/apps/fmdita/idml2dita/config</entry>
   
   <entry key="idml2DitaXsl">/apps/fmdita/idml2dita/xsl</entry>
   ```

Konfigurieren Sie die folgenden Parameter in der `idml2dita_io.xml`:

- Geben Sie im `inputDir` den Speicherort des Eingabeordners an, in dem Ihre InDesign-Quelldokumente verfügbar sind. Wenn Ihre InDesign-Dokumente beispielsweise in einem Ordner mit dem Namen &quot;`indesigntodita`&quot; `projects` Ordner gespeichert sind, geben Sie den Speicherort wie folgt an: `/content/dam/idmlfiles/indesigntodita/`

- Geben `outputDir` im Element den Speicherort des Ausgabeordners an oder behalten Sie den standardmäßigen Ausgabespeicherort bei, um das konvertierte DITA-Dokument zu speichern. Wenn der angegebene Ausgabeordner nicht in DAM vorhanden ist, erstellt der Konvertierungs-Workflow den Ausgabeordner.

- Geben Sie im `mapStyle` den Speicherort der Zuordnungsdatei an, die Zuordnungen von InDesign-Dokumentstilen zu DITA-Elementen enthält. Die Standardzuordnung wird in der Datei gespeichert, die sich unter befindet:

```XML
    /stmap.adobeidml.xml
```

>[!NOTE]
>
> Weitere Informationen zur Dateistruktur und `stmap.adobeidml.xml` Möglichkeit, sie anzupassen, finden Sie im Abschnitt [Vorbereiten der Zuordnungsdatei für die Migration von InDesign zu DITA](appendix.md#id194AF0003HT) in *Anhang*.

1. Speichern Sie die `idml2dita_io.xml`-Datei.

1. Melden Sie sich nach dem Konfigurieren der erforderlichen Parameter in der `idml2dita_io.xml` bei AEM an und öffnen Sie die Assets-Benutzeroberfläche.

1. Navigieren Sie zum Speicherort des Eingabeordners \(`indesigntodita`\).

1. Laden Sie die InDesign-Quelldokumente in diesen Ordner hoch. Informationen zum Hochladen von Inhalten in DAM finden Sie unter [Vorhandenen DITA-Inhalt hochladen](migrate-content-upload-existing-dita-content.md#).


## Migrieren von XHTML-Dokumenten {#id1949B04L0Y4}

Mit AEM Guides können Sie Ihre vorhandenen XHTML-Dokumente in Dokumente vom Typ „DITA-Thema“ konvertieren. Sie müssen die Speicherorte der Eingabe- und Ausgabeordner zusammen mit anderen Parametern angeben, und die Dokumente werden in das DITA-Format konvertiert. Es gibt zwei Methoden, mit denen Sie Ihre strukturierten HTML-Dokumente konvertieren können:

- alle Dokumente in den Eingabeordner hochladen oder
- Erstellen Sie eine ZIP-Datei aller Dokumente zusammen mit den Mediendateien und laden Sie sie in den Eingabeordner hoch. Dieser Ansatz wird im Allgemeinen für eine Reihe von HTML-Dateien verwendet, die miteinander verknüpft sind und es eine Inhaltsverzeichnisdatei \(index.html\) gibt. Die Datei index.html enthält Links zu allen HTML-Dateien im Set.

Unabhängig davon, ob Sie alle Dateien einzeln oder gebündelt in eine ZIP-Datei hochladen, erstellt der Konvertierungsprozess eine Eins-zu-eins-Zuordnung zwischen den HTML-Dateien und den resultierenden DITA-Dateien. Dies bedeutet, dass im Eingabeordner für jede HTML-Datei eine DITA-Datei erstellt wird.

Folgende Punkte müssen beim Hochladen Ihrer Dokumente in einer ZIP-Datei berücksichtigt werden:

- Alle referenzierten Themen sollten in der ZIP-Datei platziert werden.

- Alle referenzierten Mediendateien sollten innerhalb der Themendateien mit relativem Link referenziert werden.

- Erstellen Sie eine Datei „index.html“ und fügen Sie Links zu Themen hinzu, die Sie dem Inhaltsverzeichnis hinzufügen möchten. Diese Datei „index.html“ wird verwendet, um die DITA-Zuordnungsdatei zu erstellen. In der Datei index.html können Sie auch eine verschachtelte Themenliste erstellen, wie im folgenden Codebeispiel gezeigt:

  ```XML
  <?xml version="1.0" encoding="UTF-8"?>
  <html
  xmlns="http://www.w3.org/1999/xhtml">
      <head>
          <title>Sample Index File</title>
      </head>
      <body>
          <h1>Sample Index</h1>
          <div class="content">
              <ul class="book">
                  <li class="topicref">
                      <a href="Topic1.html">Topic 1</a>
                      <ul class="book">
                          <li class="topicref">
                              <a href="Topic1-1.html">Topic 1.1</a>
                          </li>
                          <li class="topicref">
                              <a href="Topic1-2.html">Topic 1.2</a>
                          </li>
                      </ul>
                  </li>
                  <li class="topicref">
                      <a href="Topic2.html">Topic 2</a>
                  </li>
              </ul>
          </div>
      </body>
  </html>
  ```

  Beachten Sie, dass für jedes `ul`-Tag das `class`-Attribut auf `book` festgelegt sein muss. Ebenso muss die `li` jedes `class`-Tags auf `topicref` gesetzt werden.

- Wenn Sie Inline-Stile verwenden, konvertieren Sie die Inline-Stile in Ihrer XHTML-Datei in CSS-basierte Stilklassen. Verwenden Sie dann die Stilattributzuordnung, um diese klassenbasierten Stile in der konvertierten DITA-Datei in das DITA-`outputclass`-Attribut zu konvertieren.

  Beim Generieren der HTML- oder AEM-Site-Ausgabe aus diesen DITA-Dateien können die `outputclass`-Attribute verwendet werden, um auf generierte HTML- oder AEM-Site Stilklassen anzuwenden, die mit Ihren HTML-Quellinhalten übereinstimmen.


Abgesehen von den Überlegungen zum Erstellen der ZIP-Datei muss Ihr XHTML-Dokument auch gut strukturiert sein. Ihr Dokument sollte beispielsweise über einen *Titel* gefolgt von *Überschrift 1*, *Überschrift 2* usw. verfügen. Jede der Überschriften sollte etwas Inhalt enthalten. Wenn Ihr Dokument nicht gut strukturiert ist, funktioniert der Migrationsprozess möglicherweise nicht wie erwartet.

Führen Sie die folgenden Schritte aus, um Ihr vorhandenes XHTML-Dokument in DITA-Thema zu konvertieren:

1. Melden Sie sich bei AEM an und öffnen Sie den CRXDE Lite-Modus.

1. Navigieren Sie zu der standardmäßigen Konfigurationsdatei, die am folgenden Speicherort verfügbar ist:

   `/libs/fmdita/config/h2d_io.xml`

1. Erstellen Sie einen Überlagerungsknoten des `config` Ordners im `apps`.

1. Navigieren Sie zu der Konfigurationsdatei, die im Knoten `apps` verfügbar ist:

   `/apps/fmdita/config/h2d_io.xml`

   Die `h2d_io.xml`-Datei enthält die folgenden konfigurierbaren Parameter:

   - Geben Sie im `inputDir`-Element den Speicherort Ihres Eingabeordners an, in dem Ihre Quell-XHTML-Dokumente verfügbar sind. Wenn Ihre XHTML-Dokumente beispielsweise in einem Ordner mit dem Namen `xhtmltodita` in `projects` Ordner gespeichert sind, geben Sie den Speicherort wie folgt an: `/content/dam/projects/xhtmltodita/`

   - Geben `outputDir` im Element den Speicherort des Ausgabeordners an oder behalten Sie den standardmäßigen Ausgabespeicherort bei. Wenn der angegebene Ausgabeordner nicht in DAM vorhanden ist, erstellt der Konvertierungs-Workflow den Ausgabeordner.

   - Geben Sie für das `createRev` an, ob eine neue Version des konvertierten DITA-Themas erstellt werden soll \(`true`\) oder nicht \(`false`\).

1. Speichern Sie die `h2d_io.xml`-Datei.

1. Melden Sie sich nach dem Konfigurieren der erforderlichen Parameter in der `h2d_io.xml` bei AEM an und öffnen Sie die Assets-Benutzeroberfläche.

1. *\(Optional\)* Sie können den Abschnitt „Verknüpfungen“ auch zu den konvertierten Dokumenten hinzufügen. Führen Sie die folgenden Schritte aus, um diese Funktion zu aktivieren:

   >[!NOTE]
   >
   > Standardmäßig wird der Abschnitt Verknüpfte Links in den konvertierten Dokumenten nicht erstellt.

   1. Navigieren Sie zur Datei h2d.xsl am folgenden Speicherort:

      /libs/fmdita/html2dita/

   2. Suchen Sie nach dem folgenden Parameter:

      `<xsl:param name="generate-related-links" select="false()"/>`

   3. Setzen Sie den Wert des obigen Parameters auf `true()`.
   4. Speichern und schließen Sie die Datei.
1. Navigieren Sie zum Speicherort des Eingabeordners \(`xhtmltodita`\).

1. Laden Sie die Quell-XHTML-Dokumente in diesen Ordner hoch. Informationen zum Hochladen von Inhalten in DAM finden Sie unter [Vorhandenen DITA-Inhalt hochladen](migrate-content-upload-existing-dita-content.md#).


Mit dem `<config> </config>` können Sie einen oder mehrere Konfigurationsblöcke für die Konvertierung definieren. Der Konvertierungs-Workflow wird ausgeführt und die endgültige Ausgabe in Form eines DITA-Themas wird an dem im `outputDir` angegebenen Speicherort gespeichert.

## Migrieren von unstrukturierten FrameMaker-Dokumenten {#id1949B050VUI}

Mit AEM Guides können Sie Ihre vorhandenen unstrukturierten Dokumente aus FrameMaker \(`.fm` und `.book`\) in DITA-Dokumente konvertieren. Umfassende Informationen zum Prozess finden Sie unter [Migration der technischen Dokumentation von unstrukturierten zu DITA in Adobe FrameMaker](https://migrate-from-unstructured-to-dita-step-by-step-guide.meetus.adobeevents.com/).

<!-- Deprecated information -
 //The first step is to create style mappings using FrameMaker and save those settings in a .sts file. Next, if you are using custom DITA, then you can map your custom elements with the source FrameMaker formats in the `ditaElems.xml` file. For example, if you have created a custom element named `impnote` to handle all important notes, then you can define this custom element in the `ditaElems.xml` file. Once this custom element is defined, AEM Guides would not raise an error while converting FrameMaker document containing `impnote` element.

Also, If you want to specify some additional attributes with your custom or valid DITA element, you can define those in the style2attrMap.xml file. For example, you can specify the `type` attribute with the value of `important` to be passed on with the `impnote` element. This additional information can be specified in the style2attrMap.xml file.

In addition to specifying

To convert your existing unstructured FrameMaker documents into DITA format, perform the following steps:

1.  Create style mappings in FrameMaker and save those settings in a .sts file.

1.  Log into AEM and open the CRXDE Lite mode.

1.  If you have custom DITA elements, define those in the `ditaElems.xml` file available at the following location:

    `/libs/fmdita/config/ditaElems.xml`

1.  Create an overlay node of the `config` folder within the `apps` node.

1.  Navigate to the configuration file available in the `apps` node:

    `/apps/fmdita/config/ditaElems.xml`

    The `ditaElems.xml` file contains a single configurable parameter:

    -   In the `elem` parameter, specify the name of the custom element that you want to use in your converted DITA documents. This element would be passed on as is in the generated DITA documents.

1.  If you want to specify additional attributes, define those in the `style2attrMap.xml` file available at the following location:

    `/libs/fmdita/config/style2attrMap.xml`

1.  Create an overlay node of the `config` folder within the `apps` node.

1.  Navigate to the configuration file available in the `apps` node:

    `/apps/fmdita/config/style2attrMap.xml`

    The `style2attrMap.xml` file contains the following configurable parameters:

    -   In the `fmStyle` parameter, specify the source format used in the FrameMaker document that you want to map.

    -   In the`ditaAttr` element, specify the DITA attribute that you want to map with the source format.

    -   In the `ditaVal` element, specify the value for the mapped attribute. If you don't have any value, you can leave this entry blank.

1.  Save the `style2attrMap.xml` file.

1. After configuring the required parameters in the `style2attrMap.xml` file, log into AEM and open the Assets UI.

1. Navigate to and click on the FrameMaker document that you want to convert.

    The DITA map console appears showing the list of Output Presets available to generate output.

1. Select DITA output format and configure the required parameters.

    >[!NOTE]
    >
    > You must use the same settings file \(.sts\) that you created in FrameMaker. Also, specify the Settings Name and Destination Path.

1. Click the **Generate** icon to start the output generation process.


Using the `<attrMap> </attrMap>` block, you can define one or multiple blocks of configurations for conversion. Depending on the content, you could have a .dita file and a .ditamap file as the converted files.

-->

## Migrieren beliebiger anderer strukturierter Dokumente {#id1949B0590YK}

Mit AEM Guides können Sie Ihre vorhandenen strukturierten Dokumente in gültige DITA-Dokumente konvertieren. Sie müssen die Speicherorte der Eingabe- und Ausgabeordner, den Speicherort der Umwandlungsdatei, die Erweiterung, mit der die endgültige Ausgabe gespeichert wird, und angeben, ob eine neue Version des Dokuments erforderlich ist oder nicht.

Führen Sie die folgenden Schritte aus, um Ihre vorhandenen strukturierten Dokumente in das DITA-Format zu konvertieren:

1. Melden Sie sich bei AEM an und öffnen Sie den CRXDE Lite-Modus.

1. Navigieren Sie zu der standardmäßigen Konfigurationsdatei, die am folgenden Speicherort verfügbar ist:

   `/libs/fmdita/config/XSLConfig.xml`

1. Erstellen Sie einen Überlagerungsknoten des `config` Ordners im `apps`.

1. Navigieren Sie zu der Konfigurationsdatei, die im Knoten `apps` verfügbar ist:

   `/apps/fmdita/config/XSLConfig.xml`

   Die `XSLConfig.xml`-Datei enthält die folgenden konfigurierbaren Parameter:

   - Geben Sie im `inputDir`-Element den Speicherort Ihres Eingabeordners an, in dem Ihre strukturierten Quelldokumente verfügbar sind. Wenn Ihre strukturierten Dokumente beispielsweise in einem Ordner mit dem Namen `xsltodita` in `projects` Ordner gespeichert sind, geben Sie den Speicherort wie folgt an: `/content/dam/projects/xsltodita/`

   - Geben `outputDir` im Element den Speicherort des Ausgabeordners an oder behalten Sie den standardmäßigen Ausgabespeicherort bei. Wenn der angegebene Ausgabeordner nicht in DAM vorhanden ist, erstellt der Konvertierungs-Workflow den Ausgabeordner.

   - Geben Sie im `xslFolder`-Element den Speicherort des Ordners an, in dem die XSL-Umwandlungsdateien gespeichert werden.

   - Geben Sie im ``xslPath``-Element den Speicherort der primären XSL-Datei an, die zum Initiieren des Konvertierungsprozesses verwendet wird.

   - Geben Sie im ``outputExt``-Element die Dateierweiterungen der endgültigen Ausgabedatei an, die aus dem Transformations-Stream erstellt wird.

   - Geben Sie für das `createRev` an, ob eine neue Version des konvertierten DITA-Themas erstellt werden soll \(`true`\) oder nicht \(`false`\).

1. Speichern Sie die `XSLConfig.xml`-Datei.

1. Melden Sie sich nach dem Konfigurieren der erforderlichen Parameter in der `XSLConfig.xml` bei AEM an und öffnen Sie die Assets-Benutzeroberfläche.

1. Navigieren Sie zum Speicherort des Eingabeordners \(`xsltodita`\).

1. Laden Sie die strukturierten Quelldokumente in diesen Ordner hoch. Informationen zum Hochladen von Inhalten in DAM finden Sie unter [Vorhandenen DITA-Inhalt hochladen](migrate-content-upload-existing-dita-content.md#).


Mit dem `<config> </config>` können Sie einen oder mehrere Konfigurationsblöcke für die Konvertierung definieren. Der Konvertierungs-Workflow wird ausgeführt und die endgültige Ausgabe in Form eines DITA-Themas wird an dem im `outputDir` angegebenen Speicherort gespeichert.

**Übergeordnetes Thema:**&#x200B;[&#x200B; Migrieren vorhandener Inhalte](migrate-content.md)
