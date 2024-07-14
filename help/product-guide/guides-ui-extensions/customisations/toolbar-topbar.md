---
title: Symbolleiste und Symbolleiste
description: Symbolleiste und Symbolleiste anpassen
role: User, Admin
exl-id: 7065c9b8-67ac-4f6d-8124-daa547f2dc3b
source-git-commit: e40ebf4122decc431d0abb2cdf1794ea704e5496
workflow-type: tm+mt
source-wordcount: '56'
ht-degree: 0%

---

# Symbolleiste und Symbolleiste anpassen

Um die `topbar` und `toolbar` anzupassen, verwenden wir die IDs: `topbar` oder `toolbar` und folgen derselben Ansicht, der Controller-Struktur.

Nachfolgend finden Sie ein triviales Beispiel für die Anpassung der Symbolleiste. In unserem Beispiel haben wir die Schaltfläche `Insert Numbered List` entfernt und die Schaltfläche `Insert Paragraph` mit unserer eigenen Komponente durch einen benutzerdefinierten Klick-Handler ersetzt.

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

        INSERT_P(){
            this.next("AUTHOR_INSERT_ELEMENT",  "p" )
        }
    }
}
```
