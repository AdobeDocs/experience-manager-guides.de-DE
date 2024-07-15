---
title: Ereignis-Handler für Massenaktivierung
description: Erfahren Sie mehr über den Massen-Aktivierungsabschließen-Ereignishandler
feature: Bulk Activation Event Handler
role: Developer
level: Experienced
exl-id: 08b153d7-3d13-4804-9e3e-38790dbea1f3
source-git-commit: e40ebf4122decc431d0abb2cdf1794ea704e5496
workflow-type: tm+mt
source-wordcount: '185'
ht-degree: 2%

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

|Name|Type|Description|
|----|----|-----------|
|`path`|String|The path of the file that triggered this event. <br> For example, `/content/output/sites/ditamap1-ditamap`. <br> It is a list of paths serialized as a JSON array.|
|`messageType`|String|The type of a message. <br>Possible option : `REPLICATION`|
|`action`|String|This is the action performed. <br>Possible option : `BulkReplicate`|
|`user`|String|The user who started the operation.|
|`result`|String|The result of the Bulk Activation. It is a serialized JSON Object: <br>`{"success":boolean,"code":integer,"message":"" }`|
|`agentId`|String|The agentId used in the replication. For example, `"publish"`.|
|`importMode`|String|Import mode used in Activation. The possible options are: <br>`REPLACE, MERGE, UPDATE`.|


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
