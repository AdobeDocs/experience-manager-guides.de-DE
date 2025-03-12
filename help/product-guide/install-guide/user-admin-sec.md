---
title: Benutzerverwaltung und Sicherheit
description: Erfahren Sie, wie Benutzerverwaltung und Sicherheit funktionieren
exl-id: 1269a652-5261-413d-9ea0-b4f75003e9d8
feature: User Management
role: Admin
level: Experienced
source-git-commit: 9b657b0530db8fafe3bb6d30a9002791acf8f226
workflow-type: tm+mt
source-wordcount: '710'
ht-degree: 10%

---

# Benutzerverwaltung und Sicherheit {#id181AED00G5Z}

Um auf Funktionen in AEM Guides zuzugreifen und sie zu konfigurieren, müssen Sie Benutzende erstellen. Diesen Benutzern können dann Berechtigungen für den Zugriff auf alle oder bestimmte Funktionen in AEM Guides zugewiesen werden. Erfahren Sie, wie Sie die Benutzerautorisierung konfigurieren und verwalten und wie die Authentifizierung und Autorisierung in AEM funktioniert.

Die folgenden Themen in der Dokumentation zu AEM helfen Ihnen, die Konzepte und Funktionen der Benutzerverwaltung und Sicherheit zu verstehen:

