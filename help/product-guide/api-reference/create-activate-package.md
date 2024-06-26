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

## Paket Erstellen und aktivieren

Ein POST-Methode, das das CRX-Paket erstellt und aktiviert.

**URL** anfordern:
http://*&lt;aem-guides-server\>*: *&lt;port-number\>*/bin/fmdita/activate&lt;/port-number\>&lt;/aem-guides-server\>

**Parameter**:
Die Anfrage Abfrage besteht aus der Zeichenfolge der JSON-Regeln. Die Content-Typ der POST-Anfrage muss auf eingestellt sein.`application/json; charset=UTF-8`

**Beispiel**:
Das folgende Beispiel zeigt den API-Aufruf mithilfe des cURL-Befehls:

```XML
curl -u <*username*>:<*password*> -H "Content-Type: application/json; charset=UTF-8"  -k -X POST -d "{[JSON rules string](create-activate-package-java.md#example-create-activate-package-id198JH0B905Z)}" http://<*aem-guides-server*>:<*port-number*>/bin/fmdita/activate
```


**Optionaler Parameter**

`activationTarget`

**Gültige Werte**

`preview` oder `publish` für Cloud Service und `publish` für On-Premise-Software

- Wenn der Parameter zum Cloud Service einen ungültig-Wert enthält, schlägt das Paket Aktivierung fehl.

- Wenn bei On-Premise-Software der Parameter einen ungültig-Wert enthält, wird der Fehler protokolliert, und die Veröffentlichung erfolgt mit dem Standardwert `publish`.

Wenn Sie den optionalen Parameter nicht definieren, `activationTarget`wird er unter Verwendung des standardmäßigen veröffentlichen Agenten sowohl für Cloud Service als auch für On-Premise-Software aktiviert.



Das folgende Beispiel zeigt den API-Aufruf mithilfe des curl-Befehls mit optionalem Parameter:


    &#39;&#39;&#39;XML
    
    curl -u &lt;*username*>:&lt;*password*> -H &quot;Inhaltstyp: Applikation/json; charset=UTF-8&quot; -k -X POST -d &quot;{[JSON-Regelzeichenfolge](create-activate-package-java.md#example-create-activate-package-id198JH0B905Z)}&quot; http://&lt;*aem-guides-server*>:&lt;*port-number*>/bin/fmdita/activate?activationTarget=&#39;&lt;validActivationTargetValue>&#39;
    &#39;&#39;&#39;
&lt;/validActivationTargetValue>&lt;/*port-number*>&lt;/*aem-guides-server*>&lt;/*password*>&lt;/*username*>