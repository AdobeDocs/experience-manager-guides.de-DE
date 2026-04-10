---
title: Konfigurieren der DITA Assets-Replikation für Cloud Service
description: Erfahren Sie, wie Sie die Replikation von DITA-Assets für Cloud Service konfigurieren
feature: Output Generation
role: Admin
level: Experienced
exl-id: 1eafc6b2-2b85-486a-bb2c-0038fae1fef9
hidefromtoc: true
source-git-commit: 564ee1731be2378744ffd2ed54a2fd423901a0b3
workflow-type: tm+mt
source-wordcount: '60'
ht-degree: 3%

---

# Konfigurieren der DITA-Asset-Replikation

Um die Asset-Verarbeitungsfunktion zu konfigurieren, führen Sie die folgenden Schritte aus:

1. Verwenden Sie die Anweisungen unter [Konfigurationsüberschreibungen](../cs-install-guide/download-install-additional-config-override.md), um die Konfigurationsdatei zu erstellen.

1. Geben Sie in der Konfigurationsdatei die folgenden Details (Eigenschaft) an:

   | PID | Eigenschaftsschlüssel | Eigenschaftswert |
   |---|---|---|
   | `com.adobe.fmdita.config.ConfigManager` | `publish.replicate` | **Standardwert:** „true“ |
