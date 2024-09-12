---
title: Erhöhen Sie die Übersetzungsleistung für Ihre DITA-Dateien in AEM Handbüchern
description: Best Practices, Tipps und Tricks zur Leistungssteigerung von DITA-Übersetzungsprojekten in AEM Guides
feature: Translation
role: User, Admin
author: Pulkit Nagpal (punagpal)
exl-id: d7e4f3ae-2143-4767-b7ab-c89f5e5eef59
source-git-commit: 18fe3cbb1439d489d243d98a546ef1095104a863
workflow-type: tm+mt
source-wordcount: '288'
ht-degree: 0%

---

# Best Practices für die Übersetzung in AEM Guides

Die Leistung für Ihr Übersetzungsprojekt kann mit der im Laufe der Zeit zunehmenden Übersetzungsaktivität im System abnehmen.

Jedes Übersetzungsprojekt generiert mehrere Benutzergruppen für den Zugriff, was zu einer Erhöhung der Anzahl der Benutzergruppen innerhalb des Systems führt. Wenn sich die Anzahl der Benutzergruppen erhöht, kann dies CRUD-Vorgänge im Zusammenhang mit Benutzerberechtigungen schrittweise verlangsamen, was sich möglicherweise auf die AEM insgesamt auswirken kann. Wenn Übersetzungsprojekte nach der Fertigstellung aktiv bleiben, kann sich dies negativ auf die Synchronisation von AEM und Übersetzungsanbieter auswirken.

**Die Befolgung der unten beschriebenen Best Practices trägt zur Aufrechterhaltung einer effizienten Umgebung bei.**

## Wenn Sie einen älteren Build als 4.6 (On-Premise) oder 2404 (Cloud) verwenden:

- Markieren Sie alle Projekte als &quot;Inaktiv&quot;, sobald die Übersetzung abgeschlossen und validiert ist. Das Projekt bleibt zur Überprüfung verfügbar und wird einfach als inaktiv markiert.
   - Die Durchführung dieser Schritte trägt dazu bei, die Gesamtleistung der Übersetzungen im guten Zustand zu halten.
     ![Inaktives Übersetzungsprojekt ](../assets/translation/translation-project-image1.png)

- Bei älteren Projektordnern, die als inaktiv, genehmigt und geprüft markiert sind, sollten gelöscht werden
   - Die Durchführung dieser Schritte trägt dazu bei, die Gesamtleistung der Übersetzung im guten Zustand zu erhalten, indem temporäre Übersetzungsdateien und Benutzergruppen, die mit diesem Projektordner verknüpft sind, bereinigt werden.
     ![Übersetzungsprojekt und -ordner löschen ](../assets/translation/translation-project-image2.png)


## Wenn Sie auf sind, erstellen Sie Version 4.6 oder 2404 oder höher:

Sie können weiterhin dieselben Schritte wie oben beschrieben ausführen. Ab Version 4.6/2404 führt AEM Guides eine Editoreinstellung für Administratoren ein, um das automatische Löschen von Übersetzungsprojekten zu deaktivieren.

Siehe: [Ein abgeschlossenes Übersetzungsprojekt automatisch löschen oder deaktivieren](https://experienceleague.adobe.com/en/docs/experience-manager-guides/using/user-guide/author-content/create-preview-topics/author-content-aem-guides/work-with-web-editor/translate-documents-web-editor#automatically-delete-or-disable-a-completed-translation-project)

![Automatisierte Einstellungen zum Löschen und Deaktivieren des Übersetzungsprojekts in AEM Guides ](../assets/translation/translation-project-image3.png)
