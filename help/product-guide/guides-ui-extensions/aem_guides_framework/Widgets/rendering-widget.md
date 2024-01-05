---
title: Rendering-Widgets
description: Funktionsweise des Renderings in JUI Widgets
source-git-commit: f9a72e44fe1a3d90180ff728189a24ea9c7b1b1a
workflow-type: tm+mt
source-wordcount: '86'
ht-degree: 0%

---

# Rendering-Widgets

Ein Widget kann gerendert werden, indem es mithilfe seiner `id`

So rendern Sie das Widget `widget_languages` überall in der App können wir die einfache Syntax verwenden:

```json
{
    "component": "widget",
    "id": "widget_languages"
}
```

Widgets können auch zum Rendern komplexer Elemente verwendet werden, z. B. zum Rendern der Liste der Mitwirkenden für jede Datei.
Hier kann das Widget wie folgt erstellt werden:

```js title="fileContributorsWidget.js"
const widgetJSON =  {
    component: "div", 
    id: "file_contributors", 
    items: [ // adding components to the widget
        {
            component: "div",
            items: [
                {
                    component: "icon",
                    icon: "file"
                },
                {
                    component: "label",
                    label: "@fileName"
                }
            ]
        },
        {
            component: "list",
            data: "@contributors",
            itemConfig: {
                component: "label"
            }
        }
    ]
},
```

Um nun eine Liste der Beitragenden für jede Datei zu rendern, schreiben wir die Liste wie folgt:

```js title="fileContributorsList.js"
const listJSON = {
    component: "list"
    data: "@files"
    itemConfig: {
        component: "widget",
        id: "file_contributors"
    }
}
```

Hier `@files` ist eine Liste von Dateiobjekten mit Feldern

```typescript
- fileName: string
- contributors: Array<String>
```
