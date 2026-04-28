---
title: Verwenden von Bedingungsvorgaben
description: Kenntnis der Verwendung von Bedingungsvorgaben in AEM Guides Erfahren Sie, wie Sie in AEM Bedingungsvorgaben erstellen, bearbeiten, kopieren und löschen können.
feature: Publishing
role: User
hide: true
exl-id: 991179c7-186e-4b23-b918-248f596644ec
source-git-commit: a70b3ce942b3e69445ad1d7ba6c8f7542e0ff176
workflow-type: tm+mt
source-wordcount: '1213'
ht-degree: 2%

---

# Verwenden von Bedingungsvorgaben {#id1825FL004PN}

Sie können Attribute in Ihren DITA-Themen definieren und die Bedingungsvorgabe verwenden, um festzulegen, was mit dem Attribut in der endgültigen Ausgabe geschieht. Sie können beispielsweise Attribute als Version 1.0 und Version 2.0 in Ihrem Inhalt hinzufügen und eine Bedingungsvorgabe verwenden, um Version 1.0 für Version 1.0 einzuschließen und Version 2.0 auszuschließen. Ebenso können Sie Ihrem Inhalt Attribute wie Betriebssystem Windows und Betriebssystem Linux hinzufügen und dann den relevanten Inhalt für Ihre endgültige Ausgabe je nach Betriebssystem ein- oder ausschließen.

Sie haben zwei Möglichkeiten, um Bedingungsvorgaben zu erstellen:

* Vom Web-Editor aus: Ermöglicht das Erstellen und Verwalten der Bedingungsvorgaben für eine DITA-Zuordnung über den Web-Editor.
* Vom Zuordnungs-Dashboard aus: Ermöglicht das Erstellen und Verwalten der Bedingungsvorgaben für eine DITA-Zuordnung über das Zuordnungs-Dashboard.


## Bedingungsvorgaben im Web-Editor

Mit Experience Manager Guides können Sie Bedingungsvorgaben über den Web-Editor verwalten und in den Ausgabevorgaben verwenden, um die endgültige Ausgabe zu generieren.
Sie können die Bedingungsvorgaben erstellen und anzeigen, die Attribute anzeigen und die Aktionen für die aktuelle Zuordnung in der Ansicht **Bedingungsvorgaben** im Web-Editor verwalten.

<img src="images//manage-condtions-presets.png" alt= "Bedingungsvorgaben im Web-Editor" width="800" border="1px">



### Erstellen einer Bedingungsvorgabe

Die **Bedingungsvorgaben** enthält detaillierte Informationen zu den Bedingungsvorgaben, wie Attribute, Werte und Aktionen.
Sie können eine Bedingungsvorgabe der Themen erstellen, indem Sie die folgenden Schritte ausführen:

1. Öffnen Sie **Bedienfeld** Repository“ die DITA-Zuordnungsdatei in der Zuordnungsansicht.
1. Wählen Sie die **Verwalten** aus.
1. Wählen **auf** linken Seite „Bedingungsvorgaben“ aus. Die Liste der für die DITA-Zuordnung definierten Bedingungsvorgaben wird angezeigt.
1. Klicken Sie auf das Symbol + neben **Bedingungsvorgaben**, um das Dialogfeld **Neue**&quot; zu öffnen.
1. Geben Sie einen eindeutigen Namen für die Voreinstellung ein.

   >[!NOTE]
   >
   > Eine Fehlermeldung wird angezeigt, wenn das Feld „Name“ leer ist oder Sie ein ungültiges Zeichen oder einen Namen eingeben, der mit einer vorhandenen Bedingungsvorgabe übereinstimmt. Sie können einen Bindestrich &quot;-&quot; oder Unterstrich „_“ als Trennzeichen verwenden.

