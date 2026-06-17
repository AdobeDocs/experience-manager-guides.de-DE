---
title: Neue PDF-Engine aktivieren
description: Erfahren Sie, wie Sie die neue PDF-Engine in Experience Manager Guides aktivieren
feature: Web Editor Configuration
role: Admin
level: Experienced
source-git-commit: f3f30400f776f746427e257e2c937ff3413aa9ac
workflow-type: tm+mt
source-wordcount: '74'
ht-degree: 2%

---


# Konfigurieren der nativen PDF Engine v2

Die neue Publishing-Engine für Native PDF, d. h. _native PDF-Engine v2_, bietet aktualisierte PDF-Rendering-Funktionen und Fehlerbehebungen für _native PDF-Engine v1_-Probleme.

Verwenden Sie die Anweisungen unter [Konfigurationsüberschreibungen](../install-conf-guide/download-install-config-override.md), um die Konfigurationsdatei zu erstellen. Geben Sie in der Konfigurationsdatei die folgenden Details (Eigenschaft) an:

| PID | Eigenschaftsschlüssel | Eigenschaftswert |
|-----|--------------|----------------|
| `com.adobe.fmdita.publish.config.GuidesPublishConfiguratorService` | `guides.publish.config` | `{"PDF_ENGINE": "v2"}` <br> Standardwert: `v1` |