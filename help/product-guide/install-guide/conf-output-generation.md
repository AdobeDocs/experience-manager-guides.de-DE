---
title: Ausgabegenerierungseinstellungen konfigurieren
description: Erfahren Sie, wie Sie die Einstellungen für die Generierung von Ausgaben konfigurieren
exl-id: 6df31e3c-683c-4188-b917-9c1855d9b95b
feature: Output Generation
role: Admin
level: Experienced
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '5762'
ht-degree: 1%

---

# Ausgabegenerierungseinstellungen konfigurieren {#id181AI0B0E30}

AEM Guides verfügt über eine Vielzahl von Konfigurationsoptionen, mit denen Sie den Output-Generierungsprozess anpassen können. In diesem Thema werden alle Konfigurationen und Anpassungen behandelt, die Ihnen bei der Einrichtung Ihres Ausgabegenerierungsprozesses helfen.

## Konfigurieren der Registerkarte &quot;Grundlinie&quot;im DITA-Map-Dashboard {#id223MD0D0YRM}

Sie können die Registerkarte &quot;Grundlinie&quot;im Dashboard der Karte konfigurieren und ausblenden.

Die Option **Registerkarte &quot;Grundlinie ausblenden&quot;** ist standardmäßig nicht aktiviert und muss über &quot;configMgr&quot;aktiviert werden. Führen Sie die folgenden Schritte aus, um die Option standardmäßig im Web-Editor zu aktivieren:

1. Öffnen Sie die Seite Adobe Experience Manager Web Console Configuration .

   Die Standard-URL für den Zugriff auf die Konfigurationsseite lautet:

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Suchen Sie nach dem Bundle **com.adobe.fmdita.config.ConfigManager** und klicken Sie darauf.

1. Wählen Sie die Option **Registerkarte &quot;Grundlinie ausblenden&quot;** aus.

1. Klicken Sie auf **Speichern**.

   >[!NOTE]
   >
   > Diese Konfiguration ist standardmäßig deaktiviert und die Registerkarte &quot;Grundlinie&quot;ist im Landkarten-Dashboard verfügbar.


## FrameMaker Publishing Server konfigurieren {#id1678G0Z0TN6}

Sie können FrameMaker Publishing Server \(FMPS\) verwenden, um eine Ausgabe für Ihren DITA-Inhalt zu generieren. Durch die Konfiguration von FMPS können Sie die Ausgabe in mehreren Formaten generieren, die von FMPS unterstützt werden.

>[!NOTE]
>
> Um die Ausgabe mithilfe von FMPS zu generieren, müssen Sie über den FMPS-Server verfügen. Weitere Informationen zur Installation und Konfiguration finden Sie im FrameMaker Publishing Server-Benutzerhandbuch.

Um AEM Guides für die Verwendung von FMPS zu konfigurieren, aktualisieren Sie die folgenden Eigenschaften des Bundles `com.adobe.fmdita.config.ConfigManager` in der Web-Konsole.

>[!NOTE]
>
> Rufen Sie die URL http://&lt;Servername\>:&lt;Port\>/system/console/configMgr auf, um die Web-Konsole zu öffnen.

