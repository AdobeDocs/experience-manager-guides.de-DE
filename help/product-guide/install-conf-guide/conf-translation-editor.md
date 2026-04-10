---
title: Konfigurieren der Übersetzungsfunktion im Web-Editor
description: Erfahren Sie, wie Sie die Übersetzungsfunktion im Web-Editor konfigurieren
feature: Web Editor Configuration
role: Admin
level: Experienced
source-git-commit: 6f3f05419f4f5cdd45ab580cdee6fa869f20f01d
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

Beachten Sie, dass **Filter** Verwalten“ nicht mehr verfügbar ist.

**Übergeordnetes Thema:**[ Anpassen des Web-Editors](customize-overview.md)
