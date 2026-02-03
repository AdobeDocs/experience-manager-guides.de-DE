---
title: Konfigurieren von Dokumentenstatusfiltern
description: Erfahren Sie, wie Sie Dokumentenstatusfilter konfigurieren
feature: Web Editor Configuration
role: Admin
level: Experienced
source-git-commit: 4942b914ff278ebcf09d00da32d6f9c7cc4d7ff9
workflow-type: tm+mt
source-wordcount: '251'
ht-degree: 0%

---

# Konfigurieren von Dokumentenstatusfiltern

Adobe Experience Manager Guides bietet die Funktion zum Durchsuchen einer Datei anhand ihres aktuellen Dokumentstatus. Sie können die Filtersuche verwenden, um Dateien über die Repository-Benutzeroberfläche zu suchen und Dateien zu durchsuchen.

Führen Sie die folgenden Schritte aus, um die Filter für den Dokumentstatus zu konfigurieren:

1. Melden Sie sich bei Adobe Experience Manager als Administrator an.
1. Klicken Sie oben auf den Adobe Experience Manager-Link und anschließend auf **Tools**.
1. Wählen Sie **Guides** aus der Liste der Tools und dann **Ordnerprofile** aus.
1. Öffnen Sie die **Globales Profil**-Kachel. Sie können auch eine bestimmte Ordnerprofilkachel auswählen, wenn diese Änderungen nicht global, sondern nur auf diesen Ordner angewendet werden sollen.
1. Navigieren Sie zu **XML-Editor-Konfiguration**.
1. Wählen Sie **oben** Symbol „Bearbeiten“ aus.
1. Wählen Sie das **Herunterladen**-Symbol aus, um die `ui\_config.json`-Datei auf Ihr lokales System herunterzuladen.
Informationen zur heruntergeladenen `ui\_config.json` finden Sie im folgenden Abschnitt:

       &quot;
       „repositoryFilters“: &lbrack;
       &lbrace;
       „title“: „Document state“,
       „property“: „jcr:content/metadata/docstate“,
       „children“: &lbrack;
       &lbrace;
       „title“: „draft“,
       „value“: „Entwurf“
       &rbrace;,
       &lbrace;
       „title“: „Bearbeiten“,
       „value“: „Bearbeiten“
       &rbrace;,
       &lbrace;
       „title“: „In-Review“,
       „value“: „In-Review“
       &rbrace;,
       &lbrace;
       „title“: „Approved“,
       „value“: „Approved“
       &rbrace;,
       &lbrace;
       „title“: „Überprüft“,
       „value“: „Überprüft“
       &rbrace;,
       &lbrace;
       „title“: „Done“,
       „value“: „Done“
       &rbrace;
       &rbrack;
       &rbrace;
       &rbrack;
       &quot;
   Dieser Ausschnitt stellt die in Experience Manager Guides verfügbaren Standardfilter für den Dokumentstatus dar.

1. Sie können die Filterwerte auf Grundlage des Workflows Ihrer Organisation anpassen. Um beispielsweise den benutzerdefinierten Dokumentstatus „Ausstehend **hinzuzufügen, fügen** den folgenden Eintrag unter `children` ein:

   ```
   {
       "title": "Pending",
       "value": "Pending"
   }
   ```

1. Speichern Sie die Datei nach der Aktualisierung und laden Sie sie hoch.

Die konfigurierten Filter werden im Bedienfeld **Filter** im Repository auf der Startseite angezeigt.

**Übergeordnetes Thema:**&#x200B;[&#x200B; Anpassen des Web-Editors](conf-web-editor.md)
