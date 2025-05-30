---
title: Themen überprüfen
description: Erfahren Sie, wie Sie Themen überprüfen und die Funktionen als Reviewer, Dokumentansicht, Themenansicht, kontextuelle Symbolleiste, Vorschaumodus, Hinzufügen von Anlagen zu Kommentaren und Bedienfeld „Bedingungen“ in AEM Guides verwenden.
feature: Reviewing
role: User
hide: true
exl-id: 371d89b8-fe05-4477-9bf8-cc47c0899108
source-git-commit: ea597cd14469f21e197c700542b9be7c373aef14
workflow-type: tm+mt
source-wordcount: '2351'
ht-degree: 0%

---

# Themen überprüfen {#id2056B0W0FBI}

Wenn Sie ein Prüfer sind, erhalten Sie eine E-Mail mit einer Prüfungsanfrage mit dem Link zu den Prüfthemen. Durch Klicken auf den Link gelangen Sie zur Überprüfungsseite, auf der Sie Ihr Feedback zu den freigegebenen Themen hinzufügen können.

Führen Sie die folgenden Schritte aus, um ein Thema zu überprüfen:

1. Klicken Sie auf den direkten Link, der in der E-Mail mit der Überprüfungsanfrage angegeben ist.

   Das Thema oder der Zuordnungs-Link wird in einem Browser geöffnet.

   >[!NOTE]
   >
   > Sie können den Link zur Themenüberprüfung auch über den Bereich Benachrichtigungen im Posteingang in der Benutzeroberfläche von AEM aufrufen.

1. Je nachdem, wie die Themenüberprüfung eingeleitet wird, werden die beiden folgenden Bildschirme angezeigt:

   >[!NOTE]
   >
   > Die Benutzeroberfläche sieht möglicherweise anders aus, wenn Sie die Überprüfung in erstellt haben:
   >
   > - AEM Guides as a Cloud Service Version November 2022 oder früher
   > - AEM Guides Version 4.1 oder früher



   Der folgende Bildschirm wird angezeigt, wenn eine DITA-Zuordnung verwendet wird, um den Überprüfungs-Workflow zu starten:

   ![](images/multiple-topics-review.png){width="800" align="left"}

   Folgende Optionen sind auf diesem Bildschirm verfügbar:

   - **A**: Der Name der Prüfungsaufgabe.
   - **B**: Klicken Sie auf das Symbol Themenansicht , um den Themenbereich ein- oder auszublenden.

   - **C**: Sie können nach dem gewünschten Thema suchen, indem Sie einen Teil des Textes des Titels oder Dateipfads in die Suchleiste eingeben.

     Wählen Sie ![](images/view-options.svg) in der Nähe der Suchleiste aus, um alle Themen oder Themen mit Kommentaren anzuzeigen. Standardmäßig können Sie alle in der Prüfungsaufgabe vorhandenen Themen anzeigen.


   - **D**: Die durch ***F*** hervorgehobenen Zahlen können gefiltert werden, indem die gewünschte Filteroption hier ausgewählt wird. Kommentare können nach Typ, Status, Prüfer oder Version gefiltert werden. Wenn Sie beispielsweise anzeigen möchten, wie viele durchgestrichene Kommentare in den einzelnen zu überprüfenden Themen vorgenommen wurden, klicken Sie auf das Filtersymbol und wählen Sie dann **Überprüfungstyp** \> **Löschung**.

     >[!NOTE]
     >
     > Beim Anwenden der Filter werden im Kommentarbedienfeld nur die Kommentare angezeigt, die den ausgewählten Filtern entsprechen. Die Anzahl der gefilterten Kommentare wird auf der linken Seite im Themenbereich angezeigt.

   - **E**: Ein Thema, das dem aktuellen Reviewer zur Überprüfung zugewiesen ist, wird schwarz angezeigt und kann angeklickt werden. Wenn der Reviewer auf einen Themen-Link klickt, wird dieses Thema an den Anfang des Bildschirms gebracht.
   - **F**: Ein Thema, das nicht zur Überprüfung verfügbar ist, wird ausgegraut. Das Thema wird im schreibgeschützten Modus angezeigt und Sie dürfen keine Prüfungskommentare zu diesen Themen hinzufügen.

   - **G**: Anzahl der eingegangenen Kommentare zu einem Thema. Diese Zahl ändert sich je nach angewendetem Filter.

   Alle Themen in der Karte werden als einzelnes zusammengesetztes Dokument angezeigt. Die Themen, die der Reviewer überprüfen darf, werden normal angezeigt. Die Themen, die die Überprüfung nicht überprüfen darf, werden nicht angezeigt.

   ![](images/review-read-only.png){width="800" align="left"}

   Im obigen Screenshot wird das Thema Allgemeine Beschreibung für den aktuellen Reviewer freigegeben. Es wird normal angezeigt. Das nächste Thema, Verlauf des Fluginhalts , wird jedoch nicht zur Überprüfung freigegeben und es wird im schreibgeschützten Modus angezeigt. Das Thema, das derzeit im Fokus steht, wird auch im Inhaltsverzeichnis hervorgehoben.

   Der folgende Bildschirm wird angezeigt, wenn ein oder mehrere Themen ausgewählt und zur Überprüfung freigegeben werden:

   ![](images/review-composite-view.png){width="800" align="left"}

   >[!NOTE]
   >
   > Bei mehreren Themen werden sie als zusammengesetztes Dokument in der Dokumentansicht angezeigt. Der obige Screenshot zeigt zwei verschiedene Themen, die nacheinander in einer einzigen Ansicht vorgestellt werden.

