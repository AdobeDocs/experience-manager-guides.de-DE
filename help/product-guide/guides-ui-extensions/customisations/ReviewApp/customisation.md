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

Um die Anpassung der Review-App zu erleichtern, haben wir einige der unten aufgeführten und erläuterten Erweiterungspunkte bereitgestellt:

## Review-Comment

- id: `review_comment`
- hook: `this.next('updateExtraProps')`:

Wie [hier](../../aem_guides_framework/basic-customisation.md) erläutert, werden alle neuen Attribute, die bei der Anpassung hinzugefügt werden, unter `this.model.extraProps` gespeichert. Mit der Methode &quot;`updateExtraProps`&quot; können Sie einem Überprüfungskommentar Attribute hinzufügen und dabei auch die Aktualisierung und Speicherung des hinzugefügten Attributs auf dem Server durchführen.

### Nutzungsbeispiel

Angenommen, Sie möchten Ihren Kommentaren die Felder `commentRationale` und `severity` hinzufügen.
Aktualisieren wir die `commentRationale` auf &quot;Dies ist ein wichtiger Satz&quot;. und die `severity` auf &quot;CRITICAL&quot;setzen.
Dies kann mithilfe der folgenden Syntax erfolgen:

```typescript
  this.next('updateExtraProps', {
    'commentRationale': 'This is an important sentence.',
    'severity': 'CRITICAL'
  })
```

Das obige Codefragment verarbeitet die Aktualisierung und Speicherung der Werte. Die gespeicherten Werte können über die Benutzeroberfläche gerendert werden, indem die Ansicht definiert wird.

```JSON
{
    "component" : "label",
    "label": "@extraProps.commentRationale"
}
```

## Bedienfeld für Inline-Überprüfung

- id: `inline_review_panel`

1. hook: `onNewCommentEvent`
Mit dem Hook `onNewCommentEvent` können Sie ein Ereignis ausgeben oder eine Methode für ein neues Kommentar- oder Antwortereignis aufrufen.
Die im `onNewCommentEvent` empfangenen Protokolle umfassen:
   - events: das Kommentar-/Antwortereignis, das gesendet wurde.
   - newComment: boolean
Wenn das gesendete Ereignis ein neues Kommentar-Ereignis war, d. h. `highlight`, `insertion`, `deletion`, `sticky note comment`
   - newReply: boolean
Wenn das gesendete Ereignis ein neues Antwortereignis war.

2. hook: `sendExtraProps`

Dieser Erweiterungspunkt ist nützlich, wenn Sie einen `event` erweitern und `extraProps` aus dem Inline-Überprüfungsfenster senden möchten. Wir erklären Ihnen die Verwendung dieser beiden Haken unten.

### Beispiel für Inline-Prüfungsbereich

Angenommen, wir möchten bei jedem Versand eines neuen Kommentars oder einer neuen Antwort eine extraProp, `userInfo` senden. Nun erfolgt dies über das Inline-Überprüfungsfenster, aber wir haben nicht den Verweis auf die commentId des neu generierten Kommentars, daher können wir zu diesem Zweck den folgenden Code schreiben.

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

Im obigen Codeausschnitt überprüfen wir, ob das gesendete Ereignis ein neuer Kommentar oder eine neue Antwort war. Im Falle eines neuen Kommentars oder einer neuen Antwort rufen wir die Methode `setUserInfo` auf

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

In der obigen Methode erweitern wir das Ereignis, um extraProps zu senden, die den Vornamen, die E-Mail-Adresse, den Titel usw. des Benutzers enthalten. Wenn Sie das Ereignis auf diese Weise erweitern, wird sichergestellt, dass die extraProps mit der richtigen commentId gesendet werden, sodass sie an den richtigen Kommentar angehängt werden.

Der Hook `updateExtraProps` nennt grundsätzlich den Hook `sendExtraProps`, also wann was zu verwenden ist?

Wir verwenden `updateExtraProps` im `review_comment`-Controller, der bereits über die `id` des Kommentars verfügt, und deshalb müssen Sie nur die `extraProps.` erwähnen

Die `inline_review_panel` hat jedoch keinen Zugriff auf die ID des Kommentars. Jedes Mal, wenn Sie ein Ereignis aus dem Inline-Überprüfungsfenster senden müssen, ist die `sendExtraProps` praktisch.
