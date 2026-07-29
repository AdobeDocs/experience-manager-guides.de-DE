---
title: Versionshinweise | Neue Funktionen in Adobe Experience Manager Guides Version 2026.08.0
description: Erfahren Sie mehr über die neuen und erweiterten Funktionen der Version 2026.08.0 von Adobe Experience Manager Guides
role: Leader
source-git-commit: b866964c30a565eab0f6f9aec4b3fc9013f15f75
workflow-type: tm+mt
source-wordcount: '1383'
ht-degree: 0%

---

# Neue Funktionen in der Version 2026.08.0 (August 2026)

Dieser Artikel behandelt die neuen und erweiterten Funktionen, die mit der Version 2026.08.0 von Adobe Experience Manager Guides as a Cloud Service eingeführt wurden.

Eine Liste der in dieser Version behobenen Probleme finden Sie unter [Behobene Probleme in Version 2026.08.0](fixed-issues-2026-08-0.md).

Erfahren Sie mehr [Upgrade-Anweisungen für die Version 2026.08.0](../release-info/upgrade-instructions-2026-08-0.md).


## Neue Zuordnungssammlung zum Verwalten von Zuordnungen und Veröffentlichen von Ausgaben

Neue Zuordnungssammlung vereint die Verwaltung von Zuordnungen und die Generierung von Ausgaben in einer einzigen Oberfläche. Von einem Ort aus können Sie Karten und Vorgaben verwalten, Ausgaben generieren und veröffentlichen, den Generierungs- und Veröffentlichungsverlauf anzeigen und vieles mehr. Durch das Zusammenführen verwandter Veröffentlichungsaufgaben wird es einfacher, mit Zuordnungssammlungen zu arbeiten und die Ausgabeaktivität über mehrere Zuordnungen und die zugehörigen Sprachen hinweg zu verfolgen. Diese Aktualisierung behebt auch Leistungsprobleme, die bei großen Zuordnungssammlungen auftreten.

![](assets/new-maps-collection.png)

Weitere Informationen finden Sie unter [Verwenden einer neuen Zuordnungssammlung für die Ausgabegenerierung](../user-guide/generate-output-use-new-map-collection-output-generation.md).


## Abrufen von Inhalten aus Git-Repositorys mithilfe des Git-Connectors

Experience Manager Guides führt jetzt den Git-Connector ein, mit dem Sie Inhalte aus Git-Repositorys in Experience Manager Guides importieren können. Nachdem die Inhalte importiert wurden, können Teams weiterhin Experience Manager Guides für ihre Workflows zum Erstellen, Überprüfen, Übersetzen und Veröffentlichen verwenden.

Um importierte Inhalte auf dem neuesten Stand zu halten, unterstützt Git-Connector auch das erneute Abrufen von Inhalten aus dem Quell-Repository, um Aktualisierungen einzubringen. Sie umfasst eine intelligente Änderungserkennung zur Identifizierung von Inhaltsaktualisierungen, behält Themen- und Zuordnungs-GUIDs während des Imports und erneuten Abrufs bei und bietet Funktionen zur Konfliktbehebung, mit denen Unterschiede zwischen Repository-Inhalten und bereits in Experience Manager Guides verfügbaren Inhalten verwaltet werden können. Weitere Informationen finden Sie unter [Inhalt mit Git-Connector importieren](../user-guide/web-editor-git-connector.md).

![](assets/git-bulk-importer-import-all.png)


## Experience Manager Guides fügt MCP-Unterstützung für die Integration des KI-Assistenten hinzu

Experience Manager Guides unterstützt jetzt die Integration von MCP (Model Context Protocol), sodass KI-Assistenten wie Anthropic Claude eine direkte Verbindung zu Ihrer AEM Guides-Umgebung herstellen können.

