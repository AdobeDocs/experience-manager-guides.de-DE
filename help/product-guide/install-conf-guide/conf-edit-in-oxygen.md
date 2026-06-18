---
title: Konfigurieren Sie die Option zur Bearbeitung in Oxygen
description: Erfahren Sie, wie Sie die Option zum Bearbeiten im Oxygen Connector-Plug-in konfigurieren.
feature: Web Editor Configuration
role: Admin
level: Experienced
exl-id: 41ecbbb2-81c3-473d-b48b-7370a74a6474
source-git-commit: cc73b81787a3c3dbe8390d93e558064327e59965
workflow-type: tm+mt
source-wordcount: '104'
ht-degree: 1%

---

# Konfigurieren Sie die Option zum Bearbeiten in Oxygen für Cloud Service

AEM Guides ermöglicht es den Benutzenden auch, ihre DITA-Themen und DITA-Karten im Oxygen Connector-Plug-in zu bearbeiten.

Verwenden Sie die Anweisungen unter [Konfigurationsüberschreibungen](download-install-config-override.md#), um die Konfigurationsdatei zu erstellen. Geben Sie in der Konfigurationsdatei die folgenden Details (Eigenschaft) zum Konfigurieren der Option **In Sauerstoff bearbeiten** an:



| PID | Eigenschaftsschlüssel | Eigenschaftswert |
|---|------------|--------------|
| `com.adobe.fmdita.xmleditor.config.XmlEditorConfig` | `xmleditor.editinoxygen` | Boolescher Wert \(true/false\). **Standardwert**: false |

>[!NOTE]
>
> Diese Konfiguration ist standardmäßig deaktiviert und die Option ist im Editor nicht verfügbar.

**Übergeordnetes Thema:**[ Editor anpassen](customize-overview.md)
