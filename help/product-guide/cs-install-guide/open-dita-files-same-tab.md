---
title: DITA-Themen- oder Zuordnungsdateien auf derselben Registerkarte öffnen
description: Erfahren Sie, wie Sie DITA-Themen oder -Zuordnungsdateien auf derselben Registerkarte öffnen
exl-id: 466cbea4-c75a-488e-bde2-465cf2c184d5
feature: Web Editor Configuration
role: Admin
level: Experienced
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '208'
ht-degree: 0%

---

# DITA-Themen- oder Zuordnungsdateien auf derselben Registerkarte öffnen {#id223HH0301J3}

Wenn Sie in einigen Workflows auf einen Link eines Themas oder einer Zuordnungsdatei klicken, wird dieser in einer neuen Registerkarte geöffnet. Dies kann dazu führen, dass in Ihrem Browser viele Tabs geöffnet werden, was sich auf Ihre Produktivität auswirken könnte. Sie können dieses Verhalten beim Öffnen einer Themen- oder Zuordnungsdatei in einer neuen Registerkarte ändern und das Öffnen auf der aktuellen Registerkarte erzwingen.

Verwenden Sie die Anweisungen unter [Konfigurationsüberschreibungen](download-install-additional-config-override.md#) , um die Konfigurationsdatei zu erstellen. Geben Sie in der Konfigurationsdatei die folgenden \(Eigenschaft\)-Details ein, um ein Thema oder eine Zuordnungsdatei in einer neuen Registerkarte zu öffnen:

| PID | Eigenschaftenschlüssel | Eigenschaftswert |
|---|------------|--------------|
| `com.adobe.fmdita.xmleditor.config.XmlEditorConfig` | `xmleditor.openinsametab` | Boolesch \(true/false\). <br> **Standardwert**: `false` |

Diese Einstellung wirkt sich auf die folgenden Stellen aus, an denen Sie auf die Themen- oder Zuordnungsdateien zugreifen können:

- DITA-Thema erstellen \(am Ende des Workflows, wenn Sie auf das **Thema öffnen** button\)

- DITA-Map erstellen \(am Ende des Workflows, wenn Sie auf die **Open Map** button\)

- Registerkarte &quot;Themen&quot;in der DITA-Map-Konsole

- Registerkarte &quot;Grundlinien&quot;in der DITA-Map-Konsole

- Registerkarte &quot;Berichte&quot;in der DITA-Map-Konsole


**Übergeordnetes Thema:**[ Anpassen des Web-Editors](conf-web-editor.md)
