---
title: Anpassen
description: Anpassen der Überprüfungs-App
role: User, Admin
exl-id: 9f6a4e9f-fc13-40b5-a30f-151c94faff81
source-git-commit: 492f72768e0de74a91eb7acc9db8264e21bfc810
workflow-type: tm+mt
source-wordcount: '402'
ht-degree: 0%

---

# Anpassen der Überprüfungs-App

Um die Anpassung der Überprüfungs-App zu erleichtern, haben wir einige unten aufgeführte und erläuterte Erweiterungspunkte bereitgestellt:

## review-comment

- ID: `review_comment`
- Hook: `this.next('updateExtraProps')`:

Wie [hier](../../aem_guides_framework/basic-customisation.md) erläutert, wird jedes neue Attribut, das während der Anpassung hinzugefügt wird, unter `this.model.extraProps`. Mit der Methode `updateExtraProps` können Sie Attribute zu einem Überprüfungskommentar hinzufügen und so die Aktualisierung und Speicherung des hinzugefügten Attributs auf dem Server durchführen.

### Anwendungsbeispiel

Sie können beispielsweise Felder `commentRationale` und `severity` zu Ihren Kommentaren hinzufügen.
Aktualisieren wir die `commentRationale` auf „Dies ist ein wichtiger Satz“. und die `severity` auf „KRITISCH“.
Dies kann mit der Syntax erfolgen:

```typescript
  this.next('updateExtraProps', {
    'commentRationale': 'This is an important sentence.',
    'severity': 'CRITICAL'
  })
```

Das obige Codefragment übernimmt die Aktualisierung und Speicherung der Werte. Die gespeicherten Werte können in der Benutzeroberfläche gerendert werden, indem die Ansicht definiert wird.

```JSON
{
    "component" : "label",
    "label": "@extraProps.commentRationale"
}
```

## Inline-Überprüfungsfeld

- ID: `inline_review_panel`

1. Hook: `onNewCommentEvent`
Mit dem Hook-`onNewCommentEvent` können Sie ein Ereignis auslösen oder eine Methode bei einem neuen Kommentar- oder Antwortereignis aufrufen.
Zu den in der `onNewCommentEvent` empfangenen Argumenten gehören:
   - Ereignisse: Das Kommentar-/Antwortereignis, das gesendet wurde.
   - newComment: Boolesch
Wenn das gesendete Ereignis ein neues Kommentarereignis war, d. h. `highlight`, `insertion`, `deletion`, `sticky note comment`
   - newReply: Boolesch
Wenn das gesendete Ereignis ein neues Antwortereignis war.

2. Hook: `sendExtraProps`

Dieser Hook ist nützlich, wenn Sie eine `event` erweitern und `extraProps` über das Inline-Prüfungsfenster senden möchten. Nachfolgend werden wir die Verwendung dieser beiden Erweiterungspunkte erläutern.

### Beispiel für ein Inline-Prüfungsbedienfeld

Angenommen, wir möchten jedes Mal, wenn ein neuer Kommentar oder eine Antwort gesendet wird, eine extraProp, `userInfo` senden. Nun erfolgt dies über das Inline-Prüfungsfenster, jedoch haben wir nicht den Verweis auf die commentId des neu generierten Kommentars, daher können wir zu diesem Zweck den folgenden Code schreiben.

```typescript
    onNewCommentEvent(args){
      const events = _.get(args, "events")
      const currTopicIndex = tcx.model.getValue(tcx.model.KEYS.REVIEW_CURR_TOPIC) || this.getValue('currTopicIndex') || "0"
      const event = _.get(_.get(events, currTopicIndex), '0')
      const newComment = _.get(args, 'newComment')
      const newReply = _.get(args, 'newReply')
      if ((newComment || newReply) && event) {
        this.next('setUserInfo', event)
      }
    },
```

Im obigen Code-Snippet überprüfen wir, ob das gesendete Ereignis ein neuer Kommentar oder eine neue Antwort war. Im Falle eines neuen Kommentars oder einer neuen Antwort rufen wir die Methode `setUserInfo` auf

```typescript
    const getUserInfo = (userId) => {
      return $.ajax({
        url: '/bin/dxml/xmleditor/userinfo',
        data: {
          username: userId,
        },
        success: (data) => {
          return data
        }
      })
    }

    setUserInfo(event) {
      getUserInfo(event.user).done(userData => {
        const extraProps = {
          "userFirstName": userData?.givenName || '',
          "userLastName": userData?.familyName || '',
          "userTitle": userData?.title || '',
          "userJobTitle": userData?.jobTitle || '',
          'userEmail': userData?.email || '',
        }
        const data = {... event, extraProps}
        this.next(
          'sendExtraProps',
          data
        )
      })
    },
```

Bei der obigen Methode erweitern wir das Ereignis, um zusätzliche Props zu senden, die den Vornamen, die E-Mail-Adresse, den Titel usw. des Benutzers enthalten. Wenn Sie das Ereignis auf diese Weise erweitern, wird sichergestellt, dass die zusätzlichen Props mit der richtigen commentId gesendet werden, sodass sie an den richtigen Kommentar angehängt werden.

Der Hook ruft `updateExtraProps` von Natur aus den Hook `sendExtraProps` auf, wann soll er also verwendet werden?

Wir verwenden `updateExtraProps` im `review_comment` Controller, der bereits die `id` des Kommentars hat und daher muss man nur die `extraProps.` erwähnen

Der `inline_review_panel` hat jedoch keinen Zugriff auf die ID des Kommentars. Daher ist die `sendExtraProps` praktisch, sobald Sie ein Ereignis aus dem Inline-Prüfungsfenster senden müssen.
