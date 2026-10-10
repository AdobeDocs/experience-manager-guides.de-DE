---
title: Konfigurieren der PDF-Generierung für ein einzelnes Thema
description: Erfahren Sie, wie Sie die PDF-Generierung für einzelne Themen konfigurieren
feature: Web Editor Configuration
role: Admin
level: Experienced
exl-id: a456027a-56a4-48c0-a79b-2f423692abc2
product_v2:
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
    internal-label: Experience Manager
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
    internal-label: Experience Manager Guides
feature_v2:
  - id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
    internal-label: Configuration
subfeature_v2:
  - id: b0521e56-a0b2-40b6-bf47-ebc98751f9ba
    internal-label: Web Editor configuration
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
level_v2:
  - id: d378ca77-2da1-4f39-ad92-1917fe974a38
    internal-label: Experienced
source-git-commit: 81a0e7f0736ba4970673dd87a888a4c60d3c1b4e
workflow-type: tm+mt
source-wordcount: '272'
ht-degree: 0%
---
# Konfigurieren der PDF-Generierung für ein einzelnes Thema für Cloud Service

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

Wenn Sie nach dem Ausführen der oben genannten Schritte dasselbe Ordnerprofil aus den Benutzereinstellungen im Editor auswählen, wird im Vorschaumodus eines Themas die Option für die PDF-Generierung angezeigt.

**Übergeordnetes Thema:**&#x200B;[&#x200B; Editor anpassen](customize-overview.md)
