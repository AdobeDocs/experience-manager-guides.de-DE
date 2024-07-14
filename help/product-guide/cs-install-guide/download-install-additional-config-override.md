---
title: Konfigurationsüberschreibungen
description: Erfahren Sie, wie Konfigurationsüberschreibungen
exl-id: dc5f81f7-5b0a-4d12-a944-ba66b0239d5c
feature: Installation
role: Admin
level: Experienced
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '93'
ht-degree: 0%

---

# Konfigurationsüberschreibungen {#id216IFC003XA}

Für Konfigurationsaktualisierungen sollte der folgende allgemeine Ansatz verwendet werden:

1. Greifen Sie auf das Git-Repository von Cloud Manager zu.

1. Erstellen Sie eine neue JSON-Datei am folgenden Speicherort:

   src/main/content/jcr\_root/apps/fmditaCustom/config/

1. Benennen Sie die Datei im folgenden Format:

   $\{PID\}.cfg.json

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


**Übergeordnetes Thema:**[ Herunterladen und Installieren](download-install.md)
