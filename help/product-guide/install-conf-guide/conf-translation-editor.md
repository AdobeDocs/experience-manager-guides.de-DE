---
title: Konfigurieren der Übersetzungsfunktion im Web-Editor
description: Erfahren Sie, wie Sie die Übersetzungsfunktion im Web-Editor konfigurieren
feature: Web Editor Configuration
role: Admin
level: Experienced
exl-id: 22d7e1c7-2059-43fb-b7aa-3ae4a6072678
source-git-commit: 82c93529b8535532cf50f6428c41a1881b24859e
workflow-type: tm+mt
source-wordcount: '157'
ht-degree: 0%

---

# Konfigurieren der Übersetzungsfunktion im Web-Editor für Cloud Service

Der Web-Editor bietet eine leistungsstarke Übersetzungsfunktion, mit der Sie Ihre Inhalte in mehrere Sprachen übersetzen können.

Sie können die Registerkarte **Verwalten** im Web-Editor verwenden, um Ihre Inhalte zu übersetzen. Diese Registerkarte ist standardmäßig verfügbar.

Um die Registerkarte **Verwalten** im Web-Editor auszublenden, führen Sie die folgenden Schritte aus:

1. Melden Sie sich bei **Adobe Experience Manager** als Admin an.
1. Klicken Sie oben auf den Link **Adobe Experience Manager** und wählen Sie &quot;**&quot;**.
1. Wählen Sie **Guides** aus der Liste der Tools aus und klicken Sie auf **Ordnerprofile**.
1. Klicken Sie auf die **Globales Profil**-Kachel.
1. Klicken Sie auf **XML-Editor-Konfiguration**.
1. Klicken Sie oben **auf** Bearbeiten“.
1. Laden Sie die `ui\_config.json` Datei herunter.Entfernen Sie das folgende Codefragment aus der heruntergeladenen Datei:

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

Beachten Sie, dass **Filter** Verwalten“ nicht mehr verfügbar ist.

**Übergeordnetes Thema:**[ Anpassen des Web-Editors](customize-overview.md)
