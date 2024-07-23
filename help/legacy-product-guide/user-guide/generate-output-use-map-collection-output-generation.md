---
title: Verwenden der Kartensammlung für die Ausgabegenerierung
description: Erfahren Sie, wie Sie eine Zuordnungssammlung erstellen und löschen und eine DITA-Zuordnung hinzufügen oder löschen. Konfigurieren, Generieren und Abbrechen einer Ausgabegenerierungsaufgabe aus einer Zuordnungssammlung in AEM Guides.
feature: Publishing
role: User
source-git-commit: 76c731c6a0e496b5b1237b9b9fb84adda8fa8a92
workflow-type: tm+mt
source-wordcount: '1212'
ht-degree: 0%

---

# Verwenden der Kartensammlung für die Ausgabegenerierung {#id1723F20G0HS}

In jeder Organisation kann ein Produkt über mehrere Arten von Dokumentation verfügen. Als Publishing-Spezialist möchten Sie steuern, welche Ausgabe Sie für welches Dokument generieren möchten. Außerdem sollte es eine Möglichkeit geben, mehrere Dokumente mit einem einzigen Klick im Batch-Modus zu veröffentlichen.

AEM Guides bietet Ihnen die Möglichkeit, Ihre Inhalte für die Veröffentlichung mithilfe eines Dashboards namens Kartensammlung zu organisieren. Mit einer Kartensammlung können Sie alle verschiedenen Arten von Dokumenten in einer Einheit zusammenführen. Sie können festlegen, welche Art von Ausgabe Sie für jedes Dokument in Ihrer Map Collection generieren möchten. Darüber hinaus können Sie die Ausgabe generieren und den Fortschritt der Ausgabenerstellung im Publishing-Dashboard anzeigen.

Mit der Sammlung &quot;Karte&quot;können Sie anzeigen, ob sich eine Karte von der letzten veröffentlichten Ausgabe ändert. Sie können die Details auf der Registerkarte Karten und Vorgaben Ihrer Map-Sammlung anzeigen und die Ausgabe dann bei Bedarf erneut veröffentlichen. Weitere Informationen finden Sie unter Hinzufügen einer Zuordnung zu einer Map-Sammlung.

## Erstellen einer Zuordnungssammlung und Hinzufügen von DITA-Maps

So erstellen Sie eine Map Collection und fügen der Sammlung DITA-Maps hinzu:

1. Klicken Sie auf der Assets-Benutzeroberfläche auf **Sammlungen zuordnen**.

   Wenn der Link Sammlungen zuordnen nicht verfügbar ist, wählen Sie in der linken Leiste die Option **Navigation** und klicken Sie dann auf **Sammlungen zuordnen**.

   ![](images/access-map-collection-left-rail.png){width="350" align="left"}

1. Geben Sie einen Titel für Ihre Zuordnungssammlung ein.
1. Klicken Sie auf **Erstellen**.

   Bei der Erstellung der Zuordnungssammlung wird eine Erfolgsmeldung angezeigt.

1. Klicken Sie in der Erfolgsmeldung auf **Schließen** .

   Die neu erstellte Zuordnungsdatei wird auf der Seite Sammlungen zuordnen angezeigt.

1. Klicken Sie auf das graue Feld in der Kachel der Sammlung, die Sie bearbeiten möchten.
1. Klicken Sie auf **Bearbeiten** und dann auf **Karten hinzufügen**.
1. Suchen und fügen Sie die DITA-Maps hinzu, die Sie der Map-Sammlung hinzufügen möchten.

   Standardmäßig werden alle Vorgaben und Gebietsschemata, die mit der Zuordnung verknüpft sind, automatisch hinzugefügt.

1. Wählen Sie die gewünschte Ausgabe aus, indem Sie die gleitende Schaltfläche ein- oder ausschalten.
1. Klicken Sie auf **Fertig**.

   Die DITA-Zuordnungsdateien werden Ihrer Zuordnungssammlung hinzugefügt.

   ![ Sammlungs-Dashboard für die Zuordnung](./images/map-collection-dashboard.png){width="800" align="left"}

Die folgenden Filteroptionen und Zuordnungsdetails werden auf der Sammlungsseite angezeigt:

