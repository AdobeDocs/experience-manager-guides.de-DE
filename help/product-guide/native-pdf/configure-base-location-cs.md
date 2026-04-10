---
title: Native PDF | Konfigurieren des Basisausgabespeicherorts für die Veröffentlichung von PDF für Cloud-Services
description: Konfigurieren des Speicherorts der Basisausgabe für die Veröffentlichung von PDF für Cloud-Services
feature: Output Generation
role: Admin
level: Experienced
exl-id: d79085d6-938a-4e80-84a2-03562e6b76e0
hidefromtoc: true
source-git-commit: 564ee1731be2378744ffd2ed54a2fd423901a0b3
workflow-type: tm+mt
source-wordcount: '79'
ht-degree: 2%

---

# Konfigurieren des Speicherorts der Basisausgabe für die Veröffentlichung der Ausgabe für Cloud-Services

Führen Sie die folgenden Schritte aus, um den Basisausgabespeicherort zu konfigurieren:

1. Verwenden Sie die Anweisungen unter [Konfigurationsüberschreibungen](../cs-install-guide/download-install-additional-config-override.md), um die Konfigurationsdatei zu erstellen.

1. Geben Sie in der Konfigurationsdatei die folgenden (Eigenschafts-)Details an, um den Basisausgabespeicherort zu konfigurieren:

   | PID | Eigenschaftsschlüssel | Eigenschaftswert |
   |---|---|---|
   | `com.adobe.fmdita.config.ConfigManager` | `base.output.path` | **Standardwert:** &quot;/content/dam/fmdita-output“ |