1. Öffnen Sie das Bedienfeld „Kommentare **durch Klicken auf** Symbol „Kommentare“ oben rechts in der Symbolleiste.

   Geben Sie Kommentare zur Überprüfung ein, indem Sie den entsprechenden Kommentartyp in der Symbolleiste auswählen und die Eingabetaste drücken, um Ihren Kommentar zu übermitteln.

   >[!NOTE]
   >
   > Im Bedienfeld Kommentare werden nur die Kommentare zu den aktuellen Themen angezeigt. Wenn Sie den Fokus auf ein anderes Thema verschieben, werden die Kommentare zum anderen Thema angezeigt.

1. Klicken Sie **die Schaltfläche** Schließen“, nachdem Sie die Überprüfung des Themas abgeschlossen haben. Durch Klicken auf **Schließen** werden Sie zur Seite weitergeleitet, von der aus Sie auf das Prüfungsthema zugegriffen haben.

## Auf dem Überprüfungsbildschirm verfügbare zusätzliche Funktionen

**Dokumentansicht und Themenansicht** - Wenn mehrere Themen zur Überprüfung freigegeben werden, wird den Reviewern standardmäßig eine zusammengesetzte Dokumentansicht mit Themen angezeigt. Im Falle einer DITA-Kartenüberprüfung werden alle Themen in der Karte in Form eines einzigen Dokuments präsentiert, das einer Buchansicht ähnelt. Wenn Sie möchten, können Sie auch auf ein bestimmtes Thema klicken, und nur dieses Thema wird dann auf dem Überprüfungsbildschirm angezeigt.

Wenn Sie ein einzelnes Thema anzeigen, erhalten Sie eine zusätzliche Option, um zur Dokumentansicht zurückzukehren. Im folgenden Screenshot wird ein bestimmtes Thema aus einer Zuordnungsdatei zur Überprüfung geöffnet. Mit der hervorgehobenen Option **Dokumentansicht anzeigen** können Benutzer zur Dokumentansicht der Zuordnungsdatei zurückkehren.

![](images/switch-document-view.png){width="800" align="left"}

