---
title: Eingabeaufforderung zum Einchecken einer Datei beim Schließen konfigurieren
description: Erfahren Sie, wie Sie die Aufforderung zum Einchecken einer Datei beim Schließen konfigurieren
exl-id: d184c97f-8405-4bcd-963d-635f17584897
feature: Web Editor Configuration
role: Admin
level: Experienced
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '200'
ht-degree: 1%

---

# Eingabeaufforderung zum Einchecken einer Datei beim Schließen konfigurieren {#id222HC040PE8}

Wenn der Benutzer versucht, eine Datei zu schließen, die im Web Editor mit der Schaltfläche **Schließen** auf der Registerkarte der Datei geöffnet ist, oder mit der Option **Schließen** im Menü &quot;Optionen&quot;wird ein Dialogfeld angezeigt, wenn die Datei nicht gespeicherte Daten oder eine nicht gespeicherte Version aufweist. Der Benutzer wird aufgefordert, die Datei zu entsperren, wenn sie gesperrt ist.

Das Kontrollkästchen **Datei entsperren** ist standardmäßig nicht aktiviert und Sie müssen dies über configMgr aktivieren. Führen Sie die folgenden Schritte aus, um die Option standardmäßig im Web-Editor zu aktivieren:

1. Öffnen Sie die Seite Adobe Experience Manager Web Console Configuration .

   Die Standard-URL für den Zugriff auf die Konfigurationsseite lautet:

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Suchen Sie nach dem Bundle **com.adobe.fmdita.xmleditor.config.XmlEditorConfig** und klicken Sie darauf.

1. Wählen Sie die Option **Beim Schließen nach Einchecken fragen** aus.

1. Klicken Sie auf **Speichern**.


Wenn diese Konfiguration aktiviert ist, ist im Dialogfeld standardmäßig das Kontrollkästchen **Datei entsperren** aktiviert.

Weitere Informationen finden Sie im Abschnitt *Szenarien schließen und speichern* im Handbuch Verwenden von Adobe Experience Manager Guides as a Cloud Service .

**Übergeordnetes Thema:**[ Web-Editor anpassen](conf-web-editor.md)
