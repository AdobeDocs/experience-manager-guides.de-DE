---
title: Versionshinweise zu | Adobe Experience Manager Guides as a Cloud Service, Version April 2023
description: Version April 2023 von Adobe Experience Manager Guides as a Cloud Service
exl-id: 269e3a13-584d-4cff-a18a-d4fa89646a5a
feature: Release Notes
role: Leader
source-git-commit: 6d8c01f20f7b59fed92c404561b647d9ebecb050
workflow-type: tm+mt
source-wordcount: '381'
ht-degree: 0%

---

# Neue Funktionen in der Version April 2023 von Adobe Experience Manager Guides as a Cloud Service

Dieser Artikel behandelt die neuen und erweiterten Funktionen in der Version April 2023 von Adobe Experience Manager Guides (später *AEM Guides as a Cloud Service*).

Weitere Informationen zu den Upgrade-Anweisungen, der Kompatibilitätsmatrix und den in dieser Version behobenen Problemen finden Sie im Artikel [Versionshinweise](release-notes-2023-4-0.md) .

## Erweiterte Metadatenunterstützung beim PDF-Publishing

AEM Guides bietet jetzt erweiterte Unterstützung für die Metadaten, die den Metadaten in Ihrer PDF-Ausgabe zugeordnet sind. Die Metadatenoptionen enthalten Informationen zum Dokument und dessen Inhalt, z. B. den Namen des Autors, den Dokumenttitel, Schlüsselwörter, Copyright-Informationen und andere Datenfelder.

<img src="assets/pdf-metadata.png" alt=" Native PDF-Metadaten">

Sie können eine XMP-Datei importieren, und AEM Guides kann die Informationen aus der Datei auswählen. Sie haben auch die Möglichkeit, die Namen und Werte der Metadaten mithilfe des Dropdown-Menüs anzugeben. Sie können auch benutzerdefinierte Metadaten hinzufügen, indem Sie direkt in das Namensfeld eingeben.


## Verbessertes Bedienfeld für Gliederungsansichten

AEM Guides bietet ein verbessertes Bedienfeld für die Gliederungsansicht, in dem Sie eine hierarchische Ansicht der im Dokument verwendeten Elemente erhalten.

<img src="assets/select-element-content-outline-view_cs.png" alt=" Native PDF-Metadaten">

Die Gliederungsansicht bietet die folgenden Verbesserungen:

* Das Dropdown-Menü „Anzeigeoptionen“ wird oben im Bedienfeld „Gliederungsansicht“ angezeigt. Wenn ein Element eine ID, ein Attribut und einen Text hat, können Sie diese aus der Dropdown-Liste auswählen, um sie zusammen mit dem Element anzuzeigen. Die Attribute, die im Bereich Gliederungsansicht angezeigt werden können, werden durch die Einstellungen der Anzeigeattribute bestimmt, die von Ihrem Administrator im **Editor-Einstellungen“ konfiguriert**.

* Mithilfe der Suchfunktion können Sie nach einem Element anhand seines Namens, seiner ID, seines Textes oder seines Attributwerts suchen.


## Microservice-basierte Veröffentlichung für AEM Guides as a Cloud Service

AEM Guides as a Cloud Service bietet die Funktion, große Veröffentlichungsarbeitslasten gleichzeitig mit auf Microservices basierenden Veröffentlichungen auszuführen und die branchenführende Adobe I/O Runtime Server-lose Plattform zu nutzen.

In der April-Version können Sie jetzt mehrere Veröffentlichungsanfragen gleichzeitig ausführen und Massen-PDF-Ausgaben sehr effizient mithilfe der auf Microservices basierenden nativen PDF-Veröffentlichung generieren.
Weitere Informationen finden Sie unter [Konfigurieren einer neuen, auf Microservices basierenden Veröffentlichung für AEM Guides as a Cloud Service](../knowledge-base/publishing/configure-microservices.md).
