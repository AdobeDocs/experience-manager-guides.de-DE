---
title: Rendern von Widgets
description: Funktionsweise des Renderings in JUI-Widgets
role: User, Admin
exl-id: 381cc7b9-c957-40be-9db4-8347eefe2fa7
source-git-commit: e40ebf4122decc431d0abb2cdf1794ea704e5496
workflow-type: tm+mt
source-wordcount: '86'
ht-degree: 0%

---

# Rendern von Widgets

Wir können ein Widget rendern, indem wir es mithilfe seiner `id` referenzieren

Um das Widget an einer beliebigen Stelle in der App `widget_languages` zu rendern, können wir die einfache Syntax verwenden:

```json
{
    "component": "widget",
    "id": "widget_languages"
}
```

Widgets können auch verwendet werden, um komplexe Elemente zu rendern, z. B. um die Liste der Mitwirkenden für jede Datei zu rendern.
Hier kann das Widget wie folgt aufgebaut werden:

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

Um nun für jede Datei eine Liste der Mitwirkenden zu rendern, schreiben wir die Liste wie folgt:

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

Im Folgenden finden `@files` eine Liste von Dateiobjekten mit Feldern

```typescript
- fileName: string
- contributors: Array<String>
```
