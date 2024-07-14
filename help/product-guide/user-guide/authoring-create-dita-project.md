---
title: Erstellen eines DITA-Projekts
description: Erstellen Sie ein DITA-Projekt mit einer Vorlage in AEM Guides. Erfahren Sie, wie Sie mit einem DITA-Projekt die Überprüfungen starten können.
exl-id: 0cd83fe3-1764-4f04-ae11-0b71b6ac576c
feature: Reviewing
role: User
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '468'
ht-degree: 0%

---

# Erstellen eines DITA-Projekts {#id1645HA00NM6}

AEM Guides bietet eine DITA-Projektvorlage, mit der Sie Ihre Prüfungsaufgaben erstellen und verwalten können.

Sie können ein DITA-Projekt erstellen und es dann verwenden, um Ihre Überprüfungen zu initiieren. Mit einem Projekt können Sie einen Termin festlegen und die Aufgaben und die Zeit steuern, die zum Abschließen der Prüfungsaufgabe erforderlich sind, für die Sie das Projekt erstellt haben.

Sie können Team-Mitglieder zu einem Projekt hinzufügen, denen dann verschiedene Rollen zugewiesen werden können - Autoren, Prüfer und Herausgeber.

Nachdem Sie Ihr DITA-Projekt erstellt haben, können Sie Ihre Überprüfung über den Web Editor oder die Assets-Benutzeroberfläche starten. Weitere Informationen finden Sie unter [Themen zur Überprüfung senden](review-send-topics-for-review.md#).

Wenn ein Autor einen Überprüfungs-Workflow initiiert, erhalten die ausgewählten Mitglieder des Projekts eine E-Mail-Benachrichtigung. Informationen zum Konfigurieren von E-Mail-Benachrichtigungen finden Sie unter *E-Mail-Vorlagen anpassen* in Installieren und Konfigurieren von Adobe Experience Manager Guides as a Cloud Service.

Führen Sie die folgenden Schritte aus, um ein DITA-Projekt zu erstellen:

1. Öffnen Sie die Projektekonsole.

   Sie können auch über die folgende URL auf die Projektekonsole zugreifen:

   ```http
   http://<server name>:<port>/projects.html
   ```

1. Klicken Sie auf **Erstellen** \> **Projekt** , um den Assistenten Projekt erstellen zu starten.

   ![](images/project-console-63.png){width="650" align="left"}

1. Wählen Sie auf der Seite Projekt erstellen die Vorlage **DITA-Projekt** aus und klicken Sie auf **Weiter**.

1. Geben Sie auf der Seite &quot;Projekteigenschaften&quot;die folgenden Details ein:

   Informationen auf der Registerkarte **Einfach**:

   ![](images/create-project.png){width="650" align="left"}

   - Geben Sie den **Titel**, die **Beschreibung** und das **Fälligkeitsdatum** Ihres Projekts ein.

   - Sie können optional eine Miniaturansicht für das Projekt auswählen.

   - Standardmäßig werden Sie zum Eigentümer des Projekts gemacht. So fügen Sie diesem Projekt weitere Benutzer hinzu:

   1. Geben Sie einen Benutzer in der Dropdownliste **Benutzer** ein oder wählen Sie ihn aus.

   1. Wählen Sie einen Benutzertyp aus: Autoren, Überprüfer oder Herausgeber.

      >[!NOTE]
      >
      >In dieser Dropdownliste werden weitere Benutzertypen angezeigt. Für ein DITA-Projekt sollten Sie jedoch nur den Benutzertyp Autoren, Prüfer oder Herausgeber wählen. Selbst wenn Sie einen Benutzer eines anderen Typs hinzufügen, kann dieser Benutzer nicht auf DITA-spezifische Funktionen zugreifen, die in AEM Guides verfügbar sind.

   1. Klicken Sie auf **Hinzufügen**.

      >[!NOTE]
      >
      >Wenn Sie AEM Guides Version 3.5 oder früher verwenden, wird Ihnen eine Option angezeigt, eine DITA-Map-Datei auszuwählen, um wichtige Verweise für Themenbearbeitung, Vorschau und Review-Workflows aufzulösen. In Version 3.6 und höheren Versionen können Sie die Stammzuordnung über den Web-Editor festlegen. Weitere Informationen finden Sie unter [Benutzereinstellungen](web-editor-features.md#id2087G0P40SB) im Web-Editor. Eine weitere Möglichkeit, die Stammzuordnung festzulegen, besteht darin, sie in den Profilen auf globaler Ebene oder auf Ordnerebene zu konfigurieren. Weitere Informationen finden Sie unter *Konfigurieren von globalen Profilen oder Profilen auf Ordnerebene* im Installations- und Konfigurationshandbuch.

   Informationen auf der Registerkarte **Erweitert**:

   - Geben Sie einen Namen für das Projekt ein. Dieser Name wird verwendet, um die URL für dieses Projekt zu erstellen.

1. Klicken Sie auf **Erstellen**.

   Das Dialogfeld Projekt erstellt wird angezeigt.

1. Klicken Sie auf **Öffnen** , um Ihre Projektseite zu öffnen.


**Übergeordnetes Thema:**[ Themen oder Zuordnungen überprüfen](review.md)
