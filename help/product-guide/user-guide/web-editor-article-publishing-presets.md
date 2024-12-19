---
title: Erstellen von Ausgabevorgaben aus dem Web-Editor
description: Erstellen Sie Ausgabevorgaben aus dem Web-Editor. Erfahren Sie, wie Sie eine Ausgabevorgabe in AEM Guides bearbeiten, umbenennen, duplizieren und löschen können.
exl-id: cd38b039-ef91-45c9-a226-433e57b09873
feature: Authoring, Features of Web Editor, Publishing
role: User
source-git-commit: be06612d832785a91a3b2a89b84e0c2438ba30f2
workflow-type: tm+mt
source-wordcount: '370'
ht-degree: 0%

---

# Erstellen von Ausgabevorgaben aus dem Web-Editor {#id218CL400JW3}

Führen Sie die folgenden Schritte aus, um Ausgabevorgaben für Ihre DITA-Zuordnung zu erstellen:

1. Navigieren Sie in der Assets-Benutzeroberfläche zu der Zuordnungsdatei, die Sie bearbeiten möchten.

1. Um eine exklusive Sperre für die Zuordnungsdatei zu erhalten, wählen Sie die Zuordnungsdatei aus und klicken Sie auf **Auschecken**.

1. Wählen Sie die **Themen bearbeiten** aus dem Aktionsmenü in der Zuordnungsdatei aus.

   Die Zuordnungsdatei wird zur Bearbeitung im Web-Editor geöffnet.

   >[!NOTE]
   >
   > Sie können mit dem erweiterten Zuordnungs-Editor ein beliebiges Thema zur Karte hinzufügen oder daraus löschen. Weitere Informationen finden Sie unter [Arbeiten mit dem erweiterten Zuordnungs-Editor](map-editor-advanced-map-editor.md#).

1. Wählen **auf der Registerkarte** Ausgabe“ das Symbol + aus, um eine Ausgabevorgabe für Ihre DITA-Zuordnung zu erstellen.

   ![](images/output-tab-preset_cs.png){width="350" align="left"}

1. Geben Sie den Namen der Vorgabe im Dialogfeld „Vorgabe hinzufügen“ ein und klicken Sie dann auf **Hinzufügen**.

1. Geben Sie die folgenden Konfigurationsdetails ein.

   1. Wählen Sie die erforderlichen Optionen auf der Registerkarte **Allgemein** aus. Sie können eine Ausgabevorgabe mit oder ohne Bedingungen erstellen. Sie können auch eine DITVAL-Datei verwenden. Mit AEM Guides können Sie auch eine Grundlinie zum Veröffentlichen einer bestimmten Version Ihrer DITA-Zuordnung auswählen.
   1. Geben Sie die Details der AEM-Site auf der Registerkarte **AEM** ein. **Site** zeigt die Liste der AEM Sites an, die in Ihrem AEM-Repository verfügbar sind. **Kategorie**, **Abschnittsvorlage** und **Artikelvorlage** sind die Strukturkomponenten, mit denen das Erscheinungsbild Ihrer Ausgabe organisiert wird. Diese sind in der AEM-Site-Vorlage vordefiniert.

      >[!NOTE]
      >
      > Aktualisieren Sie jedes Dropdown, um die weitere Klassifizierung in der nächsten Dropdown-Liste zu erhalten.

   1. Wählen Sie auf der **Artikel**-Registerkarte die Themen aus, für die Sie die Ausgabe generieren möchten.
1. Wählen Sie oben **das Symbol** Voreinstellung generieren) aus, um die Ausgabe zu generieren.

   ![](images/add-preset-articles-tab_cs.png){width="800" align="left"}

1. Sie sehen den Status des Ausgabegenerierungsprozesses. Die Spalte **Themen** listet die Themen auf, für die Ausgaben generiert werden, während die Spalte **Status** den Veröffentlichungsstatus jedes Themas anzeigt.

   Um die Ausgabe anzuzeigen, bewegen Sie den Mauszeiger über das Thema und klicken Sie auf Ausgabe anzeigen.

   ![](images/add-preset-output-generated_cs.png){width="800" align="left"}


>[!NOTE]
>
> Sie können eine vorhandene Ausgabevorgabe auch über das Menü Optionen bearbeiten, umbenennen, duplizieren oder löschen.

![](images/edit-preset_cs.png){width="550" align="left"}

**Übergeordnetes Thema**[ Artikelbasierte Veröffentlichung im Web-Editor](web-editor-article-publishing.md)
