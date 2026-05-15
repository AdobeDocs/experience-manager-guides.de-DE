---
title: Konfigurieren der Übersetzungsfunktion im Web-Editor
description: Erfahren Sie, wie Sie die Übersetzungsfunktion im Web-Editor konfigurieren
exl-id: e25473c3-9a84-4658-87c9-6fd72bcaa2b6
feature: Web Editor Configuration
role: Admin
level: Experienced
TQID: https://experienceleague.adobe.com/7-SFQ0FXQ6bGo3pjAOK-18sEsU4-zriruioG2nMx2o0
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2:
  - id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
subfeature_v2:
  - id: b0521e56-a0b2-40b6-bf47-ebc98751f9ba
  - id: b1ef4d86-3917-4b76-a0bc-4a4771f9b3b0
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 154
ht-degree: 0%

---

# Konfigurieren der Übersetzungsfunktion im Web-Editor {#id21BONI0J0YR}

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

**Übergeordnetes Thema:**&#x200B;[&#x200B; Anpassen des Web-Editors](conf-web-editor.md)
