---
title: DITA-Zuordnungsbericht aus dem Web-Editor
description: Generieren Sie DITA-Map-Berichte aus dem Web-Editor in AEM Guides. Erfahren Sie, wie Sie eine CSV-Datei für Themenlisten, Multimedia-, Metadaten- und Berichte zu fehlerhaften Links erstellen.
exl-id: 2f202b41-85d9-4a5a-aa28-e25715ce5e2e
feature: Report Generation
role: User
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '2366'
ht-degree: 0%

---

# DITA-Zuordnungsbericht aus dem Web-Editor {#id231HF0Z0NXA}

AEM Guides verfügt über eine Funktion im Web Editor, mit der Sie die Gesamtintegrität Ihrer Verweise überprüfen und Berichte für diese generieren können.

Sie können die Themenliste anzeigen, die Metadaten aller Verweise verwalten und die Multimedia-Liste für die aktuelle Zuordnung auf der Registerkarte **Berichte** im Web Editor anzeigen.

## Erstellen einer CSV-Datei aus der Themenlistenansicht

Die Ansicht &quot;**Themenliste**&quot;enthält detaillierte Informationen zu Ihren Themen, wie den Referenztyp, den Dokumentstatus und den Autor.

Sie können einen Bericht zu den Themen erstellen, indem Sie die folgenden Schritte ausführen:

1. Öffnen Sie im Bedienfeld **Repository** die DITA-Map-Datei in der Kartenansicht.
1. Klicken Sie auf die Registerkarte **Verwalten**.
1. Doppelklicken Sie auf der linken Seite auf **Themenliste** . Die Liste der in der DITA-Map vorhandenen Themen wird angezeigt.

   ![](images/web-editor-topiclist-panel.png){width="800" align="left"}

1. Im Bedienfeld **Filter** können Sie Ihre Themen nach dem **Referenztyp** \(direkt oder indirekt\), dem **Dokumentstatus** \(dem aktuellen Status Ihrer Themen) filtern. Wenn sich Ihre Themen beispielsweise im Status &quot;Bearbeiten&quot;, &quot;In Prüfung&quot;oder &quot;Überprüfen&quot;befinden, werden sie aufgelistet\) oder der **Autor** des Themas.

1. Sie können auch die folgenden Themenfilteroptionen verwenden, um die folgenden Spalten in der Liste anzuzeigen:

   - **Thema** Der Titel des Themas wird in der DITA-Zuordnung angegeben. Sie können auf das Thema klicken, um es zu bearbeiten.
   - **Dateiname** Name der Datei.
   - **UUID** Die universelle eindeutige Kennung \(UUID\) der Datei.
   - **Dateispeicherort** Der vollständige Pfad des Themas.
   - **Verweistyp** Der Verweistyp - direkt oder indirekt.
   - **Dokumentenstatus** Der aktuelle Status des Themas.
   - **Autor** Der Benutzer, der zuletzt am Thema gearbeitet hat.
   - **Übergeordnete Zuordnung** Die Liste aller Maps, auf die direkt auf das Thema verwiesen wird.
   >[!NOTE]
   >
   > Klicken Sie auf **Aktualisieren** , um eine neue Liste der Themen abzurufen und alle Änderungen in Ihrer Zuordnungsdatei anzuzeigen oder zu überprüfen, ob ein Verweis in Ihrer Themendatei aktualisiert wird.

1. Klicken Sie auf **CSV herunterladen** , um die aktuelle Momentaufnahme der Themen in der DITA-Map herunterzuladen. Die CSV-Datei enthält die ausgewählten Spalten und die in der Ansicht **Themenliste** gefilterten Themen. Anschließend können Sie diese CSV-Datei mit der Themenliste in einem beliebigen CSV-Editor öffnen.

**Metadaten stapelweise aus dem Metadatenbericht verwalten**

Mit AEM Guides können Sie DITA-Inhalte über den Web-Editor taggen. Sie können Tags auf ein einzelnes Thema anwenden oder die Bulk-Tagging-Funktion verwenden, um mehrere Tags auf mehrere Themen, eine DITA-Map oder eine Unterzuordnung anzuwenden. Sie können auch den Dokumentstatus aller ausgewählten Themen in den nächsten möglichen allgemeinen Dokumentstatus ändern.

## Anzeigen von Metadaten

Führen Sie die folgenden Schritte aus, um die Metadaten Ihrer Referenzen in der aktuellen DITA-Zuordnung anzuzeigen:

