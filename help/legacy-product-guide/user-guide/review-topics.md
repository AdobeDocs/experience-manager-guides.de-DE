---
title: Prüfungsthemen
description: Erfahren Sie, wie Sie Themen überprüfen und die Funktionen als Prüfer, Dokumentansicht, Themenansicht, kontextbezogene Symbolleiste, Vorschaumodus, Hinzufügen von Anlagen zu Kommentaren und Bedingungsbedienfeld in AEM Guides verwenden.
exl-id: fc87fc37-f1cd-4a19-96c2-3a08a8222002
feature: Reviewing
role: User
source-git-commit: 7db3df07fd17eecae1c502554118ca12f95fb5ab
workflow-type: tm+mt
source-wordcount: '2351'
ht-degree: 0%

---

# Prüfungsthemen {#id2056B0W0FBI}

Wenn Sie Überprüfer sind, erhalten Sie eine E-Mail mit einer Überprüfungsanfrage mit dem Link zu den Prüfungsthemen. Durch Klicken auf den Link gelangen Sie zur Überprüfungsseite, auf der Sie Ihr Feedback zu den freigegebenen Themen hinzufügen können.

Führen Sie die folgenden Schritte aus, um ein Thema zu überprüfen:

1. Klicken Sie auf den direkten Link in der E-Mail mit der Überprüfungsanforderung.

   Der Themen- oder Zuordnungslink wird in einem Browser geöffnet.

   >[!NOTE]
   >
   > Sie können auch über Ihren Benachrichtigungsbereich im Posteingang in der AEM-Benutzeroberfläche auf den Link zur Themenüberprüfung zugreifen.

1. Je nachdem, wie die Themenüberprüfung initiiert wird, können Sie einen der folgenden beiden Bildschirme sehen:

   >[!NOTE]
   >
   > Die Benutzeroberfläche kann sich unterscheiden, wenn Sie die Überprüfung in erstellt haben:
   >
   > - AEM Guides as a Cloud Service Version November 2022 oder früher
   > - AEM Guides-Version 4.1 oder früher



   Der folgende Bildschirm wird angezeigt, wenn eine DITA-Zuordnung zum Initiieren des Überprüfungs-Workflows verwendet wird:

   ![](images/multiple-topics-review.png){width="800" align="left"}

   Auf diesem Bildschirm stehen die folgenden Optionen zur Verfügung:

   - **A**: Der Name der Prüfungsaufgabe.
   - **B**: Klicken Sie auf das Symbol &quot;Themenansicht&quot;, um den Themenbereich ein- oder auszublenden.

   - **C**: Sie können nach dem erforderlichen Thema suchen, indem Sie einen Teil des Textes des Titels oder Dateipfads in die Suchleiste eingeben.

     Wählen Sie ![](images/view-options.svg) in der Nähe der Suchleiste aus, um alle Themen oder Themen mit Kommentaren anzuzeigen. Standardmäßig können Sie alle in der Prüfungsaufgabe vorhandenen Themen anzeigen.


   - **D**: Die durch ***F*** hervorgehobenen Zahlen können gefiltert werden, indem Sie die gewünschte Filteroption von hier auswählen. Sie können Kommentare nach Typ, Status, Überprüfer oder Version filtern. Wenn Sie z. B. sehen möchten, wie viele Durchstreichen-Kommentare in jedem der unter dem Prüfungsthema vorgenommen wurden, klicken Sie auf das Filtersymbol und wählen Sie dann **Überprüfungstyp** \> **Löschvorgang**.

     >[!NOTE]
     >
     > Beim Anwenden der Filter werden nur die Kommentare angezeigt, die mit den ausgewählten Filtern übereinstimmen. Die Anzahl der gefilterten Kommentare wird links im Themenbereich angezeigt.

   - **E**: Ein Thema, das dem aktuellen Überprüfer zur Überprüfung zugewiesen wird, wird schwarz angezeigt und kann angeklickt werden. Wenn der Validierer auf einen Themenlink klickt, wird das Thema an den Anfang des Bildschirms gebracht.
   - **F**: Ein Thema, das nicht zur Überprüfung verfügbar ist, ist ausgegraut. Das Thema wird im schreibgeschützten Modus angezeigt und Sie dürfen zu solchen Themen keine Überprüfungskommentare hinzufügen.

   - **G**: Anzahl der Kommentare zu einem Thema. Diese Zahl ändert sich je nach angewendetem Filter.

   Alle Themen in der Karte werden als ein einziges zusammengesetztes Dokument angezeigt. Die Themen, die der Validierer überprüfen darf, werden normal angezeigt. Die Themen, die der Review nicht überprüfen darf, werden nicht angezeigt.

   ![](images/review-read-only.png){width="800" align="left"}

   Im obigen Screenshot wird das Thema &quot;Allgemeine Beschreibung&quot;für die Überprüfung des aktuellen Validierers freigegeben, was normal angezeigt wird. Das nächste Thema, Verlauf des Fluginhalts, wird jedoch nicht zur Überprüfung freigegeben und im schreibgeschützten Modus angezeigt. Das Thema, das derzeit im Fokus ist, wird auch im Inhaltsverzeichnis hervorgehoben.

   Der folgende Bildschirm wird angezeigt, wenn ein Thema oder mehrere Themen ausgewählt und zur Überprüfung freigegeben werden:

   ![](images/review-composite-view.png){width="800" align="left"}

   >[!NOTE]
   >
   > Bei mehreren Themen werden sie in der Dokumentansicht als ein zusammengesetztes Dokument angezeigt. Im obigen Screenshot werden zwei verschiedene Themen hervorgehoben, die nacheinander in einer Ansicht dargestellt werden.