- [Benutzer und Gruppen in AEM](https://helpx.adobe.com/experience-manager/6-5/sites/administering/using/security.html#UsersandGroupsinAEM)

- [Berechtigungen in AEM](https://helpx.adobe.com/de/experience-manager/6-5/sites/administering/using/security.html#PermissionsinAEM)

- [Verwalten von Benutzern und Gruppen](https://helpx.adobe.com/experience-manager/6-5/sites/administering/using/security.html#ManagingUsersandGroups)

- [Verwalten von Berechtigungen](https://helpx.adobe.com/experience-manager/6-5/sites/administering/using/security.html#ManagingPermissions)


## Von AEM Guides erstellte Benutzergruppen {#id181TF0K0MHT}

AEM Guides bietet drei vordefinierte Gruppen. Diese Gruppen sind: *Autoren*, *Prüfer* und *Herausgeber*. Je nach Gruppe, der eine Benutzerin oder ein Benutzer zugeordnet ist, können sie bzw. er bestimmte Aufgaben ausführen. Beispielsweise kann eine Veröffentlichungsaufgabe nur von einem Herausgeber, nicht aber von einem Autor oder einem Prüfer ausgeführt werden. Auf ähnliche Weise kann ein Autor ein neues Thema erstellen und ein Prüfer kann nur ein Thema überprüfen.

>[!TIP]
>
> Best Practices *Festlegen von Benutzerberechtigungen finden Sie* Abschnitt „Berechtigungen“ im Best Practices-Handbuch.

In der folgenden Tabelle sind verschiedene Aufgaben sowie die Gruppen aufgeführt, die diese Aufgaben ausführen können:

| Aufgabe | Autoren | Prüfer | Herausgeber |
|----|-------|---------|----------|
| DITA-Thema erstellen | Ja |   | Ja |
| DITA-Map erstellen | Ja |   | Ja |
| Zuordnen von Sammlungen | Ja |   | Ja |
| Bewertungsaufgabe erstellen | Ja |   | Ja |
| Prüfungsthema[1](#fntarg_1) | Ja | Ja | Ja |
| Tastenauflösung | Ja |   | Ja |
| In FrameMaker öffnen | Ja |   | Ja |
| Auschecken/Einchecken | Ja |   | Ja |
| Thema bearbeiten | Ja |   | Ja |
| Thema verschieben | Ja |   | Ja |
| Themeneigenschaften bearbeiten | Ja |   | Ja |
| Kopieren | Ja |   | Ja |
| Löschen | Ja |   | Ja |
| Link freigeben | Ja |   | Ja |
| **Dokumentstatus** |
| Dokumentenstatusprofil erstellen/bearbeiten |   |   | Ja |
| Dokumentstatus ändern[2](#fntarg_2) | Ja | Ja | Ja |
| **In der DITA-Zuordnungskonsole verfügbare Funktionen \(Registerkarte „Ausgabevorgaben“\)** |
| Generieren |   |   | Ja |
| Bearbeiten |   |   | Ja |
| Duplizieren |   |   | Ja |
| Erstellen |   |   | Ja |
| Vorgabe löschen |   |   | Ja |
| **In der DITA-Zuordnungskonsole verfügbare Funktionen \(Registerkarte „Ausgaben“\)** |
| Erzeugte Ausgabe anzeigen | Ja |   | Ja |
| **In der DITA-Zuordnungskonsole verfügbare Funktionen \(Registerkarte Themen\)** |
| Bewertungsaufgabe erstellen | Ja |   | Ja |
| Bearbeiten | Ja |   | Ja |
| **In der DITA-Zuordnungskonsole verfügbare Funktionen \(Registerkarte „Baselines“\)** |
| Erstellen |   |   | Ja |
| Bearbeiten |   |   | Ja |
| Duplizieren |   |   | Ja |
| Remove |   |   | Ja |
| DITA Map Console \(Registerkarte „Berichte“\) | Ja |   | Ja |
| **In der DITA-Zuordnungskonsole verfügbare Funktionen \(Bedingungsvorgaben\)** |
| Erstellen/Bearbeiten einer Bedingungsvorgabe |   |   | Ja |

## Zusätzliche Hinweise zu Benutzergruppen

Die folgende Liste enthält einige Empfehlungen und Punkte zu Benutzergruppen und entsprechenden Berechtigungen:

- Wenn Sie möchten, dass ein Benutzer den Übersetzungs- oder Review-Workflow startet, stellen Sie sicher, dass der Benutzer Mitglied der Gruppe *Herausgeber* und *Projekte-Administratoren* ist.

- Benutzer müssen über die Berechtigungen zum Lesen, Erstellen, Löschen und Ändern für die Ordner der Quell- und Zielsprache verfügen, an denen sie arbeiten müssen.

- Wenn Sie ein Projekt erstellen, sind Sie Eigentümer des Projekts mit &quot;*&quot;-*. Damit andere Benutzende in einem Projekt ihre Team-Mitglieder sehen, Aufgaben erstellen oder Workflows erstellen können, müssen sie Lesezugriff auf `/home/users`- und `/home/groups` haben. Lesezugriff auf `/home/users`- und `/home/groups`-Knoten kann beispielsweise erteilt werden, indem der `projects-users` Lesezugriff gewährt wird.

- *Reviewer* können über die Projektkonsole oder über einen Benachrichtigungslink im Posteingang auf Prüfungskommentare zu einem zu überprüfenden Thema zugreifen und diese hinzufügen. Außerdem ist dieser Zugriff nur bis zum Zeitpunkt verfügbar, zu dem die Prüfungsaufgabe geöffnet ist.

- Standardmäßig erhalten *Herausgeber* Zugriff und Berechtigungen für die folgenden Ordner in DAM:

   - ``/var/dxml``-\> Lesen und Schreiben

   - `/content/dam/fmdita-outputs` -\> Lesen und Schreiben

   - `/content/output/sites` -\> Lesen und Schreiben

  Sie müssen Ihrem Herausgeber explizite Lese- und Schreibberechtigungen erteilen, wenn Sie einen anderen Speicherort außer den oben genannten standardmäßigen Veröffentlichungsspeicherorten verwenden.

- Alle Benutzer unter *Autoren*, *Reviewer* und *Publisher* haben Lesezugriff auf alle Inhalte in DAM.

- Berechtigungen auf Ordnerebene müssen Benutzern über die Seite Benutzerverwaltung zugewiesen werden.

- Wenn Sie möchten, dass Ihre Benutzerinnen und Benutzer Suchvorgänge für DAM durchführen können, sollten Sie Ihre Benutzerinnen und Benutzer zu einem Mitglied der Gruppe *dam-users* machen.

- Wenn Sie einem Benutzer Administratorrechte gewähren möchten, können Sie dies tun, indem Sie ihm Zugriff über AEM-Standardgruppen wie *Administratoren*, *Projekte-Administratoren* oder OSGi-Konfiguration \(Felix Console\) gewähren.

- Wenn Sie einem Benutzer die Rechte zum Ändern eines Dokumentstatus erteilen möchten, stellen Sie sicher, dass Sie den Benutzer im Abschnitt „Statusübergang“ des Dokumentstatusprofils hinzufügen.

[1](#fnsrc_1) Wenn *Autoren* und *Herausgeber* zu einer Überprüfung eingeladen werden.[2](#fnsrc_2) Abhängig von den Berechtigungen, die dem Benutzer im Dokumentstatusprofil gewährt wurden.
