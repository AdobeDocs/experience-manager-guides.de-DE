---
title: Einstellungen für die Ausgabegenerierung konfigurieren
description: Erfahren Sie, wie Sie Einstellungen für die Ausgabenerstellung konfigurieren
feature: Output Generation
role: Admin
level: Experienced
source-git-commit: 6f3f05419f4f5cdd45ab580cdee6fa869f20f01d
workflow-type: tm+mt
source-wordcount: '3314'
ht-degree: 1%

---

# Einstellungen für die Ausgabegenerierung konfigurieren {#id181AI0B0E30}

AEM Guides bietet viele Konfigurationsoptionen, mit denen Sie den Prozess der Ausgabenerstellung anpassen können. In diesem Abschnitt werden alle Konfigurationen und Anpassungen behandelt, die Ihnen beim Einrichten des Prozesses der Ausgabenerstellung helfen.

## Konfigurieren der Registerkarte „Baseline“ im Dashboard „DITA-Zuordnung“ {#id223MD0D0YRM}

Die folgenden Registerkarten enthalten Anweisungen zum Ausblenden der Registerkarte „Baseline“ im DITA-Zuordnungs-Dashboard basierend auf Ihrer Experience Manager Guides-Einrichtung: Cloud Service oder On-Premise.

>[!BEGINTABS]

>[!TAB Cloud Service]

