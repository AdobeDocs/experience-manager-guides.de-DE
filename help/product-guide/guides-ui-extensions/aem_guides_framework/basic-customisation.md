---
title: Anpassen der App
description: Anpassen der App
role: User, Admin
exl-id: 3e454c48-2168-41a5-bbab-05c8a5b5aeb1
TQID: https://experienceleague.adobe.com/7DiEcUTAvp4rT3Fy9pIv4-zaHKwswjokjlaBgx8Pbyo
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2:
  - id: ab01a588-7dea-43f2-a699-0b3f128465d6
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 485
ht-degree: 0%

---

# Anpassen der App

## Funktionalität im Erweiterungs-Framework verfügbar gemacht

Wir haben eine Reihe von Funktionen und Gettern unter einem `proxy` verfügbar gemacht, mit dem auf Daten-, Konfigurations- und Trigger-Ereignisse zugegriffen werden kann. Nachstehend finden Sie eine Liste und wie Sie darauf zugreifen können.

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

Unsere App folgt einer MVC-Struktur (Model, View, Controller)

## Modell

Das Modell definiert die verschiedenen Attribute und speichert deren Werte. Die Werte der verschiedenen im Modell gespeicherten Attribute können vom Controller aus über die Syntax aufgerufen werden

```typescript
this.getValue('attributeName')
```

Zur Anpassung in der App werden alle neu erstellten Attribute unter einer Zuordnung im Modell hinzugefügt.
Um ein neues Attribut im Modell festzulegen, verwenden wir die folgende Syntax im Controller:

```typescript
// If a key is not already in model then it will be added to extraProps
this.setValue('key', value)
```

Um auf ein zum Modell hinzugefügtes Attribut zuzugreifen, verwenden wir die folgende Syntax:

```typescript
const value = this.getValue("key")
```

## Anzeigen

Die Ansicht definiert die Benutzeroberfläche der App. Wir verwenden JSON-Dateien, um die Ansicht unserer Dateien zu definieren. Hier definieren wir die Komponenten, das CSS (wie in der zusätzlichen Klasse der Komponenten angegeben) und rendern die im Modell gespeicherten Werte.
In unserer App wird jede Ansicht mithilfe einer JSON-Datei definiert. Auf die JSONs wird unter Verwendung ihrer eindeutigen IDs verwiesen, die als `id` bezeichnet werden.

## Controller

Der Controller dient zur Verarbeitung von Ereignissen und zur Verarbeitung der Daten. Der Controller dient zum Abrufen und Senden von Daten vom Server und ist die Schnittstelle zwischen dem, was auf der Benutzeroberfläche angezeigt und auf dem Backend gespeichert wird.

- Zum Festlegen von Werten bei der Initialisierung verwenden wir die Funktion `init` .
- Um dem Controller eine Methode hinzuzufügen, verwenden wir die folgende Syntax:

```typescript
methodName: function(args){
    // functionality
}
```

Der `methodName` dient hier als `key`, um auf die Methode in der JSON-Ansicht (View) oder in anderen Funktionen zu verweisen

- Um eine Methode im Controller aufzurufen, verwenden wir die Syntax

```typescript
this.next('methodName', args)
```

## Beispiel

Lassen Sie uns nun anhand eines einfachen Beispiels zeigen, wie diese drei Komponenten miteinander interagieren.
Wir fügen eine Schaltfläche hinzu, die den Beschriftungswert bei einem Klick ändert

### Beispiel anzeigen

Im Folgenden definieren wir die JSON für eine Schaltfläche, die einen dynamischen Text anzeigt, der im Modell unter dem Variablennamen `buttonLabel` gespeichert ist.
In diesem Beispiel wird durch Klicken auf die Schaltfläche die Bezeichnung geändert.

```JSON
{
    "component": "button",
    "label": "@extraProps.buttonLabel",
    "variant": "cta",
    "on-click": "switchButtonLabel",
}
```

### Beispielmodell

In diesem Fall enthält `extraProps.buttonLabel` die Beschriftung der Schaltfläche

### Beispiel für einen Controller

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

Unter GIF wird der obige Code in Aktion angezeigt
![basic_customization](imgs/basic_customisation.gif "Basic customization-Schaltfläche")


### Konfigurationsbeispiel anzeigen

In diesem Fall greifen wir mithilfe von `viewConfig` auf das Suchmodusereignis zu und erstellen einen Trigger, um es zu aktualisieren

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

### Abonnieren - Beispiel

In diesem Fall fügen wir ein Abonnement unter „Datei umbenennen“ zum Konsolenprotokoll hinzu, wenn die Option „Datei umbenennen“ angeklickt wird

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

### Anwendungsereignis-Beispiel abonnieren

In diesem Fall wurde die Anmeldung am aktiven Dokument der Konsole geändert (Registerkarten in der Editor-Benutzeroberfläche werden geändert)

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

### Anwendungsmodellereignisse abonnieren - Beispiel

Beispiel für das Abonnieren von Mobile-App-Modellereignissen wie `app.mode`

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

In diesem fügen wir ein Abonnement für `tabChange` Ereignis hinzu, das ein Ereignis `left_panel_container` Controllers ist, der agiert
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

Sie können direkt ausgelöst werden, wenn Sie wissen, welches Ereignis ausgelöst werden soll und welche Daten es enthält

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
