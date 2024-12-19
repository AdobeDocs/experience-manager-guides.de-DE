---
title: Migrieren von Nicht-DITA-Inhalten
description: Erfahren Sie, wie Sie Nicht-DITA-Inhalte migrieren
exl-id: 4597d1be-5426-4eba-8490-e42d0e565427
feature: Migration
role: Admin
level: Experienced
source-git-commit: 1644bfba3332b0f023aa8d70aefd2680d4220d8a
workflow-type: tm+mt
source-wordcount: '2802'
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

   - Geben Sie im props2propagate-Element die Eigenschaften an, die an die DITA-Zuordnung übergeben werden sollen. Diese Eigenschaft ist erforderlich, um die Standardmetadaten dc:title, dc:subject,dam:keywords,dam:category aus den Dokumentmetadaten in die konvertierten DITA-Assets zu übergeben.

1. Speichern Sie die `w2d_io.xml`-Datei.

1. Melden Sie sich nach dem Konfigurieren der erforderlichen Parameter in der `w2d_io.xml`-Datei bei AEM an und öffnen Sie die Assets-Benutzeroberfläche.

1. Navigieren Sie zum Speicherort des Eingabeordners \(`wordtodita`\).

1. Laden Sie die Word-Quelldokumente in diesen Ordner hoch. Informationen zum Hochladen von Inhalten in DAM finden Sie unter [Vorhandenen DITA-Inhalt hochladen](migrate-content-upload-existing-dita-content.md#).


Mit dem `/config` `config` können Sie einen oder mehrere Konfigurationsblöcke für die Konvertierung definieren. Der Konvertierungs-Workflow wird ausgeführt und die endgültige Ausgabe in Form eines DITA-Themas wird an dem im `outputDir` angegebenen Speicherort gespeichert.

## Migrieren von Adobe InDesign-Dokumenten {#id195AD0B0K5Z}

Mit AEM Guides können Sie InDesign-Dokumente konvertieren. InDesign ermöglicht ähnlich wie FrameMaker auch das Erstellen unstrukturierter und strukturierter Dokumente. Die unstrukturierten Dokumente verwenden die Absatz- und Zeichenstile zum Formatieren von Inhalten. Das strukturierte Dokument verwendet Elemente und die entsprechenden Attribute.

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

Führen Sie die folgenden Schritte aus, um Ihre vorhandenen InDesign-Dokumente in ein DITA-Themendokument zu konvertieren:

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

1. Fügen Sie in der `idml2dita_io.xml`-Datei die Zuordnung der Konfigurationen hinzu, die im Ordner `idml12dita` vorhanden sind.
1. Fügen Sie in `idml2dita_io.xml` Datei die folgenden Eigenschaften hinzu:

   ```
   <entry key="idml2DitaConfig">/apps/fmdita/idml2dita/config</entry>
   
   <entry key="idml2DitaXsl">/apps/fmdita/idml2dita/xsl</entry>
   ```

Konfigurieren Sie die folgenden Parameter in der `idml2dita_io.xml`:

- Geben Sie im `inputDir` den Speicherort des Eingabeordners an, in dem Ihre Quell-InDesign-Dokumente verfügbar sind. Wenn Ihre InDesign-Dokumente beispielsweise in einem Ordner mit dem Namen &quot;`indesigntodita`&quot; `projects` Ordner gespeichert sind, geben Sie den Speicherort wie folgt an: `/content/dam/idmlfiles/indesigntodita/`

- Geben `outputDir` im Element den Speicherort des Ausgabeordners an oder behalten Sie den standardmäßigen Ausgabespeicherort bei, um das konvertierte DITA-Dokument zu speichern. Wenn der angegebene Ausgabeordner nicht in DAM vorhanden ist, erstellt der Konvertierungs-Workflow den Ausgabeordner.

- Geben Sie im `mapStyle` den Speicherort der Zuordnungsdatei an, die Zuordnungen für das InDesign von Dokumentstilen zu DITA-Elementen enthält. Die Standardzuordnung wird in der Datei gespeichert, die sich unter befindet:

```XML
    /stmap.adobeidml.xml
```

>[!NOTE]
>
> Weitere Informationen zur Dateistruktur und dazu, wie Sie `stmap.adobeidml.xml` Datei anpassen können, finden Sie im Abschnitt [Vorbereiten der Zuordnungsdatei für das InDesign zur DITA-](appendix.md#id194AF0003HT) in *Anhang*.

1. Speichern Sie die `idml2dita_io.xml`-Datei.

1. Melden Sie sich nach dem Konfigurieren der erforderlichen Parameter in der `idml2dita_io.xml`-Datei bei AEM an und öffnen Sie die Assets-Benutzeroberfläche.

1. Navigieren Sie zum Speicherort des Eingabeordners \(`indesigntodita`\).

1. Laden Sie die Quell-InDesign-Dokumente in diesen Ordner hoch. Informationen zum Hochladen von Inhalten in DAM finden Sie unter [Vorhandenen DITA-Inhalt hochladen](migrate-content-upload-existing-dita-content.md#).


## Migrieren von XHTML-Dokumenten {#id1949B04L0Y4}

Mit AEM Guides können Sie Ihre vorhandenen XHTML-Dokumente in Dokumente vom Typ „DITA-Thema“ konvertieren. Sie müssen die Speicherorte der Eingabe- und Ausgabeordner zusammen mit anderen Parametern angeben, und die Dokumente werden in das DITA-Format konvertiert. Es gibt zwei Methoden, mit denen Sie Ihre strukturierten HTML-Dokumente konvertieren können:

- alle Dokumente in den Eingabeordner hochladen oder
- Erstellen Sie eine ZIP-Datei aller Dokumente zusammen mit den Mediendateien und laden Sie sie in den Eingabeordner hoch. Dieser Ansatz wird im Allgemeinen für eine Reihe von HTML-Dateien verwendet, die miteinander verknüpft sind und es gibt ein Inhaltsverzeichnis \(index.html\). Die Datei index.html enthält Links zu allen HTML-Dateien im Set.

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

  Beachten Sie, dass für jedes `ul`-Tag das `class`-Attribut auf `book` festgelegt sein muss. Ebenso muss die `class` jedes `li`-Tags auf `topicref` gesetzt werden.

- Wenn Sie Inline-Stile verwenden, konvertieren Sie die Inline-Stile in Ihrer XHTML-Datei in CSS-basierte Stilklassen. Verwenden Sie dann die Stilattributzuordnung, um diese klassenbasierten Stile in der konvertierten DITA-Datei in das DITA-`outputclass`-Attribut zu konvertieren.

  Beim Generieren von HTML- oder AEM Site-Ausgaben aus diesen DITA-Dateien können die `outputclass`-Attribute verwendet werden, um auf generierte HTML- oder AEM-Sites Stilklassen anzuwenden, die mit Ihren Quell-HTML-Inhalten übereinstimmen.


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

1. Melden Sie sich nach dem Konfigurieren der erforderlichen Parameter in der `h2d_io.xml`-Datei bei AEM an und öffnen Sie die Assets-Benutzeroberfläche.

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

Mit AEM Guides können Sie vorhandene unstrukturierte FrameMaker \(`.fm` und `.book`\)-Dokumente in DITA-Dokumente konvertieren. Der erste Schritt besteht darin, Stilzuordnungen mithilfe von FrameMaker zu erstellen und diese Einstellungen in einer STS-Datei zu speichern. Wenn Sie anschließend benutzerdefinierte DITA verwenden, können Sie Ihre benutzerdefinierten FrameMaker-Elemente den Quell-CD-Formaten in der `ditaElems.xml` zuordnen. Wenn Sie beispielsweise ein benutzerdefiniertes Element mit dem Namen `impnote` für alle wichtigen Notizen erstellt haben, können Sie dieses benutzerdefinierte Element in der `ditaElems.xml` definieren. Sobald dieses benutzerdefinierte Element definiert ist, würde AEM Guides beim Konvertieren eines FrameMaker-Dokuments, das `impnote` Element enthält, keinen Fehler mehr auslösen.

Wenn Sie außerdem einige zusätzliche Attribute mit Ihrem benutzerdefinierten oder gültigen DITA-Element angeben möchten, können Sie diese in der Datei style2attrMap.xml definieren. Sie können beispielsweise das Attribut `type` mit dem Wert `important` angeben, der mit dem `impnote`-Element übergeben werden soll. Diese zusätzlichen Informationen können in der Datei style2attrMap.xml angegeben werden.

Zusätzlich zur Angabe von

Führen Sie die folgenden Schritte aus, um Ihre vorhandenen unstrukturierten FrameMaker-Dokumente in das DITA-Format zu konvertieren:

1. Erstellen Sie Stilzuordnungen im FrameMaker und speichern Sie diese Einstellungen in einer STS-Datei.

1. Melden Sie sich bei AEM an und öffnen Sie den CRXDE Lite-Modus.

1. Wenn Sie über benutzerdefinierte DITA-Elemente verfügen, definieren Sie diese in der `ditaElems.xml`-Datei, die am folgenden Speicherort verfügbar ist:

   `/libs/fmdita/config/ditaElems.xml`

1. Erstellen Sie einen Überlagerungsknoten des `config` Ordners im `apps`.

1. Navigieren Sie zu der Konfigurationsdatei, die im Knoten `apps` verfügbar ist:

   `/apps/fmdita/config/ditaElems.xml`

   Die `ditaElems.xml` enthält einen einzelnen konfigurierbaren Parameter:

   - Geben Sie im `elem`-Parameter den Namen des benutzerdefinierten Elements an, das Sie in Ihren konvertierten DITA-Dokumenten verwenden möchten. Dieses Element wird so weitergegeben, wie es in den generierten DITA-Dokumenten vorhanden ist.

1. Wenn Sie zusätzliche Attribute angeben möchten, definieren Sie diese in der `style2attrMap.xml`-Datei, die am folgenden Speicherort verfügbar ist:

   `/libs/fmdita/config/style2attrMap.xml`

1. Erstellen Sie einen Überlagerungsknoten des `config` Ordners im `apps`.

1. Navigieren Sie zu der Konfigurationsdatei, die im Knoten `apps` verfügbar ist:

   `/apps/fmdita/config/style2attrMap.xml`

   Die `style2attrMap.xml`-Datei enthält die folgenden konfigurierbaren Parameter:

   - Geben Sie im `fmStyle`-Parameter das Quellformat an, das in dem FrameMaker-Dokument verwendet wird, das Sie zuordnen möchten.

   - Geben `ditaAttr` im Element das DITA-Attribut an, das Sie dem Quellformat zuordnen möchten.

   - Geben Sie im `ditaVal`-Element den Wert für das zugeordnete Attribut an. Wenn Sie keinen Wert haben, können Sie diesen Eintrag leer lassen.

1. Speichern Sie die `style2attrMap.xml`-Datei.

1. Melden Sie sich nach dem Konfigurieren der erforderlichen Parameter in der `style2attrMap.xml`-Datei bei AEM an und öffnen Sie die Assets-Benutzeroberfläche.

1. Navigieren Sie zu dem FrameMaker-Dokument, das Sie konvertieren möchten, und klicken Sie darauf.

   Die DITA-Zuordnungskonsole wird mit der Liste der für die Generierung der Ausgabe verfügbaren Ausgabevorgaben angezeigt.

1. Wählen Sie das DITA-Ausgabeformat aus und konfigurieren Sie die erforderlichen Parameter.

   >[!NOTE]
   >
   > Sie müssen die Einstellungsdatei \(.sts\) verwenden, die Sie auf FrameMaker erstellt haben. Geben Sie außerdem den Einstellungsnamen und den Zielpfad an.

1. Klicken Sie auf **Generieren**, um den Ausgabegenerierungsprozess zu starten.


Mit dem `<attrMap> </attrMap>` können Sie einen oder mehrere Konfigurationsblöcke für die Konvertierung definieren. Je nach Inhalt könnten Sie eine DITA-Datei und eine DITAMAP-Datei als konvertierte Dateien verwenden.

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

1. Melden Sie sich nach dem Konfigurieren der erforderlichen Parameter in der `XSLConfig.xml`-Datei bei AEM an und öffnen Sie die Assets-Benutzeroberfläche.

1. Navigieren Sie zum Speicherort des Eingabeordners \(`xsltodita`\).

1. Laden Sie die strukturierten Quelldokumente in diesen Ordner hoch. Informationen zum Hochladen von Inhalten in DAM finden Sie unter [Vorhandenen DITA-Inhalt hochladen](migrate-content-upload-existing-dita-content.md#).


Mit dem `<config> </config>` können Sie einen oder mehrere Konfigurationsblöcke für die Konvertierung definieren. Der Konvertierungs-Workflow wird ausgeführt und die endgültige Ausgabe in Form eines DITA-Themas wird an dem im `outputDir` angegebenen Speicherort gespeichert.

**Übergeordnetes Thema:**[ Migrieren vorhandener Inhalte](migrate-content.md)
