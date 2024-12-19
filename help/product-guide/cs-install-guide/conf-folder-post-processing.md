---
title: Dateinamen konfigurieren
description: Erfahren Sie, wie Sie die Nachbearbeitung für einen auf Adobe Experience Manager Assets hochgeladenen Ordner deaktivieren
feature: Filename Configuration
role: Admin
level: Experienced
exl-id: 42722c6f-1b1c-4a7e-89ef-a373623eb774
source-git-commit: 5d99274da8fdacbd255d426fa4913b5773ca45f8
workflow-type: tm+mt
source-wordcount: '258'
ht-degree: 1%

---

# Deaktivieren der Nachbearbeitung für einen Ordner

Standardmäßig werden alle hochgeladenen Assets mit dem Workflow DAM-Update-Asset verarbeitet. Experience Manager Guides führt im Rahmen dieses Workflows eine zusätzliche Verarbeitung, die so genannte Nachbearbeitung, aus. Dies hilft auch beim Generieren der UUIDs

Beim Hochladen Ihrer Dateien und Ordner auf den *Adobe Experience Manager Assets*-Server können Sie auch die Nachbearbeitung und das Generieren von UUIDs deaktivieren.


Verwenden Sie die Anweisungen unter [Konfigurationsüberschreibungen](download-install-additional-config-override.md#), um die Konfigurationsdatei zu erstellen. Geben Sie in der Konfigurationsdatei die folgenden (Eigenschafts-)Details an, um die Nachbearbeitung für einen bestimmten Pfad zu deaktivieren oder die Nachbearbeitung für einen Ordner zu ignorieren:

| PID | Eigenschaftsschlüssel | Eigenschaftswert |
|---|------------|--------------|
| `com.adobe.fmdita.config.ConfigManager` | `ignored.post.processing.paths` | Zeichenfolgenwert zum Festlegen beliebiger standardmäßiger NODE_OPTIONS-Werte (mehrwertige Eigenschaft, Zeichenfolgen mit einem Pfad, bei dem `/` am Ende weggelassen werden) <br> **Standardwert**: `/content/dam/projects/translation_output` |


| PID | Eigenschaftsschlüssel | Eigenschaftswert |
|---|------------|--------------|
| `com.adobe.fmdita.config.ConfigManager` | `enabled.post.processing.paths` | Zeichenfolgenwert zum Festlegen beliebiger standardmäßiger NODE_OPTIONS-Werte (mehrwertige Eigenschaft, Zeichenfolgen mit einem Pfad, bei dem `/` am Ende weggelassen werden) <br> **Standardwert**: `/content/dam` |


## Regeln zum Aktivieren oder Deaktivieren der Nachbearbeitung

Standardmäßig erfolgt die Nachbearbeitung für jeden Ordnerpfad unter dem Experience Manager DAM. Konfigurationen werden für jeden Ordner gemäß den folgenden Regeln angewendet:

* Wenn das übergeordnete Element für die Nachbearbeitung ignoriert wird, aber der untergeordnete Ordner aktiviert ist, werden das untergeordnete Element und alle seine Nachfolger als aktiviert betrachtet.
* Wenn das übergeordnete Element für die Nachbearbeitung aktiviert ist, das untergeordnete Element jedoch ignoriert wird, werden das untergeordnete Element und alle seine Nachfolger als ignoriert betrachtet.
* Wenn derselbe Ordnerpfad sowohl in den Konfigurationen „ignore.post.processing.Paths“ als auch in den Konfigurationen „enabled.post.processing.Paths“ vorhanden ist, wird er bei der Nachbearbeitung als ignoriert betrachtet.
