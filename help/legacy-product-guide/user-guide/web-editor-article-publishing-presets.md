---
title: Erstellen von Ausgabevorgaben aus dem Web-Editor
description: Erstellen Sie Ausgabevorgaben aus dem Web-Editor. Erfahren Sie, wie Sie eine Ausgabevorgabe in AEM Guides bearbeiten, umbenennen, duplizieren und löschen können.
feature: Authoring, Features of Web Editor, Publishing
role: User
hide: true
exl-id: ce8e3614-907b-4172-a8f0-e81e4dc096df
TQID: https://experienceleague.adobe.com/nCmtXuQXfOVVHbmGrRT6rVzEa6NlR-o9TGmwhqczWPs
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2:
  - id: a3bd6397-2eb2-4908-a61c-226e26855dca
  - id: ab01a588-7dea-43f2-a699-0b3f128465d6
  - id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
subfeature_v2:
  - id: ad602516-aca3-4247-9ae8-f393d958efa9
  - id: f89f75b0-cf2e-4e96-aec8-fe8c39cbd0ef
  - id: fd6cc9e1-e5e5-494e-b7b1-a32f2d6cd7c9
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 370
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

   ![](images/output-tab-preset_cs.png){width="350"}

1. Geben Sie den Namen der Vorgabe im Dialogfeld „Vorgabe hinzufügen“ ein und klicken Sie dann auf **Hinzufügen**.

1. Geben Sie die folgenden Konfigurationsdetails ein.

   1. Wählen Sie die erforderlichen Optionen auf der Registerkarte **Allgemein** aus. Sie können eine Ausgabevorgabe mit oder ohne Bedingungen erstellen. Sie können auch eine DITVAL-Datei verwenden. Mit AEM Guides können Sie auch eine Grundlinie zum Veröffentlichen einer bestimmten Version Ihrer DITA-Zuordnung auswählen.
   1. Geben Sie die Details der AEM-Site auf der Registerkarte **AEM** ein. **Site** zeigt die Liste der AEM Sites an, die in Ihrem AEM-Repository verfügbar sind. **Kategorie**, **Abschnittsvorlage** und **Artikelvorlage** sind die Strukturkomponenten, mit denen das Erscheinungsbild Ihrer Ausgabe organisiert wird. Diese sind in der AEM-Site-Vorlage vordefiniert.

      >[!NOTE]
      >
      > Aktualisieren Sie jedes Dropdown, um die weitere Klassifizierung in der nächsten Dropdown-Liste zu erhalten.

   1. Wählen Sie auf der **Artikel**-Registerkarte die Themen aus, für die Sie die Ausgabe generieren möchten.
1. Wählen Sie oben **das Symbol** Voreinstellung generieren) aus, um die Ausgabe zu generieren.

   ![](images/add-preset-articles-tab_cs.png){width="800"}

1. Sie sehen den Status des Ausgabegenerierungsprozesses. Die Spalte **Themen** listet die Themen auf, für die Ausgaben generiert werden, während die Spalte **Status** den Veröffentlichungsstatus jedes Themas anzeigt.

   Um die Ausgabe anzuzeigen, bewegen Sie den Mauszeiger über das Thema und klicken Sie auf Ausgabe anzeigen.

   ![](images/add-preset-output-generated_cs.png){width="800"}


>[!NOTE]
>
> Sie können eine vorhandene Ausgabevorgabe auch über das Menü Optionen bearbeiten, umbenennen, duplizieren oder löschen.

![](images/edit-preset_cs.png){width="550"}

**Übergeordnetes Thema**&#x200B;[&#x200B; Artikelbasierte Veröffentlichung im Web-Editor](web-editor-article-publishing.md)
