---
title: Java-basierte API zum Erstellen und Aktivieren von Paketen
description: Erfahren Sie mehr über die Java-basierte API zum Erstellen und Aktivieren von Paketen
exl-id: b801c2b3-445f-4aa7-a4f2-029563d7cb3a
feature: Java-Based API Packages
role: Developer
level: Experienced
TQID: https://experienceleague.adobe.com/g5Mp7tMM9JaAYwNmMyPmaFEcI0fx66vrX8ry97lIUF8
product_v2: id: fae5e35a-80c9-4b94-9352-1a060a6aab1did: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2: id: a01bfd36-4ab8-4bf8-9dc0-5b45b890552eid: a3bd6397-2eb2-4908-a61c-226e26855dcaid: c6d09140-3c91-45d3-b7ed-b681af752f43
role_v2: id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 618
ht-degree: 1%

---

# Java-basierte API zum Erstellen und Aktivieren von Paketen {#id175UB30E05Z}

>[!NOTE]
>
> Sie können die in Experience Manager Guides verfügbaren Java-basierten APIs verwenden, um benutzerdefinierte Plug-ins zu erstellen und vordefinierte Workflows zu erweitern. Dieser Artikel wird im November 2024 archiviert.
> In [![javadoc](https://javadoc.io/badge2/com.adobe.aem/aem-guides-sdk-api/javadoc.svg)](https://javadoc.io/doc/com.adobe.aem/aem-guides-sdk-api) finden Sie die neueste und detaillierte Dokumentation zur Verwendung der Java-basierten API.


Mit der folgenden Java-basierten API können Sie CRX-Pakete erstellen und aktivieren. Diese API ist in Form eines Bundles verfügbar. Sie müssen dieses Bundle in Ihren Code aufnehmen, um diese APIs verwenden zu können.

Paketdetails:

- Gruppen-ID: **com.adobe.fmdita**

- Artefakt-ID: **api**

- Version: **.3**

- Paket: **com.adobe.fmdita.api.crxactivate**

- Klassendetails:

  ```JAVA
  public class CRXActivator
  ```

  Die **`CRXActivator`**-Klasse enthält eine Methode zum Erstellen von CRX-Paketen und zum Replizieren derselben auf der Veröffentlichungsinstanz.


## Erstellen und Aktivieren von Paketen

Die `activate` Methode erstellt ein CRX-Paket auf der Autoreninstanz und repliziert es bei Bedarf auf der Veröffentlichungsinstanz. Es wird davon ausgegangen, dass die AEM-Replikationsparameter bereits in der Autoreninstanz eingerichtet wurden. Diese Methode erstellt das CRX-Paket basierend auf einer Liste von Regeln, die als Eingabeparameter in einer JSON-Zeichenfolge bereitgestellt werden.
>[!NOTE]
>
> Fehler, die während des Erstellungs- oder Aktivierungsprozesses auftreten, werden in die `outputstream` geschrieben.

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

### Beispiel mit optionalem dritten Parameter

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

| Name | Typ | Beschreibung |
|----|----|-----------|
| `json` | Zeichenfolge | JSON-String, der das zu erstellende CRX-Paket bestimmt. Verwenden Sie das folgende Format, um die JSON-Zeichenfolge zu erstellen: <br>- `activate`: Ist vom Typ Boolescher Wert \(`true`/`false`\). Bestimmt, ob das in der Autoreninstanz erstellte CRX-Paket auf der Veröffentlichungsinstanz repliziert wird. <br> - `rules`: Ist vom Typ JSON-Array. Ein Array von JSON-Regeln, die sequenziell verarbeitet werden, um das CRX-Paket zu erstellen. <br> - `rootPath`: Ist vom Typ Zeichenfolge. Der Basispfad, auf dem die Knoten-/Eigenschaftsabfragen ausgeführt werden. Wenn keine Knoten-/Eigenschaftsabfragen vorhanden sind, werden der Stammpfad und alle unter dem Stammpfad vorhandenen Knoten in das CRX-Paket aufgenommen. <br> - `nodeQueries`: Ist vom Typ Regex-Array. Ein Array von regulären Ausdrücken, die verwendet werden, um bestimmte Dateien unter dem Stammpfad einzuschließen. <br> - `propertyQueries`: Ist vom Typ JSON-Array. Ein Array von JSON-Objekten, wobei jedes JSON-Objekt aus einer XPath-Abfrage besteht, die auf dem Stammpfad ausgeführt werden soll, und dem Namen einer Eigenschaft, die in jedem JCR-Knoten nach der Ausführung der Abfrage vorhanden ist. Der Wert der -Eigenschaft in jedem JCR-Knoten sollte ein Pfad oder ein Array von Pfaden sein. Die in dieser Eigenschaft vorhandenen Pfade werden dem CRX-Paket hinzugefügt. |
| `outputstream` | java.io.OutputStream | Dies wird verwendet, um das Ergebnis verschiedener Phasen zu schreiben, z. B. die Ausführung von Abfragen, die Dateieinbindung, die Erstellung von CRX-Paketen oder die Aktivierung. Alle Fehler, die während des Erstellungs- oder Aktivierungsprozesses auftreten, werden in die `outputstream` geschrieben. Dies ist für das Debugging nützlich. |
| `session` | Zeichenfolge | Eine gültige JCR-Sitzung mit Aktivierungsberechtigung. |
| `activationTarget` | Zeichenfolge | (*Optional*) `preview` oder `publish` für Cloud Service und `publish` für On-Premise-Software-<br> - Wenn der Parameter einen ungültigen Wert enthält, schlägt die Paketaktivierung bei Cloud Service fehl. <br> : Wenn der Parameter für die On-Premise-Software einen ungültigen Wert enthält, wird der Fehler protokolliert und die Veröffentlichung erfolgt mit dem Standardwert `publish`. |

**Ausnahme**:

Löst `java.io.IOException` und `java.io.IllegalArgumentException` aus


Wenn Sie `activationTarget` den optionalen Parameter nicht definieren, wird er über den standardmäßigen Veröffentlichungsagenten für Cloud Service und On-Premise-Software aktiviert.


**Beispiel**:
Das folgende Beispiel zeigt, wie Sie eine JSON-Abfrage erstellen:

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

- Nur die Bilder .png, .jpg und .gif unter dem Pfad /content/dam/nested sind im Paket enthalten.
- Alle Knoten unter /content/output/sites/hierarchy\_ditamap sind im Paket enthalten.
- Die Pfade in der `fileReference` Eigenschaft der Knoten unter /content/output/sites/hierarchy\_ditamap sind im Paket enthalten.
