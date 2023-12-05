---
title: REST-API zum Erstellen und Aktivieren von Paketen
description: Erfahren Sie mehr über die REST-API zum Erstellen und Aktivieren von Paketen
exl-id: 90686f77-a769-44bc-90eb-116cf9d0341e
source-git-commit: 5e0584f1bf0216b8b00f00b9fe46fa682c244e08
workflow-type: tm+mt
source-wordcount: '117'
ht-degree: 0%

---

# REST-API zum Erstellen und Aktivieren von Paketen {#id198CF0260Y4}

Mit der folgenden REST-API können Sie CRX-Pakete erstellen und aktivieren.

## Package erstellen und aktivieren

Eine POST-Methode, die das CRX-Paket erstellt und aktiviert.

**Anforderungs-URL**: http://*&lt;aem-guides-server>*: *&lt;port-number>*/bin/fmdita/activate

**Parameter**: Die Anforderungsabfrage besteht aus der JSON-Regelzeichenfolge. Der Inhaltstyp der POST-Anforderung muss auf `application/json; charset=UTF-8`.

**Beispiel**: Die folgenden Beispiele zeigen den API-Aufruf mithilfe des curl-Befehls:

    &quot;
    curl -u &lt;*username*>:&lt;*password*> -H &quot;Content-Type: application/json; charset=UTF-8&quot; -k -X POST -d &quot;{[JSON rules string](create-activate-package-java.md#example-create-activate-package-id198JH0B905Z)}&quot; http://&lt; em-guides-server*>:&lt;*port-number*>/bin/fmdita/activate
    &quot;
