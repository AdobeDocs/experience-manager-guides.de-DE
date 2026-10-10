---
title: Konfigurieren von Dokumentenstatusfiltern
description: Erfahren Sie, wie Sie Dokumentenstatusfilter konfigurieren
feature: Web Editor Configuration
role: Admin
level: Experienced
exl-id: 6dee8479-770f-48d7-9939-5035388d16d8
product_v2:
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
    internal-label: Experience Manager
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
    internal-label: Experience Manager Guides
feature_v2:
  - id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
    internal-label: Configuration
subfeature_v2:
  - id: b0521e56-a0b2-40b6-bf47-ebc98751f9ba
    internal-label: Web Editor configuration
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
level_v2:
  - id: d378ca77-2da1-4f39-ad92-1917fe974a38
    internal-label: Experienced
source-git-commit: 81a0e7f0736ba4970673dd87a888a4c60d3c1b4e
workflow-type: tm+mt
source-wordcount: '218'
ht-degree: 0%
---
# Konfigurieren von Dokumentenstatusfiltern für Cloud Service

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

   ```
   "repositoryFilters": [
       {
       "title": "Document state",
       "property": "jcr:content/metadata/docstate",
       "children": [
           {
           "title": "Draft",
           "value": "Draft"
           },
           {
           "title": "Edit",
           "value": "Edit"
           },
           {
           "title": "In-Review",
           "value": "In-Review"
           },
           {
           "title": "Approved",
           "value": "Approved"
           },
           {
           "title": "Reviewed",
           "value": "Reviewed"
           },
           {
           "title": "Done",
           "value": "Done"
           }
       ]
       }
   ]
   ```

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

**Übergeordnetes Thema:**[ Editor anpassen](customize-overview.md)
