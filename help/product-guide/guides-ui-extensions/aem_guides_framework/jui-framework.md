---
title: Jui Framework
description: Grundlagen zu Jui Framework
role: User, Admin
source-git-commit: be06612d832785a91a3b2a89b84e0c2438ba30f2
workflow-type: tm+mt
source-wordcount: '265'
ht-degree: 1%

---

# Jui Framework

Bevor wir uns mit dem Schreiben von Erweiterungen befassen, werden wir die Architektur des Frameworks verstehen.
Damit wir sie effektiv erweitern können.

## Einführung

JUI ist ein MVC-Framework zusätzlich zu React- und Adobe React Spectrum-Komponenten. JUI ist die JSON-Benutzeroberfläche. Sie besteht aus mehreren Git-Repositorys.

JUI-Core ist die Kernbibliothek mit allen Logiken, um die JSON-Konfiguration in funktionierende React-Komponenten zu konvertieren und sie mit einer relevanten Controller-Klasseninstanz zu verknüpfen.
Die JUI-React-Spectrum-Bibliothek verfügt über Wrapper-Widgets von Adobe React Spectrum-Komponenten

## JUI Core Design

### MVC UI Design

![JUI MVC-Fluss](./imgs/jui-mvc-flow.png)

### Widget

- Hat eine eindeutige ID.
- Hat eine einzelne JSON-Datei zur Ansicht.
- Kann über einen eigenen oder freigegebenen Controller verfügen.
- Kann übergeordnetes Modell oder neues Modell verwenden.
- Kann UI-Elemente enthalten (React-Komponenten)
- Kann andere Widgets haben
- App ist ein Widget

![JUI Widget](./imgs/jui-widget.png)

### Element

- ist eine HTML/React-Komponente.
- Hat kein Modell, verwendet es das übergeordnete Widget-Modell.

### Ereignishandler

- Next(eventOpts)
   - So erstellen Sie einen Trigger für ein Ereignis mit einigen Optionen
- Subscribe(callback)
   - Benachrichtigung erhalten, dass das Ereignis mit der Konfiguration ausgelöst wird

### App/globales Modell

- Next(new value)
   - So veröffentlichen Sie einen neuen Wert
- Subscribe(callback)
   - So erhalten Sie eine Benachrichtigung zur Werteänderung
   - Erstes Mal alten Wert abrufen
- GetValue()
   - So rufen Sie den aktuellen Wert ab

### Controller

- Sie sollte von der Controller-Klasse erweitert werden
- APIs
- CreateModel
   - So erstellen Sie ein separates untergeordnetes Widget-Modell
- InitEventHandler
   - So erstellen Sie untergeordnete Widgets als separaten Ereignishandler
- RegisterCommands
   - So registrieren Sie lokale, übergeordnete oder App-Ereignisse
- Next(eventName, eventHandler)
   - Trigger-Ereignis des untergeordneten Widget-Ereignis-Handlers, des übergeordneten Widget-Ereignis-Handlers oder des App-Ereignis-Handlers
- Subscribe(callback, eventHandler)
- SubscribeAppModel(callback)

### Beispiel-App-Design

![Beispielanwendung](./imgs/jui-sample-app.png)
