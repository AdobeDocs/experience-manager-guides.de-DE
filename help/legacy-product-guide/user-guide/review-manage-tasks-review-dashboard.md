---
title: Verwalten von Prüfungsaufgaben mithilfe des Überprüfungs-Dashboards
description: Verwalten Sie Prüfungsaufgaben über das Dashboard "Überprüfen"in AEM Guides. Erfahren Sie mehr über die durchgeführten Aktionen auf der Registerkarte "Aufgabe", "Inhalt", "Überprüfer"und überprüfen Sie den Status einer Prüfungsaufgabe.
feature: Reviewing
role: User
source-git-commit: fa07db6a9cb8d8f5b133258acd5647631b22e28a
workflow-type: tm+mt
source-wordcount: '1300'
ht-degree: 0%

---

# Verwalten von Prüfungsaufgaben mithilfe des Überprüfungs-Dashboards {#id2056B0Y70X4}

Der Workflow zur Verwaltung von Überprüfungen kann eine Vielzahl von Aufgaben umfassen. Sie können beispielsweise Prüfer für ein bestimmtes Thema hinzufügen oder die Frist für eine Überprüfung verlängern. Sie können die Prüfungsaufgabe auch als abgeschlossen kennzeichnen, wenn Sie der Meinung sind, dass alle Beteiligten ihre Meinung dazu geäußert haben. Diese Aufgaben können über das Dashboard &quot;Überprüfen&quot;verwaltet werden.

Führen Sie die folgenden Schritte aus, um auf das Überprüfungs-Dashboard zuzugreifen und es zu verwenden:

>[!NOTE]
>
> Sie können Prüfungsaufgaben nur für die Projekte verwalten, für die Sie der Autor sind \(oder Initiator\). Selbst wenn Sie Überprüfer oder Herausgeber sind \(Benutzer\), haben Sie keinen Zugriff auf eine der Projektaufgaben.

1. Klicken Sie in der Konsole **Projekte** auf das Überprüfungsprojekt, das Sie verwalten möchten.

   Ein Projektbereich mit Aufgabenkacheln wird angezeigt.

   ![](images/review-management.png){width="800" align="left"}

1. Klicken Sie auf die drei Punkte in der Kachel **Bewertungen**.

   Das Überprüfungs-Dashboard wird angezeigt. Im Dashboard werden alle von Ihnen erstellten Prüfungsaufgaben aufgelistet.

   ![](images/review-dashboard.png){width="800" align="left"}

   Im Dashboard &quot;Überprüfen&quot;werden die Details zur Prüfungsaufgabe angezeigt, z. B. der Aufgabenname, der Benutzer, der die Überprüfung gestartet hat, das Datum, an dem die Überprüfung gestartet wurde, das Fälligkeitsdatum, der Status, die Anzahl neuer Kommentare, die vom Autor nicht akzeptiert oder abgelehnt wurden, und der Name der Überprüfer. Die Aufgaben werden in der Reihenfolge der neu erstellten Aufgaben zu älteren Aufgaben aufgelistet.

   >[!NOTE]
   >
   > Wenn Sie auf den Link Prüfungsaufgabe klicken, wird das Thema oder die Zuordnungsdatei, die zur Überprüfung gesendet wird, geöffnet.

