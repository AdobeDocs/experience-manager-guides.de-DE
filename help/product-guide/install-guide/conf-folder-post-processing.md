---
title: Dateinamen konfigurieren
description: Erfahren Sie, wie Sie die Nachbearbeitung für einen Ordner deaktivieren, der in Adobe Experience Manager Assets hochgeladen wurde.
feature: Filename Configuration
role: Admin
level: Experienced
source-git-commit: 532e7c562a233619a8c4b7cbdbaef44bc73eb4b2
workflow-type: tm+mt
source-wordcount: '322'
ht-degree: 0%

---


# Deaktivieren der Nachbearbeitung für einen Ordner

Standardmäßig werden alle hochgeladenen Assets mit dem Workflow DAM-Update-Asset verarbeitet. Experience Manager Guides führen im Rahmen dieses Workflows eine zusätzliche Verarbeitung durch, die als Nachbearbeitung bezeichnet wird. Dies hilft auch beim Generieren der UUIDs

Beim Hochladen Ihrer Dateien und Ordner in die *Adobe Experience Manager Assets* -Server können Sie auch die Nachbearbeitung und die Generierung von UUIDs deaktivieren.


Führen Sie die folgenden Schritte aus, um die Nachbearbeitung für einen bestimmten Pfad zu deaktivieren oder die Nachbearbeitung für einen Ordner zu ignorieren:


1. Öffnen Sie die Seite Adobe Experience Manager Web Console Configuration .

   Die Standard-URL für den Zugriff auf die Konfigurationsseite lautet:

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Suchen Sie nach und klicken Sie auf **com.adobe.fmdita.config.ConfigManager** Bundle

1. Wählen Sie die **Ignorierte Pfade für die Nachbearbeitung** , um einen Ordner für die Nachbearbeitung zu ignorieren.

   Zeichenfolgenwert zum Festlegen beliebiger standardmäßiger NODE_OPTIONS (mehrwertige Eigenschaft, Zeichenfolgen mit Pfad, der weggelassen wird) `/` am Ende)

   **Standardwert**: `/content/dam/projects/translation_output`

   >[!NOTE]
   >
   > Diese Eigenschaft ist standardmäßig deaktiviert und die Registerkarte &quot;Übersetzung&quot;ist im Landkarten-Dashboard verfügbar.

1. Wählen Sie die **Aktivierte Pfade für die Nachbearbeitung** , um einen Pfad für die Nachbearbeitung zu aktivieren.

   Zeichenfolgenwert zum Festlegen beliebiger standardmäßiger NODE_OPTIONS (mehrwertige Eigenschaft, Zeichenfolgen mit Pfad, der weggelassen wird) `/` am Ende)

   **Standardwert**: `/content/dam/`

   >[!NOTE]
   >
   > Diese Eigenschaft ist standardmäßig deaktiviert und die Registerkarte &quot;Übersetzung&quot;ist im Landkarten-Dashboard verfügbar.


1. Klicken Sie auf **Speichern**.



## Regeln zum Aktivieren oder Deaktivieren der Nachbearbeitung

Standardmäßig erfolgt die Nachbearbeitung für jeden Ordnerpfad im DAM-Ordner des Experience Managers. Konfigurationen werden für jeden Ordner gemäß den folgenden Regeln angewendet:

* Wenn das übergeordnete Element für die Nachbearbeitung ignoriert wird, der untergeordnete Ordner jedoch aktiviert ist, werden das untergeordnete Element und alle seine Nachfolger als aktiviert betrachtet.
* Wenn das übergeordnete Element für die Nachbearbeitung aktiviert ist, das untergeordnete Element jedoch ignoriert wird, werden das untergeordnete Element und alle seine Nachfolger als ignoriert betrachtet.
* Wenn derselbe Ordnerpfad sowohl in den Konfigurationen &quot;Ignoriert.post.processing.paths&quot;als auch &quot;enabled.post.processing.paths&quot;vorhanden ist, wird er bei der Nachbearbeitung als ignoriert betrachtet.
