---
title: Automatische Dateinamen basierend auf UUID konfigurieren
description: Erfahren Sie, wie Sie automatische Dateinamen basierend auf der UUID konfigurieren.
exl-id: bdbdf119-b928-4ed2-bab3-d99370da8aa9
feature: Filename Configuration
role: Admin
level: Experienced
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '193'
ht-degree: 1%

---

# Automatische Dateinamen basierend auf UUID konfigurieren {#id205QG070D5Z}

Standardmäßig erhalten Autoren bei der Erstellung einer Themen- oder Zuordnungsdatei die Möglichkeit, auch den Dateinamen anzugeben. Autoren können die Dateinamen gemäß ihren Anforderungen zuweisen. Dies kann jedoch zu Inkonsistenz führen und eine große Bandbreite an Dateinamen kann in einem großen Dokumentationssystem angezeigt werden. Als Administrator können Sie Ihre Autoren daran hindern, Dateinamen für die Dateien zuzuweisen, die sie in Ihrem System erstellen. Für jede neue Themen- oder Zuordnungsdatei können Sie automatisch UUID-basierte Dateinamen zuweisen.

Verwenden Sie die Anweisungen unter [Konfigurationsüberschreibungen](download-install-additional-config-override.md#) , um die Konfigurationsdatei zu erstellen. Geben Sie in der Konfigurationsdatei die folgenden \(Eigenschaft\)-Details an, um automatische Dateinamen basierend auf der UUID zu konfigurieren:

| PID | Eigenschaftenschlüssel | Eigenschaftswert |
|---|------------|--------------|
| `com.adobe.fmdita.xmleditor.config.XmlEditorConfig` | `xmleditor.uniquefilenames` | Boolesch \(true/false\).<br> **Standardwert**: false |

>[!NOTE]
>
> Wenn diese Option aktiviert ist, sehen Autoren beim Erstellen eines neuen Themas oder einer neuen Zuordnungsdatei nicht die Option, den Dateinamen anzugeben. Eine neue Themen- oder Zuordnungsdatei kann über die Assets-Benutzeroberfläche und den Web-Editor erstellt werden.

**Übergeordnetes Thema:**[ Dateinamen konfigurieren](conf-file-names.md)
