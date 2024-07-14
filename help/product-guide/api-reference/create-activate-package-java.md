---
title: Java-basierte API zum Erstellen und Aktivieren von Paketen
description: Informationen zur Java-basierten API zum Erstellen und Aktivieren von Paketen
exl-id: b801c2b3-445f-4aa7-a4f2-029563d7cb3a
feature: Java-Based API Packages
role: Developer
level: Experienced
source-git-commit: 4ce78061ddb193d3c16241ff32fa87060c9c7bd6
workflow-type: tm+mt
source-wordcount: '550'
ht-degree: 0%

---

# Java-basierte API zum Erstellen und Aktivieren von Paketen {#id175UB30E05Z}

Mit der folgenden Java-basierten API können Sie CRX-Pakete erstellen und aktivieren. Diese API ist in Form eines Bundles verfügbar. Sie müssen dieses Bundle in Ihren Code aufnehmen, um diese APIs verwenden zu können.

Paketdetails:

- Gruppen-ID: **com.adobe.fmdita**

- Artefakt-ID: **api**

- Version: **3.3**

- Paket: **com.adobe.fmdita.api.crxactivate**

- Klassendetails:

  ```JAVA
  public class CRXActivator
  ```

  Die Klasse **`CRXActivator`** enthält eine Methode zum Erstellen von CRX-Paketen und zum Replizieren dieser auf der Veröffentlichungsinstanz.


## Packages erstellen und aktivieren

Die Methode `activate` erstellt ein CRX-Paket auf der Autoreninstanz und repliziert es gegebenenfalls auf der Veröffentlichungsinstanz. Es wird davon ausgegangen, dass die AEM Replikationsparameter bereits in der Autoreninstanz eingerichtet wurden. Diese Methode erstellt das CRX-Paket basierend auf einer Liste von Regeln, die als Eingabeparameter in einer JSON-Zeichenfolge bereitgestellt werden.
>[!NOTE]
>
> Während des Erstellungs- oder Aktivierungsprozesses aufgetretene Fehler werden in `outputstream` geschrieben.

### Beispiel mit zwei Parametern

**Syntax**:


```JAVA
public static void activate
(
  String json, 
  OutputStream outputstream, 
  Session session
) 
throws GuidesApiException
```

### Beispiel mit drittem optionalen Parameter

```JAVA
public static void activate
(
  String json, 
  OutputStream outputstream,
  String activationTarget, 
  Session session
) 
throws GuidesApiException
```

**Parameter**:
|Name|Typ|Beschreibung|
|—|—|—|
|`json`|String|JSON-Zeichenfolge, die das zu erstellende CRX-Paket bestimmt. Verwenden Sie das folgende Format, um die JSON-Zeichenfolge zu erstellen: <br> - `activate`: Ist vom Typ Boolesch \(`true`/`false`\). Bestimmt, ob das in der Autoreninstanz erstellte CRX-Package auf die Veröffentlichungsinstanz repliziert wird. <br> - `rules`: Ist vom Typ JSON-Array. Ein Array von JSON-Regeln, die nacheinander verarbeitet werden, um das CRX-Paket zu erstellen. <br> - `rootPath`: Ist vom Typ String. Der Basispfad, auf dem die Knoten-/Eigenschaftenabfragen ausgeführt werden. Wenn keine Knoten-/Eigenschaftenabfragen vorhanden sind, werden der Stammpfad und alle Knoten, die unter dem Stammpfad vorhanden sind, in das CRX-Paket aufgenommen. <br> - `nodeQueries`: Ist vom Typ Regex-Array. Ein Array von regulären Ausdrücken, die verwendet werden, um bestimmte Dateien unter dem Stammpfad einzuschließen. <br> - `propertyQueries`: Ist vom Typ JSON-Array. Ein Array von JSON-Objekten mit jedem JSON-Objekt, das aus einer XPath-Abfrage besteht, die auf dem Stammpfad ausgeführt werden soll, und dem Namen einer Eigenschaft, die in jedem JCR-Knoten vorhanden ist, nachdem die Abfrage ausgeführt wurde. Der Wert der Eigenschaft in jedem JCR-Knoten sollte ein Pfad oder ein Array von Pfaden sein. Die in dieser Eigenschaft vorhandenen Pfade werden dem CRX-Paket hinzugefügt.|
|`outputstream`|java.io.OutputStream|Dies wird verwendet, um das Ergebnis verschiedener Phasen zu schreiben, z. B. Abfrageausführung, Dateieinbindung, Erstellung von CRX-Paketen oder Aktivierung. Jeder Fehler, der beim Erstellen oder Aktivieren auftritt, wird in den `outputstream` geschrieben. Dies ist für das Debugging nützlich.|
|`session`|String|Eine gültige JCR-Sitzung mit Aktivierungsberechtigung.|
|`activationTarget`|String|(*Optional*) `preview` oder `publish` für Cloud Service und `publish` für On-Premise-Software <br> - Wenn der Parameter einen ungültigen Wert enthält, schlägt die Paketaktivierung fehl. <br> - Bei On-Premise-Software wird der Fehler protokolliert, wenn der Parameter einen ungültigen Wert enthält, und die Veröffentlichung erfolgt mit dem Standardwert `publish`. |

**Exception**:

Gibt `java.io.IOException` und `java.io.IllegalArgumentException` aus


Wenn Sie den optionalen Parameter &quot;`activationTarget`&quot; nicht definieren, wird sowohl für Cloud Service- als auch für On-Premise-Software der standardmäßige Veröffentlichungsagent verwendet.


**Beispiel**:
Das folgende Beispiel zeigt, wie eine JSON-Abfrage erstellt wird:

```JSON
{
  "activate": true,
  "rules": [
    {
      "rootPath": "/content/dam/nested",
      "nodeQueries": [
        ".*\\.jpg",
        ".*\\.png",
        ".*\\.gif"        
      ]
    },
    {
      "rootPath": "/content/output/sites/hierarchy_ditamap"
    },
    {
      "rootPath": "/content/output/sites/hierarchy_ditamap",
      "propertyQueries": [
        {
          "query": "//*[@fileReference]",
          "property": "fileReference"
        }
      ]
    }
  ]
}
```

Die JSON-Beispielabfrage besteht aus den folgenden Regeln:

- Nur die Bilder .png, .jpg und .gif unter /content/dam/nested werden in das Paket aufgenommen.
- Alle Knoten unter /content/output/sites/hierarchy\_ditamap sind im Paket enthalten.
- Die Pfade, die in der Eigenschaft `fileReference` von Knoten unter /content/output/sites/hierarchy\_ditamap vorhanden sind, sind im Paket enthalten.
