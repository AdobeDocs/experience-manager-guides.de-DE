---
title: Bezeichnung
description: Bezeichnung
role: User, Admin
source-git-commit: be06612d832785a91a3b2a89b84e0c2438ba30f2
workflow-type: tm+mt
source-wordcount: '46'
ht-degree: 6%

---

# Bezeichnung

Um Text oder Zeichenfolge anzuzeigen, verwenden wir die Komponente, Bezeichnung.
Die Beschriftungskomponente in JUI steht für einen HTML-Code `<label/>`.

Nachfolgend finden Sie ein Beispiel für das Hinzufügen einer statischen Beschriftung

```js title="staticLabel.js"
const staticLabelJSON =  {
    "component": "label", //tells the component name
    "label": "This is an example label", // the string to be displayed
}
```

Unter JSON wird eine dynamische Zeichenfolge angezeigt:

```js title="dynamicLabel.js"
const labelJSON =  {
    "component": "label", //tells the component name
    "label": "@name", // the variable storing the text to be displayed
},
```

Die gerenderte Bezeichnung sieht wie folgt aus:

![label](./imgs/label.png "Titel")