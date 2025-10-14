---
title: Verwenden von Bedingungsvorgaben
description: Kenntnis der Verwendung von Bedingungsvorgaben in AEM Guides Erfahren Sie, wie Sie in AEM Bedingungsvorgaben erstellen, bearbeiten, kopieren und löschen können.
exl-id: f6865a34-abdd-4d23-b903-0211bebd13b7
feature: Publishing
role: User
source-git-commit: ac83f613d87547fc7f6a18070545e40ad4963616
workflow-type: tm+mt
source-wordcount: '1152'
ht-degree: 2%

---

# Verwenden von Bedingungsvorgaben {#id1825FL004PN}

Sie können Attribute in Ihren DITA-Themen definieren und die Bedingungsvorgabe verwenden, um festzulegen, was mit dem Attribut in der endgültigen Ausgabe geschieht. Sie können beispielsweise Attribute als Version 1.0 und Version 2.0 in Ihrem Inhalt hinzufügen und eine Bedingungsvorgabe verwenden, um Version 1.0 für Version 1.0 einzuschließen und Version 2.0 auszuschließen. Ebenso können Sie Ihrem Inhalt Attribute wie Betriebssystem Windows und Betriebssystem Linux hinzufügen und dann den relevanten Inhalt für Ihre endgültige Ausgabe je nach Betriebssystem ein- oder ausschließen.

Sie haben zwei Möglichkeiten, um Bedingungsvorgaben zu erstellen:

- [In der Zuordnungskonsole](#condition-presets-from-the-map-console)
- [Vom Zuordnungs-Dashboard aus](#condition-presets-from-the-map-dashboard)


## Bedingungsvorgaben über die Zuordnungskonsole

Experience Manager Guides ermöglicht es Ihnen, Bedingungsvorgaben über die Zuordnungskonsole zu erstellen und zu verwalten und sie in den **Ausgabevorgaben** zu verwenden, um die endgültige bedingte Ausgabe zu generieren.

<img src="images/manage-condtions-presets.png" alt= "Bedingungsvorgaben in der Zuordnungs-Konsole" border="1px">

### Erstellen einer Bedingungsvorgabe

Die **Bedingungsvorgaben** enthält detaillierte Informationen zu den Bedingungsvorgaben, wie Attribute, Werte und Aktionen.

Sie können eine Bedingungsvorgabe der Themen erstellen, indem Sie die folgenden Schritte ausführen:

1. [Öffnen Sie die DITA-Zuordnungsdatei in der Zuordnungskonsole](./open-files-map-console.md).
1. Navigieren Sie links zu **Bedingungsvorgaben** . Die Liste der für die DITA-Zuordnung definierten Bedingungsvorgaben wird angezeigt.
1. Klicken Sie auf das Symbol + neben **Bedingungsvorgaben**, um das Dialogfeld **Neue**&quot; zu öffnen.
1. Geben Sie einen eindeutigen Namen für die Voreinstellung ein.

   >[!NOTE]
   >
   > Eine Fehlermeldung wird angezeigt, wenn das Feld „Name“ leer ist oder Sie ein ungültiges Zeichen oder einen Namen eingeben, der mit einer vorhandenen Bedingungsvorgabe übereinstimmt. Sie können einen Bindestrich &quot;-&quot; oder Unterstrich „_“ als Trennzeichen verwenden.

1. Wählen Sie **Erstellen** aus.

   Die neue Bedingungsvorgabe wird der Liste hinzugefügt.
1. Wählen Sie die Bedingungsvorgabe aus, um die Attribute und Aktionen anzuzeigen.

   Das Bedienfeld **Attribute** zeigt alle Attribute an, die zu allen in der Zuordnung vorhandenen Verweisen hinzugefügt wurden. Im rechten Bedienfeld werden nur die Bedingungen angezeigt, die Sie den Bedingungsvorgaben hinzugefügt haben.
1. Führen Sie einen der folgenden Schritte aus, um die Attribute hinzuzufügen:
   - Wählen Sie ein oder mehrere Attribute aus, um alle darunter liegenden Werte zur Bedingungsvorgabe hinzuzufügen. Sie können beispielsweise das Attribut `platform` auswählen, um alle zugehörigen Werte hinzuzufügen.
   - Wählen Sie einen oder mehrere Attributwerte aus, um sie zur Bedingungsvorgabe hinzuzufügen. Sie können beispielsweise die `Unix` und `Win` Werte des Platform-Attributs auswählen
   - Wählen Sie ein beliebiges Attribut- und Wertepaar aus und ziehen Sie es in das mittlere Bedienfeld. Sie können beispielsweise den `Unix` des Platform-Attributs auswählen und ziehen.
   - **Alle auswählen** um alle Attribute und deren Werte zur Bedingungsvorgabe hinzuzufügen. Standardmäßig ist die Aktion für ein Attribut `Include`.

1. Wählen Sie **Hinzufügen**. Sie können diesen Schritt wiederholen, um weitere Attribute hinzuzufügen. Die hinzugefügten Attribute werden aus dem mittleren in den rechten Bereich verschoben.
1. Wählen Sie **Entfernen** oben in der Aktionsleiste aus, um die ausgewählten Attribute im rechten Bedienfeld zu entfernen.
1. (Optional) Bei Bedarf können Sie die auf die Attribute angewendete Aktion überschreiben.

   Führen Sie einen der folgenden Schritte aus:
Wählen Sie für ein Attribut eine der folgenden Aktionen aus der Dropdown-Liste Aktion oder aus der Symbolleiste aus.

   - Einschließen
   - Ausschließen
   - Passthrough
   - Kennzeichnung

   Wählen Sie mehrere Attributzeilen aus dem rechten Bedienfeld und wählen Sie oben in der Aktionsleiste eine Aktion aus. Beispielsweise können Sie für die ausgewählten Attribute **Aktion** Ausschließen“ auswählen.
1. Klicken Sie **Speichern**, um die Bedingungsvorgabe zu speichern.

   >[!NOTE]
   >
   > Es wird eine Warnung angezeigt, wenn Sie eine andere Vorgabe auswählen oder die Vorgabe schließen, ohne sie zu speichern.

Nachdem Sie eine Bedingungsvorgabe erstellt haben, wird sie in der Dropdown **Liste &quot;**&quot; von **Ausgabevorgaben“**. Weitere Informationen zum Veröffentlichen [PDF-Ausgabe](../web-editor/native-pdf-web-editor.md).

### Umbenennen einer Bedingungsvorgabe

Führen Sie die folgenden Schritte aus, um eine Bedingungsvorgabe umzubenennen:

1. Bewegen Sie den Mauszeiger über eine Bedingungsvorgabe im Bedienfeld **Bedingungsvorgaben**.
1. Wählen Sie **Optionsmenü** Umbenennen“ aus, um das Dialogfeld **Bedingungsvorgabe umbenennen** zu öffnen.
1. Bearbeiten Sie den Namen der Bedingungsvorgabe.
1. Wählen Sie **Umbenennen** aus.

### Duplizieren einer Bedingungsvorgabe

Gehen Sie wie folgt vor, um eine Bedingungsvoreinstellung zu duplizieren:

1. Bewegen Sie den Mauszeiger über eine Bedingungsvorgabe im Bedienfeld **Bedingungsvorgaben**.
1. Wählen Sie **Optionsmenü die Option** Duplizieren“ aus, um das Dialogfeld **Bedingungsvorgabe duplizieren** zu öffnen.

   >[!NOTE]
   >
   > Der Standardname der Voreinstellung lautet `<selected condition preset name>_1`. Sie können den Namen Ihren Anforderungen entsprechend ändern.

1. Wählen Sie **Duplizieren** aus.

### Bedingungsvorgabe löschen

Gehen Sie wie folgt vor, um Bedingungsvorgaben zu löschen:

1. Bewegen Sie den Mauszeiger über eine Bedingungsvorgabe im Bedienfeld **Bedingungsvorgaben**.
1. Wählen Sie **Optionsmenü** Löschen“ aus, um das Dialogfeld **Bedingungsvorgabe löschen** zu öffnen.
1. Wählen Sie **Löschen** aus.



## Bedingungsvorgaben im Zuordnungs-Dashboard


### Erstellen einer Bedingungsvorgabe

Führen Sie die folgenden Schritte aus, um eine Bedingungsvoreinstellung zu erstellen:

1. Wählen Sie **Registerkarte** Bedingungsvorgaben“ im DITA-Zuordnungs-Dashboard aus.
1. Wählen Sie **Erstellen** aus.
1. Geben Sie unter „Bedingung“ einen Namen für **Voreinstellung**.
1. Wählen Sie eine der folgenden Standardaktionen aus der **Standardaktion festlegen auf** Dropdown-Liste:

   - Einschließen
   - Ausschließen
   - Passthrough
   - Markierung
Die Aktion wird als Standardaktion für alle Attribute festgelegt, unabhängig davon, ob sie zur Bedingungsvoreinstellung hinzugefügt werden oder nicht.

   Sie haben beispielsweise 15 Bedingungsattribute in Ihrem Dokument und vier davon in die Bedingungsvorgabe aufgenommen. Wenn Sie **Ausschließen** als Standardaktion auswählen, wird sie auf alle 15 Attribute angewendet.

1. Führen Sie einen der folgenden Schritte aus, um die Attribute hinzuzufügen:
   - Wählen Sie **Hinzufügen** aus, um der Bedingungsvorgabe ein Attribut hinzuzufügen. Sie können diesen Schritt wiederholen, um weitere Attribute hinzuzufügen.
   - Wählen Sie **Alle hinzufügen** aus, um alle Attribute zur Bedingungsvorgabe hinzuzufügen.
1. \(Optional\) Bei Bedarf können Sie die Standardaktion überschreiben, die auf die Attribute in Schritt 4 angewendet wurde. Führen Sie einen der folgenden Schritte aus:
   - Wählen Sie mehrere Attribute und eine Aktion aus **Aktion für ausgewählte Bedingungen festlegen auf** und wählen Sie **Anwenden** aus.
   - Wählen Sie eine Aktion für ein Attribut aus der **Aktion** Dropdown-Liste aus.
1. Wählen Sie **Speichern** aus.

### Bearbeiten einer Bedingungsvorgabe

Sie können Änderungen an einer vorhandenen Bedingungsvorgabe vornehmen, um die Aktionen zu ändern, die auf die Attribute in der Bedingungsvorgabe angewendet werden. Führen Sie die folgenden Schritte aus, um eine Bedingungsvorgabe zu bearbeiten:

1. Wählen Sie **Registerkarte** Bedingungsvorgaben“ in der DITA-Zuordnungskonsole aus.
1. Klicken Sie **Schaltfläche** Bearbeiten“.
1. Nehmen Sie die erforderlichen Änderungen für alle Attribute in der Bedingungsvorgabe vor.
1. Wählen Sie **Speichern** aus.

### Erstellen einer Kopie einer Bedingungsvorgabe

Sie können eine Kopie einer Bedingungsvorgabe erstellen und sie dann entsprechend Ihren Anforderungen ändern. Führen Sie die folgenden Schritte aus, um eine Kopie einer Bedingungsvorgabe zu erstellen:

1. Wählen Sie **Registerkarte** Bedingungsvorgaben“ in der DITA-Zuordnungskonsole aus.
1. Klicken Sie **Schaltfläche** Duplizieren“.

   >[!NOTE]
   >
   > Der Standardname der Voreinstellung lautet `<selected condition preset name>_Duplicate`

   Sie können den Namen entsprechend Ihren Anforderungen ändern.

1. \(Optional\) Nehmen Sie die erforderlichen Änderungen für alle Attribute in der Bedingungsvorgabe vor.
1. Wählen Sie **Speichern** aus.

### Bedingungsvorgabe löschen

Sie können eine oder mehrere Bedingungsvorgaben auf der Registerkarte **Bedingungsvorgabe** der DITA-Zuordnungskonsole löschen. Gehen Sie wie folgt vor, um Bedingungsvorgaben zu löschen:

1. Wählen Sie **Registerkarte** Bedingungsvorgaben“ in der DITA-Zuordnungskonsole aus.
1. Wählen Sie die zu löschende(n) Bedingungsvorgabe(en) aus.
1. Klicken Sie auf **Schaltfläche** Entfernen“.
1. Wählen **Entfernen** aus, um die Aktion zu bestätigen.

**Übergeordnetes Thema:**&#x200B;[&#x200B; Ausgabegenerierung](generate-output.md)
