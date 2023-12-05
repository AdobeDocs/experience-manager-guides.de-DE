---
title: Ereignishandler für die Nachbearbeitung
description: Erfahren Sie mehr über den Ereignishandler für die Nachbearbeitung
exl-id: 3b105ff5-02d4-40e3-a713-206a7fcf18b2
source-git-commit: 5e0584f1bf0216b8b00f00b9fe46fa682c244e08
workflow-type: tm+mt
source-wordcount: '198'
ht-degree: 1%

---

# Ereignishandler für die Nachbearbeitung {#id175UB30E05Z}

AEM Guides stellen das com/adobe/fmdita/postprocess/complete-Ereignis bereit, das zur Durchführung von Nachbearbeitungsvorgängen verwendet wird. Dieses Ereignis wird ausgelöst, wenn ein Vorgang für eine DITA-Datei ausgeführt wird. Die folgenden Vorgänge auf einen DITA-Datei-Trigger verweisen auf dieses Ereignis:

>[!NOTE]
>
> Dieses Ereignis wird für den Löschvorgang in AEM 6.1 nicht ausgelöst.

- Hochladen
- Kreation
- Änderung
- Löschen

Sie müssen einen AEM Ereignishandler erstellen, um die in diesem Ereignis verfügbaren Eigenschaften zu lesen und eine weitere Verarbeitung durchzuführen.

Ereignisdetails werden nachfolgend erläutert:

**Ereignisname**:

```
com/adobe/fmdita/postprocess/complete 
```

**Parameter**: |Name|Typ|Beschreibung| |—|—|—| |`path`|String|Der Pfad der Datei, die dieses Ereignis ausgelöst hat. Normalerweise handelt es sich hierbei um die Datei, für die ein Vorgang ausgeführt wurde.| |`status`|String|Der Rückgabestatus für den ausgeführten Vorgang. Die möglichen Optionen sind: - <br>- ERFOLG: Der Nachbearbeitungsprozess wurde erfolgreich abgeschlossen. <br>- MIT FEHLERN ABGESCHLOSSEN: Der Nachbearbeitungsprozess ist abgeschlossen, allerdings mit einigen Fehlern. <br>- FEHLGESCHLAGEN: Die Nachbearbeitung schlug aufgrund eines fatalen Fehlers fehl.| |`message`|Zeichenfolge|Falls der Status MIT FEHLERN ODER FEHLGESCHLAGEN ABGESCHLOSSEN ist, enthält dieser Parameter die Details zum Fehler oder zum Grund des Fehlschlagens.| |`operation`|String|Der Nachbearbeitungsvorgang, der für die Datei ausgeführt wird. Die möglichen Optionen sind:<br>- Zusatz <br>- Aktualisierung <br>- Löschen|
