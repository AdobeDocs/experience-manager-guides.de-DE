---
title: Fügen Sie benutzerdefinierte Schriftarten zu Ihrer DITA-PDF hinzu
description: Dank der Integration benutzerdefinierter Schriftarten können Sie die Markenidentität und die visuelle Konsistenz aller Inhalte in nativen DITA-PDF verbessern.
feature: Native PDF Output
author: Pulkit Nagpal(punagpal)
role: User, Admin
source-git-commit: 518bec870dc07e88a422d889a1c54be26c248799
workflow-type: tm+mt
source-wordcount: '222'
ht-degree: 0%

---

# Fügen Sie benutzerdefinierte Schriftarten zu Ihrer nativen DITA-PDF hinzu.

## Dieser Artikel behandelt:

Hinzufügen der benutzerdefinierten Schriftart zur Stärkung der Markenidentität und visuellen Konsistenz aller Inhalte.

Dieser Prozess umfasst drei Schritte:

- [Hochladen der benutzerdefinierten Schriftart](#step-1--upload-the-custom-font-to-the-resource-folder-of-your-template)
- [Nehmen Sie die erforderlichen Änderungen im Stylesheet der PDF-Vorlagen vor.](#step-2--make-necessary-changes-in-pdf-templatess-stylesheet)

- [Einbetten verwendeter Schriftarten (optional)](#step-3-optional--embed-used-font-in-pdf)

## Schritt 1 : Laden Sie die benutzerdefinierte Schriftart in den Ordner der Vorlage hoch.

![Hochladen und Importieren benutzerdefinierter Schriftarten ](../assets/publishing/custom-font1.png)

## 2. Schritt : Vornehmen der erforderlichen Änderungen im Stylesheet von PDF-Vorlagen

![Schriftbild im Stylesheet der PDF ](../assets/publishing/custom-font2.png)

## Schritt 3 (Optional): Einbetten der verwendeten Schriftart in PDF

![Einbetten benutzerdefinierter Schriftarten in DITA-PDF ](../assets/publishing/custom-font3.png)

## Häufig gestellte Fragen

- ### Kann ich Adobe Fonts verwenden?

> Ja, gehen Sie zu fonts.adobe.com und klicken Sie auf &quot;Zum Webprojekt hinzufügen&quot;.
> 
> Kopieren Sie den Importcode wie `" @import url("https://use.typekit.net/xxxx.css")`;
>
> Fügen Sie in das CSS Ihres Inhalts ein und nehmen Sie die gewünschten Änderungen in Ihrer CSS-Datei vor.

![Verwenden der Adobe-Schriftart in DITA-PDF](../assets/publishing/custom-font4.png)


- ### Meine Schriftart wird nicht auf dem PDF angezeigt

> Rechtschreibprüfung für Schriftnamen (der häufigste Fehler)
>
> Stellen Sie sicher, dass Sie die Schriftart einbetten, wenn Schriftarten nicht auf dem System verfügbar sind, auf dem PDF geöffnet ist.

- ## Bei allen anderen Abfragen wenden Sie sich an Ihre jeweiligen CSMs.


## Weitere Ressourcen:

- [Einbinden des Inhaltsverzeichnisses von DITA Bookmap in PDF](./how-to-include-bookmap-toc-in-pdf-publishing.md)
- [Einbinden von TOC in die PDF-Veröffentlichung](./how-to-include-bookmap-toc-in-pdf-publishing.md)
- [Video zur Expertensitzung zum nativen PDF](../../expert-sessions/native-pdf-publishing-eamples-part1-june2023.md)