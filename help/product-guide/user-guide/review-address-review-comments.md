---
title: Kommentare zur Adressenüberprüfung
description: Erfahren Sie, wie Sie als Autor oder Autorin in AEM Guides Kommentare überprüfen können. Erfahren Sie, wie Autoren Kommentare in einem Dokument bearbeiten, filtern, akzeptieren oder ablehnen können.
exl-id: 4c969788-f700-4fd6-8afa-8e5b411b59f3
feature: Reviewing
role: User
source-git-commit: ae36a7fdff6ae147619340aa3a3d2bb6c7774fe0
workflow-type: tm+mt
source-wordcount: '1024'
ht-degree: 0%

---

# Kommentare zur Adressenüberprüfung {#id2056B0X0KBI}


Als Autor können Sie Kommentare in einem Thema mit dem Web-Editor bearbeiten. Die Kommentare werden auf der Grundlage der im Überprüfungsfeld ausgewählten Überprüfungsaufgabe geladen. Weitere Informationen finden Sie in der Beschreibung des Bedienfelds **Überprüfen** ![](images/active-review-tasklist-icon.svg) im Abschnitt [Linkes Bedienfeld](../user-guide/web-editor-features.md#id2051EA0M0HS).

In den folgenden Abschnitten werden Möglichkeiten zum Bearbeiten von Kommentaren im Web-Editor beschrieben.

Ein Autor kann im Web-Editor Kommentare in einem Dokument ansprechen. Es werden visuelle Indikatoren bereitgestellt, die angeben, ob Kommentare eingefügt \(text\), gelöscht oder hervorgehoben wurden. Auch die Art des Kommentars wird oben in jedem Kommentareintrag erwähnt.

>[!NOTE]
>
> Achten Sie beim Bearbeiten von Überprüfungskommentaren \(für ein aktives Überprüfungsdokument\) darauf, dass Sie - das zu überprüfende Thema wird nicht in mehreren Registerkarten mit aktivierter Ansicht „Vollständige Tags“ geöffnet - nicht zwischen dem Authoring- und dem Source-Ansichtsmodus wechseln.

![](images/comments-page-web-editor_cs-new.png){width="800" align="left"}

Im Web-Editor-Modus enthält das rechte Bedienfeld die Symbole Überprüfen und Änderungen verfolgen . Im Bedienfeld Überprüfung werden alle Kommentare angezeigt, die von Prüfern in Ihrem Dokument vorgenommen wurden. Das **Änderungen verfolgen** zeigt den Status aller eingefügten und gelöschten Kommentare in Ihrem Dokument an.

- **A**: Wählen Sie eine Prüfungsaufgabe aus, um Prüfungskommentare anzuzeigen. Wenn Ihr Thema für die Überprüfung in mehreren Prüfungsaufgaben freigegeben wurde, werden diese Aufgaben in dieser Dropdown-Liste angezeigt.

  Wenn Sie eine Prüfungsaufgabe aus der Liste auswählen, werden die Kommentare angezeigt, die von den Prüfern in dieser Aufgabe gemacht wurden. Sie können die Prüfungskommentare unabhängig in Aufgaben bearbeiten, was bedeutet, dass jede Aktualisierung eines Kommentars nur für Prüfer dieser jeweiligen Aufgabe sichtbar ist.

- **B:** Wählen Sie **Prüfungsdetails** ![](images/active-review-info-icon.svg) im Bedienfeld **Kommentare** aus, um weitere Informationen zur Prüfungsaufgabe anzuzeigen:

   - **Name**: Name der Prüfungsaufgabe .
   - **Prüfungsversion**: Zeigt die Version an, die der ausgewählten Prüfungsaufgabe zugeordnet ist. Auf diese Weise behalten Sie den Überblick über die Version, die Sie zur Überprüfung freigegeben haben
   - **Status**: Aktueller Status der Prüfungsaufgabe.

  >[!NOTE]
  >
  > Wenn sich die Stammzuordnung Ihrer Prüfungsaufgabe von der Stammzuordnung für die Bearbeitung unterscheidet, werden die zugehörigen Informationen angezeigt, um anzugeben, dass die Bearbeitung und die Stammzuordnung für die Überprüfung nicht übereinstimmen.

- **C**: Wenn Sie Ihr Thema nach dem Initiieren der Überprüfung aktualisiert haben, wird Ihre Arbeitskopie durch Auswahl des Symbols Thema auf Überprüfung zurücksetzen auf die Version zurückgesetzt, die für die Überprüfung freigegeben wurde. Dies erleichtert Ihnen die direkte Integration des Review-Feedbacks in die Version, die zur Überprüfung freigegeben wurde. Nach der Einbindung des Feedbacks können Sie Änderungen in der zurückgesetzten Version speichern oder eine neue Revision des Themas erstellen. Wenn Sie eine neue Version Ihres Themas erstellen, wird aus der Themenversion, die zur Überprüfung freigegeben wurde, eine neue Verzweigung erstellt. Wenn Sie beispielsweise Version `1.2` eines Themas für eine Überprüfung freigegeben haben, während die aktuelle Autorenversion `1.3` ist, können Sie dieses Symbol verwenden, um zur Version `1.2` zurückzukehren und Überprüfungskommentare einzubinden. Wenn Sie sich dafür entscheiden, eine neue Revision zu erstellen, nachdem Sie Änderungen an Version `1.2` integriert haben, wird für das Thema eine neue Verzweigung mit Version `1.2.0` erstellt.

  Nach der Einbindung von Überprüfungsfeedback möchten Sie in der Regel Änderungen aus der neuesten Version des Themas zusammenführen. Verwenden Sie dazu die Funktion [Zusammenführen](web-editor-features.md#id205DF04E0HS), um alle Aktualisierungen abzurufen, die vorgenommen wurden, nachdem das Thema zur Überprüfung freigegeben wurde.

- **D**: Öffnen Sie die Ansicht nebeneinander, um die kommentierte Version des Themas anzuzeigen. Wie im obigen Screenshot gezeigt, ist der Abschnitt ganz links die neueste Version des Themas, in der Sie Änderungen vornehmen können. Der nächste Abschnitt ist die kommentierte Version des Themas. Wenn Sie zwischen Kommentaren im Thema navigieren, ändert sich die Seitenansicht und zeigt die Version des Themas an, zu dem der Kommentar abgegeben wurde. Jeder Kommentar im Kommentarbereich ist mit dem entsprechenden Text in diesem Abschnitt verknüpft. Damit können Sie den kommentierten Text leichter identifizieren. Die Kommentare werden in der Reihenfolge des kommentierten Texts im Dokument angezeigt.

  Die Versionsnummer wird oben in der Seitenansicht angezeigt. Wenn Sie dieses Symbol erneut auswählen, wird die kommentierte Version des Themas ausgeblendet.

- E: Importieren Sie die eingefügten und gelöschten \(oder Durchgestrichen\) Kommentare direkt in das Thema. Nach Auswahl des Symbols Importieren werden alle Texteinfügungen und -löschungen in der Arbeitskopie des Themas angezeigt. Es gibt zwei Möglichkeiten, Kommentare zu akzeptieren oder abzulehnen.

  Wenn Sie die vorgeschlagene Änderung \(Einfügung oder Löschung\) einzeln übernehmen möchten, klicken Sie einfach mit der rechten Maustaste auf den Kommentar im Inhalt und wählen Sie Änderung akzeptieren oder ablehnen. Je nach Auswahl wird der Kommentar akzeptiert oder abgelehnt. Im Falle eines akzeptierten Kommentars wird der Inhalt zum Inhalt hinzugefügt und im Falle einer Ablehnung wird er aus dem Inhalt entfernt. Außerdem wird der Status des Kommentars im Überprüfungsfeld geändert.

  ![](images/import-comment-accept-web-editor_cs-new.png){width="800" align="left"}

  Sie können auch das Bedienfeld Änderungen verfolgen verwenden, um Kommentare zu akzeptieren oder abzulehnen. Wenn Sie einen Kommentar auswählen, wird der Kommentar im Dokument hervorgehoben.

  ![](images/changes-tab_cs-new.png){width="800" align="left"}

  >[!IMPORTANT]
  >
  > Die Funktion Kommentare importieren funktioniert nur bei Dokumenten, die seit der Freigabe zur Überprüfung nicht geändert wurden. Wenn Sie nach dem Senden des Dokuments zur Überprüfung Änderungen vorgenommen haben, erhalten Sie einen Warnhinweis, um **Import erzwingen** Kommentare in Ihr Dokument zu importieren. Dies führt jedoch zum Verlust aller Aktualisierungen, die Sie in Ihrem Dokument vorgenommen haben. Der Warnhinweis **Import erzwingen** wird auch angezeigt, wenn das Dokument außerhalb erstellt und dann zur Überprüfung freigegeben wird. Sie können die Kommentare importieren.

  Wenn Sie einen Kommentar akzeptieren oder ablehnen, wird er aus der Liste „Getrackte Änderungen“ entfernt. Dies dient auch als Indikator dafür, wie viele Kommentare in dem Dokument angesprochen werden müssen.

- **F**: Laden Sie im Menü Mehr Optionen alle im Prüfungsthema verfügbaren Anhänge herunter.
- **G**: Suchen nach einem Text in Kommentaren.
- **H**: Akzeptieren oder Ablehnen eines Kommentars.

- **I**: Einen Filter auf die Kommentare anwenden. Sie können nach Kommentaren filtern, und zwar auf der Grundlage von Überprüfungstyp \(alle, hervorgehoben, gelöscht, eingefügt oder Haftnotiz\), Überprüfungsstatus \(alle, akzeptiert, abgelehnt oder keine\), Reviewers \(alle oder bestimmte Reviewer\(s\)\) oder Themenversionen.


**Übergeordnetes Thema:**[ Einführung zur Überprüfung](review.md)
