---
title: Verwenden des DITAVAL-Editors
description: Erfahren Sie, wie Sie DITAVAL-Dateien mit dem DIVATAL-Editor in AEM Guides erstellen und bearbeiten. Erfahren Sie, wie der DITAVAL-Editor DITAVAL-Dateien in Autoren- und Quellansichten unterstützt.
feature: Authoring, DITAVAL Editor
role: User
hide: true
exl-id: 8eee347d-840e-4eaf-9441-c7c53a7c3aa0
source-git-commit: 26fa1e52920c1f1abd5655b9ca7341600a9bca67
workflow-type: tm+mt
source-wordcount: '758'
ht-degree: 0%

---

# DITAVAL-Editor {#ditaval-editor}

DITAVAL-Dateien werden zur Erzeugung von bedingten Ausgaben verwendet. In einem einzelnen Thema können Sie Bedingungen mithilfe von Elementattributen hinzufügen, um Inhalte mit Bedingungen zu versehen. Anschließend erstellen Sie eine DITAVAL-Datei, in der Sie die Bedingungen angeben, die aufgenommen werden sollen, um Inhalte zu generieren, und welche Bedingung bei der endgültigen Ausgabe ausgeschlossen werden soll.

Mit AEM Guides können Sie DITAVAL-Dateien mit dem DITAVAL-Editor ganz einfach erstellen und bearbeiten. Der DITAVAL-Editor ruft die in Ihrem System definierten Attribute \(oder tags\) ab, mit denen Sie DITAVAL-Dateien erstellen oder bearbeiten können. Weitere Informationen zum Erstellen und Verwalten von Tags in AEM finden Sie [ Abschnitt „Verwalten von ](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/features/tags.html?lang=de)&quot; in der Dokumentation zu AEM.

## DITAVAL-Datei erstellen

Führen Sie die folgenden Schritte aus, um eine DITAVAL-Datei zu erstellen:

1. Navigieren Sie in der Assets-Benutzeroberfläche zu dem Speicherort, an dem Sie die DITAVAL-Datei erstellen möchten.

1. Klicken Sie **Erstellen** \> **DITA-Thema**.

1. Wählen Sie auf der Blueprint-Seite DITAVAL-Dateivorlage aus und klicken Sie auf **Weiter**.

1. Geben Sie auf der Seite Eigenschaften die **Titel** und **Name** für die DITAVAL-Datei an.

   >[!NOTE]
   >
   > Der Name wird automatisch basierend auf dem Titel der Datei vorgeschlagen. Wenn Sie den Dateinamen manuell angeben möchten, stellen Sie sicher, dass der Name keine Leerzeichen, Apostrophe oder geschweifte Klammern enthält und mit &quot;.ditaval“ endet.

1. Klicken Sie auf **Erstellen**. Die Meldung Thema erstellt wird angezeigt.

   Sie können die DITAVAL-Datei zur Bearbeitung im DITAVAL-Editor öffnen oder die Themendatei im AEM-Repository speichern.


## DITAVAL-Datei bearbeiten

Führen Sie folgende Schritte aus, um eine DITAVAL-Datei zu bearbeiten:

1. Navigieren Sie in der Assets-Benutzeroberfläche zur DITAVAL-Datei, die Sie bearbeiten möchten.

1. Um eine exklusive Sperre für die Datei zu erhalten, wählen Sie die Datei aus und klicken Sie auf **Auschecken**.

1. Wählen Sie die Datei aus und klicken Sie auf **Bearbeiten**, um die Datei im AEM Guides DITAVAL-Editor zu öffnen.

   Mit dem DITAVAL-Editor können Sie die folgenden Aufgaben ausführen:

   A: Linkes Bedienfeld ein/aus
