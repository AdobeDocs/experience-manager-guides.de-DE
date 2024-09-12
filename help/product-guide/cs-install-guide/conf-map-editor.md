---
title: Festlegen des Erweiterten Map-Editors als Standard
description: Erfahren Sie, wie Sie den erweiterten Map-Editor als Standard festlegen.
exl-id: 365264ab-f990-42c1-ab79-61a40ecea42f
feature: Web Editor Configuration
role: Admin
level: Experienced
source-git-commit: 126cecdaa481b9da1add4ba3664c26c2bc5da068
workflow-type: tm+mt
source-wordcount: '297'
ht-degree: 0%

---

# Festlegen des Erweiterten Map-Editors als Standard {#id181AI0003PN}

>[!NOTE]
>
> Der Basic Map Editor, der zuvor in Experience Manager Guides verfügbar war, wurde ab Version 4.3 und 2307 eingestellt. Sie können nicht auf den Basic Map Editor zugreifen, um DITA-Maps zu erstellen und zu verwalten.
>Es wird empfohlen, den erweiterten Map-Editor zu verwenden. Der erweiterte Map Editor bietet erweiterte Funktionen und bessere Anpassungsoptionen. Erfahren Sie mehr über die Verwendung des [erweiterten Map-Editors](../user-guide/map-editor-advanced-map-editor.md).

Für Versionen vor 4.3 und 2307 ist Experience Manager Guides mit einem Basic Map Editor und einem Advanced Map Editor ausgestattet. Der Basic Map Editor bietet Ihnen alle notwendigen Funktionen zum Erstellen Ihrer Zuordnungsdatei. Der erweiterte Map-Editor ist wesentlich umfangreicher und im Web-Editor integriert. Mit dem erweiterten Map Editor können Autoren DITA-Zuordnungsdateien mit einer benutzerfreundlichen Benutzeroberfläche erstellen und bearbeiten.

Standardmäßig wird eine neue Zuordnungsdatei bei der Erstellung im Basic Map Editor geöffnet. Sie können dieses Verhalten ändern, indem Sie die Einstellung aktivieren, um den erweiterten Map-Editor standardmäßig zu öffnen.

Verwenden Sie die Anweisungen unter [Konfigurationsüberschreibungen](download-install-additional-config-override.md#) , um die Konfigurationsdatei zu erstellen. Geben Sie in der Konfigurationsdatei die folgenden \(Eigenschaft\)-Details an, um den Basic Map Editor zu aktivieren:

| PID | Eigenschaftenschlüssel | Eigenschaftswert |
|---|------------|--------------|
| `com.adobe.fmdita.xmleditor.config.XmlEditorConfig` | ``fmdita.hide.oldmapeditor`` | Boolesch \(true/false\). Wenn Sie den erweiterten Map-Editor standardmäßig verwenden möchten, legen Sie diese Eigenschaft auf &quot;true&quot;fest.<br> **Standardwert**: false |

>[!NOTE]
>
> Wenn ein Autor eine Zuordnungsdatei erstellt und sie zur Bearbeitung öffnet, wird standardmäßig der Basic Map Editor gestartet. Wenn die Option &quot;Bearbeiten&quot;für eine Zuordnungsdatei über die Assets-Benutzeroberfläche ausgewählt ist, wird sie auch im Basic Map Editor geöffnet.

**Übergeordnetes Thema:**[ Web-Editor anpassen](conf-web-editor.md)
