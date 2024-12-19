---
title: Label
description: Label
role: User, Admin
exl-id: aceefb08-3198-4c3a-90ec-ac1cdde28582
source-git-commit: e40ebf4122decc431d0abb2cdf1794ea704e5496
workflow-type: tm+mt
source-wordcount: '46'
ht-degree: 6%

---

# Label

Um einen beliebigen Text oder eine beliebige Zeichenfolge anzuzeigen, verwenden wir die Komponente Beschriftung .
Die Beschriftungskomponente in der JUI stellt eine HTML-`<label/>` dar.

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

![label](./imgs/label.png "label")
