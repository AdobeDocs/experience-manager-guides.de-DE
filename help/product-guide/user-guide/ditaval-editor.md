---
title: Verwenden des DITAVAL-Editors
description: Erfahren Sie, wie Sie DITAVAL-Dateien mit dem DIVATAL-Editor in Adobe Experience Manager Guides erstellen und bearbeiten. Erfahren Sie, wie der DITAVAL-Editor DITAVAL-Dateien in Autoren- und Quellansichten unterstützt.
exl-id: f3901a4f-1925-42aa-b773-0d6f18175ce8
feature: Authoring, DITAVAL Editor
role: User
source-git-commit: ac83f613d87547fc7f6a18070545e40ad4963616
workflow-type: tm+mt
source-wordcount: '1039'
ht-degree: 0%

---

# DITAVAL-Editor {#ditaval-editor}

DITAVAL-Dateien werden zur Erzeugung von bedingten Ausgaben verwendet. In einem einzelnen Thema können Sie Bedingungen mithilfe von Elementattributen hinzufügen, um Inhalte mit Bedingungen zu versehen. Anschließend erstellen Sie eine DITAVAL-Datei, in der Sie die Bedingungen angeben, die aufgenommen werden sollen, um Inhalte zu generieren, und welche Bedingung bei der endgültigen Ausgabe ausgeschlossen werden soll.

Mit Adobe Experience Manager Guides können Sie DITAVAL-Dateien mit dem DITAVAL-Editor ganz einfach erstellen und bearbeiten. Der DITAVAL-Editor ruft die in Ihrem System definierten Attribute \(oder tags\) ab, mit denen Sie DITAVAL-Dateien erstellen oder bearbeiten können. Weitere Informationen zum Erstellen und Verwalten von Tags in Adobe Experience Manager finden Sie [ Abschnitt „Verwalten von ](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/features/tags.html?lang=de)&quot; in der Dokumentation zu Adobe Experience Manager.

In den folgenden Abschnitten werden die verfügbaren Optionen für eine DITAVAL-Datei in Experience Manager Guides beschrieben.

