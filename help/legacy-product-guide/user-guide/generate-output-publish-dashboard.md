---
title: Verwalten von Veröffentlichungsaufgaben mit dem Dashboard „Veröffentlichen“
description: Verwalten Sie Veröffentlichungsaufgaben mithilfe des Veröffentlichungs-Dashboards in AEM Guides. Wissen, wie man auf das Veröffentlichungs-Dashboard zugreift und eine Veröffentlichungsaufgabe abbricht.
feature: Publishing
role: User
hide: true
exl-id: 9d311979-a7d7-47f5-945c-520eda99798f
source-git-commit: 1426cdaecdd358f06e76908b09330e65997e8452
workflow-type: tm+mt
source-wordcount: '525'
ht-degree: 0%

---

# Verwalten von Veröffentlichungsaufgaben mit dem Dashboard „Veröffentlichen“ {#id205CC08305Z}

Wenn auf Ihrem System eine große Anzahl von Veröffentlichungsaufgaben ausgeführt wird, ist es praktisch unmöglich, jede DITA-Map einzeln zu überprüfen, um die Veröffentlichungsaufgabe zu überwachen. AEM Guides bietet Admins und Herausgebern eine einheitliche Ansicht aller im System ausgeführten Veröffentlichungsaufgaben. Eine Liste aller aktiven Veröffentlichungsaufgaben ist im Veröffentlichungs-Dashboard verfügbar.

Das Veröffentlichungs-Dashboard bietet einen vollständigen Überblick über alle Veröffentlichungsaufgaben, die derzeit im System ausgeführt werden.

![](images/publish-dashboard.png){width="800" align="left"}

Das Veröffentlichungs-Dashboard enthält die folgenden Details:

- **Zuordnungstitel** - Der Titel einer Zuordnungsdatei, die derzeit veröffentlicht wird oder sich in der Veröffentlichungswarteschlange befindet.

- **Dateiname** - Der Dateiname der DITA-Zuordnung.

- **Ausgabevorgabe** - Name der Ausgabevorgabe, die zum Generieren der Ausgabe verwendet wird.

- **Initiiert von** - Benutzername der Person, die die Veröffentlichungsaufgabe initiiert hat.

- **Gestartet am** - Datum und Uhrzeit des Starts der Veröffentlichungsaufgabe.

- **Verstrichene Zeit** Zeit seit der Ausführung der Veröffentlichungsaufgabe im System.

- **Löschsymbol** - Abbrechen oder Beenden einer Veröffentlichungsaufgabe.

Das linke Bedienfeld im Veröffentlichungs-Dashboard bietet die folgenden Filteroptionen:

- **Ausgabevorgabe** - Wählen Sie eine oder mehrere Ausgabevorgaben aus, für die Sie die derzeit aktiven Veröffentlichungsaufgaben anzeigen möchten. Im folgenden Screenshot werden die Veröffentlichungsaufgaben gefiltert, um nur die Aufgaben anzuzeigen, die die Ausgabevorgabe der AEM-Site verwenden:

  ![](images/publish-dashboard-preset-filter.png){width="800" align="left"}

- **Initiiert von** - Wählen Sie einen Benutzernamen aus der Liste aus, um die Veröffentlichungsaufgaben anzuzeigen, die vom ausgewählten Benutzer initiiert wurden.

- **Map** - Wählen Sie in der Liste eine Zuordnungsdatei aus, um die Veröffentlichungsaufgaben anzuzeigen, die für die ausgewählte Zuordnung ausgeführt werden.

## Zugriff auf das Veröffentlichungs-Dashboard {#id205CC100DY4}

Führen Sie die folgenden Schritte aus, um auf das Dashboard „Veröffentlichen“ zuzugreifen:

>[!NOTE]
>
> Nur ein Administrator oder Herausgeber kann auf das Dashboard „Veröffentlichen“ zugreifen.

1. Klicken Sie oben auf den Adobe Experience Manager-Link und wählen Sie **Tools** aus.

1. Wählen Sie **Guides** aus der Liste der Tools aus.

1. Klicken Sie auf die Kachel **Dashboard veröffentlichen**.

   Das Veröffentlichungs-Dashboard wird mit einer Liste aller aktiven Veröffentlichungsaufgaben im System geöffnet.

   Wenn Sie auf den Dateinamen-Link klicken, wird die DITA-Zuordnungskonsole der ausgewählten Zuordnung angezeigt.

   ![](images/publish-dashboard-click-filename-link.png){width="800" align="left"}


>[!NOTE]
>
> Sie können auf das Dashboard Veröffentlichen auch über die Registerkarte Ausgaben zugreifen, während Sie im Dashboard Zuordnung eine Ausgabe generieren. Weitere Informationen finden Sie unter [Anzeigen des Status der Aufgabe zur Ausgabenerstellung](generate-output-for-a-dita-map.md#viewing_output_history).

## Abbrechen einer Veröffentlichungsaufgabe

Führen Sie die folgenden Schritte aus, um eine Aufgabe zur Ausgabegenerierung über das Veröffentlichungs-Dashboard abzubrechen:

1. [Zugriff auf das Veröffentlichungs-Dashboard](#id205CC100DY4).

1. Klicken Sie in der Liste der aktiven Veröffentlichungsaufgaben auf das Löschsymbol einer Aufgabe, die Sie abbrechen möchten.

   ![](images/publish-dashboard-cancel-task.png){width="800" align="left"}

1. Klicken Sie **der** Abbruchmeldung bestätigen auf „Ja“.

   Der Abbruchsbefehl wird akzeptiert, und der Abbruch wird versucht, solange die Aufgabe aktiv bleibt. Nachdem die Aufgabe erfolgreich beendet wurde, wird sie aus der aktuell aktiven Aufgabenliste entfernt. Der Status der Aufgabe wird auch in der DITA Map-Konsole als Abgebrochen aktualisiert. Im folgenden Screenshot wird die Aufgabe *HTML5* über das Veröffentlichungs-Dashboard abgebrochen, und ihr Status wird auch in der DITA-Zuordnungskonsole geändert.

   ![](images/cancelled-output-task.png){width="800" align="left"}


**Übergeordnetes Thema:**[ Ausgabegenerierung](generate-output.md)
