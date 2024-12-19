---
title: Textbereich
description: Textbereich
role: User, Admin
exl-id: 4c576acc-fa6a-4c41-9b92-443ba51dc8ee
source-git-commit: 08d379acc98dac425f1c84b0ac2226b0e34f6d8b
workflow-type: tm+mt
source-wordcount: '64'
ht-degree: 3%

---

# Textfeld und Textbereich

Um Text als Eingabe zu verwenden, verwenden wir die Komponenten, das Textfeld und den Textbereich.
Die Textbereichskomponente in der Benutzeroberfläche stellt eine HTML-`<textarea/>` dar.

```js title="textArea.js"
const textAreaJSON =  {
    "component": "textarea", //tells the component name
    "id": "input_name", // can be used to give a unique identifier to a component
    "data": "@name", // the variable storing the inputted text
    "on-keyup": {
        "name": "submitName",
        "eventArgs": {
            "keys": [
            "ENTER"
            ]
        }
    },
},
```

Hier `on-keyup` die Syntax zum Aufrufen der Befehle in den Controllern.
Dadurch wird ein textArea erzeugt, in dem durch Drücken der EINGABETASTE die `submitName` aufgerufen wird.

Der gerenderte Textbereich sieht wie folgt aus:

![text-area](./imgs/text_area.png "text area")
