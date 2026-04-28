---
title: Arbeiten mit dem erweiterten Zuordnungs-Editor
description: Erfahren Sie, wie Sie mit dem erweiterten Zuordnungs-Editor in AEM Guides arbeiten. Machen Sie sich mit den Funktionen des erweiterten Karten-Editors vertraut. Bearbeiten Sie Themen über eine DITA-Karte und verwenden Sie die Layout-Ansicht, die Autorenansicht und den Vorschaumodus.
feature: Authoring, Map Editor
role: User
hide: true
exl-id: b63d7c0f-9c29-4fb4-b8fe-9790b16f8726
source-git-commit: a70b3ce942b3e69445ad1d7ba6c8f7542e0ff176
workflow-type: tm+mt
source-wordcount: '3838'
ht-degree: 0%

---

# Arbeiten mit dem erweiterten Zuordnungs-Editor {#id1942D0S0IHS}

Der erweiterte Zuordnungs-Editor verfügt über eine intuitive Benutzeroberfläche und ähnelt dem Web-Editor. Wenn Sie eine Zuordnungsdatei im Web-Editor öffnen, erhalten Sie die Möglichkeit, die Zuordnungsdatei mithilfe der erweiterten Benutzeroberfläche des Zuordnungs-Editors zu bearbeiten. Mit dem erweiterten Zuordnungs-Editor können Sie Themenreferenzen, wichtige Verweise hinzufügen, Inhalte strukturieren und vieles mehr.

Zusätzlich zur Bearbeitung von Zuordnungsdateien direkt über den Web-Editor können Sie auch Themendateien in einer Zuordnung öffnen, um den Web-Editor zu bearbeiten. Dieses Thema führt Sie durch die Funktionen im erweiterten Zuordnungs-Editor und zeigt Ihnen, wie Sie Dateien in einer DITA-Zuordnung im Web-Editor öffnen und bearbeiten können.

## Themen zu einer Zuordnungsdatei hinzufügen

Führen Sie die folgenden Schritte aus, um Ihre Zuordnungsdatei mit dem erweiterten Zuordnungs-Editor zu erstellen:

1. Navigieren Sie in der Assets-Benutzeroberfläche zu der Zuordnungsdatei, die Sie bearbeiten möchten.

   >[!NOTE]
   >
   > Stellen Sie sicher, dass Sie den Asset-Auswahlmodus nicht aktiviert haben.

1. Um eine exklusive Sperre für die Zuordnungsdatei zu erhalten, wählen Sie die Zuordnungsdatei aus und klicken Sie auf **Auschecken**.

   >[!NOTE]
   >
   > Sobald Sie eine exklusive Sperre für eine Zuordnungsdatei haben, können andere Benutzer die Zuordnung nicht mehr bearbeiten. Sie wären jedoch in der Lage, an den Themen innerhalb der Zuordnungsdatei zu arbeiten. Wenn Ihr Admin Ihren Web-Editor so konfiguriert hat, dass Dateien vor der Bearbeitung ausgecheckt werden, können Sie eine Datei erst bearbeiten, nachdem Sie sie ausgecheckt haben. Ebenso werden Sie, falls konfiguriert, aufgefordert, alle ausgecheckten Dateien einzuchecken, bevor Sie sie schließen

1. Klicken Sie bei ausgewählter Zuordnungsdatei auf **Themen bearbeiten**.

   ![](images/edit-map-main-menu.png){width="800" align="left"}

   Sie können auch die Option **Themen bearbeiten** aus dem Aktionsmenü in der Zuordnungsdatei auswählen:

   ![](images/edit-map-action-menu.png){width="800" align="left"}

   Die Zuordnungsdatei wird im Web-Editor geöffnet und kann dort bearbeitet werden.

