---
title: Standardwert für die Tag-Ansicht konfigurieren
description: Erfahren Sie, wie Sie den Standardwert für die Tag-Ansicht konfigurieren
exl-id: 3ab75101-4c23-4e45-bfcf-76c1f5b92c96
feature: Web Editor Configuration
role: Admin
level: Experienced
TQID: 'https://experienceleague.adobe.com/e-BZ7-itZXflsqHW9-5Vo6ktr9RS73xdIWMZh4BU2MU'
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
    internal-label: Experience Manager Guides
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
    internal-label: Experience Manager
feature_v2:
  - id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
    internal-label: Configuration
subfeature_v2:
  - id: b0521e56-a0b2-40b6-bf47-ebc98751f9ba
    internal-label: Web Editor configuration
  - id: b1ef4d86-3917-4b76-a0bc-4a4771f9b3b0
    internal-label: Profiles
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
level_v2:
  - id: d378ca77-2da1-4f39-ad92-1917fe974a38
    internal-label: Experienced
source-git-commit: 81a0e7f0736ba4970673dd87a888a4c60d3c1b4e
workflow-type: tm+mt
source-wordcount: '215'
ht-degree: 0%
---
# Standardwert für die Tag-Ansicht konfigurieren {#id223GN0M0NDC}

AEM Guides ermöglicht es Ihnen, den Standardstatus für die Tag-Ansicht im Web-Editor zu konfigurieren, sodass die Tag-Ansicht für die Sitzung eines neuen Benutzers standardmäßig aktiviert oder deaktiviert bleibt.Führen Sie die folgenden Schritte aus, um den Standardwert für die Tag-Ansicht zu konfigurieren:

1. Laden Sie die Konfigurationsdatei für die Benutzeroberfläche herunter, indem Sie sich als Administrator bei Adobe Experience Manager anmelden.
1. Klicken Sie oben auf den Adobe Experience Manager-Link und wählen Sie **Tools** aus.
1. Wählen Sie **Guides** aus der Liste der Tools aus und klicken Sie auf **Ordnerprofile**.
1. Klicken Sie auf die **Globales Profil**-Kachel.
1. Wählen Sie die Registerkarte **XML** Editor-Konfiguration) aus und klicken Sie oben auf **Symbol** Bearbeiten“.
1. Klicken Sie im Abschnitt **Konfiguration der Benutzeroberfläche des XML** Editors auf das **Herunterladen**-Symbol, um die `ui_config.json`-Datei auf Ihr lokales System herunterzuladen.
1. Ändern Sie in der `ui_config.json`-Datei den Ansichtsstatus der Standard-Tags, indem Sie den Abschnitt defaultValues wie unten dargestellt ändern:

```
"defaultValues":
                {
                "tagsView": true
                }
```

1.) Speichern Sie die Datei und laden Sie sie hoch.

>[!NOTE]
>
> Die Voreinstellung des Benutzers im Web-Editor zum Aktivieren/Deaktivieren der Tag-Ansicht hat Vorrang vor diesem Standardwert. Wenn ein Benutzer also die Tags-Ansicht im Web-Editor aktiviert, bleibt sie auch über die gesamten Sitzungen hinweg aktiviert.

**Übergeordnetes Thema:**[ Anpassen des Web-Editors](conf-web-editor.md)