1. Öffnen Sie im Bereich &quot;Repository&quot;die DITA-Map-Datei in der Kartenansicht.
1. Klicken Sie auf die Registerkarte **Verwalten**.
1. Doppelklicken Sie links auf **Metadaten** . Die Metadatenliste aller Verweise in der DITA-Zuordnung wird angezeigt. Dazu gehören auch die Medienreferenzen.

   ![](images/web-editor-metadata-panel.png){width="800" align="left"}

1. Im Bereich **Filter** können Sie Ihre Themen nach dem **Dokumentstatus** filtern \(dem aktuellen Status Ihrer Themen). Wenn sich Ihre Themen beispielsweise im Status &quot;Bearbeiten&quot;, &quot;In Prüfung&quot;oder &quot;Überprüfen&quot;befinden, werden sie aufgelistet\), **Verweise** \(direkt oder indirekt\), **Dateityp** \(Zuordnung, Thema und Bild\) des Verweises.
1. Sie können auch festlegen, dass nur die **Dateien ohne Tags** angezeigt werden sollen, oder Sie können bestimmte Tags aus dem Filter **Tags** auswählen, um die mit ihnen verknüpften Dateien anzuzeigen.
   1. Sie können auch die folgenden Themenfilteroptionen verwenden, um die folgenden Spalten in der Metadatenliste anzuzeigen:
      - **Titel** \(standardmäßig ausgewählt\) Der Titel der referenzierten Datei wird in der DITA-Zuordnung angegeben. Sie können auf die Datei klicken, um sie zu bearbeiten. Sie können auch im Web Editor auf eine Audio- oder Videodatei klicken und diese wiedergeben. Sie können die Lautstärke oder die Ansicht des Videos ändern. Im Kontextmenü haben Sie auch die Möglichkeit, Bilder herunterzuladen, die Wiedergabegeschwindigkeit zu ändern oder Bilder im Bild anzuzeigen.

        >[!NOTE]
        >
        > Neben dem Titel einer ausgecheckten Datei wird auch ein Symbol zum Auschecken angezeigt. Sie können den Mauszeiger über das Symbol bewegen, um den Namen des Benutzers anzuzeigen.

      - **Dateiname** Der Name der Datei.
      - **Dateispeicherort** Der vollständige Pfad der Datei.
      - **Tags** \(standardmäßig ausgewählt\) Auf die Datei angewendete Tags.

        >[!NOTE]
        >
        > Standardmäßig können Sie zwei Tags für eine Datei anzeigen. Um weitere Tags anzuzeigen, klicken Sie auf **Mehr anzeigen**. Klicken Sie auf **Weniger anzeigen** , um die Liste erneut zu vereinigen.

      - **Verweistyp** Der Verweistyp - direkt oder indirekt
      - **Dokumentstatus** \(standardmäßig ausgewählt\) Der aktuelle Status der Referenzdatei.
      - **Dateityp** \(standardmäßig ausgewählt\) Typ der Quelldatei. Die verfügbaren Optionen sind &quot;Zuordnung&quot;, &quot;Thema&quot;und &quot;Bild&quot;.
      - **Ausgecheckt von** Der Benutzer, der die Datei ausgecheckt hat.
1. Klicken Sie auf **CSV herunterladen** , um die aktuelle Momentaufnahme der Verweise in der DITA-Map herunterzuladen. Die CSV-Datei enthält die ausgewählten Spalten und die in der Ansicht &quot;Themenliste&quot;gefilterten Referenzen. Sie können diese Metadaten-CSV-Datei dann in einem beliebigen CSV-Editor öffnen.

**Aktualisieren von Metadaten**

1. Um Metadaten zu aktualisieren, wählen Sie die Dateien aus, für die Sie aktualisieren möchten.

   >[!NOTE]
   >
   > Es ist nicht möglich, ausgecheckte Dateien auszuwählen. Neben dem Titel einer ausgecheckten Datei wird auch ein Symbol zum Auschecken angezeigt. Sie können den Mauszeiger über das Symbol bewegen, um den Namen des Benutzers anzuzeigen.

1. Wählen Sie oben **Verwalten** aus.

   ![](images/web-editor-manage-metadata.png){width="350" align="left"}

