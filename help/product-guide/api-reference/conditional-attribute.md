---
title: REST-API zum Arbeiten mit bedingten Attributen
description: Erfahren Sie mehr über die REST-API für die Verwendung mit bedingten Attributen.
exl-id: 1f0e023a-422c-47b9-917f-b0d80090471c
feature: Rest API Conditional Attributes
role: Developer
level: Experienced
source-git-commit: 6184bb98c9897e980a6fba2f97476570228188af
workflow-type: tm+mt
source-wordcount: '147'
ht-degree: 6%

---

# REST-API zum Arbeiten mit bedingten Attributen {#id175UB30E05Z}

Mit der folgenden REST-API können Sie bedingte Attribute zu einem Ordnerprofil hinzufügen.

## Bedingtes Attribut in einem Profil auf Ordnerebene hinzufügen

Eine POST -Methode, die einem angegebenen Ordnerprofil bedingte Attribute hinzufügt.

**Anforderungs-URL**:\
http://*&lt;aem-guides-server\>*: *&lt;port-number\>*/bin/fmdita/folderprofiles

**Parameter**:

| Name | Typ | Erforderlich | Beschreibung |
|----|----|--------|-----------|
| `:operation` | Zeichenfolge | Ja | Name des aufgerufenen Vorgangs. Der Wert dieses Parameters ist ``ADDATTRIBUTEPROFILES``. <br> **Hinweis:** Beim Wert wird nicht zwischen Groß- und Kleinschreibung unterschieden. |
| `profilename` | Zeichenfolge | Ja | Anzeigename des Profils auf Ordnerebene, dem die bedingten Attribute hinzugefügt werden müssen. |
| `conditionalprofiles` | JSON-Array | Ja | Ein JSON-Array, das aus dem bedingten Attributnamen und den Werten besteht. Das folgende Beispielcodefragment zeigt das JSON-Array mit zwei Attributen - `platform` und `product` mit mehreren Werten, die ihnen zugewiesen sind. |

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
Gibt eine HTTP-Antwort 200 \(Erfolgreich\) zurück.
