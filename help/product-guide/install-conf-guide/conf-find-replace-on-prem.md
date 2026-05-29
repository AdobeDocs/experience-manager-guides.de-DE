---
title: Konfigurieren von Suchen und Ersetzen (Source-Ansicht) für On-Premise
description: Erfahren Sie, wie Sie Suchen und Ersetzen (Source-Ansicht) für On-Premise konfigurieren
feature: Configuration
role: Admin
level: Experienced
source-git-commit: 8d231bdbf00adb354bc31616e880495b00a3959c
workflow-type: tm+mt
source-wordcount: '84'
ht-degree: 2%

---

# Konfigurieren von Suchen und Ersetzen (Source-Ansicht) für On-Premise

Die folgenden Schritte erläutern, wie Sie die Ansicht „Suchen und Ersetzen“ (Source-Ansicht) in Ihrer On-Premise-Umgebung aktivieren.

1. Öffnen Sie die Seite Konfiguration der Adobe Experience Manager-Web-Konsole .

   Die Standard-URL für den Zugriff auf die Konfigurationsseite lautet:

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Suchen Sie nach dem Bundle **com.adobe.fmdita.config.ConfigManager** und wählen Sie es aus.

1. Aktivieren Sie die Einstellung **Markup suchen und ersetzen aktivieren** (enable.markup.findreplace).

1. Wählen Sie **Speichern** aus.
