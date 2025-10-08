---
title: Dateinamen konfigurieren
description: Erfahren Sie, wie Sie die Nachbearbeitung für einen auf Adobe Experience Manager Assets hochgeladenen Ordner deaktivieren
feature: Filename Configuration
role: Admin
level: Experienced
exl-id: ff6e1322-9655-42aa-b353-199c70c9de49
source-git-commit: e84a00237e61275c6cd1ddd312883ac4f66b65ff
workflow-type: tm+mt
source-wordcount: '394'
ht-degree: 0%

---

# Deaktivieren der Nachbearbeitung für einen Ordner

Standardmäßig werden alle hochgeladenen Assets mit dem Workflow DAM-Update-Asset verarbeitet. Experience Manager Guides führt im Rahmen dieses Workflows eine zusätzliche Verarbeitung, die so genannte Nachbearbeitung, aus. Dies hilft auch beim Generieren der UUIDs.

Beim Hochladen Ihrer Dateien und Ordner auf den *Adobe Experience Manager Assets*-Server können Sie auch die Nachbearbeitung und das Generieren von UUIDs deaktivieren.


Führen Sie die folgenden Schritte aus, um die Nachbearbeitung für einen bestimmten Pfad zu deaktivieren oder die Nachbearbeitung für einen Ordner zu ignorieren:


1. Öffnen Sie die Seite Konfiguration der Adobe Experience Manager-Web-Konsole .

   Die Standard-URL für den Zugriff auf die Konfigurationsseite lautet:

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Suchen Sie nach dem Bundle **com.adobe.fmdita.config.ConfigManager** und klicken Sie darauf.

1. Wählen Sie die Option **Ignorierte Pfade für Nachbearbeitung** aus, um einen Ordner für die Nachbearbeitung zu ignorieren.

   Zeichenfolgenwert zum Festlegen eines beliebigen standardmäßigen NODE_OPTIONS (Eigenschaft mit mehreren Werten, Zeichenfolgen mit einem Pfad, bei dem am Ende `/` weggelassen werden)

   **Standardwert**: `/content/dam/projects/translation_output`

   >[!NOTE]
   >
   > Diese Eigenschaft ist standardmäßig deaktiviert und die Registerkarte Übersetzung ist im Zuordnungs-Dashboard verfügbar.

1. Wählen Sie die Option **Aktivierte Pfade für die Nachbearbeitung** aus, um einen Pfad für die Nachbearbeitung zu aktivieren.

   Zeichenfolgenwert zum Festlegen eines beliebigen standardmäßigen NODE_OPTIONS (Eigenschaft mit mehreren Werten, Zeichenfolgen mit einem Pfad, bei dem am Ende `/` weggelassen werden)

   **Standardwert**: `/content/dam/`

   >[!NOTE]
   >
   > Diese Eigenschaft ist standardmäßig deaktiviert und die Registerkarte Übersetzung ist im Zuordnungs-Dashboard verfügbar.


1. Klicken Sie auf **Speichern**.

>[!NOTE]
>
> Neben den ignorierten und aktivierten Pfaden, die über die OSGi-Konfiguration konfiguriert werden, wird das Nachbearbeitungsverhalten auch durch einen Knoten auf Repository-Ebene unter `/var/dxml/postprocess/ignoredPaths` beeinflusst. <br> Wenn ein Ordner unerwartet von der Nachbearbeitung ausgeschlossen wird und nicht in der OSGi-Konfiguration aufgeführt ist, wird empfohlen, diesen Repository-Knoten zu überprüfen. Wenn der Pfad dort angezeigt wird und auf `true` festgelegt ist, wird er ignoriert. Um die Verarbeitung wieder zu aktivieren, können Sie die entsprechende Eigenschaft manuell aus dem Knoten entfernen.

## Regeln zum Aktivieren oder Deaktivieren der Nachbearbeitung

Standardmäßig erfolgt die Nachbearbeitung für jeden Ordnerpfad unter dem Experience Manager DAM-Ordner. Konfigurationen werden für jeden Ordner gemäß den folgenden Regeln angewendet:

* Wenn das übergeordnete Element für die Nachbearbeitung ignoriert wird, aber der untergeordnete Ordner aktiviert ist, werden das untergeordnete Element und alle seine Nachfolger als aktiviert betrachtet.
* Wenn das übergeordnete Element für die Nachbearbeitung aktiviert ist, das untergeordnete Element jedoch ignoriert wird, werden das untergeordnete Element und alle seine Nachfolger als ignoriert betrachtet.
* Wenn derselbe Ordnerpfad sowohl in den Konfigurationen „ignore.post.processing.Paths“ als auch in den Konfigurationen „enabled.post.processing.Paths“ vorhanden ist, wird er bei der Nachbearbeitung als ignoriert betrachtet.
