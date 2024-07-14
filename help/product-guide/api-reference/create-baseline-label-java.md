---
title: Java-basierte APIs für die Verwendung mit Grundlinien und Bezeichnungen
description: Erfahren Sie mehr über die Java-basierten APIs für die Verwendung mit Grundlinien und Bezeichnungen
exl-id: 0e2ba1bb-f5bf-44da-848a-a55385460c83
feature: Java-Based API Baseline
role: Developer
level: Experienced
source-git-commit: be06612d832785a91a3b2a89b84e0c2438ba30f2
workflow-type: tm+mt
source-wordcount: '890'
ht-degree: 0%

---

# Java-basierte APIs für die Verwendung mit Grundlinien und Bezeichnungen {#id175UB30E05Z}

Mit den folgenden Java-basierten APIs können Sie eine Grundlinie erstellen und Dateien Beschriftungen zu einer Grundlinie hinzufügen. Diese APIs sind in Form eines Bundles verfügbar. Sie müssen dieses Bundle in Ihren Code aufnehmen, um diese APIs verwenden zu können.

Paketdetails:

- Gruppen-ID: **com.adobe.fmdita**

- Artefakt-ID: **api**

- Version: **3.5**

- Paket: **com.adobe.fmdita.api.baselines**

- Klassendetails:

  ```JAVA
  public class BaselineUtils extends Object
  ```

  Die Klasse **BaselineUtils** enthält Methoden zum Erstellen von Grundlinien und Anwenden von Beschriftungen auf Dateien in einer Grundlinie.


## Erstellen einer Grundlinie

Die Methode zur Erstellung einer Grundlinie verfügt über zwei Versionen: eine für die XML Documentation-Lösungsversion 3.5 und eine andere für Versionen vor Version 3.5 \(einschließlich Versionen 3.4, 3.3 und 3.2\). Die API Version 3.5 ermöglicht die Erstellung einer Grundlinie mithilfe einer Beschriftung, direkter Verweise und indirekter Verweise in einer Map-Datei.

Die andere Version der API verwendet das Datum und die Uhrzeit, um eine Grundlinie zu erstellen. Diese API wird aus Gründen der Abwärtskompatibilität mit Systemen mit XML Documentation-Lösung 3.4, 3.3 oder 3.2 beibehalten.

**Syntax \(für Version 3.5\)**:

```JAVA
public static String createBaseline(Session session, 
String sourcePath, 
String baselineTitle, 
String label, 
LinkedHashMap directContext, 
LinkedHashMap indirectContext) 
throws GuidesApiException
```

**Parameter**:
|Name|Typ|Beschreibung|
|—|—|—|
|`session`|javax.jcr.Session|Eine gültige JCR-Sitzung. Die Benutzersitzung muss sowohl Lese- als auch Schreibberechtigungen für die DITA-Zuordnung und Leseberechtigungen für alle in der Grundlinie enthaltenen Referenzdateien haben.|
|`sourcePath`|String|Absoluter Pfad der DITA-Map-Datei im AEM Repository.|
|`baselineTitle`|String|Ein eindeutiger Titel für die Grundlinie.|
|`label`|String|Wählen Sie die Version eines Themas aus, auf das die angegebene Bezeichnung angewendet wird.|
|`directContext`|LinkedHashMap&lt;String, Object\>|Die Konfigurationen, anhand derer direkt auf das Thema \(content\) verwiesen wird, werden anhand der Reihenfolge, die in der Zuordnung erwähnt wird, eine Version aufgelöst. <br> Wenn nach der Iteration auf allen Schlüsseln der Zuordnung keine Version gefunden wird, schlägt der Prozess zur Erstellung der Grundlinie fehl. <br> Wenn die HashMap leer ist \(leere und nicht Null-Zuordnung als Standard senden\), wird sie standardmäßig wie folgt aufgefüllt: <br>`directContext.put("label", label);` <br> `directContext.put("latest", true);` <br> Wenn Sie möchten, dass die Grundlinien-Erstellung nur die Version einer bestimmten Beschriftung auswählt und fehlschlägt, wenn keine solche Version vorhanden ist, setzen Sie den Schlüssel `label` und die Beschriftung, auf der Sie eine Grundlinie erstellen möchten.|
|`indirectContext`|LinkedHashMap&lt;String, Object\>|Die Konfigurationen, anhand derer indirekt auf das Thema \(referenzierter Inhalt\) verwiesen wird, werden anhand der Reihenfolge, die in der Zuordnung erwähnt wird, eine Version aufgelöst. <br> Wenn nach der Iteration auf allen Schlüsseln der Zuordnung keine Version gefunden wird, schlägt der Prozess zur Erstellung der Grundlinie fehl. <br> Wenn die HashMap leer ist \(leere und nicht Null-Zuordnung als Standard senden\), wird sie standardmäßig wie folgt aufgefüllt: <br>`indirectContext.put("label", label);` <br>`indirectContext.put "pickAutomatically", null);` <br> Wenn Sie möchten, dass es die neueste Version ist, anstatt eine Version automatisch zu übernehmen, ersetzen Sie: <br>`indirectContext.put("pickAutomatically", null);` <br> _with:_ <br>`indirectContext.put("latest", true)`|

