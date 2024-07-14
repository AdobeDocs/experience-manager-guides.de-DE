---
title: Pakete für die artikelbasierte Veröffentlichung installieren
description: Erfahren Sie, wie Sie Pakete für eine artikelbasierte Veröffentlichung installieren.
exl-id: d83fc1a9-0822-47f0-8099-22a74b9ced2a
feature: Web Editor Configuration
role: Admin
level: Experienced
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '348'
ht-degree: 0%

---

# Pakete für die artikelbasierte Veröffentlichung installieren {#id21BNL02052Z}

AEM Guides bietet eine leistungsstarke artikelbasierte Veröffentlichungsfunktion, die in den Web Editor integriert ist. Mit dieser Funktion können Sie ein oder mehrere Themen gleichzeitig veröffentlichen. Nachdem Sie eine Zuordnung im Map Editor geöffnet haben, können Sie zur Registerkarte &quot;Ausgaben&quot;navigieren, um eine Vorgabe zu erstellen, und dann ein oder mehrere Themen auswählen, um die Ausgabe zu generieren. Sie können die Funktion zur artikelbasierten Veröffentlichung verwenden, um schrittweise die Ausgabe eines oder mehrerer Themen zu generieren oder Ihre Inhalte auf einer Knowledgebase-Plattform in Artikelform zu veröffentlichen. Weitere Informationen finden Sie unter *Artikelbasierte Veröffentlichung im Web-Editor-Abschnitt* im Benutzerhandbuch.

So erstellen Sie eine AEM Site zum Veröffentlichen einer artikelbasierten Ausgabe:

1. Laden Sie das Inhaltspaket für XML Documentation-Komponenten für Cloud Service **von Ihrem [Adobe-Software-Verteilungsportal](https://experience.adobe.com/#/downloads/content/software-distribution/en/general.html) herunter.**
1. Öffnen Sie AEM Package Manager. Die Standard-URL für den Zugriff auf den Paketmanager lautet: `https://<hostname>/crx/packmgr/index.jsp`
1. Laden Sie das XML Documentation Components Content Package für Cloud Service hoch und installieren Sie es dann.
1. Laden Sie die `Knowledge-base-template-for-article-based-publishing-for-cloud-service.zip`-Datei von Ihrem [Adobe Software Distribution-Portal](https://experience.adobe.com/#/downloads/content/software-distribution/en/general.html) herunter.
1. Wählen Sie in der globalen Navigation **Sites** aus.
1. Klicken Sie in der Sites-Benutzeroberfläche oben rechts auf die Schaltfläche **Erstellen** .
1. Wählen Sie **Site aus Vorlage** aus dem Dropdown-Menü **Erstellen** aus.
1. Klicken Sie auf die Schaltfläche **Importieren** und wählen Sie dann die auf Ihr System heruntergeladene `Knowledge-base-template-for-article-based-publishing-for-cloud-service.zip` aus. Nachdem die Site-Vorlage importiert wurde, wird sie unten aufgeführt.

   >[!NOTE]
   >
   > Sie müssen die ZIP-Datei nur zum ersten Mal importieren. Nach dem Import ist die Site-Vorlage in der Liste verfügbar.

   Wählen Sie **Knowledgebase-Vorlage für artikelbasierte Veröffentlichung** aus, um die AEM-Site zu erstellen, und klicken Sie oben rechts auf **Weiter** .

1. Geben Sie den **Site-Titel** und den **Site-Namen** ein und klicken Sie oben rechts auf **Erstellen** . Eine AEM Site wird mit der Site-Vorlage Tragopan erstellt. \(Die Site &quot;Tragopan&quot;ist eine Beispiel-Knowledgebase AEM Site mit Vorlagen für Kategorien, Abschnitte und Artikelseiten.\)

   >[!NOTE]
   >
   > Sie können mehrere AEM Sites mit derselben Vorlage erstellen.


Sie können die AEM-Website verwenden, um Ihren Artikel mithilfe der Ausgabevorgaben aus dem Web Editor zu veröffentlichen.

**Übergeordnetes Thema:**[ Web-Editor anpassen](conf-web-editor.md)
