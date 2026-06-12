---
title: Verwalten von globalen und Ordnerprofil-Ausgabevorgaben
description: Erfahren Sie, wie Sie in AEM Guides globale Ausgabevorgaben und Ordnerprofile als Admin-Benutzerinnen und -Benutzer erstellen, bearbeiten, umbenennen, duplizieren und löschen.
exl-id: 549c9fe2-77f8-423c-8b3e-b43e56055732
feature: Authoring, Features of Web Editor, Publishing
role: User
TQID: https://experienceleague.adobe.com/FCtMWJZh9bc9sayuHsMWnd-c6mZ0Uvi0ZAgv2lOSu-4
product_v2: id: fae5e35a-80c9-4b94-9352-1a060a6aab1did: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2: id: a3bd6397-2eb2-4908-a61c-226e26855dcaid: ab01a588-7dea-43f2-a699-0b3f128465d6id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
subfeature_v2: id: ad602516-aca3-4247-9ae8-f393d958efa9id: b1ef4d86-3917-4b76-a0bc-4a4771f9b3b0id: f89f75b0-cf2e-4e96-aec8-fe8c39cbd0efid: f9dbea21-a714-40dd-bc90-080d8046c93fid: fd6cc9e1-e5e5-494e-b7b1-a32f2d6cd7c9
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 478
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

   ![](images/add-global-output-preset.png){width="350"}

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

**Übergeordnetes Thema:**[ Arbeiten mit dem Web-Editor](web-editor.md)
