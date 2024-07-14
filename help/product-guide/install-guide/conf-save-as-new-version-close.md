---
title: Eingabeaufforderung zum Speichern als neue Version beim Schließen konfigurieren
description: Erfahren Sie, wie Sie die Aufforderung zum Speichern als neue Version beim Schließen konfigurieren
exl-id: 1b8c3eaa-a654-4563-9541-18a59b7d306c
feature: Web Editor Configuration
role: Admin
level: Experienced
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '214'
ht-degree: 0%

---

# Eingabeaufforderung zum Speichern als neue Version beim Schließen konfigurieren {#id222HBI00XXA}

Wenn der Benutzer versucht, eine Datei zu schließen, die im Web Editor mithilfe der Schaltfläche **Schließen** auf der Registerkarte der Datei oder der Option **Schließen** im Menü &quot;Optionen&quot;geöffnet ist, wird ein Dialogfeld angezeigt, wenn die Datei nicht gespeicherte Daten oder eine nicht gespeicherte Version aufweist. Der Benutzer wird aufgefordert, die Datei als neue Version zu speichern, wenn die Version nicht gespeichert wird.

Das Kontrollkästchen **Als neue Version speichern** ist standardmäßig nicht aktiviert und Sie müssen dies über configMgr aktivieren. Führen Sie die folgenden Schritte aus, um die Option standardmäßig im Web-Editor zu aktivieren:

1. Öffnen Sie die Seite Adobe Experience Manager Web Console Configuration .

   Die Standard-URL für den Zugriff auf die Konfigurationsseite lautet:

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Suchen Sie nach dem Bundle **com.adobe.fmdita.xmleditor.config.XmlEditorConfig** und klicken Sie darauf.

1. Wählen Sie die Option **Nach neuer Version beim Schließen fragen** aus.

1. Klicken Sie auf **Speichern**.


Wenn diese Option aktiviert ist, wird im Dialogfeld standardmäßig das Kontrollkästchen **Als neue Version speichern** aktiviert.

Weitere Informationen finden Sie im Abschnitt *Szenarien schließen und speichern* im Handbuch Verwenden von Adobe Experience Manager Guides as a Cloud Service .

**Übergeordnetes Thema:**[ Web-Editor anpassen](conf-web-editor.md)