- **Filter:** Die aktuelle Leiste zeigt die folgenden Filter an:
   - **Geändert**: Sie können &quot;Ja&quot;oder &quot;Nein&quot;auswählen. Wenn Sie &quot;Ja&quot;auswählen, werden nur die modifizierten DITA-Maps in der Tabelle Maps und Vorgaben angezeigt.
   - **Vorgabe**: Wählen Sie eine Vorgabe aus, für die Sie die Zuordnungsdateien herausfiltern möchten. Wenn Sie beispielsweise die Vorgabe *AEM Site* auswählen, werden nur die Karten angezeigt, für die die Ausgabevorgabe *AEM Site* konfiguriert ist.
   - **Sprache**: Sie können einen der verfügbaren Sprachcodes auswählen und nur die ausgewählte Sprache in der Tabelle &quot;Karten und Vorgaben&quot;anzeigen.
- **Karten und Vorgaben**: Die Tabelle &quot;Karten und Vorgaben&quot;enthält Informationen in den folgenden Spalten:
   - **Zuordnung**: Zeigt den Titel der DITA-Map-Datei an.
   - **Dateiname**: Zeigt den Dateinamen der DITA-Zuordnung an.
   - **Sprache**: Zeigt die Sprache der DITA-Zuordnung an.
   - **Vorgabe**: Zeigt den in der Zuordnungsdatei konfigurierten Vorgabetyp an.
   - **Grundlinie**: Zeigt die Grundlinie an, die von der Ausgabevorgabe verwendet wird.  Wenn keine Grundlinie verwendet wird, wird ein Bindestrich &#39;-&#39; angezeigt.
   - **Geändert**: Gibt an, ob die DITA-Zuordnung nach der letzten Veröffentlichung aktualisiert wird. Anhand dieser Informationen können Sie entscheiden, ob Sie die Ausgabe für diese DITA-Zuordnung erneut veröffentlichen möchten oder nicht.
   - **Zuletzt generiert**: Zeigt Datum und Uhrzeit der letzten generierten Ausgabe an.

## Konfigurieren und Generieren der Ausgabe mithilfe einer Map Collection

Um die Ausgabe mithilfe einer Map Collection zu konfigurieren und zu generieren, führen Sie die folgenden Schritte aus:

1. Öffnen Sie die Kartensammlung. Sie können die verschiedenen Ausgabevorgaben wie die AEM Site, PDF (einschließlich nativer PDF), HTML5, EPUB und benutzerdefinierte Vorgaben anzeigen. Sie können auch die von Ihrem Administrator erstellten globalen und Ordnerprofilvorgaben anzeigen.

   Das Symbol &quot;![](images/global-preset-icon.svg)&quot;zeigt eine Vorgabe auf Ordnerprofilebene an.
1. \(Optional\) Führen Sie je nach Anforderung einen der folgenden Schritte aus:
   - Wenden Sie Filter aus der linken Leiste an, um die geänderten Zuordnungen, Ausgabevorgaben oder Sprachen zu filtern.
   - Klicken Sie, falls erforderlich, auf **Bearbeiten** und ändern Sie die gewünschte Ausgabe, indem Sie die gleitende Schaltfläche ein- oder ausschalten.



     >[!NOTE]
     >  
     > Standardmäßig ist jede neue Vorgabe deaktiviert.

1. Sie können die Vorgaben für eine DITA-Zuordnung wie folgt aktivieren:

   - Aktivieren Sie jede einzelne Vorgabe.
   - Aktivieren Sie **Alle Vorgaben** für eine DITA-Zuordnung, um alle Vorgaben in einem Schritt auszuwählen. Diese Option ist standardmäßig deaktiviert.
   - Aktivieren Sie **Ordnerprofilvorgaben** für eine DITA-Zuordnung, um alle Ordnerprofilvorgaben dafür auszuwählen. Diese Option ist standardmäßig deaktiviert.
     ![Bearbeiten einer Zuordnungssammlung in Cloud Services](images/edit-map-collection-cs.png){width="800" align="left"}



