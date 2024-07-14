---
title: Konfigurieren der Bearbeitungsoption in Sauerstoff
description: Erfahren Sie, wie Sie die Option zur Bearbeitung im Oxygen Connector-Plug-in konfigurieren.
exl-id: 96081a6d-39cf-4697-8b43-6494543ea187
feature: Web Editor Configuration
role: Admin
level: Experienced
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '104'
ht-degree: 1%

---

# Konfigurieren der Bearbeitungsoption in Sauerstoff

AEM Guides ermöglicht es Benutzern auch, ihre DITA-Themen und DITA-Maps im Oxygen-Connector-Plugin zu bearbeiten.

Verwenden Sie die Anweisungen unter [Konfigurationsüberschreibungen](download-install-additional-config-override.md#) , um die Konfigurationsdatei zu erstellen. Geben Sie in der Konfigurationsdatei die folgenden (Eigenschaftsdetails) an, um die Option **In Sauerstoff bearbeiten** zu konfigurieren:



| PID | Eigenschaftenschlüssel | Eigenschaftswert |
|---|------------|--------------|
| `com.adobe.fmdita.xmleditor.config.XmlEditorConfig` | `xmleditor.editinoxygen` | Boolesch \(true/false\). **Standardwert**: false |

>[!NOTE]
>
> Diese Konfiguration ist standardmäßig deaktiviert und die Option ist im Web-Editor nicht verfügbar.

**Übergeordnetes Thema:**[ Web-Editor anpassen](conf-web-editor.md)
