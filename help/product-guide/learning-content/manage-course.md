---
title: Verwalten eines Kurses in Produktschulung und -lernen
description: Erfahren Sie mehr über die verschiedenen Funktionen in Experience Manager Guides, mit denen Sie Ihren Kurs effizient verwalten können.
feature: Authoring
role: User
exl-id: 0f480d08-2f8a-494e-ab56-4965e5eeb960
source-git-commit: 0171f7b798686a0a16942e98133001a4c05bb76b
workflow-type: tm+mt
source-wordcount: '708'
ht-degree: 0%

---

# Verwalten von Kursen

Nachdem Sie einen Kurs erstellt haben, wird er im Kursmanager-Bedienfeld geöffnet. Sie können den Kurs sperren und alle erforderlichen Änderungen auf Kursebene vornehmen. In den folgenden Abschnitten werden die verfügbaren Optionen zum Bearbeiten des Kurses erläutert.

## Neuen Inhalt hinzufügen

Führen Sie die folgenden Schritte aus, um neue Inhalte zu Ihrem Kurs hinzuzufügen:

1. Wählen Sie das Menü **Optionen** > **Neu hinzufügen** aus.

   ![](assets/learning-course-content.png)
2. Wählen Sie den Inhaltstyp aus, den Sie erstellen möchten. Folgende Optionen sind verfügbar:
   - **Überblick**: Das erste Thema Ihres Kurses, das eine kurze Einführung in das bietet, was der Kurs abdeckt.
   - **Thema**: Das Hauptmaterial in einem Kurs besteht aus kurzen, fokussierten Elementen wie Schritten, Beispielen oder Erklärungen, die eine bestimmte Fähigkeit oder Idee lehren. Weitere Informationen finden Sie unter [Thema erstellen und anpassen](./create-content.md).
   - **Zusammenfassung**: Ein kurzer Überblick am Ende eines Kurskapitels, der die Lernenden an die wichtigsten Punkte erinnert, die sie gerade gelernt haben.
   - **Quiz**: Eine Reihe von Fragen, mit denen überprüft wird, wie gut jemand versteht, was er gelernt hat. Weitere Informationen finden Sie unter [Quiz erstellen und verwalten](./create-quiz.md).
   - **Fragenbank**: Ein gemeinsam genutzter Pool wiederverwendbarer Fragen, mit denen sich schnell und konsistent Quiz erstellen lassen. Weitere Informationen finden Sie unter [Fragenbank](./create-qb.md).
   - **Group**: Eine Lerngruppe hilft dabei, verwandte Themen wie Kapitel, Themen und andere Module in einer logischen Reihenfolge zu organisieren, indem eine klare Hierarchie erstellt wird, die die Verwaltung und Wiederverwendung von Schulungsmaterialien erleichtert.
3. Wählen Sie **Erstellen** aus.

