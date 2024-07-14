---
title: Versionshinweise | Adobe Experience Manager Guides as a Cloud Service, Version April 2023
description: Adobe Experience Manager Guides as a Cloud Service-Version vom April 2023
exl-id: 269e3a13-584d-4cff-a18a-d4fa89646a5a
feature: Release Notes
role: Leader
source-git-commit: 6d8c01f20f7b59fed92c404561b647d9ebecb050
workflow-type: tm+mt
source-wordcount: '381'
ht-degree: 0%

---

# Neue Funktionen in der Adobe Experience Manager Guides as a Cloud Service-Version vom April 2023

In diesem Artikel werden die neuen und verbesserten Funktionen in der Adobe Experience Manager Guides-Version vom April 2023 (später als *AEM Guides as a Cloud Service* bezeichnet) behandelt.

Weitere Informationen zu den Upgrade-Anweisungen, der Kompatibilitätsmatrix und den in dieser Version behobenen Problemen finden Sie im Artikel [Versionshinweise](release-notes-2023-4-0.md) .

## Erweiterte Metadatenunterstützung beim PDF-Publishing

AEM Guides bietet jetzt erweiterte Unterstützung für die Metadaten, die den Metadaten in Ihrer PDF-Ausgabe zugeordnet sind. Die Metadatenoptionen enthalten Informationen über das Dokument und seinen Inhalt, wie z. B. den Namen des Autors, den Dokumenttitel, Schlüsselwörter, Copyright-Informationen und andere Datenfelder.

<img src="assets/pdf-metadata.png" alt=" native PDF-Metadaten">

Sie können eine XMP-Datei importieren und AEM Guides kann die Informationen aus der Datei auswählen. Sie können die Metadatennamen und -werte auch über das Dropdown-Menü angeben. Sie können auch benutzerdefinierte Metadaten hinzufügen, indem Sie direkt in das Namensfeld eingeben.


## Verbessertes Bedienfeld für die Gliederungsansicht

AEM Guides bietet ein verbessertes Bedienfeld für die Gliederungsansicht, in dem Sie die hierarchische Ansicht der im Dokument verwendeten Elemente erhalten.

<img src="assets/select-element-content-outline-view_cs.png" alt=" native PDF-Metadaten">

Die Gliederung bietet die folgenden Verbesserungen:

* Das Dropdown-Menü &quot;Anzeigeoptionen&quot;wird über dem Bedienfeld &quot;Konturansicht&quot;angezeigt. Wenn ein Element über eine ID, ein Attribut und Text verfügt, können Sie diese aus der Dropdown-Liste auswählen, um sie zusammen mit dem Element anzuzeigen. Die Attribute, die im Bedienfeld &quot;Umrissansicht&quot;angezeigt werden können, werden durch die Einstellungen für die Anzeigenattribute bestimmt, die von Ihrem Administrator in den **Editor-Einstellungen** konfiguriert wurden.

* Mithilfe der Suchfunktion können Sie nach einem Element anhand seines Namens, seiner ID, seines Textes oder seines Attributwerts suchen.


## Microservice-basierte Veröffentlichung für AEM Guides as a Cloud Service

AEM Guides as a Cloud Service bietet die Funktion zum gleichzeitigen Ausführen großer Veröffentlichungsarbeitslasten mit mikrodienstbasierter Veröffentlichung und zur Nutzung der branchenführenden Server-losen Adobe I/O Runtime-Plattform.

Ab der April-Version können Sie mehrere Veröffentlichungsanforderungen gleichzeitig ausführen und mithilfe des Microservice-basierten nativen PDF-Publishing sehr effizient Bulk-PDF-Ausgaben generieren.
Weitere Informationen finden Sie unter [Konfigurieren der neuen mikrodienstbasierten Veröffentlichung für AEM Guides as a Cloud Service](../knowledge-base/publishing/configure-microservices.md).
