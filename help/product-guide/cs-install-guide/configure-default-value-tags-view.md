---
title: Standardwert für die Tag-Ansicht konfigurieren
description: Erfahren Sie, wie Sie den Standardwert für die Tag-Ansicht konfigurieren
exl-id: 3ab75101-4c23-4e45-bfcf-76c1f5b92c96
feature: Web Editor Configuration
role: Admin
level: Experienced
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '215'
ht-degree: 0%

---

# Standardwert für die Tag-Ansicht konfigurieren {#id223GN0M0NDC}

Mit AEM Guides können Sie den Standardstatus für die Tag-Ansicht im Web Editor konfigurieren. So können Sie die Tag-Ansicht für eine neue Benutzersitzung standardmäßig aktivieren oder deaktivieren. Führen Sie die folgenden Schritte aus, um den Standardwert für die Tag-Ansicht zu konfigurieren:

1. Laden Sie die Konfigurationsdatei der Benutzeroberfläche herunter, indem Sie sich bei Adobe Experience Manager als Administrator anmelden.
1. Klicken Sie oben auf den Adobe Experience Manager-Link und wählen Sie **Instrumente**.
1. Auswählen **Handbücher** aus der Liste der Tools und klicken Sie auf die Schaltfläche **Ordnerprofile**.
1. Klicken Sie auf **Globales Profil** Kachel.
1. Wählen Sie die **Konfiguration des XML-Editors** und klicken Sie auf **Bearbeiten** Symbol oben.
1. Im **Konfiguration der Benutzeroberfläche des XML-Editors** klicken Sie auf die **Herunterladen** zum Herunterladen des `ui_config.json` -Datei auf Ihrem lokalen System.
1. Im `ui_config.json` ändern Sie den Status der standardmäßigen Tags-Ansicht, indem Sie den Abschnitt defaultValues wie unten gezeigt ändern:

```
"defaultValues":
                {
                "tagsView": true
                }
```

1.) Speichern Sie die Datei und laden Sie sie hoch.

>[!NOTE]
>
> Die Voreinstellung des Benutzers im Web Editor zum Aktivieren/Deaktivieren der Tags-Ansicht hat Vorrang vor diesem Standardwert. Wenn ein Benutzer also die Tag-Ansicht über den Web-Editor aktiviert, bleibt sie auch während der Sitzungen aktiviert.

**Übergeordnetes Thema:**[ Anpassen des Web-Editors](conf-web-editor.md)