1. Wenn Sie neue Tags hinzufügen möchten, wählen Sie neue Tags aus der Dropdown-Liste aus, um sie auf alle ausgewählten Themen anzuwenden. Sie können auch ein beliebiges Tag löschen, indem Sie auf das Kreuzsymbol neben dem Tag klicken.

   >[!NOTE]
   >
   > Die allgemeinen Tags, die auf alle ausgewählten Themen angewendet werden, werden aufgelistet.

1. Wählen Sie einen neuen Dokumentstatus aus, wenn Sie den Dokumentstatus aller ausgewählten Verweise ändern möchten. Das Dopdown zeigt den gemeinsamen möglichen Status für alle ausgewählten Themen an. Wenn der aktuelle Status Ihrer Themen beispielsweise In-Review lautet, können Sie den Status &quot;Entwurf&quot;, &quot;Genehmigt&quot;oder &quot;Überprüfen&quot;anzeigen.
1. Klicken Sie auf **Aktualisieren** , um die Metadaten zu aktualisieren. Eine Bestätigungsmeldung wird für die Metadaten angezeigt, unabhängig davon, ob sie erfolgreich aktualisiert wurden oder fehlgeschlagene Aktualisierungen aufweisen. Sie klicken auch auf **Bericht herunterladen** , um die Metadaten-CSV-Datei aus dem Bestätigungsdialogfeld herunterzuladen. Diese CSV-Datei enthält die Details zum Aktualisierungsstatus für die ausgewählten Verweise.

## Multimedia-Bericht erstellen

Der Bericht **Multimedia** enthält detaillierte Informationen zu den in Ihrer Zuordnung verwendeten Multimedia-Dateien, wie den Titel, den Typ \(Audio, Video und Bilder\), die Dateien, in denen Multimedia verwendet wird, und den Referenztyp der Dateien, in denen sie verwendet wurden. Sie können auch die UUID und den Speicherort der Multimedia-Dateien im Repository anzeigen. Sie können einen Multimedia-Bericht erstellen, indem Sie die folgenden Schritte ausführen:

1. Öffnen Sie im Bedienfeld **Repository** die DITA-Map-Datei in der Kartenansicht.
1. Klicken Sie auf die Registerkarte **Verwalten**.
1. Doppelklicken Sie links auf **Multimedia** . Die Liste der in der DITA-Karte vorhandenen Multimedia-Dateien wird angezeigt.
1. Im Bedienfeld **Filter** können Sie die Liste nach Multimedia oder nach den Namen von sortieren, die in Verweisen verwendet werden.

   - Bei der Bestellung durch **Multimedia** wird der Name des Multimedia-Programms in der ersten Spalte angezeigt und dann werden die Namen aller Verweise, in denen sie verwendet wurden, in einer anderen Spalte in derselben Zeile angezeigt. Der folgende Screenshot zeigt beispielsweise die Multimedia-Datei WarmCoolForC.gif in der ersten Spalte und drei Referenzen, in denen sie verwendet wird, werden in der dritten Spalte in derselben Zeile angezeigt.

     ![](images/multimedia-report-file-order.png){width="650" align="left"}

   - Wenn Sie nach der Spalte **Verwendet in** bestellen, wird die verschobene Ansicht angezeigt, in der die Namen der Verweise, in denen Multimedia verwendet wurde, in der ersten Spalte aufgeführt sind, während die Multimedia-Namen in einer anderen Spalte in separaten Zeilen aufgeführt sind. Der folgende Screenshot zeigt beispielsweise die Namen der drei Verweise \(Sitztemperatur anpassen, Sitztemperatur ändern und Besatzfläche ändern\) in der ersten Spalte und das Multimedia WarmCoolForC.gif wird in der dritten Spalte in drei separaten Zeilen angezeigt.

     ![](images/multimedia-report-used-in-order.png){width="650" align="left"}

1. Sie können Ihre Multimedia-Daten nach dem **Multimediatyp** und dem **Referenztyp** filtern. Die Liste der Multimedia-Dateien wird je nach Auswahl in der Dropdown-Liste angezeigt. Sie können beispielsweise festlegen, dass nur die Audioverweise in Ihrer DITA-Zuordnung angezeigt werden und eine Datei nur die darin verwendeten Audioverweise anzeigt.

   >[!NOTE]
   >
   > Je nach dem Typ des Multimediums, das in Ihrer Zuordnung verwendet wird, werden Bild, Video und Audio in der Dropdown-Liste **Multimedientyp** aufgelistet und Direkt oder Indirect in der Dropdown-Liste **Referenztyp** aufgeführt.

