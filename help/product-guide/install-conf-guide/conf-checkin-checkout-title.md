---
title: Konfigurieren des Titels für die Symbole „Einchecken“ und „Auschecken“
description: Erfahren Sie, wie Sie den Titel für die Symbole zum Ein- und Auschecken konfigurieren
feature: Web Editor Configuration
role: Admin
level: Experienced
exl-id: 3032b49e-73d1-44d0-88b4-7e6e9444cac6
source-git-commit: cc73b81787a3c3dbe8390d93e558064327e59965
workflow-type: tm+mt
source-wordcount: '168'
ht-degree: 0%

---

# Konfigurieren des Titels für die Symbole zum Ein- und Auschecken für On-Premise

Mit AEM Guides können Sie den Titel für die Symbole zum Ein- und Auschecken im Editor konfigurieren. Führen Sie die folgenden Schritte aus, um den Titel für die Symbole zum Ein- und Auschecken zu konfigurieren:

1. Laden Sie die Konfigurationsdatei für die Benutzeroberfläche herunter, indem Sie sich als Administrator bei Adobe Experience Manager anmelden.
1. Klicken Sie oben auf den Adobe Experience Manager-Link und wählen Sie **Tools** aus.
1. Wählen Sie **Guides** aus der Liste der Tools aus und klicken Sie auf **Ordnerprofile**.
1. Klicken Sie auf die **Globales Profil**-Kachel.
1. Wählen Sie die Registerkarte **XML** Editor-Konfiguration) aus und klicken Sie oben auf **Symbol** Bearbeiten“.
1. Klicken Sie im Abschnitt **Konfiguration der Benutzeroberfläche des XML** Editors auf das **Herunterladen**-Symbol, um die `ui_config.json`-Datei auf Ihr lokales System herunterzuladen.
1. Ändern Sie in der `ui_config.json`-Datei den Titel im Abschnitt „topbar“. Sie können die folgenden Werte ändern:

   ```json
   //Change title to "Check out" instead of "Lock"
           "title": "Check out"
   
   //Change title to "Check in" instead of "@checkOutBy
            "title": "Check in"
   ```

1. Speichern Sie die Datei und laden Sie sie hoch.
