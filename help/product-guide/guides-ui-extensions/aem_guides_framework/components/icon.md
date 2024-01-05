---
title: Symbol
description: Symbol
source-git-commit: 2e1cb576fa3b0a765304508e5f7962a154f1a72c
workflow-type: tm+mt
source-wordcount: '49'
ht-degree: 6%

---

# Symbol

Um ein Symbol anzuzeigen, verwenden wir die Komponente, das Symbol .
Die Textbereichskomponente in JUI stellt einen HTML-Code dar `<icon/>`.

Die unter verfügbaren Symbole [Adobe Spectrum-Symbole](https://spectrum.adobe.com/page/icons/) sind mit unserer App kompatibel.

```js title="icon.js"
const iconJSON =  {
    "component": "icon", //tells the component name
    "icon": "info", // name of the icon to be used
    "size": "S", // size of the icon
    "title": "Information" // tooltip corresponding to the icon.
},
```

Schaltflächen können auch Symbole hinzugefügt werden.

Das gerenderte Symbol sieht wie folgt aus:

![icon](./imgs/info_icon.png "Symbol")
