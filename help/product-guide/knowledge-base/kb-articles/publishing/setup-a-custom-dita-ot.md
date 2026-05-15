---
title: Einrichten eines benutzerdefinierten DITA-OT in [!DNL AEM Guides]
description: Erfahren Sie, wie Sie in ein benutzerdefiniertes DITA-OT einrichten [!DNL Adobe Experience Manager Guides]
role: Admin
exl-id: f479c2cf-5b8b-4517-be97-81303468007a
feature: DITA-OT Configuration
TQID: https://experienceleague.adobe.com/EaU6rkZL-RBkkYDhKxHNkizIVSqNzEDd-TtFlJAmREw
product_v2: id: fae5e35a-80c9-4b94-9352-1a060a6aab1did: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2: id: a3bd6397-2eb2-4908-a61c-226e26855dcaid: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
subfeature_v2: id: b1ef4d86-3917-4b76-a0bc-4a4771f9b3b0
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: a004cc84-67b9-4a33-a3a7-8ec7273ef4dc
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 174
ht-degree: 0%

---

# Einrichten eines benutzerdefinierten DITA-OT in [!DNL AEM Guides] für AEM

Die Schritte zum Hinzufügen eines benutzerdefinierten DITA-OT werden im Abschnitt _Verwenden benutzerdefinierter DITA-OT_ des _Installations- und Konfigurationshandbuchs_ beschrieben.

Die allgemeinen Schritte sind:

+ Abrufen der grundlegenden DITA-OT-Daten
   + Wenn Sie eine Kopie des vordefinierten DITA-OT von [!DNL AEM Guides] erhalten möchten, laden Sie sie von Pfad `/etc/fmdita/dita_resources/DITA-OT.zip` herunter
   + Wenn Sie eine andere Version erhalten möchten, können Sie sie von [dita-ot repo](https://www.dita-ot.org/download)
+ Nehmen Sie Änderungen am DITA-OT vor, z[ B. ](https://www.dita-ot.org/dev/topics/plugins-installing.html) Hinzufügen eines neuen Plug-ins oder Anpassen vorhandener Plug-ins (siehe Beispiel im Abschnitt „Verknüpfte Links“ unten)
+ Upload `DITA-OT.zip` empfangen in `/apps/<project-folder>/dita_resources` (Erstellen eines benutzerdefinierten Projektordners wird empfohlen)
+ Fügen Sie DITA-Profile über **[!UICONTROL Tools]** > **[!UICONTROL Handbücher]** > **[!UICONTROL DITA-Profile]** hinzu (verwenden Sie den DITA-OT-Pfad, in den das benutzerdefinierte DITA-OT hochgeladen wird, siehe Screenshot unten)
  ![DITA-Profile](assets/dita-profile.png)

>[!MORELIKETHIS]
>
>+ [Anpassen von DITA-OT-Plug-in-Beispielen](https://www.dita-ot.org/dev/topics/pdf-customization.html)
