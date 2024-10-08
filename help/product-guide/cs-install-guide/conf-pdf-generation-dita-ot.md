---
title: PDF-Generierung für einzelne Themen konfigurieren
description: Erfahren Sie, wie Sie die Erstellung von PDF für einzelne Themen konfigurieren
exl-id: 5b66fd3b-6450-49ce-b06e-d2d5bab37990
feature: Web Editor Configuration
role: Admin
level: Experienced
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '268'
ht-degree: 0%

---

# PDF-Generierung für einzelne Themen konfigurieren {#id22ADC70M0XA}

Mit der AEM Guides können Sie die PDF einzelner Themen oder eine ganze Map-Datei generieren. Sie können Ihre Themen im PDF-Format mithilfe der nativen PDF- oder DITA-OT-Methode veröffentlichen. Verwenden Sie die native PDF-Methode, um eine funktionsreiche PDF-Ausgabe basierend auf W3C CSS3- und CSS-Medienstandards zu generieren. Sie können die DITA-OT-Methode verwenden, um eine PDF-Ausgabe für eine Zuordnung aus dem Map-Dashboard zu generieren.

>[!NOTE]
>
> Native PDF ist die Standardmethode zum Generieren einer PDF in der aktuellen Version von AEM Guides.

So aktivieren Sie die alte PDF-Generierung über DITA-OT im Themenvorschaumodus:

1. Melden Sie sich bei Adobe Experience Manager als Administrator an und laden Sie die Konfigurationsdatei der Benutzeroberfläche herunter.

1. Klicken Sie dazu oben auf den Adobe Experience Manager-Link und wählen Sie **Tools** aus.
1. Wählen Sie **Handbücher** aus der Liste der Tools und klicken Sie auf **Ordnerprofile**.
1. Klicken Sie auf die Kachel **Globales Profil** .
1. Wählen Sie die Registerkarte **XML-Editor-Konfiguration** aus und klicken Sie oben auf das Symbol **Bearbeiten** .
1. Klicken Sie auf das Symbol **Download** , um die Datei ui\_config.json auf Ihr lokales System herunterzuladen. Anschließend können Sie Änderungen an der Datei vornehmen und diese dann hochladen.
1. Suchen Sie in der Datei &quot;`ui_config.json`&quot;die folgende Konfiguration:

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

   und ersetzen Sie sie durch

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

Wenn Sie nach dem Ausführen der oben genannten Schritte unter Benutzereinstellungen im Web-Editor dasselbe Ordnerprofil auswählen, wird im Vorschaumodus eines Themas die Option zum Generieren von PDF angezeigt.

**Übergeordnetes Thema:**[ Web-Editor anpassen](conf-web-editor.md)
