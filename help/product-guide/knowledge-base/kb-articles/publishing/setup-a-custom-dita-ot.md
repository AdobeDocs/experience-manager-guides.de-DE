---
title: Einrichten von benutzerdefiniertem DITA-OT in [!DNL AEM Guides]
description: Erfahren Sie, wie Sie benutzerdefinierte DITA-OT in [!DNL Adobe Experience Manager Guides] einrichten.
role: Admin
exl-id: f479c2cf-5b8b-4517-be97-81303468007a
feature: DITA-OT Configuration
source-git-commit: be06612d832785a91a3b2a89b84e0c2438ba30f2
workflow-type: tm+mt
source-wordcount: '143'
ht-degree: 0%

---

# Einrichten von benutzerdefiniertem DITA-OT in [!DNL AEM Guides] für AEM

Die Schritte zum Hinzufügen eines benutzerdefinierten DITA-OT werden im Abschnitt _Verwenden benutzerdefinierter DITA-OT-Plug-ins_ des _Installations- und Konfigurationshandbuchs_ beschrieben.

Auf hoher Ebene sind die Schritte:

+ Grundlegendes DITA-OT abrufen
   + Wenn Sie eine Kopie des vordefinierten DITA-OT von [!DNL AEM Guides] erhalten möchten, laden Sie es aus dem Pfad `/etc/fmdita/dita_resources/DITA-OT.zip` herunter
   + Wenn Sie eine andere Version erhalten möchten, können Sie sie von [dita-to repo](https://www.dita-ot.org/download) herunterladen.
+ Nehmen Sie Änderungen an DITA-OT vor, z. B. das Hinzufügen eines neuen Plug-ins](https://www.dita-ot.org/dev/topics/plugins-installing.html) oder Anpassen vorhandener Plug-ins (siehe Beispiel im Abschnitt zu verwandten Links unten).[
+ Laden Sie `DITA-OT.zip` in `/apps/<project-folder>/dita_resources` hoch (es wird empfohlen, einen benutzerdefinierten Projektordner zu erstellen).
+ Fügen Sie das DITA-Profil über **[!UICONTROL Tools]** > **[!UICONTROL Handbücher]** > **[!UICONTROL DITA-Profile]** hinzu (verwenden Sie den DITA-OT-Pfad, in den das benutzerdefinierte DITA-OT hochgeladen wird, siehe Screenshot unten).
  ![DITA-Profile](assets/dita-profile.png)

>[!MORELIKETHIS]
>
>+ [DITA-OT-Plug-in-Beispiele anpassen](https://www.dita-ot.org/dev/topics/pdf-customization.html)
