---
title: Native PDF | Konfigurieren des Basisausgabespeicherorts für die Veröffentlichung von PDF für Cloud-Services
description: Konfigurieren des Speicherorts der Basisausgabe für die Veröffentlichung von PDF für Cloud-Services
feature: Output Generation
role: Admin
level: Experienced
exl-id: d79085d6-938a-4e80-84a2-03562e6b76e0
source-git-commit: ccaf2ead1a9a24ab822298c6b9ef6866a1c32e8c
workflow-type: tm+mt
source-wordcount: '80'
ht-degree: 2%

---

# Konfigurieren des Speicherorts der Basisausgabe für die Veröffentlichung der Ausgabe für Cloud-Services

Führen Sie die folgenden Schritte aus, um den Basisausgabespeicherort zu konfigurieren:

1. Verwenden Sie die Anweisungen unter [Konfigurationsüberschreibungen](../cs-install-guide/download-install-additional-config-override.md), um die Konfigurationsdatei zu erstellen.

1. Geben Sie in der Konfigurationsdatei die folgenden (Eigenschafts-)Details an, um den Basisausgabespeicherort zu konfigurieren:

   | PID | Eigenschaftsschlüssel | Eigenschaftswert |
   |---|---|---|
   | `com.adobe.fmdita.config.ConfigManager` | `base.output.path` | **Standardwert:** &quot;/content/dam/fmdita-output“ |
