---
title: Schaltfläche
description: Schaltfläche
role: User, Admin
source-git-commit: be06612d832785a91a3b2a89b84e0c2438ba30f2
workflow-type: tm+mt
source-wordcount: '60'
ht-degree: 5%

---


# Schaltfläche

Um eine Schaltfläche anzuzeigen, verwenden wir die Komponente, Schaltfläche .
Die Schaltflächenkomponente in JUI stellt einen HTML-Code dar `<button/>`.

```js title="buttonJSON.js"
const buttonJSON = {
  "component": "button",//tells the component name
  "label": "Yes, login",//tells the text for the button
  "variant": "cta",//tells the variants for the button which  provides default styles
  "on-click": "done",//tells what function to run after user clicks the button
};
```

Dadurch wird eine Schaltfläche mit der Bezeichnung `Yes, login`. Die anderen Eigenschaften umfassen, sind jedoch nicht auf variant,label,on-click beschränkt.
> **_NOTE:_**  Die `on-<events>` ist die Syntax zum Aufrufen der Befehle in den Controllern.

Die gerenderte Schaltfläche sieht wie folgt aus:

![button](imgs/yes_login_button.png "Schaltfläche")
