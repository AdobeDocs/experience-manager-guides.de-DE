---
title: Kommentare zur Adressenüberprüfung
description: Learn how to address review comments as an author in AEM Guides. Discover how an author can edit, filter, accept, or reject comments in a document.
feature: Reviewing
role: User
hide: true
exl-id: a9551eb0-ad30-424d-b1c8-c079125d8118
source-git-commit: a70b3ce942b3e69445ad1d7ba6c8f7542e0ff176
workflow-type: tm+mt
source-wordcount: '1036'
ht-degree: 0%

---

# Kommentare zur Adressenüberprüfung {#id2056B0X0KBI}


As an author, you can address comments in a topic using the Web Editor. The comments are loaded based on the review task selected in the Review panel. For more details, view the **Review** panel ![](images/active-review-tasklist-icon.svg) feature description in the [Left Panel](../user-guide/web-editor-features.md#id2051EA0M0HS) section.

The following sections describe ways of editing comments in the Web Editor.

An author can address comments in a document from the Web Editor. Visual indicators are provided indicating whether comments that were inserted \(text\), deleted or highlighted. Also the type of comment is mentioned at the top of every comment entry.

>[!NOTE]
>
> While addressing review comments \(for an active review document\), ensure that you—do not open the in-review topic in multiple tabs with full tags view enabled, do not switch between the Author and Source view modes.

![](images/comments-page-web-editor_cs.png){width="800" align="left"}

In the Web Editor mode, the right panel contains the Review and Tracked Changes icons. The Review panel shows all comments made in your document by reviewers. The **Tracked Changes** panel shows the status of all inserted and deleted comments in your document.

- **A**: Select a review task to see review comments. If your topic has been shared for review in multiple review tasks, you will see those tasks listed in this drop-down.

  When you select a review task from the list, you get to see the comments made by reviewers in that task. You can address the review comments independently in tasks, which mean that any update on a comment is visible to reviewers of that respective task only.

- **B:**  Select **Review details** ![](images/active-review-info-icon.svg) in the **Comments** panel to view more information about the review task:

   - **Name**: Name of the review task .
   - **Review Version**: Dispalys the version associated with the selected review task. This helps you to keep a track of the version that you had shared for review
   - **Status**: Current status of the review task.

  >[!NOTE]
  >
  > If the root map of your review task is different from the authoring root map, it displays the information about it to indicate that the authoring and the review root map don&#39;t match.

- **C**: Wenn Sie Ihr Thema nach dem Initiieren der Überprüfung aktualisiert haben, wird Ihre Arbeitskopie durch Klicken auf das Symbol Thema zur Überprüfung der Version zurücksetzen auf die Version zurückgesetzt, die zur Überprüfung freigegeben wurde. Dies erleichtert Ihnen die direkte Integration des Review-Feedbacks in die Version, die zur Überprüfung freigegeben wurde. Nach der Einbindung des Feedbacks können Sie Änderungen in der zurückgesetzten Version speichern oder eine neue Revision des Themas erstellen. Wenn Sie eine neue Version Ihres Themas erstellen, wird aus der Themenversion, die zur Überprüfung freigegeben wurde, eine neue Verzweigung erstellt. Wenn Sie beispielsweise Version `1.2` eines Themas für eine Überprüfung freigegeben haben, während die aktuelle Autorenversion `1.3` ist, können Sie dieses Symbol verwenden, um zur Version `1.2` zurückzukehren und Überprüfungskommentare einzubinden. Wenn Sie sich dafür entscheiden, eine neue Revision zu erstellen, nachdem Sie Änderungen an Version `1.2` integriert haben, wird für das Thema eine neue Verzweigung mit Version `1.2.0` erstellt.

  Nach der Einbindung von Überprüfungsfeedback möchten Sie in der Regel Änderungen aus der neuesten Version des Themas zusammenführen. Verwenden Sie dazu die Funktion [Zusammenführen](web-editor-features.md#id205DF04E0HS), um alle Aktualisierungen abzurufen, die vorgenommen wurden, nachdem das Thema zur Überprüfung freigegeben wurde.

- **D**: Öffnen Sie die Ansicht nebeneinander, um die kommentierte Version des Themas anzuzeigen. Wie im obigen Screenshot gezeigt, ist der Abschnitt ganz links die neueste Version des Themas, in der Sie Änderungen vornehmen können. Der nächste Abschnitt ist die kommentierte Version des Themas. Wenn Sie zwischen Kommentaren im Thema navigieren, ändert sich die Seitenansicht und zeigt die Version des Themas an, zu dem der Kommentar abgegeben wurde. Jeder Kommentar im Kommentarbereich ist mit dem entsprechenden Text in diesem Abschnitt verknüpft. Damit können Sie den kommentierten Text leichter identifizieren. Die Kommentare werden in der Reihenfolge des kommentierten Texts im Dokument angezeigt.

  Die Versionsnummer wird oben in der Seitenansicht angezeigt. Durch erneutes Klicken auf dieses Symbol wird die kommentierte Version des Themas ausgeblendet.

- E: Importieren Sie die eingefügten und gelöschten \(oder Durchgestrichen\) Kommentare direkt in das Thema. Nach dem Klicken auf das Symbol Importieren werden alle Texteinfügungen und Löschungen in der Arbeitskopie des Themas angezeigt. Es gibt zwei Möglichkeiten, Kommentare zu akzeptieren oder abzulehnen.

  Wenn Sie die vorgeschlagene Änderung \(Einfügung oder Löschung\) einzeln übernehmen möchten, klicken Sie einfach mit der rechten Maustaste auf den Kommentar im Inhalt und wählen Sie Änderung akzeptieren oder ablehnen. Je nach Auswahl wird der Kommentar akzeptiert oder abgelehnt. Im Falle eines akzeptierten Kommentars wird der Inhalt zum Inhalt hinzugefügt und im Falle einer Ablehnung wird er aus dem Inhalt entfernt. Außerdem wird der Status des Kommentars im Überprüfungsfeld geändert.

  ![](images/import-comment-accept-web-editor_cs.png){width="800" align="left"}

  Sie können auch die Überprüfungsfunktion im rechten Bedienfeld verwenden, um Kommentare zu akzeptieren oder abzulehnen. Wenn Sie auf einen Kommentar klicken, wird der Kommentar im Dokument hervorgehoben.

  ![](images/changes-tab_cs.png){width="800" align="left"}

  >[!IMPORTANT]
  >
  > Die Funktion Kommentare importieren funktioniert nur bei Dokumenten, die seit der Freigabe zur Überprüfung nicht geändert wurden. Wenn Sie nach dem Senden des Dokuments zur Überprüfung Änderungen vorgenommen haben, erhalten Sie einen Warnhinweis, um **Import erzwingen** Kommentare in Ihr Dokument zu importieren. Dies führt jedoch zum Verlust aller Aktualisierungen, die Sie in Ihrem Dokument vorgenommen haben. Der Warnhinweis **Import erzwingen** wird auch angezeigt, wenn das Dokument außerhalb erstellt und dann zur Überprüfung freigegeben wird. Sie können die Kommentare importieren.

  Wenn Sie einen Kommentar akzeptieren oder ablehnen, wird er aus der Liste „Getrackte Änderungen“ entfernt. Dies dient auch als Indikator dafür, wie viele Kommentare in dem Dokument angesprochen werden müssen.

- **F**: Laden Sie im Menü Mehr Optionen alle im Prüfungsthema verfügbaren Anhänge herunter.
- **G**: Suchen nach einem Text in Kommentaren.
- **H**: Akzeptieren oder Ablehnen eines Kommentars.

- **I**: Einen Filter auf die Kommentare anwenden. Sie können nach Kommentaren filtern, indem Sie die folgenden Kategorien verwenden: Prüfungstyp \(alle, hervorgehoben, gelöscht, eingefügt oder Haftnotiz\), Prüfstatus \(alle, akzeptiert, abgelehnt oder keine\), Prüfer \(alle oder bestimmte Prüfer\(s\)\) oder Versionen des Themas.


**Übergeordnetes Thema:**&#x200B;[&#x200B; Themen oder Karten überprüfen](review.md)
