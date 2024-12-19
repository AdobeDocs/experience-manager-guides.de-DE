---
title: Widgets
description: Grundlegendes zu Widgets
role: User, Admin
exl-id: 96e960df-d595-4d58-8ad4-27057f857bac
source-git-commit: e40ebf4122decc431d0abb2cdf1794ea704e5496
workflow-type: tm+mt
source-wordcount: '87'
ht-degree: 2%

---

# Widgets

Mehrere grundlegende Komponenten, wie im Abschnitt Komponenten beschrieben, können kombiniert werden, um ein Widget zu erstellen.
Widgets können verwendet werden, um eine neue „komplexere“ Komponente zu erstellen oder Elementen einer Komponente eine Struktur zu verleihen.

Lassen Sie uns in das Konzept eines Widgets eintauchen!

Wir beginnen mit einem einfachen Widget, um eine Liste von Sprachen anzuzeigen.

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

`@languages` ist hier ein Array, das im Modell der `widget_languages` wie folgt definiert ist: [„Englisch“, „Französisch“, „Hindi“, „Spanisch“, „Urdu“]

Das gerenderte grundlegende Widget sieht wie folgt aus:

![basic_widget](imgs/basic_widget.png "basic widget")
