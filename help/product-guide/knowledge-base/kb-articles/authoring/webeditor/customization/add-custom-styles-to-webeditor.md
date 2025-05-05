---
title: Hinzufügen benutzerdefinierter Stile zu Handbüchern im Web-Editor
description: Erfahren Sie, wie Sie benutzerdefinierte Stile hinzufügen können, um das Erscheinungsbild des Web-Editors für Handbücher zu ändern.
exl-id: 03143fb2-d05d-4103-b172-8b91880b7f9e
feature: Web Editor
role: User, Admin
source-git-commit: be06612d832785a91a3b2a89b84e0c2438ba30f2
workflow-type: tm+mt
source-wordcount: '261'
ht-degree: 0%

---

# Hinzufügen benutzerdefinierter Stile zu Handbüchern im Web-Editor

In diesem Artikel erfahren Sie, wie Sie benutzerdefinierte Stile hinzufügen können, um das standardmäßige Erscheinungsbild des Web-Editors zu ändern.

Dies umfasst die folgenden Schritte:
- Hinzufügen der benutzerdefinierten Stile über die Konfiguration des XML-Editors für Ordnerprofile
- Auswählen des entsprechenden Ordnerprofils im Web-Editor und Testen der Änderungen


## Beispielhafte Implementierung

Sehen wir uns dazu ein Beispiel an, in dem die Kurzbeschreibung und der Titel als separater Block mit einigen Stilaspekten im Editor angezeigt werden sollen.

![Vorschau des Web-Editors mit benutzerdefinierten Stilen](../../../assets/authoring/webeditor-customstyles-preview.png)


## Implementieren von


### Hinzufügen des benutzerdefinierten CSS zum Ordnerprofil

Verwenden Sie die Ordnerprofile, um *css_layout.css* auf der Registerkarte „XML-Editor-Konfiguration“ zu überprüfen und das CSS mit benutzerdefinierten Stilen hinzuzufügen

[Verwenden Sie diesen Link, um mehr über Ordnerprofile und das Konfigurieren des CSS-Vorlagenlayouts zu erfahren](https://experienceleague.adobe.com/docs/experience-manager-guides-learn/videos/advanced-user-guide/editor-configuration.html?lang=de#customize-the-css-template-layout)

Verwenden Sie Folgendes, um den oben genannten Stil in Ihrem Web-Editor einzurichten:
- Verwenden Sie [css_layout.css](../../../assets/authoring/webeditor-customstyles-css_layout.css) und laden Sie es in den Profilordner Ihrer Wahl hoch
- Installieren Sie das angehängte Paket [webeditor-styles-resources.zip](../../../assets/authoring/webeditor-styles-resources.zip) mithilfe von AEM Package Manager, um die in der obigen CSS-Datei verwendeten Ressourcen zu installieren

```
This will install the resources at path "/content/dam/resources" which will include sub-folders "fonts" and "images"
```


### Testen

- Web-Editor öffnen
- Wählen Sie in den Benutzereinstellungen den Profilordner aus, dem Sie die benutzerdefinierten Stile hinzugefügt haben. Wenn Sie es zum globalen Profil hinzugefügt haben, verwenden Sie es wahrscheinlich bereits.
- Wenn Sie ein Thema öffnen, werden Sie feststellen, dass der Bearbeitungsbereich eine benutzerdefinierte Benutzeroberfläche haben sollte

```
Please note this is compatible to AEM Guides version 4.2 and AEM Guides cloud version 2303 (March)
```


## Verweise

Vielleicht interessieren Sie sich auch für die Expertensitzung zu WebEditor-Konfigurationen und -Anpassungen, die unter [Expertensitzung auf WebEditor“ behandelt ](https://experienceleague.adobe.com/docs/experience-manager-guides-learn/tutorials/knowledge-base/expert-session/webbased-authoring-jan2023.html?lang=de)