1. Wählen Sie **Erstellen** aus.
The new condition preset is added to the list.
1. Double-click a condition preset to view the attributes and the actions.
The **Attributes** panel shows all the attributes added to any references present in the map. The right panel shows only the conditions that you have added to the condition presets.
1. Do any of the following to add the attributes:
   * Select one or more attributes to add all the values under them to the condition preset. For example, you can select the `platform` attribute to add all its values.
   * Select one or more attribute values to add them to the condition preset. For example, you can select the `Unix` and `Win` values of the platform attribute
   * Select any attribute and value pair and drag it to the center panel. For example, you can select the `Unix` value of the platform attribute and drag it.
   * **Select all** to add all the attributes and their values to the condition preset.
By default, the action for an attribute is `Include`.

1. Wählen Sie **Hinzufügen**. You can repeat this step to add more attributes. The attributes that you add move from the central to the right panel.
1. Select Remove from the actions bar on the top to remove the selected attributes in the right panel.
1. (Optional) If required, you can override the action applied to the attributes.
Führen Sie einen der folgenden Schritte aus:
   * For any attribute, select one of the following actions from the Action drop-down.
      * Einschließen
      * Ausschließen
      * Passthrough
      * Kennzeichnung
   * Select multiple attribute rows from the right panel and choose an action from the actions bar on the top. For example, you can select Exclude action for the selected attributes.
1. Select **Save** to save the condition preset.

   >[!NOTE]
   >
   > You view a warning if you select another preset or close the preset without saving it.

Once you create a condition preset, it appears under the **Condition Presets** dropdown of the Output presets. Learn more about how to [Publish PDF output](/help/product-guide/web-editor/native-pdf-web-editor.md).

### Umbenennen einer Bedingungsvorgabe

Führen Sie die folgenden Schritte aus, um eine Bedingungsvorgabe umzubenennen:

1. Bewegen Sie den Mauszeiger über eine Bedingungsvorgabe im Bedienfeld **Bedingungsvorgaben**.
1. Wählen Sie **Optionsmenü die Option** Umbenennen **aus, um das Dialogfeld „Bedingungsvorgabe umbenennen** zu öffnen.
1. Bearbeiten Sie den Namen der Bedingungsvorgabe.
1. Klicken Sie auf **Umbenennen**.

### Duplizieren einer Bedingungsvorgabe

Gehen Sie wie folgt vor, um eine Bedingungsvoreinstellung zu duplizieren:

1. Bewegen Sie den Mauszeiger über eine Bedingungsvorgabe im Bedienfeld **Bedingungsvorgaben**.
1. Wählen Sie **Optionsmenü die Option** Duplizieren“ aus, um das Dialogfeld **Bedingungsvorgabe duplizieren** zu öffnen.
   >[!NOTE]
   >
   > Der Standardname der Voreinstellung lautet `<selected condition preset name>_1`. Sie können den Namen Ihren Anforderungen entsprechend ändern.

1. Klicken Sie **Duplizieren**.

### Bedingungsvorgabe löschen

Gehen Sie wie folgt vor, um Bedingungsvorgaben zu löschen:

1. Bewegen Sie den Mauszeiger über eine Bedingungsvorgabe im Bedienfeld **Bedingungsvorgaben**.
1. Wählen Sie **Optionsmenü** Löschen“ aus, um das Dialogfeld **Löschen einer**&quot; zu öffnen.
1. Klicken Sie auf **Löschen**.



## Bedingungsvorgaben im Zuordnungs-Dashboard


### Erstellen einer Bedingungsvorgabe

Führen Sie die folgenden Schritte aus, um eine Bedingungsvoreinstellung zu erstellen:

1. Wählen Sie **Registerkarte** Bedingungsvorgaben“ in der DITA-Zuordnungskonsole aus.
1. Klicken Sie auf **Erstellen**-Schaltfläche.
1. Geben Sie unter „Bedingung“ einen Namen für **Voreinstellung**.
1. Wählen Sie eine der folgenden Standardaktionen aus der **Standardaktion festlegen auf** Dropdown-Liste:

   * Einschließen
   * Ausschließen
   * Passthrough
   * Kennzeichnung
