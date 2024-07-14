---
title: REST-APIs für die Output-Verwaltung
description: Erfahren Sie mehr über REST-APIs für die Output-Verwaltung
exl-id: dab654f5-555d-4a89-bc94-55b1e938f255
feature: Rest API Output Management
role: Developer
level: Experienced
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '1175'
ht-degree: 0%

---

# REST-APIs für die Output-Verwaltung {#id175UB30E05Z}

Die folgenden REST-APIs stehen zur Verwaltung der Ausgabe in AEM Guides zur Verfügung.

## Abrufen aller Ausgabevorgaben für eine DITA-Zuordnung {#get-output-presets-dita-map}

Eine POST -Methode, die alle für eine DITA-Zuordnung konfigurierten Ausgabevorgaben abruft.

**Anforderungs-URL**:
http://*&lt;aem-guides-server\>*: *&lt;port-number\>*/bin/publishlistener

**Parameter**:\
|Name|Typ|Erforderlich|Beschreibung|
|—|—|—|—|—|
|`:operation`|String|Yes|Name des aufzurufenden Vorgangs. Der Wert dieses Parameters ist `getalloutputs`.<br> **Hinweis:** Beim Wert wird nicht zwischen Groß- und Kleinschreibung unterschieden.|
|`sourcePath`|String|Ja|Absoluter Pfad der DITA-Map-Datei.|

**Antwortwerte**:
Gibt ein Array von JSON Output Preset -Objekten zurück, von denen jedes die folgenden Elemente enthält:

| Element | Beschreibung |
|-------|-----------|
| `outputName` | Name der Ausgabevorgabe. Ausgabenamen sind im Umfang der DITA-Zuordnung, in der sie definiert sind, eindeutig. |
| `outputType` | Ausgabetyp, der mit dieser Vorgabe generiert wurde, z. B. AEM Site, PDF, EPUB oder andere. Die verfügbaren Optionen sind:<br>-   AEMSITE <br>-   PDF <br>-   HTML5 <br>-   EPUB <br> -   BENUTZERDEFINIERT |
| `outputTitle` | Ein beschreibender Name für die Ausgabevorgabeneinstellungen. Damit wird der Wert für die Eigenschaft &quot;Setting Name&quot;für die Ausgabevorgabe definiert. |
| `ditaValPathList` | Array von DITAVAL-Dateipfaden, die zum Generieren der gewünschten Ausgabe verwendet werden sollen. |
| `targetPath` | Pfad, in dem die Ausgabe veröffentlicht oder gespeichert wird. |
| `siteName` | *\(Für AEM Site-Ausgabe\)* Name der AEM Site. |
| `templatePath` | *\(Für AEM Site-Ausgabe\)* Pfad des Vorlagenknotens, der zum Generieren der gewünschten Ausgabe verwendet werden soll. |
| `searchScope` | Geben Sie den Umfang für den Suchvorgang an. Der Wert für diesen Parameter muss auf `local` gesetzt werden. |
| `generateTOC` | *\(Für AEM Site-Ausgabe\)* Geben Sie an, ob ein Inhaltsverzeichnis generiert wird \(true\) oder nicht \(false\). |
| `generateBreadcrumbs` | *\(Für AEM Site-Ausgabe\)* Geben Sie an, ob die Breadcrumbs generiert werden \(true\) oder nicht \(false\). |
| `overwriteStrategy` | *\(Für AEM Site-Ausgabe\)* Geben Sie an, ob Dateien am Ziel überschrieben werden \(true\) oder nicht \(false\). |
| `pdfGenerator` | Geben Sie die zu verwendende PDF-Generierungs-Engine an. Die möglichen Werte sind:<br>-   DITAOT <br>-   FMPS |

>[!NOTE]
>
> Das Element `DitaValPath` wird nicht mehr unterstützt.

## Ausgabevorgabe erstellen

Eine POST -Methode, die eine neue Ausgabevorgabe für eine DITA-Zuordnung erstellt.

**Anforderungs-URL**:
http://*&lt;aem-guides-server\>*: *&lt;port-number\>*/bin/publishlistener

**Parameter**:
|Name|Typ|Erforderlich|Beschreibung|
|—|—|—|—|—|
|`:operation`|String|Yes|Name des aufzurufenden Vorgangs. Der Wert dieses Parameters ist ``createoutput``.<br> **Hinweis:** Beim Wert wird nicht zwischen Groß- und Kleinschreibung unterschieden.|
|`sourcePath`|String|Ja|Absoluter Pfad der DITA-Map-Datei.|
|`outputTitle`|String|Ja|Ein beschreibender Name für die Ausgabevorgabeneinstellungen. Damit wird der Wert für die Eigenschaft &quot;Setting Name&quot;für die Ausgabevorgabe definiert.<br> **Hinweis:** Wenn eine neue Ausgabevorgabe erstellt wird, gibt das Backend-System einen eindeutigen Namen für die Ausgabevorgabe aus dem angegebenen Titel aus.|
|`outputType`|String|Ja|Ausgabetyp, der mithilfe dieser Vorgabe generiert wurde, z. B. AEM Site, PDF, EPUB oder andere. Die verfügbaren Optionen sind:<br>-   AEMSITE <br>-   PDF <br>-   HTML5 <br>-   EPUB <br> -   BENUTZERDEFINIERT|

