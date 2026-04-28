---
title: Nativer PDF | Konfigurieren des Knotenprozesses für die native Veröffentlichung von PDF
description: Erfahren Sie, wie Sie den Knotenprozess für die native Veröffentlichung von PDF konfigurieren
feature: Output Generation
role: Admin
level: Experienced
exl-id: f470939b-a5cb-4d28-92d1-7a0a52c4c637
source-git-commit: ccaf2ead1a9a24ab822298c6b9ef6866a1c32e8c
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