1. Klicken Sie auf das Symbol **Bearbeiten**.

   ![](images/edit-map-icon.png){width="550" align="left"}

   Die Zuordnung wird in der Benutzeroberfläche des erweiterten Zuordnungs-Editors geöffnet. If you have opened a new map file, then only the title of the map is shown in the editor.

   ![](images/new-map-file-in-editor.png){width="800" align="left"}

   - **A** - \(*Main toolbar*\): This is similar to the Web Editor&#39;s main toolbar. See [Main toolbar](web-editor-features.md#id2051EA0G05Z) in the Web Editor for more details.

   - **B** - \(*Secondary toolbar*\) This is the Secondary toolbar that allows you to work with map files. For more information about the functionalities available through Secondary toolbar, see [Features available in the Advanced Map Editor&#39;s toolbar](#id205DEC0005Z).

   - **C** - \(*Map views*\): Allows you to switch the Map Editor between the Layout, Author, Source and Preview. The **Layout** view allows you to organize the topics in a DITA map. This gives the tree or hierarchical view of the map. The **Author** view allows you to edit the topics in the Map Editor. This also gives the WYSIWYG view of the map file. The **Source** view allows you to work with the underlying XML of the map file. The Preview gives you a consolidated view of all topic and sub-maps within the map file. The **Close** link closes the map file.

   - **D** - \(*Left Panel*\): Gives access to the left panel which gives you access to the Favorites, Repository, Map, Outline and other features. Sie können sie erweitern oder reduzieren, indem Sie auf das Symbol Seitenleiste erweitern \(![](images/sidebar-expand-icon.svg)\) klicken. For more details about the features available in the left panel, see [Left panel](web-editor-features.md#id2051EA0M0HS) in the Web Editor.

   - **E** - \(*Middle Area*\): Map content editing area.

   - **F** - \(*Right Panel*\): Gives access to the Properties panel. You can see the content properties and the map properties of the selected topic or map. For more details about the functionalities available in this panel, see [Right panel](web-editor-features.md#id2051EB003YK) in the Web Editor.

1. In the Left Panel, switch to the **Repository View**.

1. In the AEM repository, navigate to the folder that contains the topics or sub-maps that you want to add.

1. Select the topic or map file in the **Repository View** and drag-and-drop it into the \(middle\) map content editing area.

   The topic is added in the map.

   ![map editor add topic](images/map-editor-add-topic.png){width="800" align="left"}

1. To add subsequent topics or a sub-map, drag-and-drop the topic or sub-map to the required location in the map.

   Consider the following points while building your map file:

   - The file is added at a location where the horizontal bar appears in the map editing area. In the following screenshot, the *Overview* topic will get added in between the *General Description* and *Launch and Landing Site* topics.

     ![](images/horizontal-line-in-adv-map-editor.png){width="350" align="left"}

   - To replace a topic, place the topic on top, left, or right of the topic that you want to replace. A Vertical bar to the left or right of a topic indicates that it will get replaced with the topic being dropped on it.

     ![](images/vertical-bar-left-right.png){width="550" align="left"}

     However, before replacing a topic, you get a confirmation prompt. The topic is replaced only after you give the confirmation.

     ![](images/replace-topic-confirm.png){width="300" align="left"}

   - If you add a sub-map to your DITA map, the sub-map is shown as a link in the DITA map. To view all the topics of the sub-map, Crtl+Click the sub-map link. The content of the sub-map are shown in a new tab. Similarly, to open a topic from the DITA map, Crtl+Click the topic link and it opens up in the new tab.

   - You can use shortcut keys CTRL+Z and CTRL+Y or their respective icons in the toolbar to undo or redo any change in the map.

   - To change the position of a topic, select the topic \(by clicking on the topic icon\), then drag-and-drop it at the desired location in the map file. Ensure that the horizontal bar is visible at the location where you want to place the topic. In the following screenshot, the topic *Launch and Landing Site* is being moved after the *Overview* topic.

     ![](images/move-topic-adv-map-editor.png){width="350" align="left"}

   - To check the properties of your map file, right-click anywhere in the map editing area and choose **Properties** from the context menu. Based on your AEM version, you could see properties like metadata, schedule \(de\)activation, references, document state and more.

1. Klicken Sie auf **Speichern**.


## Features available in the Advanced Map Editor&#39;s toolbar {#id205DEC0005Z}

The toolbar in the Advanced Map Editor is similar to the topic Web Editor. The basic operations like toggling the left panel, saving map, creating a new version of map, undo/redo last operation, and delete the selected elements are common in both editors. For detail about how these operations work, see [Know the Web Editor features](web-editor-features.md#) section.

The following map-specific operations are also available on the toolbar in the Layout and Author views:

## Layout view {#id205DEC0005Z_layout_view}

When you open a map for editing it opens the Layout view of the Map Editor.The Layout view displays the map hierarchy in a tree view and allows you to organize the topics in a map.

>[!NOTE]
>
> In der Layout-Ansicht werden nur die Verweise angezeigt, die in einer Zuordnung vorhanden sind. Wenn Referenzen beschädigt sind, wird links neben der Referenz ein kleines Kreuz-Symbol angezeigt

In der Layout-Ansicht können Sie die folgenden Aufgaben ausführen:

**Themenreferenz einfügen** - ![](images/insert-topic-reference.png)

Zeigt den Dialog für die Themensuche an. Navigieren Sie zu der Themen-/Zuordnungsdatei, die Sie einfügen möchten, und klicken Sie auf Auswählen , um sie der Zuordnung hinzuzufügen.
![](images/insert-topic-reference-dialog.png){width="800" align="left"}


**Themengruppe einfügen** - ![](images/insert-topic-group.png)

Fügen Sie das `topicgroup` ein. Weitere Informationen zur Gruppierung von Themen finden Sie in der [Themengruppe](https://docs.oasis-open.org/dita/v1.0/langspec/topicgroup.html) Dokumentation in OASIS DITA Language Specification.

**Schlüsseldefinition einfügen** - ![](images/Key_icon.svg)

Zeigt das Dialogfeld Keydef einfügen an. Verwenden Sie dieses Dialogfeld, um eine beliebige Schlüsseldefinition zu definieren, die Sie in der Zuordnung verwenden möchten.

![](images/insert-key-definition-dialog.png){width="300" align="left"}

**Einfügen vor/Einfügen nach** - ![](images/insert_element_before_icon.svg)/![](images/insert_element_after_icon.svg)

Zeigt das Dialogfeld Element einfügen an. Wählen Sie das Element aus, das Sie in die Zuordnung einfügen möchten. Je nach Vorgang wird das neue Element vor oder nach dem aktuellen Element in der Zuordnung eingefügt.

**Vordere Materie einfügen** - ![](images/frontmatter.svg)

Dieses Symbol wird angezeigt, wenn Sie eine Bookmap zur Bearbeitung öffnen. Sie können Komponenten wie ein Inhaltsverzeichnis, einen Index und eine Liste von Tabellen am Anfang des Buches einfügen.

**Einfügen der Materie** - ![](images/backmatter.svg)

Dieses Symbol wird angezeigt, wenn Sie eine Bookmap zur Bearbeitung öffnen. Sie können Komponenten für ein Ende des Buches wie einen Index, ein Glossar und eine Liste von Figuren einfügen.

**Ausgewähltes Element nach links/rechts verschieben** - ![](images/left-arrow-icon.png)/![](images/right-arrow-icon.png)

Klicken Sie auf den Pfeil nach links, um das Thema in der Hierarchie nach links zu verschieben. Dadurch wird das jeweilige Thema in der Hierarchie wesentlich um eine Ebene nach oben gefördert. For example, clicking the left arrow while a child topic is selected make it the sibling of the topic above it. Similarly, if you click the right arrow, the topic is pushed towards the right side making it the child of the topic above it.

**Move the Selected Item Up/Down![](images/arrowup.svg)** - / ![](images/arrowdown.svg)

Click the up or down arrow icons&#39; to move the topic up or down in the hierarchy.

>[!NOTE]
>
> You can also drag-and-drop the references to move them in a map.

**Lock/Unlock** - ![](images/LockClosed_icon.svg) / ![](images/LockOpen_icon.svg)

Gets a lock on the map file and release the lock. If you have unsaved changes in your map file, then at the time of releasing the lock, you are prompted to save the map file. The changes are saved in the current version of the map file.

**Merge** - ![](images/merge-icon.svg)

For more details about merging content from a different version of the same or a different file, see [Merge](web-editor-features.md#id205DF04E0HS) in the Web Editor.

**Versionsverlauf** - ![](images/version-history-web-editor-ico.svg)

Check the available versions and labels on your active topic, and revert to any version from theeditor itself.

**Version Label** - ![](images/version-label-icon.svg)

Displays the version label management dialog. Select a version from the dropdown list. Choose the label you want to apply to the selected version and click **Add Label** to add it.

**View Options** - ![](images/view-options.svg)

Displays a dropdown which gives you the option to Show Line Numbers, Show Check box, and Show FileName.

- **Show Line Numbers**

Shows or hides the line number for each topic. The line numbers are shown depending on the level in the hierarchy.

- **Show Check Box**

Shows or hides a checkbox for each topic. You can use the checkbox to select the topic\(s\) and perform various tasks using the Options menu. Weitere Informationen finden Sie im Menü [Optionen](#id228ID8006H8).

- **Dateinamen anzeigen**

Zeigt den Dateinamen der Titel der Themen an.

>[!NOTE]
>
> Wenn Sie den Mauszeiger über den Titel eines Themas bewegen, wird der Dateipfad angezeigt.


**Themen basierend auf bedingten Filtern anzeigen** Wenn Sie Bedingungen auf ein Thema angewendet haben, wird rechts neben dem Thema ein Filtersymbol angezeigt. Wenn Sie den Mauszeiger über ein Filtersymbol bewegen, werden die angewendete Bedingung und ihr Attributwert angezeigt.

**Menü „Optionen“ in der Layout-Ansicht**

Neben der Organisation von Themen in der Zuordnungsdatei können Sie auch die folgenden Aktionen über das Menü Optionen ausführen, das für ein Element in der Layout-Ansicht verfügbar ist:

![](images/map-editor-options-menu.png){width="650" align="left"}

- **Hinzufügen**: Im Zuordnungs-Editor können Sie ein neues Thema oder eine leere Referenz hinzufügen:
   - **Leere Referenz**: Mit dieser Option können Sie eine leere Referenz in Ihre DITA-Zuordnung einfügen. Sie können später auf den eingefügten leeren Verweis doppelklicken und die Themendetails hinzufügen. Weitere Informationen finden Sie unter [Thema erstellen](web-editor-features.md#id228ICI0105U) im Web-Editor.
   - **Neues Thema**: Wenn Sie im Menü ein neues Thema erstellen, wird das Dialogfeld Neues Thema erstellen angezeigt. Geben Sie im Dialogfeld Neues Thema erstellen die erforderlichen Details ein und klicken Sie auf Erstellen . Weitere Informationen finden Sie unter [Thema erstellen](web-editor-features.md#id228ICI0105U) im Web-Editor.
- **Verschieben**: Sie können ein Thema in der Hierarchie nach oben/unten/rechts/links verschieben.Sie können auch ein Thema oder eine Karte aus dem Repository-Bereich auf die im Karten-Editor geöffnete Karte ziehen und dort ablegen.
- **Rückgängig**: Macht den letzten Vorgang in der Layout-Ansicht rückgängig.
- **Wiederholen**: Wiederholt den letzten Vorgang in der Layout-Ansicht.
- **Kopieren**: Kopiert den ausgewählten Verweis aus der Zuordnungsdatei.

  >[!NOTE]
  >
  > Sie können die Kontrollkästchen anzeigen und aktivieren, um mehrere Verweise zu kopieren.

- **Einfügen**: Einfügen der kopierten Verweise an der aktuellen Position in der Hierarchie.
- **Löschen**: Löscht die ausgewählten Verweise aus der Zuordnungsdatei.

  >[!NOTE]
  >
  > Sie können mehrere Verweise anzeigen und dann die Kontrollkästchen aktivieren, um sie zu löschen.


## Rechtes Bedienfeld im Karten-Editor

Im rechten Bedienfeld werden die Inhaltseigenschaften und die Zuordnungseigenschaften in der Layout-Ansicht des Zuordnungs-Editors angezeigt.

**Inhaltseigenschaften**

Das Bedienfeld Inhaltseigenschaften enthält Informationen zum Typ des aktuell in der Zuordnung ausgewählten Themas, zur zugehörigen Link-URL und zu den zugehörigen Attributen. Weitere Informationen finden Sie unter [Inhaltseigenschaften](web-editor-features.md#id228IDB00HMM) im Web-Editor.

- **Andere Attribute** Wenn Ihr Administrator ein Profil für Attribute erstellt hat, erhalten Sie diese Attribute zusammen mit den konfigurierten Werten. Im Bedienfeld Inhaltseigenschaften können Sie diese Attribute auswählen und sie relevanten Inhalten in Ihrem Thema zuweisen. Sie können auch Attribute zuweisen, die von Ihrem Administrator unter der Registerkarte **Attribute anzeigen** in den Editor-Einstellungen konfiguriert wurden. Die für ein Element definierten Attribute werden im Layout- und Gliederungsansicht angezeigt. Dies hilft Ihnen, einen kurzen Blick auf alle Themen in einer Zuordnung zu werfen, für die ein bestimmtes Attribut definiert ist. Beispielsweise alle Themen, bei denen das Plattformattribut als &quot;Android&quot; definiert ist.

  ![Layout-Ansicht](images/layout-inline-attributes.png){width="650" align="left"}


  Weitere Informationen finden Sie unter *Attribute anzeigen* im Abschnitt *Editor-Einstellungen* -Funktionsbeschreibung [Linkes Bedienfeld](web-editor-features.md#id2051EA0M0HS).

- **Metadaten** Mithilfe der Metadaten können Sie die Metadateninformationen festlegen. Sie können den Navigationstitel, den Link-Text, die Kurzbeschreibung und die Keywords definieren.

Weitere Informationen zu den Standardattributen und Metadaten für Themen finden Sie in der Dokumentation [topicref](https://docs.oasis-open.org/dita/v1.2/os/spec/langref/topicref.html) in der OASIS DITA Language Specification.

**Eigenschaften zuordnen**

Zeigt das Dialogfeld Zuordnungseigenschaften an, in dem Sie die Attribute und Metadateninformationen für die Zuordnung festlegen können.

## Autorenansicht {#id205DEC0005Z_author_view}

Die **Autor**-Ansicht ermöglicht es Ihnen, Ihre DITA-Karte im Web-Editor zu bearbeiten. Hier wird die WYSIWYG-Ansicht des Karten-Editors angezeigt. Einige der in der Autorenansicht angezeigten Symbole sind mit der Layout-Ansicht identisch. Weitere Informationen finden Sie unter [Layout-Ansicht](#id205DEC0005Z_layout_view). Darüber hinaus können Sie die folgenden Symbole anzeigen und die zugehörigen Aufgaben von der Autorenansicht aus ausführen:

**Einfügen vor/Einfügen nach** - ![](images/insert_element_before_icon.svg)/![](images/insert_element_after_icon.svg)

Zeigt das Dialogfeld Element einfügen an. Wählen Sie das Element aus, das Sie in die Zuordnung einfügen möchten. Je nach Vorgang wird das neue Element vor oder nach dem aktuellen Element in der Zuordnung eingefügt.

**Element einfügen** - ![](images/Add_icon.svg)

Zeigt das Dialogfeld Element einfügen an. Wählen Sie das Element aus, das Sie einfügen möchten. Sie können die Tastatur verwenden, um durch die Liste der Elemente zu scrollen, und die Eingabetaste drücken, um das gewünschte Element einzufügen. Alternativ können Sie direkt auf das Element klicken, um es in die Karte einzufügen.

**Beziehungstabelle einfügen** - ![](images/relationship_table_icon.svg)

Fügt eine Beziehungstabelle in die Zuordnung ein. Da das Konzept der Arbeit mit der Beziehungstabelle identisch ist, wie im Abschnitt Grundlegender Zuordnungs-Editor erläutert, finden [&#x200B; unter „Arbeiten mit Beziehungstabellen im &#x200B;](map-editor-basic-map-editor.md#id1944B0I0COB) Zuordnungs-Editor“ weitere Details.

**Wiederverwendbaren Inhalt einfügen** - ![](images/content-reuse-icon.png)

Zeigt das Dialogfeld Inhalt wiederverwenden an. Verwenden Sie dieses Dialogfeld, um den Inhalt, den Sie wiederverwenden möchten, in Ihre Karte einzufügen.

**Navigationstitelattribut aktualisieren** - ![](images/navtitle-refresh-icon.svg)

Synchronisiert das `title` einer referenzierten Datei in einer Zuordnung mit dem in ihrem `@navtitle` angegebenen Wert. Sie können einer Zuordnung verschiedene Arten von Referenzdateien hinzufügen, z. B. Themen-, Referenz-, Aufgaben-, \(Unter\)-Zuordnungen usw. Die meisten dieser Dateien unterstützen das `@navtitle`. Wenn eine Datei das Attribut `@navtitle` enthält, wird das Attribut `@navtitle` für dieselbe Datei in der Zuordnung aktualisiert. Falls das `@navtitle` nicht vorhanden ist, wird das `@navtitle`-Attribut zu dieser Referenzdatei hinzugefügt und seine `title` wird ebenfalls aktualisiert, um die `@navtitle` anzuzeigen.

>[!NOTE]
>
> Ihr Administrator kann das automatische Hinzufügen `@navtitle` Attributs zu jeder Referenzdatei konfigurieren, die Sie einer Zuordnung hinzufügen. Weitere Informationen zum Konfigurieren des automatischen Hinzufügens `@navtitle` Attributs finden Sie unter *@navtitle Attribut standardmäßig einschließen* unter Installieren und Konfigurieren von Adobe Experience Manager Guides as a Cloud Service.

Klicken Sie auf das Symbol Navigationstitelattribut aktualisieren , um die Werte des `title` und des `@navtitle` zu synchronisieren.

**Tag-Ansicht ein/aus** - ![](images/Label_icon.svg)

Blendet die XML-Tags ein oder aus. Die Tags dienen als visuelle Hinweise auf die Begrenzung eines Elements. Wenn Sie in diesem Modus einen Topic/Map-Verweis einfügen möchten, ziehen Sie die gewünschte Datei per Drag-and-Drop vor oder nach dem Tag. Die horizontale Leiste wird im Tag-Ansichtsmodus nicht angezeigt.

**Änderungen verfolgen/deaktivieren** - ![](images/track-change-icon.svg)

Sie können alle Aktualisierungen in der Zuordnungsdatei verfolgen, indem Sie den Modus Änderungen verfolgen aktivieren. Nach der Aktivierung der Tracking-Änderungen werden alle Einfügungen und Löschungen im Dokument erfasst. Weitere Informationen finden Sie unter &quot;[&#x200B; aktivieren/deaktivieren](web-editor-features.md#id205DF0203Y4) im Web-Editor.

**Prüfungsaufgabe erstellen** - ![](images/create-review-task-icon.svg)

Sie können eine Prüfungsaufgabe des aktuellen Themas oder der Zuordnungsdatei direkt im Web-Editor erstellen. Öffnen Sie die Datei, für die Sie die Prüfungsaufgabe erstellen möchten, und klicken Sie auf Prüfungsaufgabe erstellen , um den Erstellungsprozess der Überprüfung zu starten. Befolgen Sie die Anweisungen unter [Themen oder Karten überprüfen](review.md#) für weitere Details.

## Themen über DITA-Map bearbeiten {#id17ACJ0F0FHS}

Das Bearbeiten eines einzelnen Themas gibt dem Autor nicht den vollständigen Kontext. Ein Autor hätte keine Informationen darüber, wo ein Thema in einer DITA-Karte platziert ist. Ohne diese kontextuellen Informationen wird es für Autoren ein wenig schwierig, Inhalte zu erstellen.

Mit AEM Guides können Autorinnen und Autoren eine DITA-Zuordnung im Web-Editor öffnen und die Platzierung von Themen innerhalb der Zuordnung sehen. Dies hilft Autoren zu wissen, wo genau das Thema in der Karte platziert ist, und relevantere Inhalte zu erstellen. Wenn mehrere Autoren an einem Projekt arbeiten, können sie außerdem wissen, welche Themen in der Karte verfügbar sind, und Inhalte bei Bedarf wiederverwenden.

Um Themen über eine DITA-Zuordnung zu bearbeiten, führen Sie die folgenden Schritte aus:

1. Navigieren Sie in der Assets-Benutzeroberfläche zu der DITA-Karte, die die Themen enthält, die Sie bearbeiten möchten.
1. Klicken Sie auf die DITA-Map, um sie in der DITA-Map-Konsole zu öffnen.
1. Wählen Sie die **Themen** aus, um eine Liste der in der DITA-Karte verfügbaren Themen anzuzeigen.

   >[!TIP]
   >
   > Auf der Registerkarte Themen haben Sie die Möglichkeit, die Zuordnungsdatei mit den abhängigen Elementen herunterzuladen. Weitere Informationen finden Sie unter [Exportieren einer DITA-Zuordnungsdatei](authoring-download-assets.md#id218UBA00IXA).

1. Klicken Sie in der Hauptsymbolleiste auf **Themen bearbeiten**.

   Die DITA-Karte wird im Web-Editor geöffnet.

   >[!NOTE]
   >
   > Sie können auch die DITA-Zuordnungsdatei in der Assets-Benutzeroberfläche auswählen und auf **Themen bearbeiten** in der Hauptsymbolleiste klicken, um den Web-Editor zu starten.

   ![](images/web-editor-map-view_cs.png){width="350" align="left"}

1. \(*Optional*\) Sie können auch ein Thema aus der Karte auswählen und die Datei vor der Bearbeitung auschecken. Um Datei(en) auszuchecken, wählen Sie eine oder mehrere Dateien im linken Bereich aus und klicken Sie auf **Auschecken**. Sie können die Sperre für eine Datei auch aufheben, indem Sie die ausgecheckte Datei auswählen und auf das Symbol **Auschecken abbrechen und Entsperren** in der Kartenansicht klicken.

   >[!IMPORTANT]
   >
   > Wenn Ihr Administrator die Option **Bearbeitung ohne Auschecken deaktivieren** konfiguriert hat, müssen Sie die Datei vor der Bearbeitung auschecken. Wenn Sie die Datei nicht auschecken, wird das Dokument im Editor im schreibgeschützten Modus geöffnet.

   Im folgenden Screenshot sind die Symbole für Auschecken und Sperren \(A\), Auschecken abbrechen und Entsperren \(B\), Als neue Version speichern und Entsperren \(C\), Bearbeiten \(D\), Vorschau \(E\), verschiedene Symbole mit verschiedenen DITA-Dateitypen \(F\) und Dateien, die ausgecheckt sind \(G\), hervorgehoben.

   ![](images/file-checkout-map-editor.png){width="550" align="left"}

1. Klicken Sie auf einen Themenlink, um ihn im Web-Editor zur Bearbeitung zu öffnen.

   Sie können mehrere Themen im Editor öffnen, wobei jedes Thema auf einer neuen Registerkarte im Editor geöffnet wird. Selbst wenn Ihre DITA-Karte Unter-Maps enthält, werden Themen aus den Unter-Maps ebenfalls auf einer neuen Registerkarte zur Bearbeitung geöffnet. Wenn Sie die Themen unter einer Unterkarte anzeigen möchten, können Sie auf die Unterkarte klicken und sie erweitern.

   ![](images/web-editor-multiple-topics.png){width="800" align="left"}

   Wenn Sie auf eine Zuordnungsdatei klicken, wird die Zuordnung in einer neuen Registerkarte des Webbrowsers geöffnet.

1. Nachdem Sie die Bearbeitung der Themen abgeschlossen haben, können Sie Folgendes tun:

   - Sie können sie einzeln speichern. Wenn Sie auf **Ohne Speichern schließen** klicken, wird ein Dialogfeld angezeigt, in dem Sie aufgefordert werden, die nicht gespeicherten Themen zu speichern:

     ![](images/save-multiple-topics.PNG){width="550" align="left"}

     Sie können alle ausgewählten Themen speichern oder die Auswahl der Themen aufheben, die Sie nicht speichern möchten.

   - Sie können das Thema mit der Schaltfläche **Als neue Version speichern und entsperren** einchecken. Wenn Sie eine Version des Themas speichern, wird eine neue Version erstellt und die Sperre wird ebenfalls aufgehoben.

     Es wird empfohlen, Ihre Änderungen zu speichern, bevor Sie die Dateien einchecken.  Beim Speichern der Änderungen wird die XML-Datei validiert.

   - Sie können auch mehrere Themen mithilfe der Schaltfläche **Als neue Version speichern und entsperren** auswählen und einchecken. Wenn Sie eine Version der Themen speichern, wird für jedes Thema eine neue Version erstellt und die Sperre wird ebenfalls aufgehoben. Sie können den Fortschritt des Eincheckens der Themen auch im Dialogfeld **Als neue Version speichern und entsperren** anzeigen. Beim Einchecken der Dateien wird eine Erfolgsmeldung angezeigt.

   - Wenn Ihr Administrator die Option zum Einchecken von Dateien beim Schließen aktiviert hat, wird eine Aufforderung zum Speichern von Dateien angezeigt, sobald die ausgecheckten Dateien geschlossen werden. Wenn diese Option aktiviert ist, wird beim Schließen des Editors mit geänderten Dateien die Liste der ausgecheckten Dateien angezeigt, die gespeichert werden müssen. Die ausgecheckten Dateien werden mit einem Sperrsymbol angezeigt:

     ![](images/save-on-close.PNG){width="550" align="left"}

      - Durch Klicken auf **Schließen ohne Speichern** werden die Dateien geschlossen, ohne dass Änderungen gespeichert werden.

      - Durch Klicken auf **Speichern** werden die Änderungen gespeichert, die Dateien werden jedoch nicht eingecheckt.

      - Wenn Sie die Option **Dateien überprüfen** auswählen und dann auf die Schaltfläche **Speichern** klicken, werden die Dateien eingecheckt (erstellt eine weitere Version) und die Dateien werden ebenfalls gespeichert.


## Vorschau einer Karte

Um die Position der einzelnen Themendateien innerhalb einer Zuordnung anzeigen zu können, ist es wünschenswert, den Zuordnungsinhalt in einem aufeinander folgenden Fluss zu sehen. Mit der Funktion „Zuordnungsvorschau“ können Sie den gesamten Inhalt der Zuordnungsdatei mit einem Klick anzeigen. Sie müssen keine Ausgabe der Zuordnungsdatei generieren, um zu sehen, wie die gesamte Zuordnung nach der Veröffentlichung aussieht. Sie können einfach auf die Vorschau der Karte zugreifen und alle Themen und Unterkarten werden in Form eines Buches gerendert.

Sie können auf die Vorschau einer Karte zugreifen über:

- **Benutzeroberfläche von Assets**: Navigieren Sie in der Benutzeroberfläche von Assets zum Speicherort der Zuordnung, wählen Sie die Zuordnungsdatei aus und wählen Sie **Vorschau der Zuordnung** in der Symbolleiste aus. Die Vorschau der Karte wird auf einer neuen Registerkarte angezeigt. Sie können den Inhalt aller Themen im Vorschaumodus anzeigen. In dieser Ansicht können Sie kein Thema bearbeiten.

  >[!NOTE]
  >
  > Wenn die *Vorschau der Karte* Option in der Hauptsymbolleiste nicht sichtbar ist, wurde sie möglicherweise unter das Symbolleistenmenü **Mehr** verschoben.

- **Erweiterter Karten-Editor**: Klicken Sie im erweiterten Karten-Editor auf das Vorschausymbol, um die Vorschau der aktuellen Karte anzuzeigen.

  ![](images/map-preview-icon.png){width="350" align="left"}

  Im Vorschaumodus können Sie die folgenden zusätzlichen Aufgaben ausführen:

   - Klicken Sie mit der rechten Maustaste auf ein Thema und wählen Sie **Bearbeiten**, um das Thema zur Bearbeitung in einer neuen Registerkarte zu öffnen.

     >[!NOTE]
     >
     > Wenn Sie keine Bearbeitungsrechte haben, wird das Thema im schreibgeschützten Modus geöffnet.

   - Springen Sie zum gewünschten Thema, indem Sie auf den Thementitel in der Zuordnungsstruktur (im linken Bereich) klicken.

   - Das aktuelle Thema in der Kartenvorschau ist auch in der Kartenstruktur hervorgehoben.


**Übergeordnetes Thema:** [Arbeiten mit dem Zuordnungs-Editor](map-editor.md)
