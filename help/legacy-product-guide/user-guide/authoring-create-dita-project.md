---
title: Erstellen eines DITA-Projekts
description: Create a DITA project using a template in AEM Guides. Learn how to use a DITA project to initiate the reviews.
feature: Reviewing
role: User
hide: true
exl-id: 1b29c50a-04d0-4052-b893-44fb8bcc3c97
source-git-commit: a70b3ce942b3e69445ad1d7ba6c8f7542e0ff176
workflow-type: tm+mt
source-wordcount: '472'
ht-degree: 0%

---

# Erstellen eines DITA-Projekts {#id1645HA00NM6}

AEM Guides provides a DITA project template that you can use to create and manage your review tasks.

You can create a DITA project and then use it to initiate your reviews. A project lets you define a deadline and control the tasks and time required to complete the review task for which you have created the project.

You can add team members to a project who could then be assigned various roles – Authors, Reviewers, and Publishers.

Once you have created your DITA project, you can initiate your review from the Web Editor or the Assets UI. For more details, see [Send topics for review](review-send-topics-for-review.md#).

Similarly, whenever an author initiates any review workflow the selected members of the project get an email notification. To configure email notifications, see *Customize email templates* in Install and configure Adobe Experience Manager Guides as a Cloud Service.

Perform the following steps to create a DITA project:

1. Open Projects console.

   You can also access the Projects console using the following URL:

   ```http
   http://<server name>:<port>/projects.html
   ```

1. Click **Create** \> **Project** to launch the Create Project wizard.

   ![](images/project-console-63.png){width="650" align="left"}

1. On the Create Project page, select the **DITA Project** template and click **Next**.

1. On the Project Properties page, enter the following details:

   Information in the **Basic** tab:

   ![](images/create-project.png){width="650" align="left"}

   - Enter your project&#39;s **Title**, **Description**, and **Due Date**.

   - You can, optionally, choose a thumbnail for the project.

   - By default, you are made the owner of the project. To add more users to this project:

   1. Enter or choose a user from the **User** drop-down list.

   1. Choose a user type - Authors, Reviewers, or Publishers.

      >[!NOTE]
      >
      >In dieser Dropdown-Liste werden andere Benutzertypen angezeigt. Bei einem DITA-Projekt sollten Sie jedoch nur aus den Benutzertypen „Autoren“, „Prüfer“ oder „Herausgeber“ auswählen. Selbst wenn Sie Benutzende eines anderen Typs hinzufügen, können diese nicht auf DITA-spezifische Funktionen zugreifen, die in AEM Guides verfügbar sind.

   1. Klicken Sie auf **Hinzufügen**.

      >[!NOTE]
      >
      >Wenn Sie AEM Guides Version 3.5 oder früher verwenden, wird eine Option zur Auswahl einer DITA-Zuordnungsdatei angezeigt, um die wichtigsten Verweise für Themenbearbeitung, Vorschau und Überprüfungs-Workflows aufzulösen. In 3.6 und höheren Versionen können Sie die Stammzuordnung über den Web-Editor festlegen. Weitere Informationen finden Sie unter [Benutzereinstellungen](web-editor-features.md#id2087G0P40SB) im Web-Editor. Eine andere Möglichkeit, die Stammzuordnung festzulegen, besteht darin, sie auf globaler oder Ordnerebene zu konfigurieren. Weitere Informationen finden Sie unter *Konfigurieren von globalen Profilen oder Profilen auf* im Installations- und Konfigurationshandbuch.

   Informationen auf der Registerkarte **Erweitert**:

   - Geben Sie einen Namen für das Projekt ein. Dieser Name wird verwendet, um die URL für dieses Projekt zu erstellen.

1. Klicken Sie auf **Erstellen**.

   Das Dialogfeld Projekt erstellt wird angezeigt.

1. Klicken Sie **Öffnen**, um Ihre Projektseite zu öffnen.


**Übergeordnetes Thema:**[ Themen oder Karten überprüfen](review.md)
