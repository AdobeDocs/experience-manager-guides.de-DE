---
title: Konfigurationsüberschreibungen für Cloud Service
description: Erfahren Sie, wie Sie Konfigurations-Überschreibungen vornehmen
feature: Installation
role: Admin
level: Experienced
exl-id: baf48913-ced7-444f-a125-661c0213d847
source-git-commit: 82c93529b8535532cf50f6428c41a1881b24859e
workflow-type: tm+mt
source-wordcount: '91'
ht-degree: 0%
---
# Konfigurationsüberschreibungen für Cloud Service {#id216IFC003XA}

Für alle Konfigurationsaktualisierungen in Experience Manager Guides as a Cloud Service sollte der folgende allgemeine Ansatz verwendet werden:

1. Greifen Sie auf das Git-Repository Ihrer Cloud Manager zu.

1. Erstellen Sie eine neue JSON-Datei am folgenden Speicherort:

   `src/main/content/jcr\_root/apps/fmditaCustom/config/`

1. Benennen Sie die Datei im folgenden Format:

   `$\{PID\}.cfg.json`

   Hier ist die PID die Prozess-ID der Konfiguration.

1. Fügen Sie Eigenschaften in der JSON-Datei im folgenden Format hinzu:

   ```
   {
      "aem.adminuname": "updatedUserjson",
      "valid.characters": "[-a-zA-Z0-9_@$]",
      "dita.serialization": true
   }
   ```

1. Übertragen Sie die Änderungen und führen Sie die Cloud Manager-Pipeline aus, um die aktualisierte Konfiguration bereitzustellen.
