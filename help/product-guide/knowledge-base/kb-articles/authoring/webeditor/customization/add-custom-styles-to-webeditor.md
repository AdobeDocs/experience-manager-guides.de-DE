---
title: Hinzufügen benutzerdefinierter Stile zum Guides-Editor
description: Erfahren Sie, wie Sie benutzerdefinierte Stile hinzufügen, um das Erscheinungsbild des Guides-Editors zu ändern.
exl-id: 03143fb2-d05d-4103-b172-8b91880b7f9e
feature: Web Editor
role: User, Admin
source-git-commit: be06612d832785a91a3b2a89b84e0c2438ba30f2
workflow-type: tm+mt
source-wordcount: '261'
ht-degree: 0%

---

# Hinzufügen benutzerdefinierter Stile zum Guides-Editor

In diesem Artikel erfahren Sie, wie Sie benutzerdefinierte Stile hinzufügen können, um das Erscheinungsbild und die Standardeinstellung für den Webserver zu ändern.

Dies umfasst die folgenden Schritte:
- Hinzufügen benutzerdefinierter Stile über die Konfiguration des XML-Editors für Ordnerprofile
- Auswählen des entsprechenden Ordnerprofils im WebEditor und Testen der Änderungen


## Implementieren anhand eines Beispiels

Sehen wir uns dazu ein Beispiel an, in dem wir die kurze Beschreibung und den Titel als separaten Block mit einigen Stilaspekten im Editor anzeigen möchten.

![Anzeigen einer Vorschau des Webeditors mit benutzerdefinierten Stilen](../../../assets/authoring/webeditor-customstyles-preview.png)


## Implementieren


### Hinzufügen der benutzerdefinierten CSS zum Ordnerprofil

Verwenden Sie die Ordnerprofile, um die *css_layout.css* auf der Registerkarte &quot;XML-Editor-Konfiguration&quot;zu überprüfen und das CSS mit benutzerdefinierten Stilen hinzuzufügen.

[Verwenden Sie diesen Link, um mehr über das Ordnerprofil und das Konfigurieren des CSS-Vorlagenlayouts zu erfahren](https://experienceleague.adobe.com/docs/experience-manager-guides-learn/videos/advanced-user-guide/editor-configuration.html?lang=en#customize-the-css-template-layout)

Verwenden Sie Folgendes, um den obigen Stil in Ihrem Webserver einzurichten:
- Verwenden Sie [css_layout.css](../../../assets/authoring/webeditor-customstyles-css_layout.css) und laden Sie es in das Ordnerprofil Ihrer Wahl hoch
- Installieren Sie das angehängte Paket [webeditor-styles-resources.zip](../../../assets/authoring/webeditor-styles-resources.zip) mit AEM Paketmanager, um die in der obigen CSS-Datei verwendeten Ressourcen zu installieren.

```
This will install the resources at path "/content/dam/resources" which will include sub-folders "fonts" and "images"
```


### Testen

- Öffnen Sie den Web-Editor
- Wählen Sie in den Benutzereinstellungen das Ordnerprofil aus, in dem Sie die benutzerdefinierten Stile hinzugefügt haben. Wenn Sie es zum globalen Profil hinzugefügt haben, verwenden Sie es wahrscheinlich bereits.
- Öffnen Sie ein Thema. Sie werden feststellen, dass der Bearbeitungsbereich über eine benutzerdefinierte Benutzeroberfläche verfügen sollte.

```
Please note this is compatible to AEM Guides version 4.2 and AEM Guides cloud version 2303 (March)
```


## Verweise

Möglicherweise interessieren Sie sich auch für die Expertensitzung rund um die Konfiguration und Anpassung von Webservern, die in der [Expertensitzung zum Webserver](https://experienceleague.adobe.com/docs/experience-manager-guides-learn/tutorials/knowledge-base/expert-session/webbased-authoring-jan2023.html?lang=en) behandelt wird.
