---
title: Native PDF | Konfigurieren des Knotenprozesses für die native PDF-Veröffentlichung
description: Erfahren Sie, wie Sie den Knotenprozess für die native PDF-Veröffentlichung konfigurieren
exl-id: f470939b-a5cb-4d28-92d1-7a0a52c4c637
feature: Output Generation
role: Admin
level: Experienced
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '118'
ht-degree: 1%

---

# Konfigurieren des Knotenprozesses für die native PDF-Veröffentlichung

Die native PDF-Veröffentlichung startet einen separaten NodeJs-Prozess, um die im Veröffentlichungsprozess generierten Dateien in eine endgültige PDF zu konvertieren. Möglicherweise müssen Sie die Konfigurationen dieses Knotenprozesses anpassen, bei dem native PDF-Veröffentlichungen ausgeführt werden, um verschiedene Szenarien zu unterstützen. Um beispielsweise größere Arbeitslasten auszuführen, sollten Sie die maximale Heap-Größe erhöhen, die für den erstellten NodeJs-Prozess verfügbar ist.

Verwenden Sie die Anweisungen unter [Konfigurationsüberschreibungen](../cs-install-guide/download-install-additional-config-override.md), um die Konfigurationsdatei zu erstellen. Geben Sie in der Konfigurationsdatei die folgenden Details (Eigenschaft) an:

| PID | Eigenschaftsschlüssel | Eigenschaftswert |
|---|---|---|
| `com.adobe.fmdita.config.ConfigManager` | `native.pdf.node.opts` | Zeichenfolgenwert zum Festlegen eines beliebigen `NODE_OPTIONS`.<BR> Standardwert: &quot;&quot; |
