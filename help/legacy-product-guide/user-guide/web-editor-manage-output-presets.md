---
title: Ausgabevorgaben für Global- und Ordnerprofile verwalten
description: Erfahren Sie, wie Sie in AEM Guides Ausgabevorgaben für globale Profile und Ordnerprofile erstellen, bearbeiten, umbenennen, duplizieren und löschen.
exl-id: 549c9fe2-77f8-423c-8b3e-b43e56055732
feature: Authoring, Features of Web Editor, Publishing
role: User
source-git-commit: 7db3df07fd17eecae1c502554118ca12f95fb5ab
workflow-type: tm+mt
source-wordcount: '418'
ht-degree: 0%

---

# Ausgabevorgaben für Global- und Ordnerprofile verwalten {#id22BLJ0D0V1U}

Die Vorgaben &quot;Global&quot;und &quot;Ordnerprofil&quot;stehen nur Administratoren auf Ordnerebene zur Verfügung.

Als Administrator können Sie mit AEM Guides Ausgabevorgaben für die globalen und Ordnerprofile erstellen und verwalten. Dann können Sie diese Ausgabevorgaben einfach verwenden, um Ausgaben für alle Maps zu generieren, die mit diesem globalen oder Ordnerprofil verbunden sind.

Führen Sie die folgenden Schritte aus, um eine Ausgabevorgabe für die Profile Global und Ordner zu erstellen:

1. Wählen Sie die DITA-Zuordnung aus, für die Sie eine Ausgabevorgabe erstellen möchten.
1. Wählen Sie die Option **Themen bearbeiten** aus dem Menü **Optionen** der Zuordnungsdatei aus. Die Zuordnungsdatei wird zur Bearbeitung im Web-Editor geöffnet.
1. Wählen Sie auf der Registerkarte **Ausgabe** das Symbol + aus, um eine Ausgabevorgabe für Ihre DITA-Zuordnung zu erstellen.

   ![](images/add-global-output-preset.png){width="350" align="left"}

1. Geben Sie die folgenden Details im Dialogfeld **Vorgabe hinzufügen** ein:
   - Typ
   - Name
   - Ziel \(für die Knowledgebase-Vorgabe\)
1. Aktivieren Sie das Kontrollkästchen **Zum Ordnerprofil hinzufügen** , um eine Ausgabevorgabe für das zugehörige Ordnerprofil zu erstellen, und klicken Sie dann auf **Hinzufügen**. Die Vorgabe wird erstellt und auf der Registerkarte **Ausgabe** aller zugehörigen Maps angezeigt. Das Symbol \( ![](images/global-preset-icon.svg)\) gibt eine Vorgabe auf Ordnerprofilebene an.
1. Geben Sie die Konfigurationsdetails ein. Weitere Informationen zu Ausgabevorgaben finden Sie unter [Grundlegendes zu den Ausgabevorgaben](./generate-output-understand-presets.md).

   >[!NOTE]
   >
   > Diese Vorgaben, die zum Ordnerprofil hinzugefügt werden, sind unabhängig von den Karten, sodass die zuordnungsspezifischen Konfigurationen für diese Vorgaben nicht vorhanden sind.

1. Sie können oben das Symbol **Vorgabe generieren** auswählen, um die Ausgabe für die mit der erstellten Ausgabevorgabe verknüpften Zuordnungen zu generieren. Sie sehen den Status des Generierungsprozesses der Ausgabe. Um die Ausgabe anzuzeigen, bewegen Sie den Mauszeiger über das Thema und klicken Sie auf **Ausgabe anzeigen**.

>[!NOTE]
>
> AEM Guides bietet außerdem eine vordefinierte PDF-Ausgabevorgabe zum Generieren der Ausgabe für Ihre DITA-Maps.

**Andere Vorgänge aus dem Menü &quot;Optionen&quot;**

Sie können auch die folgenden Vorgänge für die Vorgabe im Menü Optionen ausführen:

- Wählen Sie die Vorgabe als Standard-PDF-Vorgabe aus. Anschließend wird die ausgewählte Vorgabe als Standardvorgabe verwendet, um die PDF-Ausgabe mithilfe der Option **Als PDF herunterladen** für eine Zuordnung zu generieren.
- **Bearbeiten**, **Umbenennen**, **Duplizieren** oder **Löschen** einer vorhandenen Ausgabevorgabe aus dem Menü **Optionen**.

>[!NOTE]
>
> Wenn eine Ausgabevorgabe in den globalen und Ordnerprofilen gelöscht wird, wird sie in allen zugehörigen Maps angezeigt und nicht auf der Registerkarte **Ausgabe**.

**Übergeordnetes Thema:**[ Arbeiten mit dem Web-Editor](web-editor.md)
