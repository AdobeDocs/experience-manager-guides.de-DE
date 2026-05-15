---
title: Integrieren von Desktop-basierten XML-Editoren
description: Erfahren Sie, wie Sie Desktop-basierte XML-Editoren integrieren
feature: Publishing FrameMaker Documents
role: Admin
level: Experienced
exl-id: 86ba53fa-0e08-4791-9018-09fe974691da
TQID: https://experienceleague.adobe.com/4cejVcInzwcFBWgxobUvn7g2teizpQCCeTC2Z5CZ1K8
product_v2: id: fae5e35a-80c9-4b94-9352-1a060a6aab1did: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2: id: a3bd6397-2eb2-4908-a61c-226e26855dcaid: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
subfeature_v2: id: bf79f6d3-0ad0-4d82-99e4-42ce98324d60
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 368
ht-degree: 1%

---

# Integrieren von Desktop-basierten XML-Editoren

Auf dem Markt sind viele XML-Editoren verfügbar, und Sie könnten bereits einen verwenden. Adobe FrameMaker ist einer der leistungsfähigsten XML-Editoren, der mit dem AEM-Connector geliefert wird. Mit dem AEM-Connector in FrameMaker können Sie einfach eine Verbindung zum AEM-Repository herstellen, Dateien ein- und auschecken und Dateien direkt in FrameMaker bearbeiten. Sie können Experience Manager Guides auch so konfigurieren, dass FrameMaker über den Web-Editor gestartet wird. Sobald die Datei in FrameMaker geöffnet ist, können Sie sie bearbeiten und wieder in das AEM-Repository einchecken.

## Aktivieren der Dateibearbeitung in FrameMaker über den Web-Editor

Sie können FrameMaker oder einen anderen DITA-Editor verwenden, um DITA-Inhalte zu erstellen und zu aktualisieren. Wenn Ihr Unternehmen jedoch FrameMaker als DITA-Editor verwendet, können Sie Ihren Benutzenden die Möglichkeit geben, DITA-Dokumente direkt in FrameMaker von AEM aus zu öffnen.


Standardmäßig wird den Benutzenden die Schaltfläche **In FrameMaker öffnen** in der AEM-Symbolleiste nicht angezeigt. Führen Sie die folgenden Schritte aus, um diese Schaltfläche in der AEM-Symbolleiste hinzuzufügen:

Verwenden Sie die Anweisungen unter [Konfigurationsüberschreibungen](download-install-additional-config-override.md#), um die Konfigurationsdatei zu erstellen. Geben Sie in der Konfigurationsdatei die folgenden \(Eigenschaft\)-Details an, um diese Schaltfläche auf der AEM-Symbolleiste hinzuzufügen:


| PID | Eigenschaftsschlüssel | Eigenschaftswert |
|---|------------|--------------|
| `com.adobe.fmdita.xmleditor.config.XmlEditorConfig` | `xmleditor.openinframebuttonshow` | Boolescher Wert \(true/false\). Wenn Sie die Schaltfläche **In FrameMaker öffnen** anzeigen möchten, legen Sie diese Eigenschaft auf „true“ fest. <br> **Standardwert**: false |



Wenn Sie Version 2409 und FrameMaker Version September 2022 - Update 3 verwenden, müssen Sie die Konfiguration **FrameMaker Version 2022 Update 3 oder höher**, damit Ihre Benutzerinnen und Benutzer die Experience Manager Guides-Serverdetails an FrameMaker weitergeben können.  Standardmäßig ist sie deaktiviert.


| PID | Eigenschaftsschlüssel | Eigenschaftswert |
|---|------------|--------------|
| `com.adobe.fmdita.xmleditor.config.XmlEditorConfig` | `xmleditor.openinframe2022above` | Boolescher Wert \(true/false\). Wenn Sie FrameMaker Version September 2022 - Update 3 verwenden, setzen Sie diese Eigenschaft auf „true“. <br> **Standardwert**: false |



Wenn Sie die Eigenschaft *openinframebuttonshow* auf „true“ setzen, wird **Schaltfläche „In FrameMaker öffnen** angezeigt, wenn Sie eine DITA-Datei im AEM-Repository auswählen. Wenn diese Eigenschaft nicht auf &quot;*&quot; festgelegt*, wird die Schaltfläche **In FrameMaker öffnen** nur angezeigt, wenn Sie eine .fm- oder eine .book-Datei im Repository auswählen.
