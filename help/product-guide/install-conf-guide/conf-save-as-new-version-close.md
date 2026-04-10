---
title: Eingabeaufforderung zum Speichern als neue Version beim Schließen konfigurieren
description: Erfahren Sie, wie Sie die Eingabeaufforderung konfigurieren, um beim Schließen als neue Version zu speichern
feature: Web Editor Configuration
role: Admin
level: Experienced
source-git-commit: 6f3f05419f4f5cdd45ab580cdee6fa869f20f01d
workflow-type: tm+mt
source-wordcount: '300'
ht-degree: 1%

---

# Eingabeaufforderung zum Speichern als neue Version beim Schließen konfigurieren {#id222HBI00XXA}

Wenn der/die Benutzende versucht, eine Datei zu schließen, die im Web-Editor mit der Schaltfläche **Schließen** auf der Registerkarte der Datei oder der Option **Schließen** im Menü Optionen geöffnet wurde, wird ein Dialogfeld angezeigt, wenn die Datei ungespeicherte Daten oder eine ungespeicherte Version enthält. Der/die Benutzende wird aufgefordert, die Datei als neue Version zu speichern, wenn die Version nicht gespeichert wurde.

Die folgenden Registerkarten enthalten Anweisungen basierend auf Ihrer Experience Manager Guides-Einrichtung: Cloud Service oder On-Premise.

>[!BEGINTABS]

>[!TAB Cloud Service]

Verwenden Sie die Anweisungen unter [Konfigurationsüberschreibungen](download-install-config-override.md#), um die Konfigurationsdatei zu erstellen. Geben Sie in der Konfigurationsdatei die folgenden \(property\)-Details ein, um beim Schließen eine Eingabeaufforderung zum Speichern als neue Version zu konfigurieren:

| PID | Eigenschaftsschlüssel | Eigenschaftswert |
|---|------------|--------------|
| `com.adobe.fmdita.xmleditor.config.XmlEditorConfig` | `xmleditor.savenewversion` | Boolescher Wert \( true/false\). <br>  **Standardwert**: true |

Wenn diese Konfiguration aktiviert ist **ist das Kontrollkästchen** Als neue Version speichern“ im Dialogfeld standardmäßig aktiviert.

Weitere Informationen finden Sie *Abschnitt „Schließen und Speichern von Dateien* im Handbuch Verwenden von Adobe Experience Manager Guides as a Cloud Service .

>[!TAB On-Premise]

1. Öffnen Sie die Seite Konfiguration der Adobe Experience Manager-Web-Konsole .

   Die Standard-URL für den Zugriff auf die Konfigurationsseite lautet:

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Suchen Sie nach dem Bundle **com.adobe.fmdita.xmeditor.config.XmlEditorConfig** und klicken Sie darauf.

1. Wählen Sie die Option **Beim Schließen nach neuer Version**.

1. Klicken Sie auf **Speichern**.


Das **Als neue Version speichern**-Kontrollkästchen ist nicht standardmäßig aktiviert. Sie müssen es daher im configMgr aktivieren.

Wenn diese Option ausgewählt ist **ist das Kontrollkästchen** Als neue Version speichern“ im Dialogfeld standardmäßig aktiviert.

Weitere Informationen finden Sie *Abschnitt „Schließen und Speichern von Dateien* im Handbuch Verwenden von Adobe Experience Manager Guides as a Cloud Service .

>[!ENDTABS]