1. Öffnen Sie das Bedienfeld Kommentare , indem Sie auf das Symbol **Kommentare** oben rechts in der Symbolleiste klicken.

   Geben Sie Überprüfungskommentare ein, indem Sie in der Symbolleiste einen geeigneten Kommentartyp auswählen und die Eingabetaste drücken, um Ihren Kommentar einzureichen.

   >[!NOTE]
   >
   > Im Bereich &quot;Kommentare&quot;werden nur die Kommentare zu den aktuellen Themen angezeigt. Wenn Sie den Fokus auf ein anderes Thema verschieben, werden die Kommentare zum anderen Thema angezeigt.

1. Klicken Sie auf die Schaltfläche **Schließen** , nachdem Sie die Überprüfung des Themas abgeschlossen haben. Wenn Sie auf die Schaltfläche **Schließen** klicken, werden Sie zu der Seite weitergeleitet, von der Sie auf das Prüfungsthema zugegriffen haben.

## Zusätzliche Funktionen auf dem Prüfungsbildschirm

**Dokumentansicht und Themenansicht** - Standardmäßig wird den Validierern eine zusammengesetzte Dokumentansicht der Themen angezeigt, wenn mehrere Themen zur Überprüfung freigegeben sind. Bei einer DITA-Map-Überprüfung werden alle Themen in der Karte in Form eines einzigen Dokuments präsentiert, das einer Buchansicht ähnelt. Wenn Sie möchten, können Sie auch auf ein bestimmtes Thema klicken und nur dieses Thema wird dann auf dem Prüfungsbildschirm angezeigt.

Wenn Sie ein einzelnes Thema anzeigen, erhalten Sie eine zusätzliche Option, um zur Dokumentansicht zurückzukehren. Im folgenden Screenshot wird ein bestimmtes Thema aus einer Map-Datei zur Überprüfung geöffnet. Mit der hervorgehobenen Option &quot;**Dokumentansicht anzeigen**&quot; kann der Benutzer zurück zur Dokumentansicht der Zuordnungsdatei wechseln.

![](images/switch-document-view.png){width="800" align="left"}