1. Sie können auch die folgenden Filteroptionen verwenden, um die folgenden Spalten in der Liste anzuzeigen:

   - **Multimedia** \(standardmäßig ausgewählt\) Der Titel des Multimediums wird in der DITA-Zuordnung angegeben. Sie können auf das Multimedia klicken, um es zu bearbeiten.
   - **Multimedia-Speicherort** Der vollständige Pfad der Multimedia-Dateien.
   - **Multimedia-UUID** Die universelle eindeutige Kennung \(UUID\) der Datei.
   - **Multimedia-Typ** \(standardmäßig ausgewählt\) Typ des Multimediums. Die verfügbaren Optionen sind Audio, Video oder Bild.
   - **Verwendet in** \(standardmäßig ausgewählt\) Die Verweise, in denen das Multimedia verwendet wurde. Sie können auf die Referenz klicken, um sie zu bearbeiten.
   - **Verweistyp** \(standardmäßig ausgewählt\) Der Verweistyp - direkt oder indirekt.
   >[!NOTE]
   >
   > Klicken Sie auf **Aktualisieren** , um eine neue Liste der Multimedia-Dateien zu erhalten und alle Änderungen in Ihrer Map-Datei anzuzeigen oder ob Multimedia in Ihrer DITA-Map aktualisiert wird.

1. Sie können auch im Web Editor auf eine Audio- oder Videodatei klicken und diese wiedergeben. Sie können die Lautstärke oder die Ansicht des Videos ändern. Im Kontextmenü haben Sie auch die Möglichkeit, Bilder herunterzuladen, die Wiedergabegeschwindigkeit zu ändern oder Bilder im Bild anzuzeigen.

   ![](images/video-web-editor.png){width="800" align="left"}

1. Klicken Sie auf **CSV herunterladen** , um die aktuelle Momentaufnahme der Multimedia-Dateien in die DITA-Map herunterzuladen. Die CSV-Datei enthält die ausgewählten Spalten und die Multimedia-Datei, die in der Ansicht **Multimedia** gefiltert wurden. Sie können diese Multimedia-CSV-Datei dann in einem beliebigen CSV-Editor öffnen.


## Fehlerbehebung bei fehlerhaften Links{#report-broken-links}

**Beschädigte Links** ist ein nützlicher Bericht, der Ihnen die Details der fehlerhaften Links auf Ihrer aktuellen Zuordnung liefert. Sie können die fehlerhaften Links anzeigen, die für DITA-Themen, Multimedia-Dateiverweise, Content-Schlüssel-Verweise usw. sein können. Sie haben auch die Möglichkeit, diese hier selbst zu reparieren.
Der Bericht enthält detaillierte Informationen wie den fehlerhaften Link, den Link-Typ, die Dateien, in denen die Referenz verwendet wird, und den Typ der Dateien, in denen sie verwendet wurden.
Sie können den Bericht auf fehlerhafte Links anzeigen, indem Sie die folgenden Schritte ausführen:
1. Öffnen Sie im Bedienfeld **Repository** die DITA-Map-Datei in der Kartenansicht.
1. Klicken Sie auf die Registerkarte **Verwalten**.
1. Doppelklicken Sie auf der linken Seite auf **Beschädigte Links** . Die Liste der fehlerhaften Links oder Verweise, die in der DITA-Zuordnung vorhanden sind, wird angezeigt.
1. Im Bedienfeld **Filter** können Sie die Liste nach Links oder nach den Namen von sortieren, die in Verweisen verwendet werden.

   - Wenn Sie nach **Beschädigter Link** sortieren, werden die Pfade der fehlerhaften Links in der ersten Spalte angezeigt und dann werden die Namen aller Verweise, in denen sie verwendet wurden, in einer anderen Spalte in separaten Zeilen angezeigt. Wenn derselbe fehlerhafte Link in mehreren Dateien verwendet wird, werden sie in einer Zeile angezeigt und als gruppierte Zeilen oder Unterzeilen angezeigt. Der folgende Screenshot zeigt beispielsweise drei fehlerhafte Links in der ersten Spalte und die Referenz, in der sie verwendet werden, `TestMap.ditamap` wird in der dritten Spalte in drei separaten Zeilen angezeigt.
   ![](images/broken-link-report.png){width="800" align="left"}

   - Wenn Sie nach der Spalte **Verwendet in** bestellen, wird die verschobene Ansicht angezeigt, in der die Namen der Verweise, in denen die fehlerhaften Links verwendet wurden, in der ersten Spalte aufgeführt sind, während die fehlerhaften Links in einer anderen Spalte in derselben Zeile aufgeführt sind. Der folgende Screenshot zeigt beispielsweise den Verweis (in dem der fehlerhafte Link verwendet wird) `TestMap.ditamap` in der ersten Spalte und die fehlerhaften Links in der dritten Spalte in derselben Zeile.
   ![](images/broken-link-filter-usedin.png){width="800" align="left"}
