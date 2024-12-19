---
title: Verwenden von Bedingungsvorgaben
description: Kenntnis der Verwendung von Bedingungsvorgaben in AEM Guides Erfahren Sie, wie Sie Bedingungsvorgaben in AEM erstellen, bearbeiten, kopieren und löschen können.
feature: Publishing
role: User
exl-id: 991179c7-186e-4b23-b918-248f596644ec
source-git-commit: 86fb9cc382689beb493847cb506c788199a2d3f4
workflow-type: tm+mt
source-wordcount: '1210'
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
Die neue Bedingungsvorgabe wird der Liste hinzugefügt.
1. Doppelklicken Sie auf eine Bedingungsvorgabe, um die Attribute und Aktionen anzuzeigen.
Das Bedienfeld **Attribute** zeigt alle Attribute an, die zu allen in der Zuordnung vorhandenen Verweisen hinzugefügt wurden. Im rechten Bedienfeld werden nur die Bedingungen angezeigt, die Sie den Bedingungsvorgaben hinzugefügt haben.
1. Führen Sie einen der folgenden Schritte aus, um die Attribute hinzuzufügen:
   * Wählen Sie ein oder mehrere Attribute aus, um alle darunter liegenden Werte zur Bedingungsvorgabe hinzuzufügen. Sie können beispielsweise das Attribut `platform` auswählen, um alle zugehörigen Werte hinzuzufügen.
   * Wählen Sie einen oder mehrere Attributwerte aus, um sie zur Bedingungsvorgabe hinzuzufügen. Sie können beispielsweise die `Unix` und `Win` Werte des Platform-Attributs auswählen
   * Wählen Sie ein beliebiges Attribut- und Wertepaar aus und ziehen Sie es in das mittlere Bedienfeld. Sie können beispielsweise den `Unix` des Platform-Attributs auswählen und ziehen.
   * **Alle auswählen** um alle Attribute und deren Werte zur Bedingungsvorgabe hinzuzufügen.
Standardmäßig ist die Aktion für ein Attribut `Include`.

1. Wählen Sie **Hinzufügen**. Sie können diesen Schritt wiederholen, um weitere Attribute hinzuzufügen. Die hinzugefügten Attribute werden aus dem mittleren in den rechten Bereich verschoben.
1. Wählen Sie oben in der Aktionsleiste Entfernen aus, um die ausgewählten Attribute im rechten Bedienfeld zu entfernen.
1. (Optional) Bei Bedarf können Sie die auf die Attribute angewendete Aktion überschreiben.
Führen Sie einen der folgenden Schritte aus:
   * Wählen Sie für ein Attribut eine der folgenden Aktionen aus der Dropdown-Liste Aktion aus.
      * Einschließen
      * Ausschließen
      * Passthrough
      * Kennzeichnung
   * Wählen Sie mehrere Attributzeilen aus dem rechten Bedienfeld und wählen Sie oben in der Aktionsleiste eine Aktion aus. Sie können beispielsweise für die ausgewählten Attribute die Aktion Ausschließen auswählen.
1. Klicken Sie **Speichern**, um die Bedingungsvorgabe zu speichern.

   >[!NOTE]
   >
   > Es wird eine Warnung angezeigt, wenn Sie eine andere Vorgabe auswählen oder die Vorgabe schließen, ohne sie zu speichern.

Nachdem Sie eine Bedingungsvorgabe erstellt haben, wird sie in der Dropdown **Liste &quot;**&quot; der Ausgabevorgaben angezeigt. Erfahren Sie mehr über die [Publish PDF-Ausgabe](/help/product-guide/web-editor/native-pdf-web-editor.md).

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
   * Markierung
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

**Übergeordnetes Thema:**[ Ausgabegenerierung](generate-output.md)
