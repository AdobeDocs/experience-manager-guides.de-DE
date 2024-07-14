---
title: Widgets
description: Widgets
role: User, Admin
exl-id: 96e960df-d595-4d58-8ad4-27057f857bac
source-git-commit: e40ebf4122decc431d0abb2cdf1794ea704e5496
workflow-type: tm+mt
source-wordcount: '87'
ht-degree: 2%

---

# Widgets

Mehrere grundlegende Komponenten, wie im Abschnitt Komponenten beschrieben, können kombiniert werden, um ein Widget zu erstellen.
Widgets können verwendet werden, um eine neue &quot;komplexere&quot;Komponente zu erstellen oder Elemente einer Komponente zu strukturieren.

Tauchen wir in das Konzept eines Widgets ein!

Zunächst erstellen wir ein einfaches Widget, um eine Liste von Sprachen anzuzeigen.

```js title="basicWidget.js"
const widgetJSON =  {
    "component": "div", 
    "id": "widget_languages", 
    "items": [ // adding components to the widget
        {
            "component": "div",
            "items": [
                {
                    "component": "icon",
                    "icon": "info"
                },
                {
                    "component": "label",
                    "label": "List of some languages"
                }
            ]
        },
        {
            "component": "list",
            "data": "@languages"
        }
    ]
},
```

Hier ist `@languages` ein Array, das im Modell von `widget_languages` definiert ist als: [&quot;English&quot;, &quot;French&quot;, &quot;Hindi&quot;, &quot;Spanisch&quot;, &quot;Urdu&quot;]

Das gerenderte grundlegende Widget sieht wie folgt aus:

![basic_widget](imgs/basic_widget.png "Basic widget")
