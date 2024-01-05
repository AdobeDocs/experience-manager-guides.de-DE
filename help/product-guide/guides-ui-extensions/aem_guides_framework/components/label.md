---
title: Bezeichnung
description: Bezeichnung
source-git-commit: 2e1cb576fa3b0a765304508e5f7962a154f1a72c
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