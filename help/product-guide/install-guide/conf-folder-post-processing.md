---
title: Dateinamen konfigurieren
description: Erfahren Sie, wie Sie die Nachbearbeitung für einen auf Adobe Experience Manager Assets hochgeladenen Ordner deaktivieren
feature: Filename Configuration
role: Admin
level: Experienced
exl-id: ff6e1322-9655-42aa-b353-199c70c9de49
TQID: https://experienceleague.adobe.com/QGFFy-2t4eZYQwe6eGna-m7tOnxnEqmpL7sM5F2R-oo
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2:
  - id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
subfeature_v2:
  - id: ccd46b93-df7f-4458-ba4c-90a3562d9ab0
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 398
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
> Neben den ignorierten und aktivierten Pfaden, die über die OSGi-Konfiguration konfiguriert werden, wird das Nachbearbeitungsverhalten auch durch einen Knoten auf Repository-Ebene beeinflusst, der sich unter `/var/dxml/postprocess/ignoredPaths` befindet. <br> Wenn ein Ordner unerwartet von der Nachbearbeitung ausgeschlossen wird und in der OSGi-Konfiguration nicht aufgeführt ist, wird empfohlen, diesen Repository-Knoten zu überprüfen. Wenn der Pfad dort angezeigt wird und auf `true` festgelegt ist, wird er ignoriert. Um die Verarbeitung wieder zu aktivieren, können Sie die entsprechende Eigenschaft manuell aus dem Knoten entfernen.

## Regeln zum Aktivieren oder Deaktivieren der Nachbearbeitung

Standardmäßig erfolgt die Nachbearbeitung für jeden Ordnerpfad unter dem Experience Manager DAM-Ordner. Konfigurationen werden für jeden Ordner gemäß den folgenden Regeln angewendet:

* Wenn das übergeordnete Element für die Nachbearbeitung ignoriert wird, aber der untergeordnete Ordner aktiviert ist, werden das untergeordnete Element und alle seine Nachfolger als aktiviert betrachtet.
* Wenn das übergeordnete Element für die Nachbearbeitung aktiviert ist, das untergeordnete Element jedoch ignoriert wird, werden das untergeordnete Element und alle seine Nachfolger als ignoriert betrachtet.
* Wenn derselbe Ordnerpfad sowohl in den Konfigurationen „ignore.post.processing.Paths“ als auch in den Konfigurationen „enabled.post.processing.Paths“ vorhanden ist, wird er bei der Nachbearbeitung als ignoriert betrachtet.
