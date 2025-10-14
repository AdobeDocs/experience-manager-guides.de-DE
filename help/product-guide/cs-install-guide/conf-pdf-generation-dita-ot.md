---
title: Konfigurieren der Erstellung von Single Topic PDF
description: Erfahren Sie, wie Sie die Erstellung von Single Topic PDF konfigurieren
exl-id: 5b66fd3b-6450-49ce-b06e-d2d5bab37990
feature: Web Editor Configuration
role: Admin
level: Experienced
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '268'
ht-degree: 0%

---

# Konfigurieren der Erstellung von Single Topic PDF {#id22ADC70M0XA}

Mit der AEM Guides können Sie die PDF einzelner Themen oder eine ganze Kartendatei generieren. Sie können Ihre Themen in einem PDF-Format mit nativem PDF oder DITA-OT veröffentlichen. Verwenden Sie die native PDF-Methode, um eine funktionsreiche PDF-Ausgabe auf der Grundlage von W3C CSS3- und CSS-Paging-Medienstandards zu generieren. Sie können die DITA-OT-Methode verwenden, um eine PDF-Ausgabe für eine Zuordnung über das Zuordnungs-Dashboard zu generieren.

>[!NOTE]
>
> Das native PDF ist die Standardmethode zum Generieren einer PDF in der aktuellen Version von AEM Guides.

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

Wenn Sie nach dem Ausführen der oben genannten Schritte dasselbe Ordnerprofil aus den Benutzereinstellungen im Web-Editor auswählen, wird im Vorschaumodus eines Themas die Option zum Generieren von PDF angezeigt.

**Übergeordnetes Thema:**&#x200B;[&#x200B; Anpassen des Web-Editors](conf-web-editor.md)
