---
title: Java-basierte APIs für die Arbeit mit Grundlinien und Kennzeichnungen
description: Erfahren Sie mehr über die Java-basierten APIs für die Arbeit mit Grundlinien und Kennzeichnungen
exl-id: 0e2ba1bb-f5bf-44da-848a-a55385460c83
feature: Java-Based API Baseline
role: Developer
level: Experienced
source-git-commit: 8c80a4da8e61909aab0f2db81ef97149774b36c4
workflow-type: tm+mt
source-wordcount: '931'
ht-degree: 2%

---

# Java-basierte APIs für die Arbeit mit Grundlinien und Kennzeichnungen {#id175UB30E05Z}

>[!NOTE]
>
> Sie können die in Experience Manager Guides verfügbaren Java-basierten APIs verwenden, um benutzerdefinierte Plug-ins zu erstellen und vordefinierte Workflows zu erweitern. Dieser Artikel wird im November 2024 archiviert.
> In [![javadoc](https://javadoc.io/badge2/com.adobe.aem/aem-guides-sdk-api/javadoc.svg)](https://javadoc.io/doc/com.adobe.aem/aem-guides-sdk-api) finden Sie die neueste und detaillierte Dokumentation zur Verwendung der Java-basierten API.


Mit den folgenden Java-basierten APIs können Sie Grundlinien erstellen und Dateien in einer Grundlinie Kennzeichnungen hinzufügen. Diese APIs sind in Form eines Bundles verfügbar. Sie müssen dieses Bundle in Ihren Code aufnehmen, um diese APIs verwenden zu können.

Paketdetails:

- Gruppen-ID: **com.adobe.fmdita**

- Artefakt-ID: **api**

- Version: **.5**

- Paket: **com.adobe.fmdita.api.baselines**

- Klassendetails:

  ```JAVA
  public class BaselineUtils extends Object
  ```

  Die **BaselineUtils**-Klasse enthält Methoden zum Erstellen von Baselines und zum Anwenden von Kennzeichnungen auf Dateien in einer Baseline.


## Erstellen einer Baseline

Die Methode „Baseline erstellen“ hat zwei Versionen: eine für die XML Documentation-Lösungsversion 3.5 und eine für Versionen vor Version 3.5 \(diese umfasst die Versionen 3.4, 3.3 und 3.2\). Die Version 3.5-API ermöglicht die Erstellung von Grundlinien mithilfe einer Beschriftung, direkter Verweise und indirekter Verweise in einer Zuordnungsdatei.

Die andere API-Version verwendet Datum und Uhrzeit, um eine Baseline zu erstellen. Diese API wird aus Gründen der Abwärtskompatibilität mit Systemen beibehalten, die XML Documentation-Lösungen 3.4, 3.3 oder 3.2 verwenden.

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

| Name | Typ | Beschreibung |
|----|----|-----------|
| `session` | javax.jcr.Session | Eine gültige JCR-Sitzung. Die Benutzersitzung muss sowohl Lese- als auch Schreibberechtigungen für die DITA-Zuordnung und Leseberechtigungen für alle in der Baseline enthaltenen Referenzdateien haben. |
| `sourcePath` | Zeichenfolge | Absoluter Pfad der DITA-Zuordnungsdatei im AEM-Repository. |
| `baselineTitle` | Zeichenfolge | Ein eindeutiger Titel für die Baseline. |
| `label` | Zeichenfolge | Wählen Sie die Version eines Themas aus, auf das die angegebene Beschriftung angewendet wurde. |
| `directContext` | LinkedHashMap&lt;String, Objekt\> | Bei den Konfigurationen, auf deren Grundlage das direkt referenzierte Thema \(content\) ausgewählt wird, wird zur Auflösung einer Version die in der Zuordnung angegebene Reihenfolge befolgt. <br> Wenn nach der Iteration für alle Schlüssel der Zuordnung keine Version gefunden wird, schlägt der Erstellungsprozess der Baseline fehl. <br> Wenn die HashMap leer ist \(Leere und keine Null-Map für Standard\), wird sie standardmäßig wie folgt ausgefüllt: <br>`directContext.put("label", label);` <br> `directContext.put("latest", true);` <br> Wenn bei der Basiserstellung nur die Version einer bestimmten Beschriftung ausgewählt werden soll und sie fehlschlägt, wenn keine solche Version vorhanden ist, legen Sie den `label` und die Beschriftung, für die Sie eine Basiserstellung erstellen möchten, fest. |
| `indirectContext` | LinkedHashMap&lt;String, Objekt\> | Bei den Konfigurationen, auf deren Grundlage das indirekt referenzierte Thema \(referenzierte Inhalte\) ausgewählt wird, wird zur Auflösung einer Version die in der Zuordnung angegebene Reihenfolge befolgt. <br> Wenn nach der Iteration für alle Schlüssel der Zuordnung keine Version gefunden wird, schlägt der Erstellungsprozess der Baseline fehl. <br> Wenn die HashMap leer ist \(Leere und nicht null Map für Standard\), wird sie standardmäßig wie folgt ausgefüllt: <br>`indirectContext.put("label", label);` <br>`indirectContext.put "pickAutomatically", null);` <br> Wenn Sie möchten, dass es sich um die neueste Version handelt, anstatt automatisch eine Version zu wählen, ersetzen Sie: <br>`indirectContext.put("pickAutomatically", null);` <br> _mit:_ <br>`indirectContext.put("latest", true)` |

**Rückgabe**:
Der Name der Baseline, der der Knotenname der Baseline im JCR-Repository ist. Der Titel der neu erstellten Baseline wird dem Benutzer auf der Seite Baseline für die DITA-Zuordnung angezeigt.

**Ausnahme**:
Gibt ``ItemExistExceptiom`` aus, wenn bereits eine Baseline mit demselben Titel vorhanden ist.

**Syntax \(für Versionen 3.4, 3.3 und 3.2\)**

```JAVA
public static String createBaseline
(Session session, 
String sourcePath, 
String baselineTitle, 
Date versionDate) throws GuidesApiException
```

**Parameter**:

| Name | Typ | Beschreibung |
|----|----|-----------|
| `session` | javax.jcr.Session | Eine gültige JCR-Sitzung. Die Benutzersitzung muss sowohl Lese- als auch Schreibberechtigungen für die DITA-Zuordnung und Leseberechtigungen für alle in der Baseline enthaltenen Referenzdateien haben. |
| ``sourcePath`` | Zeichenfolge | Absoluter Pfad der DITA-Zuordnungsdatei im AEM-Repository. |
| `baselineTitle` | Zeichenfolge | Ein eindeutiger Titel für die Baseline. |
| `versionDate` | Datum | Die Grundlinie wird unter Verwendung der Versionen von Themen\ (die direkt von der DITA-Karte\ referenziert werden) erstellt, wie zu diesem Datum. Geben Sie das Datum im `d-MM-yyyy H:mm` an. |

**Rückgabe**:
Der Name der Baseline, der der Knotenname der Baseline im JCR-Repository ist. Der Titel der neu erstellten Baseline wird dem Benutzer auf der Seite Baseline für die DITA-Zuordnung angezeigt.

**Ausnahme**:
Löst ``RepositoryException.``

## Anwenden von Kennzeichnungen

Die ``applyLabel`` Methode wendet eine oder mehrere Kennzeichnungen auf die Dateien in einer Grundlinie an.

**Syntax**:

```JAVA
public static void applyLabel(Session session,
                  String sourcePath,
                  String baselineName,
                  String label)
                  throws RepositoryException, WorkflowException, Exception
```

**Parameter**:

| Name | Typ | Beschreibung |
|----|----|-----------|
| `session` | javax.jcr.Session | Eine gültige JCR-Sitzung. |
| `sourcePath` | Zeichenfolge | Absoluter Pfad der DITA-Zuordnungsdatei im AEM-Repository. |
| ``baselineName`` | Zeichenfolge | Name des Basisknotens, auf den die Bezeichnung angewendet werden soll. Um den Namen des Baseline-Knotens abzurufen, können Sie die Methode [\#id185NFF0085Z](#id185NFF0085Z) verwenden oder den Baselines-Knoten der DITA-Zuordnung in CRXDE überprüfen.<br> **Hinweis:** Bezeichnung wird auf Versionen von Dateien angewendet, die direkt von der Zuordnungsdatei in der Baseline referenziert werden. |
| `label` | Zeichenfolge | Eine Beschriftung, die auf Dateien in der Grundlinie angewendet wird. Stellen Sie sicher, dass die Beschriftung nicht die folgenden Zeichen enthält: &amp;sol; &amp;comma;amp;colon; &amp;comma;amp;lbrack; &amp;comma;amp;rbrack; &amp;comma;amp;vert; &amp;comma; &amp;amp;amp;ast; <br> Wenn Sie mehrere Beschriftungen festlegen möchten, trennen Sie Beschriftungen mit einem Komma; zum Beispiel Beschriftung1, Beschriftung2. |

**Ausnahme**:
Löst `RepositoryException` aus.

## Kennzeichnungen löschen

Die ``deleteLabel``-Methode löscht eine oder mehrere Kennzeichnungen aus den Dateien in einer Grundlinie.

**Syntax**:

```JAVA
public static Map
<String, String> deleteLabel(Session session, 
String sourcePath, 
String baselineName, 
String label) throws GuidesApiException
```

**Parameter**:

| Name | Typ | Beschreibung |
|----|----|-----------|
| `session` | javax.jcr.Session | Eine gültige JCR-Sitzung. |
| `sourcePath` | Zeichenfolge | Absoluter Pfad der DITA-Zuordnungsdatei im AEM-Repository. |
| `baselineName` | Zeichenfolge | Name der Baseline, aus der die Bezeichnung gelöscht werden soll. <br> **Hinweis** Die Bezeichnung wird aus der Version von Dateien gelöscht, auf die in der Baseline direkt in der Zuordnungsdatei verwiesen wird. |
| `label` | Zeichenfolge | Eine Bezeichnung, die aus Dateien in der Baseline gelöscht werden soll. <br> Wenn Sie mehrere Kennzeichnungen löschen möchten, trennen Sie Kennzeichnungen durch ein Komma; z. B. Label1, Label2. |

**Rückgabe**:
Die Zuordnung mit *key:value* Paar `path:deletedlabels` für alle Dateien in der Baseline.

**Ausnahme**:
Löst ``RepositoryException`, `VersionException`, `Exception`` aus.
