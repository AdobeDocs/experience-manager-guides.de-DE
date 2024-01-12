---
title: Textbereich
description: Textbereich
role: User, Admin
source-git-commit: be06612d832785a91a3b2a89b84e0c2438ba30f2
workflow-type: tm+mt
source-wordcount: '64'
ht-degree: 3%

---

# Textfeld und Textbereich

Um Text als Eingabe zu verwenden, verwenden wir die Komponenten, das Textfeld und den Textbereich.
Die Textbereichskomponente in JUI stellt einen HTML-Code dar `<textarea/>`.

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

Hier, `on-keyup` ist die Syntax zum Aufrufen der Befehle in den Controllern.
Dadurch wird ein textArea erzeugt, in dem durch Drücken der EINGABETASTE das Ereignis aufgerufen wird `submitName`

Der gerenderte Textbereich sieht wie folgt aus:

![Textbereich](./imgs/text_area.png "Textbereich")
