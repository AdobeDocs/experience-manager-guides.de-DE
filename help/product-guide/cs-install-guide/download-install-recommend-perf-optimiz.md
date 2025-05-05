---
title: Recommendations für Leistungsoptimierung
description: Recommendations für Leistungsoptimierung kennenlernen
exl-id: 92ac1f81-2f51-44b0-82c3-56b39e8f3027
feature: Performance Optimization
role: Admin
level: Experienced
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '149'
ht-degree: 0%

---

# Recommendations für Leistungsoptimierung {#id213BD0JG0XA}

Beachten Sie für die Leistungsoptimierung die folgenden Punkte:

- Informationen zur Optimierung von Inhalten und zur Indizierung finden Sie unter [Optimieren der Inhaltssuche und -indizierung](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/operations/indexing.html?lang=de) in der AEM-Dokumentation.

- Patchen von Xerces-JAR bei Verwendung benutzerdefinierter DITA-OT-Dateien für die Veröffentlichung. Dies ist eine obligatorische Konfiguration, je nach Anwendungsfall. Diese Änderung ist nur erforderlich, wenn Sie benutzerdefinierte DITA-OT-Dateien für die Veröffentlichung der Ausgabe verwenden.

  *Erforderliche Konfiguration*: Ersetzen Sie die Xerces-JAR-Datei in Ihrem benutzerdefinierten DITA-OT-Paket durch die im Lieferumfang enthaltene OOTB. Die standardmäßige Datei „OOTB xercesImpl-2.11.0.jar“ ist in der Datei &quot;/libs/fmdita/dita\_resources/DITA-OT.zip&quot; verfügbar. Stellen Sie sicher, dass Sie die Datei xercesImpl-2.11.0.jar so umbenennen, dass sie mit der alten Xerces-JAR-Datei übereinstimmt, die ersetzt wird. Dies kann zur Laufzeit erfolgen.

  Durch diese Änderung wird die Veröffentlichungszeit und die Speicherauslastung beim Veröffentlichen von DITA-Karten mit einer großen Anzahl von Themen reduziert.


**Übergeordnetes Thema:**&#x200B;[ Herunterladen und installieren](download-install.md)
