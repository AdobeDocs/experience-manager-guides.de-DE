---
title: Integrieren von Desktop-basierten XML-Editoren
description: Erfahren Sie, wie Sie Desktop-basierte XML-Editoren integrieren
feature: Publishing FrameMaker Documents
role: Admin
level: Experienced
exl-id: 86ba53fa-0e08-4791-9018-09fe974691da
source-git-commit: 682eaf6f4a3a158f49a8f2ea91ce9cd2de3ff772
workflow-type: tm+mt
source-wordcount: '363'
ht-degree: 1%

---

# Integrieren von Desktop-basierten XML-Editoren

Auf dem Markt sind viele XML-Editoren verfügbar, und Sie könnten bereits einen verwenden. Adobe FrameMaker ist einer der leistungsfähigsten XML-Editoren, der mit dem AEM-Connector geliefert wird. Mithilfe des AEM-Connectors in FrameMaker können Sie sich einfach mit dem AEM-Repository verbinden, Dateien ein- und auschecken und Dateien direkt in FrameMaker bearbeiten. Sie können Experience Manager Guides auch so konfigurieren, dass FrameMaker vom Web-Editor aus gestartet wird. Sobald die Datei auf FrameMaker geöffnet ist, können Sie sie bearbeiten und wieder in das AEM-Repository einchecken.

## Aktivieren der Dateibearbeitung im FrameMaker über den Web-Editor

Sie können FrameMaker oder einen anderen DITA-Editor verwenden, um DITA-Inhalte zu erstellen und zu aktualisieren. Wenn Ihr Unternehmen jedoch FrameMaker als DITA-Editor verwendet, können Sie Ihren Benutzenden die Möglichkeit geben, DITA-Dokumente direkt in FrameMaker über AEM zu öffnen.


Standardmäßig wird den Benutzenden die Schaltfläche **In FrameMaker öffnen** in der AEM-Symbolleiste nicht angezeigt. Führen Sie die folgenden Schritte aus, um diese Schaltfläche in der AEM-Symbolleiste hinzuzufügen:

Verwenden Sie die Anweisungen unter [Konfigurationsüberschreibungen](download-install-additional-config-override.md#), um die Konfigurationsdatei zu erstellen. Geben Sie in der Konfigurationsdatei die folgenden \(Eigenschaft\)-Details an, um diese Schaltfläche auf der AEM-Symbolleiste hinzuzufügen:


| PID | Eigenschaftsschlüssel | Eigenschaftswert |
|---|------------|--------------|
| `com.adobe.fmdita.xmleditor.config.XmlEditorConfig` | `xmleditor.openinframebuttonshow` | Boolescher Wert \(true/false\). Wenn Sie die Schaltfläche **Auf FrameMaker öffnen** anzeigen möchten, legen Sie diese Eigenschaft auf „true“ fest. <br> **Standardwert**: false |



Wenn Sie Version 2409 und FrameMaker Version September 2022 - Update 3 verwenden, müssen Sie die Konfiguration **FrameMaker Version 2022 Update 3 oder höher**, damit Ihre Benutzerinnen und Benutzer die Experience Manager Guides-Serverdetails an FrameMaker weitergeben können.  Standardmäßig ist sie deaktiviert.


| PID | Eigenschaftsschlüssel | Eigenschaftswert |
|---|------------|--------------|
| `com.adobe.fmdita.xmleditor.config.XmlEditorConfig` | `xmleditor.openinframe2022above` | Boolescher Wert \(true/false\). Wenn Sie FrameMaker Version September 2022 - Update 3 verwenden, setzen Sie diese Eigenschaft auf „true“. <br> **Standardwert**: false |



Wenn Sie die Eigenschaft *openinframebuttonshow* auf „true“ setzen, wird **Schaltfläche „In FrameMaker öffnen** angezeigt, wenn Sie eine beliebige DITA-Datei im AEM-Repository auswählen. Wenn diese Eigenschaft nicht auf &quot;*&quot;* ist, wird die Schaltfläche **In FrameMaker öffnen** nur angezeigt, wenn Sie eine .fm- oder eine .book-Datei im Repository auswählen.
