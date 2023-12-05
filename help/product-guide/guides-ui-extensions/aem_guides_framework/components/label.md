---
sidebar_position: 2
source-git-commit: 5e0584f1bf0216b8b00f00b9fe46fa682c244e08
workflow-type: tm+mt
source-wordcount: '44'
ht-degree: 2%

---


# Beschriftung

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