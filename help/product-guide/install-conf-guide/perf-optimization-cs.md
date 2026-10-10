---
title: Empfehlungen zur Leistungsoptimierung für Cloud Service
description: Empfehlungen zur Leistungsoptimierung
feature: Performance Optimization
role: Admin
level: Experienced
exl-id: 6c9684d4-180f-4ccb-bfd6-6c82a8a7b720
product_v2:
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
    internal-label: Experience Manager
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
    internal-label: Experience Manager Guides
feature_v2:
  - id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
    internal-label: Configuration
subfeature_v2:
  - id: baa3aa24-d162-4a57-b73a-d27341145083
    internal-label: Performance optimization
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
level_v2:
  - id: d378ca77-2da1-4f39-ad92-1917fe974a38
    internal-label: Experienced
source-git-commit: 81a0e7f0736ba4970673dd87a888a4c60d3c1b4e
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
