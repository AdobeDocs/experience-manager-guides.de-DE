---
title: Massenaktivierung - vollständiger Ereignishandler
description: Informationen zum vollständigen Ereignis-Handler für die Massenaktivierung
feature: Bulk Activation Event Handler
role: Developer
level: Experienced
exl-id: 08b153d7-3d13-4804-9e3e-38790dbea1f3
source-git-commit: 9b8971bf7065a94a2e42669094249c822c555718
workflow-type: tm+mt
source-wordcount: '185'
ht-degree: 7%

---

# Massenaktivierung - vollständiger Ereignishandler

Experience Manager Guides stellt `com/adobe/fmdita/replication/complete` Ereignis bereit, mit dem alle Vorgänge nach Abschluss eines Massenaktivierungsprozesses ausgeführt werden. Dieses Ereignis wird ausgelöst, wenn ein Massenaktivierungsprozess abgeschlossen ist. Wenn Sie beispielsweise die Massenaktivierung einer AEM-Site-Voreinstellung einer Zuordnung ausführen, wird dieses Ereignis nach dem Ende des Aktivierungsprozesses aufgerufen.

Sie müssen einen AEM-Ereignishandler erstellen, um die in diesem Ereignis verfügbaren Eigenschaften zu lesen und die Verarbeitung fortzusetzen.

Details zum Ereignis werden unten erläutert:

**Ereignisname**:

```
com/adobe/fmdita/replication/complete 
```

**Parameter**:

| Name | Typ | Beschreibung |
|----|----|-----------|
| `path` | Zeichenfolge | Pfad der Datei, die dieses Ereignis ausgelöst hat <br> Zum Beispiel `/content/output/sites/ditamap1-ditamap`. <br> Es handelt sich um eine Liste von Pfaden, die als JSON-Array serialisiert wurden. |
| `messageType` | Zeichenfolge | Der Typ einer Nachricht. <br>Mögliche Option: `REPLICATION` |
| `action` | Zeichenfolge | Dies ist die durchgeführte Aktion. <br>Mögliche Option: `BulkReplicate` |
| `user` | Zeichenfolge | Der Benutzer, der den Vorgang gestartet hat. |
| `result` | Zeichenfolge | Das Ergebnis der Massenaktivierung. Es handelt sich um ein serialisiertes JSON-Objekt: <br>`{"success":boolean,"code":integer,"message":"" }` |
| `agentId` | Zeichenfolge | Die bei der Replikation verwendete agentId. Zum Beispiel: `"publish"`. |
| `importMode` | Zeichenfolge | Bei Aktivierung verwendeter Importmodus. Die möglichen Optionen sind: <br>`REPLACE, MERGE, UPDATE`. |


**Beispiel-Ereignis-Listener**:

```XML
@Component(service = EventHandler.class,
        immediate = true,
        property = {
                EventConstants.EVENT_TOPIC + "=" + "com/adobe/fmdita/replication/complete",
        })
 
public class SampleEventHandler implements EventHandler {
 
    protected final Logger log = LoggerFactory.getLogger(this.getClass());
 
    @Override
    public void handleEvent(final Event event) {
        Map<String, String> properties = new HashMap<>();
        properties.put("paths", (String) event.getProperty("paths"));
        properties.put("messageType", (String) event.getProperty("messageType"));
        properties.put("action", (String) event.getProperty("action"));
        properties.put("result", (String) event.getProperty("result"));
        properties.put("user", (String) event.getProperty("user"));
        properties.put("agentId", (String) event.getProperty("agentId"));
        properties.put("importMode", (String) event.getProperty("importMode"));
 
        String eventTopic = event.getTopic();
        log.debug("eventTopic {}", eventTopic);
        for(Map.Entry entry:properties.entrySet()) {
            log.debug(entry.getKey() + " : " + entry.getValue());
        }
 
    }
}
```
