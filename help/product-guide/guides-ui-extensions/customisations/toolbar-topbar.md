---
title: Symbolleiste und Symbolleiste
description: Symbolleiste und Symbolleiste anpassen
role: User, Admin
source-git-commit: be06612d832785a91a3b2a89b84e0c2438ba30f2
workflow-type: tm+mt
source-wordcount: '56'
ht-degree: 0%

---


# Symbolleiste und Symbolleiste anpassen

So passen Sie die `topbar` und `toolbar`verwenden wir die IDs: `topbar` oder `toolbar`und folgen Sie derselben Ansicht, der Controller-Struktur.

Nachfolgend finden Sie ein triviales Beispiel für die Anpassung der Symbolleiste. Hier haben wir die `Insert Numbered List` und ersetzt die `Insert Paragraph` -Schaltfläche mit unserer eigenen Komponente unter Verwendung eines benutzerdefinierten On-Click-Handlers.

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