**Gibt** zurück:
Der Name der Grundlinie, der der Knotenname der Grundlinie im JCR-Repository ist. Der Titel der neu erstellten Grundlinie wird dem Benutzer auf der Grundlagenseite für die DITA-Zuordnung angezeigt.

**Exception**:
Gibt ``ItemExistExceptiom`` aus, wenn bereits eine Grundlinie mit demselben Titel vorhanden ist.

**Syntax \(für Versionen 3.4, 3.3 und 3.2\)**

```JAVA
public static String createBaseline
(Session session, 
String sourcePath, 
String baselineTitle, 
Date versionDate) throws GuidesApiException
```

**Parameter**:
|Name|Typ|Beschreibung|
|—|—|—|
|`session`|javax.jcr.Session|Eine gültige JCR-Sitzung. Die Benutzersitzung muss sowohl Lese- als auch Schreibberechtigungen für die DITA-Zuordnung und Leseberechtigungen für alle in der Grundlinie enthaltenen Referenzdateien haben.|
|``sourcePath``|String|Absoluter Pfad der DITA-Map-Datei im AEM Repository.|
|`baselineTitle`|String|Ein eindeutiger Titel für die Grundlinie.|
|`versionDate`|Datum|Die Grundlinie wird mit den Versionen der Themen erstellt\ (direkt referenziert aus der DITA-Zuordnung\) wie zu diesem Datum. Geben Sie das Datum im Format `d-MM-yyyy H:mm` an.|

**Gibt** zurück:
Der Name der Grundlinie, der der Knotenname der Grundlinie im JCR-Repository ist. Der Titel der neu erstellten Grundlinie wird dem Benutzer auf der Grundlagenseite für die DITA-Zuordnung angezeigt.

**Exception**:
Throws ``RepositoryException.``

## Anwenden von Beschriftungen

Die Methode ``applyLabel`` wendet eine oder mehrere Beschriftungen auf die Dateien in einer Grundlinie an.

**Syntax**:

```JAVA
public static void applyLabel(Session session,
                  String sourcePath,
                  String baselineName,
                  String label)
                  throws RepositoryException, WorkflowException, Exception
```

**Parameter**:
|Name|Typ|Beschreibung|
|—|—|—|
|`session`|javax.jcr.Session|Eine gültige JCR-Sitzung.|
|`sourcePath`|String|Absoluter Pfad der DITA-Map-Datei im AEM Repository.|
|``baselineName``|String|Name des Grundlinien-Knotens, auf den die Beschriftung angewendet werden soll. Um den Namen des Grundlinien-Knotens abzurufen, können Sie die Methode [\#id185NFF0085Z](#id185NFF0085Z) verwenden oder den Grundlinien-Knoten der DITA-Zuordnung in CRXDE überprüfen.<br> **Hinweis:** Die Beschriftung wird auf die Version von Dateien angewendet, die direkt von der Map-Datei in der Grundlinie referenziert werden.|
|`label`|String|Eine Beschriftung, die auf Dateien in der Grundlinie angewendet wird. Achten Sie darauf, dass die Beschriftung folgende Zeichen nicht enthält: &amp;sol; &amp;comma; &amp;colon; &amp;comma; &amp;lbrack; &amp;comma; &amp; &amp;rbrack; &amp;comma; &amp;comma; &amp;ast; <br> Wenn Sie mehrere Beschriftungen festlegen möchten, trennen Sie sie mit einem Komma; 1, Beschriftung2.|

**Exception**:
Gibt `RepositoryException` aus.

## Löschen von Bezeichnungen

Die ``deleteLabel`` -Methode löscht eine oder mehrere Beschriftungen aus den Dateien in einer Grundlinie.

**Syntax**:

```JAVA
public static Map
<String, String> deleteLabel(Session session, 
String sourcePath, 
String baselineName, 
String label) throws GuidesApiException
```

**Parameter**:
|Name|Typ|Beschreibung|
|—|—|—|
|`session`|javax.jcr.Session|Eine gültige JCR-Sitzung.|
|`sourcePath`|String|Absoluter Pfad der DITA-Map-Datei im AEM Repository.|
|`baselineName`|String|Name der Grundlinie, von der die Beschriftung gelöscht werden soll. <br> **Hinweis:** Die Beschriftung wird aus der Version der Dateien gelöscht, die direkt von der Map-Datei im Grundlinien referenziert werden.|
|`label`|String|Eine Beschriftung, die aus Dateien in der Grundlinie gelöscht werden soll. <br> Wenn Sie mehrere Bezeichnungen löschen möchten, trennen Sie diese durch ein Komma, z. B. Label1, Label2.|

**Gibt** zurück:
Die Zuordnung mit dem *Schlüssel-Wert-Paar* von `path:deletedlabels` für alle Dateien in der Grundlinie.

**Exception**:
Gibt ``RepositoryException`, `VersionException`, `Exception`` aus.
