---
title: Veröffentlichen eines Themas in einem Inhaltsfragment
description: Veröffentlichen Sie ein Thema oder die Elemente innerhalb eines Themas in einem Inhaltsfragment in AEM Guides.  Erfahren Sie, wie Sie die für ein Thema vorhandenen Inhaltsfragmente anzeigen und erneut veröffentlichen.
exl-id: b1769e48-d721-4e93-b10f-04b385272be7
feature: Publishing
role: User
source-git-commit: 26aacde56e84c9f3a5ee5106b9271b4b12f8969a
workflow-type: tm+mt
source-wordcount: '938'
ht-degree: 1%

---

# Veröffentlichen von Inhaltsfragmenten

Inhaltsfragmente sind separate Inhaltselemente in Adobe Experience Manager. Es handelt sich um strukturierte Inhalte, die auf einem Inhaltsmodell basieren. Inhaltsfragmente sind reine Inhalte ohne Design- oder Layout-Informationen. Sie können unabhängig von den von Adobe Experience Manager unterstützten Kanälen erstellt und verwaltet werden. Inhaltsfragmente sind modular, wobei Inhalte in kleinere Komponenten unterteilt werden.

Mit Experience Manager Guides können Sie ein Thema oder seine Elemente in einem Inhaltsfragment veröffentlichen.

>[!NOTE]
>
>Sie können nur die Elemente in einem Thema auswählen, für die ein ID-Attribut definiert ist.


Um ein Inhaltsfragment zu erstellen, führen Sie die folgenden Schritte aus:

