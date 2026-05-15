---
title: Einfache Anpassung
description: Einfaches Anpassungsbeispiel
role: User, Admin
exl-id: 7f19f0b0-2a1b-4a8b-b28c-3918a1bc9096
TQID: https://experienceleague.adobe.com/IFKRQlzewz3NcnX-xruXzInQMiEzwEmhe-4knxXPrJM
product_v2: id: fae5e35a-80c9-4b94-9352-1a060a6aab1did: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 296
ht-degree: 0%

---

# Einfaches Anpassungsbeispiel

Wir zeigen Ihnen nun, wie Sie diese Anpassungen in unsere AEM Guides-App integrieren können.

Angenommen, wir möchten diese Schaltfläche in einer vorhandenen Ansicht der App hinzufügen.
Dazu müssen wir drei grundlegende Dinge tun:

1. Die `id` der JSON-Ansicht, der wir unsere Komponente hinzufügen möchten.
2. Die `target`, d. h. der Speicherort in der JSON, der die neue Komponente hinzugefügt werden soll. Die `target` wird mithilfe eines `key` und `value` definiert. Das Schlüssel-Wert-Paar kann ein beliebiges Attribut sein, mit dem die Komponente definiert wird, die bei der eindeutigen Identifizierung helfen kann.
Wir können auch Indizes verwenden, um auf das Ziel zu verweisen.
Wir haben 3 ViewStates: `APPEND`, `PREPEND`, `REPLACE`.
3. Die JSON der neu erstellten Komponente und die entsprechenden Methoden.

Angenommen, wir möchten der in der Überprüfung verwendeten Anmerkungs-Toolbox eine Schaltfläche hinzufügen, mit der die Datei in AEM geöffnet wird.

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

1. die `id` der JSON-Datei, in die wir unsere Komponente einfügen möchten, d. h. `annotation_toolbox`
2. Das Ziel ist die Schaltfläche `addcomment` . Wir fügen unsere Schaltfläche nach der Schaltfläche `addcomment` mithilfe der `append` viewState hinzu.
3. Wir definieren das On-Click-Ereignis der Schaltfläche im Controller.

Die JSON-Datei für die `.src/jsons/review_app/annotation_toolbox.json` „annotation_toolbox“

Vor der Anpassung sah die Anmerkungs-Toolbox wie folgt aus:

![annotation-toolbox](imgs/annotation_toolbox.png "annotation toolbox")

Nach der Anpassung sieht die Anmerkungs-Toolbox wie folgt aus:

![customized-annotation-toolbox](imgs/customised_annotation_toolbox.png "customized-annotation toolbox")

## CSS hinzufügen

Aus Konsistenzgründen stellen wir die bereits formatierte Komponente bereit. Auf die eingefügte JSON werden inhärente Stile angewendet
Die primäre Möglichkeit, CSS zu verwalten, besteht in der Verwendung des extraClass-Schlüssels in den Erweiterungen.

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

Sie können benutzerdefinierte Stile mit CSS-Klassen einfügen, indem Sie eine CSS-Datei zu Clientlibs hinzufügen. Während des Builds erstellen wir auch [Tailwind](https://tailwindcss.com/docs/utility-first)-Ausgabe für die Dienstprogrammklassen in Tailwind. Die entsprechende Konfiguration kann auf der `tailwind.config.js` der Erweiterung unter `./tailwind.config.js` gefunden werden
