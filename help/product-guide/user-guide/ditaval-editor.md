---
title: Verwenden des DITAVAL-Editors
description: Erfahren Sie, wie Sie DITAVAL-Dateien mit dem DIVATAL Editor in AEM Guides erstellen und bearbeiten. Erfahren Sie, wie der DITAVAL-Editor DITAVAL-Dateien in der Autoren- und Quellansicht unterstützt.
exl-id: f3901a4f-1925-42aa-b773-0d6f18175ce8
feature: Authoring, DITAVAL Editor
role: User
source-git-commit: be06612d832785a91a3b2a89b84e0c2438ba30f2
workflow-type: tm+mt
source-wordcount: '758'
ht-degree: 0%

---

# DITAVAL-Editor {#ditaval-editor}

DITAVAL-Dateien werden verwendet, um eine bedingte Ausgabe zu generieren. In einem einzelnen Thema können Sie Bedingungen mithilfe von Elementattributen hinzufügen, um Inhalte an Bedingungen zu knüpfen. Anschließend erstellen Sie eine DITAVAL-Datei, in der Sie die Bedingungen angeben, die aufgenommen werden sollen, um Inhalte zu generieren, und welche Bedingung aus der endgültigen Ausgabe ausgeschlossen werden soll.

Mit AEM Guides können Sie DITAVAL-Dateien einfach mit dem DITAVAL-Editor erstellen und bearbeiten. Der DITAVAL-Editor ruft die in Ihrem System definierten Attribute \(oder Tags\) ab und Sie können sie zum Erstellen oder Bearbeiten von DITAVAL-Dateien verwenden. Weitere Informationen zum Erstellen und Verwalten von Tags in AEM finden Sie im Abschnitt [Verwalten von Tags](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/features/tags.html?lang=en) in AEM Dokumentation.

## DITAVAL-Datei erstellen

Führen Sie die folgenden Schritte aus, um eine DITAVAL-Datei zu erstellen:

1. Navigieren Sie in der Assets-Benutzeroberfläche zu dem Speicherort, an dem Sie die DITAVAL-Datei erstellen möchten.

1. Klicken Sie auf **Erstellen** \> **DITA-Thema**.

1. Wählen Sie auf der Blueprint-Seite die DITAVAL-Dateivorlage aus und klicken Sie auf **Weiter**.

1. Geben Sie auf der Eigenschaftsseite den **Titel** und den **Namen** für die DITAVAL-Datei an.

   >[!NOTE]
   >
   > Der Name wird basierend auf dem Titel Ihrer Datei automatisch vorgeschlagen. Wenn Sie den Dateinamen manuell angeben möchten, stellen Sie sicher, dass der Name keine Leerzeichen, Apostroph oder Klammern enthält und mit &quot;.ditaval&quot;endet.

1. Klicken Sie auf **Erstellen**. Die Meldung Thema erstellt wird angezeigt.

   Sie können die DITAVAL-Datei zur Bearbeitung im DITAVAL-Editor öffnen oder die Themendatei im AEM Repository speichern.


## DITAVAL-Datei bearbeiten

Führen Sie die folgenden Schritte aus, um eine DITAVAL-Datei zu bearbeiten:

1. Navigieren Sie in der Assets-Benutzeroberfläche zur DITAVAL-Datei, die Sie bearbeiten möchten.

1. Um eine exklusive Sperre für die Datei zu erhalten, wählen Sie die Datei aus und klicken Sie auf **Auschecken**.

1. Wählen Sie die Datei aus und klicken Sie auf **Bearbeiten** , um die Datei im AEM Guides DITAVAL-Editor zu öffnen.

   Mit dem DITAVAL-Editor können Sie die folgenden Aufgaben ausführen:

   A: Linkes Bedienfeld ein/aus