**Arbeiten mit verschiedenen Arten von Kommentar-Tools** - Sie können Inline-Kommentare hinzufügen, indem Sie Text markieren, durch Text streichen, Text einfügen oder eine Kommentar-Anmerkung hinzufügen. Nachfolgend werden die verschiedenen Arten von Kommentar-Tools beschrieben, die in der Symbolleiste „Kommentare“ verfügbar sind:

![](images/comments-toolbar.png){width="350" align="left"}

- **Hervorheben** \(![](images/review-highlight-icon.svg)\): Um einen Hervorhebungskommentar hinzuzufügen, wählen Sie den Text aus und klicken Sie auf das Symbol „Hervorheben“. Oder klicken Sie auf das Symbol Hervorheben und wählen Sie den gewünschten Text aus:

  ![](images/highlight-comment.png){width="650" align="left"}

  Im Bedienfeld „Kommentare“ wird ein Popup angezeigt, in dem Sie Ihren Kommentar für den hervorgehobenen Inhalt hinzufügen können.

- **Durchstreichen** \(![](images/review-text-strike-through-icon.svg)\): Wenn Sie das Entfernen von Inhalten vorschlagen möchten, wählen Sie den Inhalt aus und klicken Sie auf das Symbol „Durchstreichen“. Oder wählen Sie den gewünschten Text aus und klicken Sie auf die Löschen -Taste:

  Im Bedienfeld Kommentare wird ein Popup angezeigt, in dem Sie Ihren Kommentar für den gelöschten Inhalt hinzufügen können.

- **Text einfügen** \(![](images/review-insert-text-icon.svg)\): Wenn Sie Text einfügen möchten, klicken Sie auf das Symbol „Text einfügen“, und setzen Sie den Cursor an die Stelle, an der Sie den Text einfügen möchten, und geben Sie die Informationen ein. Oder platzieren Sie den Cursor an die Stelle, an der Sie Text einfügen möchten, und beginnen Sie mit der Eingabe. Die hinzugefügten Informationen werden in grüner Schriftart angezeigt:

- **Kommentar hinzufügen**\(![](images/review-comment-icon.svg)\): Wenn Sie einen Kommentar vom Typ Haftnotiz hinzufügen möchten, klicken Sie auf das Symbol Kommentar hinzufügen und geben Sie den Kommentar in das Popup-Fenster ein.


**Kontextuelle Symbolleiste**

Mit der kontextuellen Symbolleiste können Sie Text auch schnell markieren oder durchstreichen. Führen Sie die folgenden Schritte aus, um mithilfe der kontextuellen Symbolleiste einen Kommentar abzugeben:

1. Wählen Sie den Text aus, den Sie markieren oder durchstreichen möchten. Die kontextuelle Symbolleiste wird angezeigt.

   ![](images/review-quick-launch-toolbar.png){width="550" align="left"}

1. Klicken Sie auf **Symbol** Hervorheben **oder Durchstreichen** .
1. Sie können im Kommentarbereich Kommentare für die Hervorhebungs- oder Durchgestrichen-Aktion hinzufügen.

**Überprüfen mithilfe des Bedienfelds &quot;**&quot; - Das Bedienfeld „Kommentare“ zeigt eine Liste der Kommentare an, die zum aktuellen Thema abgegeben wurden. In diesem Bedienfeld werden auch Kommentare anderer Validierungsverantwortlicher aufgelistet, wenn das Thema an mehrere Validierungsverantwortliche gesendet wird. Jeder Kommentar im Kommentarbereich ist mit dem entsprechenden Text im aktuellen Thema verknüpft. Damit können Sie den kommentierten Text leichter identifizieren. Bei jedem Kommentar wird der Name des Reviewers angezeigt, der den Kommentar hinzugefügt hat, zusammen mit dem Zeitstempel.

