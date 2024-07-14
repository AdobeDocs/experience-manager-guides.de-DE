---
title: Anpassen der App
description: Anpassen der App
role: User, Admin
exl-id: 3e454c48-2168-41a5-bbab-05c8a5b5aeb1
source-git-commit: 4f00d6b7ad45636618bafe92e643b3e288ec2643
workflow-type: tm+mt
source-wordcount: '336'
ht-degree: 0%

---

# Anpassen der App

Unsere App folgt einer MVC-Struktur (Modell, Ansicht, Controller)

## Modell

Das Modell definiert die verschiedenen Attribute und speichert deren Werte. Auf die Werte der verschiedenen im Modell gespeicherten Attribute kann vom Controller mithilfe der Syntax zugegriffen werden

```typescript
this.getValue('attributeName')
```

Zur Anpassung in der App werden alle neu erstellten Attribute unter einer Zuordnung im Modell hinzugefügt.
Um ein neues Attribut im Modell festzulegen, verwenden wir die folgende Syntax im Controller:

```typescript
// If a key is not already in model then it will be added to extraProps
this.setValue('key', value)
```

Um auf ein Attribut zuzugreifen, das dem Modell hinzugefügt wurde, verwenden wir die folgende Syntax:

```typescript
const value = this.getValue("key")
```

## Anzeigen

Die Ansicht definiert die Benutzeroberfläche der App. Wir verwenden JSON-Dateien, um die Ansicht unserer Dateien zu definieren. In unserem Beispiel definieren wir die Komponenten, den CSS (wie in der Extraklasse der Komponenten angegeben) und rendern die im Modell gespeicherten Werte.
In unserer App wird jede Ansicht mithilfe einer JSON definiert. Auf die JSONs wird mit ihren eindeutigen IDs, die als `id` bezeichnet werden, verwiesen.

## Controller

Der Controller wird verwendet, um Ereignisse zu verarbeiten und die Daten zu verarbeiten. Der Controller wird verwendet, um Daten vom Server abzurufen und zu senden. Es ist die Schnittstelle zwischen dem, was auf der Benutzeroberfläche angezeigt und im Backend gespeichert wird.

- Zum Festlegen von Werten bei der Initialisierung verwenden wir die Funktion `init` .
- Um eine Methode zum Controller hinzuzufügen, verwenden wir die folgende Syntax:

```typescript
methodName: function(args){
    // functionality
}
```

Die `methodName` dient hier als `key`, um auf die Methode in der JSON (Ansicht) oder in anderen Funktionen zu verweisen

- Um eine Methode im Controller aufzurufen, verwenden wir die Syntax

```typescript
this.next('methodName', args)
```

## Beispiel

Verwenden wir nun ein einfaches Beispiel, um zu zeigen, wie diese drei Komponenten miteinander interagieren.
Wir fügen eine Schaltfläche hinzu, mit der der Beschriftungswert eines Klicks geändert wird.

### Beispiel anzeigen

Unten definieren wir die JSON für eine Schaltfläche, die einen dynamischen Text anzeigt, der im Modell unter dem Variablennamen `buttonLabel` gespeichert ist.
In diesem Beispiel ändert sich der Titel der Schaltfläche.

```JSON
{
    "component": "button",
    "label": "@extraProps.buttonLabel",
    "variant": "cta",
    "on-click": "switchButtonLabel",
}
```

### Modellbeispiel

In diesem Fall enthält `extraProps.buttonLabel` den Titel der Schaltfläche

### Controller-Beispiel

```typescript
  controller: {
    init: function (context) {
      context.setValue("buttonLabel", "Submit")
    },

    switchButtonLabel(){
        const buttonLabel = this.getValue("buttonLabel") === "Submit"? "Cancel" : "Submit"
        this.setValue("buttonLabel", buttonLabel)
    }
  }
```

Unter GIF wird der oben stehende Code in Aktion angezeigt.
![basic_customization](imgs/basic_customisation.gif "Schaltfläche &quot;Grundlegende Anpassung&quot;")
