---
title: Konfigurieren Sie die Option zur Bearbeitung in Oxygen
description: Erfahren Sie, wie Sie die Option zum Bearbeiten im Oxygen Connector-Plug-in konfigurieren.
exl-id: 96081a6d-39cf-4697-8b43-6494543ea187
feature: Web Editor Configuration
role: Admin
level: Experienced
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '104'
ht-degree: 1%

---

# Konfigurieren Sie die Option zur Bearbeitung in Oxygen

AEM Guides ermöglicht es den Benutzenden auch, ihre DITA-Themen und DITA-Karten im Oxygen Connector-Plug-in zu bearbeiten.

Verwenden Sie die Anweisungen unter [Konfigurationsüberschreibungen](download-install-additional-config-override.md#), um die Konfigurationsdatei zu erstellen. Geben Sie in der Konfigurationsdatei die folgenden Details (Eigenschaft) zum Konfigurieren der Option **In Sauerstoff bearbeiten** an:



| PID | Eigenschaftsschlüssel | Eigenschaftswert |
|---|------------|--------------|
| `com.adobe.fmdita.xmleditor.config.XmlEditorConfig` | `xmleditor.editinoxygen` | Boolescher Wert \(true/false\). **Standardwert**: false |

>[!NOTE]
>
> Diese Konfiguration ist standardmäßig deaktiviert und die Option ist im Web-Editor nicht verfügbar.

**Übergeordnetes Thema:**&#x200B;[&#x200B; Anpassen des Web-Editors](conf-web-editor.md)