1. Wählen Sie eine Prüfungsaufgabe aus.

   In der Symbolleiste werden die Optionen Eigenschaften bearbeiten und [Status](#check-review-status-id199RF0A0UHS) angezeigt.

1. Wenn Sie auf **Eigenschaften bearbeiten** klicken, wird die Seite &quot;Aufgabendetails&quot;angezeigt.

   Auf der Seite &quot;Aufgabendetails&quot;gibt es drei Registerkarten: &quot;Aufgabe&quot;, &quot;Inhalt&quot;und &quot;Prüfer&quot;. In den folgenden Abschnitten werden die verschiedenen Funktionen beschrieben, die auf den einzelnen Registerkarten verfügbar sind.


## Registerkarte &quot;Aufgabe&quot;

![](images/review-task-page.png){width="800" align="left"}

Sie können die folgenden Aktionen auf der Registerkarte **Aufgabe** ausführen:

- Ändern Sie den Titel der Aufgabe im Feld **Titel** .
- Fügen Sie in der Dropdownliste **Zuweisen zu** Standardzuweisungen hinzu. Die von Ihnen hinzugefügten validierungsverantwortlichen Benutzer erhalten Zugriff auf die Überprüfung aller Themen, die Teil dieser Prüfungsaufgabe sind. Sie können auf der Registerkarte [Validierer](#reviewer-tab-id199RF0N0MUI) festlegen, ob weitere Validierer für bestimmte Themen entfernt oder selektiv hinzugefügt werden sollen.
- Aktualisieren Sie die Beschreibung der Aufgabe im Feld **Beschreibung** .
- Ändern Sie das **Fälligkeitsdatum**. Sie können den Termin für den Abschluss der Aufgabe vorbereiten oder verschieben.
- Wählen Sie die Option aus, um Benutzer auf die Themen zu beschränken, die ihnen zugewiesen sind.
- Klicken Sie auf **Aktualisieren** , um die geänderten Details zu aktualisieren.
- Klicken Sie auf **Fertig stellen** , um die Prüfungsaufgabe vor dem Fälligkeitsdatum als abgeschlossen zu markieren. Wenn die Aufgabe eines einzelnen Themas als abgeschlossen markiert ist, wird die Überprüfung des ausgewählten Themas geschlossen. Bei Themen, die über eine DITA-Zuordnung zur Überprüfung freigegeben werden, schließt die Kennzeichnung der DITA-Map-Aufgabe als &quot;Complete&quot;jedoch die Überprüfung aller Themen in der Map, die zur Überprüfung freigegeben wurden.
- Klicken Sie auf **Duplizieren** , um eine Kopie der Prüfungsaufgabe zu erstellen. Das Erstellen einer doppelten Prüfungsaufgabe verläuft ähnlich wie das Erstellen einer neuen Prüfungsaufgabe. Nachdem Sie den Workflow für die doppelte Aufgabe gestartet haben, wird Ihnen die Seite Prüfungsaufgabe erstellen angezeigt. Sie müssen die neuen Aufgabendetails angeben, wie unter [Themen zur Überprüfung senden](review-send-topics-for-review.md#) beschrieben.

  Wenn Sie eine Prüfungsaufgabe ausgewählt haben, die aus einer DITA-Zuordnung erstellt wurde, werden Ihnen die Themen angezeigt, die Teil der Zuordnung sind. Anschließend können Sie die Themen auswählen, die Sie in die neue Prüfungsaufgabe aufnehmen möchten.

  Wenn eine Prüfungsaufgabe aus einer oder mehreren Themenüberprüfungen dupliziert wird, werden nur diese Themen in der Liste der Prüfungsaufgaben angezeigt. Sie können diese Themen für eine Überprüfung mit einer anderen Gruppe von Validierern freigeben.

- Klicken Sie auf **Schließen** , um zur Seite &quot;Posteingang&quot;zu wechseln.

## Registerkarte &quot;Inhalt&quot;

![](images/review-content-page.png){width="800" align="left"}

Sie können die folgenden Aktionen auf der Registerkarte **Inhalt** ausführen:

- Ändern Sie die Version des Themas, das zur Überprüfung gesendet wird. Sie können die neueste Version des Themas, Version als Datum, Version mit einer bestimmten Bezeichnung oder Version mit einer bestimmten Grundlinie auswählen \(für eine DITA-Zuordnung\).

- Klicken Sie auf **Aktualisieren** , um die aktualisierte Version des Themas für die Prüfer freizugeben. Die validierungsverantwortlichen Benutzer erhalten eine E-Mail-Benachrichtigung, dass die neuere Version des Themas zur Überprüfung gesendet wurde. Wenn ein Prüfer das Thema das nächste Mal öffnet, wird ihm die aktualisierte Version des Themas angezeigt.

  >[!NOTE]
  >
  > Bei einer aktualisierten Version eines Themas werden die alten Kommentare auch in der neueren Version beibehalten. Überprüfer können auch die Unterschiede zwischen den beiden Versionen sehen.

- Klicken Sie auf **Fertig stellen** , um die Prüfungsaufgabe vor dem Fälligkeitsdatum als abgeschlossen zu markieren. Wenn die Aufgabe eines einzelnen Themas als abgeschlossen markiert ist, wird die Überprüfung des ausgewählten Themas geschlossen. Bei Themen, die über eine DITA-Zuordnung zur Überprüfung freigegeben werden, schließt die Kennzeichnung der DITA-Map-Aufgabe als &quot;Complete&quot;jedoch die Überprüfung aller Themen in der Map, die zur Überprüfung freigegeben wurden.

- Klicken Sie auf **Duplizieren** , um eine neue Prüfungsaufgabe zu erstellen, die die aktuelle Aufgabe als Basis verwendet.


## Registerkarte &quot;Validierer&quot; {#reviewer-tab-id199RF0N0MUI}

![](images/reviewers-tab.png){width="800" align="left"}

Sie können die folgenden Aktionen auf der Registerkarte **Überprüfer** durchführen:

- **Alle auswählen**: Wählt alle Themen in der Themenliste aus. Nach Auswahl aller Themen können Sie einfach einen Batch-Vorgang ausführen.
- **Auswahl löschen**: Hebt die Auswahl der in der Themenliste ausgewählten Themen auf.

  >[!NOTE]
  >
  > Sie können ein Thema auch einzeln auswählen oder deaktivieren, indem Sie auf das Kontrollkästchen neben dem Thema klicken.

- **Hinzufügen**: Zeigt das Dialogfeld &quot;Überprüfer hinzufügen&quot;an. Sie können den Namen eines Validierers oder einer Benutzerrolle \(oder Gruppe\) eingeben, den Sie als Validierer zu den ausgewählten Themen hinzufügen möchten.
- **Entfernen**: Zeigt das Dialogfeld &quot;Überprüfer entfernen&quot;an. Sie können den Namen eines Validierers oder einer Benutzerrolle \(oder Gruppe\) eingeben, den Sie als Validierer aus den ausgewählten Themen entfernen möchten.
- **Neu zuweisen**: Zeigt das Dialogfeld &quot;Überprüfer erneut zuweisen&quot;an. Sie können den Namen eines Validierers oder einer Benutzerrolle eingeben \(oder Gruppe\), dem Sie die Prüfungsaufgabe zuweisen möchten. Dadurch werden alle vorhandenen Prüfer aus den ausgewählten Themen entfernt und die neu ausgewählten Prüfer diesen Themen zugewiesen.
- **Exportieren**: Ermöglicht den Export der Details der Prüfungsaufgabe in eine CSV-Datei. Die Datei enthält Details wie den Pfad und Titel des Themas, den Namen des Prüfers und die Version der Themen, die zur Überprüfung gesendet werden.
- **Überprüfer bearbeiten**: Durch Klicken auf das Symbol ![](images/edit_pencil_icon.svg) in der Themenliste wird das Dialogfeld &quot;Überprüfer bearbeiten&quot;angezeigt. Sie können Überprüfer für das ausgewählte Thema in diesem Dialogfeld hinzufügen oder entfernen.

## Überprüfen des Status einer Prüfungsaufgabe {#check-review-status-id199RF0A0UHS}

Wenn Sie auf der Hauptseite des Überprüfungs-Dashboards eine Prüfungsaufgabe auswählen und auf **Status** klicken, wird der Statusbericht der Prüfungsaufgabe angezeigt:

![](images/review-status-report.png){width="800" align="left"}

Der Statusbericht für die Prüfungsaufgabe enthält die folgenden Details:

- Name\(n\) des Validierers, dem die Prüfungsaufgabe zugewiesen ist.
- Die Spalte Status gibt den Prüfungsstatus an. Der Status kann einer der folgenden sein:
   - **Nicht gestartet**: Der Überprüfer hat den Überprüfungslink noch nicht geöffnet.
   - **Wird ausgeführt**: Der Überprüfer hat den Überprüfungslink geöffnet und befindet sich im Review-Verfahren zum Thema.
   - **Abgeschlossen**: Der Überprüfer hat die Überprüfung abgeschlossen, indem er die ihm zugewiesene Prüfungsaufgabe abgeschlossen hat. Die Überprüfungsaufgabe befindet sich für jeden Überprüfer im Posteingang für AEM Benachrichtigungen.
- Wenn ein Überprüfer einen Überprüfungslink öffnet und zu einem bestimmten Thema navigiert, wird dieses Thema zur Liste &quot;Geprüft&quot;hinzugefügt. Dies hilft Autoren dabei festzustellen, ob die validierungsverantwortlichen Benutzer ihre jeweiligen Abschnitte geöffnet haben oder nicht. Wenn Kommentare abgegeben werden, werden diese in Klammern angezeigt.
- Gesamtzahl der Kommentare zu allen Themen. Bei mehreren Themen, die geprüft werden, wird die Anzahl der Kommentare zu den einzelnen Themen \(in Klammern\) in Bezug auf den Themennamen angegeben.
- Das Datum, an dem der Validierer zuletzt auf ein Thema zugegriffen hat.

**Übergeordnetes Thema:**[ Themen oder Zuordnungen überprüfen](review.md)
