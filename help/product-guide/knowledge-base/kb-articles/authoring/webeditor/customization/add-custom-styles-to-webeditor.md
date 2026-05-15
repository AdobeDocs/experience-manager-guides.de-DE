---
title: Hinzufügen benutzerdefinierter Stile zu Handbüchern im Web-Editor
description: Erfahren Sie, wie Sie benutzerdefinierte Stile hinzufügen können, um das Erscheinungsbild des Web-Editors für Handbücher zu ändern.
exl-id: 03143fb2-d05d-4103-b172-8b91880b7f9e
feature: Web Editor
role: User, Admin
TQID: https://experienceleague.adobe.com/uQc8TTz7dHxbN6-zbin-esQevLoJR-IMR1hchrwEs8M
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2:
  - id: ab01a588-7dea-43f2-a699-0b3f128465d6
  - id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
subfeature_v2:
  - id: ad602516-aca3-4247-9ae8-f393d958efa9
  - id: b1ef4d86-3917-4b76-a0bc-4a4771f9b3b0
  - id: f89f75b0-cf2e-4e96-aec8-fe8c39cbd0ef
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 300
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

[Verwenden Sie diesen Link, um mehr über Ordnerprofile und das Konfigurieren des CSS-Vorlagenlayouts zu erfahren](https://experienceleague.adobe.com/docs/experience-manager-guides-learn/videos/advanced-user-guide/editor-configuration.html?lang=en#customize-the-css-template-layout)

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

Vielleicht interessieren Sie sich auch für die Expertensitzung zu WebEditor-Konfigurationen und -Anpassungen, die unter [Expertensitzung auf WebEditor“ behandelt &#x200B;](https://experienceleague.adobe.com/docs/experience-manager-guides-learn/tutorials/knowledge-base/expert-session/webbased-authoring-jan2023.html?lang=en)
