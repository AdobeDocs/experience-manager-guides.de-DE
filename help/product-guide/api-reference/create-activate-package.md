---
title: REST-API zum Erstellen und Aktivieren von Paketen
description: Erfahren Sie mehr über die REST-API zum Erstellen und Aktivieren von Paketen
exl-id: 90686f77-a769-44bc-90eb-116cf9d0341e
feature: Rest API Packages
role: Developer
level: Experienced
source-git-commit: b95a64ca2e8ebffebec3d8ff8704f76f7faceca2
workflow-type: tm+mt
source-wordcount: '205'
ht-degree: 0%

---

# REST-API zum Erstellen und Aktivieren von Paketen {#id198CF0260Y4}

Mit der folgenden REST-API können Sie CRX-Pakete erstellen und aktivieren.

## Package erstellen und aktivieren

Eine POST-Methode, die das CRX-Package erstellt und aktiviert.

**Anforderungs-URL**:
http://*&lt;aem-guides-server\>*: *&lt;port-number\>*/bin/fmdita/activate

**Parameter**:
Die Anfrage-Abfrage besteht aus der JSON-Regelzeichenfolge. Der Inhaltstyp der POST-Anforderung muss auf `application/json; charset=UTF-8` gesetzt sein.

**Beispiel**:
Das folgende Beispiel zeigt den API-Aufruf mit dem curl-Befehl:

```XML
curl -u <*username*>:<*password*> -H "Content-Type: application/json; charset=UTF-8"  -k -X POST -d "{[JSON rules string](create-activate-package-java.md#example-create-activate-package-id198JH0B905Z)}" http://<*aem-guides-server*>:<*port-number*>/bin/fmdita/activate
```


**Optionaler Parameter**

`activationTarget`

**Gültige Werte**

`preview` oder `publish` für Cloud Service und `publish` für On-Premise-Software

- Wenn zum Cloud Service der Parameter einen ungültigen Wert enthält, schlägt die Paketaktivierung fehl.

- Wenn der Parameter für On-Premise-Software einen ungültigen Wert enthält, wird der Fehler protokolliert und die Veröffentlichung erfolgt mit dem Standardwert `publish`.

Wenn Sie den optionalen Parameter &quot;`activationTarget`&quot; nicht definieren, wird sowohl für Cloud Service- als auch für On-Premise-Software der standardmäßige Veröffentlichungsagent verwendet.



Das folgende Beispiel zeigt den API-Aufruf mit dem Befehl curl mit dem optionalen Parameter :


    &quot;XML
    
    curl -u &lt;*username*>:&lt;*password*> -H &quot;Content-Type: application/json; charset=UTF-8&quot; -k -X POST -d &quot;{[JSON rules string](create-activate-package-java.md#example-create-activate-package-id198JH0B905Z)}&quot; http://&lt;*aem-guides-server*>:&lt;*port-number*>/bin/fmdita/activate?activationTarget=`&lt;validActivationTargetValue>`
    &quot;
