---
title: Öffnen von DITA-Themen oder Zuordnungsdateien in derselben Registerkarte
description: Erfahren Sie, wie Sie DITA-Themen oder -Zuordnungsdateien in derselben Registerkarte öffnen.
feature: Web Editor Configuration
role: Admin
level: Experienced
source-git-commit: 6f3f05419f4f5cdd45ab580cdee6fa869f20f01d
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

**Übergeordnetes Thema:**[ Anpassen des Web-Editors](customize-overview.md)
