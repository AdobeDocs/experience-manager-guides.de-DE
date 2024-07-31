---
title: Java-basierte APIs für Konversions-Workflow
description: Erfahren Sie mehr über die Java-basierten APIs für den Konvertierungs-Workflow
exl-id: 807d9ffa-23e3-476c-992d-c1f495233892
feature: Java-Based API Conversion Workflow
role: Developer
level: Experienced
source-git-commit: 83966cc9187b13dd3b5956821e0aa038b41db28e
workflow-type: tm+mt
source-wordcount: '259'
ht-degree: 5%

---

# Java-basierte APIs für Konversions-Workflow {#id175UB30E05Z}

Mit den folgenden Java-basierten APIs können Sie HTML- und Word-Dokumente in das DITA-Format konvertieren. Diese APIs sind in Form eines Bundles verfügbar. Sie müssen dieses Bundle in Ihren Code aufnehmen, um diese APIs verwenden zu können.

**Bundle details**:

- Gruppen-ID: **com.adobe.fmdita**

- Artefakt-ID: **api**

- Version: **3.2**

- Paket: **com.adobe.fmdita.api.conversion**

- Klassendetails:

  ```JAVA
  public class ConversionUtils extends Object
  ```

  Die Klasse **ConversionUtils** enthält Methoden zum Konvertieren von HTML- und Word-Dokumenten in das DITA-Format.


## Konvertieren von HTML-Dokumenten

Die `convertHtmlToDita` -Methode konvertiert HTML-Dokumente in das DITA-Format.

**Syntax**:

```JAVA
public static void convertHtmlToDita(Session session, 
                  String inputFile, 
                  String destPath, 
                  boolean createRev) 
                  throws RepositoryException, WorkflowException
```

**Parameter**:

| Name | Typ | Beschreibung |
|----|----|-----------|
| `session` | javax.jcr.Session | Eine gültige JCR-Sitzung. |
| `inputFile` | Zeichenfolge | Absoluter Pfad der HTML-Quelldateien im AEM Repository. |
| `destPath` | Zeichenfolge | Absoluter Pfad des Zielorts, an dem die konvertierten DITA-Dateien gespeichert werden. |
| `createRev` | Boolesch | Geben Sie an, ob eine Revision der Dateien \( `true`\) am angegebenen Ziel erstellt wird oder nicht \( `false`\). Dies wird nur berücksichtigt, wenn der Zielspeicherort eine vorhandene Version der konvertierten Dateien enthält. |

**Exception**:
Gibt `RepositoryException` aus.

## Konvertieren von Word-Dokumenten

Die ``convertWordToDita`` -Methode konvertiert Word-Dokumente in das DITA-Format.

**Syntax**:

```JAVA
public static void convertWordToDita(Session session, 
                  String inputFile,
                  String destPath, 
                  String style2tagMap, 
                  boolean createRev) 
                  throws RepositoryException, WorkflowException
```

**Parameter**:

| Name | Typ | Beschreibung |
|----|----|-----------|
| `session` | javax.jcr.Session | Eine gültige JCR-Sitzung. |
| `inputFile` | Zeichenfolge | Absoluter Pfad der Word-Quelldateien in AEM Repository. |
| `destPath` | Zeichenfolge | Absoluter Pfad des Zielorts, an dem die konvertierten DITA-Dateien gespeichert werden. |
| `style2tagMap` | Zeichenfolge | Absoluter Pfad der Stilzuordnungsdatei, die für die Konvertierung verwendet wird. |
| `createRev` | Boolesch | Geben Sie an, ob eine Revision der Dateien \( `true`\) am angegebenen Ziel erstellt wird oder nicht \( `false`\). Dies wird nur berücksichtigt, wenn der Zielspeicherort eine vorhandene Version der konvertierten Dateien enthält. |

**Exception**:
Gibt `RepositoryException` aus.
