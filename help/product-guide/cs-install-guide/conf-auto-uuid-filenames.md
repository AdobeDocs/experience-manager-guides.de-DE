---
title: Konfigurieren automatischer Dateinamen basierend auf UUID
description: Erfahren Sie, wie Sie automatische Dateinamen basierend auf der UUID konfigurieren
exl-id: bdbdf119-b928-4ed2-bab3-d99370da8aa9
feature: Filename Configuration
role: Admin
level: Experienced
TQID: 'https://experienceleague.adobe.com/HxTJaPGbwH31vitQ-Cu6wPyCuzZSWDXtq6xMY4hXEAI'
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
    internal-label: Experience Manager Guides
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
    internal-label: Experience Manager
feature_v2:
  - id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
    internal-label: Configuration
subfeature_v2:
  - id: ccd46b93-df7f-4458-ba4c-90a3562d9ab0
    internal-label: Filename configuration
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
level_v2:
  - id: d378ca77-2da1-4f39-ad92-1917fe974a38
    internal-label: Experienced
source-git-commit: 81a0e7f0736ba4970673dd87a888a4c60d3c1b4e
workflow-type: tm+mt
source-wordcount: '197'
ht-degree: 1%
---
# Konfigurieren automatischer Dateinamen basierend auf UUID {#id205QG070D5Z}

Wenn ein Thema oder eine Zuordnungsdatei erstellt wird, haben Autoren standardmäßig die Möglichkeit, auch den Dateinamen anzugeben. Autoren können die Dateinamen gemäß ihren Anforderungen zuweisen. Dies kann jedoch zu Inkonsistenzen führen, und in einem großen Dokumentationssystem kann ein breites Spektrum von Dateinamen angezeigt werden. Als Admin können Sie Ihre Autoren daran hindern, den Dateien, die sie in Ihrem System erstellen, Dateinamen zuzuweisen. Für jede neue Themen- oder Zuordnungsdatei können Sie UUID-basierte Dateinamen automatisch zuweisen.

Verwenden Sie die Anweisungen unter [Konfigurationsüberschreibungen](download-install-additional-config-override.md#), um die Konfigurationsdatei zu erstellen. Geben Sie in der Konfigurationsdatei die folgenden \(property\)-Details an, um automatische Dateinamen basierend auf der UUID zu konfigurieren:

| PID | Eigenschaftsschlüssel | Eigenschaftswert |
|---|------------|--------------|
| `com.adobe.fmdita.xmleditor.config.XmlEditorConfig` | `xmleditor.uniquefilenames` | Boolescher Wert \(true/false\).<br> **Standardwert**: false |

>[!NOTE]
>
> Wenn diese Option aktiviert ist, wird den Autoren beim Erstellen eines neuen Themas oder einer Zuordnungsdatei die Option zum Angeben des Dateinamens nicht angezeigt. Über die Assets-Benutzeroberfläche und den Web-Editor kann eine neue Themen- oder Zuordnungsdatei erstellt werden.

**Übergeordnetes Thema:**&#x200B;[&#x200B; Dateinamen konfigurieren](conf-file-names.md)
