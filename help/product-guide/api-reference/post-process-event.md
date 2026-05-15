---
title: Ereignishandler nach der Verarbeitung
description: Informationen zum Ereignis-Handler nach der Verarbeitung
exl-id: 3b105ff5-02d4-40e3-a713-206a7fcf18b2
feature: Post-Processing Event Handler
role: Developer
level: Experienced
TQID: https://experienceleague.adobe.com/ixD-jFpXxkdmPbOWtCDxPgjtxu-FfJkzGCdUHNeA1CY
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2:
  - id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 427
ht-degree: 4%

---

# Ereignishandler nach der Verarbeitung {#id175UB30E05Z}

## UUID und Cloud Service

Adobe Experience Manager Guides stellt `com/adobe/guides/postprocess/complete` Ereignis bereit, das zum Ausführen von Nachbearbeitungsvorgängen verwendet wird. Dieses Ereignis wird ausgelöst, wenn ein Vorgang für eine DITA-Datei ausgeführt wird. Die folgenden Vorgänge auf einem DITA-Datei-Trigger bewirken dieses Ereignis:

- Hochladen
- Erstellen
- Ändern

>[!NOTE]
>
> Das Nachbearbeitungs-Ereignis wird durch Aktivieren des `fire.processing.events`-Flags ausgelöst, das ein Konfigurationsparameter in der `fmdita config manager` ist. Bei Festlegung auf „true“ werden Ereignisse (com/adobe/guides/postprocess/complete) zum Tracking des Abschlusses der Nachbearbeitung Trigger. Standardmäßig ist dies auf „false“ (deaktiviert) festgelegt.

Sie müssen einen Adobe Experience Manager-Ereignishandler erstellen, um die in diesem Ereignis verfügbaren Eigenschaften zu lesen und weitere Verarbeitungsschritte durchzuführen.

Details zum Ereignis werden unten erläutert:

**Ereignisname**:

```
com/adobe/guides/postprocess/complete 
```

**Parameter**:

| Name | Typ | Beschreibung |
|----|----|-----------|
| `path` | Zeichenfolge | Pfad der Datei, die dieses Ereignis ausgelöst hat In der Regel ist dies die Datei, für die ein Vorgang ausgeführt wurde. |
| `eventType` | Zeichenfolge | Der Ereignistyp, d. h. ERSTELLEN oder ÄNDERN. |
| `status` | Zeichenfolge | Der Rückgabestatus für den ausgeführten Vorgang. Die möglichen Optionen sind: <br>- ERFOLG: Der Nachbearbeitungsvorgang wurde erfolgreich abgeschlossen. <br>- FEHLGESCHLAGEN: Der Nachbearbeitungsvorgang ist aufgrund eines Fehlers fehlgeschlagen. |
| `errorMsg` | Zeichenfolge | Die Fehlermeldung im Falle eines Fehlers beim Nachbearbeitungs-Vorgang. |
| `uuid` | Zeichenfolge | Die UUID der Datei, die dieses Ereignis ausgelöst hat. In der Regel ist dies die Datei, für die ein Vorgang ausgeführt wurde. |

**Beispiel-Ereignis-Listener**


```
@Component(service = EventHandler.class,
        immediate = true,
        property = {
                EventConstants.EVENT_TOPIC + "=" + "com/adobe/guides/postprocess/complete",
        })
public class PostProcessCompleteEventHandler implements EventHandler {

    protected final Logger log = LoggerFactory.getLogger(this.getClass());

    @Override
    public void handleEvent(final Event event) {
        Set<String> propertyNames = new HashSet<>(Arrays.asList(event.getPropertyNames()));
        Map<String, String> properties = new HashMap<>();
        properties.put("path", (String) event.getProperty("path"));
        properties.put("eventType", (String) event.getProperty("eventType"));
        properties.put("status", (String) event.getProperty("status"));
        if(propertyNames.contains("errorMsg")) {
            properties.put("errorMsg", (String) event.getProperty("errorMsg"));
        }
        if (propertyNames.contains("uuid")) {
            properties.put("uuid", (String) event.getProperty("uuid"));
        }
        String eventTopic = event.getTopic();
        log.debug("eventTopic {}", eventTopic);
        for(Map.Entry entry:properties.entrySet()) {
            log.debug(entry.getKey() + " : " + entry.getValue());
        }
    }
}
```

## Nicht-UUID


Adobe Experience Manager Guides macht das com/adobe/fmdita/postprocess/complete-Ereignis verfügbar, das für die Durchführung von Nachbearbeitungsvorgängen verwendet wird. Dieses Ereignis wird ausgelöst, wenn ein Vorgang für eine DITA-Datei ausgeführt wird. Die folgenden Vorgänge auf einem DITA-Datei-Trigger bewirken dieses Ereignis:

>[!NOTE]
>
> Dieses Ereignis wird nicht für den Löschvorgang in AEM 6.1 ausgelöst.

- Hochladen
- Kreation
- Änderung
- Löschung

Sie müssen einen Adobe Experience Manager-Ereignishandler erstellen, um die in diesem Ereignis verfügbaren Eigenschaften zu lesen und weitere Verarbeitungsschritte durchzuführen.

Details zum Ereignis werden unten erläutert:

**Ereignisname**:

```
com/adobe/fmdita/postprocess/complete 
```

**Parameter**:

| Name | Typ | Beschreibung |
|----|----|-----------|
| `path` | Zeichenfolge | Pfad der Datei, die dieses Ereignis ausgelöst hat In der Regel ist dies die Datei, für die ein Vorgang ausgeführt wurde. |
| `status` | Zeichenfolge | Der Rückgabestatus für den ausgeführten Vorgang. Die möglichen Optionen sind: <br>- ERFOLG: Der Nachbearbeitungsvorgang wurde erfolgreich abgeschlossen. <br>- ABGESCHLOSSEN MIT FEHLERN: Der Nachbearbeitungsvorgang wurde abgeschlossen, jedoch mit einigen Fehlern. <br>- FEHLGESCHLAGEN: Der Nachbearbeitungsvorgang ist aufgrund eines Fehlers fehlgeschlagen. |
| `message` | Zeichenfolge | Falls der Status MIT FEHLERN ABGESCHLOSSEN ODER FEHLGESCHLAGEN ist, enthält dieser Parameter Details zum Fehler oder zur Fehlerursache. |
| `operation` | Zeichenfolge | Der für die Datei durchgeführte Nachbearbeitungsvorgang. Die möglichen Optionen sind: <br>- Hinzufügen <br>- Aktualisieren <br> Löschen |
