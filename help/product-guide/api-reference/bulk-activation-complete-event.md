---
title: Ereignis-Handler für Massenaktivierung
description: Erfahren Sie mehr über den Massen-Aktivierungsabschließen-Ereignishandler
feature: Bulk Activation Event Handler
role: Developer
level: Experienced
exl-id: 08b153d7-3d13-4804-9e3e-38790dbea1f3
source-git-commit: 9b8971bf7065a94a2e42669094249c822c555718
workflow-type: tm+mt
source-wordcount: '185'
ht-degree: 7%

---

# Ereignis-Handler für Massenaktivierung

Experience Manager Guides zeigt das `com/adobe/fmdita/replication/complete` -Ereignis an, das verwendet wird, um nach Abschluss eines Massenaktivierungsprozesses alle Vorgänge auszuführen. Dieses Ereignis wird ausgelöst, wenn ein Massenaktivierungsprozess abgeschlossen ist. Wenn Sie beispielsweise die Massenaktivierung einer AEM Site-Vorgabe einer Zuordnung ausführen, wird dieses Ereignis nach dem Ende des Aktivierungsprozesses aufgerufen.

Sie müssen einen AEM Ereignishandler erstellen, um die in diesem Ereignis verfügbaren Eigenschaften zu lesen und eine weitere Verarbeitung durchzuführen.

Ereignisdetails werden nachfolgend erläutert:

**Ereignisname**:

```
com/adobe/fmdita/replication/complete 
```

**Parameter**:

| Name | Typ | Beschreibung |
|----|----|-----------|
| `path` | Zeichenfolge | Der Pfad der Datei, die dieses Ereignis ausgelöst hat. <br> Zum Beispiel `/content/output/sites/ditamap1-ditamap`. <br> Dies ist eine Liste von Pfaden, die als JSON-Array serialisiert wurden. |
| `messageType` | Zeichenfolge | Der Typ einer Nachricht. <br>Mögliche Option : `REPLICATION` |
| `action` | Zeichenfolge | Dies ist die ausgeführte Aktion. <br>Mögliche Option : `BulkReplicate` |
| `user` | Zeichenfolge | Der Benutzer, der den Vorgang gestartet hat. |
| `result` | Zeichenfolge | Das Ergebnis der Massenaktivierung. Dies ist ein serialisiertes JSON-Objekt: <br>`{"success":boolean,"code":integer,"message":"" }` |
| `agentId` | Zeichenfolge | Die in der Replikation verwendete agentId. Zum Beispiel: `"publish"`. |
| `importMode` | Zeichenfolge | In Activation verwendeter Importmodus. Die möglichen Optionen sind: <br>`REPLACE, MERGE, UPDATE`. |


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