**Arbeiten mit verschiedenen Arten von Kommentar-Tools** - Sie können Inline-Kommentare hinzufügen, indem Sie Text hervorheben, Text durchstreichen, Text einfügen oder einen Kommentar hinzufügen. Die verschiedenen in der Symbolleiste &quot;Kommentare&quot;verfügbaren Tools für die Kommentarbearbeitung werden nachfolgend beschrieben:

![](images/comments-toolbar.png){width="350" align="left"}

- **Hervorheben** \(![](images/review-highlight-icon.svg)\): Um einen Hervorhebungskommentar hinzuzufügen, wählen Sie den Text aus und klicken Sie auf das Symbol Hervorheben . Oder klicken Sie auf das Symbol Hervorheben und wählen Sie den gewünschten Text aus:

  ![](images/highlight-comment.png){width="650" align="left"}

  Im Fenster Kommentare wird ein Popup angezeigt, in dem Sie Ihren Kommentar für den hervorgehobenen Inhalt hinzufügen können.

- **Durchstreichen** \(![](images/review-text-strike-through-icon.svg)\): Wenn Sie das Entfernen von Inhalten vorschlagen möchten, wählen Sie den Inhalt aus und klicken Sie auf das Durchstreichen-Symbol. Wählen Sie alternativ den gewünschten Text aus und klicken Sie auf die Entf-Taste:

  Im Fenster Kommentare wird ein Popup angezeigt, in dem Sie Ihren Kommentar für den gelöschten Inhalt hinzufügen können.

- **Text einfügen** \(![](images/review-insert-text-icon.svg)\): Wenn Sie Text einfügen möchten, klicken Sie auf das Symbol &quot;Text einfügen&quot;und platzieren Sie den Cursor an die Stelle, an der Sie den Text einfügen möchten, und geben Sie die Informationen ein. Oder platzieren Sie den Cursor an die Stelle, an der Sie Text einfügen und mit der Eingabe beginnen möchten. Die hinzugefügten Informationen werden in grüner Schriftart angezeigt:

- **Kommentar hinzufügen**\(![](images/review-comment-icon.svg)\): Wenn Sie einen Kommentar vom Typ &quot;Kurznotiz&quot;hinzufügen möchten, klicken Sie auf das Symbol Kommentar hinzufügen und geben Sie den Kommentar in das Popup-Fenster ein.


**Kontextuelle Symbolleiste**

Mit der dedizierten Symbolleiste können Sie Text auch schnell hervorheben oder durchsuchen. Führen Sie die folgenden Schritte aus, um Kommentare über die dedizierte Symbolleiste zu erstellen:

1. Wählen Sie den Text aus, den Sie markieren oder durchstreichen möchten. Die dedizierte Symbolleiste wird angezeigt.

   ![](images/review-quick-launch-toolbar.png){width="550" align="left"}

1. Klicken Sie auf das Symbol **Hervorheben** oder **Durchstreichen** .
1. Sie können Kommentare zum Hervorheben oder Durchstreichen im Kommentarbereich hinzufügen.

**Überprüfen mit dem Fenster &quot;Kommentare&quot;** - Im Bereich &quot;Kommentare&quot;wird eine Liste mit Kommentaren zum aktuellen Thema angezeigt. In diesem Bedienfeld werden auch Kommentare von anderen Validierern aufgelistet, wenn das Thema an mehrere Validierungsverantwortliche gesendet wird. Jeder Kommentar im Kommentarbereich ist mit dem entsprechenden Text im aktuellen Thema verknüpft. Sie können damit den kommentierten Text identifizieren. Jeder Kommentar zeigt den Namen des Validierers an, der den Kommentar hinzugefügt hat, sowie den Zeitstempel.

Die Kommentare werden in der Reihenfolge des kommentierten Texts im Dokument angezeigt. Zum Beispiel gibt es einen Hervorhebungskommentar zum ersten Satz und einen Einfügetext-Kommentar zum zweiten Satz im ersten Absatz. Dann wird der Hervorhebungstext-Kommentar vor dem eingefügten Textkommentar angezeigt.

