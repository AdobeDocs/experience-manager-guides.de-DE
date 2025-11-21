---
title: Native PDF | Generieren von PDF-Ausgaben
description: Erfahren Sie, wie Sie die native PDF-Veröffentlichung verwenden, eine PDF-Ausgabevorgabe erstellen und generieren, temporäre Dateien nach der Generierung der nativen PDF-Ausgabe herunterladen und Sprachvariablen in Adobe Experience Manager Guides verwenden.
exl-id: ec3d59b7-1dda-4fd1-848e-21d8a36ff5e4
feature: Publishing, Native PDF Output
role: User
source-git-commit: 6e23f52fc9124d0f07f8108da1b5fe574f553469
workflow-type: tm+mt
source-wordcount: '3232'
ht-degree: 1%

---

# Native PDF-Ausgabevorgabe

Beim Erstellen von Inhalten ist es wichtig sicherzustellen, dass die Inhalte für die Anzeige, Bearbeitung und das Drucken optimiert sind. Mithilfe von Standards wie dem W3C CSS3 für die Inhaltsformatierung und CSS-Seitenmedienstandards für Seitendefinitionseigenschaften wie Größe, Ränder, Ausrichtung, Seitenumbrüche, Kopfzeilen, Fußzeilen und Seitennummerierung können Sie die Ansicht und das Layout für Ihr PDF-Dokument festlegen, um Konsistenz und Benutzerfreundlichkeit zu gewährleisten. Die native PDF-Veröffentlichungsfunktion verwendet diese Standards, um eine PDF zu generieren.

Mit der nativen PDF-Veröffentlichung können Sie vordefinierte Vorlagen verwenden, um die Konsistenz des Inhalts-Layouts und der Struktur sicherzustellen, Stylesheets anwenden, um das Erscheinungsbild Ihrer Ausgabe zu ändern, PDF zu optimieren, Druckermarken festzulegen, Unterstützung für Bildschirmlesehilfen zuzulassen, PDF-Konformität festzulegen, Schriftarten einzubetten und vieles mehr.

Das Generieren einer PDF mit der nativen PDF-Veröffentlichung hat zwei Aspekte:

* Verwendung von Vorlagen zum Anwenden von Stilen auf Inhalte, Festlegen von Seiten-Layouts und verschiedenen Einstellungen zur Feinabstimmung Ihrer PDF. Autoren können die bereitgestellten Beispielvorlagen verwenden/ändern oder benutzerdefinierte Vorlagen erstellen und erweiterte Konfigurationsoptionen festlegen, die von Herausgebern und Entwicklern verwendet werden.

* Erstellen oder konfigurieren Sie eine PDF-Ausgabevorgabe, um die PDF-Einstellungen zu steuern. Nachdem Sie eine PDF-Ausgabevorgabe erstellt haben, können Sie die PDF generieren.

## Erstellen einer Ausgabevorgabe

Führen Sie die folgenden Schritte aus, um die PDF-Voreinstellung über die Zuordnungskonsole zu erstellen:

1. [Öffnen Sie eine DITA-Zuordnungsdatei in der Zuordnungskonsole](../user-guide/open-files-map-console.md).

   Sie können auf die Zuordnungsdatei auch über das Widget **Letzte Dateien** im Abschnitt [Übersicht](../user-guide/intro-home-page.md#overview) zugreifen. Die ausgewählte Zuordnungsdatei wird dann in der Zuordnungskonsole geöffnet.
1. Klicken **auf der Registerkarte** Ausgabevorgaben“ auf das Symbol + , um eine Ausgabevorgabe zu erstellen.
1. Wählen Sie **PDF** aus der Dropdown-Liste Typ im Dialogfeld **Neue**) aus.
1. Geben Sie **Feld** einen Namen für diese Voreinstellung ein.
1. Wählen Sie im Feld **PDF generieren mit** die Option **Native-PDF**.
1. Wählen Sie die **Zum aktuellen Ordnerprofil hinzufügen**, um eine Ausgabevorgabe innerhalb des aktuellen Ordnerprofils zu erstellen. Das ![Ordnerprofilsymbol](./assets/global-preset-icon.svg) gibt eine Vorgabe auf Ordnerprofilebene an.

   Weitere Informationen zu [Verwalten globaler und Ordnerprofil-Ausgabevorgaben](../user-guide/web-editor-manage-output-presets.md).

1. Wählen Sie **Hinzufügen** aus.

   Die Voreinstellung für PDF wird erstellt.

