---
title: Öffnen von DITA-Themen oder Zuordnungsdateien in derselben Registerkarte
description: Erfahren Sie, wie Sie DITA-Themen oder -Zuordnungsdateien in derselben Registerkarte öffnen.
exl-id: 466cbea4-c75a-488e-bde2-465cf2c184d5
feature: Web Editor Configuration
role: Admin
level: Experienced
TQID: https://experienceleague.adobe.com/futODy2B62sg-Epb4bnmxHVAOUVoGDoKg5WJWV-7bpM
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2:
  - id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
  - id: d90290ec-3e61-4ebd-8649-bcafe0836803
subfeature_v2:
  - id: b0521e56-a0b2-40b6-bf47-ebc98751f9ba
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 207
ht-degree: 0%

---

# Öffnen von DITA-Themen oder Zuordnungsdateien in derselben Registerkarte {#id223HH0301J3}

Wenn Sie in einigen Workflows auf einen Link eines Themas oder einer Zuordnungsdatei klicken, wird diese auf einer neuen Registerkarte geöffnet. Dies kann dazu führen, dass in Ihrem Browser viele Registerkarten geöffnet werden, was sich auf Ihre Produktivität auswirken kann. Sie können dieses Verhalten ändern, wenn Sie ein Thema oder eine Zuordnungsdatei in einer neuen Registerkarte öffnen und das Öffnen in der aktuellen Registerkarte erzwingen.

Verwenden Sie die Anweisungen unter [Konfigurationsüberschreibungen](download-install-additional-config-override.md#), um die Konfigurationsdatei zu erstellen. Geben Sie in der Konfigurationsdatei die folgenden \(Eigenschaft\)-Details ein, um eine Themen- oder Zuordnungsdatei in einer neuen Registerkarte zu öffnen:

| PID | Eigenschaftsschlüssel | Eigenschaftswert |
|---|------------|--------------|
| `com.adobe.fmdita.xmleditor.config.XmlEditorConfig` | `xmleditor.openinsametab` | Boolescher Wert \(true/false\). <br> **Standardwert**: `false` |

Diese Einstellung wirkt sich auf die folgenden Orte aus, von denen aus Sie auf das Thema oder die Zuordnungsdateien zugreifen können:

- DITA-Thema erstellen \(am Ende des Workflows, wenn Sie auf die Schaltfläche **Thema öffnen** klicken)

- DITA-Map erstellen \(Klicken Sie am Ende des Workflows auf die Schaltfläche **Zuordnung öffnen**\)

- Registerkarte „Themen“ in der DITA-Zuordnungskonsole

- Registerkarte „Baselines“ in der DITA-Zuordnungskonsole

- Registerkarte „Berichte“ in der DITA-Zuordnungskonsole


**Übergeordnetes Thema:**&#x200B;[&#x200B; Anpassen des Web-Editors](conf-web-editor.md)
