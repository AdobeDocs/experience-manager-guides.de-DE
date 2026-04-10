---
title: Konfigurieren der PDF-Generierung für ein einzelnes Thema
description: Erfahren Sie, wie Sie die PDF-Generierung für einzelne Themen konfigurieren
exl-id: 5b66fd3b-6450-49ce-b06e-d2d5bab37990
feature: Web Editor Configuration
role: Admin
level: Experienced
hidefromtoc: true
source-git-commit: 564ee1731be2378744ffd2ed54a2fd423901a0b3
workflow-type: tm+mt
source-wordcount: '268'
ht-degree: 0%

---

# Konfigurieren der PDF-Generierung für ein einzelnes Thema {#id22ADC70M0XA}

Mit der AEM Guides können Sie die PDF einzelner Themen oder eine gesamte Zuordnungsdatei generieren. Sie können Ihre Themen im PDF-Format mit der nativen PDF- oder DITA-OT-Methode veröffentlichen. Verwenden Sie die native PDF-Methode , um eine funktionsreiche PDF-Ausgabe basierend auf W3C CSS3- und CSS-Seitenmedienstandards zu generieren. Sie können die DITA-OT-Methode verwenden, um eine PDF-Ausgabe für eine Zuordnung über das Zuordnungs-Dashboard zu generieren.

>[!NOTE]
>
> Native PDF ist die Standardmethode zum Generieren einer PDF in der aktuellen Version von AEM Guides.

Führen Sie die folgenden Schritte aus, um die alte PDF-Generierung über das DITA-OT im Themenvorschaumodus zu aktivieren:

1. Melden Sie sich bei Adobe Experience Manager als Administrator an und laden Sie die Konfigurationsdatei der Benutzeroberfläche herunter.

1. Klicken Sie dazu auf den Adobe Experience Manager-Link oben und wählen Sie **Tools**.
1. Wählen Sie **Guides** aus der Liste der Tools aus und klicken Sie auf **Ordnerprofile**.
1. Klicken Sie auf die **Globales Profil**-Kachel.
1. Wählen Sie die Registerkarte **XML** Editor-Konfiguration) aus und klicken Sie **oben auf** Bearbeiten“
1. Klicken Sie auf **Herunterladen**, um die Datei ui\_config.json auf Ihr lokales System herunterzuladen. Anschließend können Sie Änderungen an der Datei vornehmen und diese dann hochladen.
1. Suchen Sie in der `ui_config.json` nach der folgenden Konfiguration:

   ```
   {
                           "component": "button",
                           "variant": "action",
                           "quiet": true,
                           "icon": "filePDF",
                           "title": "Download as PDF",
                           "on-click": "EDITOR_SAVE_AS_PDF"
                           }
   ```

   und ersetzen durch

   ```
   {
                           "component": "button",
                           "icon": "filePDF",
                           "variant": "action",
                           "quiet": true, "title": "Export as PDF",
                           "on-click": "DOWNLOAD_TOPIC_PDF",
                           "show" : ["@isPreviewMode", "@isXmlMode"]
                           }
   ```

1. Speichern Sie die Datei und laden Sie sie hoch.

Wenn Sie nach dem Ausführen der oben genannten Schritte dasselbe Ordnerprofil aus den Benutzereinstellungen im Web-Editor auswählen, wird im Vorschaumodus eines Themas die Option für die PDF-Generierung angezeigt.

**Übergeordnetes Thema:**[ Anpassen des Web-Editors](conf-web-editor.md)
