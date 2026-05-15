---
title: Benutzerverwaltung und Sicherheit
description: Erfahren Sie, wie Benutzerverwaltung und Sicherheit funktionieren
exl-id: 10ab0f3c-97dc-4293-ab73-75b438c03d99
feature: User Management
role: Admin
level: Experienced
TQID: https://experienceleague.adobe.com/QpFE9DrZXxZTfONQFEtNCZCBRu5zOhjFkf1PcVj9sfU
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2:
  - id: a3bd6397-2eb2-4908-a61c-226e26855dca
  - id: b1210526-416b-4ef6-bcc0-1692e99f30e9
  - id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
  - id: d90290ec-3e61-4ebd-8649-bcafe0836803
  - id: e88e74c7-6080-446a-8eb0-496f1ac5f7e6
subfeature_v2:
  - id: a7a242db-c88c-4e44-818b-bfb4ef92efdf
  - id: c8841798-1a28-4264-a46a-984860f8e6f6
  - id: f7774ebe-aec9-42b6-97e4-5002acdc712e
  - id: f9dbea21-a714-40dd-bc90-080d8046c93f
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: cdd65e7e-8839-44a2-bc21-0e03623b5dd1
  - id: d095671a-1355-40aa-8b5f-06c33c68080b
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 728
ht-degree: 12%

---

# Benutzerverwaltung und Sicherheit {#id181AED00G5Z}

Um auf Funktionen in der AEM Guides zuzugreifen und sie zu konfigurieren, müssen Sie Benutzende erstellen. Diesen Benutzern können dann Berechtigungen für den Zugriff auf alle oder bestimmte Funktionen in der AEM Guides zugewiesen werden. Erfahren Sie, wie Sie die Benutzerautorisierung konfigurieren und verwalten und wie die Authentifizierung und Autorisierung in AEM funktioniert.

Die folgenden Themen in der Dokumentation zu AEM helfen Ihnen, die Konzepte und Funktionen der Benutzerverwaltung und Sicherheit zu verstehen:

