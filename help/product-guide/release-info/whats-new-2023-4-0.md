---
title: Versionshinweise | Adobe Experience Manager Guides as a Cloud Service, Version April 2023
description: Version April 2023 von Adobe Experience Manager Guides as a Cloud Service
exl-id: 269e3a13-584d-4cff-a18a-d4fa89646a5a
feature: Release Notes
role: Leader
TQID: https://experienceleague.adobe.com/c1aOcwHgxAs11yAalOnlW-ghsTP1Or32TnBwLsc59-M
product_v2: id: fae5e35a-80c9-4b94-9352-1a060a6aab1did: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2: id: a3bd6397-2eb2-4908-a61c-226e26855dca
subfeature_v2: id: d6596f3f-92a7-43ec-b444-237db6adad05
role_v2: id: f8a45b24-4be7-4f1b-909b-60d06b483a20
topic_v2: id: a004cc84-67b9-4a33-a3a7-8ec7273ef4dc
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 370
ht-degree: 0%

---

# Neue Funktionen in der Version April 2023 von Adobe Experience Manager Guides as a Cloud Service

Dieser Artikel behandelt die neuen und erweiterten Funktionen in der Version April 2023 von Adobe Experience Manager Guides (später *AEM Guides as a Cloud Service*).

Weitere Informationen zu den Upgrade-Anweisungen, der Kompatibilitätsmatrix und den in dieser Version behobenen Problemen finden Sie im Artikel [Versionshinweise](release-notes-2023-4-0.md) .

## Erweiterte Metadatenunterstützung bei der Veröffentlichung in PDF

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

In der April-Version können Sie jetzt mehrere Veröffentlichungsanfragen gleichzeitig ausführen und mithilfe der auf Microservices basierenden nativen PDF-Veröffentlichung sehr effizient PDF-Massenausgaben generieren.
Weitere Informationen finden Sie unter [Konfigurieren neuer Microservice-basierter Veröffentlichungen für AEM Guides as a Cloud Service](../knowledge-base/publishing/configure-microservices.md).
