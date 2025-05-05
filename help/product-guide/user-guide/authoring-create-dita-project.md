---
title: Erstellen eines DITA-Projekts
description: Erstellen Sie ein DITA-Projekt mithilfe einer Vorlage in AEM Guides. Erfahren Sie, wie Sie mit einem DITA-Projekt die Überprüfungen einleiten können.
exl-id: 0cd83fe3-1764-4f04-ae11-0b71b6ac576c
feature: Reviewing
role: User
source-git-commit: ae36a7fdff6ae147619340aa3a3d2bb6c7774fe0
workflow-type: tm+mt
source-wordcount: '468'
ht-degree: 0%

---

# Erstellen eines DITA-Projekts {#id1645HA00NM6}

Adobe Experience Manager Guides bietet eine DITA-Projektvorlage, mit der Sie Ihre Prüfungsaufgaben erstellen und verwalten können.

Sie können ein DITA-Projekt erstellen und es dann verwenden, um Ihre Überprüfungen einzuleiten. Mit einem Projekt können Sie einen Termin definieren und die Aufgaben und die Zeit steuern, die zum Abschließen der Prüfungsaufgabe erforderlich sind, für die Sie das Projekt erstellt haben.

Sie können Team-Mitglieder zu einem Projekt hinzufügen, denen dann verschiedene Rollen zugewiesen werden können - Autoren, Prüfer und Herausgeber.

Nachdem Sie Ihr DITA-Projekt erstellt haben, können Sie Ihre Überprüfung über den Editor oder die Assets-Benutzeroberfläche starten. Weitere Informationen finden Sie unter [Themen zur Überprüfung senden](review-send-topics-for-review.md#).

Wenn ein Autor einen Prüfungs-Workflow initiiert, erhalten die ausgewählten Mitglieder des Projekts ebenfalls eine E-Mail-Benachrichtigung. Um E-Mail-Benachrichtigungen zu konfigurieren, zeigen Sie *E-Mail-Vorlagen anpassen* unter Installieren und Konfigurieren von Adobe Experience Manager Guides as a Cloud Service an.

Führen Sie die folgenden Schritte aus, um ein DITA-Projekt zu erstellen:

1. Öffnen Sie die Projektekonsole.

   Sie können über die folgende URL auch auf die Projektekonsole zugreifen:

   ```http
   http://<server name>:<port>/projects.html
   ```

1. Wählen Sie **Erstellen** \> **Projekt**, um den Assistenten zum Erstellen eines Projekts zu starten.

   ![](images/project-console-63.png){width="650" align="left"}

1. Wählen Sie auf der Seite Projekt erstellen die Vorlage **DITA-Projekt** und klicken Sie auf **Weiter**.

1. Geben Sie auf der Seite Projekteigenschaften die folgenden Details ein:

   Informationen auf der Registerkarte **Standard**:

   ![](images/create-project.png){width="650" align="left"}

   - Geben Sie den **(Titel**, **Beschreibung** und **Fälligkeitsdatum** ein.

   - Sie können optional eine Miniaturansicht für das Projekt auswählen.

   - Standardmäßig werden Sie zum Besitzer des Projekts gemacht. So fügen Sie diesem Projekt weitere Benutzer hinzu:

   1. Geben Sie einen Benutzer aus der Dropdown-Liste **Benutzer** ein oder wählen Sie einen aus.

   1. Wählen Sie einen Benutzertyp aus: Autoren, Prüfer oder Herausgeber.

      >[!NOTE]
      >
      >In dieser Dropdown-Liste werden andere Benutzertypen angezeigt. Bei einem DITA-Projekt sollten Sie jedoch nur aus den Benutzertypen „Autoren“, „Prüfer“ oder „Herausgeber“ auswählen. Selbst wenn Sie Benutzende eines anderen Typs hinzufügen, können diese nicht auf DITA-spezifische Funktionen zugreifen, die in Experience Manager Guides verfügbar sind.

   1. Wählen Sie **Hinzufügen** aus.

      >[!NOTE]
      >
      >Wenn Sie Experience Manager Guides Version 3.5 oder früher verwenden, wird eine Option zur Auswahl einer DITA-Zuordnungsdatei angezeigt, um die wichtigsten Verweise für Themenbearbeitung, Vorschau und Überprüfungs-Workflows aufzulösen. In Version 3.6 und höheren Versionen können Sie die Stammzuordnung über den Editor festlegen. Weitere Informationen finden Sie unter [ im ](web-editor-features.md#id2087G0P40SB). Eine andere Möglichkeit, die Stammzuordnung festzulegen, besteht darin, sie auf globaler oder Ordnerebene zu konfigurieren. Weitere Informationen finden Sie *Konfigurieren von globalen Profilen oder Profilen auf*) im Installations- und Konfigurationshandbuch.

   Informationen auf der Registerkarte **Erweitert**:

   - Geben Sie einen Namen für das Projekt ein. Dieser Name wird verwendet, um die URL für dieses Projekt zu erstellen.

1. Wählen Sie **Erstellen** aus.

   Das Dialogfeld Projekt erstellt wird angezeigt.

1. Wählen Sie **Öffnen** aus, um Ihre Projektseite zu öffnen.


**Übergeordnetes Thema:**&#x200B;[ Einführung zur Überprüfung](review.md)
