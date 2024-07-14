---
title: Symbol
description: Symbol
role: User, Admin
exl-id: 5ba41c77-7329-49fc-bce5-02682261ea8e
source-git-commit: e40ebf4122decc431d0abb2cdf1794ea704e5496
workflow-type: tm+mt
source-wordcount: '49'
ht-degree: 6%

---

# Symbol

Um ein Symbol anzuzeigen, verwenden wir die Komponente, das Symbol .
Die Textbereichskomponente in JUI stellt einen HTML-Code `<icon/>` dar.

Die unter [Adobe Spectrum Icons](https://spectrum.adobe.com/page/icons/) verfügbaren Symbole sind mit unserer App kompatibel.

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

![icon](./imgs/info_icon.png "icon")
