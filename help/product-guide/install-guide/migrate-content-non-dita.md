---
title: Nicht-DITA-Inhalt migrieren
description: Erfahren Sie, wie Sie Nicht-DITA-Inhalte migrieren.
exl-id: 4597d1be-5426-4eba-8490-e42d0e565427
feature: Migration
role: Admin
level: Experienced
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '2761'
ht-degree: 0%

---

# Nicht-DITA-Inhalt migrieren {#id181AH0R02HT}

Dieser Abschnitt führt Sie durch den Migrationsprozess, um Nicht-DITA-Dokumente in das DITA-Format zu migrieren. AEM Guides bietet Migration aus den folgenden Quellen:

- [Microsoft Word](#id1949B040Z5Z)

- [InDesign-Dokumente](#id195AD0B0K5Z)

- [XHTML](#id1949B04L0Y4)

- [Unstrukturierte FrameMaker-Dokumente](#id1949B050VUI)

- [Jedes andere strukturierte Dokument](#id1949B0590YK)


## Migrieren von Microsoft Word-Dokumenten {#id1949B040Z5Z}

Mit AEM Guides können Sie vorhandene Word-Dokumente \(`.docx`\) in DITA-Thementypdokumente migrieren. Sie müssen die Eingabe- und Ausgabeordnerspeicherorte zusammen mit anderen Parametern angeben und das Dokument wird in ein DITA-Dokument konvertiert. Je nach Inhalt können Sie über eine .dita-Datei und eine .ditamap-Datei verfügen.

Um ein Word-Dokument erfolgreich konvertieren zu können, sollte Ihr Dokument gut strukturiert sein. Beispielsweise sollte Ihr Dokument einen Titel, gefolgt von Überschrift 1, Überschrift 2 usw. haben. Jede Überschrift sollte einen Inhalt enthalten. Wenn Ihr Dokument nicht gut strukturiert ist, funktioniert der Prozess möglicherweise nicht wie erwartet.

Standardmäßig verwendet AEM Guides das Transformations-Framework [Word-to-DITA \(Word2DITA\)](http://www.dita4publishers.org/docs/repo/org.dita4publishers.word2dita/word2dita/word2dita-intro.html). Diese Umwandlung hängt von der Konfigurationsdatei [style-to-tag mapping](http://www.dita4publishers.org/docs/repo/org.dita4publishers.word2dita/word2dita/style-to-tag-map-overview.html) ab. Um die Word2DITA-Transformation erfolgreich verwenden zu können, müssen Sie die folgenden Richtlinien beachten, um Ihr Word-Dokument für die Konvertierung vorzubereiten:

>[!NOTE]
>
> Wenn Sie Änderungen an der standardmäßigen Konfigurationsdatei für die Zuordnung von Stil zu Tag vornehmen, müssen Sie die Richtlinien aktualisieren und verwenden, die Ihre aktualisierte Stilzuordnung bestätigen.

- Stellen Sie sicher, dass Ihr Dokument mit einem Titel beginnt. Dieser Titel ist dem DITA-Map-Titel zugeordnet. Außerdem müssen auf den Titel einige reguläre Inhalte folgen.

- Nach dem Titel sollte Überschrift 1, Überschrift 2 usw. stehen. Jede Überschrift muss Inhalt enthalten. Die Überschriften werden in neue Themen vom Typ Konzept umgewandelt. Die Hierarchie der generierten Themen richtet sich nach den Überschriftenebenen im Dokument. So geht beispielsweise Überschrift 1 der Überschrift 2 voran und Überschrift 2 geht dem Inhalt von Überschrift 3 voran.

- Das Dokument muss mindestens einen Inhalt vom Typ Überschrift enthalten.

- Vergewissern Sie sich, dass Sie keine gruppierten Bilder haben. Wenn Sie Bilder in Ihrem Dokument gruppiert haben, heben Sie die Gruppierung aller dieser Bilder auf.

- Entfernen Sie alle Kopf- und Fußzeilen.

- Inline-Stile wie Fett, Kursiv und Unterstrichen werden in Elemente `b`, `i` und `u` umgewandelt.

- Alle sortierten und unsortierten Listen werden in `ol` - und `ul` -Elemente umgewandelt. Dies gilt auch für verschachtelte Listen, Listen in Tabellen, Anmerkungen oder Fußnoten.

- Alle Hyperlinks werden in `xref` umgewandelt.

- Der Dateiname der konvertierten Dateien basiert auf dem Überschriftentext gefolgt von einer Dateinummer. Die Dateinummer ist eine sequenzielle Zahl, die auf der Position des Überschriftentextes im Dokument basiert. Wenn beispielsweise ein Überschriftentext &quot;Beispielüberschrift&quot;lautet und er die 10. Überschrift im Dokument ist, ist der resultierende Dateiname für dieses Thema ähnlich dem Beispiel\_Überschrift\_10.dita.


Führen Sie die folgenden Schritte aus, um Ihre vorhandenen Word-Dokumente in DITA-Thementypdokumente zu konvertieren:

1. Melden Sie sich bei AEM an und öffnen Sie den CRXDE Lite-Modus.

1. Navigieren Sie zur Standardkonfigurationsdatei, die unter folgendem Speicherort verfügbar ist:

   `/libs/fmdita/config/w2d_io.xml`

1. Erstellen Sie einen Überlagerungsknoten des Ordners `config` im Knoten `apps` .

1. Navigieren Sie zur Konfigurationsdatei, die im Knoten `apps` verfügbar ist:

   `/apps/fmdita/config/w2d_io.xml`

   Die Datei `w2d_io.xml` enthält die folgenden konfigurierbaren Parameter:

   - Geben Sie im Element `inputDir` den Speicherort des Eingabeordners an, in dem Ihre Word-Quelldokumente verfügbar sind. Wenn Ihre Word-Dokumente beispielsweise in einem Ordner mit dem Namen `wordtodita` im Ordner `projects` gespeichert sind, geben Sie den Speicherort als &quot;`/content/dam/projects/wordtodita/`&quot;an.

   - Geben Sie im Element `outputDir` den Speicherort des Ausgabeordners an oder behalten Sie den standardmäßigen Ausgabespeicherort bei, um das konvertierte DITA-Dokument zu speichern. Wenn der angegebene Ausgabeordner nicht in DAM vorhanden ist, erstellt der Konvertierungs-Workflow den Ausgabeordner.

   - Geben Sie für das Element `createRev` an, ob eine neue Version des konvertierten DITA-Themas erstellt werden soll \(`true`\) oder nicht \(`false`\).

   - Geben Sie im Element `s2tMap` den Speicherort der Zuordnungsdatei an, die Zuordnungen für Word-Dokumentstile zu DITA-Elementen enthält. Die Standardzuordnung wird in der Datei gespeichert, die sich unter:

     ```XML
     /libs/fmdita/word2dita/word-builtin-styles-style2tagmap.xml
     ```

     >[!NOTE]
     >
     > Weitere Informationen zur Struktur der Datei `word-builtin-styles-style2tagmap.xml` und dazu, wie Sie sie anpassen können, finden Sie unter [Style to Tag Mapping](http://www.dita4publishers.org/docs/repo/org.dita4publishers.word2dita/word2dita/style-to-tag-map-overview.html) im *DITA für Herausgeber-Benutzerhandbuch*.

   - Geben Sie im Element props2Propagate die Eigenschaften an, die an die DITA-Zuordnung übergeben werden sollen. Diese Eigenschaft ist erforderlich, um die Standardmetadaten wie dc:title,dc:subject,dam:keywords,dam:category aus Dokumentmetadaten an konvertierte DITA-Assets zu übergeben.

1. Speichern Sie die Datei `w2d_io.xml`.

1. Nachdem Sie die erforderlichen Parameter in der Datei `w2d_io.xml` konfiguriert haben, melden Sie sich bei AEM an und öffnen Sie die Assets-Benutzeroberfläche.

1. Navigieren Sie zum Eingabeordnerspeicherort \(`wordtodita`\).

1. Laden Sie die Word-Quelldokumente in diesen Ordner hoch. Informationen zum Hochladen von Inhalten in DAM finden Sie unter [Hochladen vorhandener DITA-Inhalte ](migrate-content-upload-existing-dita-content.md#).


Mit dem Block `config` `/config` können Sie einen oder mehrere Konfigurationsblöcke für die Konvertierung definieren. Der Konvertierungs-Workflow wird ausgeführt und die endgültige Ausgabe in Form eines DITA-Themas wird an dem im Element `outputDir` angegebenen Speicherort gespeichert.

## Migrieren von Adobe InDesign-Dokumenten {#id195AD0B0K5Z}

Mit AEM Guides können Sie InDesign-Dokumente konvertieren. Ähnlich wie beim FrameMaker ermöglicht InDesign auch die Erstellung unstrukturierter und strukturierter Dokumente. Die unstrukturierten Dokumente verwenden die Absätze- und Zeichenstile zum Formatieren von Inhalten. Das strukturierte Dokument verwendet Elemente und die zugehörigen Attribute.

Der Konvertierungsprozess erfordert die Zuordnung der Absätze- und Zeichenstilformate zu relevanten DITA-Elementen. Gleichermaßen enthält die Zuordnungsdatei bei strukturierten Dokumenten eine Eins-zu-Eins-Zuordnung von InDesign-Elementen und -Attributen mit DITA-Elementen und -Attributen.

Der Konvertierungsprozess umfasst die folgenden Aktionen im Backend:

- Die Datei *InDesign Markup Language* \(IDML\) ist in ein Arbeitsverzeichnis entpackt.
- Die Datei designmap.xml wird gelesen, um die einzelnen InDesign-Geschichten zu finden.
- Alle Geschichten werden zu einer einzelnen XML-Instanz zusammengeführt, &quot;leere&quot;Geschichten werden verworfen.
- Alle eingebetteten Grafiken werden exportiert.
- Vorkonvertierung von Standardstrukturen wie Tabellen und Grafiken in das DITA-Format.
- Stil- oder Strukturzuordnung zur endgültigen Ausgabe basierend auf der Zuordnungsdatei.
- Erstellung und Validierung einzelner DITA-Themen und DITA-Zuordnungsdateien.
- Löschen temporärer Dateien.

Im Großen und Ganzen erfordert der Konvertierungsprozess, dass Sie die InDesign--Dateien für die Konvertierung vorbereiten](appendix.md#id195DBF0045Z) und die Zuordnungsdatei für die InDesign zu DITA-Migration vorbereiten](appendix.md#id194AF0003HT). Anschließend müssen Sie das angegebene Verfahren zum Ausführen des Konvertierungsprozesses befolgen.[[

Führen Sie die folgenden Schritte aus, um Ihre vorhandenen InDesign-Dokumente in DITA-Thementypdokumente zu konvertieren:

1. Melden Sie sich bei AEM an und öffnen Sie den CRXDE Lite-Modus.

1. Navigieren Sie zur Standardkonfigurationsdatei, die unter folgendem Speicherort verfügbar ist:

   `/libs/fmdita/config/idml2dita_io.xml`

1. Erstellen Sie einen Überlagerungsknoten des Ordners `config` im Knoten `apps` .

1. Navigieren Sie zur Konfigurationsdatei, die im Knoten `apps` verfügbar ist:

   `/apps/fmdita/config/idml2dita_io.xml`

   Konfigurieren Sie die folgenden Parameter in der Datei `idml2dita_io.xml` :

   - Geben Sie im Element `inputDir` den Speicherort des Eingabeordners an, in dem die Quelldokumente für InDesign verfügbar sind. Wenn Ihre InDesign-Dokumente beispielsweise in einem Ordner mit dem Namen `indesigntodita` im Ordner `projects` gespeichert sind, geben Sie folgenden Speicherort an: `/content/dam/idmlfiles/indesigntodita/`

   - Geben Sie im Element `outputDir` den Speicherort des Ausgabeordners an oder behalten Sie den standardmäßigen Ausgabespeicherort bei, um das konvertierte DITA-Dokument zu speichern. Wenn der angegebene Ausgabeordner nicht in DAM vorhanden ist, erstellt der Konvertierungs-Workflow den Ausgabeordner.

   - Geben Sie im Element `mapStyle` den Speicherort der Zuordnungsdatei an, die Zuordnungen für InDesign-Dokumentstile zu DITA-Elementen enthält. Die Standardzuordnung wird in der Datei gespeichert, die sich unter:

     ```XML
     /stmap.adobeidml.xml
     ```

     >[!NOTE]
     >
     > Weitere Informationen zur Dateistruktur von `stmap.adobeidml.xml` und dazu, wie Sie sie anpassen können, finden Sie im Abschnitt [Vorbereiten der Zuordnungsdatei für die InDesign zur DITA-Migration](appendix.md#id194AF0003HT) im Abschnitt *Anhang*.

1. Speichern Sie die Datei `idml2dita_io.xml`.

1. Nachdem Sie die erforderlichen Parameter in der Datei `idml2dita_io.xml` konfiguriert haben, melden Sie sich bei AEM an und öffnen Sie die Assets-Benutzeroberfläche.

1. Navigieren Sie zum Eingabeordnerspeicherort \(`indesigntodita`\).

1. Laden Sie die Quelldokumente in diesen InDesign hoch. Informationen zum Hochladen von Inhalten in DAM finden Sie unter [Hochladen vorhandener DITA-Inhalte ](migrate-content-upload-existing-dita-content.md#).


## Migrieren von XHTML-Dokumenten {#id1949B04L0Y4}

Mit AEM Guides können Sie vorhandene XHTML-Dokumente in DITA-Themendokumente konvertieren. Sie müssen die Eingabe- und Ausgabeordnerspeicherorte zusammen mit anderen Parametern angeben und die Dokumente werden in das DITA-Format konvertiert. Es gibt zwei Methoden zum Konvertieren von strukturierten HTML-Dokumenten:

- Laden Sie alle Dokumente in den Eingabeordner hoch oder
- Erstellen Sie eine ZIP-Datei aller Dokumente zusammen mit den Mediendateien und laden Sie sie in den Eingabeordner hoch. Dieser Ansatz wird im Allgemeinen für eine Reihe von HTML-Dateien verwendet, die miteinander verknüpft sind, und es gibt ein Inhaltsverzeichnis \(index.html\). Die Datei index.html enthält Links zu allen HTML-Dateien im Satz.

Unabhängig davon, ob Sie alle Dateien einzeln oder gebündelt in einer ZIP-Datei hochladen, erstellt der Konvertierungsprozess eine Eins-zu-Eins-Zuordnung zwischen den HTML-Dateien und den resultierenden DITA-Dateien. Dies bedeutet im Wesentlichen, dass für jede HTML-Datei im Eingabeordner eine .dita-Datei erstellt wurde.

Folgende Punkte müssen beim Hochladen Ihrer Dokumente in eine ZIP-Datei berücksichtigt werden:

- Alle referenzierten Themen sollten in der ZIP-Datei platziert werden.

- Alle referenzierten Mediendateien sollten mithilfe des relativen Links in den Themendateien referenziert werden.

- Erstellen Sie eine Datei index.html und fügen Sie Links zu den Themen hinzu, die Sie im Inhaltsverzeichnis hinzufügen möchten. Diese Datei index.html wird zum Erstellen der DITA-Map-Datei verwendet. In der Datei &quot;index.html&quot;können Sie auch verschachtelte Themen erstellen, die wie im folgenden Codebeispiel gezeigt auflisten:

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

  Beachten Sie, dass für jedes `ul` -Tag das Attribut `class` auf `book` gesetzt sein muss. Ebenso muss der `class`-Wert jedes `li`-Tags auf `topicref` gesetzt werden.

- Wenn Sie Inline-Stile verwenden, konvertieren Sie die Inline-Stile in CSS-basierte Stilklassen in Ihrer XHTML-Datei. Verwenden Sie dann die Stilattribut-Zuordnung, um diese klassen-basierten Stile in das DITA `outputclass` -Attribut in der konvertierten DITA-Datei zu konvertieren.

  Beim Generieren von HTML- oder AEM Site-Ausgabe aus diesen DITA-Dateien können die `outputclass` -Attribute verwendet werden, um die Stilklasse auf die generierte HTML oder AEM Site anzuwenden und Ihren Quell-HTML-Inhalt abzugleichen.


Neben den Überlegungen zum Erstellen der ZIP-Datei muss Ihr XHTML-Dokument auch gut strukturiert sein. Beispielsweise sollte Ihr Dokument einen *Titel*, gefolgt von *Überschrift 1*, *Überschrift 2* usw. aufweisen. Jede Überschrift sollte einen Inhalt enthalten. Wenn Ihr Dokument nicht gut strukturiert ist, funktioniert der Migrationsprozess möglicherweise nicht wie erwartet.

Führen Sie die folgenden Schritte aus, um Ihr vorhandenes XHTML-Dokument in ein DITA-Thema zu konvertieren:

1. Melden Sie sich bei AEM an und öffnen Sie den CRXDE Lite-Modus.

1. Navigieren Sie zur Standardkonfigurationsdatei, die unter folgendem Speicherort verfügbar ist:

   `/libs/fmdita/config/h2d_io.xml`

1. Erstellen Sie einen Überlagerungsknoten des Ordners `config` im Knoten `apps` .

1. Navigieren Sie zur Konfigurationsdatei, die im Knoten `apps` verfügbar ist:

   `/apps/fmdita/config/h2d_io.xml`

   Die Datei `h2d_io.xml` enthält die folgenden konfigurierbaren Parameter:

   - Geben Sie im Element `inputDir` den Speicherort Ihres Eingabeordners an, in dem Ihre Quell-XHTML-Dokumente verfügbar sind. Wenn Ihre XHTML-Dokumente beispielsweise in einem Ordner mit dem Namen `xhtmltodita` im Ordner `projects` gespeichert sind, geben Sie den Speicherort wie folgt an: `/content/dam/projects/xhtmltodita/`

   - Geben Sie im Element`outputDir` den Speicherort Ihres Ausgabeordners an oder behalten Sie den standardmäßigen Speicherort für die Ausgabe bei. Wenn der angegebene Ausgabeordner nicht in DAM vorhanden ist, erstellt der Konvertierungs-Workflow den Ausgabeordner.

   - Geben Sie für das Element `createRev` an, ob eine neue Version des konvertierten DITA-Themas erstellt werden soll \(`true`\) oder nicht \(`false`\).

1. Speichern Sie die Datei `h2d_io.xml`.

1. Nachdem Sie die erforderlichen Parameter in der Datei `h2d_io.xml` konfiguriert haben, melden Sie sich bei AEM an und öffnen Sie die Assets-Benutzeroberfläche.

1. *\(Optional\)* Sie können auch den Abschnitt mit den zugehörigen Links zu den konvertierten Dokumenten hinzufügen. Führen Sie die folgenden Schritte aus, um diese Funktion zu aktivieren:

   >[!NOTE]
   >
   > Standardmäßig wird der Abschnitt für zugehörige Links nicht in den konvertierten Dokumenten erstellt.

   1. Navigieren Sie zur Datei h2d.xsl im folgenden Verzeichnis:

      /libs/fmdita/html2dita/

   2. Suchen Sie nach dem folgenden Parameter:

      `<xsl:param name="generate-related-links" select="false()"/>`

   3. Setzen Sie den Wert des obigen Parameters auf `true()`.
   4. Speichern und schließen Sie die Datei.
1. Navigieren Sie zum Eingabeordnerspeicherort \(`xhtmltodita`\).

1. Laden Sie die XHTML-Quelldokumente in diesen Ordner hoch. Informationen zum Hochladen von Inhalten in DAM finden Sie unter [Hochladen vorhandener DITA-Inhalte ](migrate-content-upload-existing-dita-content.md#).


Mit dem Block `<config> </config>` können Sie einen oder mehrere Konfigurationsblöcke für die Konvertierung definieren. Der Konvertierungs-Workflow wird ausgeführt und die endgültige Ausgabe in Form eines DITA-Themas wird an dem im Element `outputDir` angegebenen Speicherort gespeichert.

## Migrieren von unstrukturierten FrameMaker-Dokumenten {#id1949B050VUI}

Mit AEM Guides können Sie bestehende unstrukturierte FrameMaker \(`.fm` und `.book`\) in DITA-Dokumente konvertieren. Der erste Schritt besteht darin, Stilzuordnungen mithilfe von FrameMaker zu erstellen und diese Einstellungen in einer .sts-Datei zu speichern. Wenn Sie als Nächstes benutzerdefiniertes DITA verwenden, können Sie Ihre benutzerdefinierten FrameMaker-Elemente den Quellformaten in der Datei `ditaElems.xml` zuordnen. Wenn Sie beispielsweise ein benutzerdefiniertes Element mit dem Namen `impnote` erstellt haben, um alle wichtigen Hinweise zu verarbeiten, können Sie dieses benutzerdefinierte Element in der Datei `ditaElems.xml` definieren. Nachdem dieses benutzerdefinierte Element definiert wurde, löst AEM Guides beim Konvertieren des FrameMaker-Dokuments mit dem Element `impnote` keinen Fehler aus.

Wenn Sie zusätzliche Attribute mit Ihrem benutzerdefinierten oder gültigen DITA-Element angeben möchten, können Sie diese auch in der Datei style2attrMap.xml definieren. Sie können beispielsweise das Attribut `type` mit dem Wert `important` angeben, das mit dem Element `impnote` übergeben werden soll. Diese zusätzlichen Informationen können in der Datei style2attrMap.xml angegeben werden.

Zusätzlich zur Angabe von

Gehen Sie wie folgt vor, um Ihre bestehenden unstrukturierten FrameMaker-Dokumente in das DITA-Format zu konvertieren:

1. Erstellen Sie Stilzuordnungen in FrameMaker und speichern Sie diese Einstellungen in einer .sts-Datei.

1. Melden Sie sich bei AEM an und öffnen Sie den CRXDE Lite-Modus.

1. Wenn Sie benutzerdefinierte DITA-Elemente haben, definieren Sie diese in der Datei &quot;`ditaElems.xml`&quot;, die am folgenden Speicherort verfügbar ist:

   `/libs/fmdita/config/ditaElems.xml`

1. Erstellen Sie einen Überlagerungsknoten des Ordners `config` im Knoten `apps` .

1. Navigieren Sie zur Konfigurationsdatei, die im Knoten `apps` verfügbar ist:

   `/apps/fmdita/config/ditaElems.xml`

   Die Datei `ditaElems.xml` enthält einen einzelnen konfigurierbaren Parameter:

   - Geben Sie im Parameter `elem` den Namen des benutzerdefinierten Elements an, das Sie in Ihren konvertierten DITA-Dokumenten verwenden möchten. Dieses Element wird wie in den generierten DITA-Dokumenten übergeben.

1. Wenn Sie zusätzliche Attribute angeben möchten, definieren Sie diese in der Datei &quot;`style2attrMap.xml`&quot;, die am folgenden Speicherort verfügbar ist:

   `/libs/fmdita/config/style2attrMap.xml`

1. Erstellen Sie einen Überlagerungsknoten des Ordners `config` im Knoten `apps` .

1. Navigieren Sie zur Konfigurationsdatei, die im Knoten `apps` verfügbar ist:

   `/apps/fmdita/config/style2attrMap.xml`

   Die Datei `style2attrMap.xml` enthält die folgenden konfigurierbaren Parameter:

   - Geben Sie im Parameter `fmStyle` das Quellformat an, das im FrameMaker-Dokument verwendet wird, das Sie zuordnen möchten.

   - Geben Sie im Element `ditaAttr` das DITA-Attribut an, das Sie dem Quellformat zuordnen möchten.

   - Geben Sie im Element `ditaVal` den Wert für das zugeordnete Attribut an. Wenn Sie keinen Wert haben, können Sie diesen Eintrag leer lassen.

1. Speichern Sie die Datei `style2attrMap.xml`.

1. Nachdem Sie die erforderlichen Parameter in der Datei `style2attrMap.xml` konfiguriert haben, melden Sie sich bei AEM an und öffnen Sie die Assets-Benutzeroberfläche.

1. Navigieren Sie zum FrameMaker-Dokument, das Sie konvertieren möchten, und klicken Sie darauf.

   Die DITA-Zuordnungskonsole wird mit der Liste der zum Generieren der Ausgabe verfügbaren Ausgabevorgaben angezeigt.

1. Wählen Sie das DITA-Ausgabeformat aus und konfigurieren Sie die erforderlichen Parameter.

   >[!NOTE]
   >
   > Sie müssen dieselbe Einstellungsdatei \(.sts\) verwenden, die Sie in FrameMaker erstellt haben. Geben Sie außerdem den Einstellungsnamen und den Zielpfad an.

1. Klicken Sie auf das Symbol **Erzeugen** , um den Generierungsprozess der Ausgabe zu starten.


Mit dem Block `<attrMap> </attrMap>` können Sie einen oder mehrere Konfigurationsblöcke für die Konvertierung definieren. Abhängig vom Inhalt können Sie als konvertierte Dateien eine .dita-Datei und eine .ditamap-Datei verwenden.

## Migrieren anderer strukturierter Dokumente {#id1949B0590YK}

Mit AEM Guides können Sie vorhandene strukturierte Dokumente in gültige DITA-Dokumente konvertieren. Sie müssen die Speicherorte für Eingabe- und Ausgabeordner, den Speicherort der Umwandlungsdatei, die Erweiterung, mit der die endgültige Ausgabe gespeichert wird, und angeben, ob eine neue Version des Dokuments erforderlich ist oder nicht.

Führen Sie die folgenden Schritte aus, um Ihre vorhandenen strukturierten Dokumente in das DITA-Format zu konvertieren:

1. Melden Sie sich bei AEM an und öffnen Sie den CRXDE Lite-Modus.

1. Navigieren Sie zur Standardkonfigurationsdatei, die unter folgendem Speicherort verfügbar ist:

   `/libs/fmdita/config/XSLConfig.xml`

1. Erstellen Sie einen Überlagerungsknoten des Ordners `config` im Knoten `apps` .

1. Navigieren Sie zur Konfigurationsdatei, die im Knoten `apps` verfügbar ist:

   `/apps/fmdita/config/XSLConfig.xml`

   Die Datei `XSLConfig.xml` enthält die folgenden konfigurierbaren Parameter:

   - Geben Sie im Element `inputDir` den Speicherort Ihres Eingabeordners an, in dem die strukturierten Quelldokumente verfügbar sind. Wenn Ihre strukturierten Dokumente beispielsweise in einem Ordner mit dem Namen `xsltodita` im Ordner `projects` gespeichert sind, geben Sie folgenden Speicherort an: `/content/dam/projects/xsltodita/`

   - Geben Sie im Element`outputDir` den Speicherort Ihres Ausgabeordners an oder behalten Sie den standardmäßigen Speicherort für die Ausgabe bei. Wenn der angegebene Ausgabeordner nicht in DAM vorhanden ist, erstellt der Konvertierungs-Workflow den Ausgabeordner.

   - Geben Sie im Element `xslFolder` den Speicherort des Ordners an, in dem die XSL-Transformationsdateien gespeichert werden.

   - Geben Sie im Element ``xslPath`` den Speicherort der primären .XSL-Datei an, die zum Initiieren des Konvertierungsprozesses verwendet wird.

   - Geben Sie im Element ``outputExt`` die Dateierweiterungen der endgültigen Ausgabedatei an, die aus dem Transformationsstream erstellt wird.

   - Geben Sie für das Element `createRev` an, ob eine neue Version des konvertierten DITA-Themas erstellt werden soll \(`true`\) oder nicht \(`false`\).

1. Speichern Sie die Datei `XSLConfig.xml`.

1. Nachdem Sie die erforderlichen Parameter in der Datei `XSLConfig.xml` konfiguriert haben, melden Sie sich bei AEM an und öffnen Sie die Assets-Benutzeroberfläche.

1. Navigieren Sie zum Eingabeordnerspeicherort \(`xsltodita`\).

1. Laden Sie die strukturierten Quelldokumente in diesen Ordner hoch. Informationen zum Hochladen von Inhalten in DAM finden Sie unter [Hochladen vorhandener DITA-Inhalte ](migrate-content-upload-existing-dita-content.md#).


Mit dem Block `<config> </config>` können Sie einen oder mehrere Konfigurationsblöcke für die Konvertierung definieren. Der Konvertierungs-Workflow wird ausgeführt und die endgültige Ausgabe in Form eines DITA-Themas wird an dem im Element `outputDir` angegebenen Speicherort gespeichert.

**Übergeordnetes Thema:**[ Migrieren vorhandener Inhalte](migrate-content.md)
