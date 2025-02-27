---
title: Veröffentlichen eines Themas in einem Experience Fragment
description: Veröffentlichen Sie ein Thema oder die Elemente innerhalb eines Themas in einem Experience Fragment in AEM Guides.  Erfahren Sie, wie Sie die für ein Thema vorhandenen Experience Fragments anzeigen und erneut veröffentlichen.
feature: Publishing
role: User
hide: true
exl-id: c3c6c063-441c-413b-a63e-0acbd126ca6d
source-git-commit: ea597cd14469f21e197c700542b9be7c373aef14
workflow-type: tm+mt
source-wordcount: '995'
ht-degree: 1%

---

# Veröffentlichen von Experience Fragments

Experience Fragments sind modulare Inhalte in Adobe Experience Manager. Diese Inhaltsbausteine basieren auf Vorlagen und kapseln sowohl den Inhalt als auch sein Layout. Diese wiederverwendbaren Inhaltselemente ermöglichen es Inhaltserstellern, konsistente, skalierbare Erlebnisse über mehrere Kanäle hinweg zusammenzustellen und bereitzustellen, die von Experience Manager unterstützt werden. Mit dieser Funktion können Sie auf einfache Weise und effizient konsistente Marketing-Erlebnisse wie Newsletter, Werbebanner und Kundenbewertungen erstellen.

Mit Experience Manager Guides können Sie ein Thema oder seine Elemente in einem Experience Fragment veröffentlichen. Sie können eine JSON-basierte Zuordnung zwischen einem Thema und seinen Elementen in einem Experience Fragment erstellen. Verwenden Sie dann die Zuordnung, um ein Thema oder seine Elemente in einem Experience Fragment zu veröffentlichen. Anschließend können Sie Experience Fragments auf einer beliebigen Experience Manager-Site verwenden oder die Details über APIs extrahieren, die von Experience Fragments unterstützt werden.




Um ein Experience Fragment zu generieren, führen Sie die folgenden Schritte aus:


1. Erstellen Sie einen Ordner in den Experience Fragments. Verwenden Sie diesen Ordner, um die Experience Fragments zu speichern, die Sie basierend auf den Experience Fragment-Vorlagen erstellen. Beispiel: *sales-experience-fragments*.
1. Wählen Sie den Ordner aus und klicken Sie **oben auf** Symbol „Eigenschaften“.
1. Bearbeiten Sie die Eigenschaften des Ordners (z. B *„sales-experience-fragments*).


   * **Titel**: Den Titel des Ordners anzeigen oder bearbeiten.

   * **Zulässige Vorlagen**: Enthält die Liste der Vorlagen, die als untergeordnete Seiten des Experience Fragments hinzugefügt werden können. Um die zulässige Vorlage hinzuzufügen, geben Sie den regulären Ausdruck zum Abrufen der erforderlichen Vorlagen im Feld **Zulässige Vorlagen** an.
Zum Beispiel:
     `/libs/cq/experience-fragments/components/experiencefragment/template`

     Wenn Sie keine zulässige Vorlage für einen Ordner definieren, werden die Vorlagen standardmäßig aus dem übergeordneten Ordner oder dem Vorlagenordner ausgewählt.
   * **Orderable**: Ermöglicht das Ändern der Reihenfolge der Assets innerhalb eines Ordners.
     ![Fügen Sie Cloud-Konfigurationsdetails in den Ordnereigenschaften hinzu](images/experience-fragment-folder-properties.png){width="650" align="left"}
     *Fügen Sie die Cloud-Konfiguration in den Ordnereigenschaften hinzu, um sie mit den Fragmentvorlagen zu verbinden.*
1. Um ein Experience Fragment zu generieren, wählen Sie **Neue Ausgabe** ![neues Ausgabesymbol](./images/Add_icon.svg) aus dem Abschnitt **Ausgaben** im Abschnitt **Dateieigenschaften** eines Themas aus.
1. Wählen Sie **Experience Fragment** aus.\
   ![Registerkarte „Optionen“ der Dateieigenschaften](./images/file-properties-outputs.png){width="300" align="left"}

   *Ein neues Experience Fragment aus den Dateieigenschaften eines Themas hinzufügen*.

   >[!NOTE]
   >
   > Sie können ein Experience Fragment auch über die „Repository **Ansicht“**. Wählen Sie das Thema aus, das Sie als Experience Fragment veröffentlichen möchten. Wählen Sie dann im Menü **Optionen** die Option **Veröffentlichen als** > **Experience Fragment**.

