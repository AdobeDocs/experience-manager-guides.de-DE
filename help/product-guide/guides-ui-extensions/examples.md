---
sidebar_position: 8
source-git-commit: eb3fe92d36bc58a11e47f786a10d5938e2ed0184
workflow-type: tm+mt
source-wordcount: '371'
ht-degree: 0%

---


# Beispiele

In diesem Paket haben wir auch einige Anpassungsbeispiele bereitgestellt (verfügbar unter `guides_extension/src`). Unten finden Sie eine kurze Beschreibung für jeden von ihnen.

1. [Kontextmenü](./../../src/file_options.ts)
In diesem Beispiel haben wir das Kontextmenü `file_options` angepasst, um die Optionen `Delete` und `Edit` zu entfernen und die Option `Duplicate` durch eine Option `Download` zu ersetzen.

2. [Linke Leiste](../../src/left_panel_container.ts)
In diesem Beispiel haben wir die `left tab panel` so angepasst, dass ein weiterer `tab` mit dem Titel &quot;TESTERWEITERUNG&quot;und ein entsprechender `tab panel` mit einer Bezeichnung vorhanden sind: `Test Tab Panel`

3. [Rechter Bereich](../../src/right_panel_container.ts)
In diesem Beispiel haben wir die `right tab panel` so angepasst, dass eine weitere `tab` mit dem Titel &quot;TESTERWEITERUNG&quot;und eine entsprechende `tab panel` mit einer Bezeichnung vorhanden ist: `New Tab Panel`

4. [Repository-Bereich](../../src/repository_panel.ts)

5. [Symbolleiste](../../src/toolbar.ts)
In diesem Beispiel haben wir die Schaltflächen `Insert Element`, `Insert Paragraph`, `Insert Numbered List`, `Insert Bulleted List` durch eine einzelne Schaltfläche `More Insert Options` ersetzt, die all diese Schaltflächen enthält.

[Anwendungsbeispiele überprüfen]

1. [Anmerkungs-Toolbox](../../src/review_app_examples/annotation_extension.ts)
In diesem Beispiel haben wir der Anmerkungs-Toolbox eine weitere Schaltfläche hinzugefügt, mit der das aktuelle Prüfungsthema in AEM geöffnet wird.

2. [Kommentar überprüfen](../../src/review_app_examples/review_comment.ts)
In diesem Beispiel haben wir den Benutzernamen durch Benutzerinformationen ersetzt (bestehend aus dem vollständigen Namen und dem Titel des Kommentars), eine eindeutige Kommentar-ID, ein mailTo-Symbol hinzugefügt und Eingabefelder hinzugefügt, mit denen der Schweregrad und die Begründung von Kommentaren erwähnt werden.
Wir haben auch eine `accept with modification` -Schaltfläche zu Kommentaren auf der XMLEditor-Seite hinzugefügt, die ein Dialogfeld öffnet.

3. [Kommentar-Antwort](../../src/review_app_examples/comment_reply.ts)
In diesem Beispiel haben wir den Benutzernamen durch Benutzerinformationen ersetzt (bestehend aus dem vollständigen Namen und dem Titel des Kommentars) und ein mailTo -Symbol in der Kommentarkopfzeile hinzugefügt.

4. [Inline-Überprüfungsbereich](../../src/review_app_examples/inline_review_panel.ts)
In dieser Datei berechnen und weisen wir die eindeutige Kommentar-ID zu, die in den Beispielen `Review Comment` und `Comment Reply` erwähnt wird.
   - Die Methode `setCommentId` legt die eindeutige Kommentar-ID für jeden Kommentar fest, je nach Anzahl der Kommentare.

   - Der `setUserInfo` legt den Wert von userInfo fest, wobei für jeden Kommentar der vollständige Name und der Titel verwendet werden.

   - Die `onNewCommentEvent` stellt sicher, dass die `setUserInfo` -Methode für jeden neuen Kommentar oder jede neue Antwort aufgerufen wird.

   - Die Funktion `updatedProcessComments` wird für jedes neue Kommentar-Ereignis ausgeführt und stellt sicher, dass `setCommentId` aufgerufen wird, wenn ein neues Kommentar-Ereignis eintritt.

5. [Themenüberprüfungs-Bedienfeld](../../src/review_app_examples/topic_reviews.ts): Diese Datei erweitert das [Inline-Überprüfungsbedienfeld](../../src/review_app_examples/inline_review_panel.ts), sodass hinzugefügte Anpassungen auch auf der Seite &quot;Review-App&quot;funktionieren.

6. [Annehmen mit Dialogfeld &quot;Änderung&quot;](../../src/review_app_examples/accept_with_modification_dialog.ts)
Dies ist ein Beispiel für das Hinzufügen neuer Widgets zur App. Hier haben wir ein neues Dialogfeld mit zwei Eingabetextfeldern erstellt: `Revised Text` und `Adjudicator Comment Rationale`

![Mit Änderungs-Dialogfeld akzeptieren](./imgs/accept_with_modification_dialogue.png)

Hier finden Sie das Überprüfungsbedienfeld vor und nach der Anpassung:

![Überprüfungsbereich;](./imgs/review_panel.png)
![Mit Änderungs-Dialogfeld akzeptieren](./imgs/customised_review_panel.png)
