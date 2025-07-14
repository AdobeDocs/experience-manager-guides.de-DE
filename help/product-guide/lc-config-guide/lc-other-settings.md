---
title: Konfigurieren anderer Einstellungen
description: Erfahren Sie, wie Sie Ordner, Asset-Ordner, Variablen, Snippets, Bedingungen und mehr für verschiedene Abteilungen in Experience Manager Guides konfigurieren.
feature: Authoring
role: Admin
level: Experienced
source-git-commit: 5f42540a32da6e85a5c8aa0831582ce871c9088a
workflow-type: tm+mt
source-wordcount: '360'
ht-degree: 0%

---

# Konfigurieren anderer Einstellungen

Als Administrator können Sie auch die folgenden Einstellungen für die Autoren und Herausgeber der Lernkurse konfigurieren:

- **Ordnereinstellungen**
   - **Erstellen verschiedener Ordner**: Sie können Ordner für Autoren und Herausgeber erstellen, die in verschiedenen Abteilungen oder Produkten in Ihrem Unternehmen arbeiten. Diese Ordner können bestimmten Ordnerprofilen zugeordnet werden, die jeweils mit unterschiedlichen Authoring- und Ausgabevorlagen konfiguriert sind, um abteilungsspezifische Lernkurserstellung und dezentrale Verwaltung zu unterstützen.

     Sie können einen neuen Ordner über das Repository-Bedienfeld erstellen.

     ![](assets/create-new-folder.png){width="350" align="left"}
   - **Erstellen von Sprachordnern**: Wenn Sie Inhalte in verschiedene Sprachen übersetzen, müssen Sie Ordner für jede Sprache erstellen. Jeder dieser Sprachordner enthält den Inhalt, der dieser Sprache entspricht.

     Weitere Informationen finden Sie unter [Best Practices für die Übersetzung von Inhalten](../user-guide/translation-first-time.md).
   - **Assets-Verwaltung**: Ähnlich wie bei Ordnern können Sie auch verschiedene Assets-Ordner erstellen, um die Anforderungen verschiedener Abteilungen zu erfüllen. Auf diese Weise stellen Sie auch sicher, dass Autoren und Herausgeber Zugriff auf das richtige CSS haben, das in ihren Vorlagen, Bildern und anderen Assets konfiguriert ist.

     ![](assets/configure-assets-folder.png){width="350" align="left"}
- **Snippets**: Sie können Snippets auf Ordnerebene konfigurieren, um sicherzustellen, dass Autoren Zugriff auf die richtigen Snippets haben. Nur Administratoren können Snippets in Experience Manager Guides erstellen, die dann von Autoren im Editor verwendet werden können.

  Sie können auf Snippets über das linke Bedienfeld im Editor zugreifen.

  ![](assets/create-snippets.png){width="350" align="left"}
- **Bedingungen**: Als Administrator können Sie standardmäßige DITA-unterstützte bedingte Attribute auf globaler Ebene oder Ordnerebene konfigurieren. Autoren verwenden dann konfigurierte Bedingungen, indem sie die gewünschte Bedingung einfach per Drag-and-Drop auf ihren Inhalt ziehen.

  Sie können auf Bedingungen über das linke Bedienfeld im Editor zugreifen.

  ![](assets/create-conditions.png){width="350" align="left"}
- **Variablen**: Sie können Variablen definieren, um Ihre Inhalte portabler, konsistenter und einfacher zu aktualisieren. Während der Ausgabegenerierung werden Variablen durch die Werte aus dem ausgewählten Variablensatz ersetzt, sodass Sie benutzerdefinierte Ausgaben effizient erstellen können.

  Weitere Informationen finden Sie unter [Neue Variable erstellen](../native-pdf/native-pdf-variables.md#create-a-new-variable)

- **Editor-Symbolleiste**: Sie können die Editor-Symbolleiste gemäß den Anforderungen Ihres Unternehmens anpassen. Sie können beispielsweise den Namen einer Symbolleistenschaltfläche, ihre Position usw. ändern.

  Weitere Informationen finden Sie unter [Konfigurieren und Anpassen des XML-Editors](../cs-install-guide/conf-folder-level.md#configure-and-customize-the-xml-editor-id2065g300o5z).
