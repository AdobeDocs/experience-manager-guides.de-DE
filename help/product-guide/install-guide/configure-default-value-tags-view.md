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

Mit AEM Guides können Sie den Standardstatus für die Tag-Ansicht im Web-Editor konfigurieren, sodass die Tag-Ansicht für die Sitzung eines neuen Benutzers standardmäßig aktiviert oder deaktiviert bleibt. Führen Sie die folgenden Schritte aus, um den Standardwert für die Tag-Ansicht zu konfigurieren:

1. Laden Sie die Konfigurationsdatei für die Benutzeroberfläche herunter, indem Sie sich als Administrator bei Adobe Experience Manager anmelden.
1. Klicken Sie oben auf den Adobe Experience Manager-Link und wählen Sie **Tools** aus.
1. Wählen Sie **Guides** aus der Liste der Tools aus und klicken Sie auf **Ordnerprofile**.
1. Klicken Sie auf die **Globales Profil**-Kachel.
1. Wählen Sie die Registerkarte **XML** Editor-Konfiguration) aus und klicken Sie oben auf **Symbol** Bearbeiten“.
1. Klicken Sie im Abschnitt **Konfiguration der Benutzeroberfläche des XML** Editors auf das **Herunterladen**-Symbol, um die `ui_config.json`-Datei auf Ihr lokales System herunterzuladen.
1. Ändern Sie in der `ui_config.json`-Datei den Ansichtsstatus der Standard-Tags, indem Sie den Abschnitt defaultValues wie unten dargestellt ändern:

   ```json
   "defaultValues":
                   {
                   "tagsView": true
                   }
   ```

1. Speichern Sie die Datei und laden Sie sie hoch.

>[!NOTE]
>
> Die Voreinstellung des Benutzers im Web-Editor zum Aktivieren/Deaktivieren der Tag-Ansicht hat Vorrang vor diesem Standardwert. Wenn ein Benutzer also die Tags-Ansicht im Web-Editor aktiviert, bleibt sie auch über die gesamten Sitzungen hinweg aktiviert.

**Übergeordnetes Thema:**&#x200B;[ Anpassen des Web-Editors](conf-web-editor.md)
