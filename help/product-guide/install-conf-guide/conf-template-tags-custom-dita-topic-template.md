---
title: Konfigurieren einer benutzerdefinierten DITA-Themenvorlage
description: Erfahren Sie, wie Sie eine benutzerdefinierte DITA-Themenvorlage konfigurieren
feature: Template Configuration
role: Admin
level: Experienced
source-git-commit: 6f3f05419f4f5cdd45ab580cdee6fa869f20f01d
workflow-type: tm+mt
source-wordcount: '488'
ht-degree: 2%

---

# Konfigurieren einer benutzerdefinierten DITA-Themenvorlage {#id16A7G0O02TD}

Im Lieferumfang von AEM Guides sind die folgenden DITA-Themenvorlagen enthalten:

- Thema

- Aufgabe

- Konzept

- Referenz

- Glossar

- Fehlerbehebung

- Leer


Sie können jede dieser Vorlagen verwenden, um Themenvorlagen gemäß Ihren Authoring-Anforderungen zu erstellen. Die Vorlage Leere DITA enthält keine Struktur oder Elemente wie die anderen Vorlagen. Sie können die leere Vorlage als Grundlage verwenden, wenn Ihre Vorlage stark angepasst ist und nicht auf regulären DITA-Themenvorlagen basiert.

Um die DITA-Themenvorlage anzupassen und für das Authoring zu verwenden, müssen Sie die folgenden drei Hauptaufgaben ausführen:

1. *\(Optional\)* [Konfigurieren des benutzerdefinierten DITA-Vorlagenordnerpfads](#id191LCF0095Z)

1. [Erstellen einer benutzerdefinierten Authoring-Vorlage](conf-profiles.md#id1917D0EG0HJ)

1. Fügen Sie eine benutzerdefinierte Vorlage zum globalen Profil oder zum Profil auf Ordnerebene hinzu, wie im Abschnitt [Konfigurieren von Authoring-Vorlagen](conf-profiles.md#id1889D0IL0Y4) beschrieben


## Konfigurieren des benutzerdefinierten DITA-Vorlagenordnerpfads {#id191LCF0095Z}

Mit AEM Guides können Sie einen Ordner konfigurieren, in dem Sie Ihre benutzerdefinierten DITA-Karten und -Vorlagen speichern können. Standardmäßig werden die Vorlagendateien im folgenden Ordner in DAM gespeichert:

`/content/dam/dita-templates/`

Um Themen- und Zuordnungsvorlagendateien zu verwalten, stehen dedizierte Ordner zum Speichern des Themas und Zuordnungsvorlagen zur Verfügung. Standardmäßig werden alle Themenvorlagen unter dem `/content/dam/dita-templates/topics` gespeichert

Ordner. Alle Zuordnungsvorlagen werden im Ordner `/content/dam/dita-templates/maps` gespeichert.

Als Administrator können Sie benutzerdefinierte Zuordnungs- oder Themenvorlagen im Standardordner erstellen oder Ihren eigenen Ordner erstellen, um benutzerdefinierte Vorlagen zu speichern. Wenn Sie planen, den Standardordner zu verwenden, können Sie diesen Prozess überspringen.

Die folgenden Registerkarten enthalten Anweisungen zum Konfigurieren des benutzerdefinierten DITA-Vorlagenordnerpfads basierend auf Ihrer Experience Manager Guides-Einrichtung: Cloud Service oder On-Premise.


>[!BEGINTABS]

>[!TAB Cloud Service]

Verwenden Sie die Anweisungen unter [Konfigurationsüberschreibungen](download-install-config-override.md#), um die Konfigurationsdatei zu erstellen. Geben Sie in der Konfigurationsdatei die folgenden \(property\)-Details an, um einen Ordner für Ihre benutzerdefinierten DITA-Themenvorlagen zu konfigurieren:

>[!IMPORTANT]
>
> Sie können diesen Prozess überspringen, wenn Sie den Standardordner zum Speichern benutzerdefinierter Vorlagen verwenden möchten.

| PID | Eigenschaftsschlüssel | Eigenschaftswert |
|---|------------|--------------|
| `com.adobe.fmdita.config.ConfigManager` | `topic.templates` | Speicherort für benutzerdefinierte Vorlagen angeben.<br> Wenn der angegebene Speicherort in DAM vorhanden ist, werden alle Standardzuordnungs- und Themenvorlagen in diesen Ordner kopiert. Wenn der Speicherort nicht vorhanden ist, wird der Ordner mit allen standardmäßigen Zuordnungs- und Themenvorlagen erstellt. |

>[!TAB On-Premise]

Führen Sie die folgenden Schritte aus, um einen Ordner für Ihre benutzerdefinierten DITA-Themenvorlagen zu konfigurieren:

>[!IMPORTANT]
>
> Sie können diesen Prozess überspringen, wenn Sie den Standardordner zum Speichern benutzerdefinierter Vorlagen verwenden möchten.

1. Öffnen Sie die Seite Konfiguration der Adobe Experience Manager-Web-Konsole .

   Die Standard-URL für den Zugriff auf die Konfigurationsseite lautet:

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Suchen Sie nach dem Bundle *com.adobe.fmdita.config.ConfigManager* und klicken Sie darauf.

1. Geben **in der Eigenschaft** Vorlagenspeicherort“ einen Speicherort für benutzerdefinierte Vorlagen an.

1. Klicken Sie auf **Speichern**.


Wenn der angegebene Speicherort in DAM vorhanden ist, werden alle standardmäßigen Zuordnungs- und Themenvorlagen in diesen Ordner kopiert. Wenn der Speicherort nicht vorhanden ist, wird der Ordner mit allen standardmäßigen Zuordnungs- und Themenvorlagen erstellt.


>[!ENDTABS]


**Übergeordnetes Thema:**[ Konfigurieren von Themen- und Zuordnungsvorlagen](conf-template-tags.md)