Wechsel zur linken Bereichsansicht. Wenn Sie die DITAVAL-Datei über die DITA-Zuordnung geöffnet haben, werden die Zuordnung und das Repository in diesem Bedienfeld angezeigt. Weitere Informationen zum Öffnen einer Datei über eine DITA-Zuordnung finden Sie unter [Themen über DITA-Zuordnung bearbeiten](map-editor-advanced-map-editor.md#id17ACJ0F0FHS).

   B: Speichern
Speichert die Änderungen, die Sie in der Datei vorgenommen haben. Alle Ihre Änderungen werden in der aktuellen Version Ihrer Datei gespeichert.

   C: Eigenschaft hinzufügen
Fügen Sie eine einzelne Eigenschaft in Ihrer DITAVAL-Datei hinzu.

   ![](images/ditaval-editor-props.png)

   In der ersten Dropdown-Liste werden die zulässigen DITA-Attribute aufgelistet, die Sie in der DITAVAL-Datei verwenden können. Es werden fünf Attribute unterstützt: `audience`, `platform`, `product`, `props` und `otherprops`.

   Die zweite Dropdown-Liste zeigt die für das ausgewählte Attribut konfigurierten Werte an. In der nächsten Dropdownliste werden die Aktionen angezeigt, die Sie für das ausgewählte Attribut konfigurieren können. Die zulässigen Werte in der Dropdown-Liste &quot;Aktion&quot;sind - `include`, `exclude`, `passthrough` und `flag`. Weitere Informationen zu diesen Werten finden Sie in der Definition des Elements [prop](http://docs.oasis-open.org/dita/dita/v1.3/errata01/os/complete/part3-all-inclusive/langRef/ditaval/ditaval-prop.html#ditaval-prop) in der OASIS DITA-Dokumentation

   D: Alle Eigenschaften hinzufügen
Wenn Sie alle in Ihrem System definierten bedingten Eigenschaften oder Attribute mit einem Klick hinzufügen möchten, verwenden Sie die Funktion Alle Eigenschaften hinzufügen .

   >[!NOTE]
   >
   > Wenn alle definierten bedingten Eigenschaften bereits in der DITAVAL-Datei vorhanden sind, können Sie keine weiteren Eigenschaften hinzufügen. In diesem Szenario erhalten Sie eine Fehlermeldung.

   ![](images/ditaval-all-props.png)

1. Nachdem Sie die Bearbeitung der DITAVAL-Datei abgeschlossen haben, klicken Sie auf **Speichern**.

   >[!NOTE]
   >
   > Wenn Sie die Datei ohne Speichern schließen, gehen die Änderungen verloren. Wenn Sie keine Änderungen in AEM Repository übertragen möchten, klicken Sie auf **Schließen** und dann auf **Schließen ohne Speichern** im Dialogfeld **Nicht gespeicherte Änderungen**.


## DITAVAL-Editor-Ansichten

Der DITAVAL-Editor von AEM Guides unterstützt die Anzeige von DITAVAL-Dateien in zwei verschiedenen Modi oder Ansichten:

**Autor**:   Dies ist eine typische Ansicht des DITAVAL-Editors, was Sie sehen, was Sie \(WYSISYG\) erhalten. Sie können Eigenschaften über die einfache Benutzeroberfläche hinzufügen oder entfernen, in der die Eigenschaften, Werte und Aktionen in einer Dropdown-Liste angezeigt werden. In der Autorenansicht haben Sie die Möglichkeit, eine einzelne Eigenschaft einzufügen und alle Eigenschaften mit einem Klick einzufügen.

Sie können auch die Version der DITAVAL-Datei finden, an der Sie derzeit arbeiten, indem Sie den Mauszeiger über den Dateinamen bewegen.

**Source**:   In der Source-Ansicht wird die zugrunde liegende XML-Datei angezeigt, aus der sich die DITAVAL-Datei zusammensetzt. In dieser Ansicht können Autoren nicht nur reguläre Textänderungen vornehmen, sondern auch Eigenschaften mithilfe des Smart-Katalogs hinzufügen oder bearbeiten.

Um den Smart-Katalog aufzurufen, platzieren Sie den Cursor am Ende einer beliebigen Eigenschaftsdefinition und geben Sie &quot;&lt;&quot;ein. Der Editor zeigt eine Liste aller gültigen XML-Elemente an, die Sie an dieser Stelle einfügen können.

![](images/ditaval-source-view.png)