## Native Konfiguration der PDF-Voreinstellung

Nachdem die Vorgabe erstellt wurde, konfigurieren Sie die nativen Vorgabeneinstellungen für PDF. Die voreingestellten Konfigurationsoptionen für DITA-OT sind auf den Registerkarten **Allgemein**, **Metadaten**, **Layout**, **Sicherheit**, **Drucken** und **Erweitert**.

<img src="assets/preset-panel-new.png" alt="Voreinstellungsfenster" width="800">

**Allgemein**

Verwenden Sie diese Option, um grundlegende Ausgabeeinstellungen anzugeben, z. B. den Ausgabepfad, den PDF-Dateinamen und mehr.

| Einstellung | Beschreibung |
| --- | --- |
| **Ausgabepfad** | Der Pfad innerhalb des AEM-Repositorys, in dem die PDF-Ausgabe gespeichert wird. Stellen Sie sicher, dass sich der Ausgabepfad nicht im Projektordner befindet. Der Ausgabepfad wird über die Variable `${base_output_path}` festgelegt, die vom Administrator konfiguriert wird. Um den Ausgabepfad zu konfigurieren, zeigen Sie [Basisausgabespeicherort für Cloud-Services konfigurieren](../native-pdf/configure-base-location-cs.md) oder [Basisausgabespeicherort für On-Premise-Services konfigurieren](../native-pdf/configure-base-output-location.md) basierend auf dem von Ihnen verwendeten Service an. <br>Sie können auch die folgenden vordefinierten Variablen verwenden, um den Ausgabepfad zu definieren. Sie können eine einzelne oder eine Kombination von Variablen verwenden, um diese Option zu definieren. <br> `${map_filename}`: Verwendet den Namen der DITA-Zuordnungsdateien , um den Zielpfad zu erstellen. <br> `${map_title}`: Verwendet den Titel der DITA-Zuordnung, um den Zielpfad zu erstellen. <br>`${preset_name}`: Verwendet den Namen der Ausgabevorgabe, um den Zielpfad zu erstellen. <br> `${language_code}`: Verwendet den Sprach-Code, in dem sich die Zuordnungsdatei befindet, um den Zielpfad zu erstellen. <br> `${map_parentpath}`: Verwendet den vollständigen Pfad der Zuordnungsdatei, um den Zielpfad zu erstellen.  <br>`${path_after_langfolder}`: Verwendet den Pfad der Zuordnungsdatei nach dem Sprachordner, um den Zielpfad zu erstellen. |
| **PDF-** | Geben Sie einen Dateinamen an, um die PDF zu speichern. Standardmäßig fügt der PDF-Dateiname den DITA-Zuordnungsnamen zusammen mit dem Vorgabenamen hinzu. Beispielsweise lautet „ditamap“ „TestMap“ und der Name der Vorgabe lautet „preset1“. Der Standardname der PDF-Datei lautet dann „TestMap_preset1.pdf“. <br>Sie können auch die folgenden vordefinierten Variablen verwenden, um die PDF-Datei zu definieren. Sie können eine einzelne oder eine Kombination von Variablen verwenden, um diese Option zu definieren. <br>`${map_filename}`<br>`${map_title}`<br>`${preset_name}` <br> `${language_code}`. |
| **Bedingungen anwenden mit** | Wählen Sie für bedingte Inhalte eine der folgenden Optionen, um eine PDF-Ausgabe basierend auf diesen Bedingungen zu generieren: <br><ul> <li> **Keine angewendet** Wählen Sie diese Option aus, wenn Sie keine Bedingung auf die Zuordnung und den Quellinhalt anwenden möchten. <br><li> **DITAVAL-Datei** Wählen Sie eine DITAVAL-Datei aus, um bedingte Inhalte zu generieren. Sie können mehrere DITAVAL-Dateien auswählen, indem Sie entweder das Durchsuchen-Dialogfeld verwenden oder den Dateipfad manuell eingeben. Um eine ausgewählte Datei zu entfernen, klicken Sie auf das Kreuzsymbol neben dem Namen der Datei. Wenn eine ungültige Datei ausgewählt ist, wird eine Fehlermeldung angezeigt, die besagt **Ungültige DITAVAL-Datei ist ausgewählt**. <br> <br>Jede DITAVAL-Datei kann eine Reihe von Eigenschaften enthalten, z. B. Filterbedingungen und Kennzeichnungsstile. Mit einer Markierung können Sie Inhalte mit Start- und End-Flags visuell markieren, z. B. mit Bildern oder Textformatierung wie fett oder kursiv. Bei sich überschneidenden Bedingungen oder Stilkonflikten können Sie mit den Einstellungen für Stilkonflikte eine Hintergrundfarbe definieren. Weitere Informationen finden Sie unter [Verwenden des DITAVAL-Editors](../user-guide/ditaval-editor.md).<br><li> **Bedingungsvorgabe** Wählen Sie in der Dropdown-Liste eine Bedingungsvorgabe aus, um eine Bedingung beim Veröffentlichen der Ausgabe anzuwenden. Diese Option ist sichtbar, wenn Sie eine Bedingung für die DITA-Zuordnungsdatei hinzugefügt haben. Die bedingten Einstellungen sind auf der Registerkarte „Bedingungsvorgaben“ der DITA-Zuordnungskonsole verfügbar. Weitere Informationen zu Bedingungsvorgaben finden Sie unter [Verwenden von Bedingungsvorgaben](https://help.adobe.com/en_US/xml-documentation-for-adobe-experience-manager/index.html#t=DXML-master-map%2Fgenerate-output-use-condition-presets.html). <br> </ul> |
| **Baseline verwenden** | Wenn Sie eine Baseline für die ausgewählte DITA-Map erstellt haben, wählen Sie diese Option, um die Version anzugeben, die Sie veröffentlichen möchten. Weitere [&#x200B; finden Sie unter „Arbeiten mit &#x200B;](https://help.adobe.com/en_US/xml-documentation-for-adobe-experience-manager/index.html#t=DXML-master-map%2Fgenerate-output-use-baseline-for-publishing.html)&quot;. |
| **Erstellen von PDF mit Änderungsleiste zwischen veröffentlichten Versionen** | Verwenden Sie die folgenden Optionen, um mithilfe von Änderungsleisten eine PDF zu erstellen, die die Inhaltsunterschiede zwischen zwei Versionen anzeigt:   <br><ul><li> **Baseline der vorherigen Version** Wählen Sie die Baseline-Version aus, die Sie mit der aktuellen Version oder einer anderen Baseline vergleichen möchten. Eine Änderungsleiste wird in der PDF angezeigt, um den geänderten Inhalt anzuzeigen. Eine Änderungsleiste ist eine vertikale Linie, die neue oder überarbeitete Inhalte visuell identifiziert. Die Änderungsleiste wird auf der linken Seite des Inhalts angezeigt, der eingefügt, geändert oder gelöscht wurde. <br> **Hinweis**: Wenn Sie **Baseline verwenden** und eine Baseline zur Veröffentlichung auswählen, wird der Vergleich zwischen den beiden ausgewählten Baseline-Versionen durchgeführt. Wenn Sie beispielsweise Baseline Version 1.3 unter **Baseline verwenden** und Version 1.1 unter **Baseline der vorherigen Version** auswählen, wird der Vergleich zwischen der Baseline Version 1.1 und der Baseline Version 1.3 durchgeführt. <br><li> **Hinzugefügten Text anzeigen** Wählen Sie diese Option aus, um den eingefügten Text grün und unterstrichen anzuzeigen. Diese Option ist standardmäßig ausgewählt. <br> <li> **Gelöschten Text anzeigen** Wählen Sie diese Option aus, um den gelöschten Text rot und mit einem Durchgestrichen anzuzeigen. Standardmäßig ist diese Option aktiviert. <br>**Hinweis** Sie können auch den Stil der Änderungsleiste, des eingefügten Inhalts oder des gelöschten Inhalts mithilfe des Stylesheets anpassen.<br></ul> |
| **Workflow nach der Generierung** | Wählen Sie diese Option aus, um eine Dropdown-Liste anzuzeigen, die alle in AEM konfigurierten Workflows enthält. Sie können den Workflow auswählen, der nach Abschluss des PDF-Generierungs-Workflows ausgeführt werden soll. |

**Metadaten**

Metadaten sind die Beschreibung oder Definition Ihres Inhalts. Metadaten helfen beim Content-Management und bei der Suche nach Dateien im Internet.

Verwenden Sie die Registerkarte Metadaten , um die Metadatenfelder wie den Namen des Autors, den Dokumenttitel, Schlüsselwörter, Copyright-Informationen und andere Datenfelder für die PDF-Ausgabe festzulegen. Sie können auch benutzerdefinierte Metadaten für Ihre PDF-Ausgabe hinzufügen.

Diese Metadaten werden den Metadaten auf der Registerkarte **Beschreibung** in den **Dokumenteigenschaften** Ihrer Ausgabe-PDF zugeordnet.



<img src="assets/pdf-metadata.png" alt="Registerkarte Metadaten" width="600">

Wählen Sie aus den Ausgabevorgaben **PDF** > **Native-PDF** > **Metadaten** aus, um Metadatenoptionen hinzuzufügen und anzupassen.
* **Verwenden von in TopicMeta hinzugefügten Metadaten**

  Standardmäßig ist diese Option aktiviert. Sie können die Metadaten verwenden, die Sie im TopicMeta-Element der DITA-Zuordnung hinzugefügt haben, um die Metadatenfelder der PDF-Ausgabe zu befüllen.

* **XMP-Datei bereitstellen**

  Sie können die Metadatenfelder auch direkt ausfüllen, indem Sie die Datei [XMP](https://www.adobe.com/products/xmp.html) (Extensible Metadata Platform) importieren. Hier können Sie eine Beispieldatei für XMP herunterladen.

[Herunterladen](assets/SampleXMP.xmp)

  Alternativ können Sie mit Adobe Acrobat eine XMP-Datei generieren.
   1. Wählen Sie **Datei** > **Eigenschaften** in Acrobat.
   1. Wählen **unter** die Option **Zusätzliche Metadaten** aus.
   1. Wählen Sie im linken Bedienfeld die Option **Erweitert** aus.
   1. Wählen Sie **Speichern** aus.

  XMP-Datei wird auf dem Gerät gespeichert.

* **Geben Sie Metadatennamen und -werte an**

   1. Fügen Sie einen Namen hinzu, indem Sie ihn aus der Dropdown-Liste auswählen, oder fügen Sie benutzerdefinierte Metadaten hinzu, indem Sie ihn direkt in das Namensfeld eingeben.
   1. Geben Sie den Wert für die Metadaten ein und wählen Sie das Symbol &quot;+&quot; aus.
Die Metadaten werden der Liste der Metadaten für die PDF hinzugefügt.

Sie können Variablen auch verwenden, um die Metadatenwerte zu definieren.  Sie können die für die DITA-Map- oder Bookmap-Datei definierten Metadaten als Variablen verwenden. Die Metadaten befinden sich unter dem Knoten `/jcr:content/metadata` der DITA-Map- oder Bookmap-Datei.
Wenn Sie eine Variable verwenden, wird deren Wert aus den Metadateneigenschaften ausgewählt.

Um eine Variable zu verwenden, müssen Sie sie im `${<variable>}`-Format definieren.

Eine der im Knoten /`jcr:content/metadata` definierten Metadateneigenschaften ist beispielsweise
`dc:title`. Sie können `${dc:title}` angeben, und der Wert des Titels wird in der endgültigen Ausgabe verwendet.

Sie können eine einzelne oder eine Kombination von Variablen zum Definieren der Metadaten verwenden. Beispiel: `${dc:title} ${dc:docstate}`. Sie können auch die Kombination einer Variablen und einer Zeichenfolge verwenden.  Zum Beispiel: `View ${dc:title} in ${dc:language}`.

Verwenden Sie Sprachvariablen, um den lokalisierten Wert von Metadateneigenschaften zu definieren. Je nach Sprache wird der lokalisierte Wert automatisch in der PDF-Ausgabe ausgewählt. Sie können beispielsweise „Author“ als Metadatenwert auf Englisch und „Author“ auf Deutsch drucken.

Format: `${lng:<variable name>}`. Beispiel: `${lng:author-label}`, wobei `author-label` eine Sprachvariable ist.

Bewegen Sie den Mauszeiger über <img src="./assets/info-details.svg" alt= "Infosymbol" width="25"> in der Nähe der Option, um weitere Details dazu anzuzeigen.


**Layout**

Verwenden Sie , um Seitenlayouts festzulegen und Seitenansichtsoptionen für die PDF-Ausgabe anzugeben, z. B. Seitenanzeige und Zoomstufen.

| Einstellung | Beschreibung |
| --- | --- |
| **PDF-Vorlage** | PDF-Vorlagen bieten eine klare Struktur für die Definition von Seiten-Layouts, Inhaltsstilen und die Anwendung verschiedener Einstellungen auf Ihre PDF-Ausgabe. Wählen Sie aus der Dropdown-Liste PDF-Vorlage die gewünschte Vorlage aus. <br> Sie können auch &quot;**durchsuchen“** <img src="./assets/browse-templates-icon.svg"  alt= "Vorlagensymbol durchsuchen" width="25"> wählen Sie eine Vorlage aus. Im Dialogfeld **PDF-Vorlage auswählen** können Sie auch eine Vorschau der Miniaturansicht sowie den Titel und die Beschreibung der ausgewählten Vorlage anzeigen. |
| **Seitenanzeige** | Verwenden Sie die Seitenanzeige für die Seitenansicht, die anzeigt, wie die PDF angezeigt wird, wenn sie geöffnet wird. Wählen Sie aus den Dropdown-Optionen Seitenanzeige aus, um eine bevorzugte Ansicht auszuwählen. <br><ul><li> **Standard** Wird gemäß der Standardeinstellung des PDF-Viewers auf dem Computer eines Benutzers angezeigt.  <br> <li> **Einzelseitenansicht** Zeigt jeweils eine Seite an.   <br> <li> **Einzelseitenscrollen** Zeigt eine einzelne Seite in einer kontinuierlichen vertikalen Spalte an.  <br> <li> **Zwei Seitenansichten** Zeigt zwei Seiten nebeneinander an. .<br> <li> **Zwei Seiten scrollen** Zeigt zwei Seiten nebeneinander mit kontinuierlichem Scrollen an. </ul> |
| **Zoom** | Wählen Sie diese Option aus, um die Größe der Seitenansicht zu ändern, die anzeigt, wie die PDF beim Öffnen angezeigt wird.  <br><ul><li> **Standard** Wird gemäß der Standardeinstellung des PDF-Viewers auf dem Computer eines Benutzers angezeigt    <br> <li> **100%** Lässt die Seite in ihrer tatsächlichen Größe erscheinen.     <br> <li> **Seite anpassen** Passt die Seitenbreite und -höhe an den Dokumentbereich an.   .<br> <li> **Seitenbreite anpassen** Legt fest, dass die Breite der Seite mit der Breite des Dokumentbereichs gefüllt wird.  <br> <li> **Seitenhöhe anpassen** Legt fest, dass die Höhe der Seite mit der Höhe des Dokumentbereichs gefüllt wird. </ul> |

**Sicherheit**

Schützen Sie Ihre PDF, indem Sie Einschränkungen zum Öffnen und Lesen der Datei hinzufügen. Verwenden Sie die folgenden Optionen, um nicht autorisierten Zugriff zu verhindern.

| Einstellung | Beschreibung |
| --- | --- |
| **Kennwort festlegen, um das Dokument zu öffnen** | Wählen Sie aus, um ein sicheres Kennwort hinzuzufügen, damit Ihre PDF-Datei angezeigt wird. Geben Sie ein Kennwort in das Feld **Benutzerkennwort** ein. Benutzende können die PDF nur öffnen, indem sie das in diesem Feld angegebene Kennwort eingeben. |
| **Dokumenteinschränkungen festlegen** | Wählen Sie diese Option aus, um einzuschränken, wie Benutzende mit Ihrer PDF interagieren können. Geben Sie im Feld **Besitzer-Kennwort** ein Kennwort ein, damit die folgenden Einschränkungseinstellungen funktionieren.  <br><ul><li> **Drucken** Wählen Sie diese Option aus, damit ein Benutzer die PDF drucken kann. <br> <li> **Drucken in Entwurfsqualität** Wählen Sie diese Option aus, damit ein Benutzer die PDF in einer niedrigeren Auflösung drucken kann.  <br> <li> **Inhaltskopie** Wählen Sie diese Option aus, damit Benutzende Inhalte aus der PDF kopieren können.   <br> <li> **Anmerkungen** Wählen Sie diese Option aus, damit ein Benutzer eine Anmerkung oder einen Kommentar in der PDF hinzufügen kann. <br> <li> **Inhaltsänderungen** Wählen Sie diese Option aus, damit Benutzende den Inhalt in der PDF ändern können. <br> <li> **Kopieren von Inhalten für Barrierefreiheit** Wählen Sie diese Option aus, damit Bildschirmlesehilfen Inhalte in PDF lesen und darin navigieren können. <br>  **Dokumentzusammenstellung** Wählen Sie diese Option aus, damit Benutzende Seiten in die PDF einfügen können. <br> **Hinweis**: Benutzende müssen das Besitzerkennwort eingeben, um die Einschränkungen in Adobe Acrobat unter Datei > Eigenschaften zu ändern. |

**Drucken**

>[!NOTE]
>
> Ab Experience Manager Guides Version 5.0/2025.02.0 ist der Druckabschnitt jetzt Teil der **nativen PDF-Ausgabevorgabe**. Bei den vorhandenen Vorlagen mit gespeicherten Druckeinstellungen bleiben die Druckdaten intakt, werden jedoch während der Ausgabe nicht mehr in der Benutzeroberfläche angezeigt oder angewendet. Um diese Einstellungen weiterhin verwenden zu können, müssen Sie sie in der nativen PDF-Ausgabevorgabe neu konfigurieren.

Konfigurieren Sie die Druckproduktionseinstellungen, um Druckermarken zuzuweisen, Farbmodelle auszuwählen und Eigenschaften im Zusammenhang mit dem Drucken Ihrer PDF-Ausgabe anzugeben.

* **Druckermarken**: Wenn Sie ein Dokument für die Druckproduktion vorbereiten, werden Druckermarken zu den Seitenbegrenzungen hinzugefügt, um die korrekte Ausrichtung, das Zuschneiden und die Farbauswahl beim Drucken zu unterstützen. Durch Auswahl einer Druckermarke wird die Seitenbegrenzung erweitert, um die Markierung aufzunehmen, die beim Drucken gekürzt wird. Sie können die folgenden Druckermarkierungen in Ihrer PDF-Ausgabe anzeigen:
   * **Beschneidungsmarken**: Wählen Sie diese Option, um eine Markierung an jeder Ecke des Beschneidungsbereichs zu platzieren, um anzugeben, wo das Papier nach dem Drucken beschnitten werden soll.
   * **Anschnittzeichen**: Aktivieren Sie diese Option, um eine Markierung an jeder Ecke des Anschnittrahmens zu platzieren und den Zuschnittbereich für das erweiterte Bild anzugeben.
   * **Registrierungsmarken**: Wählen Sie diese Option, um eine Markierung außerhalb des Zuschnittsbereichs zu platzieren, um die verschiedenen Trennzeichen in einem Farbdokument auszurichten.
   * **Farbbalken**: Wählen Sie diese Option, um einen Farbstreifen außerhalb des Endformatbereichs hinzuzufügen, um die Farbkonsistenz beizubehalten und die Tintendichte beim Drucken anzupassen.

  Legen Sie die Abmessungen für die ausgewählten Druckermarkierungen mithilfe der Optionen **Linienbreite**, **Linienfarbe** und **Anschnittrahmenbreite** fest.

* **Medienfeldgröße**: Dies ist die Gesamtgröße der Seite einschließlich des erweiterten Bereichs, der von Druckermarken belegt wird. Verwenden Sie die Dropdown-Option, um die Seitengröße für die PDF-Ausgabe auszuwählen oder eine eigene benutzerdefinierte Größe zu erstellen.

* **Farbraum**: Sie haben die Möglichkeit, zum Drucken Ihres PDF-Dokuments zwischen RGB- oder CMYK-Farbräumen zu wählen. Wählen Sie RGB aus, um den generierten PDF digital anzuzeigen, und CMYK für den physischen Druck. Im Dokument definierte Farben werden in den ausgewählten Farbraum konvertiert.

* **ICC-Profil**: Hier können Sie die Farbgenauigkeit auf allen Geräten verwalten, indem Sie ein ICC-Profil angeben. Dies gewährleistet eine konsistente Farbwiedergabe in der Druckausgabe.

Um diese Einstellung zu konfigurieren, geben Sie den ICC-Profildateipfad auf Ihrem Server an und geben Sie den ICC-Profilnamen für eine einfache Identifizierung an. Wenn das ICC-Profil online gespeichert wird, können Sie alternativ dessen URL anstelle des Dateipfads angeben.

>[!NOTE]
>
> Bei Verwendung von CMYK-Farbraum ist ein ICC-Farbprofil für die PDF/A-Erstellung erforderlich.

<!--For more information on applying these print settings, see *Printing preferences*.-->

**Erweitert**

Verwenden Sie die folgenden Optionen, um erweiterte Einstellungen zum Zusammenführen von PDFs, zum Verwenden der Komprimierung, zum Auswählen eines Kompatibilitätsstandards und mehr anzugeben.

| Einstellung | Beschreibung |
| --- | --- |
| **Erstellen einer barrierefreien (getaggten) PDF** | Wählen Sie diese Option aus, um eine PDF mit Tags zu generieren. Eine getaggte PDF erleichtert Sprachausgaben das Lesen und Navigieren in Inhalten, Hyperlinks, Lesezeichen usw. Wenn beispielsweise eine Tabelle mit Tags versehen ist, weiß die Bildschirmlesehilfe, dass sie die Tabelle liest und nicht nur Zeilen und Text. |
| **Zusammenführen von im Inhaltsverzeichnis enthaltenen PDFs** | Wählen Sie diese Option, um vorhandene PDFs in Ihrer Ausgabe zusammenzuführen, indem Sie sie als Ressourcendatei zu Ihrer DITA-Zuordnung hinzufügen. Die PDFs werden an der in der Karte dargestellten Stelle eingefügt und die Seiten werden entsprechend inkrementiert. |
| **Einbetten von verwendeten Schriftarten** | Wählen Sie diese Option aus, wenn Sie Schriftarten verwenden, die möglicherweise nicht auf dem Computer des Endbenutzers installiert sind. Wenn diese Option aktiviert ist, werden die verwendeten Schriftarten in PDF eingebettet, sodass Benutzende die PDF wie vorgesehen anzeigen können, selbst wenn die Schriftarten nicht auf ihrem Computer installiert sind. <br> **Hinweis**: Eine Schriftart kann nur eingebettet werden, wenn sie eine Einstellung vom Schriftanbieter enthält, die das Einbetten zulässt. Vergewissern Sie sich, dass Sie die erforderliche Einstellung oder Lizenz haben, bevor Sie eine Schriftart einbetten. |
| **Automatische Silbentrennung verwenden** | Wenn die automatische Silbentrennung aktiviert ist, werden Wörter am Zeilenende an grammatisch korrekten Stellen durch einen Bindestrich umbrochen. |
| **JavaScript aktivieren** | Aktivieren Sie diese Option, wenn Sie über einen JavaScript-Code verfügen, mit dem Sie Ihre Inhalte vor dem Generieren einer PDF dynamisch umwandeln können. |
| **Multimediadateien einbetten** | Wählen Sie diese Option, um beliebige Audio- und Videodateien sowie interaktive Inhalte in die PDF aufzunehmen. |
| **Verwenden Sie die vollständige Komprimierung, um die PDF-Größe zu optimieren** | Wählen Sie diese Option aus, wenn Sie die Größe eines großen PDF komprimieren/reduzieren möchten. Denken Sie daran, dass eine Komprimierung der PDF die Dateiqualität beeinträchtigen kann. |
| **Verwenden Sie die Bildkomprimierung, um die PDF-Größe zu optimieren** | Wählen Sie diese Option aus, wenn Sie die Größe der in Ihrer PDF verwendeten Bilder komprimieren/reduzieren möchten. Denken Sie daran, dass die Komprimierung eines Bildes die Bildqualität beeinträchtigen kann. |
| **Benutzerdefinierte Auflösung verwenden (Pixel pro Zoll)** | Dies ist die Seitenanzeigeauflösung in Pixeln pro Zoll. Geben Sie einen bevorzugten Wert in das Feld ein, das angezeigt wird, wenn diese Option ausgewählt ist. Der Standardwert ist 96 Pixel pro Zoll. Legen Sie einen höheren Wert fest, um mehr Inhalte in einem Zoll anzupassen, und umgekehrt, wenn Sie einen niedrigeren Wert festlegen. |
| **Wasserzeichen anzeigen** | Wählen Sie diese Option aus, um ein Wasserzeichen in Ihrer Ausgabe einzublenden. Sie können eine neue Textzeichenfolge in das Textfeld eingeben, wobei die Groß-/Kleinschreibung des Zeichens Ihren Vorstellungen entspricht. <br><br>Verwenden Sie statische Text- oder Sprachvariablen, um die lokalisierte Version des Wasserzeichens zu veröffentlichen.  Je nach Sprache wird der lokalisierte Wert automatisch in der PDF-Ausgabe ausgewählt. Sie können beispielsweise „Publisher“ als Wasserzeichen auf Englisch und „Auteure“ auf Französisch drucken.  <br>: `${lng:<variable name>}`. Beispiel: `$ {lng:publisher-label}`, wobei `publisher-label` eine Sprachvariable ist. <br> Mauszeiger über <img src="./assets/info-details.svg" alt= "Infosymbol" width="25"> in der Nähe der Option, um weitere Details dazu anzuzeigen. |
| **Aktivieren von MathML-Gleichungen** | Wählen Sie diese Option aus, um die in Ihrem Inhalt vorhandenen MathML-Gleichungen zu rendern. Die Gleichungen werden andernfalls standardmäßig ignoriert. |
| **Erstellen eines interaktiven PDF-Formulars** | Wählen Sie diese Option aus, wenn Sie interaktive und anpassbare PDF-Formularfelder für eine erweiterte Benutzereingabe in generierte PDF-Ausgaben aufnehmen möchten. |
| **Änderungen nachverfolgen** | Wählen Sie diese Option aus, wenn Sie verfolgte Änderungen in die generierte PDF aufnehmen möchten, um sie leicht überprüfen und vergleichen zu können. |
| **Temporäre Dateien beibehalten** | Wählen Sie diese Option aus, wenn Sie die beim Generieren der nativen PDF-Ausgabe erstellten HTML-Zwischendateien beibehalten möchten. Sie können die temporären Dateien später herunterladen, nachdem Sie die Ausgabe generiert haben. Die heruntergeladenen Dateien enthalten auch `system_config.xml` Datei mit Informationen zur Autoren-URL, lokalen URL und Veröffentlichungs-URL. Diese URLs werden in den AEM-Externalisierungseinstellungen konfiguriert und in der `system_config.xml`-Datei angezeigt. |
| **PDF-Konformität** | Dies ist der Standard, nach dem Sie Ihre PDF speichern möchten, um sicherzustellen, dass sie konform ist. Wählen Sie aus dem Dropdown-Menü aus, um aus der Liste der verfügbaren PDF-Standards auszuwählen. Weitere Informationen zu den unterstützten Standards finden Sie unter [Über PDF-](https://helpx.adobe.com/de/acrobat/using/pdf-conversion-settings.html#about_pdf_x_pdf_e_and_pdf_a_standards). |
| **Dateieigenschaften** | Wählen Sie die Metadaten aus, die Sie an die native PDF-Veröffentlichung übergeben möchten. Die Dropdown-Liste listet sowohl die benutzerdefinierten als auch die Standardeigenschaften auf. Beispielsweise sind `dc:description`, `dc:language`, `dc:title` und `docstate` die Standardeigenschaften, während Sie `author` als benutzerdefinierte Eigenschaft verwenden können. Die ausgewählten Metadateneigenschaften werden an die PDF-Datei übergeben, die mit dem nativen PDF generiert wurde. <br> Diese Eigenschaften werden aus der `metadataList` Datei ausgewählt, die unter verfügbar ist:`/libs/fmdita/config/metadataList`. <br>Diese Datei kann überlagert werden unter: `/apps/fmdita/config/metadataList`. |



<!--------------


### Additional notes for PDF output

**Download temporary files after generating the Native PDF output**

If you select the **Download temporary files** option in the Advanced settings, you can also download the interim HTML files created while generating the Native PDF output. Once you've generated the output, you can download the temporary files using the **Download temporary files** ![download temporary files](assets/native-pdf-download-temporary-files-icon.svg)icon on the top bar. This feature helps you view your interim HTML styles and layouts and helps you correct or change your CSS styles according to your requirements.


>[!NOTE]
>
> The **Download temporary files**  ![download temporary files](assets/native-pdf-download-temporary-files-icon.svg) icon appears only if you have generated the last PDF output using the preset wherein you have selected the option in the **Advanced** tab. 


**Use language variables**

AEM Guides also provides the support for language variables. Select **Language Variables** <img src="assets/language-variables.svg" width="25">  in the left panel to define a localized version of the out-of-the-box labels like Note, Caution, and Warning or static text in the PDF output. For more details, view [Support for language variables](../native-pdf/native-pdf-language-variables.md).


**Support for Markdown documents**

Experience Manager Guides also provides support for your Markdown documents.  Markdown files are easy to author and also provide a variety of formatting options. Learn how to [author Markdown documents from the Editor](../user-guide/web-editor-markdown-topic.md). 

You can add the Markdown topics to your DITA map and generate the PDF output using the Native PDF output presets.  Learn how to configure or [create a PDF output preset](#create-a-pdf-output-preset-create-output-preset). 

--------------->