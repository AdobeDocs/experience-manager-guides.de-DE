---
title: Kommentare zur Adressüberprüfung
description: Erfahren Sie, wie Sie in AEM Handbüchern Kommentare zur Überprüfung als Autor bearbeiten können. Hier erfahren Sie, wie Autoren Kommentare in einem Dokument bearbeiten, filtern, akzeptieren oder ablehnen können.
exl-id: 4c969788-f700-4fd6-8afa-8e5b411b59f3
source-git-commit: 5e0584f1bf0216b8b00f00b9fe46fa682c244e08
workflow-type: tm+mt
source-wordcount: '1031'
ht-degree: 0%

---

# Kommentare zur Adressüberprüfung {#id2056B0X0KBI}


Als Autor können Sie mit dem Web Editor Kommentare in einem Thema bearbeiten. Die Kommentare werden basierend auf der Überprüfungsaufgabe geladen, die im Überprüfungsbereich ausgewählt wurde. Weitere Informationen finden Sie unter **Überprüfen** panel ![](images/active-review-tasklist-icon.svg) Funktionsbeschreibung in [Linke Leiste](../user-guide/web-editor-features.md#id2051EA0M0HS) Abschnitt.

In den folgenden Abschnitten werden die Möglichkeiten zum Bearbeiten von Kommentaren im Web Editor beschrieben.

Ein Autor kann Kommentare in einem Dokument vom Web-Editor aus bearbeiten. Visuelle Indikatoren geben an, ob Kommentare eingefügt, \(Text\), gelöscht oder hervorgehoben wurden. Auch die Art des Kommentars wird oben in jedem Kommentar-Eintrag erwähnt.

>[!NOTE]
>
> Stellen Sie bei der Behandlung von Überprüfungskommentaren \(für ein aktives Überprüfungsdokument\) sicher, dass Sie - das Thema im Review nicht auf mehreren Registerkarten öffnen, bei dem die vollständige Tag-Ansicht aktiviert ist - nicht zwischen den Ansichtsmodi Autor und Quelle wechseln.

![](images/comments-page-web-editor_cs.png){width="800" align="left"}

Im Web-Editor-Modus enthält der rechte Bereich die Symbole Überprüfung und Getrackte Änderungen . Im Prüfungsbereich werden alle Kommentare angezeigt, die von den Validierern in Ihrem Dokument abgegeben wurden. Die **Getrackte Änderungen** zeigt den Status aller eingefügten und gelöschten Kommentare in Ihrem Dokument an.

- **A**: Wählen Sie eine Prüfungsaufgabe aus, um Überprüfungskommentare anzuzeigen. Wenn Ihr Thema für die Überprüfung in mehreren Prüfungsaufgaben freigegeben wurde, werden diese Aufgaben in dieser Dropdown-Liste aufgeführt.

  Wenn Sie eine Prüfungsaufgabe aus der Liste auswählen, werden die Kommentare der Prüfer in dieser Aufgabe angezeigt. Sie können die Überprüfungskommentare unabhängig in Aufgaben behandeln, was bedeutet, dass nur validierende Benutzer der jeweiligen Aufgabe auf jede Aktualisierung eines Kommentars zugreifen können.

- **B:**  Auswählen **Details überprüfen** ![](images/active-review-info-icon.svg) im **Kommentare** um weitere Informationen zur Prüfungsaufgabe anzuzeigen:

   - **Name**: Name der Prüfungsaufgabe .
   - **Version überprüfen**: Zeigt die Version an, die der ausgewählten Prüfungsaufgabe zugeordnet ist. Auf diese Weise können Sie die Version, die Sie für die Überprüfung freigegeben haben, verfolgen
   - **Status**: Aktueller Status der Prüfungsaufgabe.

  >[!NOTE]
  >
  > Wenn sich die Stammzuordnung Ihrer Prüfungsaufgabe von der Stammzuordnung für die Bearbeitung unterscheidet, werden die entsprechenden Informationen angezeigt, um anzugeben, dass die Autorenzuordnung und die Reviewstammzuordnung nicht übereinstimmen.

- **C**: Wenn Sie Ihr Thema nach dem Initiieren des Reviews aktualisiert haben und dann auf das Symbol Thema zur Review-Version zurücksetzen klicken, wird Ihre Arbeitskopie wieder auf die Version zurückgesetzt, die für die Überprüfung freigegeben wurde. Dies erleichtert es Ihnen, das Feedback zur Überprüfung direkt in die zur Überprüfung freigegebene Version zu integrieren. Nachdem Sie das Feedback integriert haben, können Sie Änderungen in der zurückgegebenen Version speichern oder eine neue Revision Ihres Themas erstellen. Wenn Sie eine neue Revision Ihres Themas erstellen, wird eine neue Verzweigung aus der Themenversion erstellt, die zur Überprüfung freigegeben wurde. Wenn Sie beispielsweise Version freigegeben haben `1.2` eines Themas zur Überprüfung, während die aktuelle Authoring-Version `1.3`können Sie dieses Symbol verwenden, um zurück zur Version zu wechseln. `1.2` für die Aufnahme von Überprüfungskommentaren. Wenn Sie eine neue Revision erstellen, nachdem Sie Änderungen an der Version übernommen haben `1.2`, dann eine neue Verzweigung mit Version `1.2.0` für das Thema erstellt.

  Nach der Integration von Review-Feedback möchten Sie in der Regel Änderungen aus der neuesten Version des Themas zusammenführen. Verwenden Sie dazu die [Zusammenführen](web-editor-features.md#id205DF04E0HS) , um alle Aktualisierungen abzurufen, die vorgenommen wurden, nachdem das Thema zur Überprüfung freigegeben wurde.

- **D**: Öffnen Sie die Ansicht nebeneinander, um die kommentierte Version des Themas anzuzeigen. Wie im obigen Screenshot gezeigt, ist der ganz links liegende Abschnitt die neueste Version des Themas, in dem Sie Änderungen vornehmen können. Im nächsten Abschnitt finden Sie die kommentierte Version des Themas. Wenn Sie zwischen Kommentaren im Thema navigieren, ändert sich die Seitenansicht und zeigt die Version des Themas an, zu dem der Kommentar abgegeben wurde. Jeder Kommentar im Kommentarbereich ist mit dem entsprechenden Text in diesem Abschnitt verknüpft. Sie können damit den kommentierten Text identifizieren. Die Kommentare werden in der Reihenfolge des kommentierten Texts im Dokument angezeigt.

  Sie können die Versionsnummer oben in der Seitenansicht sehen. Wenn Sie erneut auf dieses Symbol klicken, wird die kommentierte Version des Themas ausgeblendet.

- E: Importieren Sie die eingefügten und gelöschten \(oder Durchstreichen\) Kommentare direkt in das Thema. Nachdem Sie auf das Symbol &quot;Importieren&quot;geklickt haben, werden in der Arbeitskopie des Themas alle Einfügungen und Löschungen von Text angezeigt. Jetzt gibt es zwei Möglichkeiten, Kommentare zu akzeptieren oder abzulehnen.

  Wenn Sie die vorgeschlagene Änderung \(Einfügung oder Löschung\) einzeln einbeziehen möchten, klicken Sie einfach mit der rechten Maustaste auf den Kommentar im Inhalt und wählen Sie &quot;Änderung akzeptieren&quot;oder &quot;Änderung ablehnen&quot;. Je nach Auswahl wird der Kommentar akzeptiert oder abgelehnt. Im Falle eines akzeptierten Kommentars wird der Inhalt in den Inhalt eingefügt und im Fall einer Ablehnung wird er aus dem Inhalt entfernt. Außerdem wird der Status des Kommentars im Überprüfungsfenster geändert.

  ![](images/import-comment-accept-web-editor_cs.png){width="800" align="left"}

  Sie können auch die Überprüfungsfunktion im rechten Bereich verwenden, um Kommentare zu akzeptieren oder abzulehnen. Wenn Sie auf einen Kommentar klicken, wird der Kommentar im Dokument hervorgehoben.

  ![](images/changes-tab_cs.png){width="800" align="left"}

  >[!IMPORTANT]
  >
  > Die Funktion &quot;Kommentare importieren&quot;funktioniert nur für Dokumente, die sich seit ihrer Freigabe für die Überprüfung nicht geändert haben. Wenn Sie Änderungen vorgenommen haben, nachdem Sie das Dokument zur Überprüfung gesendet haben, erhalten Sie eine Warnung an **Import erzwingen** Kommentare in Ihr Dokument. Dies führt jedoch zum Verlust aller Aktualisierungen, die Sie in Ihrem Dokument vorgenommen haben. Die **Import erzwingen** wird auch angezeigt, wenn das Dokument außerhalb erstellt und dann zur Überprüfung freigegeben wird. Sie können nun die Kommentare importieren.

  Wenn Sie einen Kommentar akzeptieren oder ablehnen, wird er aus der Liste Getrackte Änderungen entfernt. Dies gibt auch an, wie viele Kommentare in dem Dokument behandelt werden müssen.

- **F**: Laden Sie im Menü Mehr Optionen alle im Prüfungsthema verfügbaren Anlagen herunter.
- **G**: Suchen Sie in den Kommentaren nach einem Text.
- **H**: Akzeptieren oder lehnen Sie einen Kommentar ab.

- **I**: Wenden Sie einen Filter auf die Kommentare an. Sie können nach Kommentaren filtern, indem Sie sie auf der Grundlage von Überprüfungstyp \(alle, hervorgehoben, gelöscht, eingefügt oder Kurznotiz\), Überprüfungsstatus \(alle, akzeptiert, abgelehnt oder keine\), Überprüfern \(alle oder bestimmte Überprüfer\(s\)\) oder Themenversionen anzeigen.


**Übergeordnetes Thema:**[ Themen oder Zuordnungen überprüfen](review.md)
