---
title: Konfigurieren der Asset-Verarbeitung für Cloud Service
description: Erfahren Sie, wie Sie die Asset-Verarbeitung für Cloud Service konfigurieren
feature: Output Generation
role: Admin
level: Experienced
exl-id: 219a096f-4087-489f-9b3b-104864817198
TQID: https://experienceleague.adobe.com/pwwaOoH35wROxMMw4ZWNTwCmXWUBxR6y23UWvPiqTR4
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2:
  - id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 58
ht-degree: 3%

---

# Asset-Verarbeitungsfunktion konfigurieren

Um die Asset-Verarbeitungsfunktion zu konfigurieren, führen Sie die folgenden Schritte aus:

1. Verwenden Sie die Anweisungen unter [Konfigurationsüberschreibungen](../cs-install-guide/download-install-additional-config-override.md), um die Konfigurationsdatei zu erstellen.

1. Geben Sie in der Konfigurationsdatei die folgenden Details (Eigenschaft) an:

   | PID | Eigenschaftsschlüssel | Eigenschaftswert |
   |---|---|---|
   | `com.adobe.fmdita.config.ConfigManager` | `enable.asset.processing.scheduler` | **Standardwert:** „true“ |
