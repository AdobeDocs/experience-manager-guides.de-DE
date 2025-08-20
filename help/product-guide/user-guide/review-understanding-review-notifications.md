---
title: Grundlegendes zu Prüfungsbenachrichtigungen
description: Erfahren Sie mehr über die verschiedenen Arten von Prüfungsbenachrichtigungen und deren Trigger in den verschiedenen Phasen des Prüfungs-Workflows in Experience Manager Guides.
feature: Reviewing
role: User
source-git-commit: b7648fe1d36de3c243ca5a55f42a41f7523056ce
workflow-type: tm+mt
source-wordcount: '676'
ht-degree: 0%

---

# Grundlegendes zu Prüfungsbenachrichtigungen

>[!IMPORTANT]
>
> Die in diesem Artikel beschriebenen neuen Funktionen werden standardmäßig mit der Version 2508 von Experience Manager Guides as a Cloud Services aktiviert. Überprüfungen, die vor der Migration erstellt wurden, sind nicht betroffen und verwenden weiterhin den früheren Workflow. Wenn Sie es vorziehen, die vorhandenen Funktionen ohne diese Aktualisierungen weiterhin zu verwenden, wenden Sie sich an Ihr Customer Success-Team, damit die neuen Funktionen deaktiviert werden.

Experience Manager Guides optimiert die Zusammenarbeit zwischen Autoren und Reviewern durch einen strukturierten Prüfungs-Workflow. Im Rahmen dieses Workflows spielen Benachrichtigungen eine wichtige Rolle dabei, alle Teilnehmer einer Prüfungsaufgabe auf dem Laufenden zu halten und auf Änderungen zu reagieren.

Bei jeder Durchführung einer Prüfungsaktion, wie z. B. einer Aufgabenzuweisung, eines Abschlusses oder einer Feedback-Aktualisierung, wird automatisch eine Benachrichtigung an die beteiligten Benutzer der Prüfungsaufgabe gesendet, um sie sofort darauf aufmerksam zu machen. Diese Benachrichtigungen werden in zwei Formaten gesendet:

- **AEM-**: Wird in der Benutzeroberfläche von AEM angezeigt.
- **E-Mail** Benachrichtigungen: werden direkt an den Posteingang der Benutzenden gesendet.

Die nachstehende Tabelle bietet einen Überblick über die verschiedenen Arten von Prüfungsbenachrichtigungen, welche Trigger sie ausführen und wie sie in verschiedenen Formaten angezeigt werden:


## Überprüfen von Benachrichtigungsformaten mit Beispielwerten

