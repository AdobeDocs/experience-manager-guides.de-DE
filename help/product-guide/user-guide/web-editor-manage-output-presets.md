---
title: Verwalten von globalen und Ordnerprofil-Ausgabevorgaben
description: Erfahren Sie, wie Sie in AEM Guides globale Ausgabevorgaben und Ordnerprofile als Admin-Benutzerinnen und -Benutzer erstellen, bearbeiten, umbenennen, duplizieren und löschen.
exl-id: 549c9fe2-77f8-423c-8b3e-b43e56055732
feature: Authoring, Features of Web Editor, Publishing
role: User
source-git-commit: f6ff978305d9a1587366acbe96d274408bf457f4
workflow-type: tm+mt
source-wordcount: '475'
ht-degree: 0%

---

# Verwalten von globalen und Ordnerprofil-Ausgabevorgaben {#id22BLJ0D0V1U}

Die globalen Vorgaben und Ordnerprofilvorgaben sind nur für Benutzer mit Administratorrechten auf Ordnerebene verfügbar.

Als Administrator können Sie mit Adobe Experience Manager Guides Ausgabevorgaben für die globalen Profile und Ordnerprofile erstellen und verwalten. Anschließend können Sie diese Ausgabevorgaben einfach verwenden, um eine Ausgabe für alle Zuordnungen zu generieren, die mit diesem globalen Profil oder Ordnerprofil verknüpft sind.

Führen Sie die folgenden Schritte aus, um eine Ausgabevorgabe für die globalen Profile und Ordnerprofile zu erstellen:

1. Wählen Sie die DITA-Zuordnung aus, für die Sie eine Ausgabevorgabe erstellen möchten.
1. Wählen Sie **Option** bearbeiten aus dem Menü **Optionen** der Zuordnungsdatei aus. Die Zuordnungsdatei wird im Editor zur Bearbeitung geöffnet.
1. Wählen Sie das **In Map-Konsole öffnen**, um die Map-Datei in der Map-Konsole zu öffnen.
1. Navigieren Sie in der Zuordnungskonsole zur Registerkarte **Ausgabevorgaben** und wählen Sie dann das Symbol + aus, um eine Ausgabevorgabe für Ihre DITA-Zuordnung zu erstellen.

   ![](images/add-global-output-preset.png){width="350" align="left"}

1. Geben Sie die folgenden Details im Dialogfeld **Vorgabe hinzufügen** ein:
   - Typ
   - Name
   - Target \(für Knowledgebase-Voreinstellung\)
1. Aktivieren Sie **Kontrollkästchen** Zu Ordnerprofil hinzufügen“, um eine Ausgabevorgabe für das zugehörige Ordnerprofil zu erstellen, und klicken Sie dann auf **Hinzufügen**. Die Vorgabe wird erstellt und auf der Registerkarte **Ausgabevorgaben** aller zugehörigen Zuordnungen angezeigt. \( ![](images/global-preset-icon.svg)\) zeigt eine Vorgabe auf Ordnerprofilebene an.
1. Geben Sie die Konfigurationsdetails ein. Weitere Informationen zu Ausgabevorgaben finden Sie unter [Grundlegendes zu Ausgabevorgaben](./generate-output-understand-presets.md).

   >[!NOTE]
   >
   > Diese dem Profilordner hinzugefügten Vorgaben sind unabhängig von den Zuordnungen, sodass die Zuordnungsspezifischen Konfigurationen für diese Vorgaben nicht vorhanden sind.

1. Sie können oben rechts **Symbol &quot;** generieren“ auswählen, um die Ausgabe für die Zuordnungen zu generieren, die sich auf die erstellte Ausgabevorgabe beziehen. Sie können den Status des Ausgabegenerierungsprozesses anzeigen. Um die Ausgabe anzuzeigen, wählen **Ausgabe anzeigen** im Dialogfeld **Erfolg** aus.

>[!NOTE]
>
> Experience Manager Guides bietet außerdem eine vordefinierte PDF-Ausgabevorgabe, um die Ausgabe für Ihre DITA-Zuordnungen zu generieren.

**Andere Vorgänge über das Menü Optionen**

Sie können die folgenden Vorgänge für die Voreinstellung auch über das Menü Optionen ausführen:

- **Ausgabe generieren**: Ermöglicht das Generieren einer Ausgabe für eine vorhandene Vorgabe.
- **Ausgabe anzeigen** und **Protokoll anzeigen**: Schnelllinks zum Anzeigen der generierten Ausgabe und der Protokolle.
- **Umbenennen**, **Duplizieren** oder **Löschen** einer vorhandenen Ausgabevorgabe aus dem Menü **Optionen**.
- **Standard-PDF**: Ermöglicht die Auswahl der bestehenden PDF-Vorgabe als Standard-PDF-Vorgabe. Die ausgewählte Vorgabe wird dann als Standardvorgabe verwendet, um die PDF-Ausgabe mit der Option **Als PDF herunterladen** für eine Zuordnung zu generieren.

>[!NOTE]
>
> Wenn eine Ausgabevorgabe in globalen Profilen und Ordnerprofilen gelöscht wird, wird sie in allen zugehörigen Zuordnungen angezeigt und nicht auf der Registerkarte **Ausgabevorgaben** angezeigt.

**Übergeordnetes Thema:**&#x200B;[ Arbeiten mit dem Web-Editor](web-editor.md)
