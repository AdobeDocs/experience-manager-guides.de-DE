---
title: JUI-Framework
description: Grundlegendes zum UI-Framework
role: User, Admin
exl-id: c193cf90-5916-4d8c-88f1-be5014beca1c
source-git-commit: e40ebf4122decc431d0abb2cdf1794ea704e5496
workflow-type: tm+mt
source-wordcount: '265'
ht-degree: 1%

---

# JUI-Framework

Bevor wir uns mit dem Schreiben von Erweiterungen befassen, werden wir die Architektur des Frameworks verstehen.
Damit wir es effektiv verlängern können.

## Einführung

JUI ist ein MVC-Framework, das auf React- und Adobe-React-Spectrum-Komponenten aufbaut. JUI ist die JSON-Benutzeroberfläche. Es besteht aus mehreren Git-Repositorys.

JUI-Core ist die Kernbibliothek mit der gesamten Logik zum Konvertieren der JSON-Konfiguration in funktionierende React-Komponenten und zum Verknüpfen mit einer relevanten Controller-Klasseninstanz.
JUI-React-Spectrum  Die -Bibliothek verfügt über Wrapper-Widgets zum Adobe von React Spectrum-Komponenten

## JUI-Kerndesign

### MVC-UI-Design

![JUI MVC-Fluss](./imgs/jui-mvc-flow.png)

### Widget

- Hat eine eindeutige ID.
- Hat eine einzelne JSON-Datei zur Ansicht.
- Kann einen eigenen oder freigegebenen Controller haben.
- Kann übergeordnetes Modell oder neues Modell verwenden.
- Kann Benutzeroberflächenelemente (React-Komponenten) enthalten
- Kann andere Widgets haben
- App ist ein Widget

![JUI-Widget](./imgs/jui-widget.png)

### Element

- ist eine HTML-/React-Komponente.
- hat kein Modell, es verwendet das übergeordnete Widget-Modell.

### Ereignishandler

- Next(eventOpts)
   - Zum Trigger des Ereignisses mit einigen Optionen
- Subscribe(callback)
   - Benachrichtigung abrufen, dass das Ereignis mit der Konfiguration ausgelöst wird

### App/Globales Modell

- Next(neuer Wert)
   - So veröffentlichen Sie einen neuen Wert
- Subscribe(callback)
   - So rufen Sie eine Benachrichtigung über Wertänderung ab
   - Erster alter Wert
- GetValue()
   - Abrufen des aktuellen Werts

### Controller

- Sie sollte von der Controller-Klasse erweitert werden.
- APIs
- CreateModel
   - So erstellen Sie ein separates untergeordnetes Widget-Modell
- InitEventHandler
   - So erstellen Sie einen separaten Ereignishandler für untergeordnete Widgets
- RegistrierenBefehle
   - So registrieren Sie lokale, übergeordnete oder App-Ereignisse
- Next(eventName, eventHandler)
   - Trigger Zum Ereignisereignis des untergeordneten Widget-Ereignishandlers, des übergeordneten Widget-Ereignishandlers oder des App-Ereignishandlers
- Subscribe(callback, eventHandler)
- SubscribeAppModel(callback)

### Beispiel für App-Design

![Beispielanwendung](./imgs/jui-sample-app.png)