Die Aktion wird als Standardaktion für alle Attribute festgelegt, unabhängig davon, ob sie zur Bedingungsvoreinstellung hinzugefügt werden oder nicht.

   Sie haben beispielsweise 15 Bedingungsattribute in Ihrem Dokument und vier davon in die Bedingungsvorgabe aufgenommen. Wenn Sie **Ausschließen** als Standardaktion auswählen, wird sie auf alle 15 Attribute angewendet.

1. Führen Sie einen der folgenden Schritte aus, um die Attribute hinzuzufügen:
   * Klicken Sie **Hinzufügen**, um der Bedingungsvorgabe ein Attribut hinzuzufügen. Sie können diesen Schritt wiederholen, um weitere Attribute hinzuzufügen.
   * Klicken Sie **Alle hinzufügen**, um alle Attribute zur Bedingungsvorgabe hinzuzufügen.
1. \(Optional\) Bei Bedarf können Sie die Standardaktion überschreiben, die auf die Attribute in Schritt 4 angewendet wurde. Führen Sie einen der folgenden Schritte aus:
   * Wählen Sie mehrere Attribute und eine Aktion aus **Aktion für ausgewählte Bedingungen festlegen auf** und klicken Sie auf **Anwenden**.
   * Wählen Sie eine Aktion für ein Attribut aus der **Aktion** Dropdown-Liste aus.
1. Klicken Sie auf **Speichern**.

### Bearbeiten einer Bedingungsvorgabe

Sie können Änderungen an einer vorhandenen Bedingungsvorgabe vornehmen, um die Aktionen zu ändern, die auf die Attribute in der Bedingungsvorgabe angewendet werden. Führen Sie die folgenden Schritte aus, um eine Bedingungsvorgabe zu bearbeiten:

1. Wählen Sie **Registerkarte** Bedingungsvorgaben“ in der DITA-Zuordnungskonsole aus.
1. Klicken Sie auf **Bearbeiten**-Schaltfläche.
1. Nehmen Sie die erforderlichen Änderungen für alle Attribute in der Bedingungsvorgabe vor.
1. Klicken Sie auf **Speichern**.

### Erstellen einer Kopie einer Bedingungsvorgabe

Sie können eine Kopie einer Bedingungsvorgabe erstellen und sie dann entsprechend Ihren Anforderungen ändern. Führen Sie die folgenden Schritte aus, um eine Kopie einer Bedingungsvorgabe zu erstellen:

1. Wählen Sie **Registerkarte** Bedingungsvorgaben“ in der DITA-Zuordnungskonsole aus.
1. Klicken Sie auf **Duplizieren**-Schaltfläche.

   >[!NOTE]
   >
   > Der Standardname der Voreinstellung lautet `<selected condition preset name>_Duplicate`

   Sie können den Namen entsprechend Ihren Anforderungen ändern.

1. \(Optional\) Nehmen Sie die erforderlichen Änderungen für alle Attribute in der Bedingungsvorgabe vor.
1. Klicken Sie auf **Speichern**.

### Bedingungsvorgabe löschen

Sie können eine oder mehrere Bedingungsvorgaben auf der Registerkarte **Bedingungsvorgabe** der DITA-Zuordnungskonsole löschen. Gehen Sie wie folgt vor, um Bedingungsvorgaben zu löschen:

1. Wählen Sie **Registerkarte** Bedingungsvorgaben“ in der DITA-Zuordnungskonsole aus.
1. Wählen Sie die zu löschende(n) Bedingungsvorgabe(en) aus.
1. Klicken Sie auf **Entfernen**-Schaltfläche.
1. Klicken Sie **Entfernen**, um die Aktion zu bestätigen.

**Übergeordnetes Thema:**&#x200B;[&#x200B; Ausgabegenerierung](generate-output.md)