1. Sie können fehlerhafte Links nach **Dateityp** und **Link-Typ** filtern. Die Liste der fehlerhaften Links wird basierend auf Ihrer Auswahl in der Dropdown-Liste angezeigt. Sie können beispielsweise festlegen, dass nur die Inhaltsreferenzen in Ihrer DITA-Zuordnung angezeigt werden und eine Datei nur die darin verwendeten Inhaltsreferenzen anzeigt.

   Je nach dem Typ der in Ihrer Zuordnung verwendeten Referenzen werden in der Dropdown-Liste **Linktyp** und im Dropdown-Menü **DITA-Thema** oder **DITA-Karte** die Verweise auf Datei, Schlüssel, Inhaltsreferenz, Content Key Reference, Image Reference und Multimedia File Reference aufgeführt.****
1. Sie können auch die folgenden Filteroptionen verwenden, um die folgenden Spalten in der Liste anzuzeigen:

   - **Beschädigter Link** (standardmäßig ausgewählt) Der Pfad des fehlerhaften Links wird in der DITA-Zuordnung angegeben.

   - **Link-Typ** (standardmäßig ausgewählt) Der Typ der Links. Die verfügbaren Optionen sind Content Key Reference, Content Reference, DITA Topic, File Reference, Image Reference, Key reference, and Multimedia File Reference.

   - **Verwendet in** (standardmäßig ausgewählt) Die Verweise, in denen der fehlerhafte Link verwendet wurde. Sie können auf die Referenz klicken, um sie im Autorenmodus anzuzeigen.

   - **Dateityp** (standardmäßig ausgewählt) Der Typ des Verweises - DITA Map oder DITA-Thema.
Klicken Sie auf **Aktualisieren** , um eine neue Liste mit fehlerhaften Links abzurufen und alle Änderungen in Ihrer Map-Datei anzuzeigen oder ob ein beschädigter Link in Ihrer DITA-Map aktualisiert wird.
1. Sie können auf das Symbol **Link reparieren** (![](images/fix-broken-link.svg)) klicken, um den fehlerhaften Link zu beheben.

   >[!NOTE]
   >
   > Bewegen Sie den Mauszeiger über den Pfad des fehlerhaften Links unter der Spalte &quot;Beschädigter Link&quot;, um das Symbol &quot;Link reparieren&quot;(![](images/fix-broken-link.svg)) anzuzeigen.

   Sie können einen Link in beiden Ansichten korrigieren, wenn Sie nach **Beschädigten Links** oder nach **Verwendet in** bestellt haben.

   >[!NOTE]
   >
   > Wenn Sie einen fehlerhaften Link korrigieren, während Sie nach fehlerhaften Links sortiert haben, wird der Link in allen Dateien behoben, in denen er verwendet wird (die in einer einzigen Zeile gruppiert sind).

1. Sie müssen die erforderlichen Referenzdetails im Dialogfeld **Link aktualisieren** aktualisieren. Die im Dialogfeld **Link aktualisieren** erforderlichen Details hängen vom Referenztyp ab.\
   Wenn Sie einen Link korrigieren, wird er nicht unter der Liste der fehlerhaften Links angezeigt. Stattdessen können Sie sie unter der Themenliste oder den Metadaten anzeigen.

1. Klicken Sie auf **CSV herunterladen** , um die aktuelle Momentaufnahme der fehlerhaften Links in der DITA-Map herunterzuladen. Die CSV-Datei enthält die ausgewählten Spalten und die fehlerhaften Links, die in der Ansicht &quot;Broken Links&quot;gefiltert wurden. Sie können diese CSV-Datei dann in einem beliebigen CSV-Editor öffnen und anzeigen.


**Übergeordnetes Thema:**[ Berichte](reports-intro.md)
