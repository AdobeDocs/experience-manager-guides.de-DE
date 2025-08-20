---
title: Konfigurieren des Speicherorts der Basisausgabe für die Veröffentlichung der Ausgabe für On-Premise-Services
description: Konfigurieren des Speicherorts der Basisausgabe für die Veröffentlichung der Ausgabe für On-Premise-Services
feature: Output Generation
role: Admin
level: Experienced
source-git-commit: ab6f1f09de2ef758d7f05ba0a49194ac9f387dea
workflow-type: tm+mt
source-wordcount: '108'
ht-degree: 1%

---

# Konfigurieren des Speicherorts der Basisausgabe für die Veröffentlichung der Ausgabe für On-Premise-Services

Führen Sie die folgenden Schritte aus, um den Basisausgabespeicherort zu konfigurieren:

1. Öffnen Sie die Seite Konfiguration der Adobe Experience Manager-Web-Konsole .

   Die Standard-URL für den Zugriff auf die Konfigurationsseite lautet:

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Suchen Sie nach dem Bundle *com.adobe.fmdita.config.ConfigManager* und wählen Sie es aus.

1. Aktualisieren Sie die Eigenschaft **Basisausgabespeicherort**, um den Standardpfad im AEM-Repository anzugeben, in dem die PDF nach der Veröffentlichung gespeichert wird. Wenn ein ungültiger Pfad eingegeben wird, wird außerdem automatisch zum Standardpfad zurückgesetzt: /content/dam/fmdita-output.

1. Klicken Sie auf **Speichern**.


