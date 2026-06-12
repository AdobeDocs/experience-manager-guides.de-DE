---
title: JUI-Framework
description: Grundlegendes zum UI-Framework
role: User, Admin
exl-id: c193cf90-5916-4d8c-88f1-be5014beca1c
TQID: https://experienceleague.adobe.com/AQFEy2bHTDHXq6QH8KTBOEzUvtA3Hf2ojhxvD0dsI7o
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2:
  - id: a01bfd36-4ab8-4bf8-9dc0-5b45b890552e
  - id: c6d09140-3c91-45d3-b7ed-b681af752f43
  - id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 249
ht-degree: 1%

---

# JUI-Framework

Bevor wir uns mit dem Schreiben von Erweiterungen befassen, werden wir die Architektur des Frameworks verstehen.
Damit wir es effektiv verlängern können.

## Einführung

JUI ist ein MVC-Framework, das auf React- und Adobe React Spectrum-Komponenten aufbaut. JUI ist die JSON-Benutzeroberfläche. Es besteht aus mehreren Git-Repositorys.

JUI-Core ist die Kernbibliothek mit der gesamten Logik zum Konvertieren der JSON-Konfiguration in funktionierende React-Komponenten und zum Verknüpfen mit einer relevanten Controller-Klasseninstanz.
Die JUI-React-Spectrum-Bibliothek verfügt über Wrapper-Widgets von Adobe React Spectrum-Komponenten

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

- ist eine HTML/React-Komponente.
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
   - Zum Ereignisereignis des untergeordneten Widget-Ereignishandlers, des übergeordneten Widget-Ereignishandlers oder des App-Ereignishandlers
- Subscribe(callback, eventHandler)
- SubscribeAppModel(callback)

### Beispiel für App-Design

![Beispielanwendung](./imgs/jui-sample-app.png)
