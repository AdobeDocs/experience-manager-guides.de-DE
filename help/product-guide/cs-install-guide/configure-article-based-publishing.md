---
title: Installieren von Paketen für die artikelbasierte Veröffentlichung
description: Erfahren Sie, wie Sie Pakete für die artikelbasierte Veröffentlichung installieren
exl-id: d83fc1a9-0822-47f0-8099-22a74b9ced2a
feature: Web Editor Configuration
role: Admin
level: Experienced
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '348'
ht-degree: 0%

---

# Installieren von Paketen für die artikelbasierte Veröffentlichung {#id21BNL02052Z}

AEM Guides bietet eine leistungsstarke Funktion zum Veröffentlichen auf Artikelbasis, die in den Web-Editor integriert ist. Mit dieser Funktion können Sie ein oder mehrere Themen gleichzeitig veröffentlichen. Nachdem Sie eine Zuordnung im Zuordnungs-Editor geöffnet haben, können Sie zur Registerkarte Ausgaben navigieren, um eine Vorgabe zu erstellen, und dann ein oder mehrere Themen auswählen, um die Ausgabe zu generieren. Sie können die Funktion zum artikelbasierten Veröffentlichen verwenden, um schrittweise Ausgaben für ein oder mehrere Themen zu generieren oder Ihre Inhalte Artikel für Artikel auf einer Wissensdatenbankplattform zu veröffentlichen. Weitere Informationen finden Sie *Abschnitt Artikelbasierte Veröffentlichung im Web-Editor* im Benutzerhandbuch.

Um eine AEM-Site zum Veröffentlichen der artikelbasierten Ausgabe zu erstellen, führen Sie die folgenden Schritte aus:

1. Laden Sie das **XML Documentation-Komponenten-Inhaltspaket für den Cloud Service** von Ihrem [Adobe-Software-Verteilungsportal ](https://experience.adobe.com/#/downloads/content/software-distribution/en/general.html).
1. Öffnen Sie AEM Package Manager. Die Standard-URL für den Zugriff auf den Package Manager lautet: `https://<hostname>/crx/packmgr/index.jsp`
1. Laden Sie das Inhaltspaket der XML Documentation-Komponenten für Cloud Service hoch und installieren Sie es dann.
1. Laden Sie die `Knowledge-base-template-for-article-based-publishing-for-cloud-service.zip` Datei vom [Adobe Software Distribution-Portal](https://experience.adobe.com/#/downloads/content/software-distribution/en/general.html) herunter.
1. Wählen Sie in der globalen Navigation **Sites** aus.
1. Klicken Sie in der Sites **Benutzeroberfläche oben rechts auf** Schaltfläche „Erstellen“.
1. Wählen Sie **Site aus Vorlage** aus der **Erstellen**.
1. Klicken Sie auf **Importieren** und wählen Sie dann die auf Ihrem System heruntergeladene `Knowledge-base-template-for-article-based-publishing-for-cloud-service.zip` aus. Nachdem die Site-Vorlage importiert wurde, wird sie unten aufgelistet.

   >[!NOTE]
   >
   > Sie müssen die ZIP-Datei nur für das erste Mal importieren. Nach dem Import ist die Site-Vorlage in der Liste verfügbar.

   Wählen Sie **Knowledgebase-Vorlage für die artikelbasierte Veröffentlichung** aus, um die AEM-Site zu erstellen, und klicken **oben rechts** Weiter“.

1. Geben Sie **Site-Titel** und den **Site-Namen** ein und klicken Sie **Erstellen** in der oberen rechten Ecke. Eine AEM-Site wird mithilfe der Tragopan-Site-Vorlage erstellt. \(Die Tragopan-Website ist eine Beispiel-AEM-Website der Wissensdatenbank mit Vorlagen für eine Kategorie, einen Abschnitt und Artikelseiten.\)

   >[!NOTE]
   >
   > Sie können mit derselben Vorlage mehrere AEM-Sites erstellen.


Sie können die AEM-Site verwenden, um Ihren Artikel mithilfe der Ausgabevorgaben aus dem Web-Editor zu veröffentlichen.

**Übergeordnetes Thema:**[ Anpassen des Web-Editors](conf-web-editor.md)