1. Verwenden Sie die Anweisungen unter [Konfigurationsüberschreibungen](download-install-config-override.md#), um die Konfigurationsdatei zu erstellen.
1. Geben Sie in der Konfigurationsdatei die folgenden \(Eigenschaft\)-Details ein, um die Registerkarte „Baseline“ im Zuordnungs-Dashboard zu konfigurieren.

| PID | Eigenschaftsschlüssel | Eigenschaftswert |
|---|------------|--------------|
| `com.adobe.fmdita.config.ConfigManager` | `hide.tabs.baseline` | Boolesch\(`true/false`\).**Standardwert**: `true` |

>[!NOTE]
>
> Diese Konfiguration ist standardmäßig aktiviert und die Registerkarte Baseline ist im Zuordnungs-Dashboard nicht verfügbar.

>[!TAB On-Premise]

1. Öffnen Sie die Seite Konfiguration der Adobe Experience Manager-Web-Konsole .

   Die Standard-URL für den Zugriff auf die Konfigurationsseite lautet:

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Suchen Sie nach dem Bundle **com.adobe.fmdita.config.ConfigManager** und klicken Sie darauf.

1. Wählen Sie die Option **Registerkarte „Grundlinie ausblenden** aus.

1. Klicken Sie auf **Speichern**.

>[!NOTE]
>
> Diese Konfiguration ist standardmäßig deaktiviert und die Registerkarte Baseline ist im Zuordnungs-Dashboard verfügbar.

>[!ENDTABS]


## Konfigurieren von gemischten Veröffentlichungen innerhalb einer bestehenden AEM-Site {#id1691I0V0MGR}

Wenn Sie über eine AEM-Site verfügen, die DITA-Inhalte enthält, können Sie die Ausgabe Ihrer AEM-Site so konfigurieren, dass DITA-Inhalte an einem vordefinierten Speicherort innerhalb Ihrer Site veröffentlicht werden. Im folgenden Screenshot einer AEM Site-Seite ist beispielsweise der Knoten `ditacontent` für das Speichern von DITA-Inhalten reserviert:

![](assets/publish-in-aem-site.png)

Die verbleibenden Knoten auf der Seite werden direkt aus dem AEM-Website-Editor erstellt. Das Konfigurieren der Veröffentlichungseinstellung zum Veröffentlichen von DITA-Inhalten an einem vordefinierten Speicherort stellt sicher, dass keiner Ihrer vorhandenen Nicht-DITA-Inhalte durch den AEM Guides-Veröffentlichungsprozess geändert wird.

Sie müssen die folgenden Konfigurationen auf Ihrer vorhandenen Site durchführen, um die Veröffentlichung von DITA-Inhalten in einem vordefinierten Knoten zu ermöglichen:

- Konfigurieren der Vorlageneigenschaften Ihrer Site

- Hinzufügen von Knoten zur Site, um DITA-Inhalte zu veröffentlichen


Die folgenden Registerkarten enthalten Anweisungen zum Konfigurieren der Vorlageneigenschaften Ihrer bestehenden Site basierend auf Ihrer Experience Manager Guides-Einrichtung: Cloud Service oder On-Premise.

>[!BEGINTABS]

>[!TAB Cloud Service]

1. Verwenden Sie den Package Manager, um die Datei /libs/fmdita/config/templates/default herunterzuladen.

   >[!NOTE]
   >
   > Nehmen Sie keine Anpassungen in den Standardkonfigurationsdateien im Knoten `libs` vor. Sie müssen eine Überlagerung des Knotens `libs` im Knoten `apps` erstellen und die erforderlichen Dateien nur im Knoten `apps` aktualisieren.

1. Fügen Sie die folgenden Eigenschaften hinzu:

   | Eigenschaftsname | Typ | Wert |
   |-------------|----|-----|
   | `topicContentNode` | Zeichenfolge | Geben Sie den Knotennamen an, in dem der DITA-Inhalt veröffentlicht werden soll. Der Standardknoten, auf dem AEM Guides DITA-Inhalte veröffentlicht, lautet beispielsweise: <br> `jcr:content/contentnode` |
   | `topicHeadNode` | Zeichenfolge | Geben Sie den Knotennamen an, in dem die Metadateninformationen Ihres DITA-Inhalts gespeichert werden sollen. Der Standardknoten, in dem AEM Guides Metadateninformationen speichert, lautet beispielsweise: <br> `jcr:content/headnode` |


Wenn Sie das nächste Mal DITA-Inhalte mithilfe der Vorlagenkonfigurationen Ihrer Site veröffentlichen, werden die Inhalte in den Knoten veröffentlicht, die in den `topicContentNode`- und `topicHeadNode` angegeben sind.

>[!TAB On-Premise]

1. Melden Sie sich bei AEM an und öffnen Sie den CRXDE Lite-Modus.

1. Navigieren Sie zum Vorlagenkonfigurationsknoten Ihrer Site. Beispielsweise speichert AEM Guides die standardmäßigen Vorlagenkonfigurationen im folgenden Knoten:

   `/libs/fmdita/config/templates/default`

   >[!NOTE]
   >
   > Nehmen Sie keine Anpassungen in den Standardkonfigurationsdateien im Knoten `libs` vor. Sie müssen eine Überlagerung des Knotens `libs` im Knoten `apps` erstellen und die erforderlichen Dateien nur im Knoten `apps` aktualisieren.

1. Fügen Sie die folgenden Eigenschaften hinzu:

   | Eigenschaftsname | Typ | Wert |
   |-------------|----|-----|
   | `topicContentNode` | Zeichenfolge | Geben Sie den Knotennamen an, in dem der DITA-Inhalt veröffentlicht werden soll. Der Standardknoten, auf dem AEM Guides DITA-Inhalte veröffentlicht, lautet beispielsweise: <br>`jcr:content/contentnode` |
   | `topicHeadNode` | Zeichenfolge | Geben Sie den Knotennamen an, in dem die Metadateninformationen Ihres DITA-Inhalts gespeichert werden sollen. Der Standardknoten, in dem AEM Guides Metadateninformationen speichert, lautet beispielsweise: <br>`jcr:content/headnode` |


Der folgende Screenshot zeigt die Eigenschaften, die im Standardvorlagenknoten von AEM Guides hinzugefügt wurden:

![](assets/add-content-node.png){width="800" align="left"}

Wenn Sie das nächste Mal DITA-Inhalte mithilfe der Vorlagenkonfigurationen Ihrer Site veröffentlichen, werden die Inhalte in den Knoten veröffentlicht, die in den `topicContentNode`- und `topicHeadNode` angegeben sind.

Bei vorhandenen Sites müssen Sie jedoch die Knoten `topicContentNode` und `topicHeadNode` manuell hinzufügen.

Führen Sie die folgenden Schritte aus, um die erforderlichen Knoten zu Ihrer vorhandenen Site hinzuzufügen:

1. Melden Sie sich bei AEM an und öffnen Sie den CRXDE Lite-Modus.

1. Suchen Sie `jcr:content` in Ihrem Site-Knoten.

1. Fügen Sie `topicContentNode`- und `topicHeadNode`-Knoten mit demselben Namen hinzu, den Sie in den Vorlagenkonfigurationen der Site angegeben haben.

>[!ENDTABS]

## Konfigurieren des Speicherorts für die Basisausgabe für die Veröffentlichung

Die folgenden Registerkarten enthalten Anweisungen zum Konfigurieren des Basis-Ausgabespeicherorts basierend auf Ihrer Experience Manager Guides-Einrichtung: Cloud Service oder On-Premise.

>[!BEGINTABS]

>[!TAB Cloud Service]

1. Verwenden Sie die Anweisungen unter [Konfigurationsüberschreibungen](download-install-config-override.md), um die Konfigurationsdatei zu erstellen.

1. Geben Sie in der Konfigurationsdatei die folgenden (Eigenschafts-)Details an, um den Basisausgabespeicherort zu konfigurieren:

   | PID | Eigenschaftsschlüssel | Eigenschaftswert |
   |---|---|---|
   | `com.adobe.fmdita.config.ConfigManager` | `base.output.path` | **Standardwert:** &quot;/content/dam/fmdita-output“ |

>[!TAB On-Premise]

1. Öffnen Sie die Seite Konfiguration der Adobe Experience Manager-Web-Konsole .

   Die Standard-URL für den Zugriff auf die Konfigurationsseite lautet:

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Suchen Sie nach dem Bundle *com.adobe.fmdita.config.ConfigManager* und wählen Sie es aus.

1. Aktualisieren Sie die Eigenschaft **Basisausgabespeicherort**, um den Standardpfad im AEM-Repository anzugeben, in dem die PDF nach der Veröffentlichung gespeichert wird. Wenn ein ungültiger Pfad eingegeben wird, wird außerdem automatisch der Standardpfad `/content/dam/fmdita-outputs` verwendet.

1. Klicken Sie auf **Speichern**.

>[!ENDTABS]

## Verwenden von Metadaten in der Veröffentlichungsausgabe über DITA-OT {#id191LF0U0TY4}

AEM Guides bietet die Möglichkeit, benutzerdefinierte Metadaten beim Veröffentlichen von Ausgaben mit DITA-OT zu übergeben. Als Administrator und Publisher müssen Sie die folgenden Aufgaben ausführen, um benutzerdefinierte Metadaten in der veröffentlichten Ausgabe zu konfigurieren und zu verwenden:

- Fügen Sie als Administrator die erforderlichen Metadaten im System hinzu, damit sie auf der Seite Eigenschaften der DITA-Zuordnung verfügbar gemacht werden.

- Fügen Sie als Administrator die benutzerdefinierten Metadaten zur Metadatenliste hinzu, sodass sie in der DITA-Zuordnungskonsole angezeigt werden.

- Konfigurieren und fügen Sie als Publisher die benutzerdefinierten Metadaten mit der DITA-Zuordnung hinzu und generieren Sie die erforderliche Ausgabe.


Um die erforderlichen Metadaten im System hinzuzufügen, führen Sie die folgenden Schritte aus:

1. Melden Sie sich bei Adobe Experience Manager als Administrator an.

1. Klicken Sie oben auf den Adobe Experience Manager-Link und wählen Sie **Tools** aus.

1. Wählen Sie **Assets** aus der Liste der Tools aus.

1. Klicken Sie auf die **Metadatenschemata**.

   Die Seite Metadatenschema-Forms wird angezeigt.

1. Wählen Sie das **Standard**-Formular aus der Liste aus.

   >[!NOTE]
   >
   > Die Eigenschaften, die auf der Seite Eigenschaften für eine DITA-Zuordnung angezeigt werden, stammen aus diesem Formular.

1. Klicken Sie auf **Bearbeiten**.

1. Fügen Sie die benutzerdefinierten Metadaten hinzu, die Sie in Ihren veröffentlichten Ausgaben verwenden möchten. Wir fügen beispielsweise Zielgruppen-Metadaten mithilfe der folgenden Schritte hinzu:

   1. Ziehen Sie aus **Komponentenliste** Formular erstellen“ die Komponente **Einzeiliger Text** per Drag-and-Drop auf das Formular.

   2. Wählen Sie das neue Feld aus, um die **Einstellungen** des Felds zu öffnen.

   3. Geben **unter „Feldbezeichnung** den Metadatennamen - Zielgruppe ein.

   4. Geben Sie in **Einstellung „Zu Eigenschaft**&quot; an./jcr:content/metadata/&lt;Name der Metadaten\>. Für unser Beispiel setzen wir es auf ./jcr:content/metadata/audience.

   Fügen Sie mithilfe dieser Schritte alle erforderlichen Metadatenparameter hinzu.

1. Klicken Sie auf **Speichern**.


Der neue Parameter wird jetzt auf der Seite Eigenschaften für alle DITA-Zuordnungen angezeigt.

![](assets/properties-page-custom-metadata.PNG)

Als Nächstes müssen Sie die benutzerdefinierten Metadaten in der DITA-Zuordnungskonsole verfügbar machen. Die folgenden Registerkarten enthalten Anweisungen dazu, wie Sie die benutzerdefinierten Metadaten basierend auf Ihrer Experience Manager Guides-Einrichtung im DITA Map-Dashboard verfügbar machen können: Cloud Service oder On-Premise.

>[!BEGINTABS]

>[!TAB Cloud Service]

1. Verwenden Sie den Package Manager, um auf die Datei „metadataList“ zuzugreifen, die unter dem folgenden Speicherort im Git-Repository Ihrer Cloud Manager verfügbar ist:

   /libs/fmdita/config/metadataList

   >[!NOTE]
   >
   > Die Datei „metadataList“ enthält eine Liste mit Eigenschaften, die in der Dropdown-Liste **Eigenschaften** einer DITA-Zuordnung im Zuordnungs-Dashboard angezeigt werden. Standardmäßig werden in dieser Datei vier Eigenschaften aufgelistet: docstate, dc:language, dc:description und dc:title.

1. Fügen Sie die benutzerdefinierten Metadaten hinzu, die Sie auf der Seite Metadatenschema-Forms hinzugefügt haben. Für unser Beispiel fügen Sie den Zielgruppenparameter am Ende der Standardliste hinzu.

>[!TAB On-Premise]

1. Melden Sie sich bei AEM an und öffnen Sie den CRXDE Lite-Modus.

1. Greifen Sie auf die Datei „metadataList“ zu, die unter dem folgenden Speicherort verfügbar ist:

   /libs/fmdita/config/metadataList

   >[!NOTE]
   >
   > Die Datei „metadataList“ enthält eine Liste mit Eigenschaften, die in der Dropdown-Liste **Eigenschaften** einer DITA-Zuordnung im Zuordnungs-Dashboard angezeigt werden. Standardmäßig werden in dieser Datei vier Eigenschaften aufgelistet: docstate, dc:language, dc:description und dc:title.

1. Fügen Sie die benutzerdefinierten Metadaten hinzu, die Sie auf der Seite Metadatenschema-Forms hinzugefügt haben. Für unser Beispiel fügen Sie den Zielgruppenparameter am Ende der Standardliste hinzu.

1. Klicken Sie auf **Alle speichern**.

>[!ENDTABS]

Jetzt werden die benutzerdefinierten Metadaten in der Dropdown-Liste **Eigenschaften“ der DITA-** angezeigt.

Als Publisher müssen Sie schließlich die benutzerdefinierten Metadaten in die veröffentlichte Ausgabe einbeziehen. Um die benutzerdefinierten Metadaten beim Generieren der Ausgabe zu verarbeiten, führen Sie die folgenden Schritte aus:

1. Navigieren Sie in der Assets-Benutzeroberfläche zu der DITA-Karte, die Sie veröffentlichen möchten.

1. Wählen Sie die DITA-Zuordnungsdatei aus und öffnen Sie die zugehörige Eigenschaftsseite.

1. Geben Sie auf der Seite Eigenschaften den Wert für die benutzerdefinierten Metadaten an. In unserem Beispiel haben wir für den Zielgruppen-Parameter den Wert Extern angegeben.

   ![](assets/properties-page-custom-metadata-value.png)

1. Klicken Sie auf **Speichern und schließen**.

1. Klicken Sie auf die DITA-Zuordnungsdatei, um die DITA-Zuordnungskonsole zu öffnen.

1. Wählen **auf der Registerkarte** Ausgabevorgaben“ die Ausgabevorgabe aus, die Sie zum Generieren der Ausgabe verwenden möchten.

1. Klicken Sie auf **Bearbeiten**.

1. Wählen Sie aus **Dropdown** Liste „Eigenschaften“ die Eigenschaften aus, die Sie an den Veröffentlichungsprozess übergeben möchten.

   ![](assets/props-in-publish-output.PNG)


Die ausgewählten Eigenschaften/Metadaten werden an den Veröffentlichungsprozess übergeben und in der endgültigen Ausgabe verfügbar gemacht.

### Validieren von Metadaten, die zur Verarbeitung an das DITA-OT übergeben werden (nur für Cloud Service)

Um die an das DITA-OT übergebenen Metadatenwerte zu überprüfen, kann die lokale Umgebung mit einem Cloud-fähigen JAR verwendet werden. Da wir auf das lokale Dateisystem in der Cloud nicht zugreifen können, ist die einzige Möglichkeit, die Metadatendatei zu validieren, über ein Cloud-fähiges JAR.

- Dateiname: metadata.xml
- Dateispeicherort: crx-quickstart/profiles/ditamaps/&lt;ditamap-1234\>

  So greifen Sie auf metadata.xml zu:

   - Melden Sie sich bei dem Server-Speicherort an, auf dem die AEM-Instanz ausgeführt wird.
   - Migrieren Sie zu „crx-quickstart/profiles/ditamaps/&lt;newly-created-directory-name\>/metadata.xml&quot;.
- Beispieldateiformat:

  **metadata.xml**

  ```XML
  <?xml version="1.0" encoding="UTF-8" standalone="no"?>
  <root>
     <Path id="/absolutePath/sampleMap.ditamap">
        <metadata>
           <meta isArray="false" key="dc:description">This is a file</meta>
           <meta isArray="false" key="dc:title">Myfile</meta>
           <meta isArray="true" key="multivalueText">One;Two;Three</meta>
        </metadata>
     </Path>
     <Path id="/absolutePath/sampleTopic.dita">
        <metadata>
           <meta isArray="false" key="dc:description">description for the accountability</meta>
           <meta isArray="false" key="dc:title">accountability title</meta>
           <meta isArray="true" key="multivalueText">value1</meta>
        </metadata>
     </Path>
  </root>
  ```


- isArray: Ein boolesches Attribut, das definiert, ob die Metadaten ein \(Array\) mit mehreren Werten sind oder nicht. Die Werte werden durch ein Semikolon voneinander getrennt.
- Pfad-ID: Absoluter Pfad zur Datei, die im temporären Verzeichnis gespeichert ist.

>[!NOTE]
>
> Wenn für die Datei keine bestimmten Metadaten vorhanden sind, wird das &lt;meta\>-Tag mit dem Schlüssel nicht als Eigenschaft für diese Datei in der Datei „metadata.xml“ angezeigt.

## Konfigurieren Sie das DITA-OT-Befehlszeilenargumentfeld so, dass Stammzuordnungs-Metadaten akzeptiert werden (nur für Cloud Service)

Um das DITA-OT-Befehlszeilenargumentfeld zum Übergeben von Stammzuordnungs-Metadaten zu verwenden, führen Sie die folgenden Schritte aus:

1. Verwenden Sie die Anweisungen unter [Konfigurationsüberschreibungen](download-install-config-override.md#), um die Konfigurationsdatei zu erstellen.
1. Geben Sie in der Konfigurationsdatei die folgenden \(property\)-Details an, um das Befehlszeilenargumentfeld „DITA-OT“ in der Voreinstellung zu konfigurieren:

| PID | Eigenschaftsschlüssel | Eigenschaftswert |
|---|------------|--------------|
| `com.adobe.fmdita.config.ConfigManager` | `pass.metadata.args.cmd.line` | Boolesch\(`true/false`\).**Standardwert**: `true` |

- Wenn Sie den Eigenschaftswert auf **true** setzen, wird die DITA-OT-Befehlszeilenfunktion aktiviert, sodass Sie die Metadaten über die DITA-OT-Befehlszeile übergeben können.
- Wenn Sie den Wert der Eigenschaft auf **false** setzen, wird die DITA-OT-Befehlszeilenfunktion deaktiviert. Anschließend können Sie das Feld Eigenschaft in der Voreinstellung verwenden, um die Metadaten zu übergeben.

## Anpassen der DITA-Zuordnungskonsole {#id188HC08M0CZ}

AEM Guides bietet Ihnen die Flexibilität, die Funktionen der DITA-Zuordnungskonsole zu erweitern. Wenn Sie beispielsweise über einen Berichtssatz verfügen, der sich von dem unterscheidet, der in der AEM Guides verfügbar ist, können Sie solche Berichte zur Zuordnungskonsole hinzufügen. Um die Zuordnungskonsole anzupassen, müssen Sie eine AEM-Client-Bibliothek \(oder clientLib\) erstellen, die den Code zur Durchführung der benötigten Funktionen enthält.

>[!NOTE]
>
> Eine direkte Änderung an den Seitenkomponenten wird nicht empfohlen, da sie durch neue Versionen des Produkts überschrieben wird.

AEM Guides stellt die `apps.fmdita.dashboard-extn` zum Anpassen der Zuordnungskonsole bereit. Wenn die Zuordnungskonsole geladen wird, wird die unter der Kategorie `apps.fmdita.dashboard-extn` erstellte Funktion ausgeführt und geladen.

>[!NOTE]
>
> Weitere Informationen zum Erstellen der AEM-Client-Bibliothek finden Sie unter [Verwenden Client-seitiger Bibliotheken](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/developing/full-stack/clientlibs.html?lang=en).

## Verarbeiten der Bildausgabedarstellung während der Ausgabegenerierung {#id177BF0G0VY4}

AEM enthält einen Satz von standardmäßigen Workflows und Medien-Handles zur Verarbeitung von Assets. In AEM gibt es vordefinierte Workflows für die Asset-Verarbeitung für die gängigsten MIME-Typen. Normalerweise erstellt AEM für jedes Bild, das Sie hochladen, mehrere Ausgabedarstellungen desselben Bilds im Binärformat. Diese Ausgabedarstellungen können unterschiedlich groß sein, eine andere Auflösung, ein hinzugefügtes Wasserzeichen oder eine andere geänderte Eigenschaft aufweisen. Weitere Informationen zum Verarbeiten von Assets durch AEM finden Sie unter [Verarbeiten von Assets mit Medien-Handlern und Workflows](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/assets/asset-microservices-overview.html?lang=en) in der Dokumentation zu AEM.

Mit AEM Guides können Sie konfigurieren, welche Bildausgabe zum Zeitpunkt der Generierung der Ausgabe für Ihre Dokumente verwendet werden soll. Sie können beispielsweise aus einer der standardmäßigen Bildausgabedarstellungen auswählen oder eine erstellen und dieselbe zum Veröffentlichen Ihrer Dokumente verwenden. Die Bildausgabedarstellungszuordnung zum Veröffentlichen Ihrer Dokumente wird in der `/libs/fmdita/config/ **renditionmap.xml**`-Datei gespeichert. Ein Ausschnitt `renditionmap.xml` Datei lautet wie folgt:

>[!NOTE]
>
> Es wird empfohlen, für alle Anpassungen eine Kopie der `renditionmap.xml`-Datei im `apps`-Ordner zu erstellen.

```XML
<renditionmap>
   <mapelement>
      <mimetype>image/png</mimetype>
      <rendition output="AEMSITE">cq5dam.web.1280.1280.jpeg</rendition>
      <rendition output="PDF">original</rendition>
      <rendition output="HTML5">cq5dam.web.1280.1280.jpeg</rendition>
      <rendition output="HTML5" outputName="ditahtml5">cq5dam.thumbnail.319.319.png</rendition>
      <rendition output="EPUB">cq5dam.web.1280.1280.jpeg</rendition>
      <rendition output="CUSTOM">cq5dam.web.1280.1280.jpeg</rendition>
   </mapelement>
...
</renditionmap>
```

Das `mimetype` gibt den MIME-Typ des Dateiformats an. Das `rendition output`-Element gibt den Typ des Ausgabeformats und den Namen der Ausgabedarstellung \(z. B. `cq5dam.web.1280.1280.jpeg`\) an, die zum Veröffentlichen der angegebenen Ausgabe verwendet werden soll. Sie können die Bildausgabedarstellungen angeben, die für alle unterstützten Ausgabeformate verwendet werden sollen - AEMSITE, PDF, HTML5, EPUB und CUSTOM.

Wenn Sie verschiedene Bildausgabedarstellungen für eine Ausgabevorgabe angeben möchten, können Sie das `outputName`-Attribut verwenden, dessen Wert auf den Titel der Vorgabe festgelegt ist, um benutzerdefinierte Ausgabedarstellungen für bestimmte Ausgabevorgaben unter demselben Ausgabetyp zu definieren. Dies ist nützlich, wenn Sie für verschiedene Veröffentlichungsszenarien unterschiedliche Bildgrößen oder Formate benötigen.

Beispiel:


```XML
<renditionmap>
   <mapelement>
      <mimetype>image/png</mimetype>
      
      <rendition output="HTML5">cq5dam.web.1280.1280.jpeg</rendition>
      <rendition output="HTML5" outputName="ditahtml5">cq5dam.thumbnail.319.319.png</rendition>
      
   </mapelement>
...
</renditionmap>
```

Wenn in den oben genannten Ausgabedarstellungen das Attribut `outputName` auf `ditahtml5` (voreingestellter Titel) festgelegt ist, verwendet die `ditahtml5` die `cq5dam.thumbnail.319.319.png`. Wenn das `outputName` nicht angegeben ist, verwenden alle HTML5-Ausgaben die größere `cq5dam.web.1280.1280.jpeg`.

Wenn die angegebene Ausgabedarstellung nicht vorhanden ist, sucht der AEM Guides-Veröffentlichungsprozess zunächst nach der Web-Ausgabedarstellung des angegebenen Bildes. Wenn selbst die Web-Ausgabedarstellung nicht gefunden wird, wird die ursprüngliche Ausgabedarstellung des Bildes verwendet.

>[!NOTE]
>
> Diese Bildausgabedarstellungen steuern nur die Ausgabegenerierung. Die Web-Ausgabedarstellung eines Bildes wird verwendet, wenn Sie ein Dokument zur Vorschau oder Überprüfung öffnen.

## Automatische Bereinigungsperiode für den Ausgabegeschverlauf konfigurieren {#id19AAI070V8Q}

Wenn Sie eine Ausgabe generieren, wird die Ausgabe zusammen mit den Ausgabeprotokollen erstellt. Bei großen DITA-Zuordnungen können diese Protokolle eine große Menge an Speicherplatz in Ihrem Repository beanspruchen. Standardmäßig werden die Protokolle an folgendem Speicherort im Repository gespeichert:

`/var/dxml/metadata/outputHistory`

Über einen bestimmten Zeitraum hinweg konnte die Gesamtgröße aller Protokolldateien GB erreichen. Mit AEM Guides können Sie einen Zeitraum konfigurieren, während dessen diese Protokolldateien im Repository gespeichert werden. Nach dem angegebenen Zeitraum werden die Protokolle zusammen mit dem Verlauf der Ausgabegenerierung aus dem Repository gelöscht.

>[!NOTE]
>
> Der Verlauf der Ausgabegenerierung ist der Protokolleintrag in der Liste Erzeugte Ausgaben auf der Registerkarte Ausgaben .

Die Konfiguration der Verlaufsbereinigung wirkt sich auf die Ausgabegenerierung für alle DITA-Zuordnungen im Repository aus. Auf der Registerkarte Ausgaben einer DITA-Zuordnung wird der Verlauf nach der angegebenen Anzahl von Tagen und zu dem in der Einstellung angegebenen Zeitpunkt gelöscht.

>[!NOTE]
>
> Das Entfernen der Protokolldateien und des Verlaufs der Ausgabegenerierung hat keine Auswirkungen auf die generierte Ausgabe.

Die folgenden Registerkarten enthalten Anweisungen zum Festlegen eines Tages und einer Uhrzeit für die Bereinigung des Ausgabehistoriums und der Protokolle basierend auf Ihrem Experience Manager Guides-Setup: Cloud Service oder On-Premise.

>[!BEGINTABS]

>[!TAB Cloud Service]

Verwenden Sie die Anweisungen unter [Konfigurationsüberschreibungen](download-install-config-override.md#), um die Konfigurationsdatei zu erstellen. Geben Sie in der Konfigurationsdatei die folgenden \(property\)-Details an, um einen Tag und eine Uhrzeit für die Bereinigung des Ausgabegeschichtverlaufs und der Protokolle festzulegen:

| PID | Eigenschaftsschlüssel | Eigenschaftswert |
|---|------------|--------------|
| `com.adobe.fmdita.config.ConfigManager\|output.history.purgeperiod` | Geben Sie die Anzahl der Tage an, nach denen der Ausgabeverlauf zusammen mit den Ausgabeprotokollen bereinigt wird. Wenn Sie diese Funktion deaktivieren möchten, setzen Sie diese Eigenschaft auf 0. Täglich zum angegebenen Zeitpunkt, an dem der Bereinigungsvorgang für Ausgaben ausgeführt wird, die vor der in dieser Eigenschaft angegebenen Anzahl von Tagen generiert wurden. | **Standardwert**: 5 |
| `output.history.purgetime` | Geben Sie den Zeitpunkt an, zu dem der Bereinigungsvorgang gestartet wird. | **Standardwert**: 0:00 \(oder 12:00 midnight\) |

>[!TAB On-Premise]

1. Öffnen Sie die Seite Konfiguration der Adobe Experience Manager-Web-Konsole .

   Die Standard-URL für den Zugriff auf die Konfigurationsseite lautet:

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Suchen Sie nach dem Bundle **com.adobe.fmdita.config.ConfigManager** und klicken Sie darauf.

1. Geben **in der Eigenschaft &quot;** des Ausgabehistorie-Löschzeitraums“ die Anzahl der Tage an, nach denen der Ausgabehistorie zusammen mit den Ausgabeprotokollen bereinigt wird. Standardmäßig ist dieser Zeitraum auf 5 Tage festgelegt. Wenn Sie diese Funktion deaktivieren möchten, setzen Sie diese Eigenschaft auf 0.

1. Geben **in der Eigenschaft** Ausgabeverlauf: Bereinigungszeit“ den Zeitpunkt an, zu dem der Bereinigungsvorgang gestartet wird. Standardmäßig ist dies auf 0:00 \(oder 12:00 Mitternacht\) festgelegt. Zu dieser Zeit wird täglich der Bereinigungsvorgang für Ausgaben ausgeführt, die vor der in der Eigenschaft &quot;**des Ausgabeverlaufs: Bereinigungszeitraum“ angegebenen Anzahl** Tagen generiert wurden.

   >[!NOTE]
   >
   > Standardmäßig wird die Bereinigungsfunktion bei Ausgaben, die älter als 5 Tage sind, jeden Mitternacht ausgeführt.

1. Klicken Sie auf **Speichern**.

>[!ENDTABS]

## Ändern des Listenlimits für zuletzt generierte Ausgaben {#id1679JH0H0O2}

Sie können die maximale Anzahl generierter Ausgaben ändern, die auf der Registerkarte Ausgaben für eine DITA-Zuordnung angezeigt werden.

>[!BEGINTABS]

>[!TAB Cloud Service]

Verwenden Sie die Anweisungen unter [Konfigurationsüberschreibungen](download-install-config-override.md#), um die Konfigurationsdatei zu erstellen. Geben Sie in der Konfigurationsdatei die folgenden \(Eigenschaft\)-Details ein, um die Anzahl der in der Liste anzuzeigenden Ausgaben zu ändern:

| PID | Eigenschaftsschlüssel | Eigenschaftswert |
|---|------------|--------------|
| `com.adobe.fmdita.config.ConfigManager` | `output.historylimit` | Ganzzahliger Wert.<br> **Standardwert**: 25 |

>[!TAB On-Premise]

Standardmäßig wird eine Liste der zuletzt 25 generierten Ausgaben angezeigt. Um die Anzahl der in der Liste anzuzeigenden Ausgaben zu ändern, aktualisieren Sie die Einstellung **Ausgabelistenlimit** im `com.adobe.fmdita.config.ConfigManager`.

>[!ENDTABS]

>[!TIP]
>
> Best Practices für *Arbeit mit dem* finden Sie im Abschnitt [Ausgabehistorie](https://helpx.adobe.com/content/dam/help/en/xml-documentation-solution/cs-mar-22/Adobe-Experience-Manager-Guides_Best-Practices_EN.pdf) des -Best-Practice-Handbuchs.

## Leistungsoptimierung bei der Ausgabenerstellung (nur On-Premise) {#id176LB050VUI}

Mit AEM Guides können Sie die Pool-Größe der Ausgabegenerierungsprozesse konfigurieren, die die Anzahl der gleichzeitig ausgeführten Ausgabegenerierungsprozesse steuert. Standardmäßig ist die Größe des Prozesspools auf die Anzahl der in Ihrem System verfügbaren Verarbeitungskerne plus einen festgelegt. Sie können diesen Wert in 1 ändern, falls Sie eine sequenzielle Veröffentlichung wünschen. In diesem Fall wird die erste Veröffentlichungsaufgabe ausgeführt und die nächste Veröffentlichungsaufgabe wird in der Veröffentlichungswarteschlange gespeichert.

Um die Größe des Verarbeitungspools für die Ausgabegenerierung zu ändern, aktualisieren Sie die Einstellung **Generierungspoolgröße** im `com.adobe.fmdita.publish.manager.PublishThreadManagerImpl`.

## Konfigurieren von FrameMaker Publishing Server (nur für On-Premise) {#id1678G0Z0TN6}

Sie können FrameMaker Publishing Server \(FMPS\) verwenden, um eine Ausgabe für Ihren DITA-Inhalt zu generieren. Durch die Konfiguration von FMPS können Sie Ausgaben in mehreren Formaten generieren, die von FMPS unterstützt werden.

>[!NOTE]
>
> Um eine Ausgabe mithilfe von FMPS zu generieren, müssen Sie den FMPS-Server einrichten. Informationen zur Installation und Konfiguration finden Sie im FrameMaker Publishing Server-Benutzerhandbuch.

Um AEM Guides für die Verwendung von FMPS zu konfigurieren, aktualisieren Sie die folgenden Eigenschaften des `com.adobe.fmdita.config.ConfigManager`-Bundles in der Web-Konsole.

>[!NOTE]
>
> Greifen Sie auf die URL http://&lt;Server-Name>:&lt;Port>/system/console/configMgr zu, um die Web-Konsole zu öffnen.

| Eigenschaft | Beschreibung |
|--------|-----------|
| FrameMaker Publishing Server-Anmeldedomäne | Geben Sie den Domain-Namen oder den Arbeitsgruppennamen an, auf dem die FrameMaker Publishing Server gehostet wird. Geben Sie basierend auf der FMPS-Version den Domain-Namen wie folgt an:-   **FMPS 2020**: IP-Adresse als 192.168.1.101 <br>- **FMPS 2019 und früher**: IP-Adresse oder der Domain-Name |
| FrameMaker Publishing Server-URL | Geben Sie die URL der FrameMaker Publishing Server an. Geben Sie basierend auf der FMPS-Version die FMPS-URL als: <br>- **FMPS 2020**: `http://<fmps_ip>:<port>` \(http://192.168.1.101:7000\) <br> - **FMPS 2019 und früher**: `http://<fmps_ip>:<port>/fmserver/v1/` |
| FMPS-Version | Geben Sie die Versionsnummer der FrameMaker Publishing Server an. Geben Sie basierend auf der FMPS-Version die Versionsinformationen wie folgt an: <br>- **FMPS 2020**: 2020 <br> - **FMPS 2019 und früher**: 2019 oder 2017 |
| Benutzername und Kennwort für FrameMaker Publishing Server | Geben Sie den Benutzernamen und das Kennwort für den Zugriff auf die FrameMaker Publishing Server an. |
| FMPS-Zeitüberschreitung | \(*Optional*\) Geben Sie die Zeit \(in Sekunden\) an, für die AEM Guides auf eine Antwort von FrameMaker Publishing Server wartet. Wenn in der angegebenen Zeit keine Antwort eingeht, beendet AEM Guides die Veröffentlichungsaufgabe und die Aufgabe wird als fehlgeschlagen markiert. <br> Standardwert: 300 Sekunden \(5 Minuten\) |
| External AEM URL | *\(Optional\)* Die AEM-URL, in der die generierten Ausgabedateien von FrameMaker Publishing Server platziert werden. Zum Beispiel: `http://<server-name>:<port>/`. |
| AEM Admin-Benutzername und -Kennwort | *\(Optional\)* Benutzername und Kennwort eines Administrators Ihres AEM-Setups. Dieser wird von FrameMaker Publishing Server zur Kommunikation mit AEM verwendet. |
| Wartezeit bei FMPS-Aufgabenausführung | Diese Einstellung gilt nur für FMPS 2020. Geben Sie die Zeit \(in Sekunden\) an, nach der FMPS nicht mehr auf die Ausführung dieses Prozesses wartet. |