Der ausgewählte Inhalt wird erstellt und dem Kurs hinzugefügt. Eine Videoübersicht finden Sie unter [Hinzufügen neuer Inhalte zu einem Kurs](https://video.tv.adobe.com/v/3469537/aem-guides-learning-content?quality=12&learn=on) ![](assets/Smock_VideoCheckedOut_18_N.svg).

## Vorhandenen Inhalt hinzufügen

Sie können vorhandene Inhalte aus Ihrem Inhalts-Repository zu Ihrem Kurs hinzufügen. Führen Sie die folgenden Schritte aus, um vorhandenen Inhalt hinzuzufügen:

1. Wählen Sie das Menü **Optionen** > **Vorhandenes hinzufügen** aus.
2. Wählen Sie den Typ des Kursinhalts aus, den Sie erstellen möchten.
3. Navigieren **im Dialogfeld &quot;** auswählen“ zum Speicherort der Inhalte und wählen Sie die gewünschten Lerninhalte aus.

   ![](assets/add-existing-learning-content.png)
4. Wählen Sie **Auswählen** aus.

Der ausgewählte Kursinhalt wird dem Kurs aus dem Repository hinzugefügt.

>[!NOTE]
>
>Sie können auch die Option **Vorhandene hinzufügen** > **Datei (nur ZIP-Datei für Ressourcen)** verwenden, um eine ZIP-Datei einzuschließen, die entpackt und in die Ordnerstruktur der endgültigen SCORM-Ausgabe integriert wird. Dies hilft, die Ressourcenverpackung während der Kursveröffentlichung zu optimieren.

Eine Videoübersicht finden Sie unter [Hinzufügen vorhandener Inhalte zu einem Kurs](https://video.tv.adobe.com/v/3469537/aem-guides-learning-content?quality=12&learn=on) ![](assets/Smock_VideoCheckedOut_18_N.svg).

## Inhalt entfernen

Sie können jedes Thema aus dem Kurs entfernen, indem Sie das Menü **Optionen** für dieses spezifische Thema auswählen und dann auf **Eintrag entfernen** klicken, wie unten dargestellt.

![](assets/remove-learning-content.png)

Eine Videoübersicht finden Sie unter [Entfernen von Inhalten aus dem Kurs](https://video.tv.adobe.com/v/3475210/learning-content-aem-guides) ![](assets/Smock_VideoCheckedOut_18_N.svg).


## Kursversionen erstellen

Sie können die Versionierung Ihres Kurses über das Menü **Optionen** > **Versionierung** steuern.

![](assets/course-versioning.png)

Sie erhalten die folgenden Optionen für die Versionierung eines Kurses:

- **Als neue Version speichern**: Speichert Ihren Kurs mit einer neuen Versionsnummer.
- **Versionsverlauf**: Zeigt die Vorschau der aktuellen Version an und ermöglicht Ihnen auch, sie mit den anderen verfügbaren Versionen für den Kurs zu vergleichen.
- **Versionsbezeichnung**: Ermöglicht die Angabe von Beschriftungen in einem Freiformtextformat oder die Verwendung eines Satzes vordefinierter Beschriftungen.

## Anzeigeeinstellungen: Anzeigen

Die **Anzeigen**-Option bestimmt, wie Themen angezeigt werden. Sie können sie mithilfe von Kontrollkästchen für mehrere Themenauswahlen, Nummerierungen zur Angabe der hierarchischen Struktur oder durch Anzeige des Thementitels oder des Dateinamens darstellen.

>[!NOTE]
>
> Diese Anzeigeeinstellungen gelten nur für den Kurs-Manager und haben keine Auswirkungen auf die veröffentlichte Ausgabe.

![](assets/course-display-settings.png)

Eine Videoübersicht finden Sie unter [Einstellungen anzeigen](https://video.tv.adobe.com/v/3475210/learning-content-aem-guides) ![](assets/Smock_VideoCheckedOut_18_N.svg).

## Prüfungsaufgabe erstellen

Als Autor eines Lernkurses oder Administrator können Sie eine Prüfungsaufgabe für den Kurs erstellen und sie einem Prüfer für Feedback zuweisen. Öffnen Sie zunächst Ihren Kurs im Bedienfeld **Kursmanager** und wählen Sie dann **Prüfungsaufgabe erstellen** aus dem Menü **Optionen** wie unten dargestellt:

![](assets/create-review-task-lc.png)

Sie werden zur Seite **Prüfungsaufgabe erstellen** weitergeleitet, auf der Sie Aufgabendetails wie den Titel der Prüfungsaufgabe hinzufügen, das DITA-Projekt angeben, zu dem sie gehört, Aufgabenzeitpläne definieren, Validierungsverantwortliche zuweisen und vieles mehr. Sobald dies geschehen ist, erhalten die Reviewer eine Benachrichtigung über diese Aufgabe. Die ausgewählten Kursthemen werden in der Review-Benutzeroberfläche geöffnet. Dort können die Reviewer Kommentare hinzufügen und die Themen zur Aktualisierung zurücksenden.

Um den Prüfungs-Workflow in Experience Manager Guides zu verstehen, [ Sie Themen anzeigen und zur Überprüfung ](../user-guide/review-send-topics-for-review.md).


