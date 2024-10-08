---
title: Native PDF | PDF-Ausgabegenerierung
description: Erfahren Sie, wie Sie die native PDF-Veröffentlichung verwenden, eine PDF-Ausgabevorgabe erstellen und generieren, temporäre Dateien herunterladen, nachdem Sie die native PDF-Ausgabe generiert haben, und Sprachvariablen in AEM Guides verwenden.
exl-id: ec3d59b7-1dda-4fd1-848e-21d8a36ff5e4
feature: Publishing, Web Editor, Native PDF Output
role: User
source-git-commit: e78749b1d5b4ba944cbca69ba65c6d28355b2c34
workflow-type: tm+mt
source-wordcount: '3362'
ht-degree: 1%

---

# Publish PDF-Ausgabe

Mit AEM Guides können Sie PDF einzelner Themen oder einer ganzen Map-Datei generieren. Sie können Ihre Inhalte mit einer der drei folgenden Methoden im PDF-Format veröffentlichen:

* **DITA-OT**

Verwenden Sie diese Methode, um eine PDF-Ausgabe für eine Zuordnung aus dem Mapping-Dashboard zu generieren. Sie können die Veröffentlichungseigenschaften festlegen, bevor Sie die PDF generieren, indem Sie eine Ausgabevorgabe für die Karte erstellen, die im Karten-Dashboard geöffnet ist. Um eine Ausgabevorgabe zu erstellen oder zu bearbeiten, gehen Sie zum Abschnitt *Grundlegendes zu den Ausgabevorgaben* im [AEM Guides as a Cloud Service-Benutzerhandbuch](https://helpx.adobe.com/content/dam/help/en/xml-documentation-solution/cs-apr-22/XML-Documentation-for-Adobe-Experience-Manager_CS_User-Guide_EN.pdf).

Weitere Informationen zum Generieren einer PDF mithilfe der DITA-OT-Methode finden Sie unter [Generate PDF using DITA-OT](https://help.adobe.com/en_US/xml-documentation-for-adobe-experience-manager/index.html#t=DXML-master-map%2Fgenerate-output-pdf.html).

* **FrameMaker Publishing Server (FMPS)**

Verwenden Sie diese Methode, um eine PDF-Ausgabe nicht nur aus dem DITA-Inhalt, sondern auch aus FrameMaker-Dokumenten (.book und .fm) zu generieren, die in Ihrem AEM-Repository verfügbar sind. Die PDF kann durch Konfigurieren einer Ausgabevorgabe erstellt und mithilfe von FrameMaker Publishing Server (FMPS) veröffentlicht werden. Sie können das Erscheinungsbild Ihrer Ausgabe für PDF und andere Formate entwerfen und konfigurieren und diese in einer Einstellungsdatei (.sts) speichern. Diese Einstellungsdatei wird dann von FMPS verwendet, um eine Ausgabe für eine DITA-Map- oder .book-Datei zu generieren. Informationen zum Erstellen oder Bearbeiten einer Ausgabevorgabe finden Sie im Abschnitt *Grundlegendes zu den Ausgabevorgaben* im [AEM Guides as a Cloud Service-Benutzerhandbuch](https://helpx.adobe.com/content/dam/help/en/xml-documentation-solution/cs-apr-22/XML-Documentation-for-Adobe-Experience-Manager_CS_User-Guide_EN.pdf).

Weitere Informationen zum Konfigurieren von FMPS finden Sie unter [Generate output from FrameMaker documents](https://help.adobe.com/en_US/xml-documentation-for-adobe-experience-manager/index.html#t=DXML-master-map%2Ffm-output-generatation.html).

* **Native PDF-Veröffentlichung**

Verwenden Sie diese Methode, um eine funktionsreiche PDF-Ausgabe zu generieren, die auf W3C CSS3- und CSS-Medienstandards basiert. Mit der nativen PDF-Veröffentlichung können Sie Vorlagen verwenden, um das Layout und die Formatierung für Ihre festzulegen und verschiedene Einstellungen zur Feinabstimmung Ihrer PDF anzuwenden. Darüber hinaus können Sie mit dem Vorlageneditor Ihre eigenen Vorlagen ändern und erstellen.

Weitere Informationen zur nativen PDF-Veröffentlichung finden Sie unter [Verwenden der nativen PDF-Veröffentlichung](#native-pdf-publishing).


## Verwenden der nativen PDF-Veröffentlichung {#native-pdf-publishing}

Beim Bearbeiten von Inhalten muss sichergestellt werden, dass der Inhalt für Anzeige, Bearbeitung und Druck optimiert ist. Mithilfe von Standards wie dem W3C CSS3 für Inhaltsstile und CSS-Standards für seitendefinierte Eigenschaften wie Größe, Ränder, Ausrichtung, Seitenumbrüche, Kopfzeilen, Fußzeilen und Seitennummerierung können Sie die Ansicht und das Layout für Ihr PDF-Dokument festlegen, um Konsistenz und Benutzerfreundlichkeit zu gewährleisten. Die native PDF-Veröffentlichungsfunktion verwendet diese Standards zum Generieren einer PDF.

Mit der nativen PDF-Veröffentlichung können Sie vordefinierte Vorlagen verwenden, um das Inhaltslayout und die Inhaltsstruktur konsistent zu gestalten, Stylesheets anwenden, um das Erscheinungsbild Ihrer Ausgabe zu ändern, PDF zu optimieren, Druckermarkierungen festzulegen, Unterstützung für Bildschirmlesehilfen zuzulassen, PDF-Konformität festzulegen, Schriftarten einzubetten und vieles mehr.

Die Erstellung einer PDF mithilfe der nativen PDF-Veröffentlichung hat zwei Aspekte:

* Verwenden Sie Vorlagen, um Stile auf Inhalte anzuwenden, Seitenlayouts festzulegen und verschiedene Einstellungen zur Feinabstimmung Ihres PDF vorzunehmen. Autoren können die bereitgestellten Beispielvorlagen verwenden/ändern oder benutzerdefinierte Vorlagen erstellen und erweiterte Konfigurationsoptionen festlegen, die von Herausgebern und Entwicklern verwendet werden.

* Erstellen oder konfigurieren Sie eine PDF-Ausgabevorgabe, um die PDF-Einstellungen zu steuern. Nachdem Sie eine PDF-Ausgabevorgabe erstellt haben, können Sie die PDF generieren.

Weitere Informationen finden Sie unter [Generate a PDF output](#generate-pdf-output).

## Erstellen einer PDF-Ausgabevorgabe {#create-output-preset}

Der erste Schritt beim Generieren einer PDF-Ausgabe besteht darin, eine PDF-Ausgabevorgabe zu erstellen, die aus einer Sammlung von Veröffentlichungseigenschaften besteht, die einer Zuordnung zugewiesen sind. Sie können eine Ausgabevorgabe für jede Karte erstellen, die im Bereich &quot;Map View&quot;geöffnet ist, oder eine vorhandene Vorgabe konfigurieren, um schnell eine PDF für dieselbe Karte zu generieren.

In der PDF-Ausgabevorgabe können Sie eine Vorlage auswählen, Bedingungen anwenden, Einschränkungen festlegen, um zu steuern, wie ein Benutzer mit Ihrer PDF interagiert, erweiterte Einstellungen wie Komprimierung, Konformität und mehr konfigurieren.

So erstellen oder konfigurieren Sie eine PDF-Ausgabevorgabe:

1. Klicken Sie auf der Registerkarte &quot;Ausgabe&quot;in der linken Seitenleiste auf **Vorgaben** .
Das Fenster &quot;Voreingestellt&quot;wird geöffnet. <br>
<img src="assets/preset-panel.png" alt="Vorgabenbedienfeld" width="600">

1. Führen Sie im Ausgabefeld **Vorgaben** einen der folgenden Schritte aus:
   * Doppelklicken Sie auf eine vordefinierte PDF-Ausgabevorgabe, um sie anzuzeigen.
   * Klicken Sie auf das Symbol + neben **Vorgaben** , um eine neue Ausgabevorgabe vom Typ **Typ: PDF** hinzuzufügen.

1. So konfigurieren Sie die Einstellungen einer vorhandenen PDF-Vorgabe:
   * Klicken Sie auf das Symbol **Optionen** ![Optionen](assets/options.svg) neben der gewünschten Ausgabevorgabe und wählen Sie **Bearbeiten** aus.
Sie können die folgenden Einstellungen auf den Registerkarten **Allgemein**, **Metadaten**, **Layout**, **Sicherheit** und **Erweitert** verwenden, um eine PDF-Ausgabevorgabe zu konfigurieren:

**Allgemein**

Verwenden Sie , um grundlegende Ausgabeeinstellungen anzugeben, z. B. Ausgabepfad, PDF-Dateiname und mehr.

| Einstellung | Beschreibung |
| --- | --- |
| **Ausgabepfad** | Der Pfad im AEM-Repository, in dem die PDF-Ausgabe gespeichert wird. Stellen Sie sicher, dass sich der Ausgabepfad nicht im Projektordner befindet. Wenn Sie das Feld leer lassen, wird die Ausgabe am standardmäßigen Speicherort der DITA-Map-Ausgabe generiert.<br>Sie können auch die folgenden vordefinierten Variablen verwenden, um den Ausgabepfad zu definieren. Sie können eine einzelne oder eine Kombination von Variablen verwenden, um diese Option zu definieren. <br> `${map_filename}`: Verwendet den Namen der DITA-Map-Dateien, um den Zielpfad zu erstellen. <br> `${map_title}`: Verwendet den DITA-Map-Titel, um den Zielpfad zu erstellen. <br>`${preset_name}`: Verwendet den Namen der Ausgabevorgabe, um den Zielpfad zu erstellen. <br> `${language_code}`: Verwendet den Sprachcode, in dem sich die Map-Datei befindet, um den Zielpfad zu erstellen. <br> `${map_parentpath}`: Verwendet den vollständigen Pfad der Zuordnungsdatei, um den Zielpfad zu erstellen.  <br>`${path_after_langfolder}`: Verwendet den Pfad der Map-Datei nach dem Sprachordner, um den Zielpfad zu erstellen. |
| **PDF-Datei** | Geben Sie einen Dateinamen zum Speichern der PDF an. Standardmäßig fügt der PDF-Dateiname den DITA-Map-Namen zusammen mit dem Vorgabennamen hinzu. Beispielsweise ist ditamap &#39;TestMap&#39; und der Name der Vorgabe &#39;preset1&#39;. Dann lautet der Standardname des PDF-Dokuments &#39;TestMap_preset1.pdf&#39;. <br>Sie können auch die folgenden vordefinierten Variablen verwenden, um die PDF-Datei zu definieren. Sie können eine einzelne oder eine Kombination von Variablen verwenden, um diese Option zu definieren. <br>`${map_filename}`<br>`${map_title}`<br>`${preset_name}` <br> `${language_code}`. |
| **Bedingungen mithilfe von** anwenden | Wählen Sie für konditionalisierten Inhalt aus den folgenden Optionen, um eine PDF-Ausgabe zu generieren, die auf diesen Bedingungen basiert: <br><ul> <li> **Keine angewendet** Wählen Sie diese Option, wenn Sie keine Bedingung für die Zuordnung und den Quellinhalt anwenden möchten. <br><li> **Ditaval File** Wählen Sie eine DITAVAL-Datei aus, um konditionalisierten Inhalt zu generieren. Klicken Sie zur Auswahl auf unter &quot;Bedingungsvorgabe&quot;und suchen Sie die Datei. <br> <li> **Bedingungsvorgabe** Wählen Sie eine Bedingungsvorgabe aus der Dropdown-Liste aus, um beim Veröffentlichen der Ausgabe eine Bedingung anzuwenden. Diese Option ist sichtbar, wenn Sie eine Bedingung für die DITA-Map-Datei hinzugefügt haben. Die bedingten Einstellungen sind auf der Registerkarte Bedingungsvorgaben der DITA-Zuordnungskonsole verfügbar. Weitere Informationen zur Bedingungsvorgabe finden Sie unter [Bedingungsvorgaben verwenden](https://help.adobe.com/en_US/xml-documentation-for-adobe-experience-manager/index.html#t=DXML-master-map%2Fgenerate-output-use-condition-presets.html) <br>. </ul> |
| **Grundlinie verwenden** | Wenn Sie eine Grundlinie für die ausgewählte DITA-Zuordnung erstellt haben, wählen Sie diese Option, um die Version anzugeben, die Sie veröffentlichen möchten. Weitere Informationen finden Sie unter [Arbeiten mit Grundlinie](https://help.adobe.com/en_US/xml-documentation-for-adobe-experience-manager/index.html#t=DXML-master-map%2Fgenerate-output-use-baseline-for-publishing.html) . |
| **PDF mit Änderungsleiste zwischen veröffentlichten Versionen erstellen** | Verwenden Sie die folgenden Optionen, um mithilfe von Änderungsleisten eine PDF zu erstellen, die die Inhaltsunterschiede zwischen zwei Versionen zeigt:   <br><ul><li> **Grundlinie der vorherigen Version** Wählen Sie die Grundlinienversion aus, die Sie mit der aktuellen Version oder einer anderen Grundlinie vergleichen möchten. Auf der PDF wird eine Änderungsleiste angezeigt, die den geänderten Inhalt angibt. Ein Änderungsbalken ist eine vertikale Linie, die neue oder überarbeitete Inhalte visuell identifiziert. Die Änderungsleiste wird links neben dem Inhalt angezeigt, der eingefügt, geändert oder gelöscht wurde. <br> **Hinweis**: Wenn Sie **Grundlinie verwenden** auswählen und eine Grundlinie für die Veröffentlichung auswählen, wird der Vergleich zwischen den beiden ausgewählten Grundversionen durchgeführt. Wenn Sie beispielsweise die Grundlinie Version 1.3 unter **Grundlinie verwenden** und Version 1.1 unter **Grundlinie der vorherigen Version** auswählen, wird der Vergleich zwischen der Grundlinie Version 1.1 und der Grundlinie Version 1.3 <br> durchgeführt.<li> **Hinzugefügten Text anzeigen** Wählen Sie diese Option, um den eingefügten Text in grüner Farbe und unterstrichen anzuzeigen. Diese Option ist standardmäßig ausgewählt. <br> <li> **Gelöschten Text anzeigen** Wählen Sie diese Option aus, um den gelöschten Text in roter Farbe anzuzeigen und mit einer Durchstreichung zu markieren. Standardmäßig ist diese Option aktiviert. <br>**Hinweis** Sie können die Formatierung der Änderungsleiste, des eingefügten Inhalts oder des gelöschten Inhalts auch mithilfe des Stylesheets anpassen.<br></ul> |
| **Workflow zur Post-Generierung** | Wählen Sie diese Option, um eine Dropdownliste mit allen in AEM konfigurierten Workflows anzuzeigen. Sie können den Workflow auswählen, der nach Abschluss des Workflows zur PDF-Generierung ausgeführt werden soll. |

**Metadaten**

Metadaten sind die Beschreibung oder Definition Ihres Inhalts. Metadaten helfen beim Content Management und beim Durchsuchen von Dateien im Internet.

Legen Sie auf der Registerkarte Metadaten die Metadatenfelder wie den Namen des Autors, den Dokumenttitel, Schlüsselwörter, Copyright-Informationen und andere Datenfelder für die PDF-Ausgabe fest. Sie können auch benutzerdefinierte Metadaten für Ihre PDF-Ausgabe hinzufügen.

Diese Metadaten werden den Metadaten auf der Registerkarte **Beschreibung** in den **Dokumenteigenschaften** Ihrer Ausgabe-PDF zugeordnet.



<img src="assets/pdf-metadata.png" alt="Metadaten-Registerkarte" width="600">

Wählen Sie in den Ausgabevorgaben **PDF** > **Native-PDF** > **Metadaten** aus, um Metadatenoptionen hinzuzufügen und anzupassen.
* **In topicmeta hinzugefügte Metadaten verwenden**

  Standardmäßig ist diese Option aktiviert. Sie können die Metadaten verwenden, die Sie im topicmeta-Element der DITA-Zuordnung hinzugefügt haben, um die Metadatenfelder der PDF-Ausgabe zu füllen.

* **Stellen Sie XMP Datei bereit**

  Sie können die Metadatenfelder auch direkt ausfüllen, indem Sie die Datei &quot;[XMP](https://www.adobe.com/products/xmp.html)&quot;(Extensible Metadata Platform) importieren. Hier können Sie eine XMP herunterladen.

[Herunterladen](assets/SampleXMP.xmp)

  Alternativ können Sie eine XMP mit Adobe Acrobat generieren.
   1. Klicken Sie in Acrobat auf **Datei** > **Eigenschaften** .
   1. Klicken Sie unter **Beschreibung** auf **Zusätzliche Metadaten**.
   1. Wählen Sie im linken Bereich **Erweitert** aus.
   1. Klicken Sie auf **Speichern**.

  XMP Datei wird auf dem Gerät gespeichert.

* **Geben Sie Metadatennamen und -werte an**

   1. Fügen Sie einen Namen hinzu, indem Sie aus der Dropdown-Liste auswählen, oder fügen Sie benutzerdefinierte Metadaten hinzu, indem Sie direkt in das Namensfeld eingeben.
   1. Geben Sie den Wert für die Metadaten ein und klicken Sie auf das Symbol &quot;+&quot;.
Die Metadaten werden der Metadatenliste für die PDF hinzugefügt.

Sie können auch Variablen verwenden, um die Metadatenwerte zu definieren.  Sie können die für die DITA-Map- oder Bookmap-Datei definierten Metadaten als Variablen verwenden. Die Metadaten finden Sie unter dem Knoten &quot;`/jcr:content/metadata`&quot;der DITA-Map- oder Bookmap-Datei.
Wenn Sie eine Variable verwenden, wird ihr Wert aus den Metadateneigenschaften ausgewählt.

Um eine Variable zu verwenden, müssen Sie sie im Format `${<variable>}` definieren.

Eine der Metadateneigenschaften, die im Knoten /`jcr:content/metadata` definiert sind, lautet beispielsweise
`dc:title` Sie können `${dc:title}` angeben und der Titelwert wird in der endgültigen Ausgabe verwendet.

Sie können eine einzelne oder eine Kombination von Variablen verwenden, um die Metadaten zu definieren. Beispiel: `${dc:title} ${dc:docstate}`. Sie können auch die Kombination aus einer Variablen und einer Zeichenfolge verwenden.  Zum Beispiel: `View ${dc:title} in ${dc:language}`.

Verwenden Sie Sprachvariablen, um den lokalisierten Wert der Metadateneigenschaften zu definieren. Abhängig von Ihrer ausgewählten Sprache wird der lokalisierte Wert automatisch in der PDF-Ausgabe ausgewählt. Beispielsweise können Sie &quot;Autor&quot;als Metadatenwert in Englisch und &quot;Autorin&quot;in Deutsch drucken.

Format: `${lng:<variable name>}`. Beispiel: `${lng:author-label}` , wobei `author-label` eine Sprachvariable ist.

Bewegen <img src="./assets/info-details.svg" alt= "Infosymbol" width="25"> in der Nähe der Option, um weitere Details dazu anzuzeigen.


**Layout**

Verwenden Sie , um Seitenlayouts festzulegen und Seitenansichtsoptionen für die PDF-Ausgabe wie Seitenanzeige festzulegen und Zoomstufen festzulegen.

| Einstellung | Beschreibung |
| --- | --- |
| **PDF-Vorlage** | PDF-Vorlagen bieten eine klare Struktur für die Definition von Seitenlayouts, Inhaltsstilen und die Anwendung verschiedener Einstellungen auf Ihre PDF-Ausgabe. Wählen Sie aus der Dropdown-Liste PDF-Vorlage die gewünschte Vorlage aus. <br> Sie können auch **Vorlage durchsuchen** auswählen <img src="./assets/browse-templates-icon.svg"  alt= "Symbol &quot;Vorlagen durchsuchen&quot;" width="25"> , um eine Vorlage auszuwählen. Im Dialogfeld **PDF-Vorlage auswählen** können Sie auch eine Vorschau der Miniaturansicht sowie den Titel und die Beschreibung der ausgewählten Vorlage anzeigen. |
| **Seitenanzeige** | Verwenden Sie die Seitenanzeige für die Seitenansicht, die anzeigt, wie die PDF beim Öffnen angezeigt wird. Wählen Sie aus den Dropdown-Optionen Seitenanzeige aus, um eine bevorzugte Ansicht auszuwählen. <br><ul><li> **Standard** Wird gemäß der Standardeinstellung des PDF-Viewers auf dem Computer eines Benutzers angezeigt.  <br> <li> **Einzelseitenansicht** Zeigt jeweils eine Seite an.   <br> <li> **Scrollen auf einer Seite** Zeigt eine einzelne Seite in einer vertikalen Spalte mit fortlaufenden Seitenumbrüchen an.  <br> <li> **Zwei Seitenansichten** Zeigt zwei Seiten gleichzeitig nebeneinander an. .<br> <li> **Zweiseitiger Bildlauf** Zeigt den Seitenumbruch auf zwei Seiten nebeneinander mit kontinuierlichem Bildlauf an. </ul> |
| **Zoom** | Wählen Sie diese Option aus, um die Seitenansicht zu ändern, die anzeigt, wie das PDF beim Öffnen angezeigt wird.  <br><ul><li> **Standard** Zeigt gemäß der Standardeinstellung des PDF-Viewers auf dem Computer eines Benutzers an    <br> <li> **100%** Legt fest, dass die Seite in ihrer tatsächlichen Größe angezeigt wird.     <br> <li> **Seite anpassen** Passt die Seitenbreite und -höhe in den Dokumentbereich ein.   .<br> <li> **Seitenbreite anpassen** Legt die Breite der Seite an die Breite des Dokumentbereichs fest.  <br> <li> **Seitenhöhe anpassen** Legt fest, dass die Höhe des Seitenausfüllens die Höhe des Dokumentfensters annimmt. </ul> |

**Sicherheit**

Protect Sie Ihre PDF, indem Sie Einschränkungen zum Öffnen und Lesen der Datei hinzufügen. Verwenden Sie die folgenden Optionen, um unbefugten Zugriff zu vermeiden.

| Einstellung | Beschreibung |
| --- | --- |
| **Kennwort zum Öffnen des Dokuments festlegen** | Klicken Sie auf , um ein sicheres Kennwort hinzuzufügen, um Ihre PDF-Datei anzuzeigen. Geben Sie im Feld **Benutzerkennwort** ein Kennwort an. Die PDF kann nur durch Eingabe des in diesem Feld angegebenen Kennworts geöffnet werden. |
| **Dokumenteinschränkungen festlegen** | Wählen Sie diese Option aus, um die Interaktion der Benutzer mit Ihrer PDF zu beschränken. Geben Sie ein Kennwort im Feld **Inhaber-Kennwort** an, damit die folgenden Einschränkungseinstellungen funktionieren.  <br><ul><li> **Drucken** Wählen Sie diese Option aus, damit ein Benutzer die PDF drucken kann. <br> <li> **Druck von Entwurfsqualität** Wählen Sie diese Option, damit ein Benutzer die PDF in einer niedrigeren Auflösung drucken kann.  <br> <li> **Kopieren von Inhalten** Wählen Sie diese Option aus, damit Benutzer Inhalte von der PDF kopieren können.   <br> <li> **Anmerkungen** Wählen Sie diese Option aus, damit Benutzer Notizen oder Kommentare zur PDF hinzufügen können. <br> <li> **Inhaltsänderungen** Wählen Sie diese Option aus, damit ein Benutzer den Inhalt auf der PDF ändern kann. <br> <li> **Kopieren von Inhalten für die Barrierefreiheit** Wählen Sie diese Option aus, damit Bildschirmlesehilfen Inhalte in PDF lesen und navigieren können. <br>  **Dokumentzusammenführung** Wählen Sie diese Option, damit Benutzer Seiten in die PDF einfügen können. <br> **Hinweis**: Die Benutzer müssen das Passwort des Eigentümers eingeben, um die Einschränkungen unter &quot;Datei&quot;> &quot;Eigenschaften&quot;in Adobe Acrobat zu ändern. |

**Erweitert**

Verwenden Sie die folgenden Optionen, um erweiterte Einstellungen zum Zusammenführen von PDF festzulegen, Komprimierung, Kompatibilitätsstandard usw. zu verwenden.

| Einstellung | Beschreibung |
| --- | --- |
| **Zugreifbare (getaggte) PDF** erstellen | Wählen Sie diese Option aus, um eine PDF mit Tags zu generieren. Eine getaggte PDF erleichtert Sprachausgaben das Lesen und Navigieren von Inhalten, Hyperlinks, Lesezeichen usw. Wenn beispielsweise eine Tabelle mit Tags versehen ist, weiß die Bildschirmlesehilfe, dass sie die Tabelle liest und nicht nur Zeilen und Text. |
| **Im TOC enthaltene PDF zusammenführen** | Wählen Sie diese Option, um vorhandene PDF in Ihrer Ausgabe zusammenzuführen, indem Sie sie Ihrer DITA-Map als Ressourcendatei hinzufügen. Die PDF werden an der Stelle eingefügt, die in der Karte dargestellt wird, und die Seiten werden entsprechend inkrementiert. |
| **Verwendete Schriftarten einbetten** | Aktivieren Sie diese Option bei der Verwendung von Schriftarten, die möglicherweise nicht auf dem Computer des Endbenutzers installiert sind. Wenn diese Option aktiviert ist, werden die verwendeten Schriftarten in die PDF eingebettet, sodass der Benutzer die PDF wie gewünscht sehen kann, selbst wenn die Schriftarten nicht auf seinem Computer installiert sind. <br> **Hinweis**: Eine Schrift kann nur eingebettet werden, wenn sie eine Einstellung des Schriftartanbieters enthält, die die Einbettung dieser Schrift ermöglicht. Stellen Sie sicher, dass Sie über die erforderliche Einstellung oder Lizenz verfügen, bevor Sie eine Schriftart einbetten. |
| **Automatische Silbentrennung verwenden** | Wenn die automatische Silbentrennung aktiviert ist, werden die Wörter am Zeilenende mit einem Bindestrich an grammatisch korrekten Stellen umbrochen. |
| **JavaScript aktivieren** | Aktivieren Sie diese Option, wenn Sie über einen JavaScript-Code verfügen, den Sie verwenden möchten, um Ihren Inhalt dynamisch umzuwandeln, bevor Sie eine PDF generieren. |
| **Einbetten von Multimediadateien** | Wählen Sie diese Option aus, um Audio, Video und interaktive Inhalte in die PDF aufzunehmen. |
| **Verwenden Sie die vollständige Komprimierung, um die PDF-Größe zu optimieren** | Wählen Sie diese Option aus, wenn Sie die Größe einer großen PDF komprimieren/verringern möchten. Beachten Sie, dass das Komprimieren des PDF die Dateiqualität beeinträchtigen kann. |
| **Verwenden Sie die Bildkomprimierung, um die PDF-Größe zu optimieren** | Wählen Sie diese Option aus, wenn Sie die Größe der verwendeten Bilder in Ihrer PDF komprimieren/reduzieren möchten. Beachten Sie, dass das Komprimieren eines Bildes die Bildqualität beeinträchtigen kann. |
| **Verwenden Sie die benutzerdefinierte Auflösung (Pixel pro Zoll)** | Dies ist die Seitenanzeigeauflösung in Pixel pro Zoll. Geben Sie einen bevorzugten Wert in das Feld ein, das bei Auswahl dieser Option angezeigt wird. Der Standardwert ist 96 Pixel pro Zoll. Legen Sie einen höheren Wert fest, um mehr Inhalt in Zoll einzupassen, und umgekehrt, wenn Sie einen niedrigeren Wert festlegen. |
| **Wasserzeichen anzeigen** | Wählen Sie diese Option, um ein Wasserzeichen in der Ausgabe zu überlagern. Sie können eine neue Textzeichenfolge in das Textfeld eingeben, wobei das Zeichen wie gewünscht Groß-/Kleinschreibung verwendet wird. <br><br>Verwenden Sie statischen Text oder Sprachvariablen, um die lokalisierte Version des Wasserzeichens zu veröffentlichen.  Abhängig von Ihrer ausgewählten Sprache wird der lokalisierte Wert automatisch in der PDF-Ausgabe ausgewählt. Beispielsweise können Sie &quot;Publisher&quot;als Wasserzeichen auf Englisch und &quot;Auteure&quot;auf Französisch drucken.  <br> Format: `${lng:<variable name>}`. Beispiel: `$ {lng:publisher-label}` , wobei `publisher-label` eine Sprachvariable ist. <br> Bewegen Sie den Mauszeiger über <img src="./assets/info-details.svg" alt= "Infosymbol" width="25"> in der Nähe der Option, um weitere Details dazu anzuzeigen. |
| **Mathematische Gleichungen aktivieren** | Wählen Sie diese Option, um die in Ihrem Inhalt vorhandenen MathML-Gleichungen zu rendern. Die Gleichungen werden standardmäßig ignoriert. |
| **Temporäre Dateien herunterladen** | Wählen Sie diese Option aus, wenn Sie die Zwischendatei-HTML herunterladen möchten, die beim Generieren der nativen PDF-Ausgabe erstellt wurde. Sie können die temporären Dateien später herunterladen, nachdem Sie die Ausgabe generiert haben. |
| **PDF-Konformität** | Dies ist der Standard, den Sie speichern möchten, um sicherzustellen, dass Ihre PDF konform ist. Wählen Sie aus der Dropdown-Liste aus, um aus der Liste der verfügbaren PDF-Standards auszuwählen. Weitere Informationen zu den unterstützten Standards finden Sie unter [Über PDF-Standards](https://helpx.adobe.com/acrobat/using/pdf-conversion-settings.html#about_pdf_x_pdf_e_and_pdf_a_standards). |
| **Dateieigenschaften** | Wählen Sie die Metadaten aus, die Sie an die native PDF-Veröffentlichung übergeben möchten. In der Dropdown-Liste werden sowohl die benutzerdefinierten als auch die Standardeigenschaften aufgeführt. Beispielsweise sind `dc:description`, `dc:language`, `dc:title` und `docstate` die Standardeigenschaften, während Sie `author` als benutzerdefinierte Eigenschaft haben können. Die ausgewählten Metadateneigenschaften werden an die PDF-Datei übergeben, die mithilfe des nativen PDF generiert wurde. <br> Diese Eigenschaften werden aus der `metadataList`-Datei ausgewählt, die unter:`/libs/fmdita/config/metadataList` verfügbar ist. <br>Diese Datei kann überlagert werden unter: `/apps/fmdita/config/metadataList`. |


## Generieren einer PDF-Ausgabe {#generate-pdf-output}

Nachdem Sie die Ausgabevorgabe konfiguriert haben, können Sie mithilfe der Funktion **Vorgabe generieren** die Ausgabe aus dem Bereich &quot;Vorgaben&quot;generieren.

1. Wählen Sie auf der Registerkarte **Autor** die Ansicht **Repository** aus.\
   Dadurch wird das Repository-Bedienfeld geöffnet.

1. Öffnen Sie im Bereich &quot;Repository&quot;die DITA-Zuordnungsdatei in der **Zuordnungsansicht**.

1. Klicken Sie auf der Registerkarte **Ausgabe** auf **Vorgaben** , um den Bereich &quot;Voreingestellt&quot;anzuzeigen.
Informationen zum Erstellen oder Konfigurieren einer Ausgabevorgabe finden Sie unter [Erstellen einer PDF-Ausgabevorgabe](#create-output-preset).
1. Um Ihre Einstellungen zu speichern, klicken Sie auf das Symbol **Alle speichern** ![Alle speichern](assets/SaveFloppy_icon.svg) in der oberen linken Ecke der Standardsymbolleiste in der Ausgabeansicht.
1. Klicken Sie in der oberen Leiste auf das Symbol **Vorgabe generieren** ![Vorgabe generieren](assets/generate-output.svg) .
Sie können eine Fortschrittsleiste neben der ausgewählten Ausgabevorgabe im Bedienfeld Ausgabevorgaben anzeigen.
1. Nachdem die Ausgabegenerierung abgeschlossen ist, klicken Sie in der oberen Leiste auf das Symbol **Ausgabe anzeigen** ![Ausgabe anzeigen](assets/view-output.svg) , um die Ausgabe anzuzeigen.\
   Das Dialogfeld &quot;**Erfolg**&quot; wird in der rechten unteren Ecke des Bildschirms angezeigt.
Wenn eine Ausgabe nicht erfolgreich ist, wird die folgende Fehlermeldung angezeigt.
<img src="assets/error-log.png" alt="Fehlerprotokoll" width="250">

Um das Fehlerprotokoll anzuzeigen, klicken Sie auf &quot;**Beenden**&quot;, bewegen Sie den Mauszeiger über die ausgewählte Vorgabe und klicken Sie auf &quot;![options](assets/options.svg) **Options**&quot;> &quot;**Protokoll anzeigen**&quot;.

### Herunterladen temporärer Dateien nach der Generierung der nativen PDF-Ausgabe

Wenn Sie in den erweiterten HTML-Einstellungen die Option **Temporäre Dateien herunterladen** auswählen, können Sie auch die Zwischendateien herunterladen, die beim Generieren der nativen PDF-Ausgabe erstellt wurden. Nachdem Sie die Ausgabe generiert haben, können Sie die temporären Dateien mit dem Symbol **Temporäre Dateien herunterladen** ![ Temporäre Dateien herunterladen](assets/native-pdf-download-temporary-files-icon.svg) in der oberen Leiste herunterladen. Diese Funktion hilft Ihnen beim Anzeigen Ihrer vorläufigen HTML-Stile und Layouts und hilft Ihnen, Ihre CSS-Stile gemäß Ihren Anforderungen zu korrigieren oder zu ändern.


>[!NOTE]
>
> Das Symbol **Temporäre PDF-Dateien herunterladen** ![ Temporäre Dateien herunterladen](assets/native-pdf-download-temporary-files-icon.svg) wird nur angezeigt, wenn Sie die letzte-Ausgabe mithilfe der Vorgabe generiert haben, in der Sie die Option auf der Registerkarte **Erweitert** ausgewählt haben.



### Sprachvariablen verwenden

AEM Guides unterstützt auch Sprachvariablen. Wählen Sie **Sprachvariablen** aus <img src="./assets/language-variables.svg" width="25"> im linken Bereich, um eine lokalisierte Version der vordefinierten Beschriftungen wie Hinweis, Vorsicht und Warnung oder statischer Text in der PDF-Ausgabe zu definieren. Weitere Informationen finden Sie unter [Unterstützung für Sprachvariablen](../native-pdf/native-pdf-language-variables.md).



### Unterstützung für Markdown-Dokumente

Experience Manager Guides unterstützt auch Ihre Markdown-Dokumente.  Markdown-Dateien sind einfach zu erstellen und
bietet eine Vielzahl von Formatierungsoptionen. Erfahren Sie, wie Sie [Markdown-Dokumente aus dem Web Editor erstellen](../user-guide/web-editor-markdown-topic.md).

Sie können die Markdown-Themen zu Ihrer DITA-Zuordnung hinzufügen und die PDF-Ausgabe mithilfe der nativen PDF-Ausgabevorgaben generieren.  Erfahren Sie, wie Sie eine PDF-Ausgabevorgabe konfigurieren oder [erstellen.](#create-a-pdf-output-preset-create-output-preset)