Über einen einzigen MCP-Endpunkt können authentifizierte Benutzer Themen und Zuordnungen verwalten, Baselines erstellen und exportieren und Berichte in natürlicher Sprache generieren, während sie gleichzeitig mit ihren bestehenden AEM-Berechtigungen arbeiten. Dadurch werden sich wiederholende, navigationsintensive Aufgaben vermieden und Dokumentations-Teams können effizienter zwischen Chat-Anwendungen und MCP-fähigen Entwickler-Tools wie Cursor und Visual Studio Code arbeiten. Weitere Informationen finden Sie unter [Verwenden des Adobe Experience Manager Guides MCP-Servers](../install-conf-guide/conf-aem-guides-mcp.md).


## Verbesserungen bei Überprüfungen

### Delegieren einer Prüfungsaufgabe an einen anderen Prüfer

Validierungsverantwortliche können jetzt einem anderen Benutzer empfehlen, sich bei einer Überprüfung zu beteiligen, bevor sie an den Autor zurückgesendet wird, indem sie die neue Option **Delegieren** verwenden, die für eine Prüfungsaufgabe verfügbar ist. Dies ist nützlich, wenn ein Teil des Inhalts außerhalb des Fachwissens des Reviewers liegt oder wenn vor Abschluss der Überprüfung eine zweite Stellungnahme erforderlich ist, ohne die Anfrage an einen Projektadministrator weiterleiten zu müssen.

