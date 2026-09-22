---
title: Agent-KI-Assistent für Smart-Tagging-Funktion
description: Erfahren Sie, wie Sie den Agent AI-Assistenten für die Smart-Tagging-Funktion für Themen und Karten in einem einzigen Vorgang verwenden.
source-git-commit: cea0720e6482361a87b0e1dcff82760e3105436c
workflow-type: tm+mt
source-wordcount: '1351'
ht-degree: 0%
---

# Verwenden des KI-Assistenten im Agentenmodus

>[!NOTE]
>
> Der KI-Assistent im Agentenmodus ist in Experience Manager Guides as a Cloud Service ab Version 2026.09.0 verfügbar. Dazu muss Ihr Unternehmen CX Enterprise Coworker nutzen. Wenden Sie sich nach dem Onboarding an Ihr Customer Success-Team, um die Funktion zu aktivieren. Konfigurationsdetails finden Sie unter [Konfigurieren des KI-Assistenten im Agentenmodus](../install-conf-guide/configure-ai-assistant-agentic-mode-cs.md).

Der KI-Assistent im Agentenmodus macht das Tagging Ihrer Inhalte schneller, einfacher und konsistenter. Der KI-Assistent verwendet die Fähigkeit zum agentischen Smart-Tagging von Adobe CX Enterprise Coworker und analysiert Ihren Inhalt und empfiehlt relevante Tags basierend auf der Taxonomie Ihres Unternehmens, anstatt Inhalte manuell durchzulesen, um zu entscheiden, welche Tags angewendet werden sollen. Sie behalten die Kontrolle, indem Sie die vorgeschlagenen Tags überprüfen und sie anwenden oder ablehnen, bevor Sie Ihre Auswahl bestätigen, den manuellen Aufwand reduzieren, die Tagging-Genauigkeit verbessern und konsistente Metadaten in Ihrer Dokumentation sicherstellen.

## Bedienfeld KI-Assistent

Das Bedienfeld KI-Assistent bietet alle Tools, die Sie zum Generieren, Überprüfen und Anwenden von KI-vorgeschlagenen Tags benötigen.

![AI-Assistant-Panel für Agenten](images/guides-ai-panel.png){width="650"}

Die folgenden Komponenten des KI-Assistenten im Agentenmodus helfen Ihnen beim Hinzufügen von Dateien, Konfigurieren von Tag-Empfehlungen und Verwalten Ihres Smart-Tagging-Workflows:

- **(A)** Konversationsverlauf: Zeigen Sie frühere Konversationen an und öffnen Sie sie erneut, um frühere Tag-Empfehlungen und -Aktionen zu überprüfen.

  ![Agent KI Assistant Panel - Konversationsverlauf](images/chat-history.png){width="350"}

- **(B)** Neuer Chat: Beginnen Sie eine neue Tagging-Sitzung für ein anderes Thema, eine andere Karte oder einen anderen Dateisatz.
- **(C)** Tag-Namespace: Wählen Sie die Taxonomie-Namespaces aus, aus denen der KI-Assistent Tag-Empfehlungen generiert. Nur Tags aus den ausgewählten Namespaces werden berücksichtigt.

  ![Taxonomie des Agent-KI-Assistenten-Bedienfelds](images/taxononmy.png){width="350"}

- **(D)** Antwortraum: Überprüfen Sie die KI-generierten Tag-Empfehlungen und wählen Sie sie an, abzulehnen oder zu ändern, bevor Sie die Tags anwenden.
- **(E)** Platzierung auffordern: Geben Sie eine Eingabeaufforderung ein, um Tag-Empfehlungen für den ausgewählten Inhalt zu generieren.
- **(F)** Dateien anhängen oder Kontext hinzufügen: Fügt Themen, Karten oder externe Dateien aus Ihrem lokalen System hinzu, um den Inhalt bereitzustellen, den der KI-Assistent für Tag-Empfehlungen analysiert.
- **(G)**-Modell: Zeigt das KI-Modell an, das zur Analyse von Inhalten und Generierung von Tag-Empfehlungen verwendet wird. Mehrere OpenAI- und Anthropic-Claude-Modelle stehen zur Auswahl. Standardmäßig ist die Option **Standardmanifest verwenden** ausgewählt, die das für den ausgewählten Assistenten konfigurierte Modell verwendet.
- **(H)** Senden: Senden Sie Ihre Eingabeaufforderung und den angehängten Inhalt, um KI-gestützte Tag-Empfehlungen zu generieren.

## Anwenden von Tags auf einzelne oder mehrere Themen mit der Fähigkeit zum Smart-Tagging

Führen Sie die folgenden Schritte aus, um den KI-Assistenten zum Anwenden von Tags auf einzelne oder mehrere Themen mit der Fähigkeit zum Smart-Tagging zu verwenden:

1. Melden Sie sich bei Experience Manager Guides an.
1. Wählen Sie auf der Startseite in **Navigationsleiste die Option** KI-Assistent“ aus. Stellen Sie sicher, dass der KI-Assistent im Agentenmodus von Ihrem Administrator aktiviert wurde.
1. Fügen Sie das Thema hinzu, für das Sie Tag-Empfehlungen generieren möchten, indem Sie eine der folgenden Methoden verwenden:

   - **Verwenden von empfohlenen Eingabeaufforderungen**: Wählen Sie für den ersten Chat im Bereich Antwort die Option **Tags für eine Datei vorschlagen** aus. Die Eingabeaufforderung wird automatisch zur Eingabeaufforderung hinzugefügt. Wählen Sie `[file]` und dann das Thema aus dem Repository oder einer Sammlung im Dialogfeld **Datei**. Sie können ein Thema im Dialogfeld **Datei auswählen** auswählen.

     ![Greifen Sie mithilfe von vorgeschlagenen Eingabeaufforderungen auf das Assistentenbedienfeld für Agent-KI zu](images/suggested-prompts.png){width="650"}

   - **Verknüpfung verwenden**: Geben Sie `/` in das Feld Eingabeaufforderung ein, wählen Sie dann **Repository-Verweis hinzufügen**, um ein Thema aus dem Repository auszuwählen (oder **Dateien vom Gerät hinzufügen**, um ein Thema von Ihrem Computer hochzuladen), und geben Sie eine Eingabeaufforderung wie *Tags für eine Datei vorschlagen*.

   - **Drag-and-**: Ziehen Sie ein einzelnes Thema oder mehrere Themen per Drag-and-Drop in die Eingabeaufforderung und geben Sie eine Eingabeaufforderung wie *Tags für eine Datei vorschlagen* ein.

     ![Greifen Sie durch Ziehen und Ablegen eines Themas oder einer Karte auf das Assistentenbedienfeld für KI-Agenten zu](images/dragging-prompts.png){width="650"}

   - **Themenpfade angeben**: Geben Sie `@` ein, gefolgt von den kommagetrennten Pfaden für mehrere Themen aus denselben oder verschiedenen Zuordnungen, und geben Sie eine Eingabeaufforderung wie *Vorschlagen von Tags für eine Datei* ein.

     ![Massenthema-Hinzufügung zum Agent-KI-Assistenten](images/topics-path-add.png){width="650"}

1. Wählen Sie **Senden** aus.

1. Der KI-Assistent analysiert den Inhalt des Themas und generiert Tag-Empfehlungen.

   ![Benutzeroberfläche des Assistant-Panels von Agentic AI beim Analysieren und Denken](images/guides-ai-analysis.png){width="650"}

1. Überprüfen Sie die vorgeschlagenen Tags wie folgt:

   >[!NOTE]
   >
   > Bei Themen, die bereits Tags enthalten, zeigt der KI-Assistent die vorhandenen Tags an. Diese Tags sind schreibgeschützt und können nicht geändert oder entfernt werden.

   - Für ein einzelnes Thema können Sie **Empfehlungen akzeptieren** oder sie **ablehnen,** sie nicht erforderlich sind.

     ![Antwort des AI-Assistenten-Bedienfelds für Agenten nach der Inhaltsanalyse](images/guides-ai-tags-review.png){width="650"}

   - Für mehrere Themen:
     1. Wählen Sie **Vorschau** aus, um die KI-generierten Tag-Empfehlungen zu überprüfen.

        ![Massenanalysevorschau des Bedienfelds „Agent AI Assistant“](images/topics-tag-preview.png){width="650"}

     1. Überprüfen Sie die vorgeschlagenen Tags für jedes Thema und wählen Sie dann eine der folgenden Aktionen:
        - **Alle akzeptieren** um alle vorgeschlagenen Tags für alle Themen anzuwenden.
        - **Alle ablehnen**, um alle vorgeschlagenen Tags für alle Themen zu verwerfen.
        - **Alle Vorschläge löschen** um alle vorgeschlagenen Tags für ein bestimmtes Thema zu entfernen.
        - Wählen Sie das Symbol **X** neben einem Tag aus, um einen einzelnen Tag-Vorschlag zu entfernen.

          ![Dialogfeld für das Bedienfeld „Agent AI-Assistent“ für die Massenanalyse](images/topics-tag-preview-dialog.png){width="650"}

1. Wenn Sie die vorgeschlagenen Tags akzeptieren, fügt die Smart-Tagging-Fähigkeit die KI-generierten Tags zu den bereits auf den Inhalt angewendeten Tags hinzu.

Nach Abschluss der Überprüfung zeigt der KI-Assistent eine Zusammenfassung der auf das Thema angewendeten Tags und aller abgelehnten Tag-Empfehlungen an.

![Zusammenfassung der Antworten des Agent-KI-Assistenten](images/topic-tag-summary.png){width="650"}

## Anwenden von Tags auf mehrere Themen einer Zuordnung mithilfe der Smart-Tagging-Fähigkeit

