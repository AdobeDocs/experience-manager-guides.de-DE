---
title: Verwalten von Prüfungsaufgaben mithilfe des Überprüfungs-Dashboards
description: Verwalten Sie Prüfungsaufgaben im Überprüfungs-Dashboard in AEM Guides. Erfahren Sie, wie Sie unter der Registerkarte „Aufgabe, Inhalt, Validierungsverantwortliche“ Aktionen durchführen und den Status einer Prüfungsaufgabe überprüfen können.
exl-id: 4fef5653-1c73-4b68-adf2-b24145555142
feature: Reviewing
role: User
source-git-commit: 19e521ed790a7ac25afab88e8878250f943d9bff
workflow-type: tm+mt
source-wordcount: '1348'
ht-degree: 0%

---

# Verwalten von Prüfungsaufgaben mithilfe des Überprüfungs-Dashboards {#id2056B0Y70X4}

Der Workflow zur Überprüfungsverwaltung kann eine Vielzahl von Aufgaben enthalten. Beispielsweise können Sie Reviewer für ein bestimmtes Thema hinzufügen oder die Frist für eine Überprüfung verlängern. Sie können die Prüfungsaufgabe auch als abgeschlossen markieren, wenn Sie der Meinung sind, dass alle Beteiligten ihr Feedback gegeben haben. Diese Aufgaben können über das Überprüfungs-Dashboard verwaltet werden.

Führen Sie die folgenden Schritte aus, um auf das Überprüfungs-Dashboard zuzugreifen und es zu verwenden:

>[!NOTE]
>
> Prüfungsaufgaben können nur für die Projekte verwaltet werden, für die Sie Autor \(oder Initiator\) sind. Selbst wenn Sie ein Reviewer oder Publisher (Benutzer\) sind, haben Sie keinen Zugriff auf eine der Projektaufgaben.

