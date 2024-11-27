---
title: Erstellen von Ausgabevorgaben aus dem Web-Editor
description: Erstellen Sie Ausgabevorgaben über den Web-Editor. Erfahren Sie, wie Sie eine Ausgabevorgabe in AEM Guides bearbeiten, umbenennen, duplizieren und löschen.
exl-id: cd38b039-ef91-45c9-a226-433e57b09873
feature: Authoring, Features of Web Editor, Publishing
role: User
source-git-commit: 7db3df07fd17eecae1c502554118ca12f95fb5ab
workflow-type: tm+mt
source-wordcount: '370'
ht-degree: 0%

---

# Erstellen von Ausgabevorgaben aus dem Web-Editor {#id218CL400JW3}

Führen Sie die folgenden Schritte aus, um Ausgabevorgaben für Ihre DITA-Zuordnung zu erstellen:

1. Navigieren Sie in der Assets-Benutzeroberfläche zu der Zuordnungsdatei, die Sie bearbeiten möchten.

1. Um eine exklusive Sperre für die Zuordnungsdatei zu erhalten, wählen Sie die Zuordnungsdatei aus und klicken Sie auf **Auschecken**.

1. Wählen Sie die Option **Themen bearbeiten** aus dem Aktionsmenü in der Zuordnungsdatei aus.

   Die Zuordnungsdatei wird zur Bearbeitung im Web-Editor geöffnet.

   >[!NOTE]
   >
   > Sie können jedes Thema mit dem erweiterten Map-Editor hinzufügen oder aus der Zuordnung löschen. Weitere Informationen finden Sie unter [Arbeiten mit dem erweiterten Map-Editor](map-editor-advanced-map-editor.md#).

1. Wählen Sie auf der Registerkarte **Ausgabe** das Symbol + aus, um eine Ausgabevorgabe für Ihre DITA-Zuordnung zu erstellen.

   ![](images/output-tab-preset_cs.png){width="350" align="left"}

1. Geben Sie den Namen der Vorgabe im Dialogfeld Vorgabe hinzufügen ein und klicken Sie dann auf **Hinzufügen**.

1. Geben Sie die folgenden Konfigurationsdetails ein.

   1. Wählen Sie die erforderlichen Optionen auf der Registerkarte **Allgemein** aus. Sie können eine Ausgabevorgabe mit oder ohne Bedingungen erstellen. Sie können auch eine DITVAL-Datei verwenden. Mit AEM Guides können Sie auch eine Grundlinie für die Veröffentlichung einer bestimmten Version Ihrer DITA-Map auswählen.
   1. Geben Sie die AEM Site-Details auf der Registerkarte **AEM** ein. **Site** zeigt die Liste der AEM Sites an, die in Ihrem AEM-Repository verfügbar sind. **Kategorie**, **Abschnittsvorlage** und **Artikelvorlage** sind die Strukturkomponenten, mit denen das Erscheinungsbild Ihrer Ausgabe organisiert wird. Diese sind in der Vorlage AEM Site vordefiniert.

      >[!NOTE]
      >
      > Aktualisieren Sie jedes Dropdown-Menü, um die weitere Klassifizierung in der nächsten Dropdown-Liste zu erhalten.

   1. Wählen Sie auf der Registerkarte **Artikel** die Themen aus, für die Sie die Ausgabe generieren möchten.
1. Wählen Sie oben das Symbol **Vorgabe generieren** aus, um die Ausgabe zu generieren.

   ![](images/add-preset-articles-tab_cs.png){width="800" align="left"}

1. Sie sehen den Status des Generierungsprozesses der Ausgabe. In der Spalte **Themen** werden die Themen aufgelistet, für die die Ausgabe generiert wird, während in der Spalte **Status** der Veröffentlichungsstatus der einzelnen Themen angezeigt wird.

   Um die Ausgabe anzuzeigen, bewegen Sie den Mauszeiger über das Thema und klicken Sie auf Ausgabe anzeigen .

   ![](images/add-preset-output-generated_cs.png){width="800" align="left"}


>[!NOTE]
>
> Sie können eine vorhandene Ausgabevorgabe auch im Menü &quot;Optionen&quot;bearbeiten, umbenennen, duplizieren oder löschen.

![](images/edit-preset_cs.png){width="550" align="left"}

**Übergeordnetes Thema:**[ Artikelbasierte Veröffentlichung aus dem Web-Editor](web-editor-article-publishing.md)
