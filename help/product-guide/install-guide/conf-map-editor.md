---
title: Festlegen des erweiterten Zuordnungs-Editors als Standard
description: Erfahren Sie, wie Sie den erweiterten Karten-Editor als Standard festlegen
exl-id: ecc023f6-48eb-4afd-97a2-4b3cdd5a8991
feature: Web Editor Configuration
role: Admin
level: Experienced
TQID: https://experienceleague.adobe.com/dwHfKsMVg9UWOs2eIClHcDeGn4lFHo6JqGZEYl3NEFE
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2:
  - id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
subfeature_v2:
  - id: b0521e56-a0b2-40b6-bf47-ebc98751f9ba
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 272
ht-degree: 0%

---

# Festlegen des erweiterten Zuordnungs-Editors als Standard {#id181AI0003PN}

>[!NOTE]
>
> Der grundlegende Zuordnungs-Editor, der zuvor in Experience Manager Guides verfügbar war, wird seit Version 4.3 und 2307 nicht mehr unterstützt. Sie können nicht auf den grundlegenden Karten-Editor zugreifen, um DITA-Karten zu erstellen und zu verwalten.
>Es wird empfohlen, den erweiterten Zuordnungs-Editor zu verwenden. Der erweiterte Zuordnungs-Editor bietet erweiterte Funktionen und bessere Anpassungsoptionen. Weitere Informationen zum Arbeiten mit dem [erweiterten Karten-Editor](../user-guide/map-editor-advanced-map-editor.md).

Für ältere Versionen als 4.3 und 2307 verfügt Experience Manager Guides über einen einfachen Karteneditor und einen erweiterten Karteneditor. Der einfache Zuordnungs-Editor bietet Ihnen alle notwendigen Funktionen zum Erstellen Ihrer Zuordnungsdatei. Der erweiterte Zuordnungs-Editor bietet viel mehr Funktionen und ist in den Web-Editor integriert. Mit dem erweiterten Zuordnungs-Editor können Autoren DITA-Zuordnungsdateien mit einer benutzerfreundlichen Oberfläche erstellen und bearbeiten.

Standardmäßig wird jede neue Zuordnungsdatei, die erstellt wird, im einfachen Zuordnungs-Editor geöffnet. Sie können dieses Verhalten ändern, indem Sie die Einstellung aktivieren, um den erweiterten Zuordnungs-Editor standardmäßig zu öffnen.

Führen Sie die folgenden Schritte aus, um den erweiterten Zuordnungs-Editor als Standard-Editor für die Zuordnungsdateien festzulegen:

1. Öffnen Sie die Seite Konfiguration der Adobe Experience Manager-Web-Konsole .

   Die Standard-URL für den Zugriff auf die Konfigurationsseite lautet:

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Suchen Sie nach dem Bundle **com.adobe.fmdita.xmeditor.config.XmlEditorConfig** und klicken Sie darauf.

1. Wählen Sie die **Standard-Zuordnungs-Editor ausblenden** aus.

   Wenn diese Option aktiviert ist, wird der Link Allgemeiner Zuordnungs-Editor nirgends auf der Benutzeroberfläche angezeigt. Standardmäßig werden Zuordnungsdateien im erweiterten Zuordnungs-Editor geöffnet.
