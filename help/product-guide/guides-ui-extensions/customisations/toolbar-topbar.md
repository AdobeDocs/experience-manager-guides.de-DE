---
title: Symbolleiste und Symbolleiste
description: Anpassen von Symbolleiste und Symbolleiste
role: User, Admin
exl-id: 7065c9b8-67ac-4f6d-8124-daa547f2dc3b
source-git-commit: 4f41609368b64415993b93be27162b069e7b2e32
workflow-type: tm+mt
source-wordcount: '75'
ht-degree: 0%

---

# Anpassen von Symbolleiste und Symbolleiste

Um die `topbar` und `toolbar` anzupassen, verwenden wir die IDs: `topbar` oder `toolbar` und folgen derselben Ansicht, Controller-Struktur.

Nachfolgend finden Sie ein triviales Beispiel für die Anpassung von Symbolleisten. Hier haben wir die Schaltfläche `Insert Numbered List` entfernt und die Schaltfläche `Insert Paragraph` durch unsere eigene Komponente ersetzt, indem ein benutzerdefinierter On-Click-Handler verwendet wurde.

Um auf Funktionen zugreifen zu können, die unter `proxy` Objekt verfügbar gemacht werden, müssen wir darauf zugreifen, indem wir z. B. `this.proxy.getValue` einen Wert abrufen.

```js title = toolbar_customisation.js
const toolbarExtend = {
    id: "toolbar",
    view: {
        items: [
            {
                component: "div",
                target: {
                    key:"title",value: "Insert Numbered List",                    
                    viewState: VIEW_STATE.REPLACE
                }
            },
            {
                {
                    "component": "button",
                    "icon": "textParagraph",
                    "variant": "action",
                    "quiet": true,
                    "title": "Insert Paragraph",
                    "on-click": "INSERT_P"
                },

                target: {
                    key:"title",value: "Insert Paragraph",                    
                    viewState: VIEW_STATE.REPLACE
                }
            },
        ]
    },
    controller: {
        init: function() {
            console.log(this.proxy.getValue("canUndo"))
            this.proxy.subscribeAppEvent({
              key: "editor.preview_rendered",
              next: async function (e) {
                console.log(this.proxy.getValue("canUndo"))
              }.bind(this)
            })
        },
        INSERT_P(){
            this.next("AUTHOR_INSERT_ELEMENT",  "p" )
        }
    }
}
```
