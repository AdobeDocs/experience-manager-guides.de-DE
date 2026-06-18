---
title: Festlegen des erweiterten Zuordnungs-Editors als Standard
description: Erfahren Sie, wie Sie den erweiterten Karten-Editor als Standard festlegen
feature: Web Editor Configuration
role: Admin
level: Experienced
exl-id: 60205ca4-518f-49fa-b63b-f1a56d70fc01
source-git-commit: cc73b81787a3c3dbe8390d93e558064327e59965
workflow-type: tm+mt
source-wordcount: '349'
ht-degree: 0%

---

# Festlegen des erweiterten Zuordnungs-Editors als Standard {#id181AI0003PN}

>[!NOTE]
>
> Der grundlegende Zuordnungs-Editor, der zuvor in Experience Manager Guides verfügbar war, wird seit Version 4.3 und 2307 nicht mehr unterstützt. Sie können nicht auf den grundlegenden Karten-Editor zugreifen, um DITA-Karten zu erstellen und zu verwalten.
>Es wird empfohlen, den erweiterten Karten-Editor zu verwenden. Der erweiterte Zuordnungs-Editor bietet erweiterte Funktionen und bessere Anpassungsoptionen. Weitere Informationen zum Arbeiten mit dem [erweiterten Karten-Editor](../user-guide/map-editor-advanced-map-editor.md).

Für ältere Versionen als 4.3 und 2307 verfügt Experience Manager Guides über einen einfachen Karteneditor und einen erweiterten Karteneditor. Der einfache Zuordnungs-Editor bietet Ihnen alle notwendigen Funktionen zum Erstellen Ihrer Zuordnungsdatei. Der erweiterte Zuordnungs-Editor bietet viel mehr Funktionen und ist in den Editor integriert. Mit dem erweiterten Zuordnungs-Editor können Autoren DITA-Zuordnungsdateien mit einer benutzerfreundlichen Oberfläche erstellen und bearbeiten.

Standardmäßig wird jede neue Zuordnungsdatei, die erstellt wird, im einfachen Zuordnungs-Editor geöffnet. Sie können dieses Verhalten ändern, indem Sie die Einstellung aktivieren, um den erweiterten Zuordnungs-Editor standardmäßig zu öffnen.

Die folgenden Registerkarten enthalten Anweisungen, um den erweiterten Zuordnungs-Editor basierend auf Ihrer Experience Manager Guides-Einrichtung als Standard-Editor für die Zuordnungsdateien festzulegen: Cloud Service oder On-Premise.


>[!BEGINTABS]

>[!TAB Cloud Service]

Verwenden Sie die Anweisungen unter [Konfigurationsüberschreibungen](download-install-config-override.md#), um die Konfigurationsdatei zu erstellen. Geben Sie in der Konfigurationsdatei die folgenden \(property\)-Details an, um den einfachen Zuordnungs-Editor zu aktivieren:

| PID | Eigenschaftsschlüssel | Eigenschaftswert |
|---|------------|--------------|
| `com.adobe.fmdita.xmleditor.config.XmlEditorConfig` | ``fmdita.hide.oldmapeditor`` | Boolescher Wert \(true/false\). Wenn Sie den erweiterten Zuordnungs-Editor standardmäßig verwenden möchten, legen Sie diese Eigenschaft auf „true“ fest.<br> **Standardwert**: false |

>[!NOTE]
>
> Wenn ein Autor eine Zuordnungsdatei erstellt und sie zur Bearbeitung öffnet, wird standardmäßig der grundlegende Zuordnungs-Editor gestartet. Wenn die Option Bearbeiten für eine Zuordnungsdatei über die Assets-Benutzeroberfläche ausgewählt wird, wird sie auch im grundlegenden Zuordnungs-Editor geöffnet.

>[!TAB On-Premise]

1. Öffnen Sie die Seite Konfiguration der Adobe Experience Manager-Web-Konsole .

   Die Standard-URL für den Zugriff auf die Konfigurationsseite lautet:

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Suchen Sie nach dem Bundle **com.adobe.fmdita.xmeditor.config.XmlEditorConfig** und klicken Sie darauf.

1. Wählen Sie die **Standard-Zuordnungs-Editor ausblenden** aus.

   Wenn diese Option aktiviert ist, wird der Link Allgemeiner Zuordnungs-Editor nirgends auf der Benutzeroberfläche angezeigt. Standardmäßig werden Zuordnungsdateien im erweiterten Zuordnungs-Editor geöffnet.

>[!ENDTABS]

**Übergeordnetes Thema:**[ Editor anpassen](customize-overview.md)
