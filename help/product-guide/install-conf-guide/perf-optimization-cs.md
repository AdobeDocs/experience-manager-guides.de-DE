---
title: Empfehlungen zur Leistungsoptimierung für Cloud Service
description: Empfehlungen zur Leistungsoptimierung
feature: Performance Optimization
role: Admin
level: Experienced
exl-id: 6c9684d4-180f-4ccb-bfd6-6c82a8a7b720
source-git-commit: 82c93529b8535532cf50f6428c41a1881b24859e
workflow-type: tm+mt
source-wordcount: '152'
ht-degree: 5%
---
# Empfehlungen zur Leistungsoptimierung für Cloud Service {#id213BD0JG0XA}

Beachten Sie für die Leistungsoptimierung die folgenden Punkte:

- Informationen zur Optimierung von Inhalten und zur Indizierung finden Sie unter [Optimieren der Inhaltssuche und -indizierung](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/operations/indexing.html?lang=de) in der Dokumentation zu AEM.

- Patchen von Xerces-JAR bei Verwendung benutzerdefinierter DITA-OT-Dateien für die Veröffentlichung. Dies ist eine obligatorische Konfiguration, je nach Anwendungsfall. Diese Änderung ist nur erforderlich, wenn Sie benutzerdefinierte DITA-OT-Dateien für die Veröffentlichung der Ausgabe verwenden.

  *Erforderliche Konfiguration*: Ersetzen Sie die Xerces-JAR-Datei in Ihrem benutzerdefinierten DITA-OT-Paket durch die im Lieferumfang enthaltene OOTB. Die standardmäßige OOTB-`xercesImpl-2.11.0.jar`-Datei ist in der `/libs/fmdita/dita\_resources/DITA-OT.zip`-Datei verfügbar. Stellen Sie sicher, dass Sie die `xercesImpl-2.11.0.jar`-Datei so umbenennen, dass sie mit der alten Xerces-JAR-Datei übereinstimmt, die ersetzt wird. Dies kann zur Laufzeit erfolgen.

  Durch diese Änderung wird die Veröffentlichungszeit und die Speicherauslastung beim Veröffentlichen von DITA-Karten mit einer großen Anzahl von Themen reduziert.
