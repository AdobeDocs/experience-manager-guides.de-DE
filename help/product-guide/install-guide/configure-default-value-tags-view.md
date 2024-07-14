---
title: Standardwert für die Tag-Ansicht konfigurieren
description: Erfahren Sie, wie Sie den Standardwert für die Tag-Ansicht konfigurieren
exl-id: 52214459-74b8-47ec-982b-6176145348a8
feature: Web Editor Configuration
role: Admin
level: Experienced
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '214'
ht-degree: 0%

---

# Standardwert für die Tag-Ansicht konfigurieren {#id223GN0M0NDC}

Mit AEM Guides können Sie den Standardstatus für die Tags-Ansicht im Web Editor konfigurieren. So können Sie die Tags-Ansicht standardmäßig für die Sitzung eines neuen Benutzers aktivieren oder deaktivieren. Führen Sie die folgenden Schritte aus, um den Standardwert für die Tag-Ansicht zu konfigurieren:

1. Laden Sie die Konfigurationsdatei der Benutzeroberfläche herunter, indem Sie sich bei Adobe Experience Manager als Administrator anmelden.
1. Klicken Sie oben auf den Adobe Experience Manager-Link und wählen Sie **Tools** aus.
1. Wählen Sie **Handbücher** aus der Liste der Tools und klicken Sie auf **Ordnerprofile**.
1. Klicken Sie auf die Kachel **Globales Profil** .
1. Wählen Sie die Registerkarte **XML-Editor-Konfiguration** aus und klicken Sie oben auf das Symbol **Bearbeiten** .
1. Klicken Sie im Abschnitt **Konfiguration der XML-Editor-Benutzeroberfläche** auf das Symbol **Download** , um die Datei `ui_config.json` auf Ihr lokales System herunterzuladen.
1. Ändern Sie in der Datei &quot;`ui_config.json`&quot;den Status der standardmäßigen Tags-Ansicht, indem Sie den Abschnitt defaultValues wie unten gezeigt ändern:

   ```json
   "defaultValues":
                   {
                   "tagsView": true
                   }
   ```

1. Speichern Sie die Datei und laden Sie sie hoch.

>[!NOTE]
>
> Die Voreinstellung des Benutzers im Web Editor zum Aktivieren/Deaktivieren der Tags-Ansicht hat Vorrang vor diesem Standardwert. Wenn ein Benutzer also die Tag-Ansicht über den Web-Editor aktiviert, bleibt sie auch während der Sitzungen aktiviert.

**Übergeordnetes Thema:**[ Web-Editor anpassen](conf-web-editor.md)
