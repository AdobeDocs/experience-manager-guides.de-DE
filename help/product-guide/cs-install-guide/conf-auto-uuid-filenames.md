---
title: Konfigurieren automatischer Dateinamen basierend auf UUID
description: Erfahren Sie, wie Sie automatische Dateinamen basierend auf der UUID konfigurieren
exl-id: bdbdf119-b928-4ed2-bab3-d99370da8aa9
feature: Filename Configuration
role: Admin
level: Experienced
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '193'
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

**Übergeordnetes Thema:**[ Dateinamen konfigurieren](conf-file-names.md)