Bei Auswahl der Option Delegieren wird die Empfehlung an den Autor gesendet, der entscheidet, ob der empfohlene Reviewer zur Aufgabe hinzugefügt wird. Weitere Informationen über [Delegieren einer Prüfungsaufgabe an einen anderen Prüfer](../user-guide/review-complete-review-tasks.md#delegate-a-review-task-to-another-reviewer).

![](assets/review-delegate-option.png){width="350"}

### Aufgabenbeschreibung jetzt in der Überprüfungs-Benutzeroberfläche sichtbar

Reviewer können die Aufgabenbeschreibung jetzt direkt in der Überprüfung anzeigen, anstatt sich nur auf die Benachrichtigungs-E-Mail zu verlassen. Die beim Erstellen einer Prüfungsaufgabe eingegebene Beschreibung wird jetzt im Dialogfeld Prüfungsdetails angezeigt, auf das über das Symbol **Info** sowohl in der Benutzeroberfläche als auch im Editor zugegriffen werden kann.

Dadurch erhalten Validierungsverantwortliche während der gesamten Überprüfung Zugriff auf Anweisungen, Umfang und Schwerpunkte. Weitere Informationen finden Sie unter [Themen zur Überprüfung senden](../user-guide/review-send-topics-for-review.md).

![](assets/review-details.png){width="350"}

### Benutzeridentifizierung in der Tagging-Liste während der Überprüfung

Beim Tagging von Benutzern in Prüfungskommentaren oder Antworten zeigt das Dropdown-Menü für das Tagging jetzt die E-Mail-Adresse jedes Benutzers zusammen mit seiner Benutzer-ID an. Dies erleichtert die Identifizierung und Auswahl des richtigen Reviewers, insbesondere in großen Unternehmen, in denen Anzeigenamen allein mehrdeutig sein können.

Wenn keine E-Mail-Adresse verfügbar ist, wird stattdessen die Benutzer-ID angezeigt. Weitere Informationen zum Arbeiten mit der Überprüfungs-Benutzeroberfläche finden Sie unter [Taggen von Aufgabenbenutzenden in einem Kommentar](../user-guide/review-topics.md#tag-task-users-in-a-comment).


### Alle Prüfungsaufgaben für ein Thema anzeigen

Autoren können jetzt alle Prüfungsaufgaben (ob geöffnet oder geschlossen), die mit dem aktuell geöffneten Thema verknüpft sind, direkt im Kommentarbedienfeld anzeigen. In einer Dropdown-Liste werden alle Prüfungsaufgaben, zu denen das Thema gehört, sowie der Status und das Projekt jeder Aufgabe aufgelistet. Außerdem können Sie zwischen ihnen wechseln, um Kommentare anzuzeigen, ohne das Thema verlassen oder die Prüfungsprojekte wechseln zu müssen. Weitere Informationen über [Alle Prüfungsaufgaben für ein Thema anzeigen](../user-guide/review-address-review-comments.md#view-all-review-tasks-for-a-topic).

![](assets/review-task-selection-dropdpwn.png){width="350"}

### Verbesserte Prüferfahrung mit DITAVAL-Bedingungen

Wenn eine Prüfungsaufgabe eine oder mehrere angehängte DITAVAL-Dateien enthält, stellt das Bedienfeld Bedingungen jetzt jede Bedingung als Umschalter bereit, der so voreingestellt ist, dass er mit den angehängten DITAVAL-Dateien übereinstimmt, sodass die Prüfer den Inhalt so sehen, wie der Initiator der Überprüfung es beabsichtigt hatte. Durch Deaktivieren eines Umschalters wird dieser Inhalt vor der Überprüfung verborgen. Durch Aktivieren wird er wiederhergestellt.

Weitere Informationen finden Sie [Bereich „Bedingungen“ mit DITAVAL-basierten Bedingungen](../user-guide/review-topics.md#conditions-panel-with-ditaval-based-conditions).

![](assets/review-condition-panel-ditaval.png){width="350"}

## Verbesserungen beim Veröffentlichen

### Verwenden von Ausgabevorgaben als Vorlagen

Admins können jetzt Ausgabevorgaben als Vorlagen festlegen und über die Zuordnungskonsole standardisierte Konfigurationen für alle Zuordnungen in einem Ordnerprofil mit einer einzigen Aktion anwenden. Wenn eine Vorlage angewendet wird, zeigt das System die Anzahl der betroffenen Karten an, sodass Administratoren vor dem Rollout die volle Sichtbarkeit haben. Um die Konsistenz zu wahren, können Vorlagenvorgaben nur von Admins geändert werden, und die Ausgabegenerierung ist für Vorlagenvorgaben deaktiviert (es sei denn, die Ausgabe wurde bereits generiert, bevor die Vorgaben als Vorlage festgelegt wurden).

Weitere Informationen finden Sie unter [Konfigurieren von Vorlagenvoreinstellungen für die Ausgabegenerierung](../install-conf-guide/template-presets-output-generation.md).

### Validieren der Inhaltsqualität mit einer Konsistenzprüfung des Inhalts

Die Konsistenzprüfung von Inhalten hilft vor der Veröffentlichung, die Inhaltsqualität in allen DITA-Zuordnungen zu überprüfen. Admins können wiederverwendbare Konsistenzprüfungs-Voreinstellungen erstellen, indem sie Prüfungen auf fehlerhafte Links, doppelte IDs und die Schematron-Validierung kombinieren.

Autoren können eine Konsistenzprüfung für eine DITA-Zuordnung oder eine ausgewählte Grundlinie ausführen, um einen konsolidierten Bericht zu Problemen in allen zugehörigen Themen und Zuordnungen zu generieren. Weitere Informationen finden Sie unter [Ausführen einer Konsistenzprüfung auf einer Karte](../user-guide/map-editor-other-features.md#run-health-check-on-a-map).


## Verbesserungen an der Übersetzung

### Angeben eines benutzerdefinierten Ordnerpfads für Übersetzungsprojekte

Beim Senden von Inhalten für die Übersetzung können Sie jetzt den Ordner auswählen, in dem ein neues Übersetzungsprojekt erstellt wird, anstatt dass alle Projekte standardmäßig an einem einzigen Speicherort unter `/content/projects` abgelegt werden. Dadurch wird eine überladene Projektstruktur vermieden und die Seitenladeleistung verbessert, wenn die Anzahl der Übersetzungsprojekte steigt.

Weitere Informationen finden Sie unter [Übersetzungsprojekt erstellen](../user-guide/translate-documents-web-editor.md#create-a-translation-project).

## Verbesserungen an Lerninhalten

Die folgenden Verbesserungen sind in dieser Version für die Funktion „Produktschulungen und Lerninhalte“ verfügbar:

- In der SCORM **Ausgabekonfiguration ist jetzt eine neue Registerkarte „Teilnehmererlebnis** verfügbar, auf der Sie konfigurieren können, wie Teilnehmer mit der SCORM-Ausgabe interagieren und durch diese navigieren. Die Einstellungen sind unter Allgemein, Navigation und Quiz organisiert, sodass Sie die Zugänglichkeit von Inhalten, den Navigationsfluss und das Quizverhalten für ein maßgeschneidertes Lernerlebnis steuern können.

  Unter **Navigation** können Sie jetzt steuern, ob die Schaltfläche **Weiter** auf einer Seite aktiviert oder deaktiviert ist, sodass Lernende nur fortfahren können, wenn bestimmte Bedingungen auf dieser Seite erfüllt sind, z. B. das Öffnen aller interaktiven Elemente, das Ansehen aller Medien und mehr. Weitere Informationen finden Sie unter [SCORM-Vorgabe konfigurieren](../learning-content/config-scorm-preset.md).

  ![](assets/learner-experience.png){width="650"}

- Sie können jetzt PDF-Downloads für Teilnehmer in der SCORM-Ausgabe aktivieren. Wenn diese Option aktiviert ist, wird ein PDF-Download-Symbol zur veröffentlichten SCORM-Ausgabe hinzugefügt, sodass Lernende eine PDF-Version des Kursinhalts als Offline-Referenz herunterladen können. Dies bietet eine größere Flexibilität beim Zugriff auf Kursmaterialien und gibt Autoren mehr Kontrolle über das veröffentlichte Erlebnis. Konfigurationsdetails und Voraussetzungen finden Sie unter [Erlauben Sie Lernenden, die Kursversion von PDF herunterzuladen](../learning-content/config-scorm-preset.md).

  ![](assets/pdf-icon.png){width="650"}

- In der veröffentlichten Ausgabe eines Kurses können Lernende jetzt die Option **Antworten überprüfen** verwenden, nachdem sie einen Quizversuch unternommen haben, um ihre gesendeten Antworten erneut zu überprüfen und festzustellen, welche Antworten richtig oder falsch waren. Erfahren Sie mehr über [Frageneigenschaften in einem Quiz](../learning-content/quiz-insert-questions.md#question-properties).

  ![](assets/review-answer-quiz.png){width="650"}

- In Fragen zur Wissensüberprüfung innerhalb eines Kurses wird jetzt die Schaltfläche **Erneut versuchen** angezeigt, wenn ein Teilnehmer eine falsche Antwort auswählt, sodass er die Frage erneut versuchen kann. Dieses Verhalten ist bei Einzel- und Mehrfachauswahl-Wissensüberprüfungen konsistent. Weitere Informationen finden Sie unter [Weitere Optionen im Menü Einfügen](../learning-content/lc-other-insert-options.md).

- Wenn ein HTML-Thema zu einer Lerngruppenzuordnung hinzugefügt wird, wird das `format="html"` jetzt automatisch zum entsprechenden `topicref` hinzugefügt, um eine korrekte Verarbeitung und Veröffentlichung unter DITA-OT 4.x sicherzustellen. Weitere Informationen finden Sie unter [Vorhandene Inhalte in Ihrem Kurs hinzufügen](../learning-content/manage-course.md#add-existing-content).

## API-Verbesserung

Diese Version führt neue Swagger-APIs für Asset-Management, Übersetzung und Veröffentlichung ein, die die Verbindung dieser Workflows mit Ihren bestehenden Tools und Systemen erleichtern. Weitere Informationen finden Sie unter [API-Aktualisierungen in Experience Manager Guides-Versionen](../api-reference/api-update-swagger.md).

