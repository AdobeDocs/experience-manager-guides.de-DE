---
title: REST-API zum Erstellen und Aktivieren von Paketen
description: Informationen zur REST-API zum Erstellen und Aktivieren von Paketen
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

## Paket erstellen und aktivieren

Eine Paketmethode, die ein CRX-POST erstellt und aktiviert.

**Anfrage-URL**:
http://*&lt;aem-guides-server\>*: *&lt;port-number\>*/bin/fmdita/activate

**Parameter**:
Die Anfrageabfrage besteht aus der JSON-Regelzeichenfolge. Der Content-Typ der POST-Anfrage muss auf `application/json; charset=UTF-8` festgelegt werden.

**Beispiel**:
Das folgende Beispiel zeigt den API-Aufruf mit dem curl-Befehl:

```XML
curl -u <*username*>:<*password*> -H "Content-Type: application/json; charset=UTF-8"  -k -X POST -d "{[JSON rules string](create-activate-package-java.md#example-create-activate-package-id198JH0B905Z)}" http://<*aem-guides-server*>:<*port-number*>/bin/fmdita/activate
```


**Optionaler Parameter**

`activationTarget`

**Gültige Werte**

`preview` oder `publish` für Cloud Service und `publish` für On-Premise-Software

- Wenn der -Parameter einen ungültigen Wert enthält, schlägt die Paketaktivierung bei einem Cloud Service fehl.

- Wenn bei On-Premise-Software der Parameter einen ungültigen Wert enthält, wird der Fehler protokolliert und die Veröffentlichung erfolgt mit dem Standardwert `publish`.

Wenn Sie `activationTarget` keinen optionalen Parameter definieren, wird er über den Standardagenten für die Veröffentlichung sowohl für Cloud Service- als auch für On-Premise-Software aktiviert.



Das folgende Beispiel zeigt den API-Aufruf mit dem curl-Befehl mit optionalem Parameter:


    „XML
    
    curl -u &lt;*username*>:&lt;*password*> -H „Content-Type: application/json; charset=UTF-8“ -k -X POST -d &quot;{[JSON rules string](create-activate-package-java.md#example-create-activate-package-id198JH0B905Z)}&quot; http://&lt;*aem-guides-server*>:&lt;*port-number*>/bin/fmdita/activate?activationTarget=`&lt;validActivationTargetValue>`
     