- [DITAVAL-Datei erstellen](#create-ditaval-file)
- [DITAVAL-Datei bearbeiten](#edit-ditaval-file)
- [DITAVAl-Datei-Editor-Ansichten](#ditaval-editor-views)
- [Arbeiten mit einer DITAVAL-Datei in der Assets-Benutzeroberfläche](#working-with-ditaval-files-in-the-assets-ui)

## DITAVAL-Datei erstellen

Führen Sie die folgenden Schritte aus, um eine DITAVAL-Datei zu erstellen:

1. Wählen Sie im Repository-Bedienfeld das Symbol **Neue Datei** und wählen Sie dann **Thema** aus dem Dropdown-Menü aus.

   ![](images/new-file-option.png){align="left"}

   Sie können auf diese Option auch über die Startseite von [Experience Manager Guides ](./intro-home-page.md) über das Optionsmenü eines Ordners in der Repository-Ansicht zugreifen.

2. Das **Neues Thema** wird angezeigt.

3. Geben **im Dialogfeld** Neues Thema“ die folgenden Details an:
   - Ein Titel für das Thema.
   - \(Optional\)* Der Dateiname für das Thema. Der Dateiname wird basierend auf dem Thementitel automatisch vorgeschlagen. Wenn Ihr Administrator automatische Dateinamen basierend auf der UUID-Einstellung aktiviert hat, wird das Feld Name nicht angezeigt.
   - Eine Vorlage, auf der das Thema basieren soll. Für eine DITAVAL-Datei wählen Sie **Ditaval** aus der Dropdown-Liste aus.
   - Pfad zum Speichern der Themendatei. Standardmäßig wird der Pfad des aktuell ausgewählten Ordners im Repository im Feld Pfad angezeigt.

   ![](images/new-topic-dialog-ditaval.png){width="300" align="left"}


4. Wählen Sie **Erstellen** aus.

Das Thema wird unter dem angegebenen Pfad erstellt. Außerdem wird das Thema im Editor zur Bearbeitung geöffnet.

![](images/ditaval-file-editor.png){align="left"}

## DITAVAL-Datei bearbeiten

Wenn Sie ein DITAVAL-Thema erstellen, wird es im Editor zur Bearbeitung geöffnet. Um ein vorhandenes DITAVAL-Thema zu bearbeiten, navigieren Sie zu dem Ordner oder der Karte, in dem bzw. der sich das DITAVAL-Thema befindet, und wählen Sie **Bearbeiten** aus dem Menü **Optionen**.

Mit dem DITAVAL-Editor können Sie die folgenden Aufgaben ausführen:

- Linkes Bedienfeld ein/aus

  Linke Bereichsansicht umschalten. Wenn Sie die DITAVAL-Datei über DITA Map geöffnet haben, werden die Karte und das Repository in diesem Bedienfeld angezeigt. Weitere Informationen zum Öffnen einer Datei über DITA Map finden Sie unter [Themen über DITA Map bearbeiten](map-editor-advanced-map-editor.md#id17ACJ0F0FHS).

- Speichern Sie.

  Speichert die in der Datei vorgenommenen Änderungen. Alle Ihre Änderungen werden in der aktuellen Version Ihrer Datei gespeichert.

- Eigenschaft hinzufügen

  Fügen Sie in Ihrer DITAVAL-Datei eine einzelne Eigenschaft hinzu.

  ![](images/ditaval-editor-props-new.png)

  In der ersten Dropdown-Liste werden die zulässigen DITA-Attribute aufgelistet, die Sie in der DITAVAL-Datei verwenden können. Es werden fünf Attribute unterstützt: `audience`, `platform`, `product`, `props` und `otherprops`.

  Die zweite Dropdown-Liste zeigt die für das ausgewählte Attribut konfigurierten Werte an. Anschließend werden in der nächsten Dropdown-Liste die Aktionen angezeigt, die Sie für das ausgewählte Attribut konfigurieren können. Die zulässigen Werte in der Dropdown-Liste Aktion sind `include`, `exclude`, `passthrough` und `flag`. Weitere Informationen zu diesen Werten finden Sie unter Definition des Elements [prop](http://docs.oasis-open.org/dita/dita/v1.3/errata01/os/complete/part3-all-inclusive/langRef/ditaval/ditaval-prop.html#ditaval-prop) in der OASIS DITA-Dokumentation

- Alle Eigenschaften hinzufügen

  Wenn Sie mit einem Klick alle in Ihrem System definierten bedingten Eigenschaften oder Attribute hinzufügen möchten, verwenden Sie die Funktion Alle Eigenschaften hinzufügen .

  >[!NOTE]
  >
  > Wenn alle definierten bedingten Eigenschaften bereits in der DITAVAL-Datei vorhanden sind, können Sie keine weiteren Eigenschaften hinzufügen. In diesem Szenario wird eine Fehlermeldung angezeigt.

  ![](images/ditaval-all-props-new.png)

Nachdem Sie die Bearbeitung der DITAVAL-Datei abgeschlossen haben, klicken Sie auf **Speichern**.

>[!NOTE]
>
> Wenn Sie die Datei schließen, ohne zu speichern, gehen die Änderungen verloren. Wenn Sie keine Änderungen in das Adobe Experience Manager-Repository übernehmen möchten, wählen Sie **Schließen** und dann **Ohne Speichern schließen** im Dialogfeld **Nicht gespeicherte Änderungen** aus.

## DITAVAL Editor-Ansichten

Der DITAVAL-Editor von Adobe Experience Manager Guides unterstützt die Anzeige von DITAVAL-Dateien in zwei verschiedenen Modi oder Ansichten:

**Autor**:   Dies ist eine typische Ansicht von What You See Is What You Get \(WYSISYG\) des DITAVAL-Editors. Sie können Eigenschaften über die einfache Benutzeroberfläche hinzufügen oder entfernen, über die die Eigenschaften, ihre Werte und Aktionen in der Dropdown-Liste angezeigt werden. In der Autorenansicht haben Sie die Möglichkeit, eine einzelne Eigenschaft einzufügen und alle Eigenschaften mit einem Klick einzufügen.

Sie können auch die Version der DITAVAL-Datei finden, an der Sie gerade arbeiten, indem Sie den Mauszeiger über den Dateinamen bewegen.

**Source**:   Die Source-Ansicht zeigt den zugrunde liegenden XML-Code an, aus dem die DITAVAL-Datei besteht. In dieser Ansicht können Autoren nicht nur reguläre Textbearbeitungen durchführen, sondern auch Eigenschaften mithilfe des Smart-Katalogs hinzufügen oder bearbeiten.

Um den Smart-Katalog aufzurufen, platzieren Sie den Cursor am Ende einer Eigenschaftendefinition und geben Sie &quot;&lt;&quot; ein. Der Editor zeigt eine Liste aller gültigen XML-Elemente an, die Sie an dieser Stelle einfügen können.

![](images/ditaval-source-view-new.png)


## Arbeiten mit DITAVAL-Dateien in der Assets-Benutzeroberfläche

Sie können auch eine DITAVAL-Datei über die Assets-Benutzeroberfläche erstellen. Gehen Sie wie folgt vor, um ein neues DITAVAL-Thema zu erstellen:

1. Navigieren Sie in der Assets-Benutzeroberfläche zu dem Speicherort, an dem Sie die DITAVAL-Datei erstellen möchten.

1. Wählen Sie **Erstellen** \> **DITA-Thema**.

1. Wählen Sie auf der Blueprint-Seite DITAVAL-Dateivorlage und klicken Sie auf **Weiter**.

1. Geben Sie auf der Seite Eigenschaften die **Titel** und **Name** für die DITAVAL-Datei an.

   >[!NOTE]
   >
   > Der Name wird automatisch basierend auf dem Titel der Datei vorgeschlagen. Wenn Sie den Dateinamen manuell angeben möchten, stellen Sie sicher, dass der Name keine Leerzeichen, Apostrophe oder geschweifte Klammern enthält und mit &quot;.ditaval“ endet.

1. Wählen Sie **Erstellen** aus.

   Die Meldung Thema erstellt wird angezeigt.

Sie können die DITAVAL-Datei zur Bearbeitung im DITAVAL-Editor öffnen oder die Themendatei im Adobe Experience Manager-Repository speichern.

Führen Sie folgende Schritte aus, um eine vorhandene DITAVAL-Datei zu bearbeiten:

1. Navigieren Sie in der Assets-Benutzeroberfläche zur DITAVAL-Datei, die Sie bearbeiten möchten.

1. Um eine exklusive Sperre für die Datei zu erhalten, wählen Sie die Datei aus und klicken Sie auf **Auschecken**.

1. Wählen Sie die Datei aus und klicken Sie **Bearbeiten**, um die Datei im Adobe Experience Manager Guides DITAVAL-Editor zu öffnen.