Die Kommentare werden in der Reihenfolge des kommentierten Texts im Dokument angezeigt. Es gibt beispielsweise einen Hervorhebungskommentar für den ersten Satz und einen Textkommentar für den zweiten Satz im ersten Absatz. Dann wird der Textkommentar vor dem eingefügten Textkommentar angezeigt.

Nachfolgend werden die Aufgaben beschrieben, die Sie mit dem Bedienfeld „Kommentare“ ausführen können:

- Wenn Sie auf einen Kommentar klicken, wird dieser hervorgehoben und die Position des entsprechenden Kommentars im Dokument angezeigt.
- Sie können Antworten auf Kommentare hinzufügen.
- Sie können Ihren eigenen Kommentar bearbeiten, indem Sie im Kommentarbedienfeld auf Ihren kommentierten Text klicken und dann **Bearbeiten** aus dem Optionsmenü auswählen.
- Sie können Ihre eigenen Kommentare löschen, indem Sie im Kommentarbereich auf den Kommentar klicken und dann im Menü „Optionen **die Option** Löschen“ auswählen.

  ![](images/review-comment-options-menu.png){width="300" align="left"}

  >[!NOTE]
  >
  > Das Menü Optionen wird nur angezeigt, wenn Sie den Mauszeiger über eigene Kommentare bewegen. Es wird nicht für die Kommentare von anderen Reviewern angezeigt.

- Alle teilnehmenden Benutzer können auf Kommentare anderer Benutzer antworten. Klicken Sie bei einem Kommentar auf **Antworten** und drücken Sie die Eingabetaste , um eine Antwort zu senden.

**Vorschaumodus**

- Beim Öffnen eines Themas im Vorschaumodus wird angezeigt, wie ein Thema angezeigt wird, wenn es von einem Autor angezeigt wird, nachdem alle Änderungen angewendet wurden. Beispielsweise wird der gesamte eingefügte Text als normaler Text angezeigt und der gesamte gestrichelte \(gelöschte\) Text wird aus dem Inhalt entfernt.

- Der folgende Screenshot zeigt den Inhalt im *-*:

![](images/review-author-mode.png){width="550" align="left"}

Der folgende Screenshot zeigt den Inhalt im *-*:

![](images/review-preview-mode.png){width="550" align="left"}

**Anhänge zu Kommentaren hinzufügen** -   Wenn Sie Ihren Kommentar durch zusätzliche Informationen ergänzen möchten, die in einer anderen Datei verfügbar sind, können Sie dies tun, indem Sie ihn mit Ihrem Kommentar anhängen. Als Reviewer können Sie einfach eine oder mehrere Dateien aus Ihrem lokalen System zu Ihrem Kommentar hinzufügen. Sie können eine Datei zu allen unterstützten Kommentarformen hinzufügen - Hervorheben, Durchstreichen, Text einfügen oder Kommentar.

Wenn Sie einen der Kommentare einfügen, wird das Kommentar-Popup angezeigt. Nachdem Sie im Popup-Fenster zusätzliche Kommentare oder Informationen eingegeben haben, können Sie diese mit der Eingabetaste übermitteln. Nachdem der Kommentar hinzugefügt wurde, haben Sie die Möglichkeit, diesem Kommentar einen Anhang hinzuzufügen.

![](images/comment-pop-up-panel.png){width="800" align="left"}

Im obigen Screenshot enthält das Dokument das Popup-Fenster des hervorgehobenen Kommentars, und der Kommentar wird auch im Bedienfeld Kommentare hinzugefügt. Das Dateianhang-Symbol ![](images/file-attach-review.svg)ist zusammen mit dem Kommentar an beiden Speicherorten verfügbar.

Führen Sie die folgenden Schritte aus, um Ihrem Kommentar einen Anhang hinzuzufügen:

1. Klicken Sie auf das *Anlage hinzufügen*-Symbol ![](images/file-attach-review.svg) auf dem Kommentar, mit dem Sie eine Anlage hinzufügen möchten.

   Das Dialogfeld „Datei öffnen“ wird angezeigt.

