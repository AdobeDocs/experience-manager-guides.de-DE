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

Wenn der Benutzer versucht, eine Datei zu schließen, die im Web-Editor mit dem **Schließen** auf der Registerkarte der Datei oder **Schließen** im Menü Optionen wird ein Dialogfeld angezeigt, wenn die Datei nicht gespeicherte Daten oder eine nicht gespeicherte Version aufweist. Der Benutzer wird aufgefordert, die Datei zu entsperren, wenn sie gesperrt ist.

Die **Datei entsperren** nicht standardmäßig aktiviert ist und Sie dies über configMgr aktivieren müssen. Führen Sie die folgenden Schritte aus, um die Option standardmäßig im Web-Editor zu aktivieren:

1. Öffnen Sie die Seite Adobe Experience Manager Web Console Configuration .

   Die Standard-URL für den Zugriff auf die Konfigurationsseite lautet:

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Suchen Sie nach und klicken Sie auf **com.adobe.fmdita.xmleditor.config.XmlEditorConfig** Bundle

1. Wählen Sie die **Beim Schließen Einchecken anfordern** -Option.

1. Klicken Sie auf **Speichern**.


Wenn diese Konfiguration aktiviert ist, wird die **Datei entsperren** ist im Dialogfeld standardmäßig aktiviert.

Weitere Informationen finden Sie unter *Szenarien zum Schließen und Speichern von Dateien* im as a Cloud Service Handbuch Verwenden von Adobe Experience Manager-Handbüchern beschrieben.

**Übergeordnetes Thema:**[ Anpassen des Web-Editors](conf-web-editor.md)
