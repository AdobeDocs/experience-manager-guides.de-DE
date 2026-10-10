---
title: Öffnen von DITA-Themen oder Zuordnungsdateien in derselben Registerkarte
description: Erfahren Sie, wie Sie DITA-Themen oder -Zuordnungsdateien in derselben Registerkarte öffnen.
feature: Web Editor Configuration
role: Admin
level: Experienced
exl-id: 13f7eab1-2235-4537-9520-69d1df04e921
product_v2:
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
    internal-label: Experience Manager
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
    internal-label: Experience Manager Guides
feature_v2:
  - id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
    internal-label: Configuration
subfeature_v2:
  - id: b0521e56-a0b2-40b6-bf47-ebc98751f9ba
    internal-label: Web Editor configuration
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
level_v2:
  - id: d378ca77-2da1-4f39-ad92-1917fe974a38
    internal-label: Experienced
source-git-commit: 81a0e7f0736ba4970673dd87a888a4c60d3c1b4e
workflow-type: tm+mt
source-wordcount: '276'
ht-degree: 1%
---
# Öffnen von DITA-Themen oder Zuordnungsdateien in derselben Registerkarte {#id223HI0P202H}

Wenn Sie in einigen Workflows auf einen Link eines Themas oder einer Zuordnungsdatei klicken, wird diese auf einer neuen Registerkarte geöffnet. Dies kann dazu führen, dass in Ihrem Browser viele Registerkarten geöffnet werden, was sich auf Ihre Produktivität auswirken kann. Sie können dieses Verhalten ändern, wenn Sie ein Thema oder eine Zuordnungsdatei in einer neuen Registerkarte öffnen und das Öffnen in der aktuellen Registerkarte erzwingen.

Die folgenden Registerkarten enthalten Anweisungen zum Öffnen der DITA-Topic- oder -Zuordnungsdatei auf derselben Registerkarte, je nach Experience Manager Guides-Einrichtung: Cloud Service oder On-Premise.

>[!BEGINTABS]

>[!TAB Cloud Service]

Verwenden Sie die Anweisungen unter [Konfigurationsüberschreibungen](download-install-config-override.md#), um die Konfigurationsdatei zu erstellen. Geben Sie in der Konfigurationsdatei die folgenden \(Eigenschaft\)-Details ein, um eine Themen- oder Zuordnungsdatei in einer neuen Registerkarte zu öffnen:

| PID | Eigenschaftsschlüssel | Eigenschaftswert |
|---|------------|--------------|
| `com.adobe.fmdita.xmleditor.config.XmlEditorConfig` | `xmleditor.openinsametab` | Boolescher Wert \(true/false\). <br> **Standardwert**: `false` |

>[!TAB On-Premise]

1. Öffnen Sie die Seite Konfiguration der Adobe Experience Manager-Web-Konsole .

   Die Standard-URL für den Zugriff auf die Konfigurationsseite lautet:

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Suchen Sie nach dem Bundle **com.adobe.fmdita.xmeditor.config.XmlEditorConfig** und klicken Sie darauf.

1. Wählen Sie die **DITA-Thema/-Zuordnung auf derselben Registerkarte öffnen** aus.

1. Klicken Sie auf **Speichern**.

>[!ENDTABS]

Diese Einstellung wirkt sich auf die folgenden Orte aus, von denen aus Sie auf das Thema oder die Zuordnungsdateien zugreifen können:

- DITA-Thema erstellen \(am Ende des Workflows, wenn Sie auf die Schaltfläche **Thema öffnen** klicken)

- DITA-Map erstellen \(Klicken Sie am Ende des Workflows auf die Schaltfläche **Zuordnung öffnen**\)

- Registerkarte „Themen“ in der DITA-Zuordnungskonsole

- Registerkarte „Baselines“ in der DITA-Zuordnungskonsole

- Registerkarte „Berichte“ in der DITA-Zuordnungskonsole

**Übergeordnetes Thema:**[ Editor anpassen](customize-overview.md)