1. Wählen Sie eine oder mehrere Dateien aus, die Sie anhängen möchten.

   Die ausgewählten Dateien werden zusammen mit dem Kommentar im Bedienfeld Kommentare angezeigt.

   Im Bedienfeld Kommentare können Sie den Dateinamen und dessen Größe sehen. Sie haben auch eine Option, um eine Datei zu entfernen, indem Sie auf das Löschsymbol klicken, das mit dem Dateinamen verknüpft ![](images/Delete_icon.svg).

1. Klicken Sie auf **Absenden**.

   Die Anlagen werden hochgeladen und dem Kommentar hinzugefügt.


**Zusätzliche Hinweise zum Arbeiten mit Anhängen:**

- Standardmäßig werden nur zwei Dateien angezeigt, die mit einem Kommentar versehen sind. Wenn es mehr Dateien gibt, zeigt **Schaltfläche „Anlage anzeigen** auf der rechten Seite die Anzahl aller Anlagen \(die mehr als zwei sind\), die mit dem Kommentar verbunden sind. Sie können auf die Zahl klicken, um alle Anhänge anzuzeigen. Wenn Sie beispielsweise vier Anhänge mit einem Kommentar haben, wird +2 auf der Schaltfläche angezeigt.

![](images/review-view-attachment.png){width="550" align="left"}

- Wenn Sie den Mauszeiger über einen Anhang bewegen, erhalten Sie die Möglichkeit, den Anhang herunterzuladen oder zu entfernen. Das Entfernen des Anhangs ist nur verfügbar, wenn der aktuelle Reviewer diesen Kommentar hinzugefügt hat, wie im folgenden Screenshot gezeigt:

![](images/current-user-comment-options.png){width="550" align="left"}

Die anderen Reviewer oder Autoren erhalten nur die Option „Anlage herunterladen“.

![](images/other-reviewer-download.png){width="550" align="left"}

- Sie können alle Anlagen, die mit einem Kommentar verbunden sind, über das Dialogfeld **Anlagen anzeigen** herunterladen. Wählen Sie die Anhänge aus und klicken Sie auf **Kommentarebene auf** Symbol „Herunterladen“.

- Sie können auch die Anlagen, die mit einem Kommentar verknüpft sind, im Dialogfeld **Anlagen anzeigen** löschen. Wählen Sie die Anlagen aus und klicken Sie auf **Löschen** Symbol.

![](images/attach-files-comments-panel.png){width="550" align="left"}


**Bedienfeld „Bedingungen** -   Wenn Ihr Thema bedingte Inhalte hat, wird auf der rechten Seite das **Bedingungen** \(![](images/conditions-icon.svg)\) angezeigt. Durch Klicken auf **Bedingungen** wird das Bedienfeld Bedingungen geöffnet, in dem Sie den Inhalt entsprechend den verfügbaren Bedingungen im Thema markieren können.

:   Standardmäßig ist **Option „Alle Bedingungen hervorheben** aktiviert, alle Bedingungen sind ausgewählt, der gesamte Inhalt wird angezeigt und der bedingte Inhalt wird sowohl im Vorschau- als auch im Vorschaumodus hervorgehoben angezeigt.

:   Sie können die Option **Alle Bedingungen hervorheben** deaktivieren und den gesamten Inhalt des Themas als normalen Text ohne Hervorhebungen anzeigen.

![](images/review-conditions-panel.png){width="350" align="left"}

Sie können eine bestimmte Bedingung aus- oder einblenden.

- Wenn Sie eine Bedingung ausblenden, wird der Inhalt mit dieser Bedingung im Überprüfungsmodus nicht hervorgehoben.
- Wenn Sie eine Bedingung anzeigen, wird der bedingte Inhalt im Überprüfungsmodus hervorgehoben. Im folgenden Screenshot beispielsweise verwendet nur der Inhalt zwei Bedingungen - `win` und `mac` ist hervorgehoben.