Die Aufgaben, die Sie mit dem Bereich &quot;Kommentare&quot;ausführen können, werden unten beschrieben:

- Wenn Sie auf einen Kommentar klicken, wird der Speicherort des entsprechenden Kommentars im Dokument hervorgehoben und angezeigt.
- Sie können Antworten zu Kommentaren hinzufügen.
- Sie können Ihren eigenen Kommentar bearbeiten, indem Sie auf den Kommentar-Text im Bereich &quot;Kommentare&quot;klicken und dann im Menü &quot;Optionen&quot;die Option **Bearbeiten** auswählen.
- Sie können Ihre eigenen Kommentare löschen, indem Sie auf den Kommentar im Fenster &quot;Kommentare&quot;klicken und dann im Menü &quot;Optionen&quot;die Option **Löschen** auswählen.

  ![](images/review-comment-options-menu.png){width="300" align="left"}

  >[!NOTE]
  >
  > Das Menü Optionen wird nur angezeigt, wenn Sie den Mauszeiger über Ihre eigenen Kommentare bewegen. Sie wird von anderen Validierern nicht für die Kommentare angezeigt.

- Alle teilnehmenden Benutzer können auf Kommentare anderer Benutzer antworten. Klicken Sie in einem Kommentar auf **Antworten** und drücken Sie die Eingabetaste , um eine Antwort zu senden.

**Vorschaumodus**

- Wenn Sie ein Thema im Vorschaumodus öffnen, wird gezeigt, wie ein Thema angezeigt wird, wenn es von einem Autor nach Anwendung aller Änderungen angezeigt wird. So wird beispielsweise der gesamte eingefügte Text als normaler Text angezeigt und der gesamte Text, der durch &quot;\(gelöscht\)&quot;abgeschnitten wurde, wird aus dem Inhalt entfernt.

- Der folgende Screenshot zeigt den Inhalt im Modus *Überprüfen* :

![](images/review-author-mode.png){width="550" align="left"}

Der folgende Screenshot zeigt den Inhalt im Modus *Vorschau* :

![](images/review-preview-mode.png){width="550" align="left"}

**Anlagen zu Kommentaren hinzufügen** -   Wenn Sie Ihren Kommentar durch zusätzliche Informationen ergänzen möchten, die in einer anderen Datei verfügbar sind, können Sie dies tun, indem Sie ihn mit Ihrem Kommentar anfügen. Als Validierer können Sie einfach eine oder mehrere Dateien aus Ihrem lokalen System zu Ihrem Kommentar hinzufügen. Eine Datei kann allen unterstützten Formen von Kommentaren hinzugefügt werden: Hervorheben, Durchstreichen, Text einfügen oder ein Kommentar.

Wenn Sie einen Kommentar einfügen, wird das Kommentar-Popup angezeigt. Nachdem Sie im Popup zusätzliche Kommentare oder Informationen bereitgestellt haben, senden Sie sie durch Drücken der Eingabetaste. Nachdem der Kommentar hinzugefügt wurde, erhalten Sie die Möglichkeit, diesem Kommentar eine Anlage hinzuzufügen.

![](images/comment-pop-up-panel.png){width="800" align="left"}

Im obigen Screenshot enthält das Dokument das Popup-Fenster des Hervorhebungskommentars und der Kommentar wird auch im Fenster &quot;Kommentare&quot;hinzugefügt. Das Dateianlagesymbol ![](images/file-attach-review.svg)ist zusammen mit dem Kommentar an beiden Speicherorten verfügbar.

Führen Sie die folgenden Schritte aus, um Ihrem Kommentar Anlagen hinzuzufügen:

1. Klicken Sie auf das Symbol *Anhang hinzufügen* ![](images/file-attach-review.svg) für den Kommentar, mit dem Sie einen Anhang hinzufügen möchten.

   Das Dialogfeld &quot;Datei öffnen&quot;wird angezeigt.

