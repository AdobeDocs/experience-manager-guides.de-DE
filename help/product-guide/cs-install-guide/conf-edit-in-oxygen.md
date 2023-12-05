---
title: Konfigurieren der Bearbeitungsoption in Sauerstoff
description: Erfahren Sie, wie Sie die Option zur Bearbeitung im Oxygen Connector-Plug-in konfigurieren.
exl-id: 96081a6d-39cf-4697-8b43-6494543ea187
source-git-commit: 5e0584f1bf0216b8b00f00b9fe46fa682c244e08
workflow-type: tm+mt
source-wordcount: '104'
ht-degree: 1%

---

# Konfigurieren der Bearbeitungsoption in Sauerstoff

AEM Guides ermöglichen es den Benutzern auch, ihre DITA-Themen und DITA-Maps im Oxygen-Connector-Plugin zu bearbeiten.

Verwenden Sie die Anweisungen unter [Konfigurationsüberschreibungen](download-install-additional-config-override.md#) , um die Konfigurationsdatei zu erstellen. Geben Sie in der Konfigurationsdatei die folgenden (Eigenschaft-)Details an, um die **In Sauerstoff bearbeiten** Option:



| PID | Eigenschaftenschlüssel | Eigenschaftswert |
|---|------------|--------------|
| `com.adobe.fmdita.xmleditor.config.XmlEditorConfig` | `xmleditor.editinoxygen` | Boolesch \(true/false\). **Standardwert**: false |

>[!NOTE]
>
> Diese Konfiguration ist standardmäßig deaktiviert und die Option ist im Web-Editor nicht verfügbar.

**Übergeordnetes Thema:**[ Anpassen des Web-Editors](conf-web-editor.md)
