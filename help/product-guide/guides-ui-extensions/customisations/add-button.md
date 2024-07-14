---
title: Einfache Anpassung
description: Einfaches Anpassungsbeispiel
role: User, Admin
exl-id: 7f19f0b0-2a1b-4a8b-b28c-3918a1bc9096
source-git-commit: e40ebf4122decc431d0abb2cdf1794ea704e5496
workflow-type: tm+mt
source-wordcount: '289'
ht-degree: 0%

---

# Einfaches Anpassungsbeispiel

Lassen Sie uns nun wissen, wie diese Anpassungen in unsere AEM Guides-App integriert werden können.

Angenommen, wir möchten diese Schaltfläche in einer vorhandenen Ansicht der App hinzufügen.
Dazu müssen wir drei grundlegende Dinge tun:

1. Die `id` der JSON-Ansicht, der wir unsere Komponente hinzufügen möchten.
2. Der `target`, d. h. der Speicherort im JSON, zu dem die neue Komponente hinzugefügt werden soll. Die `target` wird mit einem `key` und einem `value` definiert. Das Schlüssel-Wert-Paar kann ein beliebiges Attribut sein, das zur Definition der Komponente verwendet wird und bei der eindeutigen Identifizierung der Komponente helfen kann.
Wir können auch Indizes verwenden, um auf das Ziel zu verweisen.
Wir haben 3 Ansichtszustände: `APPEND`, `PREPEND`, `REPLACE`.
3. JSON der neu erstellten Komponente und entsprechende Methoden.

Angenommen, wir möchten der im Review verwendeten Anmerkungs-Toolbox eine Schaltfläche hinzufügen, mit der die Datei in AEM geöffnet wird.

```typescript
export default {
  id: 'annotation_toolbox', 
  view: {
    items: [
      {
        component: 'button',
        icon: 'linkOut',
        title: 'Open topic in Assets view',
        'on-click': 'openTopicInAEM',
        target: {
          key: 'value',
          value: 'addcomment',
          viewState: VIEW_STATE.APPEND

        },
      },
    ],
  },
  controller: {
    openTopicInAEM: function (args) {
        const topicIndex = tcx.model.getValue(tcx.model.KEYS.REVIEW_CURR_TOPIC)
        const {allTopics = {}} = tcx.model.getValue(tcx.model.KEYS.REVIEW_DATA) || {}
        tcx.appGet('util').openInAEM(allTopics[topicIndex])
    },
  },
}
```

Im obigen Beispiel haben wir Folgendes:

1. den `id` der JSON, in die wir unsere Komponente einfügen möchten, d. h. `annotation_toolbox`
2. das Ziel die Schaltfläche `addcomment` ist. Wir fügen unsere Schaltfläche über die viewState `append` nach der Schaltfläche `addcomment` hinzu.
3. Wir definieren das On-Click-Ereignis der Schaltfläche im Controller.

JSON für die &quot;annotation_toolbox&quot; `.src/jsons/review_app/annotation_toolbox.json`

Vor der Anpassung sah die Anmerkungs-Toolbox wie folgt aus:

![annotation-toolbox](imgs/annotation_toolbox.png "Anmerkungs-Toolbox")

Nach der Anpassung sieht das Anmerkungs-Tool wie folgt aus:

![customized-annotation-toolbox](imgs/customised_annotation_toolbox.png "Benutzerdefinierte Anmerkungs-Toolbox")

## CSS hinzufügen

Für die Konsistenz stellen wir die Komponente bereit, die bereits formatiert ist. Der eingefügte JSON-Code weist inhärente Stile auf
Die primäre Methode zur Verwaltung von CSS besteht darin, den extraClass -Schlüssel in den Erweiterungen zu verwenden.

```js
{    
    "view":{
        items:[
            {
                compoenent:"button",
                extraClass:"underline bg-red",
            }
        ]
    }
}
```

Sie können benutzerdefinierte Stile mit CSS-Klassen einfügen, indem Sie clientlibs eine CSS-Datei hinzufügen. Während des Builds erstellen wir auch die Ausgabe [Tailwind](https://tailwindcss.com/docs/utility-first) für die Dienstprogrammklassen in Rückenwind. Die Konfiguration für dasselbe finden Sie unter `tailwind.config.js` der Erweiterung unter `./tailwind.config.js`
