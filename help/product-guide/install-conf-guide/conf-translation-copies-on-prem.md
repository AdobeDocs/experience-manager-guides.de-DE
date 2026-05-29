---
title: Konfigurieren der Initialisierung der Zielkopie im Übersetzungs-Workflow für On-Premise
description: Erfahren Sie, wie Sie die Initialisierung der Zielkopie im Übersetzungs-Workflow für On-Premise aktivieren oder deaktivieren
feature: Configuration
role: Admin
level: Experienced
source-git-commit: 8d231bdbf00adb354bc31616e880495b00a3959c
workflow-type: tm+mt
source-wordcount: '111'
ht-degree: 1%

---

# Konfigurieren der Initialisierung der Zielkopie im Übersetzungs-Workflow für On-Premise

Die folgenden Schritte erklären, wie Sie die Initialisierung der Zielkopie im Übersetzungs-Workflow für Ihre On-Premise-Umgebung aktivieren.

1. Öffnen Sie die Seite Konfiguration der Adobe Experience Manager-Web-Konsole .

   Die Standard-URL für den Zugriff auf die Konfigurationsseite lautet:

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Suchen Sie nach dem Bundle **com.adobe.fmdita.config.ConfigManager** und wählen Sie es aus.

1. Aktivieren oder deaktivieren Sie die Einstellung **Initialisieren der Zielsprachkopie mit Quellinhalten** ( translation.workflow.propagate.source.content) gemäß Ihren Anforderungen. Diese Einstellung gilt nur, wenn der alte Übersetzungs-Workflow deaktiviert ist.

1. Wählen Sie **Speichern** aus.