| Eigenschaft | Beschreibung |
|--------|-----------|
| FrameMaker Publishing Server Login Domain | Geben Sie den Domänennamen oder den Arbeitsgruppennamen an, auf dem die FrameMaker Publishing Server gehostet wird. Geben Sie je nach FMPS-Version den Domänennamen wie folgt an:   **FMPS 2020**: IP-Adresse als 192.168.1.101 <br>- **FMPS 2019 und früher**: IP-Adresse oder Domänenname |
| FrameMaker Publishing Server-URL | Geben Sie die URL der FrameMaker Publishing Server an. Geben Sie die FMPS-URL basierend auf der FMPS-Version wie folgt an:<br> - **FMPS 2020**: `http://<fmps_ip>:<port>` \(http://192.168.1.101:7000\) <br> - **FMPS 2019 und früher**: `http://<fmps_ip>:<port>/fmserver/v1/` |
| FMPS-Version | Geben Sie die Versionsnummer der FrameMaker Publishing Server an. Geben Sie basierend auf der FMPS-Version die Versionsinformationen wie folgt an: <br> - **FMPS 2020**: 2020 <br> - **FMPS 2019 und früher**: 2019 oder 2017 |
| FrameMaker Publishing Server Benutzername und Kennwort | Geben Sie den Benutzernamen und das Kennwort für den Zugriff auf die FrameMaker Publishing Server an. |
| FMPS-Zeitüberschreitung | \(*Optional*\) Geben Sie die Zeit \(in Sekunden\) an, für die AEM Guides auf eine Antwort vom FrameMaker Publishing Server wartet. Wenn keine Antwort in der angegebenen Zeit empfangen wurde, beendet AEM Guides die Veröffentlichungsaufgabe und die Aufgabe wird als fehlgeschlagen gekennzeichnet. <br> Standardwert: 300 Sekunden \(5 Minuten\) |
| Externe AEM-URL | *\(Optional\)* Die AEM-URL, in der die FrameMaker Publishing Server die generierten Ausgabedateien ablegt. Zum Beispiel: `http://<server-name>:<port>/`. |
| AEM Admin-Benutzername und Kennwort | *\(Optional\)* Der Benutzername und das Kennwort für einen Administrator Ihrer AEM. Dies wird von FrameMaker Publishing Server verwendet, um mit AEM zu kommunizieren. |
| Timeout für die Ausführung von FMPS-Aufgaben | Diese Einstellung gilt nur für FMPS 2020. Geben Sie die Zeit \(in Sekunden\) an, nach der FMPS nicht mehr auf die Ausführung dieses Prozesses warten soll. |

## Gemischte Veröffentlichung auf einer vorhandenen AEM-Site konfigurieren {#id1691I0V0MGR}

Wenn Sie über eine AEM-Site verfügen, die DITA-Inhalte enthält, können Sie Ihre AEM Site-Ausgabe so konfigurieren, dass DITA-Inhalte an einer vordefinierten Stelle auf Ihrer Site veröffentlicht werden. Im folgenden Screenshot einer AEM Site-Seite ist der Knoten `ditacontent` beispielsweise zum Speichern von DITA-Inhalten reserviert:

![](assets/publish-in-aem-site.png){width="300" align="left"}

Die verbleibenden Knoten auf der Seite werden direkt im AEM Site-Editor erstellt. Durch die Konfiguration der Veröffentlichungseinstellung zum Veröffentlichen von DITA-Inhalten an einem vordefinierten Speicherort wird sichergestellt, dass keiner Ihrer vorhandenen Nicht-DITA-Inhalte durch den AEM Guides-Veröffentlichungsprozess geändert wird.

Sie müssen die folgenden Konfigurationen auf Ihrer vorhandenen Site durchführen, um die Veröffentlichung von DITA-Inhalten in einem vordefinierten Knoten zu ermöglichen:

- Vorlageneigenschaften Ihrer Site konfigurieren

- Knoten zu Ihrer Site hinzufügen, um DITA-Inhalte zu veröffentlichen


Führen Sie die folgenden Schritte aus, um die Vorlageneigenschaften Ihrer vorhandenen Site zu konfigurieren:

1. Melden Sie sich bei AEM an und öffnen Sie den CRXDE Lite-Modus.

1. Navigieren Sie zum Vorlagenkonfigurationsknoten Ihrer Site. AEM Guides speichert beispielsweise die standardmäßigen Vorlagenkonfigurationen im folgenden Knoten:

   `/libs/fmdita/config/templates/default`

   >[!NOTE]
   >
   > Nehmen Sie keine Anpassungen in den Standardkonfigurationsdateien vor, die im Knoten `libs` verfügbar sind. Sie müssen eine Überlagerung des Knotens `libs` im Knoten `apps` erstellen und nur die erforderlichen Dateien im Knoten `apps` aktualisieren.

1. Fügen Sie die folgenden Eigenschaften hinzu:

   | Eigenschaftsname | Typ | Wert |
   |-------------|----|-----|
   | `topicContentNode` | Zeichenfolge | Geben Sie den Knotennamen an, unter dem Sie den DITA-Inhalt veröffentlichen möchten. Der Standardknoten, in dem AEM Guides DITA-Inhalte veröffentlicht, lautet beispielsweise: <br>`jcr:content/contentnode` |
   | `topicHeadNode` | Zeichenfolge | Geben Sie den Knotennamen an, unter dem Sie die Metadateninformationen Ihres DITA-Inhalts speichern möchten. Der Standardknoten, in dem AEM Guides Metadateninformationen speichert, lautet beispielsweise: <br>`jcr:content/headnode` |


Der folgende Screenshot zeigt die Eigenschaften, die im Standardvorlagenknoten von AEM Guides hinzugefügt wurden:

![](assets/add-content-node.png){width="800" align="left"}

Wenn Sie das nächste Mal DITA-Inhalte mithilfe der Vorlagenkonfigurationen Ihrer Site veröffentlichen, wird der Inhalt in den Knoten veröffentlicht, die in den Eigenschaften `topicContentNode` und `topicHeadNode` angegeben sind.

Bei vorhandenen Sites müssen Sie jedoch die Knoten `topicContentNode` und `topicHeadNode` manuell hinzufügen.

Führen Sie die folgenden Schritte aus, um die erforderlichen Knoten zu Ihrer vorhandenen Site hinzuzufügen:

1. Melden Sie sich bei AEM an und öffnen Sie den CRXDE Lite-Modus.

1. Suchen Sie `jcr:content` in Ihrem Site-Knoten.

1. Fügen Sie `topicContentNode` - und `topicHeadNode` -Knoten mit demselben Namen hinzu, den Sie in den Vorlagenkonfigurationen der Site angegeben haben.


## AEM Site-Ausgabe anpassen {#id166TG0B30WR}

AEM Guides unterstützt das Erstellen von Ausgaben in folgenden Formaten:

- AEM Site

- PDF

- HTML5
- EPUB
- Benutzerdefinierte Ausgabe über DITA-OT

Für die AEM Site-Ausgabe können Sie verschiedene Designvorlagen mit verschiedenen Ausgabeaufgaben zuweisen. Diese Designvorlagen können den DITA-Inhalt in verschiedenen Layouts rendern. Sie können beispielsweise verschiedene Designvorlagen für interne und externe Zielgruppen angeben.

Sie können auch benutzerdefinierte DITA Open Toolkit \(DITA-OT\)-Plug-ins mit AEM Guides verwenden. Sie können diese benutzerdefinierten DITA-OT-Plug-ins hochladen, um eine PDF-Ausgabe auf eine bestimmte Art zu generieren.

>[!TIP]
>
> Best Practices zum Erstellen AEM Site-Ausgabe finden Sie im Abschnitt *AEM Site-Veröffentlichung* im Best Practices-Handbuch[Anhang.md\#](appendix.md#) .

### Anpassen der Designvorlage zum Generieren der Ausgabe {#customize_xml-add-on}

AEM Guides verwendet eine Reihe vordefinierter Designvorlagen, um AEM Site-Ausgabe zu generieren. Sie können die Designvorlagen von AEM Guides anpassen, um die Ausgabe zu generieren, die Ihrem UnternehmensBranding entspricht. Eine Designvorlage ist eine Sammlung verschiedener Stile \(CSS\), Skripte \(Server- und Client-seitig\), Ressourcen \(Bilder, Logos und andere Assets\) und JCR-Knoten, die alle diese Ressourcen miteinander verknüpfen. Eine Designvorlage kann so einfach sein wie ein einzelnes serverseitiges Skript mit nur einigen JCR-Knoten oder eine komplexe Kombination von Stilen, Ressourcen und JCR-Knoten. Designvorlagen werden vom AEM Guides Publishing-Subsystem verwendet, während AEM Site-Ausgabe generiert wird. Sie steuern die Struktur, das Erscheinungsbild der generierten Ausgabe.

Es gibt keine Einschränkung, wo sich die Ressourcen für die Designvorlage auf dem Server befinden sollten, aber sie sind in der Regel entsprechend ihrer Funktion logisch organisiert. Beispielsweise werden in der Standardvorlage alle JavaScript- und CSS-Dateien im Ordner &quot;`/etc/designs/fmdita/clientlibs/siteoutput/default`&quot;gespeichert. Wo immer sich diese Dateien befinden, werden sie durch eine Sammlung von JCR-Knoten verknüpft. Gemeinsam bilden diese JCR-Knoten und die Dateien die gesamte Designvorlage.

Mit der im Lieferumfang von AEM Guides enthaltenen Standard-Designvorlage können Sie die Komponenten für Landingpages, Themen und Suchseiten anpassen. Sie können eine Kopie des Standarddesigns und der entsprechenden Referenzvorlagen erstellen und verschiedene Komponenten angeben, um die gewünschte Ausgabe zu generieren.

Führen Sie die folgenden Schritte aus, um Ihre eigene Designvorlage für AEM Site-Ausgabegenerierung festzulegen:

1. Melden Sie sich bei AEM an und öffnen Sie den CRXDE Lite-Modus.

1. Navigieren Sie zum Knoten der Standard-Designvorlage . Der Speicherort des Standardknotens der Designvorlage lautet:

   `/libs/fmdita/config/templates/`

   ![](assets/templates-node.png){width="300" align="left"}

   >[!NOTE]
   >
   > Erstellen Sie eine Kopie der Standardentwurfsvorlagen aus dem Ordner `libs` in den Ordner `apps` und nehmen Sie Änderungen im Ordner `apps` vor. Außerdem müssen Sie Änderungen an den Vorlagen vornehmen, auf die über den Standardvorlagenknoten verwiesen wird. Die referenzierten Vorlagen werden unter dem Knoten `/libs/fmdita/templates/default/cqtemplates` platziert. Erstellen Sie eine Kopie der referenzierten Vorlagen im Ordner `apps` , bevor Sie Änderungen vornehmen.

1. Klicken Sie auf die Komponente *default* im Knoten *templates* , um auf ihre Eigenschaften zuzugreifen.

   Die Eigenschaften der Designvorlagen von AEM Guides werden in der folgenden Tabelle beschrieben.

   | Eigenschaft | Beschreibung |
   |--------|-----------|
   | `landingPageTemplate`, `searchPageTemplate`, `topicPageTemplate`, `shadowPageTemplate` | Geben Sie den Knoten `cq:Template` für diese entsprechenden Seiten an \(Landingpage, Suche und Thema\). Standardmäßig befindet sich der Knoten `cq:Template` für diese Seiten im Knoten `/libs/fmdita/templates/default/cqtemplates` . Dieser Knoten definiert die Struktur und Eigenschaften der Landingpage, der Such- und der Themenseite. <br>Der `shadowPageTemplate` wird verwendet, um den Chunked-Inhalt zu optimieren. Sie müssen den Wert dieser Eigenschaft auf Folgendes festlegen: <br> `fmdita/templates/default/cqtemplates/shadowpage` <br> **Hinweis** Sie müssen einen Wert für den `topicPageTemplate` angeben. Die `landingPageTemplate` und `searchPageTemplate` sind optionale Eigenschaften. Wenn Sie nicht möchten, dass die Such- und Landingpages generiert werden, geben Sie diese Eigenschaften nicht an. |
   | `title` | Ein beschreibender Name Ihrer Designvorlage. |
   | `topicContentNode` | Der Speicherort des Knotens, der den DITA-Inhalt auf einer Themenseite enthält. Der Pfad ist relativ zur Themenseite. |
   | `topicHeadNode` | Der Speicherort des Knotens, der die Kopfwerte \(oder Metadaten\) enthält, die aus dem DITA-Inhalt abgeleitet wurden. Der Pfad ist relativ zur Themenseite. |
   | `tocNode` | Der Speicherort des Knotens, der das Inhaltsverzeichnis enthalten wird. Der Pfad ist relativ zur Landingpage oder zum Zielpfad. |
   | `basePathProp` | Der Eigenschaftsname zum Speichern des Pfads des Stammverzeichnisses der veröffentlichten Site. |
   | `indexPathProp` | Der Eigenschaftsname zum Speichern des Pfads der Landingpage/Indexseite der veröffentlichten Site. |
   | `pdfPathProp` | Der Eigenschaftsname zum Speichern des PDF-Pfads des Themas, wenn die PDF-Generierung des Themas aktiviert ist. |
   | `pdfTypeProp` | Der Eigenschaftsname zum Speichern des Typs der PDF-Generierung. Derzeit enthält diese Eigenschaft immer &quot;Thema&quot;. |
   | `searchPathProp` | Der Eigenschaftsname zum Speichern des Pfads der Suchseite, wenn die Vorlage eine Suchseite enthält. |
   | `siteTitleProp` | Der Eigenschaftsname zum Speichern des Titels der veröffentlichten Site. Dieser Titel ist normalerweise mit dem Titel der zu veröffentlichenden Karte identisch. |
   | `sourcePathProp` | Der Eigenschaftsname zum Speichern des Pfads des DITA-Quellthemas für die aktuelle Seite. |
   | `tocPathProp` | Der Eigenschaftsname zum Speichern des Pfads des TOC-Stammverzeichnisses für die veröffentlichte Site. |


>[!NOTE]
>
> Nachdem Sie einen benutzerdefinierten Designvorlagenknoten erstellt haben, müssen Sie die Option Design in den AEM Site-Ausgabevorgaben aktualisieren, um den benutzerdefinierten Designvorlagenknoten zu verwenden.

Weitere Informationen finden Sie unter [Erstellen der ersten Adobe Experience Manager 6.3-Website](https://helpx.adobe.com/experience-manager/using/first_aem63_website.html) und [Grundlagen](https://helpx.adobe.com/experience-manager/6-3/sites/developing/using/the-basics.html) zum Entwickeln Ihrer eigenen Website auf AEM.

### Dokumenttitel zum Generieren AEM Site-Ausgabe verwenden

Beim Generieren AEM Site-Ausgabe spielt die Art und Weise, wie URLs generiert werden, eine wichtige Rolle bei der Entdeckung Ihres Inhalts. Wenn Sie UUID-basierte Dateinamen verwenden, wäre das Generieren von URLs basierend auf der UUID Ihrer Dateien nicht suchfreundlich. Als Administrator oder Herausgeber haben Sie die Kontrolle darüber, wie Sie die URLs für Ihre AEM Site-Ausgabe generieren möchten. AEM Guides bietet eine Konfiguration, mit der Sie die URLs AEM Site-Ausgabe mithilfe des Dateinamens und nicht der UUID-basierten Dateinamen generieren können. Standardmäßig ist diese Option bei UUID-basierten Dateisystemen aktiviert. Dies bedeutet, dass beim Generieren AEM Site-Ausgabe für UUID-basierte Dateisysteme die Dateinamen zum Generieren der URLs und nicht der UUIDs der Dateien verwendet werden.

Beim Generieren AEM Site-Ausgabe spielt die Art und Weise, wie URLs generiert werden, eine wichtige Rolle bei der Entdeckung Ihres Inhalts. Bei nicht UUID-basierten Dateisystemen wird die AEM Site-Ausgabe unter Verwendung der Dateinamen und nicht der Dateinamen generiert. Als Administrator oder Herausgeber haben Sie die Kontrolle darüber, wie Sie die URLs für Ihre AEM Site-Ausgabe generieren möchten. AEM Guides bietet eine Konfiguration, mit der Sie die URLs AEM Site-Ausgabe mithilfe des Dateinamens und nicht der Dateinamen generieren können. Standardmäßig ist diese Option deaktiviert. Dies bedeutet, dass beim Generieren AEM Site-Ausgabe die Dateinamen zum Generieren der URLs und nicht des Dateinamens verwendet werden. Sie können die URLs anhand der Dateinamen generieren, indem Sie diese Option aktivieren.

>[!NOTE]
>
> Sie können Regeln weiter konfigurieren, sodass nur ein Zeichensatz in den URLs einer AEM Site-Ausgabe zulässig ist. Weitere Informationen finden Sie unter [Konfigurieren von Bereinigungsregeln für Dateinamen zum Erstellen von Themen und Veröffentlichen AEM Site-Ausgabe](#id2164D0KD0XA).

Um die URLs zu konfigurieren, die in AEM Site-Ausgabe generiert werden, führen Sie die folgenden Schritte aus:

1. Öffnen Sie die Seite Adobe Experience Manager Web Console Configuration .

   Die Standard-URL für den Zugriff auf die Konfigurationsseite lautet:

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Suchen Sie nach dem Bundle **com.adobe.fmdita.config.ConfigManager** und klicken Sie darauf.

1. Wählen Sie die Option **Titel für AEM Site-Seitennamen verwenden** aus.

   >[!NOTE]
   >
   > Wenn Sie die Ausgabe mit den Dateinamen generieren möchten, deaktivieren Sie diese Option.

1. Klicken Sie auf **Speichern**.


### Konfigurieren von Bereinigungsregeln für Dateinamen zum Erstellen von Themen und Veröffentlichen AEM Site-Ausgabe {#id2164D0KD0XA}

Als Administrator können Sie eine Liste gültiger Sonderzeichen definieren, die in Dateinamen zulässig sind und letztendlich die URL einer AEM Site-Ausgabe bilden. In früheren Versionen konnten Benutzer Dateinamen mit Sonderzeichen wie `@`, `$`, `>` und mehr definieren. Diese Sonderzeichen führten bei der Generierung AEM Site-Seiten zu einer kodierten URL.

Ab Version 3.8 wurden Konfigurationen hinzugefügt, um eine Liste von Sonderzeichen zu definieren, die in Dateinamen zulässig sind. Standardmäßig enthält die gültige Dateinamenkonfiguration &quot;`a-z A-Z 0-9 - _`&quot;. Dies bedeutet, dass Sie beim Erstellen einer Datei beliebige Sonderzeichen im Dateinamen haben können, diese jedoch intern durch einen Bindestrich \(`-`\) im Dateinamen ersetzt werden. Sie können beispielsweise den Titel der Datei als Einführung 1 oder Introduction@1 festlegen. Der entsprechende Dateiname, der für beide Fälle generiert wurde, wäre Einführung-1.

Beachten Sie bei der Definition einer Liste gültiger Zeichen, dass diese Zeichen &quot;`*/:[\]|#%{}?&<>"/+`&quot; und &quot;`a space`&quot; immer durch einen Bindestrich \(`-`\) ersetzt werden.

>[!NOTE]
>
> Wenn Sie die Liste der gültigen Sonderzeichen nicht konfigurieren, kann der Dateierstellungsprozess zu unerwarteten Ergebnissen führen.

So konfigurieren Sie die gültigen Sonderzeichen in Dateinamen und AEM Site-Ausgabe:

1. Öffnen Sie die Seite Adobe Experience Manager Web Console Configuration .

   Die Standard-URL für den Zugriff auf die Konfigurationsseite lautet:

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Suchen Sie nach dem Bundle *com.adobe.fmdita.common.SanitizeNodeNameImpl* und klicken Sie darauf.

1. Stellen Sie in der Eigenschaft **Unzulässige Zeichensätze für die Veröffentlichung in AEM Sites** sicher, dass die Eigenschaft auf ```'<>`@$``` festgelegt ist. Sie können dieser Liste weitere Sonderzeichen hinzufügen. Diese müssen jedoch über die folgenden Sonderzeichen verfügen.

   >[!NOTE]
   >
   > Sie können auch die anderen Eigenschaften konfigurieren, z. B. **Kleinbuchstaben verwenden** in Dateinamen, **Trennzeichen** zur Verarbeitung ungültiger Zeichen und **Maximale Zeichenanzahl** in den Dateinamen.

1. Klicken Sie auf **Speichern**.

1. Suchen Sie nach dem Bundle **com.adobe.fmdita.config.ConfigManager** und klicken Sie darauf.

1. Stellen Sie in der Eigenschaft **Regex für gültige Zeichen** sicher, dass die Eigenschaft auf `[-a-zA-Z0-9_]` festgelegt ist. Sie können dieser Liste weitere Zeichen hinzufügen. Sie muss jedoch diese einfachen Zeichen aufweisen und die Liste muss mit einem Bindestrich \(`-`\) beginnen.

   >[!NOTE]
   >
   > Diese Eigenschaft definiert die Liste der gültigen Zeichen, die zum Erstellen einer neuen Datei verwendet werden.

1. Klicken Sie auf **Speichern**.


### Reduzieren AEM Site-Knotenstruktur konfigurieren

Wenn Sie AEM Site-Ausgabe generieren, wird intern ein Knoten für jedes Element in den Themen erstellt. Für eine DITA-Map mit Tausenden von Themen kann diese Knotenstruktur zu tief werden. Diese Art von tief verschachtelter Knotenstruktur kann Leistungsprobleme bei größeren Sites haben. Die folgende Momentaufnahme zeigt eine tief verschachtelte Knotenstruktur für eine AEM Site-Ausgabe:

![](assets/deep-nested-aem-site-node-structure.png){width="300" align="left"}

Im obigen Schnappschuss sehen Sie, dass für jedes `p` -Element ein Knoten erstellt wird und dessen nachfolgende Unterelemente sowie eine ähnliche Struktur für jedes andere Element erstellt wird, das im Thema verwendet wird.

Mit AEM Guides können Sie konfigurieren, wie AEM Knotenstruktur der Site-Ausgabe intern erstellt wird. Sie können die Knotenstruktur bei bestimmten Elementen reduzieren. Das bedeutet, dass Sie ein Element definieren können, das als Hauptelement betrachtet wird. Alle darin enthaltenen Unterelemente werden mit dem Hauptelement zusammengeführt. Wenn Sie beispielsweise das Element `p` reduzieren möchten, wird jedes Element, das im Element `p` erscheint, mit dem Hauptelement `p` zusammengeführt. Für kein Unterelement innerhalb des Elements `p` wird ein separater Hinweis erstellt. Die folgende Momentaufnahme zeigt die Knotenstruktur, die auf das Element `p` reduziert wird:

![](assets/flattened-aem-site-node-structure.png){width="300" align="left"}

So reduzieren Sie AEM Site-Knotenstruktur:

1. Geben Sie das Element an, bei dem Sie die Knotenstruktur reduzieren möchten.

   1. Überlagern Sie den Knoten `libs` im Knoten `apps` und öffnen Sie die Datei &quot;elementmapping.xml&quot;.

   1. Fügen Sie die Eigenschaft `<flatten>true</flatten>` in die Definition des Elements ein, in dem Sie die Knotenstruktur reduzieren möchten. Beispiel: Wenn Sie die Knotenstruktur beim Element `p` reduzieren möchten, fügen Sie das Attribut flatten in der Definition des Elements `p` wie unten gezeigt hinzu:

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
      > Standardmäßig wurde die Eigenschaft &quot;flatten node&quot;im Element `p` konfiguriert.

1. Aktivieren Sie die Reduzierungskonfiguration des Site-Knotens in der configMgr.

   1. Öffnen Sie die Seite Adobe Experience Manager Web Console Configuration .

      Die Standard-URL für den Zugriff auf die Konfigurationsseite lautet:

      ```http
      http://<server name>:<port>/system/console/configMgr
      ```

   1. Suchen Sie nach dem Bundle *com.adobe.dxml.flattening.FlateningConfigurationService* und klicken Sie darauf.

   1. Wählen Sie die Option **Eigenschaft flachen.enabled** aus.

   1. Klicken Sie auf **Speichern**.


>[!IMPORTANT]
>
> Wenn Sie Änderungen an der Datei elementmapping.xml vorgenommen haben, stellen Sie sicher, dass Sie configMgr öffnen und jedes Bundle speichern, damit Änderungen wirksam werden.

Wenn Sie jetzt die Ausgabe der AEM Site generieren, werden die Knoten im Element `p` reduziert und im Element `p` selbst gespeichert. Sie finden die neuen Reduzierungseigenschaften für das Element `p` in CRXDE.

![](assets/flatten-aem-site-note-props-crxde.png){width="650" align="left"}

**Reduzieren der Struktur AEM Site-Notizen verhindern**

Ähnlich wie beim Festlegen des Knotens, der in AEM Site-Ausgabe reduziert werden soll, können Sie auch ein Element angeben, das Sie aus dieser Konfiguration ausschließen möchten. Wenn Sie beispielsweise Knoten beim Element `body` reduzieren möchten, aber kein Element `table` innerhalb von `body` reduziert werden soll, können Sie die Eigenschaft exclude innerhalb der Definition des Elements `table` hinzufügen.

Um das Element `table` vom Reduzieren auszuschließen, fügen Sie die folgende Eigenschaft zur Definition des Elements `table` hinzu:

`<preventancestorflattening>true|false</preventancestorflattening>`

### Versionierung für gelöschte Seiten in AEM Site-Ausgabe konfigurieren

Wenn Sie AEM Site-Ausgabe mit der für die Einstellung Vorhandene Ausgabeseiten ausgewählten Option **Löschen und** Erstellen ****generieren, wird eine Version für die zu löschende(n) Seite(n\) erstellt. Sie können das System so konfigurieren, dass vor dem Löschen die Erstellung einer Version angehalten wird.

Führen Sie die folgenden Schritte aus, um die Erstellung einer Version für die zu löschende(n\) Seite zu stoppen:

1. Öffnen Sie die Seite Adobe Experience Manager Web Console Configuration .

   Die Standard-URL für den Zugriff auf die Konfigurationsseite lautet:

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Suchen Sie nach dem Bundle *com.adobe.fmdita.config.ConfigManager* und klicken Sie darauf.

1. Wählen Sie die Option **Keine Version für gelöschte Seiten erstellen** aus.

   >[!NOTE]
   >
   > Wenn diese Option aktiviert ist, können Benutzer alle Seiten direkt löschen, ohne eine Version für sie zu erstellen. Wenn die Option nicht ausgewählt ist, wird eine Version erstellt, bevor die Seite\(n\) gelöscht wird.

1. Klicken Sie auf **Speichern**.

## Verwenden von Metadaten bei der Veröffentlichung der Ausgabe über DITA-OT {#id191LF0U0TY4}

AEM Guides bietet eine Möglichkeit, benutzerdefinierte Metadaten beim Veröffentlichen der Ausgabe mithilfe von DITA-OT zu übergeben. Als Administrator und Herausgeber müssen Sie die folgenden Aufgaben ausführen, um benutzerdefinierte Metadaten in der veröffentlichten Ausgabe zu konfigurieren und zu verwenden:

- Fügen Sie als Administrator die erforderlichen Metadaten im System hinzu, damit sie auf der Seite Eigenschaften der DITA-Zuordnung verfügbar gemacht werden.

- Fügen Sie als Administrator die benutzerdefinierten Metadaten in die Metadatenliste ein, damit sie in der DITA-Map-Konsole angezeigt werden.

- Konfigurieren und fügen Sie als Publisher die benutzerdefinierten Metadaten mit der DITA-Zuordnung hinzu und generieren Sie die erforderliche Ausgabe.


Um die erforderlichen Metadaten im System hinzuzufügen, führen Sie die folgenden Schritte aus:

1. Melden Sie sich bei Adobe Experience Manager als Administrator an.

1. Klicken Sie oben auf den Adobe Experience Manager-Link und wählen Sie **Tools** aus.

1. Wählen Sie **Assets** aus der Toolliste aus.

1. Klicken Sie auf die Kachel **Metadatenschemata** .

   Die Seite Metadatenschema Forms wird angezeigt.

1. Wählen Sie das Formular **default** aus der Liste aus.

   >[!NOTE]
   >
   > Die Eigenschaften, die auf der Seite Eigenschaften für eine DITA-Zuordnung angezeigt werden, stammen aus diesem Formular.

1. Klicken Sie auf **Bearbeiten**.

1. Fügen Sie die benutzerdefinierten Metadaten hinzu, die Sie in Ihren veröffentlichten Ausgaben verwenden möchten. Beispielsweise werden wir Zielgruppen-Metadaten mithilfe der folgenden Schritte hinzufügen:

   1. Ziehen Sie aus der Liste **Formular erstellen**-Komponenten die Komponente **Einzeiliger Text** in das Formular.

   1. Wählen Sie das neue Feld aus, um die **Einstellungen** des Felds zu öffnen.

   1. Geben Sie im Feld **Feldbezeichnung** den Metadatennamen &quot;Zielgruppe&quot;ein.

   1. Geben Sie in der Einstellung **Zu Eigenschaft zuordnen** an./jcr:content/metadata/&lt;Name der Metadaten\>. Für unser Beispiel setzen wir es auf ./jcr:content/metadata/audience.

   Fügen Sie mithilfe dieser Schritte alle erforderlichen Metadatenparameter hinzu.

1. Klicken Sie auf **Speichern**.


Der neue Parameter wird jetzt auf der Seite Eigenschaften für alle DITA-Maps angezeigt.

![](assets/properties-page-custom-metadata.PNG){width="650" align="left"}

Als Nächstes müssen Sie die benutzerdefinierten Metadaten in der DITA-Map-Konsole verfügbar machen. Führen Sie die folgenden Schritte aus, um die benutzerdefinierten Metadaten auf der DITA Map-Dashboards verfügbar zu machen:

1. Melden Sie sich bei AEM an und öffnen Sie den CRXDE Lite-Modus.

1. Greifen Sie auf die Datei &quot;metadataList&quot;zu, die unter folgendem Speicherort verfügbar ist:

   /libs/fmdita/config/metadataList

   >[!NOTE]
   >
   > Die Datei &quot;metadataList&quot;enthält eine Liste von Eigenschaften, die in der Dropdown-Liste **Eigenschaften** einer DITA-Zuordnung im Map-Dashboard angezeigt werden. Standardmäßig sind in dieser Datei vier Eigenschaften aufgelistet: docstate, dc:language, dc:description und dc:title.

1. Fügen Sie die benutzerdefinierten Metadaten hinzu, die Sie auf der Seite &quot;Metadatenschema-Forms&quot;hinzugefügt haben. Fügen Sie für unser Beispiel den Zielgruppenparameter am Ende der Standardliste hinzu.

1. Klicken Sie auf **Alle speichern**.


Jetzt werden die benutzerdefinierten Metadaten in der Dropdownliste **Eigenschaften** der DITA-Map-Konsole angezeigt.

Als Herausgeber müssen Sie schließlich die benutzerdefinierten Metadaten in die veröffentlichte Ausgabe aufnehmen. Um die benutzerdefinierten Metadaten beim Generieren der Ausgabe zu verarbeiten, führen Sie die folgenden Schritte aus:

1. Navigieren Sie in der Assets-Benutzeroberfläche zur DITA-Zuordnung, die Sie veröffentlichen möchten.

1. Wählen Sie die DITA-Map-Datei aus und öffnen Sie die zugehörige Eigenschaftenseite.

1. Geben Sie auf der Seite Eigenschaften den Wert für die benutzerdefinierten Metadaten an. Für unser Beispiel haben wir den Wert &quot;External&quot;für den Zielgruppenparameter angegeben.

   ![](assets/properties-page-custom-metadata-value.png){width="650" align="left"}

1. Klicken Sie auf **Speichern und schließen**.

1. Klicken Sie auf die DITA-Zuordnungsdatei, um die DITA-Zuordnungskonsole zu öffnen.

1. Wählen Sie auf der Registerkarte **Ausgabevorgaben** die Ausgabevorgabe aus, die Sie zum Generieren der Ausgabe verwenden möchten.

1. Klicken Sie auf **Bearbeiten**.

1. Wählen Sie aus der Dropdownliste **Eigenschaften** die Eigenschaften aus, die Sie an den Veröffentlichungsprozess weitergeben möchten.

   ![](assets/props-in-publish-output.PNG){width="650" align="left"}


Die ausgewählten Eigenschaften/Metadaten werden an den Veröffentlichungsprozess übergeben und in der endgültigen Ausgabe verfügbar gemacht.

## DITA-Elementzuordnung mit AEM Komponenten anpassen {#id1679J600HEL}

DITA-Elemente in AEM Guides werden ihren entsprechenden AEM-Komponenten zugeordnet. AEM Guides verwendet diese Zuordnung in Workflows wie Veröffentlichung und Überprüfung, um DITA-Elemente in eine entsprechende AEM zu konvertieren. Die Zuordnung wird in der Datei `elementmapping.xml` definiert, auf die über den CRXDE Lite-Modus zugegriffen werden kann. Greifen Sie im CRXDE Lite-Modus auf die folgende URL zu:

`/libs/fmdita/config/elementmapping.xml`

>[!NOTE]
>
> Nehmen Sie keine Anpassungen in den Standardkonfigurationsdateien vor, die im Knoten ``libs`` verfügbar sind. Sie müssen eine Überlagerung des Knotens ``libs`` im Knoten ``apps`` erstellen und nur die erforderlichen Dateien im Knoten ``apps`` aktualisieren.

Sie können die vordefinierten DITA-Elementzuordnungen verwenden oder DITA-Elemente Ihren benutzerdefinierten AEM zuordnen. Um Ihre benutzerdefinierten AEM-Komponenten zu verwenden, müssen Sie die Struktur der `elementmapping.xml`-Datei verstehen.

### elementmapping.xml structure

Eine allgemeine Übersicht über die Struktur von `elementmapping.xml` wird nachfolgend beschrieben:

1. Jedes DITA-Element wird zuerst nach einer entsprechenden Komponentenzuordnung basierend auf dem Elementnamen gesucht. Zum Beispiel:

   ```XML
   <ditaelement>     
      <name>**substeps**</name>  
      <class>- topic/ol task/substeps</class>  
      <componentpath>dita/components/ditaolist</componentpath>  
      <type>COMPOSITE</type>  
      <target>para</target>
   </ditaelement>
   ```

   Im obigen Beispiel werden alle `substeps` DITA-Elemente mit der Komponente `dita/components/ditaolist` gerendert.

1. Wenn ein DITA-Element keine Übereinstimmung basierend auf dem Namen findet, wird eine Übereinstimmung auf der Basis von `class` vorgenommen. Zum Beispiel:

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

   Wenn im obigen Beispiel keine Zuordnung für das Element `task` definiert ist, wird das Element `task` der obigen Komponente zugeordnet, da `task` von der Komponente `topic` übernommen wird.

1. Wenn ein Element über eine entsprechende Komponentenzuordnung verfügt, wird die weitere Verarbeitung seiner untergeordneten Elemente durch `type` bestimmt. Zum Beispiel:

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

   `type` akzeptiert die folgenden Werte:

   - COMPOSITE: Die Zuordnung von Element zu Komponente *wird auch für untergeordnete Elemente* fortgesetzt.

   - STANDALONE: Untergeordnete Elemente des aktuellen Elements werden *nicht weiter zugeordnet*.

   Wenn im obigen Beispiel das Element `<title>` untergeordnete Elemente enthält, werden diese keiner anderen Komponente zugeordnet. Die Komponente für das Element `<title>` ist für das Rendern aller untergeordneten Elemente innerhalb des Elements `<title>` verantwortlich.

1. Wenn einem einzelnen DITA-Element mehrere Komponenten zugeordnet sind, wird die beste Übereinstimmung für das Element ausgewählt. Um die beste Übereinstimmungskomponente auszuwählen, werden die Domäne und die strukturelle Spezialisierung von DITA-Elementen berücksichtigt.

   Wenn DITA-Elemente mit Domänenspezialisierung vorhanden sind und eine Komponente für die Domänenspezialisierung zugeordnet ist, erhält diese Komponente eine hohe Priorität.

   Wenn es DITA-Elemente mit struktureller Spezialisierung gibt und eine Komponente für strukturelle Spezialisierung zugeordnet ist, erhält diese Komponente eine hohe Priorität.

1. Sie können `<attributemap>` in der Elementzuordnung verwenden, um Attributwerte den entsprechenden Knoteneigenschaften zuzuordnen.

1. `textprop` kann zum Serialisieren des Textinhalts eines DITA-Elements zu einer Knoteneigenschaft verwendet werden. Darüber hinaus kann es mehrmals in einem Element-Tag verwendet werden, um den Textinhalt an mehreren Stellen in der veröffentlichten Hierarchie zu serialisieren. Sie können auch den Speicherort und Namen der Ziel-Property anpassen. Zum Beispiel:

   ```XML
   <ditaelement> 
       <name>title</name> 
       <class>- topic/title</class> 
       <componentpath>foundation/components/title</componentpath> 
       <type>STANDALONE</type> 
       <target>para</target> 
       <textprop>**jcr:title**</textprop>
   </ditaelement>
   ```

   Die obige Elementzuordnung gibt an, dass der Textinhalt des Elements `<title>` als Wert einer Eigenschaft mit dem Namen `jcr:title` auf dem Ausgabeknoten gespeichert wird.

1. `xmlprop` kann zum Serialisieren der gesamten XML für ein bestimmtes Element zu einer Knoteneigenschaft verwendet werden. Die Komponente kann dann diese Knoteneigenschaft lesen und benutzerdefiniertes Rendering durchführen. Zum Beispiel:

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

   Die obige Elementzuordnung gibt an, dass das gesamte XML-Markup für das Element `<svg-container>` als Wert einer Eigenschaft namens `data` auf dem Ausgabeknoten gespeichert wird.

1. Es gibt eine spezielle Attributzuordnung zur Verarbeitung der Pfadauflösung im Prozess der Ausgabegenerierung. Zum Beispiel:

   ```XML
   <attributemap> 
       <attribute from="href" to="fileReference" ispath="true" rel="source" /> 
       <attribute from="height" to="height" /> 
       <attribute from="width" to="width" />
   </attributemap>
   ```

   Für die obigen `attributemap` wird das Attribut `href` in Ihrem DITA-Element einer Knoteneigenschaft mit dem Namen `fileReference` zugeordnet. Da `ispath` jetzt auf `true` festgelegt ist, löst der Prozess zur Generierung der Ausgabe diesen Pfad auf und legt ihn dann in der Knoteneigenschaft `fileReference` fest.

   Wie diese Auflösung erfolgt, wird auf der Grundlage des Werts des Attributs `rel` im Attribut-Mapping bestimmt.

   - Wenn `rel=source`, wird der Wert von `href` in Bezug auf die DITA-Quelldatei aufgelöst, die derzeit verarbeitet wird. Der Wert von `href` wird aufgelöst und in den Wert der Eigenschaft `fileReference` eingefügt.

   - Wenn `rel=target`, wird der Wert von `href` in Bezug auf den Speicherort der Stammveröffentlichung aufgelöst. Der Wert von `href` wird aufgelöst und in den Wert der Eigenschaft `fileReference` eingefügt.

   Wenn Sie nicht möchten, dass eine Vorverarbeitung oder Auflösung für Pfadattribute erfolgt, müssen Sie das Attribut `ispath` nicht angeben. Der Wert wird unverändert kopiert und die Komponente kann die erforderliche Auflösung durchführen.


### DITA-Elementschema

Im Folgenden finden Sie ein Beispiel für das DITA-Elementschema in der Datei `elementmapping.xml` :

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
    <attribute from="attrname" to="propname" ispath="true|false" rel="source|target" />     
    </attributemap>     
    <skip>true|false</skip> 
</ditaelement>
```

In der folgenden Tabelle werden die Elemente im DITA-Elementschema beschrieben:

| Element | Beschreibung |
|-------|-----------|
| `<ditaelement>` | Der Knoten der obersten Ebene für jedes Zuordnungselement. |
| `<class>` | Das Klassenattribut des DITA-Zielelements, für das Sie die Komponente schreiben. <br>Beispielsweise lautet das Klassenattribut für das DITA-Thema: <br>`topic/topic` |
| `<componentpath>` | Der CRXDE-Pfad der zugeordneten AEM. |
| `<type>` | Mögliche Werte: <br>- **COMPOSITE**: Verarbeiten Sie untergeordnete Elemente sowie <br>- **STANDALONE**: Überspringt die Verarbeitung untergeordneter Elemente |
| `<attributeprop>` | Wird für die Zuordnung von serialisierten DITA-Attributen und -Werten zu AEM Knoten als Eigenschaft verwendet. Wenn Sie beispielsweise das Element `<note type="Caution">` haben und die für dieses Element zugeordnete Komponente den Wert `<attributeprop>attr_t</ attributeprop>` aufweist, werden das Attribut und der Wert des Knotens in die Eigenschaft `attr_t` des entsprechenden AEM Knotens \( `attr_t->type="caution"`\) serialisiert. |
| `<textprop>propname_t</textprop>` | Speichern Sie die Ausgabe `getTextContent()` in der Eigenschaft, die durch `propname_t.` **Hinweis:** definiert wurde. Dies ist eine optimierte Eigenschaft. |
| `<xmlprop>propname_x </xmlprop>` | Speichern Sie serialisiertes XML dieses Knotens in der Eigenschaft, die durch `propname_x.` **Hinweis:** definiert wird. Dies ist eine optimierte Eigenschaft. |
| `<xpath>` | Wenn das XPath-Element in der Elementzuordnung bereitgestellt wird, sollte die XPath-Bedingung zusammen mit dem Elementnamen und der Klasse ebenfalls erfüllt sein, damit die Komponentenzuordnung verwendet wird. |
| `<target>` | Platzieren Sie für das DITA-Element im CRX-Repository an dem angegebenen Speicherort. <br>Mögliche Werte:<br>- **head**: Unter dem Kopfknoten <br>- **text**: Unter dem Absatzknoten |
| `<wrapelement>` | Das HTML-Element, in das der Inhalt eingeschlossen werden soll. |
| `<wrapclass>` | Der Elementwert der Eigenschaft `wrapclass.` |
| `<attributemap>` | Container-Knoten, der mindestens einen `<attribute>` -Knoten enthält. |
| `<attribute from="attrname" to="propname" ispath="true|false" rel="source|target" />` | Ordnet die DITA-Attribute AEM Eigenschaften zu:<br>- **`from`**: DITA-Attributname<br>- **`to`**: AEM Name der Komponenteneigenschaft <br>- **`ispath`**: Wenn das Attribut ein Pfadwert ist \(z. B. *image*\)<br>- **`rel`**: Wenn der Pfad die Quelle oder das Ziel ist <br>**Hinweis:** Wenn `attrname` mit `%` und ordnen Sie dann `attrname minus '%'` der Eigenschaft &quot;`propname`&quot;zu. |

**Zusätzliche Hinweise**

- Wenn Sie die standardmäßige Elementzuordnung überschreiben möchten, sollten Sie die Änderungen nicht in der standardmäßigen `elementmapping.xml` -Datei vornehmen. Sie sollten eine neue Mapping-XML-Datei erstellen und die Datei an einem anderen Speicherort ablegen, vorzugsweise in dem von Ihnen erstellten benutzerdefinierten Apps-Ordner.

- In der Datei `elementmapping.xml` gibt es viele Zuordnungseinträge, die auf die Komponente &quot;fmdita/components/dita/wrapper&quot;verweisen. Wrapper ist eine generische Komponente, die relativ einfache DITA-Konstrukte rendert, die Eigenschaften auf ihrem Site-Knoten verwenden, um relevante HTML zu generieren. Sie verwendet die Eigenschaft `wrapelement` , um einschließende Tags zu generieren, und delegiert das untergeordnete Rendering an die entsprechenden Komponenten. Dies ist nützlich in Fällen, in denen Sie nur eine Container-Komponente benötigen. Anstatt eine neue Komponente zu erstellen, die ein bestimmtes Container-Tag wie `div` oder `p` rendert, können Sie die Wrapper-Komponente mit den Eigenschaften `wrapelement` und `wrapclass` verwenden, um denselben Effekt zu erzielen.

- Es wird nicht empfohlen, große Textmengen in String JCR-Eigenschaften zu speichern. Die optimierte Berechnung des Eigenschaftstyps bei der Ausgabegenerierung stellt sicher, dass große Textinhalte nicht als Zeichenfolgentyp gespeichert werden. Wenn stattdessen Inhalte gespeichert werden müssen, die größer als ein bestimmter Schwellenwert sind, wird der Eigenschaftstyp in binär geändert. Standardmäßig ist dieser Schwellenwert auf 512 Byte konfiguriert, kann jedoch im Configuration Manager \(*com.adobe.fmdita.config.ConfigManager*\) geändert werden, indem die Einstellung **Als binären Schwellenwert speichern** geändert wird.

- Wenn Sie einige \(und nicht alle\) der Elementzuordnungen überschreiben möchten, müssen Sie nicht die gesamte `elementmapping.xml` -Datei replizieren. Sie müssen eine neue XML-Zuordnungsdatei erstellen und nur die Elemente definieren, die Sie überschreiben.

- Nachdem Sie die XML-Datei am benutzerdefinierten Speicherort erstellt haben, aktualisieren Sie die Einstellung `Override Element Mapping` im Bundle `com.adobe.fmdita.config.ConfigManager` .


## DITA-Map-Konsole anpassen {#id188HC08M0CZ}

AEM Guides bietet Ihnen die Flexibilität, die Funktionen der DITA-Map-Konsole zu erweitern. Wenn Sie beispielsweise eine Reihe von Berichten haben, die sich von den in AEM Guides verfügbaren Berichten unterscheiden, können Sie diese Berichte zur Zuordnungskonsole hinzufügen. Um die Zuordnungskonsole anzupassen, müssen Sie eine AEM Client-Bibliothek \(oder ClientLib\) erstellen, die den Code enthält, um die benötigten Funktionen auszuführen.

>[!NOTE]
>
> Eine direkte Änderung an Seitenkomponenten wird nicht empfohlen, da sie durch neue Versionen des Produkts überschrieben wird.

AEM Guides stellt die Kategorie &quot;`apps.fmdita.dashboard-extn`&quot;zum Anpassen der Zuordnungskonsole bereit. Bei jedem Laden der Zuordnungskonsole wird die unter der Kategorie `apps.fmdita.dashboard-extn` erstellte Funktion ausgeführt und geladen.

>[!NOTE]
>
> Weitere Informationen zum Erstellen AEM Client-Bibliothek finden Sie unter [Verwenden Client-seitiger Bibliotheken](https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/clientlibs.html).

## Verarbeiten der Bilddarstellung während der Ausgabegenerierung {#id177BF0G0VY4}

AEM enthält eine Reihe von Standard-Workflows und Medien-Handles zur Verarbeitung von Assets. In AEM gibt es vordefinierte Workflows für die Verarbeitung von Assets für die häufigsten MIME-Typen. Normalerweise erstellt AEM für jedes Bild, das Sie hochladen, mehrere Ausgabeformate desselben Binärformats. Diese Ausgabedarstellungen können unterschiedlich groß sein, mit einer anderen Auflösung, einem hinzugefügten Wasserzeichen oder anderen geänderten Eigenschaften. Weitere Informationen dazu, wie AEM mit Assets umgehen, finden Sie unter [Verarbeiten von Assets mithilfe von Medien-Handlern und Workflows](https://helpx.adobe.com/experience-manager/6-5/assets/using/media-handlers.html) in AEM Dokumentation.

Mit AEM Guides können Sie konfigurieren, welche Bilddarstellung zum Zeitpunkt der Generierung der Ausgabe für Ihre Dokumente verwendet werden soll. Sie können beispielsweise aus einer der standardmäßigen Bildausgabeformate wählen oder eine erstellen und zum Veröffentlichen Ihrer Dokumente dasselbe verwenden. Die Bildwiedergabe-Zuordnung zum Veröffentlichen Ihrer Dokumente wird in der Datei `/libs/fmdita/config/ **renditionmap.xml**` gespeichert. Ein Codefragment der Datei `renditionmap.xml` stellt sich wie folgt dar:

>[!NOTE]
>
> Es wird empfohlen, eine Kopie der Datei `renditionmap.xml` im Ordner `apps` für alle Anpassungen zu erstellen.

```XML
<renditionmap>
   <mapelement>
      <mimetype>image/png</mimetype>
      <rendition output="AEMSITE">cq5dam.web.1280.1280.jpeg</rendition>
      <rendition output="PDF">original</rendition>
      <rendition output="HTML5">cq5dam.web.1280.1280.jpeg</rendition>
      <rendition output="EPUB">cq5dam.web.1280.1280.jpeg</rendition>
      <rendition output="CUSTOM">cq5dam.web.1280.1280.jpeg</rendition>
   </mapelement>
...
</renditionmap>
```

Das Element `mimetype` gibt den MIME-Typ des Dateiformats an. Das Element `rendition output` gibt den Typ des Ausgabeformats und den Namen der Ausgabedarstellung \(z. B. `cq5dam.web.1280.1280.jpeg`\) an, die zum Veröffentlichen der angegebenen Ausgabe verwendet werden soll. Sie können die Bildausgabeformate angeben, die für alle unterstützten Ausgabeformate verwendet werden sollen - AEMSITE, PDF, HTML5, EPUB und CUSTOM.

Wenn die angegebene Ausgabedarstellung nicht vorhanden ist, sucht der AEM Guides-Veröffentlichungsprozess zunächst nach der Webdarstellung des angegebenen Bildes. Wenn selbst die Webausgabe nicht gefunden wird, wird die ursprüngliche Ausgabe des Bildes verwendet.

>[!NOTE]
>
> Diese Bildausgabeformate steuern nur die Ausgabegenerierung. Die Webausgabe eines Bildes wird verwendet, wenn Sie ein Dokument zur Vorschau oder Überprüfung öffnen.

## Konfigurieren des Zeitrahmens für die automatische Bereinigung für den Ausgabestverlauf {#id19AAI070V8Q}

Wenn Sie eine Ausgabe generieren, wird die Ausgabe zusammen mit den Ausgabsprotokollen erstellt. Bei großen DITA-Maps können diese Protokolle viel Platz in Ihrem Repository beanspruchen. Standardmäßig werden die Protokolle am folgenden Speicherort im Repository gespeichert:

/var/dxml/metadata/outputHistory/

Über einen bestimmten Zeitraum konnte die kollektive Größe aller Protokolldateien in GBs dargestellt werden. Mit AEM Guides können Sie einen Zeitraum konfigurieren, um diese Protokolldateien im Repository zu speichern. Nach dem angegebenen Zeitraum werden die Protokolle zusammen mit dem Ausgabegenerierungsverlauf aus dem Repository gelöscht.

>[!NOTE]
>
> Der Ausgabegenerierungsverlauf ist der Protokolleintrag in der Liste Erzeugte Ausgaben auf der Registerkarte Ausgaben .

Die Konfiguration der Verlaufsbereinigungsfunktion wirkt sich auf die Generierung der Ausgabe für alle DITA-Maps im Repository aus. Auf der Registerkarte &quot;Outputs&quot;einer DITA-Zuordnung wird der Verlauf nach der angegebenen Anzahl von Tagen und zu der in der Einstellung festgelegten Zeit bereinigt.

>[!NOTE]
>
> Das Entfernen der Protokolldateien und des Ausgabegenerierungsverlaufs hat keine Auswirkungen auf die generierte Ausgabe.

Führen Sie die folgenden Schritte aus, um einen Tag und eine Uhrzeit für die Bereinigung des Ausgabedarstellungsverlaufs und der -protokolle festzulegen:

1. Öffnen Sie die Seite Adobe Experience Manager Web Console Configuration .

   Die Standard-URL für den Zugriff auf die Konfigurationsseite lautet:

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Suchen Sie nach dem Bundle **com.adobe.fmdita.config.ConfigManager** und klicken Sie darauf.

1. Geben Sie in der Eigenschaft &quot;**Bereinigungszeitraum für Ausgabedarstellungsverlauf**&quot;die Anzahl der Tage an, nach denen der Ausgabedarstellungsverlauf zusammen mit den Ausgabsprotokollen bereinigt werden soll. Standardmäßig ist er auf 5 Tage eingestellt. Wenn Sie diese Funktion deaktivieren möchten, legen Sie diese Eigenschaft auf 0 fest.

1. Geben Sie in der Eigenschaft **Bereinigungszeit für Ausgabeverlauf** den Zeitpunkt an, zu dem der Bereinigungsprozess eingeleitet wird. Standardmäßig ist sie auf 0:00 \(oder 12:00 Mitternacht\) eingestellt. Zu diesem Zeitpunkt wird der Bereinigungsprozess täglich für Ausgaben ausgeführt, die vor der Anzahl der Tage generiert wurden, die in der Eigenschaft **Bereinigungszeitraum des Ausgabenverlaufs** angegeben sind.

   >[!NOTE]
   >
   > Standardmäßig wird die Bereinigungsfunktion jeden Mitternacht bei Ausgaben ausgeführt, die älter als 5 Tage sind.

1. Klicken Sie auf **Speichern**.


## Ändern der zuletzt generierten Ausgabelistenbegrenzung {#id1679JH0H0O2}

Sie können die maximale Anzahl der generierten Ausgaben ändern, die auf der Registerkarte &quot;Ausgaben&quot;für eine DITA-Zuordnung angezeigt werden. Standardmäßig wird eine Liste der letzten 25 generierten Ausgaben angezeigt. Um die Anzahl der Ausgaben zu ändern, die in der Liste angezeigt werden sollen, aktualisieren Sie die Einstellung **Ausgabelisten-Limit** im Bundle `com.adobe.fmdita.config.ConfigManager` .

>[!TIP]
>
> Best Practices zum Arbeiten mit dem Ausgabedarstellungsverlauf finden Sie im Abschnitt *Ausgabedarstellungsverlauf* im Best Practices-Handbuch[Anhang.md\#](appendix.md#) .

## Leistungsoptimierung der Ausgabenerstellung {#id176LB050VUI}

Mit AEM Guides können Sie die Poolgröße der Ausgabegenerierungsprozesse konfigurieren, die die Anzahl der gleichzeitig ausgeführten Output-Generierungsprozesse steuert. Standardmäßig ist die Größe des Prozess-Pools auf die Anzahl der in Ihrem System verfügbaren Prozessorkerne plus 1 eingestellt. Sie können diesen Wert in 1 ändern, falls Sie eine sequenzielle Veröffentlichung wünschen. In diesem Fall wird die erste Veröffentlichungsaufgabe ausgeführt und die nächste Veröffentlichungsaufgabe wird in der Veröffentlichungswarteschlange gespeichert.

Um die Größe des Pools für die Verarbeitung der Ausgabegenerierung zu ändern, aktualisieren Sie die Einstellung **Generierungspolgröße** im Bundle `com.adobe.fmdita.publish.manager.PublishThreadManagerImpl` .
