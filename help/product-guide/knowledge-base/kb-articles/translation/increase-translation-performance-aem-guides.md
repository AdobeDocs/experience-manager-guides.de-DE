---
title: Steigern der Übersetzungsleistung für DITA-Dateien in den AEM-Handbüchern
description: Best Practices, Tipps und Tricks zur Leistungssteigerung bei DITA-Übersetzungsprojekten in AEM Guides
feature: Translation
role: User, Admin
author: Pulkit Nagpal (punagpal)
exl-id: d7e4f3ae-2143-4767-b7ab-c89f5e5eef59
TQID: https://experienceleague.adobe.com/n6-b3-ZsOIueVYWgcm1NkDLKRAOwQhWxctbgj7Q6P1U
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 324
ht-degree: 0%

---

# Best Practices für die Übersetzung in AEM Guides

Die Leistung Ihres Übersetzungsprojekts kann mit zunehmender Übersetzungsaktivität im System abnehmen.

Bei jedem Übersetzungsprojekt werden mehrere Benutzergruppen für den Zugriff generiert, was zu einem Anstieg der Anzahl der Benutzergruppen innerhalb des Systems führt. Wenn die Anzahl der Benutzergruppen zunimmt, kann es CRUD-Vorgänge im Zusammenhang mit Benutzerberechtigungen schrittweise verlangsamen, was sich möglicherweise auf die Gesamtleistung von AEM auswirkt. Wenn Übersetzungsprojekte auch nach Abschluss des Vorgangs aktiv bleiben, kann sich dies negativ auf die Leistung der Synchronisierung von Übersetzungen zwischen AEM und dem Übersetzungsanbieter auswirken.

**Die Befolgung der unten beschriebenen Best Practices wird zur Aufrechterhaltung einer effizienten Umgebung beitragen.**

## Wenn Sie einen älteren Build als 4.6 (On-Premise) oder 2404 (Cloud) verwenden:

- Markieren Sie alle Projekte als „inaktiv“, sobald die Übersetzung abgeschlossen und genehmigt ist.Das Projekt steht weiterhin zur Überprüfung zur Verfügung und wird einfach als inaktiv markiert.
   - Die folgenden Schritte helfen, die Gesamtleistung der Übersetzung bei gutem Zustand zu erhalten.
     ![Inaktive Übersetzungsprojekt-](../assets/translation/translation-project-image1.png)

- Bei älteren Projekten sollte der Ordner, der als inaktiv markiert, genehmigt und überprüft ist, gelöscht werden
   - Die folgenden Schritte helfen Ihnen, die Gesamtübersetzungsleistung in einem guten Zustand zu halten, indem sie temporäre Übersetzungsdateien und Benutzergruppen bereinigen, die mit diesem Projektordner verknüpft sind.
     ![Übersetzungsprojekt und Ordner löschen &#x200B;](../assets/translation/translation-project-image2.png)


## Wenn Sie eingeschaltet sind, erstellen Sie 4.6 oder 2404 oder höher:

Sie können weiterhin die oben genannten Schritte ausführen. Ab Version 4.6/2404 führt AEM Guides eine Editor-Einstellung für Admins ein, um das automatische Löschen von Übersetzungsprojekten zu deaktivieren.

Verweis : [Ein abgeschlossenes Übersetzungsprojekt automatisch löschen oder deaktivieren](https://experienceleague.adobe.com/en/docs/experience-manager-guides/using/user-guide/author-content/create-preview-topics/author-content-aem-guides/work-with-web-editor/translate-documents-web-editor#automatically-delete-or-disable-a-completed-translation-project)

![Automatisierte Einstellungen zum Löschen und Deaktivieren von Übersetzungsprojekten in AEM Guides &#x200B;](../assets/translation/translation-project-image3.png)