![](images/review-condition-normal-mode.png){width="650" align="left"}

Im Vorschaumodus werden der nicht bedingte Inhalt und der bedingte Inhalt, der die beiden angezeigten Bedingungen verwendet - `win` und `mac` - angezeigt. Der verbleibende bedingte Inhalt, für den die Bedingungen ausgeblendet sind, wird nicht angezeigt.

**Echtzeit-Überprüfung** -   Das Bedienfeld „Kommentare“ wird in Echtzeit mit Kommentaren und dem Feedback oder der Aktion des Autors zu den Kommentaren aktualisiert.

- Mehrere Reviewer können im selben Dokument Kommentare hinterlassen oder gleichzeitig auf Kommentare antworten. Um herauszufinden, wer das Dokument derzeit überprüft, bewegen Sie den Mauszeiger über das Benutzersymbol oben rechts im Bildschirm.

- Wenn ein Thema Teil mehrerer Prüfungsaufgaben ist, werden die in einer Aufgabe abgegebenen Kommentare in der anderen Aufgabe nicht angezeigt.

- Durch Klicken auf das Symbol Veralteter Kommentar \(![](images/outdated-comment-icon.svg)\) werden die Unterschiede zwischen der neuesten und der kommentierten Version des Dokuments angezeigt. Die Versionsnummern \(der zu vergleichenden Versionen\) werden oben in den Dokumenten angezeigt.

  ![](images/comments-page-review-mode.png){width="800" align="left"}

  >[!NOTE]
  >
  > Wenn Sie den Mauszeiger über das Symbol Veralteter Kommentar bewegen, wird die Versionsnummer des Themas angezeigt, zu dem der Kommentar hinzugefügt wurde. Wenn beispielsweise ein Kommentar zu Version 1.0 abgegeben wurde, wird derselbe angezeigt.

- Wenn Sie auf einen veralteten Kommentar klicken, wird die Version dieses Kommentars im linken Bereich geöffnet. Die vorherige Version wird im linken Bereich angezeigt und die aktuelle Version wird im rechten Bereich angezeigt. Alle Kommentare zur veralteten Version werden auf der linken Seite importiert. Sie können die vorherige Version mit der aktuellen Version vergleichen.

**Kommentare filtern** -   Sie können Kommentare in einem Dokument filtern, um bestimmte Kommentare nach Bedarf anzuzeigen. Um Kommentare zu filtern, klicken Sie auf **Filter**-Symbol \(![](images/filter-search-icon.svg)\), das im Menü rechts neben dem Textfeld „Kommentare durchsuchen“ im Bedienfeld „Kommentare“ angezeigt wird.

Wählen Sie eine oder mehrere der folgenden Filteroptionen im Dialogfeld **Filtertyp** und klicken Sie auf **Anwenden**.

- **Überprüfungstyp** - Filtern nach Kommentartyp - Hervorheben, Löschen, Einfügen oder Kommentar.
- **Prüfungsstatus** - Filtern Sie nach dem Status des Kommentars wie „Angenommen“, „Abgelehnt“ oder „Keine“.
- **Reviewer** - Filtern Sie nach dem Namen des Reviewers.

- **Versionen** - Filtern Sie nach den Kommentaren, die zu einer bestimmten Version des Themas eingegangen sind.

  Bei Verwendung der Filter werden die Kommentare im rechten Bereich entsprechend der Auswahl gefiltert und die Anzahl der Kommentare im linken Bereich wird entsprechend aktualisiert.


Um den Filter zu entfernen und alle Kommentare anzuzeigen, heben Sie die Auswahl aller Filter im Dialogfeld **Filtertyp** auf und klicken Sie auf **Anwenden**.

**Übergeordnetes Thema:**&#x200B;[ Themen oder Karten überprüfen](review.md)