Linke Bereichsansicht umschalten. Wenn Sie die DITAVAL-Datei über DITA Map geöffnet haben, werden die Karte und das Repository in diesem Bedienfeld angezeigt. Weitere Informationen zum Öffnen einer Datei über DITA Map finden Sie unter [Themen über DITA Map bearbeiten](map-editor-advanced-map-editor.md#id17ACJ0F0FHS).

   B: Speichern
Speichert die in der Datei vorgenommenen Änderungen. Alle Ihre Änderungen werden in der aktuellen Version Ihrer Datei gespeichert.

   C: Eigenschaft hinzufügen
Fügen Sie in Ihrer DITAVAL-Datei eine einzelne Eigenschaft hinzu.

   ![](images/ditaval-editor-props.png)

   In der ersten Dropdown-Liste werden die zulässigen DITA-Attribute aufgelistet, die Sie in der DITAVAL-Datei verwenden können. Es werden fünf Attribute unterstützt: `audience`, `platform`, `product`, `props` und `otherprops`.

   Die zweite Dropdown-Liste zeigt die für das ausgewählte Attribut konfigurierten Werte an. Anschließend werden in der nächsten Dropdown-Liste die Aktionen angezeigt, die Sie für das ausgewählte Attribut konfigurieren können. Die zulässigen Werte in der Dropdown-Liste Aktion sind `include`, `exclude`, `passthrough` und `flag`. Weitere Informationen zu diesen Werten finden Sie unter Definition des Elements [prop](http://docs.oasis-open.org/dita/dita/v1.3/errata01/os/complete/part3-all-inclusive/langRef/ditaval/ditaval-prop.html#ditaval-prop) in der OASIS DITA-Dokumentation

   D: Alle Eigenschaften hinzufügen
Wenn Sie mit einem Klick alle in Ihrem System definierten bedingten Eigenschaften oder Attribute hinzufügen möchten, verwenden Sie die Funktion Alle Eigenschaften hinzufügen .

   >[!NOTE]
   >
   > Wenn alle definierten bedingten Eigenschaften bereits in der DITAVAL-Datei vorhanden sind, können Sie keine weiteren Eigenschaften hinzufügen. In diesem Szenario wird eine Fehlermeldung angezeigt.

   ![](images/ditaval-all-props.png)

1. Nachdem Sie Ihre DITAVAL-Datei bearbeitet haben, klicken Sie auf **Speichern**.

   >[!NOTE]
   >
   > Wenn Sie die Datei schließen, ohne zu speichern, gehen die Änderungen verloren. Wenn Sie die Änderungen nicht in das AEM-Repository übernehmen möchten, klicken Sie auf **Schließen** und anschließend **Ohne Speichern schließen** im Dialogfeld **Nicht gespeicherte Änderungen**.


## DITAVAL Editor-Ansichten

Der DITAVAL-Editor von AEM Guides unterstützt die Anzeige von DITAVAL-Dateien in zwei verschiedenen Modi oder Ansichten:

**Autor**:   Dies ist eine typische Ansicht von What You See Is What You Get \(WYSISYG\) des DITAVAL-Editors. Sie können Eigenschaften über die einfache Benutzeroberfläche hinzufügen oder entfernen, über die die Eigenschaften, ihre Werte und Aktionen in der Dropdown-Liste angezeigt werden. In der Autorenansicht haben Sie die Möglichkeit, eine einzelne Eigenschaft einzufügen und alle Eigenschaften mit einem Klick einzufügen.

Sie können auch die Version der DITAVAL-Datei finden, an der Sie gerade arbeiten, indem Sie den Mauszeiger über den Dateinamen bewegen.

**Source**:   Die Source-Ansicht zeigt den zugrunde liegenden XML-Code an, aus dem die DITAVAL-Datei besteht. In dieser Ansicht können Autoren nicht nur reguläre Textbearbeitungen durchführen, sondern auch Eigenschaften mithilfe des Smart-Katalogs hinzufügen oder bearbeiten.

Um den Smart-Katalog aufzurufen, platzieren Sie den Cursor am Ende einer Eigenschaftendefinition und geben Sie &quot;&lt;&quot; ein. Der Editor zeigt eine Liste aller gültigen XML-Elemente an, die Sie an dieser Stelle einfügen können.

![](images/ditaval-source-view.png)