Führen Sie die folgenden Schritte aus, um den KI-Assistenten zum Anwenden von Tags auf mehrere Themen einer Zuordnung mit der Fähigkeit zum Smart-Tagging zu verwenden:

1. Melden Sie sich bei Experience Manager Guides an.
1. Wählen Sie auf der Startseite in **Navigationsleiste die Option** KI-Assistent“ aus. Stellen Sie sicher, dass der KI-Assistent im Agentenmodus von Ihrem Administrator aktiviert wurde.
1. Fügen Sie die Zuordnung hinzu, für die Sie Tag-Empfehlungen generieren möchten, indem Sie eine der folgenden Methoden verwenden, wie unter Themen beschrieben:

   - **Verwenden von empfohlenen Eingabeaufforderungen**: Wählen Sie für den ersten Chat im Bereich Antwort die Option **Tags für eine Datei vorschlagen** aus. Die Eingabeaufforderung wird automatisch zur Eingabeaufforderung hinzugefügt. Wählen Sie `[file]` und dann die Zuordnung aus dem Repository oder einer Sammlung im Dialogfeld **Datei**.

   - **Drag-and-Drop**: Ziehen Sie eine Karte per Drag-and-Drop in die Eingabeaufforderung und geben Sie eine Eingabeaufforderung wie *Tags für eine Datei vorschlagen* ein.

   - **Verknüpfung verwenden**: Geben Sie `/` in das Feld Eingabeaufforderung ein und wählen Sie dann **Repository-Verweis hinzufügen**, um eine Zuordnung aus dem Repository auszuwählen (oder **Dateien vom Gerät hinzufügen**, um eine Zuordnung von Ihrem Computer hochzuladen), und geben Sie eine Eingabeaufforderung wie *Tags für eine Datei vorschlagen*.

     ![Agent-KI-Assistent für Bulk-Tagging](images/ai-map-selection.png){width="650"}

1. Wählen Sie **Senden** aus.
Eine Meldung weist darauf hin, dass die ausgewählte Zuordnung mehrere Themen enthält. Wählen Sie **Themen auswählen** aus, um die Themen auszuwählen, für die Sie Tag-Empfehlungen erstellen möchten.

   ![Agenten-KI-Assistenten für Bulk-Tagging bei der Auswahl von Themen](images/ai-select-topics.png){width="650"}

1. Wählen **im Dialogfeld „Themen**&quot; die Themen aus, für die Sie Tag-Empfehlungen erstellen möchten.\
   Das **Themen auswählen** Dialogfeld bietet Folgendes:

   - **Themenliste:** Zeigt alle Themen in der ausgewählten Zuordnung an. Wählen Sie die Themen aus, für die Sie Tag-Empfehlungen generieren möchten.
   - **Vorschaufenster:** zeigt eine Vorschau des ausgewählten Themas zusammen mit den vorhandenen Tags an.
   - **Filtern** Filtern Sie die Themen so, dass nur die mit **Tags hinzugefügt** oder **Keine Tags hinzugefügt** angezeigt werden.

     ![Auswählen des Dialogfelds „Themen“ beim Anwenden von Tags](images/select-dialog.png){width="650"}

1. Wählen Sie **Bestätigen** aus. Der KI-Assistent analysiert die ausgewählten Themen und zeigt die Anzahl der für jedes Thema generierten Tag-Empfehlungen an.
1. Wählen Sie **Vorschau** aus, um die KI-generierten Tag-Empfehlungen zu überprüfen.
1. Überprüfen Sie die vorgeschlagenen Tags für jedes Thema und wählen Sie dann eine der folgenden Aktionen:
   - **Alle akzeptieren** um alle vorgeschlagenen Tags für alle Themen anzuwenden.
   - **Alle ablehnen**, um alle vorgeschlagenen Tags für alle Themen zu verwerfen.
   - **Alle Vorschläge löschen** um alle vorgeschlagenen Tags für ein bestimmtes Thema zu entfernen.
   - Wählen Sie das Symbol **X** neben einem Tag aus, um einen einzelnen Tag-Vorschlag zu entfernen.

     >[!NOTE]
     >
     > Bei Themen, die bereits Tags enthalten, zeigt der KI-Assistent die vorhandenen Tags an. Diese Tags sind schreibgeschützt und können nicht geändert oder entfernt werden.

   ![Dialogfeld für die Massenvorschau des Agenten-KI-Assistenten für das Tagging](images/preview-dialog.png){width="650"}

1. Wenn Sie die vorgeschlagenen Tags akzeptieren, fügt die Smart-Tagging-Fähigkeit die KI-generierten Tags zu den bereits auf den Inhalt angewendeten Tags hinzu.

Nach Abschluss der Überprüfung zeigt der KI-Assistent eine Zusammenfassung der auf die einzelnen Themen angewendeten Tags sowie alle abgelehnten Tag-Empfehlungen an.

