---
title: Ereignishandler nach der Verarbeitung
description: Informationen zum Ereignis-Handler nach der Verarbeitung
exl-id: 3b105ff5-02d4-40e3-a713-206a7fcf18b2
feature: Post-Processing Event Handler
role: Developer
level: Experienced
source-git-commit: 83966cc9187b13dd3b5956821e0aa038b41db28e
workflow-type: tm+mt
source-wordcount: '198'
ht-degree: 5%

---

# Ereignishandler nach der Verarbeitung {#id175UB30E05Z}

AEM Guides macht das com/adobe/fmdita/postprocess/complete-Ereignis verfügbar, das für die Durchführung von Nachbearbeitungsvorgängen verwendet wird. Dieses Ereignis wird ausgelöst, wenn ein Vorgang für eine DITA-Datei ausgeführt wird. Die folgenden Vorgänge auf einem DITA-Datei-Trigger bewirken dieses Ereignis:

>[!NOTE]
>
> Dieses Ereignis wird nicht für den Löschvorgang in AEM 6.1 ausgelöst.

- Hochladen
- Kreation
- Änderung
- Löschung

Sie müssen einen AEM-Ereignishandler erstellen, um die in diesem Ereignis verfügbaren Eigenschaften zu lesen und die Verarbeitung fortzusetzen.

Details zum Ereignis werden unten erläutert:

**Ereignisname**:

```
com/adobe/fmdita/postprocess/complete 
```

**Parameter**:

| Name | Typ | Beschreibung |
|----|----|-----------|
| `path` | Zeichenfolge | Pfad der Datei, die dieses Ereignis ausgelöst hat In der Regel ist dies die Datei, für die ein Vorgang ausgeführt wurde. |
| `status` | Zeichenfolge | Der Rückgabestatus für den ausgeführten Vorgang. Die möglichen Optionen sind: - <br>- ERFOLG: Der Nachbearbeitungsvorgang wurde erfolgreich abgeschlossen. <br>- ABGESCHLOSSEN MIT FEHLERN: Der Nachbearbeitungsvorgang wurde abgeschlossen, jedoch mit einigen Fehlern. <br>- FEHLGESCHLAGEN: Der Nachbearbeitungsvorgang ist aufgrund eines schwerwiegenden Fehlers fehlgeschlagen. |
| `message` | Zeichenfolge | Falls der Status MIT FEHLERN ABGESCHLOSSEN ODER FEHLGESCHLAGEN ist, enthält dieser Parameter Details zum Fehler oder zur Fehlerursache. |
| `operation` | Zeichenfolge | Der für die Datei durchgeführte Nachbearbeitungsvorgang. Die möglichen Optionen sind: <br>- Hinzufügen <br>- Aktualisieren <br> Löschen |
