---
title: Verwalten von globalen und Ordnerprofil-Ausgabevorgaben
description: Erfahren Sie, wie Sie in AEM Guides globale Ausgabevorgaben und Ordnerprofile als Admin-Benutzerinnen und -Benutzer erstellen, bearbeiten, umbenennen, duplizieren und löschen.
feature: Authoring, Features of Web Editor, Publishing
role: User
hide: true
exl-id: 4e9cd1d5-1c28-4363-917d-f58511c4f809
source-git-commit: ea597cd14469f21e197c700542b9be7c373aef14
workflow-type: tm+mt
source-wordcount: '418'
ht-degree: 0%

---

# Verwalten von globalen und Ordnerprofil-Ausgabevorgaben {#id22BLJ0D0V1U}

Die globalen Vorgaben und Ordnerprofilvorgaben sind nur für Benutzer mit Administratorrechten auf Ordnerebene verfügbar.

Als Administrator können Sie mit AEM Guides Ausgabevorgaben für die globalen Profile und Ordnerprofile erstellen und verwalten. Anschließend können Sie diese Ausgabevorgaben einfach verwenden, um eine Ausgabe für alle Zuordnungen zu generieren, die mit diesem globalen Profil oder Ordnerprofil verknüpft sind.

Führen Sie die folgenden Schritte aus, um eine Ausgabevorgabe für die globalen Profile und Ordnerprofile zu erstellen:

1. Wählen Sie die DITA-Zuordnung aus, für die Sie eine Ausgabevorgabe erstellen möchten.
1. Wählen Sie **Option** bearbeiten aus dem Menü **Optionen** der Zuordnungsdatei aus. Die Zuordnungsdatei wird zur Bearbeitung im Web-Editor geöffnet.
1. Wählen **auf der Registerkarte** Ausgabe“ das Symbol + aus, um eine Ausgabevorgabe für Ihre DITA-Zuordnung zu erstellen.

   ![](images/add-global-output-preset.png){width="350" align="left"}

1. Geben Sie die folgenden Details im Dialogfeld **Vorgabe hinzufügen** ein:
   - Typ
   - Name
   - Target \(für Knowledgebase-Voreinstellung\)
1. Aktivieren Sie **Kontrollkästchen** Zu Ordnerprofil hinzufügen“, um eine Ausgabevorgabe für das zugehörige Ordnerprofil zu erstellen, und klicken Sie dann auf **Hinzufügen**. Die Vorgabe wird erstellt und auf der Registerkarte **Ausgabe** aller zugehörigen Zuordnungen angezeigt. \( ![](images/global-preset-icon.svg)\) zeigt eine Vorgabe auf Ordnerprofilebene an.
1. Geben Sie die Konfigurationsdetails ein. Weitere Informationen zu Ausgabevorgaben finden Sie unter [Grundlegendes zu Ausgabevorgaben](./generate-output-understand-presets.md).

   >[!NOTE]
   >
   > Diese dem Profilordner hinzugefügten Vorgaben sind unabhängig von den Zuordnungen, sodass die Zuordnungsspezifischen Konfigurationen für diese Vorgaben nicht vorhanden sind.

1. Sie können oben das Symbol **Vorgabe generieren** auswählen, um die Ausgabe für die Zuordnungen zu generieren, die sich auf die erstellte Ausgabevorgabe beziehen. Sie sehen den Status des Ausgabegenerierungsprozesses. Um die Ausgabe anzuzeigen, bewegen Sie den Mauszeiger über das Thema und klicken Sie auf **Ausgabe anzeigen**.

>[!NOTE]
>
> AEM Guides bietet außerdem eine vordefinierte PDF-Ausgabevorgabe, um die Ausgabe für Ihre DITA-Zuordnungen zu generieren.

**Andere Vorgänge über das Menü Optionen**

Sie können die folgenden Vorgänge für die Voreinstellung auch über das Menü Optionen ausführen:

- Wählen Sie die Vorgabe als Standard-PDF-Vorgabe aus. Dann würde die ausgewählte Vorgabe als Standardvorgabe verwendet, um die PDF-Ausgabe mit der Option **Als PDF herunterladen** für eine Zuordnung zu generieren.
- **Bearbeiten**, **Umbenennen**, **Duplizieren** oder **Löschen** eine vorhandene Ausgabevorgabe aus dem Menü **Optionen**.

>[!NOTE]
>
> Wenn eine Ausgabevorgabe in globalen Profilen und Ordnerprofilen gelöscht wird, wird sie in allen zugehörigen Zuordnungen widergespiegelt und nicht auf der Registerkarte **Ausgabe** angezeigt.

**Übergeordnetes Thema:**&#x200B;[ Arbeiten mit dem Web-Editor](web-editor.md)
