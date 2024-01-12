---
title: Festlegen des Erweiterten Map-Editors als Standard
description: Erfahren Sie, wie Sie den erweiterten Map-Editor als Standard festlegen.
exl-id: ecc023f6-48eb-4afd-97a2-4b3cdd5a8991
feature: Web Editor Configuration
role: Admin
level: Experienced
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '199'
ht-degree: 0%

---

# Festlegen des Erweiterten Map-Editors als Standard {#id181AI0003PN}

AEM Guides verfügen über einen einfachen Map-Editor und einen erweiterten Map-Editor. Der Basic Map Editor bietet Ihnen alle notwendigen Funktionen zum Erstellen Ihrer Zuordnungsdatei. Der erweiterte Map-Editor ist wesentlich umfangreicher und im Web-Editor integriert. Mit dem erweiterten Map Editor können Autoren DITA-Zuordnungsdateien mit einer benutzerfreundlichen Benutzeroberfläche erstellen und bearbeiten.

Standardmäßig wird eine neue Zuordnungsdatei bei der Erstellung im Basic Map Editor geöffnet. Sie können dieses Verhalten ändern, indem Sie die Einstellung aktivieren, um den erweiterten Map-Editor standardmäßig zu öffnen.

Führen Sie die folgenden Schritte aus, um den erweiterten Map-Editor als Standardeditor für die Zuordnungsdateien festzulegen:

1. Öffnen Sie die Seite Adobe Experience Manager Web Console Configuration .

   Die Standard-URL für den Zugriff auf die Konfigurationsseite lautet:

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Suchen Sie nach und klicken Sie auf **com.adobe.fmdita.xmleditor.config.XmlEditorConfig** Bundle

1. Wählen Sie die **Grundlegenden Map-Editor ausblenden** -Option.

   Wenn diese Option aktiviert ist, wird den Benutzern der Link &quot;Grundlegender Map-Editor&quot;nirgends in der Benutzeroberfläche angezeigt. Standardmäßig werden Zuordnungsdateien im erweiterten Map-Editor geöffnet.
