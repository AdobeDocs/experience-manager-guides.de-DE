---
title: Benutzerdefiniertes Dialogfeld
description: Hinzufügen eines benutzerdefinierten Dialogfelds
role: User, Admin
source-git-commit: 4f41609368b64415993b93be27162b069e7b2e32
workflow-type: tm+mt
source-wordcount: '124'
ht-degree: 0%

---


# Hinzufügen eines benutzerdefinierten Dialogfelds

Gehen Sie wie folgt vor, um einen Einblick in das Hinzufügen eines benutzerdefinierten Dialogfelds in der Überprüfungs-App zu erhalten:

## Nutzungsbeispiel

```typescript
const acceptWithModification = {
  id: 'accept_with_modification_dialog',
  view: {
    component: "dialog",
    "header": {
      "items": [
        {
          component: 'label',
          extraclass: "header",
          label: 'Accept With Modifications',
        }
      ]
    },
    content: {
      items: [
        {
          component: 'div',
          "extraclass": "revised-text",
          items: [
            {
              component: 'label',
              label: 'Revised Text (Required)',
              extraclass: 'revised-text-label'
            },
            {
              component: "textarea",
              "extraclass": "revised-text-textarea",
              "data": "@extraProps.revisedText",
              "stopKeyPropagation": true,
            }
          ]
        },
        {
          component: 'div',
          "extraclass": "adjudication-rationale",
          items: [
            {
              component: 'label',
              label: 'Adjudicator Comment Rationale (Required)',
              extraclass: 'adjudication-rationale-label'
            },
            {
              component: "textarea",
              extraclass: "adjudication-rationale-textarea",
              "data": "@extraProps.adjudicationRationale",
              "on-keyup": {
                "name": "",
                "eventArgs": {
                  "keys": [
                    "ENTER"
                  ]
                }
              },
              "stopKeyPropagation": true
            }
          ]
        },
      ],
    },
    footer: {
      "items": [
        {
          "component": "button",
          "label": "Cancel",
          "on-click": "handleClose",
          "variant": "secondary"
        },
        {
          "component": "button",
          "label": "Submit",
          "variant": "cta",
          "on-click": "submitAcceptWithModification"
        }
      ]
    }
  },
  model: {
    deps: [],
  },
  controller:{

    submitAcceptWithModification: function () {
      const extraProps = {
        'revisedText': this.getValue("revisedText"),
        'adjudicationRationale': this.getValue("adjudicationRationale"),
      }
      this.args.onSuccess(extraProps)
      this.next('handleClose')
    },

    handleClose() {
      tcx.eventHandler.next(tcx.eventHandler.KEYS.APP_HIDE_DIALOG, { id: 'accept_with_modification_dialog' })
    }
  }
}
```


## Benutzerdefiniertes Dialogfeld aufrufen

In diesem Beispiel werden die Informationen zum Hinzufügen einer Schaltfläche zum Öffnen eines benutzerdefinierten Dialogfelds gekürzt.
Betrachten wir hierfür das Bedienfeld &quot;`review_comment`&quot;. Die vollständige Erweiterung finden Sie hier:
[Kommentar überprüfen](../../examples/review_app_examples/review_comment.ts)

```typescript
const reviewComment = {
  id: 'review_comment',
  view: {
    items: [
      ...
      {
        component: "button",
        "icon": "MultipleAdd",
        "variant": "action",
        "quiet": true,
        "extraclass": "hover-item",
        "title": "Accept with Modifications",
        "on-click": "acceptWithModification",
        target: {
          key: 'title',
          value: 'Reject comment',
          viewState: VIEW_STATE.APPEND,
        },
      }
    ],
  },

  controller: {
    ...

    sendAcceptWithModificationProps(args) {
      this.next('updateExtraProps', args)
    },

    acceptWithModification() {
      tcx.eventHandler.next(tcx.eventHandler.KEYS.APP_SHOW_DIALOG, 
        {
          id: 'accept_with_modification_dialog',
          args: {
            onSuccess: (extraProps) => this.next('sendAcceptWithModificationProps', extraProps),
          }
        })
    }

    ...
  }
}
```

## Übergeben von Argumenten an ein benutzerdefiniertes Dialogfeld

Hier können Sie sehen, dass wir `args` mit der Dialog-ID übergeben und einen onSuccess übergeben, um einen Callback im Erfolgsereignis zu verarbeiten.
Wir können auch `onCancel` übergeben, wenn wir beim Klicken auf Abbrechen einige benutzerdefinierte Rückrufe bereitstellen und diese innerhalb Ihres Abbrechen-Ereignisses im Dialogfeld verarbeiten möchten.