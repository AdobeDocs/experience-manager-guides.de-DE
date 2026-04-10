---
title: Anzeige von UUID-basierten Links konfigurieren
description: Erfahren Sie, wie Sie die Anzeige von UUID-basierten Links konfigurieren
feature: Web Editor Configuration
role: Admin
level: Experienced
source-git-commit: 6f3f05419f4f5cdd45ab580cdee6fa869f20f01d
workflow-type: tm+mt
source-wordcount: '305'
ht-degree: 1%

---

# Anzeige von UUID-basierten Links konfigurieren {#id2035G20M0QN}

Wenn Sie einen Link mit der Option Verweis einfügen oder Wiederverwenden von Inhalten einfügen im Editor erstellen, wird der Link standardmäßig mit der UUID des referenzierten Inhalts erstellt. Die **Link**-Eigenschaft \(im Eigenschaftenbereich\) des referenzierten Inhalts kann so konfiguriert werden, dass der relative Dateipfad des referenzierten Inhalts oder der UUID angezeigt wird. Für Cloud Service wird die UUID des referenzierten Inhalts standardmäßig im Bedienfeld Eigenschaften angezeigt. Bei On-Premise wird diese Anzeige durch die Option **UUIDs aktivieren** im `configMgr` gesteuert. Standardmäßig ist sie aktiviert, was bedeutet, dass die UUID des referenzierten Inhalts im Bedienfeld Eigenschaften angezeigt wird.

Die folgenden Registerkarten enthalten Anweisungen, um den relativen Pfad oder die UUID des referenzierten Inhalts im Editor basierend auf Ihrer Experience Manager Guides-Einrichtung anzuzeigen: Cloud Service oder On-Premise.

>[!BEGINTABS]

>[!TAB Cloud Service]

Verwenden Sie die Anweisungen unter [Konfigurationsüberschreibungen](download-install-config-override.md#), um die Konfigurationsdatei zu erstellen. Geben Sie in der Konfigurationsdatei die folgenden \(property\)-Details an, um den relativen Pfad oder die UUID des referenzierten Inhalts im Editor anzuzeigen.

| PID | Eigenschaftsschlüssel | Eigenschaftswert |
|---|------------|--------------|
| `com.adobe.fmdita.xmleditor.config.XmlEditorConfig` | `xmleditor.uuid` | Boolescher Wert \(true/false\). Wenn Sie den relativen Pfad des verknüpften Inhalts anzeigen möchten, legen Sie diese Eigenschaft auf „false“ fest. <br> **Standardwert**: true |


>[!TAB On-Premise]

1. Öffnen Sie die Seite Konfiguration der Adobe Experience Manager-Web-Konsole .

   Die Standard-URL für den Zugriff auf die Konfigurationsseite lautet:

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Suchen Sie nach dem Bundle **com.adobe.fmdita.xmeditor.config.XmlEditorConfig** und klicken Sie darauf.

1. In den *XmlEditorConfig*-Einstellungen ist die Option **UUIDs aktivieren** standardmäßig aktiviert. Dies bedeutet, dass die UUID des referenzierten Inhalts in der Eigenschaft **Link** im Bedienfeld Eigenschaften angezeigt wird.

   Wenn Sie den relativen Pfad des verknüpften Inhalts anzeigen möchten, heben Sie die Auswahl der Option **UUIDs aktivieren** auf.

1. Klicken Sie auf **Speichern**.

>[!ENDTABS]

**Übergeordnetes Thema:**[ Anpassen des Web-Editors](customize-overview.md)
