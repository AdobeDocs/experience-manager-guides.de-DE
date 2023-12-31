---
title: Widgets
description: Widgets
source-git-commit: f9a72e44fe1a3d90180ff728189a24ea9c7b1b1a
workflow-type: tm+mt
source-wordcount: '87'
ht-degree: 0%

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

Hier, `@languages` ist ein Array, das im Modell von `widget_languages` as: [&quot;English&quot;, &quot;French&quot;, &quot;Hindi&quot;, &quot;Spanish&quot;, &quot;Urdu&quot;]

Das gerenderte grundlegende Widget sieht wie folgt aus:

![basic_widget](imgs/basic_widget.png "Grundlegendes Widget")
