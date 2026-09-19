---
title: Nativer PDF | Konfigurieren des Knotenprozesses für die native Veröffentlichung von PDF
description: Erfahren Sie, wie Sie den Knotenprozess für die native Veröffentlichung von PDF konfigurieren
feature: Output Generation
role: Admin
level: Experienced
exl-id: 5321c785-8259-4ee2-9ada-ee70fb99b4fd
source-git-commit: 82c93529b8535532cf50f6428c41a1881b24859e
workflow-type: tm+mt
source-wordcount: '122'
ht-degree: 1%
---
# Konfigurieren des Knotenprozesses für die native Veröffentlichung von PDF für Cloud Service

Die native PDF-Veröffentlichung startet einen separaten NodeJs-Prozess, um die im Veröffentlichungsprozess generierten Dateien in eine endgültige PDF zu konvertieren. Möglicherweise müssen Sie die Konfigurationen dieses Knotenprozesses anpassen, bei dem die native PDF-Veröffentlichung ausgeführt wird, um verschiedene Szenarien zu unterstützen. Um beispielsweise größere Arbeitslasten auszuführen, sollten Sie die maximale Heap-Größe erhöhen, die für den erstellten NodeJs-Prozess verfügbar ist.

Verwenden Sie die Anweisungen unter [Konfigurationsüberschreibungen](../install-conf-guide/download-install-config-override.md), um die Konfigurationsdatei zu erstellen.Geben Sie in der Konfigurationsdatei die folgenden Details (Eigenschaft) an:

| PID | Eigenschaftsschlüssel | Eigenschaftswert |
|---|---|---|
| `com.adobe.fmdita.config.ConfigManager` | `native.pdf.node.opts` | Zeichenfolgenwert zum Festlegen eines beliebigen `NODE_OPTIONS`.<BR> Standardwert: &quot;&quot; |