- [AEM-Benutzende, -Gruppen und -Berechtigungen](https://experienceleague.adobe.com/docs/experience-manager-learn/cloud-service/accessing/aem-users-groups-and-permissions.html)

- [Benutzerverwaltung und Sicherheit](https://experienceleague.adobe.com/docs/experience-manager-65/administering/security/security.html?lang=de)


## Von AEM Guides erstellte Benutzergruppen {#id181TF0K0MHT}

AEM Guides bietet drei vordefinierte Gruppen. Diese Gruppen sind: *Autoren*, *Prüfer* und *Herausgeber*. Je nach Gruppe, der eine Benutzerin oder ein Benutzer zugeordnet ist, können sie bzw. er bestimmte Aufgaben ausführen. Beispielsweise kann eine Veröffentlichungsaufgabe nur von einem Herausgeber, nicht aber von einem Autor oder einem Prüfer ausgeführt werden. Auf ähnliche Weise kann ein Autor ein neues Thema erstellen und ein Prüfer kann nur ein Thema überprüfen.

>[!TIP]
>
> Best Practices *Festlegen von* finden Sie im Abschnitt „Berechtigungen“ im Handbuch zu Best Practices.

In der folgenden Tabelle sind verschiedene Aufgaben sowie die Gruppen aufgeführt, die diese Aufgaben ausführen können:

| Aufgabe | Autoren | Prüfer | Herausgeber |
|----|-------|---------|----------|
| DITA-Thema erstellen | Ja |   | Ja |
| DITA-Map erstellen | Ja |   | Ja |
| Zuordnen von Sammlungen | Ja |   | Ja |
| Bewertungsaufgabe erstellen | Ja |   | Ja |
| Prüfungsthema[1](#fntarg_1) | Ja | Ja | Ja |
| Tastenauflösung | Ja |   | Ja |
| Auschecken/Einchecken | Ja |   | Ja |
| Thema bearbeiten | Ja |   | Ja |
| Thema verschieben | Ja |   | Ja |
| Themeneigenschaften bearbeiten | Ja |   | Ja |
| Kopieren | Ja |   | Ja |
| Löschen | Ja |   | Ja |
| Link freigeben | Ja |   | Ja |
| **Dokumentstatus** |  |  |  |
| Dokumentenstatusprofil erstellen/bearbeiten |   |   | Ja |
| Dokumentstatus ändern[2](#fntarg_2) | Ja | Ja | Ja |
| **In der DITA-Zuordnungskonsole verfügbare Funktionen \(Registerkarte „Ausgabevorgaben“\)** |  |  |  |
| Generieren |   |   | Ja |
| Bearbeiten |   |   | Ja |
| Duplizieren |   |   | Ja |
| Erstellen |   |   | Ja |
| Vorgabe löschen |   |   | Ja |
| **In der DITA-Zuordnungskonsole verfügbare Funktionen \(Registerkarte „Ausgaben“\)** |  |  |  |
| Erzeugte Ausgabe anzeigen | Ja |   | Ja |
| **In der DITA-Zuordnungskonsole verfügbare Funktionen \(Registerkarte Themen\)** |  |  |  |
| Bewertungsaufgabe erstellen | Ja |   | Ja |
| Bearbeiten | Ja |   | Ja |
| **In der DITA-Zuordnungskonsole verfügbare Funktionen \(Registerkarte „Baselines“\)** |  |  |  |
| Erstellen |   |   | Ja |
| Bearbeiten |   |   | Ja |
| Duplizieren |   |   | Ja |
| Remove |   |   | Ja |
| DITA Map Console \(Registerkarte „Berichte“\) | Ja |   | Ja |
| **In der DITA-Zuordnungskonsole verfügbare Funktionen \(Bedingungsvorgaben\)** |  |  |  |
| Erstellen/Bearbeiten einer Bedingungsvorgabe |   |   | Ja |

## Zusätzliche Hinweise zu Benutzergruppen

Die folgende Liste enthält einige Empfehlungen und Punkte zu Benutzergruppen und entsprechenden Berechtigungen:

- Wenn Sie möchten, dass ein Benutzer den Übersetzungs- oder Review-Workflow startet, stellen Sie sicher, dass der Benutzer Mitglied der Gruppe *Herausgeber* und *Projekte-Administratoren* ist.

- Benutzer müssen über die Berechtigungen zum Lesen, Erstellen, Löschen und Ändern für die Ordner der Quell- und Zielsprache verfügen, an denen sie arbeiten müssen.

- Wenn Sie ein Projekt erstellen, sind Sie Eigentümer des Projekts mit &quot;*&quot;-*. Damit andere Benutzende in einem Projekt ihre Team-Mitglieder sehen, Aufgaben erstellen oder Workflows erstellen können, müssen sie Lesezugriff auf `/home/users`- und `/home/groups` haben. Lesezugriff auf `/home/users`- und `/home/groups`-Knoten kann beispielsweise erteilt werden, indem der `projects-users` Lesezugriff gewährt wird.

- *Reviewer* können über die Projektkonsole oder über einen Benachrichtigungslink im Posteingang auf Prüfungskommentare zu einem zu überprüfenden Thema zugreifen und diese hinzufügen. Außerdem ist dieser Zugriff nur bis zum Zeitpunkt verfügbar, zu dem die Prüfungsaufgabe geöffnet ist.

- Standardmäßig erhalten *Herausgeber* Zugriff und Berechtigungen für die folgenden Ordner in DAM:

   - `/content/fmdita` -\> Lesen und Schreiben

   - `/content/dam/fmdita-outputs` -\> Lesen und Schreiben

   - `/content/output/sites` -\> Lesen und Schreiben

  Sie müssen Ihrem Herausgeber explizite Lese- und Schreibberechtigungen erteilen, wenn Sie einen anderen Speicherort außer den oben genannten standardmäßigen Veröffentlichungsspeicherorten verwenden.

- Alle Benutzer unter *Autoren*, *Reviewer* und *Publisher* haben Lesezugriff auf alle Inhalte in DAM.

- Berechtigungen auf Ordnerebene müssen Benutzern über die Seite Benutzerverwaltung zugewiesen werden.

- Wenn Sie möchten, dass Ihre Benutzerinnen und Benutzer Suchvorgänge für DAM durchführen können, sollten Sie Ihre Benutzerinnen und Benutzer zu einem Mitglied der Gruppe *dam-users* machen.

- Wenn Sie einem Benutzer Administratorrechte gewähren möchten, können Sie dies tun, indem Sie ihm Zugriff über AEM-Standardgruppen wie *Administratoren*, *Projekte-Administratoren* oder OSGi-Konfiguration \(Felix Console\) gewähren.

- Wenn Sie einem Benutzer die Rechte zum Ändern eines Dokumentstatus erteilen möchten, stellen Sie sicher, dass Sie den Benutzer im Abschnitt „Statusübergang“ des Dokumentstatusprofils hinzufügen.

[1](#fnsrc_1) Wenn *Autoren* und *Herausgeber* zur Überprüfung eingeladen sind.[2](#fnsrc_2) Abhängig von den Rechten, die dem Benutzer im Dokumentstatusprofil gewährt wurden.