1. Wählen Sie eine oder mehrere Dateien aus, die Sie anhängen möchten.

   Die ausgewählten Dateien werden zusammen mit dem Kommentar im Bereich &quot;Kommentare&quot;angezeigt.

   Im Bereich &quot;Kommentare&quot;können Sie den Dateinamen und die zugehörige Größe sehen. Sie können auch eine Datei entfernen, indem Sie auf das Löschsymbol ![](images/Delete_icon.svg) klicken, das dem Dateinamen zugeordnet ist.

1. Klicken Sie auf **Absenden**.

   Die Anlagen werden hochgeladen und zum Kommentar hinzugefügt.


**Zusätzliche Hinweise zum Arbeiten mit Anhängen:**

- Standardmäßig werden nur zwei Dateien mit einem Kommentar angezeigt. Wenn mehr Dateien vorhanden sind, zeigt die Schaltfläche &quot;**Anlage anzeigen**&quot;rechts die Anzahl aller Anlagen an, die \(mehr als zwei\) mit dem Kommentar verknüpft sind. Sie können auf die Zahl klicken, um alle Anlagen anzuzeigen. Wenn Sie beispielsweise vier Anlagen mit einem Kommentar haben, sehen Sie +2 auf der Schaltfläche.

![](images/review-view-attachment.png){width="550" align="left"}

- Wenn Sie den Mauszeiger über einen Anhang bewegen, haben Sie die Möglichkeit, den Anhang herunterzuladen oder zu entfernen. Das Entfernen des Anhangs ist nur verfügbar, wenn der aktuelle Überprüfer diesen Kommentar hinzugefügt hat, wie im folgenden Screenshot gezeigt:

![](images/current-user-comment-options.png){width="550" align="left"}

Die anderen Validierer oder Autoren erhalten nur die Option zum Herunterladen von Anlagen.

![](images/other-reviewer-download.png){width="550" align="left"}

- Sie können alle Anlagen, die mit einem Kommentar verknüpft sind, aus dem Dialogfeld **Anlagen anzeigen** herunterladen. Wählen Sie die Anlagen aus und klicken Sie auf der Kommentarebene auf das Symbol **Download** .

- Sie können auch die mit einem Kommentar verknüpften Anlagen aus dem Dialogfeld **Anlagen anzeigen** löschen. Wählen Sie die Anlagen aus und klicken Sie auf das Symbol **Löschen** .

![](images/attach-files-comments-panel.png){width="550" align="left"}


**Bedienfeld &quot;Bedingungen&quot;** -   Wenn Ihr Thema bedingte Inhalte enthält, wird rechts das Symbol **Bedingungen** \(![](images/conditions-icon.svg)\) angezeigt. Durch Klicken auf das Symbol **Bedingungen** wird der Bereich &quot;Bedingungen&quot;geöffnet, in dem Sie den Inhalt gemäß den verfügbaren Bedingungen im Thema hervorheben können.

:   Standardmäßig ist die Option **Alle Bedingungen markieren** aktiviert, alle Bedingungen sind ausgewählt, der gesamte Inhalt wird angezeigt und der konditionierte Inhalt wird sowohl im Vorschau- als auch im Vorschaumodus hervorgehoben dargestellt.

:   Sie können die Option **Alle Bedingungen markieren** deaktivieren und den gesamten Inhalt im Thema als normalen Text ohne Highlights anzeigen.

![](images/review-conditions-panel.png){width="350" align="left"}

Sie können eine bestimmte Bedingung ein- oder ausblenden.

- Wenn Sie eine Bedingung ausblenden, wird der Inhalt mit dieser Bedingung im Überprüfungsmodus nicht hervorgehoben.
- Wenn Sie eine Bedingung anzeigen, wird der konditionierte Inhalt im Überprüfungsmodus hervorgehoben. Im folgenden Screenshot verwendet nur der Inhalt zwei Bedingungen: `win` und `mac` werden hervorgehoben.


