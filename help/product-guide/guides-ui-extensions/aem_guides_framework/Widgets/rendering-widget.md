---
title: Rendern von Widgets
description: Funktionsweise des Renderings in JUI-Widgets
role: User, Admin
exl-id: 381cc7b9-c957-40be-9db4-8347eefe2fa7
TQID: https://experienceleague.adobe.com/-VznRFHuyxLqumy55MssEvPMMHIIt2BelCe7C6zBqR8
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 86
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