1. Füllen Sie **Dialogfeld Experience Fragment** generieren die folgenden Details aus:
   ![Fügen Sie das Fragmentmodell und die Zuordnungsdetails im Dialogfeld Als Experience Fragment veröffentlichen hinzu](images/experience-fragment-generate.png){width="500" align="left"}

   *Fügen Sie den Pfad, die Vorlage und die Zuordnungsdetails hinzu, um ein Thema oder seine Elemente als Experience Fragment zu veröffentlichen. Sie können ein vorhandenes Experience Fragment überschreiben.*

   * **Path**: Durchsuchen Sie den Ordner und wählen Sie den Pfad aus, in dem Sie das Experience Fragment veröffentlichen möchten. Sie können auch ein vorhandenes Experience Fragment auswählen und erneut veröffentlichen.
   * **Titel**: Geben Sie den Titel des Experience Fragments ein. Standardmäßig wird der Titel mit dem Titel des Themas gefüllt. Sie können ihn bearbeiten. Dieser Titel wird verwendet, um den Namen des Experience Fragments zu generieren.
   * **Name**: Geben Sie den Namen des Experience Fragments ein. Standardmäßig wird der Name mit dem Titel des Themas gefüllt und die Leerzeichen werden durch „_“ ersetzt. Beispiel: *sample_experience_fragment*. Sie können ihn bearbeiten. Dieser Name wird verwendet, um die URL für das Experience Fragment zu generieren.
   * **Vorlage**: Wählen Sie die Experience Fragment-Vorlage aus, die Sie zum Erstellen Ihres Experience Fragments verwenden möchten. Die Vorlagen werden aus dem Ordner ausgewählt, den Sie in den Eigenschaften konfiguriert haben.
   * **Mapping**: Die Zuordnung wird aus der Datei *experienceFragmentMapping.json* ausgewählt und angezeigt.



     Ihr Administrator kann die Zuordnungen in der Datei *experienceFragmentMapping.json* hinzufügen.  Weitere Informationen zum Erstellen [ Zuordnung zwischen einem Thema und einem Experience Fragment ](/help/product-guide/cs-install-guide/conf-experience-fragment-mapping-cs.md) Sie im Installations- und Konfigurationshandbuch.

   * Sie können auch verschiedene Bedingungen zum Veröffentlichen des Inhalts auswählen.  Wählen Sie eine der folgenden Optionen aus:


      * **Keine**: Wählen Sie diese Option aus, wenn Sie keine Bedingung auf die veröffentlichte Ausgabe anwenden möchten.
      * **Verwenden von DITAVAL**: Wählen Sie die DITAVAL-Datei aus, um personalisierte Inhalte zu generieren. Sie können die DITAVAL-Datei über das Dialogfeld „Durchsuchen“ oder durch Eingabe des Dateipfads auswählen.
      * **Verwendung von Attributen**: Sie können Bedingungsattribute in Ihren DITA-Themen definieren. Wählen Sie dann das Bedingungsattribut aus, um den relevanten Inhalt zu veröffentlichen.

     >[!NOTE]
     > 
     >Bedingungen werden nur aktiviert, wenn im Thema Bedingungsattribute definiert sind.


   * Aktivieren Sie das **Vorhandenen Inhalt überschreiben**, wenn Ihr Experience Fragment bereits vorhanden ist und Sie es überschreiben möchten. Experience Manager Guides zeigt einen Fehler an, wenn Sie das Kontrollkästchen nicht aktivieren und Ihr Experience Fragment bereits vorhanden ist.
1. Klicken Sie **Generieren**, um das Experience Fragment zu veröffentlichen.
1. Sie können die Experience Fragments für ein Thema im Abschnitt **Ausgaben** in den **Dateieigenschaften**. Die Experience Fragments werden nach Datum und Uhrzeit der Veröffentlichung angezeigt. Die neueste Version ist die erste.

   ![Anzeigen der Experience Fragments für ein Thema](images/experience-fragment-outputs.png){width=300 align=„left“}

   *Zeigen Sie die für ein Thema vorhandenen Experience Fragments an und veröffentlichen Sie sie erneut.*




Nachdem Sie die Experience Fragments veröffentlicht haben, können Sie sie auch auf jeder beliebigen Adobe Experience Manager-Site verwenden.


## Optionsmenü für ein Experience Fragment

Sie können auch die folgenden Aktionen für ein Experience Fragment über das Menü **Optionen** ausführen:

* **Generieren**: Veröffentlichen Sie das Experience Fragment erneut, um es mit dem neuesten Inhalt aus dem DITA-Thema zu aktualisieren. Beim Neugenerieren der Ausgabe können Sie den Pfad, den Namen, den Titel und die Vorlage des Experience Fragments nicht ändern. Sie können jedoch beim Regenerieren der Ausgabe andere Bedingungen auswählen.

* **Duplizieren**: Duplizieren Sie ein Experience Fragment. Sie können den Pfad, den Namen, den Titel und die Vorlage ändern. Beim Duplizieren eines Experience Fragments können Sie auch andere Bedingungen auswählen.

* **Entfernen**: Ein Experience Fragment aus der Ausgabeliste entfernen. Eine Bestätigungsaufforderung wird angezeigt. Sobald Sie bestätigen, wird das Experience Fragment aus der Liste **Ausgaben** entfernt. Das Experience Fragment wird jedoch nicht aus dem Ordner gelöscht.

* **Anzeigen**: Anzeigen des Experience Fragment-Editors. Sie können auch Änderungen vornehmen und speichern.