1. Erstellen Sie ein [Inhaltsfragmentmodell](https://experienceleague.adobe.com/docs/experience-manager-65/assets/content-fragments/content-fragments-models.html?lang=de) in Adobe Experience Manager Assets.
1. Erstellen Sie einen Ordner, in dem Sie die Inhaltsfragmente speichern möchten, die Sie auf der Grundlage des Inhaltsfragmentmodells erstellen. Beispiel: „stock-content-fragments“.
1. Bearbeiten Sie die Eigenschaften des Ordners (z. B. „stock-content-fragments„) und fügen Sie den Pfad des Ordners hinzu, der das Inhaltsfragmentmodell in der Cloud-Konfiguration enthält.
Fügen Sie beispielsweise `/conf/we-retail` in der Cloud-Konfiguration hinzu. Diese Konfiguration verbindet alle Inhaltsfragmentmodelle mit dem Ordner.\
   ![Fügen Sie Cloud-Konfigurationsdetails in den Ordnereigenschaften hinzu](images/fragment-folder-cloud-configuration.png){width="650" align="left"}
   *Fügen Sie die Cloud-Konfiguration in den Ordnereigenschaften hinzu, um sie mit den Fragmentmodellen zu verbinden.*

1. Um ein Inhaltsfragment zu generieren, wählen Sie **Neue Ausgabe** ![neues Ausgabesymbol](./images/Add_icon.svg) aus dem Abschnitt **Ausgaben** im Abschnitt **Dateieigenschaften** eines Themas aus.
1. Wählen Sie **Inhaltsfragment** aus.\
   ![Registerkarte „Optionen“ der Dateieigenschaften](./images/file-properties-outputs-tab-new.png) {width="300" align="left"}

   *Ein neues Inhaltsfragment aus den Dateieigenschaften eines Themas hinzufügen*.

1. Füllen **Dialogfeld „Inhaltsfragment**&quot; die folgenden Details auf den Registerkarten **Allgemein** und **Zuordnung** aus.

   **Allgemein** Registerkarte
   ![Fügen Sie das Fragmentmodell und die Zuordnungsdetails im Dialogfeld Als Inhaltsfragment veröffentlichen hinzu](images/generate-content-fragment.png)
   *Fügen Sie den Pfad, den Namen, den Titel und die Bedingungsfilterung hinzu, um ein Thema oder seine Elemente als Inhaltsfragment zu veröffentlichen.*


   * **Pfad**: Durchsuchen und wählen Sie den Pfad des Ordners aus, in dem Sie das Inhaltsfragment veröffentlichen möchten. Wenn Sie ein vorhandenes Inhaltsfragment auswählen, wird der Inhalt der zugeordneten Felder überschrieben.
   * **Titel**: Geben Sie den Titel des Inhaltsfragments ein. Standardmäßig wird der Titel mit dem Titel des Themas gefüllt. Sie können ihn bearbeiten. Dieser Titel wird verwendet, um den Namen des Inhaltsfragments zu generieren.
   * **Name**: Geben Sie den Namen des Inhaltsfragments ein. Standardmäßig wird der Name mit dem Titel des Themas gefüllt und die Leerzeichen werden durch „_“ ersetzt. Beispiel: *sample_content_fragment*. Sie können ihn bearbeiten.  Dieser Name wird zum Generieren der URL für das Inhaltsfragment verwendet.

   * Sie können verschiedene Bedingungen auswählen, um Inhaltsfragmentvarianten zu erstellen. Wählen Sie eine der folgenden Optionen aus:
     >[!NOTE]
     > 
     > Bedingungen werden nur aktiviert, wenn im Thema Bedingungsattribute definiert sind.

      * **Keine**: Wählen Sie diese Option aus, wenn Sie keine Bedingung auf die veröffentlichte Ausgabe anwenden möchten.
      * **Verwenden von DITAVAL**: Wählen Sie die DITAVAL-Datei aus, um bestimmte Inhalte in die generierte Ausgabe ein- oder auszuschließen. Sie können die DITAVAL-Datei über das Dialogfeld „Durchsuchen“ oder durch Eingabe des Dateipfads auswählen.
      * **Verwendung von Attributen**: Sie können Bedingungsattribute in Ihren DITA-Themen definieren. Wählen Sie dann das Bedingungsattribut aus, um den relevanten Inhalt zu veröffentlichen.






   Registerkarte **Zuordnung**

   ![Fügen Sie das Fragmentmodell und die Zuordnungsdetails im Dialogfeld Als Inhaltsfragment veröffentlichen hinzu](images/content-fragment-mapping.png)

   *Wählen Sie das Inhaltsfragmentmodell aus und fügen Sie die Zuordnungsdetails hinzu, um ein Thema oder seine Elemente als Inhaltsfragment zu veröffentlichen.*

   * **Modell**: Wählen Sie das Inhaltsfragmentmodell aus, das Sie zum Erstellen Ihres Inhaltsfragments verwenden möchten. Die Modelle werden aus dem Ordner ausgewählt, den Sie auf dem Experience Manager Guides-Server konfiguriert haben.
   * **Zuordnung**: Sie können die Themenelemente anzeigen, auf die ein ID-Attribut angewendet wurde. Ziehen Sie die Themenelemente in die Felder des Inhaltsfragmentmodells.
Die rechte Seite wird im Falle eines vorhandenen Inhaltsfragments mit den veröffentlichten Inhaltsfragmentinhalten gefüllt. Diese können bei Bedarf mit dem Themeninhalt überschrieben werden. Sie können auch **Rückgängig“ auswählen** um die Zuordnungsänderungen rückgängig zu machen.


     >[!NOTE]
     >
     > Wenn Sie Version 4.4 oder frühere Versionen verwenden, wählen Sie eine Zuordnung aus der Dropdown-Liste aus. Die Zuordnungen werden aus der Datei *contentFragmentMapping.json* ausgewählt.  Ihr Administrator kann die Zuordnungen in der Datei *contentFragmentMapping.json* hinzufügen. Weitere Informationen zum Erstellen [ Zuordnung zwischen einem Thema und einem Inhaltsfragment ](../cs-install-guide/conf-content-fragment-mapping-cs.md) Sie im Installations- und Konfigurationshandbuch.

1. Wählen **Generieren**, um das Inhaltsfragment zu veröffentlichen.

1. Sie können die Inhaltsfragmente für ein Thema im Abschnitt **Ausgaben** in den **Dateieigenschaften**.

   ![Anzeigen der Inhaltsfragmente für ein Thema](images/outputs-options-menu-new.png){width="300" align="left"}

   *Anzeigen der für ein Thema vorhandenen Inhaltsfragmente und erneutes Veröffentlichen.*


Nachdem Sie die Inhaltsfragmente veröffentlicht haben, können Sie sie auch auf jeder beliebigen Adobe Experience Manager-Site verwenden.




## Optionsmenü für ein Inhaltsfragment

Sie können auch die folgenden Aktionen für ein Inhaltsfragment über das Menü **Optionen** ausführen:

* **Generieren**: Veröffentlichen Sie das Inhaltsfragment erneut, um es mit dem neuesten Inhalt aus dem DITA-Thema zu aktualisieren. Wenn Sie die Ausgabe neu generieren, können Sie den Pfad, den Namen, den Titel, das Modell und die Zuordnung des Inhaltsfragments ändern. Sie können beim Regenerieren der Ausgabe auch verschiedene Bedingungen auswählen.

* **Duplizieren**: Duplizieren eines Inhaltsfragments. Sie können den Pfad, den Namen, den Titel, das Modell und die Zuordnung ändern. Sie können auch verschiedene Bedingungen auswählen, wenn Sie ein Inhaltsfragment duplizieren, um eine Inhaltsfragmentvariante zu erstellen.

* **Entfernen**: Entfernen eines Inhaltsfragments aus der Ausgabeliste. Eine Bestätigungsaufforderung wird angezeigt. Sobald Sie bestätigen, wird das Inhaltsfragment aus der Liste **Ausgaben** entfernt.

  >[!NOTE]
  >
  > Durch diese Aktion wird kein Inhalt aus dem Inhaltsfragment gelöscht.

* **Anzeigen**: Anzeigen des Inhaltsfragment-Editors. Sie können auch Änderungen vornehmen und speichern.