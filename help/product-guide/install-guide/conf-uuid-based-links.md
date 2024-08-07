---
title: Anzeige von UUID-basierten Links konfigurieren
description: Erfahren Sie, wie Sie die Anzeige von UUID-basierten Links konfigurieren.
exl-id: ab1b0ecf-cb50-4fcd-b36e-d16a8c396054
feature: Web Editor Configuration
role: Admin
level: Experienced
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '209'
ht-degree: 0%

---

# Anzeige von UUID-basierten Links konfigurieren {#id2035G20M0QN}

Wenn Sie einen Link mit der Option Verweis einfügen oder Inhalt wiederverwenden im Web-Editor einfügen erstellen, wird der Link standardmäßig mit der UUID des referenzierten Inhalts erstellt. Die Eigenschaft **Link** \(im Eigenschaftenbereich\) des referenzierten Inhalts kann so konfiguriert werden, dass der relative Dateipfad des referenzierten Inhalts oder die UUID angezeigt wird. Diese Anzeige wird durch die Option **UUIDs aktivieren** in configMgr gesteuert. Standardmäßig ist sie aktiviert, was bedeutet, dass die UUID des referenzierten Inhalts im Bereich Eigenschaften angezeigt wird.

Führen Sie die folgenden Schritte aus, um den relativen Pfad oder die UUID des referenzierten Inhalts im Web Editor anzuzeigen:

1. Öffnen Sie die Seite Adobe Experience Manager Web Console Configuration .

   Die Standard-URL für den Zugriff auf die Konfigurationsseite lautet:

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Suchen Sie nach dem Bundle **com.adobe.fmdita.xmleditor.config.XmlEditorConfig** und klicken Sie darauf.

1. In den Einstellungen für *XmlEditorConfig* ist die Option **UUIDs aktivieren** standardmäßig aktiviert. Dies bedeutet, dass die UUID des referenzierten Inhalts in der Eigenschaft **Link** im Bereich &quot;Eigenschaften&quot;angezeigt wird.

   Wenn Sie den relativen Pfad des verknüpften Inhalts anzeigen möchten, deaktivieren Sie die Option **UUIDs aktivieren** .

1. Klicken Sie auf **Speichern**.


**Übergeordnetes Thema:**[ Web-Editor anpassen](conf-web-editor.md)
