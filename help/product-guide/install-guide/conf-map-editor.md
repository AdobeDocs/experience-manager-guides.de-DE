---
title: Festlegen des Erweiterten Map-Editors als Standard
description: Erfahren Sie, wie Sie den erweiterten Map-Editor als Standard festlegen.
exl-id: ecc023f6-48eb-4afd-97a2-4b3cdd5a8991
feature: Web Editor Configuration
role: Admin
level: Experienced
source-git-commit: 126cecdaa481b9da1add4ba3664c26c2bc5da068
workflow-type: tm+mt
source-wordcount: '270'
ht-degree: 0%

---

# Festlegen des Erweiterten Map-Editors als Standard {#id181AI0003PN}

>[!NOTE]
>
> Der Basic Map Editor, der zuvor in Experience Manager Guides verfügbar war, wurde ab Version 4.3 und 2307 eingestellt. Sie können nicht auf den Basic Map Editor zugreifen, um DITA-Maps zu erstellen und zu verwalten.
>Es wird empfohlen, den erweiterten Map-Editor zu verwenden. Der erweiterte Map Editor bietet erweiterte Funktionen und bessere Anpassungsoptionen. Erfahren Sie mehr über die Verwendung des [erweiterten Map-Editors](../user-guide/map-editor-advanced-map-editor.md).

Für Versionen vor 4.3 und 2307 ist Experience Manager Guides mit einem Basic Map Editor und einem Advanced Map Editor ausgestattet. Der Basic Map Editor bietet Ihnen alle notwendigen Funktionen zum Erstellen Ihrer Zuordnungsdatei. Der erweiterte Map-Editor ist wesentlich umfangreicher und im Web-Editor integriert. Mit dem erweiterten Map Editor können Autoren DITA-Zuordnungsdateien mit einer benutzerfreundlichen Benutzeroberfläche erstellen und bearbeiten.

Standardmäßig wird eine neue Zuordnungsdatei bei der Erstellung im Basic Map Editor geöffnet. Sie können dieses Verhalten ändern, indem Sie die Einstellung aktivieren, um den erweiterten Map-Editor standardmäßig zu öffnen.

Führen Sie die folgenden Schritte aus, um den erweiterten Map-Editor als Standardeditor für die Zuordnungsdateien festzulegen:

1. Öffnen Sie die Seite Adobe Experience Manager Web Console Configuration .

   Die Standard-URL für den Zugriff auf die Konfigurationsseite lautet:

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Suchen Sie nach dem Bundle **com.adobe.fmdita.xmleditor.config.XmlEditorConfig** und klicken Sie darauf.

1. Wählen Sie die Option **Grundlegenden Map-Editor ausblenden** aus.

   Wenn diese Option aktiviert ist, wird den Benutzern der Link &quot;Grundlegender Map-Editor&quot;nirgends in der Benutzeroberfläche angezeigt. Standardmäßig werden Zuordnungsdateien im erweiterten Map-Editor geöffnet.
