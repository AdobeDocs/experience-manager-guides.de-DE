---
title: Anzeige von UUID-basierten Links konfigurieren
description: Erfahren Sie, wie Sie die Anzeige von UUID-basierten Links konfigurieren
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

Wenn Sie einen Link mit der Option Verweis einfügen oder Wiederverwenden von Inhalten einfügen im Web-Editor erstellen, wird der Link standardmäßig mit der UUID des referenzierten Inhalts erstellt. Die **Link**-Eigenschaft \(im Eigenschaftenbereich\) des referenzierten Inhalts kann so konfiguriert werden, dass der relative Dateipfad des referenzierten Inhalts oder der UUID angezeigt wird. Diese Anzeige wird durch die Option **UUIDs aktivieren** im configMgr gesteuert. Standardmäßig ist sie aktiviert, was bedeutet, dass die UUID des referenzierten Inhalts im Bedienfeld Eigenschaften angezeigt wird.

Führen Sie die folgenden Schritte aus, um den relativen Pfad oder die UUID des referenzierten Inhalts im Web-Editor anzuzeigen:

1. Öffnen Sie die Seite Konfiguration der Adobe Experience Manager-Web-Konsole .

   Die Standard-URL für den Zugriff auf die Konfigurationsseite lautet:

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Suchen Sie nach dem Bundle **com.adobe.fmdita.xmeditor.config.XmlEditorConfig** und klicken Sie darauf.

1. In den *XmlEditorConfig*-Einstellungen ist die Option **UUIDs aktivieren** standardmäßig aktiviert. Dies bedeutet, dass die UUID des referenzierten Inhalts in der Eigenschaft **Link** im Bedienfeld Eigenschaften angezeigt wird.

   Wenn Sie den relativen Pfad des verknüpften Inhalts anzeigen möchten, heben Sie die Auswahl der Option **UUIDs aktivieren** auf.

1. Klicken Sie auf **Speichern**.


**Übergeordnetes Thema:**&#x200B;[&#x200B; Anpassen des Web-Editors](conf-web-editor.md)
