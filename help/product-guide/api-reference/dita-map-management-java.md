---
title: Java-basierte APIs für die Arbeit mit DITA-Zuordnungen
description: Erfahren Sie mehr über die Java-basierten APIs zum Arbeiten mit DITA-Zuordnungen
exl-id: bd91fc90-75f8-487c-99d1-2637e9cf9924
feature: Java-Based API Dita Map
role: Developer
level: Experienced
source-git-commit: 8c80a4da8e61909aab0f2db81ef97149774b36c4
workflow-type: tm+mt
source-wordcount: '1068'
ht-degree: 3%

---

# Java-basierte APIs für die Arbeit mit DITA-Zuordnungen {#id175UB30E05Z}

>[!NOTE]
>
> Sie können die in Experience Manager Guides verfügbaren Java-basierten APIs verwenden, um benutzerdefinierte Plug-ins zu erstellen und vordefinierte Workflows zu erweitern. Dieser Artikel wird im November 2024 archiviert.
> In [![javadoc](https://javadoc.io/badge2/com.adobe.aem/aem-guides-sdk-api/javadoc.svg)](https://javadoc.io/doc/com.adobe.aem/aem-guides-sdk-api) finden Sie die neueste und detaillierte Dokumentation zur Verwendung der Java-basierten API.



Mit den folgenden Java-basierten APIs können Sie in AEM Guides mit DITA-Zuordnungen arbeiten. Diese APIs sind in Form eines Bundles verfügbar. Sie müssen dieses Bundle in Ihren Code aufnehmen, um diese APIs verwenden zu können.

Paketdetails:

- Gruppen-ID: **com.adobe.fmdita**

- Artefakt-ID: **api**

- Version: **.2**

- Paket: **com.adobe.fmdita.api.maps**

- Klassendetails:

  ```JAVA
  public class MapUtilities extends Object
  ```

  Die MapUtilities-Klasse enthält Methoden zum Abrufen von Metadateninformationen aus einer DITA-Zuordnungsdatei.


## DITA Map mit Angehörigen herunterladen

Die `zipMapWithDependents`-Methode erstellt eine ZIP-Datei, die eine DITA-Zuordnung zusammen mit allen abhängigen Elementen wie referenzierten Themen, Unterkarten, Bildern und DTDs enthält. Die ZIP-Datei für die DITA-Map wird basierend auf einer bestimmten Grundlinie erstellt.

Außerdem können Sie entweder dieselbe Struktur \(übergeordnete und untergeordnete Ordner\) beibehalten oder eine flache Dateistruktur in einem einzigen Ordner für alle abhängigen Dateien erstellen.

>[!IMPORTANT]
>
> Die API löst eine Ausnahme aus und kann keine ZIP-Datei erstellen, wenn eine der abhängigen Dateien fehlt.

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
| `sourcePath` | Zeichenfolge | Pfad \(im AEM-Repository\) der DITA-Zuordnungsdatei, die heruntergeladen werden muss. |
| `outputStream` | java.io.OutputStream | Der Stream, in den die ZIP geschrieben werden soll. |
| `baseline` | Zeichenfolge | Der Titel der Baseline, die zum Abrufen des versionierten Inhalts verwendet wird. <br> **Hinweis:** Beim Wert wird zwischen Groß- und Kleinschreibung unterschieden. |
| flatFS | Boolesch | \(Optional\) Wenn auf „true“ gesetzt, wird eine flache Struktur von Dateien in der ZIP-Datei zurückgegeben. Wenn sich Ihre DITA-Zuordnung beispielsweise auf Inhalte in mehreren Ordnern bezieht, werden alle referenzierten Dateien in einen einzelnen Ordner gezogen. Wenn es Dateien mit demselben Namen gibt, werden diese Dateien durch Hinzufügen eines numerischen Suffix umbenannt. Alle Verweise \(in DITA-Map und Themen\) werden automatisch verarbeitet, da sie auf der Grundlage des neuen Speicherorts der Dateien in der flachen Ordnerstruktur aktualisiert werden. Wenn dies auf „false“ festgelegt ist, wird die Ordnerstruktur in der ZIP-Datei unverändert beibehalten. Wenn sich die DITA-Zuordnung auf Dateien aus mehreren Speicherorten bezieht, werden alle diese Speicherorte ebenfalls in der ZIP-Datei erstellt. Wenn Sie die ZIP-Datei wiederherstellen, wird die exakte Ordnerstruktur am Zielspeicherort erstellt. <br> Der Standardwert für diesen Parameter ist „false“. |

**Rückgabe**:
Der Inhalt der ZIP-Datei wird in die `outputStream` geschrieben.

**Ausnahme**:
Gibt ``javax.jcr.RepositoryException``, `java.io.IOException`.

## DITA-Map mit abhängigen Elementen herunterladen \(asynchron\)

Alternativ können Sie DITA Map mit abhängigen Elementen im asynchronen Modus herunterladen. Dieser Ansatz ist bei größeren DITA-Karten nützlicher.

Die `zipMapWithDependents`-Methode erstellt eine ZIP-Datei, die eine DITA-Zuordnung zusammen mit allen abhängigen Elementen wie referenzierten Themen, Unterkarten, Bildern und DTDs enthält. Die ZIP-Datei für die DITA-Map wird basierend auf einer bestimmten Grundlinie erstellt.

Außerdem können Sie entweder dieselbe Struktur \(übergeordnete und untergeordnete Ordner\) beibehalten oder eine flache Dateistruktur in einem einzigen Ordner für alle abhängigen Dateien erstellen.

>[!NOTE]
>
> Dieser Knoten wird nach einiger Zeit automatisch gelöscht, basierend auf der Konfiguration output.history.purgetime , falls definiert, oder 5 Tage als Standard.

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
| `sourcePath` | Zeichenfolge | Pfad \(im AEM-Repository\) der DITA-Zuordnungsdatei, die heruntergeladen werden muss. |
| `baseline` | Zeichenfolge | Der Titel der Baseline, die zum Abrufen des versionierten Inhalts verwendet wird. <br> **Hinweis:** Beim Wert wird zwischen Groß- und Kleinschreibung unterschieden. |
| flatFS | Boolesch | \(Optional\) Wenn auf „true“ gesetzt, wird eine flache Struktur von Dateien in der ZIP-Datei zurückgegeben. Wenn sich Ihre DITA-Zuordnung beispielsweise auf Inhalte in mehreren Ordnern bezieht, werden alle referenzierten Dateien in einen einzelnen Ordner gezogen. Wenn es Dateien mit demselben Namen gibt, werden diese Dateien durch Hinzufügen eines numerischen Suffix umbenannt. Alle Verweise \(in DITA-Map und Themen\) werden automatisch verarbeitet, da sie auf der Grundlage des neuen Speicherorts der Dateien in der flachen Ordnerstruktur aktualisiert werden. Wenn dies auf „false“ festgelegt ist, wird die Ordnerstruktur in der ZIP-Datei unverändert beibehalten. Wenn sich die DITA-Zuordnung auf Dateien aus mehreren Speicherorten bezieht, werden alle diese Speicherorte ebenfalls in der ZIP-Datei erstellt. Wenn Sie die ZIP-Datei wiederherstellen, wird die exakte Ordnerstruktur am Zielspeicherort erstellt.<br> Der Standardwert für diesen Parameter ist „false“. |

**Rückgabe**:
Der Knoten der ZIP-Datei wird in die Klasse `CompletableFuture`umschlossen. Der Benutzer kann die asynchrone Verarbeitung fortsetzen und den Thread mithilfe `.get()`Methode der Zukunft blockieren, wenn der Knoten benötigt wird. Der zurückgegebene Wert kann auch mit einem Fehler enden, der mit `.exceptionally()` Methode verarbeitet werden kann.

## Abrufen einer Liste von Baselines

Die ``getBaselineList`` Methode ruft eine Liste aller Baselines ab, die für eine bestimmte DITA-Zuordnung vorhanden sind.

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
| `sourcePath` | Zeichenfolge | Pfad \(im AEM-Repository\) der DITA-Map-Datei, für die die Baseline-Informationen abgerufen werden sollen. |

**Rückgabe**:
Eine Liste mit `HashMap` Objekten. Jedes `HashMap`-Objekt stellt eine Baseline dar und enthält den Namen und Titel der Baseline.

**Ausnahme**:
Löst ``javax.jcr.RepositoryException`` aus.

## Abrufen einer Liste von bedingten Voreinstellungen

Die ``getConditionalPresetList``-Methode ruft eine Liste aller bedingten Vorgaben ab, die für eine bestimmte DITA-Zuordnung vorhanden sind.

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
| `sourcePath` | Zeichenfolge | Pfad \(im AEM-Repository\) der DITA-Zuordnungsdatei, für die die Informationen der bedingten Voreinstellung abgerufen werden sollen. |

**Rückgabe**:
Eine Liste mit `HashMap` Objekten. Jedes `HashMap`-Objekt stellt eine bedingte Vorgabe dar und enthält den Namen und Titel der bedingten Vorgabe.

**Ausnahme**:
Löst ``javax.jcr.RepositoryException`` aus.

## Abrufen der DITAVAL-Dateiinformationen für eine bedingte Vorgabe

Die ``getDitavalFromConditionalPreset`` Methode ruft den Pfad der DITAVAL-Datei ab, die einer bedingten Voreinstellung für eine bestimmte DITA-Zuordnung entspricht.

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
| `sourcePath` | Zeichenfolge | Pfad \(im AEM-Repository\) der DITA-Map-Datei, für die die DITAVAL-Datei abgerufen werden soll. |
| `cpName` | Zeichenfolge | Name der bedingten Voreinstellung in der DITA-Map, für die die DITAVAL-Datei abgerufen werden soll. |

**Rückgabe**:
Der Pfad der DITAVAL-Datei, die der in der DITA-Zuordnungsdatei definierten bedingten Voreinstellung entspricht.

## Abrufen aller Abhängigkeiten für einen Knoten

Die ``getAllDependencies``-Methode gibt alle Abhängigkeiten eines bestimmten Knotens zurück.

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

**Rückgabe**:
Eine Knotenliste mit allen Abhängigkeiten des Stammknotens.
