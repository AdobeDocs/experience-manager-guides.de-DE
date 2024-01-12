---
title: Symbol
description: Symbol
role: User, Admin
source-git-commit: be06612d832785a91a3b2a89b84e0c2438ba30f2
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