1. Wählen Sie in **Projekte**-Konsole das Überprüfungsprojekt aus, das Sie verwalten möchten.

   Ein Projektbedienfeld mit Aufgabenkacheln wird angezeigt.

   ![](images/review-management.png){align="left"}

   >[!NOTE]
   >
   > Alternativ können Sie direkt über das linke Bedienfeld des Editors auf das Projekt-Dashboard zugreifen. Öffnen Sie das [Überprüfungsbedienfeld](./web-editor-left-panel.md#review) und verwenden Sie das Symbol **Öffnen des Projekt-Dashboards** , das für jedes im Überprüfungsbedienfeld aufgeführte Überprüfungsprojekt platziert ist.

1. Wählen Sie die drei Punkte in der Kachel **Reviews** aus.

   Das Überprüfungs-Dashboard wird angezeigt. Im Dashboard werden alle von Ihnen erstellten Prüfungsaufgaben aufgelistet.

   ![](images/review-dashboard.png){align="left"}

   Im Überprüfungs-Dashboard werden Details zur Überprüfungsaufgabe angezeigt, z. B. Name der Aufgabe, wer die Überprüfung gestartet hat, Datum, an dem die Überprüfung gestartet wurde, Fälligkeitsdatum, Status, Anzahl neuer Kommentare, die vom Autor nicht akzeptiert oder abgelehnt wurden, und Name der Validierungsverantwortlichen. Die Aufgaben werden in der Reihenfolge der neu erstellten Aufgaben zu den älteren Aufgaben aufgelistet.

   >[!NOTE]
   >
   > Wenn Sie den Link Prüfungsaufgabe auswählen, wird die zur Überprüfung gesendete Themen- oder Zuordnungsdatei geöffnet.

1. Eine Prüfungsaufgabe auswählen.

   In der Symbolleiste werden die Optionen Eigenschaften bearbeiten [Status](#check-review-status-id199RF0A0UHS) angezeigt.

1. Wenn Sie **Eigenschaften bearbeiten** auswählen, wird die Seite „Aufgabendetails“ angezeigt.

   Auf der Seite „Aufgabendetails“ gibt es drei Registerkarten: „Aufgabe“, „Inhalt“ und „Prüfer“. In den folgenden Abschnitten werden die verschiedenen Funktionen erläutert, die auf den einzelnen Registerkarten verfügbar sind.


## Registerkarte „Aufgabe“

![](images/review-task-page.png){align="left"}

Sie können die folgenden Aktionen auf der Registerkarte **Aufgabe** ausführen:

- Ändern Sie den Titel der Aufgabe im Feld **Titel** .
- Fügen Sie Standardbevollmächtigte in der Dropdown **Liste „Zuweisen an** hinzu. Die Reviewer, die Sie von hier hinzufügen, erhalten Zugriff, um alle Themen zu überprüfen, die Teil dieser Prüfungsaufgabe sind. Sie können auf der Registerkarte „Validierungsverantwortliche“ wählen, ob Sie zu bestimmten Themen [ oder selektiv weitere Validierungsverantwortliche ](#reviewer-tab-id199RF0N0MUI).
- Aktualisieren Sie die Beschreibung der Aufgabe im Feld **Beschreibung** .
- Ändern Sie das **Fälligkeitsdatum**. Sie können die Frist für den Abschluss der Aufgabe vorziehen oder verschieben.
- Wählen Sie die Option aus, um Benutzer darauf zu beschränken, nur die Themen anzusehen, die ihnen zugewiesen sind.
- Wählen Sie **Aktualisieren** aus, um die geänderten Details zu aktualisieren.

  Eine Popup-Meldung wird angezeigt, um zu bestätigen, ob die Aktualisierung erfolgreich war oder nicht.
- Wählen Sie **Abschließen**, um die Prüfungsaufgabe als vor dem Fälligkeitsdatum abgeschlossen zu markieren. Wenn die Aufgabe eines einzelnen Themas als Abgeschlossen markiert ist, wird die Überprüfung des ausgewählten Themas abgeschlossen. Bei Themen, die über eine DITA-Zuordnung zur Überprüfung freigegeben wurden, wird durch Markierung der DITA-Zuordnungsaufgabe als abgeschlossen jedoch die Überprüfung aller Themen innerhalb der Zuordnung geschlossen, die zur Überprüfung freigegeben wurden.
- Wählen Sie **Duplizieren**, um eine Kopie der Prüfungsaufgabe zu erstellen. Der Prozess des Erstellens einer doppelten Prüfungsaufgabe ähnelt dem Erstellen einer neuen Prüfungsaufgabe. Nachdem Sie den Workflow für doppelte Aufgaben gestartet haben, wird die Seite Prüfungsaufgabe erstellen angezeigt. Sie müssen die neuen Aufgabendetails angeben, wie unter [Senden von Themen zur Überprüfung](review-send-topics-for-review.md#) beschrieben.

  Wenn Sie eine Prüfungsaufgabe ausgewählt haben, die aus einer DITA-Map erstellt wurde, werden die Themen angezeigt, die Teil der Map sind. Anschließend können Sie die Themen auswählen, die Sie in die neue Prüfungsaufgabe aufnehmen möchten.

  Im Falle einer Prüfungsaufgabe, die aus einem oder mehreren Prüfungsthemen dupliziert wurde, werden nur diese Themen in der Prüfungsaufgabenliste angezeigt. Sie können diese Themen zur Überprüfung für eine andere Gruppe von Validierungsverantwortlichen freigeben.

- Wählen Sie **Schließen** aus, um zur Seite „Posteingang“ zu wechseln.

## Registerkarte „Inhalt“

![](images/review-content-page.png){align="left"}

Sie können die folgenden Aktionen auf der Registerkarte **Inhalt** ausführen:

- Ändern der Version des Themas, das zur Überprüfung gesendet wird. Sie können die neueste Version des Themas, die Version am Datum, die Version mit der spezifischen Beschriftung oder die Version mit der spezifischen Baseline \(für eine DITA-Zuordnung\) auswählen.

- Wählen Sie **Aktualisieren** aus, um die aktualisierte Version des Themas für die Prüfer freizugeben. Die Reviewer erhalten eine E-Mail-Benachrichtigung, in der sie darauf hingewiesen werden, dass die neuere Version des Themas zur Überprüfung versendet wurde. Wenn ein Reviewer das nächste Mal ein Thema öffnet, zeigt er die aktualisierte Version des Themas an.

  >[!NOTE]
  >
  > Bei einer aktualisierten Version eines Themas werden die alten Kommentare auch in der neueren Version beibehalten. Reviewer können außerdem die Unterschiede zwischen den beiden Versionen anzeigen.

- Wählen Sie **Abschließen**, um die Prüfungsaufgabe als vor dem Fälligkeitsdatum abgeschlossen zu markieren. Wenn die Aufgabe eines einzelnen Themas als Abgeschlossen markiert ist, wird die Überprüfung des ausgewählten Themas abgeschlossen. Bei Themen, die über eine DITA-Zuordnung zur Überprüfung freigegeben wurden, wird durch Markierung der DITA-Zuordnungsaufgabe als abgeschlossen jedoch die Überprüfung aller Themen innerhalb der Zuordnung geschlossen, die zur Überprüfung freigegeben wurden.

- Wählen Sie **Duplizieren**, um eine neue Prüfungsaufgabe mit der aktuellen Aufgabe als Basis zu erstellen.


## Registerkarte „Validierungsverantwortliche“ {#reviewer-tab-id199RF0N0MUI}

![](images/reviewers-tab.png){align="left"}

Sie können die folgenden Aktionen auf der Registerkarte **Validierungsverantwortliche** ausführen:

- **Alle auswählen**: Wählt alle Themen in der Themenliste aus. Nach Auswahl aller Themen können Sie ganz einfach einen Batch-Vorgang durchführen.
- **Auswahl aufheben**: Hebt die Auswahl der Themen in der Themenliste auf.

  >[!NOTE]
  >
  > Sie können ein Thema auch einzeln auswählen oder die Auswahl aufheben, indem Sie das Kontrollkästchen neben dem Thema aktivieren.

- **Hinzufügen**: Zeigt das Dialogfeld „Reviewer hinzufügen“ an. Sie können den Namen eines Reviewers oder einer Benutzerrolle \(oder einer Gruppe\) eingeben, den bzw. die Sie als Reviewer zu den ausgewählten Themen hinzufügen möchten.
- **Entfernen**: Zeigt das Dialogfeld „Reviewer entfernen“ an. Sie können den Namen eines Reviewers oder einer Benutzerrolle \(oder einer Gruppe\) eingeben, den bzw. die Sie als Reviewer aus den ausgewählten Themen entfernen möchten.
- **Neu zuweisen**: Zeigt das Dialogfeld „Reviewer neu zuweisen“ an. Sie können den Namen eines Reviewers oder einer Benutzerrolle \(oder einer Gruppe\) eingeben, dem bzw. der die Überprüfungsaufgabe zugewiesen werden soll. Dadurch werden alle vorhandenen Reviewer aus den ausgewählten Themen entfernt und die neu ausgewählten Reviewer diesen Themen zugewiesen.
- **Exportieren**: Ermöglicht den Export der Aufgabendetails für die Überprüfung in eine CSV-Datei. Die Datei enthält Details wie den Pfad und Titel des Themas, den Namen des Reviewers und die Version der Themen, die zur Überprüfung gesendet werden.
- **Reviewer bearbeiten**: Wenn Sie das ![](images/edit_pencil_icon.svg)Symbol in der Themenliste auswählen, wird das Dialogfeld „Reviewer bearbeiten“ angezeigt. Sie können Reviewer für ausgewählte Themen in diesem Dialogfeld hinzufügen oder entfernen.

## Überprüfen des Status einer Prüfungsaufgabe {#check-review-status-id199RF0A0UHS}

Wenn Sie auf der Hauptseite des Überprüfungs-Dashboards eine Überprüfungsaufgabe auswählen und **Status** wählen, wird der Statusbericht der Überprüfungsaufgabe angezeigt.

![](images/review-status-report.png){align="left"}

Der Statusbericht für die Prüfungsaufgabe enthält die folgenden Details:

- Name des Reviewers, dem die Prüfungsaufgabe zugewiesen wurde.
- Die Spalte Status gibt den Prüfungsstatus an. Der Status kann einer der folgenden sein:
   - **Nicht gestartet**: Die Überprüfenden haben den Überprüfungs-Link noch nicht geöffnet.
   - **In Bearbeitung**: Die Überprüfenden haben den Überprüfungs-Link geöffnet und sind dabei, das Thema zu überprüfen.
   - **Abschließen**: Die Überprüfenden haben die Überprüfung abgeschlossen, indem sie die ihnen zugewiesene Überprüfungsaufgabe abgeschlossen haben. Die Überprüfungsaufgabe befindet sich für jeden Reviewer im AEM-Benachrichtigungs-Posteingang.
- Wenn ein Reviewer einen Review-Link öffnet und zu einem bestimmten Thema navigiert, wird dieses der Liste „Überprüfte Themen“ hinzugefügt. Auf diese Weise können Autoren feststellen, ob die Reviewer ihre jeweiligen Abschnitte geöffnet haben. Wenn Kommentare abgegeben werden, werden diese in Klammern angezeigt.
- Gesamtzahl der Kommentare zu allen Themen. Bei mehreren zu überprüfenden Themen wird die Anzahl der Kommentare für jedes Thema \(in Klammern\) gegenüber dem Themennamen angegeben.
- Das Datum, an dem der Reviewer zuletzt auf ein Thema zugegriffen hat.

**Übergeordnetes Thema:**[ Einführung zur Überprüfung](review.md)
