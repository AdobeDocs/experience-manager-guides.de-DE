---
title: Liste
description: Liste
role: User, Admin
source-git-commit: be06612d832785a91a3b2a89b84e0c2438ba30f2
workflow-type: tm+mt
source-wordcount: '59'
ht-degree: 5%

---

# Liste

Um eine Liste anzuzeigen, verwenden wir die Komponentenliste.

```js title="list.js"
const listJSON =  {
    "component": "list", //tells the component name
    "data": "@languages", // an array of list items
},
```

Hier ist Sprache ein einfaches Array von Zeichenfolgen. `languages = ["English", "Hindi", "French"]`
Wenn wir eine Liste von Objekten rendern möchten, können wir die Struktur mithilfe der Elementkonfiguration angeben.

```js title="list.js"
const listJSON =  {
    "component": "list", //tells the component name
    "data": "@projects", // an array of list items
    "itemConfig": { // used to define the structure of the list items.
    "component": "widget",
    "id": "checkbox_label"
    }
},
```

Normalerweise ist itemConfig ein `widget`. Weitere Informationen zu Widgets finden Sie unter [Widgets](../Widgets/basic-widget.md)

Die gerenderte Liste sieht wie folgt aus:

![Liste](./imgs/list.png "Liste")
