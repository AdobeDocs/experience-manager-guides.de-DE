---
title: Konfigurieren einer benutzerdefinierten DITA-Themenvorlage
description: Erfahren Sie, wie Sie eine benutzerdefinierte DITA-Themenvorlage konfigurieren
exl-id: 5a2f4897-9697-4c5c-b5be-8fdb3a211948
feature: Template Configuration
role: Admin
level: Experienced
TQID: https://experienceleague.adobe.com/PX1v2yPqLErAIST8JPr-vUwV81HH6EeFQ4LqKES9gkI
product_v2: id: fae5e35a-80c9-4b94-9352-1a060a6aab1did: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2: id: ab01a588-7dea-43f2-a699-0b3f128465d6id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
subfeature_v2: id: b1ef4d86-3917-4b76-a0bc-4a4771f9b3b0id: df6fa66f-4542-4a6d-90ca-9f146eb5d494
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: c1579802-ddd4-4214-8a91-97b2066abe11
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 354
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

1. [Erstellen einer benutzerdefinierten Authoring-Vorlage](conf-folder-level.md#id1917D0EG0HJ)

1. Fügen Sie eine benutzerdefinierte Vorlage zum globalen Profil oder zum Profil auf Ordnerebene hinzu, wie im Abschnitt [Konfigurieren von Authoring-Vorlagen](conf-folder-level.md#id1889D0IL0Y4) beschrieben


## Konfigurieren des benutzerdefinierten DITA-Vorlagenordnerpfads {#id191LCF0095Z}

Mit AEM Guides können Sie einen Ordner konfigurieren, in dem Sie Ihre benutzerdefinierten DITA-Karten und -Vorlagen speichern können. Standardmäßig werden die Vorlagendateien im folgenden Ordner in DAM gespeichert:

`/content/dam/dita-templates/`

Um Themen- und Zuordnungsvorlagendateien zu verwalten, stehen dedizierte Ordner zum Speichern des Themas und Zuordnungsvorlagen zur Verfügung. Standardmäßig werden alle Themenvorlagen unter dem `/content/dam/dita-templates/topics` gespeichert

Ordner. Alle Zuordnungsvorlagen werden im Ordner `/content/dam/dita-templates/maps` gespeichert.

Als Administrator können Sie benutzerdefinierte Zuordnungs- oder Themenvorlagen im Standardordner erstellen oder Ihren eigenen Ordner erstellen, um benutzerdefinierte Vorlagen zu speichern. Wenn Sie planen, den Standardordner zu verwenden, können Sie diesen Prozess überspringen.

Verwenden Sie die Anweisungen unter [Konfigurationsüberschreibungen](download-install-additional-config-override.md#), um die Konfigurationsdatei zu erstellen. Geben Sie in der Konfigurationsdatei die folgenden \(property\)-Details an, um einen Ordner für Ihre benutzerdefinierten DITA-Themenvorlagen zu konfigurieren:

>[!IMPORTANT]
>
> Sie können diesen Prozess überspringen, wenn Sie den Standardordner zum Speichern benutzerdefinierter Vorlagen verwenden möchten.

| PID | Eigenschaftsschlüssel | Eigenschaftswert |
|---|------------|--------------|
| `com.adobe.fmdita.config.ConfigManager` | `topic.templates` | Geben Sie einen Speicherort für benutzerdefinierte Vorlagen an.<br> Wenn der angegebene Speicherort in DAM vorhanden ist, werden alle standardmäßigen Zuordnungs- und Themenvorlagen in diesen Ordner kopiert. Wenn der Speicherort nicht vorhanden ist, wird der Ordner mit allen standardmäßigen Zuordnungs- und Themenvorlagen erstellt. |

**Übergeordnetes Thema:**[ Konfigurieren von Themen- und Zuordnungsvorlagen](conf-template-tags.md)
