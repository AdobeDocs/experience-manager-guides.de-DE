---
title: Schaltfläche
description: Schaltfläche
role: User, Admin
exl-id: 40e3f254-f94e-4f43-8ff5-2e6e1eb1cb6f
source-git-commit: e40ebf4122decc431d0abb2cdf1794ea704e5496
workflow-type: tm+mt
source-wordcount: '60'
ht-degree: 5%

---

# Schaltfläche

Um eine Schaltfläche anzuzeigen, verwenden wir die Komponente, Schaltfläche .
Die Schaltflächenkomponente in JUI stellt einen HTML-Code `<button/>` dar.

```js title="buttonJSON.js"
const buttonJSON = {
  "component": "button",//tells the component name
  "label": "Yes, login",//tells the text for the button
  "variant": "cta",//tells the variants for the button which  provides default styles
  "on-click": "done",//tells what function to run after user clicks the button
};
```

Dadurch wird eine Schaltfläche mit der Bezeichnung `Yes, login` erzeugt. Die anderen Eigenschaften umfassen, sind jedoch nicht auf variant,label,on-click beschränkt.
> **_HINWEIS:_** Die `on-<events>` ist die Syntax zum Aufrufen der Befehle in den Controllern.

Die gerenderte Schaltfläche sieht wie folgt aus:

![button](imgs/yes_login_button.png "button")
