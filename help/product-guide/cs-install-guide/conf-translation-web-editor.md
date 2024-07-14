---
title: Übersetzungsfunktion im Web-Editor konfigurieren
description: Erfahren Sie, wie Sie die Übersetzungsfunktion im Web Editor konfigurieren
exl-id: e25473c3-9a84-4658-87c9-6fd72bcaa2b6
feature: Web Editor Configuration
role: Admin
level: Experienced
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '154'
ht-degree: 0%

---

# Übersetzungsfunktion im Web-Editor konfigurieren {#id21BONI0J0YR}

Der Web-Editor bietet eine leistungsstarke Übersetzungsfunktion, mit der Sie Ihre Inhalte in mehrere Sprachen übersetzen können.

Sie können die Registerkarte **Verwalten** im Web Editor verwenden, um Ihren Inhalt zu übersetzen. Diese Registerkarte ist standardmäßig verfügbar.

So blenden Sie die Registerkarte **Verwalten** im Web Editor aus:

1. Melden Sie sich bei **Adobe Experience Manager** als Administrator an.
1. Klicken Sie oben auf den Link **Adobe Experience Manager** und wählen Sie **Tools** aus.
1. Wählen Sie **Handbücher** aus der Liste der Tools und klicken Sie auf **Ordnerprofile**.
1. Klicken Sie auf die Kachel **Globales Profil** .
1. Klicken Sie auf **XML-Editor-Konfiguration**.
1. Klicken Sie oben auf das Symbol **Bearbeiten** .
1. Laden Sie die Datei `ui\_config.json` herunter. Entfernen Sie das folgende Codefragment aus der heruntergeladenen Datei:

   ```json
   {
       "component":"tab",
       "id":"workflow",
       "title":"Manage",
       "on-click":"APP_MODE_CHANGE",
       "items":
       [
           {
               "component":"label",
               "label":"Manage"
           }
       ]
   },
   ```

1. Laden Sie die aktualisierte Datei ui\_config.json hoch.

Beachten Sie, dass der Filter **Verwalten** nicht mehr verfügbar ist.

**Übergeordnetes Thema:**[ Web-Editor anpassen](conf-web-editor.md)