![](images/review-condition-normal-mode.png){width="650" align="left"}

Im Vorschaumodus werden der nicht konditionalisierte Inhalt und der konditionalisierte Inhalt angezeigt, der die beiden angezeigten Bedingungen verwendet - `win` und `mac`. Der verbleibende bedingte Inhalt, für den die Bedingungen ausgeblendet sind, wird nicht angezeigt.

**Echtzeitüberprüfung** -   Das Fenster Kommentare wird in Echtzeit mit Kommentaren und dem Feedback oder der Aktion aktualisiert, die der Autor zu den Kommentaren durchgeführt hat.

- Mehrere Überprüfer können Kommentare hinterlassen oder auf Kommentare gleichzeitig zum selben Dokument antworten. Sie können ermitteln, wer das Dokument derzeit überprüft, indem Sie den Mauszeiger über das Benutzersymbol in der oberen rechten Ecke des Bildschirms bewegen.

- Wenn ein Thema Teil mehrerer Prüfungsaufgaben ist, werden die in einer Aufgabe vorgenommenen Kommentare in der anderen Aufgabe nicht angezeigt.

- Durch Klicken auf das Symbol für veraltete Kommentare \(![](images/outdated-comment-icon.svg)\) werden die Unterschiede zwischen der neuesten und der kommentierten Version des Dokuments angezeigt. Die Versionsnummern \(der verglichenen Versionen\) werden oben in den Dokumenten angezeigt.

  ![](images/comments-page-review-mode.png){width="800" align="left"}

  >[!NOTE]
  >
  > Wenn Sie den Mauszeiger über das Symbol Veralteter Kommentar bewegen, wird die Versionsnummer des Themas angezeigt, zu dem der Kommentar hinzugefügt wurde. Wenn beispielsweise ein Kommentar zu Version 1.0 abgegeben wurde, wird derselbe Kommentar angezeigt.

- Wenn Sie auf einen veralteten Kommentar klicken, wird die Version dieses Kommentars im linken Bereich geöffnet. Die vorherige Version wird im linken Bereich angezeigt und die aktuelle Version wird im rechten Bereich angezeigt. Alle Kommentare zur veralteten Version werden links importiert. Sie können die vorherige Version mit der aktuellen Version vergleichen.

**Kommentare filtern** -   Sie können Kommentare in einem Dokument filtern, um nach Bedarf spezifische Kommentare anzuzeigen. Um Kommentare zu filtern, klicken Sie auf das Symbol &quot;**Filter**&quot;\(![](images/filter-search-icon.svg)\), das im Menü rechts neben dem Textfeld &quot;Suchkommentare&quot;im Bereich &quot;Kommentare&quot;angezeigt wird.

Wählen Sie im Dialogfeld **Filtertyp** eine oder mehrere der folgenden Filteroptionen aus und klicken Sie auf **Anwenden**.

- **Überprüfungstyp** - Filtern Sie nach dem Kommentartyp - Hervorheben, Löschen, Einfügen oder Kommentar.
- **Überprüfungsstatus** - Filtern Sie nach dem Status des Kommentars wie &quot;Akzeptiert&quot;, &quot;Abgelehnt&quot;oder &quot;Keine&quot;.
- **Überprüfer** - Filtern Sie nach dem Namen des Validierers.

- **Versionen** - Filtern Sie anhand der Kommentare, die zu einer bestimmten Version des Themas eingegangen sind.

  Bei Verwendung der Filter werden die Kommentare im rechten Bereich entsprechend der Auswahl gefiltert und die Anzahl der Kommentare im linken Bereich entsprechend aktualisiert.


Um den Filter zu entfernen und alle Kommentare anzuzeigen, heben Sie die Auswahl aller Filter im Dialogfeld **Filtertyp** auf und klicken Sie auf **Anwenden**.

**Übergeordnetes Thema:**[ Themen oder Zuordnungen überprüfen](review.md)
