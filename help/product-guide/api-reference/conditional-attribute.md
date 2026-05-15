---
title: REST-API für die Arbeit mit bedingten Attributen
description: Informationen zur REST-API für die Arbeit mit bedingten Attributen
exl-id: 1f0e023a-422c-47b9-917f-b0d80090471c
feature: Rest API Conditional Attributes
role: Developer
level: Experienced
TQID: https://experienceleague.adobe.com/qtmJN6jjCm3xeNYAaHTWr7G3SZFSOodcVqBOKctR3B8
product_v2: id: fae5e35a-80c9-4b94-9352-1a060a6aab1did: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2: id: a01bfd36-4ab8-4bf8-9dc0-5b45b890552eid: c6d09140-3c91-45d3-b7ed-b681af752f43
subfeature_v2: id: d27d524e-c4e5-4b77-b86b-3db049db0b25
role_v2: id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 154
ht-degree: 5%

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
