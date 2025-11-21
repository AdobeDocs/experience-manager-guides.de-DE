---
title: REST-APIs für die Ausgabeverwaltung
description: Informationen zu REST-APIs für die Ausgabeverwaltung
exl-id: dab654f5-555d-4a89-bc94-55b1e938f255
feature: Rest API Output Management
role: Developer
level: Experienced
source-git-commit: 6e23f52fc9124d0f07f8108da1b5fe574f553469
workflow-type: tm+mt
source-wordcount: '1175'
ht-degree: 6%

---

# REST-APIs für die Ausgabeverwaltung {#id175UB30E05Z}

Die folgenden REST-APIs sind für die Verwaltung der Ausgabe in AEM Guides verfügbar.

## Abrufen aller Ausgabevorgaben für eine DITA-Zuordnung {#get-output-presets-dita-map}

Eine POST-Methode, die alle für eine DITA-Zuordnung konfigurierten Ausgabevorgaben abruft.

**Anfrage-URL**:
http://*&lt;aem-guides-server\>*: *&lt;port-number\>*/bin/publishlistener

**Parameter**:

| Name | Typ | Erforderlich | Beschreibung |
|----|----|--------|-----------|
| `:operation` | Zeichenfolge | Ja | Name des aufzurufenden Vorgangs. Der Wert dieses Parameters ist `getalloutputs`.<br> **Hinweis:** Beim Wert wird nicht zwischen Groß- und Kleinschreibung unterschieden. |
| `sourcePath` | Zeichenfolge | Ja | Absoluter Pfad der DITA-Zuordnungsdatei. |

**Antwortwerte**:
Gibt ein Array von JSON-Ausgabevoreinstellungsobjekten zurück, wobei jedes Objekt die folgenden Elemente enthält:

| Element | Beschreibung |
|-------|-----------|
| `outputName` | Name der Ausgabevorgabe. Ausgabenamen sind im Gültigkeitsbereich der DITA-Zuordnung, in der sie definiert sind, eindeutig. |
| `outputType` | Typ der Ausgabe, die mit dieser Vorgabe generiert wird, z. B. AEM Site, PDF, EPUB oder andere. Die verfügbaren Optionen sind: <br>-   AEMSITE <br>-   PDF <br>-   HTML5 <br>-   EPUB <br>-   BENUTZERDEFINIERT |
| `outputTitle` | Ein beschreibender Name für die Ausgabevoreinstellungen. Damit wird der Wert für die Eigenschaft Name der Einstellung für die Ausgabevorgabe definiert. |
| `ditaValPathList` | Array von DITAVAL-Dateipfaden, die zur Generierung der gewünschten Ausgabe verwendet werden sollen. |
| `targetPath` | Pfad, in dem die Ausgabe veröffentlicht oder gespeichert wird |
| `siteName` | *\(Für AEM-Site-Ausgabe\)* Name der AEM-Site. |
| `templatePath` | *\(For AEM Site output\)* Pfad des Vorlagenknotens, der zum Generieren der gewünschten Ausgabe verwendet werden soll. |
| `searchScope` | Geben Sie den Umfang für den Suchvorgang an. Der Wert für diesen Parameter muss auf `local` gesetzt werden. |
| `generateTOC` | *\(Für AEM-Site-Ausgabe\)* Geben Sie an, ob ein Inhaltsverzeichnis generiert wird \(true\) oder nicht \(false\). |
| `generateBreadcrumbs` | *\(Für AEM-Site-Ausgabe\)* Geben Sie an, ob die Breadcrumbs generiert werden \(true\) oder nicht \(false\). |
| `overwriteStrategy` | *\(Für AEM-Site-Ausgabe\)* Geben Sie an, ob Dateien am Ziel überschrieben werden \(true\) oder nicht \(false\). |
| `pdfGenerator` | Geben Sie die zu verwendende PDF-Erzeugungsmaschine an. Die möglichen Werte sind: <br>-   DITAOT <br>-   FMPS |

>[!NOTE]
>
> `DitaValPath` Element wird nicht mehr unterstützt.

## Ausgabevorgabe erstellen

Eine POST-Methode, die eine neue Ausgabevorgabe für eine DITA-Zuordnung erstellt.

**Anfrage-URL**:
http://*&lt;aem-guides-server\>*: *&lt;port-number\>*/bin/publishlistener

**Parameter**:

| Name | Typ | Erforderlich | Beschreibung |
|----|----|--------|-----------|
| `:operation` | Zeichenfolge | Ja | Name des aufzurufenden Vorgangs. Der Wert dieses Parameters ist ``createoutput``.<br> **Hinweis:** Beim Wert wird nicht zwischen Groß- und Kleinschreibung unterschieden. |
| `sourcePath` | Zeichenfolge | Ja | Absoluter Pfad der DITA-Zuordnungsdatei. |
| `outputTitle` | Zeichenfolge | Ja | Ein beschreibender Name für die Ausgabevoreinstellungen. Damit wird der Wert für die Eigenschaft Name der Einstellung für die Ausgabevorgabe definiert.<br> **Hinweis:** Wenn eine neue Ausgabevorgabe erstellt wird, steuert das Backend-System einen eindeutigen Namen für die Ausgabevorgabe aus dem angegebenen Titel. |
| `outputType` | Zeichenfolge | Ja | Typ der Ausgabe, die mit dieser Vorgabe generiert wird, z. B. AEM Site, PDF, EPUB oder andere. Die verfügbaren Optionen sind: <br>-   AEMSITE <br>-   PDF <br>-   HTML5 <br>-   EPUB <br>-   BENUTZERDEFINIERT |

**Antwortwerte**:

| Element | Beschreibung |
|-------|-----------|
| `outputName` | Ein eindeutiger Name für die neu erstellte Ausgabevorgabe. Dieser Name wird aus dem Wert des `outputTitle` abgeleitet. |

## Ausgabevorgabe speichern

Eine POST-Methode, die Änderungen speichert, die an einer Ausgabevorgabe vorgenommen wurden.

**Anfrage-URL**:
http://*&lt;aem-guides-server\>*: *&lt;port-number\>*/bin/publishlistener

**Parameter**:

| Name | Typ | Erforderlich | Beschreibung |
|----|----|--------|-----------|
| `:operation` | Zeichenfolge | Ja | Name des aufzurufenden Vorgangs. Der Wert dieses Parameters ist ``saveoutput``.<br> **Hinweis:** Beim Wert wird nicht zwischen Groß- und Kleinschreibung unterschieden. |
| `sourcePath` | Zeichenfolge | Ja | Absoluter Pfad der DITA-Zuordnungsdatei. |
| `outputObj` | Zeichenfolge | Ja | Ein JSON-Objekt, das Eigenschaften der Ausgabevorgabe enthält, die aktualisiert wird. Die `outputObj.outputName`-Eigenschaft enthält den Namen der Ausgabevorgabe, die aktualisiert werden soll. Informationen zum Format des JSON-Objekts finden Sie in der Tabelle **Antwortwerte** in [Abrufen aller Ausgabevorgaben für eine DITA-Zuordnung](#get-output-presets-dita-map). |

**Antwortwerte**:
Gibt eine HTTP-Antwort 200 \(erfolgreich\) zurück.

## Abrufen einer bestimmten Ausgabevorgabe

Eine POST-Methode, die eine vorhandene Ausgabevorgabe abruft.

**Anfrage-URL**:
http://*&lt;aem-guides-server\>*: *&lt;port-number\>*/bin/publishlistener

**Parameter**:

| Name | Typ | Erforderlich | Beschreibung |
|----|----|--------|-----------|
| `:operation` | Zeichenfolge | Ja | Name des aufzurufenden Vorgangs. Der Wert dieses Parameters ist `getoutput`. <br>**Hinweis:** Beim Wert wird nicht zwischen Groß- und Kleinschreibung unterschieden. |
| `sourcePath` | Zeichenfolge | Ja | Absoluter Pfad der DITA-Zuordnungsdatei. |
| `outputName` | Zeichenfolge | Ja | Name der Ausgabevorgabe, für die die Details abgerufen werden müssen. |

**Antwortwerte**:

| Element | Beschreibung |
|-------|-----------|
| `outputName` | Name der Ausgabevorgabe. Ausgabenamen sind im Gültigkeitsbereich der DITA-Zuordnung, in der sie definiert sind, eindeutig. |
| `outputType` | Typ der Ausgabe, die mit dieser Vorgabe generiert wird, z. B. AEM Site, PDF, EPUB oder andere. Die verfügbaren Optionen sind: <br>-   AEMSITE <br>-   PDF <br>-   HTML5 <br>-   EPUB <br>-   BENUTZERDEFINIERTE <br> |
| `outputTitle` | Ein beschreibender Name für die Ausgabevoreinstellungen. Damit wird der Wert für die Eigenschaft Name der Einstellung für die Ausgabevorgabe definiert. |
| `ditaValPathList` | Array von DITAVAL-Dateipfaden, die zur Generierung der gewünschten Ausgabe verwendet werden sollen. |
| `targetPath` | Pfad, in dem die Ausgabe veröffentlicht oder gespeichert wird |
| `siteName` | \(Für die Ausgabe der AEM-Site\) Name der AEM-Site. |
| `siteTitle` | \(Für die Ausgabe der AEM-Site\) Titel der AEM-Site. |
| `templatePath` | \(Für AEM Site-Ausgabe\) Pfad des Vorlagenknotens, der zum Generieren der gewünschten Ausgabe verwendet werden soll. |
| `searchScope` | Geben Sie den Umfang für den Suchvorgang an. Der Wert für diesen Parameter muss auf `local` gesetzt werden. |
| `generateTOC` | \(Für AEM-Site-Ausgabe\) Geben Sie an, ob ein Inhaltsverzeichnis generiert wird \(true\) oder nicht \(false\). |
| `generateBreadcrumbs` | \(Für die AEM-Site-Ausgabe\) Geben Sie an, ob die Breadcrumbs generiert werden \(true\) oder nicht \(false\). |
| `overwriteFiles` | \(Für AEM Site-Ausgabe\) Geben Sie an, ob Dateien am Ziel überschrieben werden \(true\) oder nicht \(false\). |
| `pdfGenerator` | Geben Sie die zu verwendende PDF-Erzeugungsmaschine an. Die möglichen Werte sind: <br>-   DITAOT <br>-   FMPS |

>[!NOTE]
>
> `DitaValPath` Element wird nicht mehr unterstützt.

## Ausgabe generieren

Eine GET-Methode, die mithilfe einer oder mehrerer Ausgabevorgaben eine Ausgabe generiert.

**Anfrage-URL**:
http://*&lt;aem-guides-server\>*: *&lt;port-number\>*/bin/publishlistener

**Parameter**:

| Name | Typ | Erforderlich | Beschreibung |
|----|----|--------|-----------|
| `operation` | Zeichenfolge | Ja | Name des aufzurufenden Vorgangs. Der Wert dieses Parameters ist `GENERATEOUTPUT`.<br> **Hinweis:** Beim Wert wird zwischen Groß- und Kleinschreibung unterschieden. |
| `source` | Zeichenfolge | Ja | Absoluter Pfad der DITA-Zuordnungsdatei. |
| `outputName` | Zeichenfolge | Ja | Name der für die Ausgabe zu verwendenden Ausgabevorgabe(n) Mehrere Ausgabevorgaben können mit einem senkrechten Strich (“\|&quot;\) angegeben werden, z. B. `aemsite\|pdfoutput`. |

**Antwortwerte**:
Gibt eine HTTP-Antwort 200 \(erfolgreich\) zurück.

## Inkrementelle Ausgabe generieren

Eine GET-Methode, die mithilfe einer oder mehrerer Ausgabevorgaben eine inkrementelle Ausgabe für eine AEM-Site generiert.

**Anfrage-URL**:
http://*&lt;aem-guides-server\>*: *&lt;port-number\>*/bin/publishlistener

**Parameter**:

| Name | Typ | Erforderlich | Beschreibung |
|----|----|--------|-----------|
| `operation` | Zeichenfolge | Ja | Name des aufzurufenden Vorgangs. Der Wert dieses Parameters ist `INCREMENTALPUBLISH`. <br>**Hinweis:** Beim Wert wird zwischen Groß- und Kleinschreibung unterschieden. |
| `contentPath` | JSON | Ja | Absoluter Pfad der DITA-Zuordnungsdatei und der Themendateien zusammen mit dem Namen der Ausgabevorgaben. Verwenden Sie das folgende Beispiel als Baustein: |

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
- Das `topics`-Attribut akzeptiert ein Array von Themen, die aktualisiert werden und erneut veröffentlicht werden müssen.
- Das `fullMaps`-Attribut enthält den Pfad der Zuordnungsdateien \(wie aufgeteilte Unterzuordnungen\), die zusammen mit ihren Themen für die inkrementelle Ausgabegenerierung benötigt werden.
- Das Attribut `maps` enthält den Pfad der Zuordnungsdateien \(zum Auflösen von Schlüsselraumverweisen\), die ohne Themen auf der Festplatte extrahiert werden.
- Das `outputs`-Attribut akzeptiert ein Array von Namen von Ausgabevorgaben, die zum Generieren der Ausgabe verwendet werden.

**Antwortwerte**:
Gibt eine HTTP-Antwort 200 \(erfolgreich\) zurück.

## Ausgabevorgabe löschen

Eine POST-Methode, die eine Ausgabevorgabe löscht.

**Anfrage-URL**:
http://*&lt;aem-guides-server\>*: *&lt;port-number\>*/bin/publishlistener

**Parameter**:

| Name | Typ | Erforderlich | Beschreibung |
|----|----|--------|-----------|
| `:operation` | Zeichenfolge | Ja | Name des aufzurufenden Vorgangs. Der Wert dieses Parameters ist `deleteoutput`.<br> **Hinweis:** Beim Wert wird nicht zwischen Groß- und Kleinschreibung unterschieden. |
| `sourcePath` | Zeichenfolge | Ja | Absoluter Pfad der DITA-Zuordnungsdatei. |
| `outputName` | Zeichenfolge | Ja | Name der zu löschenden Ausgabevorgabe. |

**Antwortwerte**:
Gibt eine HTTP-Antwort 200 \(erfolgreich\) zurück.