1. Führen Sie einen der folgenden Schritte aus:

   - Um die Ausgabe der ausgewählten Maps zu generieren, wählen Sie die Zuordnungsdateien aus und klicken Sie auf **Ausgewählte generieren**.
   - Um die Ausgabe aller DITA-Maps mit den konfigurierten Vorgaben zu generieren, klicken Sie auf **Alle generieren**.

   >[!IMPORTANT]
   >
   > Wenn sich ein Ausgabeerstellungsprozess für eine Vorgabe oder DITA-Zuordnung entweder in der Warteschlange befindet oder in Bearbeitung ist, können Sie keine weitere Ausgabegenerierungsaufgabe für dieselbe Vorgabe oder Zuordnung starten.

## Konfigurieren der Metadateneigenschaften

In der Zuordnungssammlung können Sie die Metadateneigenschaften stapelweise für die DITA-Maps konfigurieren. Wählen Sie **Metadaten konfigurieren** aus, um die Seite **Asset-Metadaten** zu öffnen. Auf der Seite **Asset-Metadaten** werden alle in der Sammlung vorhandenen Karten auf der linken Seite aufgelistet.

![Konfigurieren von Metadaten](images/map-collection-asset-metadata.png){width="800" align="left"}

Führen Sie die folgenden Schritte aus, um die Metadateneigenschaften zu konfigurieren:

1. Sie können die Karten auswählen, für die die Metadaten aktualisiert werden sollen. Standardmäßig sind alle vorhandenen DITA-Maps ausgewählt.

1. Nachdem Sie die DITA-Maps ausgewählt haben, können Sie Eigenschaften wie Metadaten, planmäßige (de)Aktivierung, Verweise, Dokumentstatus und mehr anzeigen.

1. Aktualisieren Sie die Metadateneigenschaften.

1. Klicken Sie oben auf **Speichern und schließen** , um die Aktualisierungen zu speichern.
1. (Optional) Wenn Sie die Tags aktualisieren, können Sie auch im Dropdown-Menü **Speichern und schließen** die Option &quot;Anhängen&quot;auswählen, um die neuen Tags an die vorhandene Liste anzuhängen.
1. Klicken Sie im Dropdown-Menü **Speichern und schließen** auf **Senden** .
Die Metadateneigenschaften werden für die DITA-Maps aktualisiert, die Sie stapelweise aus der Zuordnungssammlung auswählen.

>[!NOTE]
> 
>Für das Dropdown-Menü **Dokumentstatus** können Sie nur die Dokumentstatus auswählen, die für alle ausgewählten DITA-Maps gemeinsam sind. Weitere Informationen finden Sie unter [**Dokumentstatus**](./web-editor-document-states.md).

Die Metadateneigenschaften werden mit den Dateieigenschaften synchronisiert. Nach der Aktualisierung können Sie sie im Web Editor im Bereich **Dateieigenschaften** anzeigen.



## Löschen einer Map-Sammlung oder einer DITA-Zuordnung aus der Map Collection

- Um eine Zuordnungssammlung zu löschen, wählen Sie auf der Seite &quot;Zuordnungssammlung&quot;eine Sammlung aus und klicken Sie auf **Löschen**.
- Um eine DITA-Map aus einer Map-Sammlung zu löschen, öffnen Sie die Map-Sammlung im Bearbeitungsmodus, wählen Sie die DITA-Map-Datei aus und klicken Sie auf **Aus Sammlung entfernen**.

Dadurch werden auch alle mit der DITA-Map verknüpften Vorgaben oder Gebietsschemata aus der Map-Sammlung entfernt.


## Abbrechen einer Ausgabenerstellungsaufgabe aus einer Map Collection

Ähnlich wie beim Abbrechen einer Ausgabegenerierungsaufgabe über die [DITA-Zuordnungskonsole](generate-output-for-a-dita-map.md#id2061H100T5Z) oder das [Publish-Dashboard](generate-output-publish-dashboard.md#) können Sie eine Ausgabegenerierungsaufgabe über eine Zuordnungssammlung abbrechen. Rufen Sie die Registerkarte &quot;Output&quot;einer Map Collection auf, wechseln Sie zur Veröffentlichungsaufgabe, die Sie abbrechen möchten, und klicken Sie auf das Symbol **Vorgang abbrechen** , um die Veröffentlichungsaufgabe abzubrechen.

![](images/cancel-publish-task-map-collection.png){width="800" align="left"}

**Übergeordnetes Thema:**[ Ausgabegenerierung](generate-output.md)