**Antwortwerte**:
|Element|Beschreibung|
|—|—|
|`outputName`|Ein eindeutiger Name für die neu erstellte Ausgabevorgabe. Dieser Name wird aus dem Wert des Parameters `outputTitle` abgeleitet.|

## Ausgabevorgabe speichern

Eine POST-Methode, die Änderungen speichert, die an einer Ausgabevorgabe vorgenommen wurden.

**Anforderungs-URL**:
http://*&lt;aem-guides-server\>*: *&lt;port-number\>*/bin/publishlistener

**Parameter**:
|Name|Typ|Erforderlich|Beschreibung|
|—|—|—|—|—|
|`:operation`|String|Yes|Name des aufzurufenden Vorgangs. Der Wert dieses Parameters ist ``saveoutput``.<br> **Hinweis:** Beim Wert wird nicht zwischen Groß- und Kleinschreibung unterschieden.|
|`sourcePath`|String|Ja|Absoluter Pfad der DITA-Map-Datei.|
|`outputObj`|String|Ja|Ein JSON-Objekt, das Eigenschaften der zu aktualisierenden Ausgabevorgabe enthält. Die Eigenschaft `outputObj.outputName` enthält den Namen der zu aktualisierenden Ausgabevorgabe. Informationen zum Format des JSON-Objekts finden Sie in der Tabelle **Antwortwerte** in [Abrufen aller Ausgabevorgaben für eine DITA-Zuordnung](#get-output-presets-dita-map).|

**Antwortwerte**:
Gibt eine HTTP-Antwort 200 \(Erfolgreich\) zurück.

## Abrufen einer bestimmten Ausgabevorgabe

Eine POST -Methode, die eine vorhandene Ausgabevorgabe abruft.

**Anforderungs-URL**:
http://*&lt;aem-guides-server\>*: *&lt;port-number\>*/bin/publishlistener

**Parameter**:
|Name|Typ|Erforderlich|Beschreibung|
|—|—|—|—|—|
|`:operation`|String|Yes|Name des aufzurufenden Vorgangs. Der Wert dieses Parameters ist `getoutput`. <br>**Hinweis:** Beim Wert wird nicht zwischen Groß- und Kleinschreibung unterschieden.|
|`sourcePath`|String|Ja|Absoluter Pfad der DITA-Map-Datei.|
|`outputName`|String|Ja|Name der Ausgabevorgabe, für die die Details abgerufen werden müssen.|

**Antwortwerte**:
|Element|Beschreibung|
|—|—|
|`outputName`|Name der Ausgabevorgabe. Ausgabenamen sind im Umfang der DITA-Zuordnung, in der sie definiert sind, eindeutig.|
|`outputType`|Ausgabetyp, der mit dieser Vorgabe generiert wurde, z. B. AEM Site, PDF, EPUB oder andere. Die verfügbaren Optionen sind:<br>-   AEMSITE <br>-   PDF <br>-   HTML5 <br>-   EPUB <br> -   BENUTZERDEFINIERTER <br>|
|`outputTitle`|Ein beschreibender Name für die Ausgabevorgabeneinstellungen. Damit wird der Wert für die Eigenschaft &quot;Setting Name&quot;für die Ausgabevorgabe definiert.|
|`ditaValPathList`|Array von DITAVAL-Dateipfaden, die zum Generieren der gewünschten Ausgabe verwendet werden sollen.|
|`targetPath`|Pfad, in dem die Ausgabe veröffentlicht oder gespeichert wird.|
|`siteName`|\(Für AEM Site-Ausgabe\) Name der AEM Site.|
|`siteTitle`|\(Für AEM Site-Ausgabe\) Titel der AEM Site.|
|`templatePath`|\(Für AEM Site-Ausgabe\) Pfad des Vorlagenknotens, der zum Generieren der gewünschten Ausgabe verwendet werden soll.|
|`searchScope`|Geben Sie den Perimeter für den Suchvorgang an. Der Wert für diesen Parameter muss auf `local` gesetzt werden.|
|`generateTOC`|\(Für AEM Site-Ausgabe\) Geben Sie an, ob ein Inhaltsverzeichnis generiert wird \(true\) oder nicht \(false\).|
|`generateBreadcrumbs`|\(Für AEM Site-Ausgabe\) Geben Sie an, ob die Breadcrumbs generiert werden \(true\) oder nicht \(false\).|
|`overwriteFiles`|\(Für AEM Site-Ausgabe\) Geben Sie an, ob Dateien am Ziel überschrieben werden \(true\) oder nicht \(false\).|
|`pdfGenerator`|Geben Sie die zu verwendende PDF-Generierungs-Engine an. Die möglichen Werte sind:<br>-   DITAOT <br>-   FMPS|

>[!NOTE]
>
> Das Element `DitaValPath` wird nicht mehr unterstützt.

## Ausgabe generieren

Eine GET-Methode, die die Ausgabe mithilfe einer oder mehrerer Ausgabevorgaben generiert.

**Anforderungs-URL**:
http://*&lt;aem-guides-server\>*: *&lt;port-number\>*/bin/publishlistener

**Parameter**:
|Name|Typ|Erforderlich|Beschreibung|
|—|—|—|—|—|
|`operation`|String|Yes|Name des aufzurufenden Vorgangs. Der Wert dieses Parameters ist `GENERATEOUTPUT`.<br> **Hinweis:** Beim Wert wird zwischen Groß- und Kleinschreibung unterschieden.|
|`source`|String|Ja|Absoluter Pfad der DITA-Map-Datei.|
|`outputName`|String|Ja|Name der Ausgabevorgabe\(n\), die zum Generieren der Ausgabe verwendet werden soll. Mehrere Ausgabevorgaben können mit einem senkrechten Strich (&quot;\|&quot;\) angegeben werden, z. B. `aemsite|pdfoutput`.|

**Antwortwerte**:
Gibt eine HTTP-Antwort 200 \(Erfolgreich\) zurück.

## Inkrementelle Ausgabe generieren

Eine GET-Methode, die mithilfe einer oder mehrerer Ausgabevorgaben eine inkrementelle Ausgabe für eine AEM Site generiert.

**Anforderungs-URL**:
http://*&lt;aem-guides-server\>*: *&lt;port-number\>*/bin/publishlistener

**Parameter**:
|Name|Typ|Erforderlich|Beschreibung|
|—|—|—|—|—|
|`operation`|String|Yes|Name des aufzurufenden Vorgangs. Der Wert dieses Parameters ist `INCREMENTALPUBLISH`. <br>**Hinweis:** Beim Wert wird zwischen Groß- und Kleinschreibung unterschieden.|
|`contentPath`|JSON|Ja|Absoluter Pfad der DITA-Map-Datei und Themendateien zusammen mit dem Namen der Ausgabevorgaben. Verwenden Sie das folgende Beispiel als Baustein:|

```XML
{
   {   
   "ditamap": 
      "/content/dam/sample/sample.ditamap",   
   "topics": [     
      "/content/dam/sample/topic1.xml",     
      "/content/dam/sample/topic2.xml"   
         ],   
   "fullMaps": [     
      "/content/dam/sample/submap.ditamap"   
      ],   
   "maps": [     
      "/content/dam/sample/keyspace.ditamap"   
      ],   
   "outputs": [     
      "aemsite"   
      ] 
   }
}
```

- Das Attribut `ditamap` nimmt den absoluten Pfad der DITA-Zuordnung an, die zum Generieren der Ausgabe verwendet wird.
- Das Attribut `topics` akzeptiert eine Reihe von Themen, die aktualisiert werden und erneut veröffentlicht werden müssen.
- Das Attribut `fullMaps` enthält den Pfad der Zuordnungsdateien \(z. B. chunked submaps\), die zusammen mit ihren Themen für die inkrementelle Ausgabegenerierung benötigt werden.
- Das Attribut `maps` enthält den Pfad der Zuordnungsdateien \(zum Auflösen von Keyspace-Referenzen\), die ohne Themen auf der Festplatte extrahiert werden.
- Das Attribut `outputs` akzeptiert ein Array von Vorgabenamen, die zum Generieren der Ausgabe verwendet werden.

**Antwortwerte**:
Gibt eine HTTP-Antwort 200 \(Erfolgreich\) zurück.

## Ausgabevorgabe löschen

Eine POST-Methode zum Löschen einer Ausgabevorgabe.

**Anforderungs-URL**:
http://*&lt;aem-guides-server\>*: *&lt;port-number\>*/bin/publishlistener

**Parameter**:
|Name|Typ|Erforderlich|Beschreibung|
|—|—|—|—|—|
|`:operation`|String|Yes|Name des aufzurufenden Vorgangs. Der Wert dieses Parameters ist `deleteoutput`.<br> **Hinweis:** Beim Wert wird nicht zwischen Groß- und Kleinschreibung unterschieden.|
|`sourcePath`|String|Ja|Absoluter Pfad der DITA-Map-Datei.|
|`outputName`|String|Ja|Name der zu löschenden Ausgabevorgabe.|

**Antwortwerte**:
Gibt eine HTTP-Antwort 200 \(Erfolgreich\) zurück.
