---
title: Eingabeaufforderung zum Einchecken einer Datei beim Schließen konfigurieren
description: Erfahren Sie, wie Sie eine Eingabeaufforderung konfigurieren, um beim Schließen eine Datei einzuchecken
exl-id: d184c97f-8405-4bcd-963d-635f17584897
feature: Web Editor Configuration
role: Admin
level: Experienced
TQID: https://experienceleague.adobe.com/mK01xE-ysqIXm9YL5xkvp1dz1-3hGr63kvt-cePEHSA
product_v2: id: fae5e35a-80c9-4b94-9352-1a060a6aab1did: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2: id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
subfeature_v2: id: b0521e56-a0b2-40b6-bf47-ebc98751f9ba
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: cc73b81787a3c3dbe8390d93e558064327e59965
workflow-type: tm+mt
source-wordcount: 196
ht-degree: 1%

---

# Eingabeaufforderung zum Einchecken einer Datei beim Schließen konfigurieren {#id222HC040PE8}

Wenn der/die Benutzende versucht, eine Datei zu schließen, die im Editor mit der Schaltfläche **Schließen** auf der Registerkarte der Datei oder der Option **Schließen** im Menü Optionen geöffnet wurde, wird ein Dialogfeld angezeigt, wenn die Datei ungespeicherte Daten oder eine ungespeicherte Version enthält. Der Benutzer wird aufgefordert, die Datei zu entsperren, wenn sie gesperrt ist.

Das **„Datei entsperren** ist nicht standardmäßig aktiviert und muss im configMgr aktiviert werden. Führen Sie die folgenden Schritte aus, um die Option im Editor standardmäßig zu aktivieren:

1. Öffnen Sie die Seite Konfiguration der Adobe Experience Manager-Web-Konsole .

   Die Standard-URL für den Zugriff auf die Konfigurationsseite lautet:

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Suchen Sie nach dem Bundle **com.adobe.fmdita.xmeditor.config.XmlEditorConfig** und klicken Sie darauf.

1. Wählen Sie die Option **Beim Schließen um Einchecken**.

1. Klicken Sie auf **Speichern**.


Wenn diese Konfiguration aktiviert ist **ist das Kontrollkästchen** Datei entsperren“ im Dialogfeld standardmäßig aktiviert.

Weitere Informationen finden Sie *Abschnitt „Schließen und Speichern von Dateien* im Handbuch Verwenden von Adobe Experience Manager Guides as a Cloud Service .

**Übergeordnetes Thema:**[ Editor anpassen](conf-web-editor.md)
