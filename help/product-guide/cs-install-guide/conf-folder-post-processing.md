---
title: Dateinamen konfigurieren
description: Erfahren Sie, wie Sie die Nachbearbeitung für einen Ordner deaktivieren, der in Adobe Experience Manager Assets hochgeladen wurde.
feature: Filename Configuration
role: Admin
level: Experienced
source-git-commit: fedd04f4a261ec199f86cb38ecd57e76b9393ae5
workflow-type: tm+mt
source-wordcount: '258'
ht-degree: 1%

---


# Deaktivieren der Nachbearbeitung für einen Ordner

Standardmäßig werden alle hochgeladenen Assets mit dem Workflow DAM-Update-Asset verarbeitet. Experience Manager Guides führen im Rahmen dieses Workflows eine zusätzliche Verarbeitung durch, die als Nachbearbeitung bezeichnet wird. Dies hilft auch beim Generieren der UUIDs

Beim Hochladen Ihrer Dateien und Ordner in die *Adobe Experience Manager Assets* -Server können Sie auch die Nachbearbeitung und die Generierung von UUIDs deaktivieren.


Verwenden Sie die Anleitung unter [Konfigurationsüberschreibungen](download-install-additional-config-override.md#) , um die Konfigurationsdatei zu erstellen. Geben Sie in der Konfigurationsdatei die folgenden (Eigenschaftsdetails) an, um die Nachbearbeitung für einen bestimmten Pfad zu deaktivieren oder die Nachbearbeitung für einen Ordner zu ignorieren:

| PID | Eigenschaftenschlüssel | Eigenschaftswert |
|---|------------|--------------|
| `com.adobe.fmdita.config.ConfigManager` | `ignored.post.processing.paths` | Zeichenfolgenwert zum Festlegen beliebiger standardmäßiger NODE_OPTIONS (mehrwertige Eigenschaft, Zeichenfolgen mit Pfad, der weggelassen wird) `/` am Ende) <br> **Standardwert**: `/content/dam/projects/translation_output` |


| PID | Eigenschaftenschlüssel | Eigenschaftswert |
|---|------------|--------------|
| `com.adobe.fmdita.config.ConfigManager` | `enabled.post.processing.paths` | Zeichenfolgenwert zum Festlegen beliebiger standardmäßiger NODE_OPTIONS (mehrwertige Eigenschaft, Zeichenfolgen mit Pfad, der weggelassen wird) `/` am Ende) <br> **Standardwert**: `/content/dam` |


## Regeln zum Aktivieren oder Deaktivieren der Nachbearbeitung

Standardmäßig erfolgt die Nachbearbeitung für jeden Ordnerpfad im DAM-Ordner des Experience Managers. Konfigurationen werden für jeden Ordner gemäß den folgenden Regeln angewendet:

* Wenn das übergeordnete Element für die Nachbearbeitung ignoriert wird, der untergeordnete Ordner jedoch aktiviert ist, werden das untergeordnete Element und alle seine Nachfolger als aktiviert betrachtet.
* Wenn das übergeordnete Element für die Nachbearbeitung aktiviert ist, das untergeordnete Element jedoch ignoriert wird, werden das untergeordnete Element und alle seine Nachfolger als ignoriert betrachtet.
* Wenn derselbe Ordnerpfad sowohl in den Konfigurationen &quot;Ignoriert.post.processing.paths&quot;als auch &quot;enabled.post.processing.paths&quot;vorhanden ist, wird er bei der Nachbearbeitung als ignoriert betrachtet.
