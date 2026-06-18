---
title: Eingabeaufforderung zum Einchecken einer Datei beim Schließen konfigurieren
description: Erfahren Sie, wie Sie eine Eingabeaufforderung konfigurieren, um beim Schließen eine Datei einzuchecken
feature: Web Editor Configuration
role: Admin
level: Experienced
exl-id: 6b1b5894-0d55-4230-83cf-6b219e969116
source-git-commit: cc73b81787a3c3dbe8390d93e558064327e59965
workflow-type: tm+mt
source-wordcount: '317'
ht-degree: 1%

---

# Eingabeaufforderung zum Einchecken einer Datei beim Schließen konfigurieren {#id222HC040PE8}

Wenn der/die Benutzende versucht, eine Datei zu schließen, die im Editor mit der Schaltfläche **Schließen** auf der Registerkarte der Datei oder der Option **Schließen** im Menü Optionen geöffnet wurde, wird ein Dialogfeld angezeigt, wenn die Datei ungespeicherte Daten oder eine ungespeicherte Version enthält. Der Benutzer wird aufgefordert, die Datei zu entsperren, wenn sie gesperrt ist.

Die folgenden Registerkarten enthalten Anweisungen zum Konfigurieren der Option „Aufforderung zum Einchecken einer Datei beim Schließen“ im Editor, basierend auf Ihrer Experience Manager Guides-Einrichtung: Cloud Service oder On-Premise.

>[!BEGINTABS]

>[!TAB Cloud Service]

Verwenden Sie die Anweisungen unter [Konfigurationsüberschreibungen](download-install-config-override.md#), um die Konfigurationsdatei zu erstellen. Geben Sie in der Konfigurationsdatei die folgenden \(property\)-Details an, um eine Eingabeaufforderung zum Einchecken einer Datei beim Schließen zu konfigurieren:

| PID | Eigenschaftsschlüssel | Eigenschaftswert |
|---|------------|--------------|
| `com.adobe.fmdita.xmleditor.config.XmlEditorConfig` | `xmleditor.checkin` | Boolescher Wert \( true/false\).<br> **Standardwert**: false |

Wenn diese Konfiguration aktiviert ist **ist das Kontrollkästchen** Datei entsperren“ im Dialogfeld standardmäßig aktiviert.

Weitere Informationen finden Sie *Abschnitt „Schließen und Speichern von Dateien* im Handbuch Verwenden von Adobe Experience Manager Guides as a Cloud Service .

>[!TAB On-Premise]

>[!NOTE]
>
>Das **„Datei entsperren** ist nicht standardmäßig aktiviert und muss im configMgr aktiviert werden. Führen Sie die folgenden Schritte aus, um die Option im Editor standardmäßig zu aktivieren:

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

>[!ENDTABS]

**Übergeordnetes Thema:**[ Editor anpassen](customize-overview.md)