| **Aktion überprüfen** | **Benachrichtigungstitel (AEM)** | **Benachrichtigungstext (AEM)** | **E-Mail-Betreff** | **E-Mail-Benachrichtigungstext** | **Empfänger** |
|-----------------------------|--------------------------------------------------|-------------------------------------------------------------|--------------------------------------------------------|------------------------------------------------------------------------------------------------|-----------------------------|
| Überprüfungsaufgabe erstellt | Überprüfungsaufgabe zugewiesen: **Homepage-Überprüfung** | Zugewiesen durch **Autor** | Überprüfungsaufgabe zugewiesen: **Homepage-Überprüfung** | **Autor** hat im Projekt **WebDocs Revamp** eine Prüfungsaufgabe **Homepage Review** mit Fälligkeitsdatum **15. August 2025**. Sie wurden als Prüfer zugewiesen. | **Prüfer** |
| Feedback eingereicht | Feedback zur Überprüfung für **Homepage-Überprüfung** | Feedback von **Prüfer** | Feedback zur Überprüfung für **Homepage-Überprüfung** | **Reviewer** hat Feedback für Aufgabe **Homepage Review** im Projekt **WebDocs Revamp** gesendet. Bitte überprüfen Sie die Änderungen und nehmen Sie rechtzeitig vor Fälligkeitsdatum (15. **2025)**. | **Autor** oder **Initiator der Aufgabe** |
| Erneute Überprüfung angefordert | Erneute Überprüfung angefordert für **Homepage-Überprüfung** | Angefordert von **author** | Erneute Überprüfung für &quot;**Review“** Autor **angefordert** | **Autor** hat das Dokument für die Aufgabe **Homepage-Überprüfung** basierend auf Ihrem Feedback aktualisiert und fordert eine erneute Überprüfung an. Bitte rechtzeitig vor Fälligkeitsdatum (15. **2025)**. | **Prüfer** |
| Review Closed | Überprüfungsaufgabe geschlossen: **Homepage-Überprüfung** | Geschlossen von **author** | Überprüfungsaufgabe geschlossen: **Homepage-Überprüfung** | Die Überprüfungsaufgabe **Homepage Review** unter Projekt **WebDocs Revamp** wurde von **Author** geschlossen. | **Autor** oder **Initiator der Aufgabe** , **Reviewer** |
| Zuweisung von Reviewer aufgehoben | Zuweisung von der Prüfungsaufgabe aufgehoben **Homepage-Überprüfung** | Zuweisung von **author** aufgehoben | Zuweisung von der Prüfungsaufgabe aufgehoben **Homepage-Überprüfung** | Die Zuweisung von der Prüfungsaufgabe **Homepage Review** unter dem Projekt **WebDocs Revamp** wurde von **Author** aufgehoben. | **Prüfer** |
| Erwähnung von Tags | Erwähnt im Kommentar zur Prüfungsaufgabe für **Homepage-Überprüfung** | Erwähnt von **author** | Erwähnt im Kommentar zur Prüfungsaufgabe für **Homepage-Überprüfung** | Sie wurden in einem Kommentar zu Aufgabe **Homepage Review** unter **WebDocs Revamp** von **Author** erwähnt. **Kommentarauszug:** *„Bitte die Überschriftenstruktur entsprechend den Richtlinien für Barrierefreiheit aktualisieren.“* | **Erwähnter Benutzer** |
| Inhalt wurde während der Überprüfung aktualisiert | Thema in Prüfungsaufgabe aktualisiert **Homepage-Überprüfung** | Aktualisiert von **author** | Thema in Prüfungsaufgabe aktualisiert **Homepage-Überprüfung** | **Autor** hat die Themenversionen für die Prüfungsaufgabe (**)**. Bitte rechtzeitig vor Fälligkeitsdatum (15. **2025)**. | **Prüfer** |


In der obigen Tabelle stellt der **Text fett gedruckt** Beispielwerte dar und wird von vordefinierten Variablen gesteuert, die in Benachrichtigungen verwendet werden können.


Beispiel:

- **Homepage-Überprüfung** ist ein Beispielaufgabenname.
- **Priya** (Author) und **John** (Reviewer) sind Beispiele für Benutzernamen.
- **WebDocs Revamp** ist ein Beispielprojektname.
- **15. Aug** 2025 ist ein Musterfälligkeitsdatum.

Wenn eine Aufgabe Kommentare enthält, wird ein Kommentarausschnitt (ein Teil des vollständigen Kommentars) in die E-Mail-Benachrichtigung aufgenommen. Der Auszug wird in den folgenden Fällen angezeigt:

- Wenn Sie in einem Kommentar getaggt sind, wird ein Auszug des getaggten Kommentars in der E-Mail-Benachrichtigung angezeigt.
- Wenn ein Kommentar auf Aufgabenebene zu einer Prüfungsaufgabe hinzugefügt wird, der Sie angehören, wird ein Auszug dieses Kommentars in der E-Mail-Benachrichtigung angezeigt.

Eine vollständige Liste der vordefinierten Variablen und die Anpassung der Überprüfungsbenachrichtigungen finden Sie unter [Konfigurieren und Anpassen von Workflows](../cs-install-guide/customize-workflows.md#customize-email-and-aem-notification-templates).




**Übergeordnetes Thema:**&#x200B;[ Einführung zur Überprüfung](review.md)
