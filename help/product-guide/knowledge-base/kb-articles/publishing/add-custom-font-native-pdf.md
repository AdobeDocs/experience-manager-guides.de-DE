---
title: Hinzufügen benutzerdefinierter Schriftarten zu DITA PDF
description: Durch die Integration benutzerdefinierter Schriftarten können Sie die Markenidentität und visuelle Konsistenz Ihrer gesamten Inhalte in nativen DITA-PDFs verbessern.
feature: Native PDF Output
author: Pulkit Nagpal(punagpal)
role: User, Admin
exl-id: 151e3b1c-6340-4ff2-84d4-246bc4b68065
TQID: https://experienceleague.adobe.com/xqr9eYA2XTcyXL8X4aS-Wu2-FmU8-aCWDpb-L2BBFqI
product_v2: id: fae5e35a-80c9-4b94-9352-1a060a6aab1did: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2: id: a3bd6397-2eb2-4908-a61c-226e26855dca
subfeature_v2: id: d6596f3f-92a7-43ec-b444-237db6adad05
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 223
ht-degree: 0%

---

# Hinzufügen benutzerdefinierter Schriftarten zu Ihrer nativen DITA-PDF

## Dieser Artikel behandelt:

Hinzufügen der benutzerdefinierten Schriftart, um die Markenidentität und visuelle Konsistenz aller Inhalte zu verbessern.

Dieser Prozess umfasst drei Schritte:

- [Benutzerdefinierte Schriftart hochladen](#step-1--upload-the-custom-font-to-the-resource-folder-of-your-template)
- [Notwendige Änderungen im Stylesheet der PDF-Vorlagen vornehmen](#step-2--make-necessary-changes-in-pdf-templatess-stylesheet)

- [Einbetten verwendeter Schriftarten (optional)](#step-3-optional--embed-used-font-in-pdf)

## Schritt 1 : Laden Sie die benutzerdefinierte Schriftart in den Ressourcenordner Ihrer Vorlage hoch

![](../assets/publishing/custom-font1.png) zum Hochladen und Importieren benutzerdefinierter Schriftarten

## Schritt 2 : Erforderliche Änderungen im Stylesheet der PDF-Vorlagen vornehmen

![Schriftart in der Stylesheet-](../assets/publishing/custom-font2.png) der PDF-Vorlage

## Schritt 3 (Optional) : Betten Sie die verwendete Schriftart in PDF ein

![Einbetten benutzerdefinierter Schriftarten in DITA PDF ](../assets/publishing/custom-font3.png)

## Häufig gestellte Fragen

### Kann ich Adobe Fonts verwenden?

> Ja, gehen Sie zu fonts.adobe.com und klicken Sie auf „Zum Web-Projekt hinzufügen“.
> 
> Kopieren Sie Importcode wie `" @import url("https://use.typekit.net/xxxx.css")`.
>
> Fügen Sie Ihren CSS-Inhalt ein und nehmen Sie die gewünschten Änderungen in Ihrer CSS-Datei vor.

![Verwenden der Adobe-Schriftart in DITA PDF](../assets/publishing/custom-font4.png)


### Meine Schriftart wird in PDF nicht angezeigt

> Überprüfen Sie die Schreibweise des Schriftnamens (häufigster Fehler).
>
> Stellen Sie sicher, dass Sie Schriftarten einbetten, wenn auf dem System, auf dem PDF geöffnet ist, keine Schriftarten verfügbar sind.

## Für alle anderen Fragen wenden Sie sich bitte an Ihren jeweiligen CSM


## Weitere Ressourcen:

- [Einbinden des Inhaltsverzeichnisses von DITA Bookmap in PDF](./how-to-include-bookmap-toc-in-pdf-publishing.md)
- [Einschließen des Inhaltsverzeichnisses in PDF Publishing](./how-to-include-bookmap-toc-in-pdf-publishing.md)
- [Expertenvideo zu nativen PDF](../../expert-sessions/native-pdf-publishing-eamples-part1-june2023.md)
