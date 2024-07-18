---
title: Anpassen der App
description: Anpassen der App
role: User, Admin
exl-id: 3e454c48-2168-41a5-bbab-05c8a5b5aeb1
source-git-commit: 3615928117ce1be527dc3c6d2ec8ddd115b78b0a
workflow-type: tm+mt
source-wordcount: '486'
ht-degree: 0%

---

# Anpassen der App

## Verfügbare Funktionen im Erweiterungs-Framework

Wir haben eine Reihe von Funktionen und Gettern unter einem `proxy` bereitgestellt, die für den Zugriff auf Daten, Konfigurationen und Trigger-Ereignisse verwendet werden können. Unten finden Sie eine Liste und wie Sie darauf zugreifen können.

```typescript
interface EventData {
  key?: string,
  keys?: string[]
  view?: any,
  next?: any,
  error?: any,
  completed?: any,
  id?: any
}

* getValue(key)
* setValue(key, value)
* subject // getter
* subscribe(opts: EventData)
* subscribeAppEvent(opts: EventData)
* subscribeAppModel(key, next)
* subscribeParentEvent(opts: EventData)
* parentEventHandlerNext(eventName: string, opts: any)
* appModelNext(eventName:string, opts) 
* appEventHandlerNext(eventName:string, opts)
* next(eventName:string, opts, eventHandler?)
* viewConfig //getter
* args //getter
```

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
    init: function () {
      this.setValue("buttonLabel", "Submit")
    },

    switchButtonLabel(){
        const buttonLabel = this.getValue("buttonLabel") === "Submit"? "Cancel" : "Submit"
        this.setValue("buttonLabel", buttonLabel)
    }
  }
```

Unter GIF wird der oben stehende Code in Aktion angezeigt.
![basic_customization](imgs/basic_customisation.gif "Schaltfläche &quot;Grundlegende Anpassung&quot;")


### Konfigurationsbeispiel anzeigen

In diesem Fall greifen wir mithilfe von `viewConfig` auf das Suchmodusereignis zu und führen einen Trigger durch, um es zu aktualisieren

```typescript
  { 
    id: 'repository_panel', 
    controller: {
      init: function () {
        console.log('Logging view config ', this.viewConfig)
        this.next(this.viewConfig.items[1].searchModeChangedEvent, { searchMode: true })
      }
    }
  }
```

### Beispiel abonnieren

In diesem Fall wird das Abonnement für den Dateinamen zum Konsolenprotokoll hinzugefügt, wenn die Option zum Umbenennen der Datei angeklickt wird.

```typescript
  { 
    id: 'repository_panel', 
    controller: {
      init: function () {
        this.subscribe({
          key: 'rename',
          next: () => { console.log('rename using extension') }
        })
      }
    }
  }
```

### Beispiel für ein App-Ereignis abonnieren

In diesem Fall protokollieren wir die Konsole über das geänderte aktive Dokument (Registerkarten in der Editor-Benutzeroberfläche ändern)

```typescript
  { 
    id: 'repository_panel', 
    controller: {
      init: function () {
        this.subscribeAppEvent({
          key: 'app.active_document_changed',
          next: () => { console.log('Extension: active document changed') }
        })
      }
    }
  }
```

### Beispiel für App-Modellereignisse abonnieren

Beispiel für das Abonnieren von App-Modellereignissen wie `app.mode`

```typescript
  { 
    id: 'repository_panel', 
    controller: {
      init: function () {
        this.subscribeAppModel('app.mode',
          () => { console.log('app mode subs') }
        )
      }
    }
  }
```

### Beispiel für übergeordnete Controller-Ereignisse

In diesem Beispiel fügen wir ein Abonnement für das `tabChange`-Ereignis hinzu, das ein Ereignis des `left_panel_container`-Controllers ist, der handelt
als übergeordneter Controller für `repository_panel`

```typescript
  { 
    id: 'repository_panel', 
    controller: {
      init: function () {
        this.subscribeParentEvent({
          key: 'tabChange',
          next: () => { console.log('tab change subs') }
        })
        this.parentEventHandlerNext('tabChange', {
          data: 'map_panel'
        )
      }
    }
  }
```

### App-Modell und App-Controller als Nächstes

Sie können direkt ausgelöst werden, indem Sie wissen, dass das richtige Ereignis ausgelöst wird und die zugehörigen Daten

```typescript
  { 
    id: 'file_options', 
    controller: {
      init: function () {
        this.appModelNext('app.mode', 'author')
        this.appEventHandlerNext('app.active_document_changed', 'active doc changed')   
      }
    }
  } 
```
