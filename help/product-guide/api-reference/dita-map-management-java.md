---
title: Java-basierte APIs zum Arbeiten mit DITA-Maps
description: Erfahren Sie mehr über die Java-basierten APIs für die Verwendung mit DITA-Maps
exl-id: bd91fc90-75f8-487c-99d1-2637e9cf9924
feature: Java-Based API Dita Map
role: Developer
level: Experienced
source-git-commit: 8c80a4da8e61909aab0f2db81ef97149774b36c4
workflow-type: tm+mt
source-wordcount: '1068'
ht-degree: 3%

---

# Java-basierte APIs zum Arbeiten mit DITA-Maps {#id175UB30E05Z}

>[!NOTE]
>
> Sie können in Experience Manager Guides verfügbare Java-basierte APIs verwenden, um benutzerdefinierte Plug-ins zu erstellen und native Workflows zu erweitern. Dieser Artikel wird im November 2024 archiviert.
> Die aktuelle und detaillierte Dokumentation zur Verwendung der Java-basierten API finden Sie unter [![javadoc](https://javadoc.io/badge2/com.adobe.aem/aem-guides-sdk-api/javadoc.svg)](https://javadoc.io/doc/com.adobe.aem/aem-guides-sdk-api) .



Mit den folgenden Java-basierten APIs können Sie mit DITA-Maps in AEM Guides arbeiten. Diese APIs sind in Form eines Bundles verfügbar. Sie müssen dieses Bundle in Ihren Code aufnehmen, um diese APIs verwenden zu können.

Paketdetails:

- Gruppen-ID: **com.adobe.fmdita**

- Artefakt-ID: **api**

- Version: **3.2**

- Paket: **com.adobe.fmdita.api.maps**

- Klassendetails:

  ```JAVA
  public class MapUtilities extends Object
  ```

  Die MapUtilities-Klasse enthält Methoden zum Abrufen von Metadateninformationen aus einer DITA-Map-Datei.


## DITA-Map mit abhängigen Elementen herunterladen

Die Methode `zipMapWithDependents` erstellt eine ZIP-Datei, die eine DITA-Zuordnung zusammen mit allen abhängigen Elementen wie referenzierten Themen, Unterkarten, Bildern und DTDs enthält. Die ZIP-Datei für die DITA-Zuordnung wird basierend auf einer gegebenen Grundlinie erstellt.

Außerdem können Sie entweder dieselbe Struktur beibehalten \(über- und untergeordnete Ordner\) oder eine flache Dateistruktur in einem einzigen Ordner für alle abhängigen Dateien erstellen.

>[!IMPORTANT]
>
> Die API gibt eine Ausnahme aus und kann keine ZIP-Datei erstellen, wenn eine der abhängigen Dateien fehlt.

**Syntax**:

```JAVA
public static void zipMapWithDependents(Session session, 
                     String sourcePath, 
                     String baseline, 
                     OutputStream outputStream,
                     boolean flatFS) 
                     throws RepositoryException, IOException
```

**Parameter**:

| Name | Typ | Beschreibung |
|----|----|-----------|
| `session` | javax.jcr.Session | Eine gültige JCR-Sitzung. |
| `sourcePath` | Zeichenfolge | Pfad \(im AEM Repository\) der DITA-Map-Datei, die heruntergeladen werden muss. |
| `outputStream` | java.io.OutputStream | Der Stream, in den die ZIP geschrieben werden soll. |
| `baseline` | Zeichenfolge | Der Titel der Grundlinie, mit der der versionierte Inhalt abgerufen wird. <br> **Hinweis:** Beim Wert wird zwischen Groß- und Kleinschreibung unterschieden. |
| flachFS | Boolesch | \(Optional\) Wenn auf &quot;true&quot;gesetzt, wird eine flache Dateistruktur in der ZIP-Datei zurückgegeben. Wenn Ihre DITA-Zuordnung beispielsweise auf Inhalte in mehreren Ordnern verweist, werden alle referenzierten Dateien in einen einzigen Ordner abgerufen. Wenn es Dateien mit demselben Namen gibt, werden diese Dateien umbenannt, indem ein numerisches Suffix hinzugefügt wird. Alle Verweise \(in DITA-Zuordnung und Themen\) werden automatisch verarbeitet, da sie basierend auf dem neuen Speicherort der Dateien in der flachen Ordnerstruktur aktualisiert werden. Wenn der Wert auf &quot;false&quot;gesetzt ist, wird die Ordnerstruktur so beibehalten, wie es in der ZIP-Datei der Fall ist. Wenn sich die DITA-Zuordnung auf Dateien von mehreren Speicherorten bezieht, werden auch alle diese Speicherorte in der ZIP-Datei erstellt. Wenn Sie die ZIP-Datei wiederherstellen, wird die genaue Ordnerstruktur am Zielspeicherort erstellt. <br> Der Standardwert für diesen Parameter ist &quot;false&quot;. |

**Gibt** zurück:
Der Inhalt der ZIP wird in die `outputStream` geschrieben.

**Exception**:
Löst ``javax.jcr.RepositoryException``, `java.io.IOException` aus.

## DITA-Map mit abhängigen Elementen herunterladen \(asynchron\)

Alternativ können Sie DITA-Map mit abhängigen Elementen im asynchronen Modus herunterladen. Dieser Ansatz ist für größere DITA-Maps nützlicher.

Die Methode `zipMapWithDependents` erstellt eine ZIP-Datei, die eine DITA-Zuordnung zusammen mit allen abhängigen Elementen wie referenzierten Themen, Unterkarten, Bildern und DTDs enthält. Die ZIP-Datei für die DITA-Zuordnung wird basierend auf einer gegebenen Grundlinie erstellt.

Außerdem können Sie entweder dieselbe Struktur beibehalten \(über- und untergeordnete Ordner\) oder eine flache Dateistruktur in einem einzigen Ordner für alle abhängigen Dateien erstellen.

>[!NOTE]
>
> Dieser Knoten wird nach einiger Zeit basierend auf der Konfiguration output.history.purgetime (sofern definiert) automatisch gelöscht, oder 5 Tage als Standard.

**Syntax**:

```JAVA
public static CompletableFuture<Node> zipMapWithDependencies(Session session,
                     String sourcePath, 
                     String baseline, 
                     boolean flatFS) 
```

**Parameter**:

| Name | Typ | Beschreibung |
|----|----|-----------|
| `session` | javax.jcr.Session | Eine gültige JCR-Sitzung. |
| `sourcePath` | Zeichenfolge | Pfad \(im AEM Repository\) der DITA-Map-Datei, die heruntergeladen werden muss. |
| `baseline` | Zeichenfolge | Der Titel der Grundlinie, mit der der versionierte Inhalt abgerufen wird. <br> **Hinweis:** Beim Wert wird zwischen Groß- und Kleinschreibung unterschieden. |
| flachFS | Boolesch | \(Optional\) Wenn auf &quot;true&quot;gesetzt, wird eine flache Dateistruktur in der ZIP-Datei zurückgegeben. Wenn Ihre DITA-Zuordnung beispielsweise auf Inhalte in mehreren Ordnern verweist, werden alle referenzierten Dateien in einen einzigen Ordner abgerufen. Wenn es Dateien mit demselben Namen gibt, werden diese Dateien umbenannt, indem ein numerisches Suffix hinzugefügt wird. Alle Verweise \(in DITA-Zuordnung und Themen\) werden automatisch verarbeitet, da sie basierend auf dem neuen Speicherort der Dateien in der flachen Ordnerstruktur aktualisiert werden. Wenn der Wert auf &quot;false&quot;gesetzt ist, wird die Ordnerstruktur so beibehalten, wie es in der ZIP-Datei der Fall ist. Wenn sich die DITA-Zuordnung auf Dateien von mehreren Speicherorten bezieht, werden auch alle diese Speicherorte in der ZIP-Datei erstellt. Wenn Sie die ZIP-Datei wiederherstellen, wird die genaue Ordnerstruktur am Zielspeicherort erstellt.<br> Der Standardwert für diesen Parameter ist &quot;false&quot;. |

**Gibt** zurück:
Der Knoten der ZIP-Datei wird in die Klasse `CompletableFuture`eingeschlossen. Der Benutzer kann die asynchrone Verarbeitung fortsetzen und die `.get()`Methode der Zukunft verwenden, um den Thread zu blockieren, wenn der Knoten benötigt wird. Der zurückgegebene Wert kann auch mit einem Fehler enden, der mit der `.exceptionally()` -Methode verarbeitet werden kann.

## Liste der Grundlinien abrufen

Die ``getBaselineList`` -Methode ruft eine Liste aller Grundlinien ab, die für eine bestimmte DITA-Zuordnung vorhanden sind.

**Syntax**:

```JAVA
public static List<HashMap<String,String>> getBaselineList( 
                  javax.jcr.Session session, 
                  String sourcePath)
                  throws javax.jcr.RepositoryException
```

**Parameter**:

| Name | Typ | Beschreibung |
|----|----|-----------|
| `session` | javax.jcr.Session | Eine gültige JCR-Sitzung. |
| `sourcePath` | Zeichenfolge | Pfad \(im AEM Repository\) der DITA-Map-Datei, für die die Basisinformationen abgerufen werden sollen. |

**Gibt** zurück:
Eine Liste von `HashMap` -Objekten. Jedes `HashMap` -Objekt stellt eine Grundlinie dar und enthält den Namen und den Titel der Grundlinie.

**Exception**:
Gibt ``javax.jcr.RepositoryException`` aus.

## Liste bedingter Vorgaben abrufen

Die ``getConditionalPresetList`` -Methode ruft eine Liste aller bedingten Vorgaben ab, die für eine bestimmte DITA-Zuordnung vorhanden sind.

**Syntax**:

```JAVA
public static List<HashMap<String,String>> getConditionalPresetList (
                  javax.jcr.Session session,
                  String sourcePath)
                  throws javax.jcr.RepositoryException
```

**Parameter**:

| Name | Typ | Beschreibung |
|----|----|-----------|
| `session` | javax.jcr.Session | Eine gültige JCR-Sitzung. |
| `sourcePath` | Zeichenfolge | Pfad \(im AEM Repository\) der DITA-Map-Datei, für die die bedingten Vorgabeninformationen abgerufen werden sollen. |

**Gibt** zurück:
Eine Liste von `HashMap` -Objekten. Jedes `HashMap` -Objekt stellt eine bedingte Vorgabe dar und enthält den Namen und den Titel der bedingten Vorgabe.

**Exception**:
Gibt ``javax.jcr.RepositoryException`` aus.

## Abrufen der DITAVAL-Dateiinformationen für eine bedingte Vorgabe

Die Methode ``getDitavalFromConditionalPreset`` ruft den Pfad der DITAVAL-Datei ab, der einer bedingten Vorgabe für eine bestimmte DITA-Zuordnung entspricht.

**Syntax**:

```JAVA
public static String getDitavalFromConditionalPreset
    (Session session,
    String sourcePath, 
    String cpName) throws RepositoryException
```

**Parameter**:

| Name | Typ | Beschreibung |
|----|----|-----------|
| `session` | javax.jcr.Session | Eine gültige JCR-Sitzung. |
| `sourcePath` | Zeichenfolge | Pfad \(im AEM Repository\) der DITA-Map-Datei, für die die DITAVAL-Datei abgerufen werden soll. |
| `cpName` | Zeichenfolge | Name der bedingten Vorgabe in der DITA-Zuordnung, für die die DITAVAL-Datei abgerufen werden soll. |

**Gibt** zurück:
Der Pfad der DITAVAL-Datei, die der in der DITA-Map-Datei definierten bedingten Vorgabe entspricht.

## Abrufen aller Abhängigkeiten für einen Knoten

Die ``getAllDependencies`` -Methode gibt alle Abhängigkeiten eines angegebenen Knotens zurück.

**Syntax**:

```JAVA
public static List
<Node> getAllDependencies 
(Node rootNode) throws GuidesApiException
```

**Parameter**:

| Name | Typ | Beschreibung |
|----|----|-----------|
| `rootNode` | javax.jcr.Node | Der Stammknoten, für den alle Abhängigkeiten abgerufen werden sollen. |

**Gibt** zurück:
Eine Knotenliste, die alle Abhängigkeiten des Stammknotens enthält.
