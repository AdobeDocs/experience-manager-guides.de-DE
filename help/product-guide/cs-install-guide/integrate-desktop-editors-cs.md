---
title: Integrieren von Desktop-basierten XML-Editoren
description: Erfahren Sie, wie Sie Desktop-basierte XML-Editoren integrieren.
feature: Publishing FrameMaker Documents
role: Admin
level: Experienced
source-git-commit: b3ae1c02d3055fe15257d5de0365d30e7af21afb
workflow-type: tm+mt
source-wordcount: '363'
ht-degree: 1%

---

# Integrieren von Desktop-basierten XML-Editoren

Es gibt viele XML-Editoren, die auf dem Markt verfügbar sind, und Sie könnten bereits einen verwenden. Adobe FrameMaker ist einer der leistungsfähigsten XML-Editoren, die mit AEM Connector geliefert werden. Über den AEM-Connector in FrameMaker können Sie einfach eine Verbindung zum AEM-Repository herstellen, Dateien auschecken und einchecken und Dateien direkt in FrameMaker bearbeiten. Sie können Experience Manager Guides auch so konfigurieren, dass FrameMaker über den Web-Editor gestartet wird. Nachdem Sie die Datei in FrameMaker geöffnet haben, können Sie sie bearbeiten und wieder in das AEM Repository einchecken.

## Aktivieren Sie die Dateibearbeitung im FrameMaker über den Web Editor

Sie können FrameMaker oder einen anderen DITA-Editor verwenden, um DITA-Inhalte zu erstellen und zu aktualisieren. Wenn Ihr Unternehmen jedoch FrameMaker als DITA-Editor verwendet, können Sie Ihren Benutzern die Möglichkeit geben, DITA-Dokumente direkt unter FrameMaker von AEM aus zu öffnen.


Standardmäßig wird Ihren Benutzern die Schaltfläche **In FrameMaker öffnen** in der AEM-Symbolleiste nicht angezeigt. Führen Sie die folgenden Schritte aus, um diese Schaltfläche in der AEM-Symbolleiste hinzuzufügen:

Verwenden Sie die Anweisungen unter [Konfigurationsüberschreibungen](download-install-additional-config-override.md#) , um die Konfigurationsdatei zu erstellen. Geben Sie in der Konfigurationsdatei die folgenden \(Eigenschaft\)-Details ein, um diese Schaltfläche in der AEM-Symbolleiste hinzuzufügen:


| PID | Eigenschaftenschlüssel | Eigenschaftswert |
|---|------------|--------------|
| `com.adobe.fmdita.xmleditor.config.XmlEditorConfig` | `xmleditor.openinframebuttonshow` | Boolesch \(true/false\). Wenn Sie die Schaltfläche **In FrameMaker öffnen** anzeigen möchten, legen Sie diese Eigenschaft auf &quot;true&quot;fest. <br> **Standardwert**: false |



Wenn Sie Version 2409 und FrameMaker Version 2022 vom September - Update 3 verwenden, müssen Sie die Konfiguration **FrameMaker Version 2022 Update 3 oder höher** aktivieren, damit Ihre Benutzer die Experience Manager Guides-Serverdetails an FrameMaker weitergeben können.  Standardmäßig ist sie deaktiviert.


| PID | Eigenschaftenschlüssel | Eigenschaftswert |
|---|------------|--------------|
| `com.adobe.fmdita.xmleditor.config.XmlEditorConfig` | `xmleditor.openinframe2022above` | Boolesch \(true/false\). Wenn Sie FrameMaker Version vom September 2022 - Update 3 verwenden, legen Sie diese Eigenschaft auf &quot;true&quot;fest. <br> **Standardwert**: false |



Wenn Sie die Eigenschaft *openframebuttonshow* auf &quot;true&quot;setzen, wird bei der Auswahl einer beliebigen DITA-Datei im AEM-Repository die Schaltfläche **In FrameMaker öffnen** angezeigt. Wenn diese Eigenschaft nicht auf *true* festgelegt ist, wird die Schaltfläche **In FrameMaker öffnen** nur angezeigt, wenn Sie eine FM- oder eine .book-Datei im Repository auswählen.



