---
title: REST-API für die Arbeit mit bedingten Attributen
description: Informationen zur REST-API für die Arbeit mit bedingten Attributen
exl-id: 1f0e023a-422c-47b9-917f-b0d80090471c
feature: Rest API Conditional Attributes
role: Developer
level: Experienced
source-git-commit: 6e23f52fc9124d0f07f8108da1b5fe574f553469
workflow-type: tm+mt
source-wordcount: '147'
ht-degree: 6%

---

# REST-API für die Arbeit mit bedingten Attributen {#id175UB30E05Z}

Mit der folgenden REST-API können Sie bedingte Attribute in einem Ordnerprofil hinzufügen.

## Hinzufügen eines bedingten Attributs in einem Profil auf Ordnerebene

Eine POST-Methode, die einem bestimmten Profil auf Ordnerebene bedingte Attribute hinzufügt.

**Anfrage-URL**:\
http://*<aem-guides-server\>*: *<port-number\>*/bin/fmdita/folderprofiles

**Parameter**:

| Name | Typ | Erforderlich | Beschreibung |
|----|----|--------|-----------|
| `:operation` | Zeichenfolge | Ja | Name des aufzurufenden Vorgangs. Der Wert dieses Parameters ist ``ADDATTRIBUTEPROFILES``. <br> **Hinweis:** Beim Wert wird nicht zwischen Groß- und Kleinschreibung unterschieden. |
| `profilename` | Zeichenfolge | Ja | Anzeigename des Profils auf Ordnerebene, in dem die bedingten Attribute hinzugefügt werden müssen. |
| `conditionalprofiles` | JSON-Array | Ja | Ein JSON-Array, das aus dem Namen und den Werten des bedingten Attributs besteht. Das folgende Codebeispiel zeigt das JSON-Array mit zwei Attributen: `platform` und `product` mit mehreren Werten, die ihnen zugewiesen sind. |

```JSON
[  {    name: "platform",    
        values: [       
                {value: "win", label: "Windows"},       
                {value: "mac", label: "Mac OS"}    
                ]},
                {    
                    name: "product",    
                    values: [      
                        {value: "aem_1", label: "AEM 6.1"},     
                        {value: "aem_4,  label: "AEM 6.4"}  
                        ]  
                }]
```

**Antwortwerte**:\
Gibt eine HTTP-Antwort 200 \(erfolgreich\) zurück.
