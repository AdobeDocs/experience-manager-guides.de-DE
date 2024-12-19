---
title: Java-basierte APIs für Konvertierungs-Workflows
description: Erfahren Sie mehr über die Java-basierten APIs für den Konvertierungs-Workflow
exl-id: 807d9ffa-23e3-476c-992d-c1f495233892
feature: Java-Based API Conversion Workflow
role: Developer
level: Experienced
source-git-commit: 8c80a4da8e61909aab0f2db81ef97149774b36c4
workflow-type: tm+mt
source-wordcount: '300'
ht-degree: 5%

---

# Java-basierte APIs für Konvertierungs-Workflows {#id175UB30E05Z}

>[!NOTE]
>
> Sie können die in Experience Manager Guides verfügbaren Java-basierten APIs verwenden, um benutzerdefinierte Plug-ins zu erstellen und vordefinierte Workflows zu erweitern. Dieser Artikel wird im November 2024 archiviert.
> In [![javadoc](https://javadoc.io/badge2/com.adobe.aem/aem-guides-sdk-api/javadoc.svg)](https://javadoc.io/doc/com.adobe.aem/aem-guides-sdk-api) finden Sie die neueste und detaillierte Dokumentation zur Verwendung der Java-basierten API.




Mit den folgenden Java-basierten APIs können Sie HTML- und Word-Dokumente in das DITA-Format konvertieren. Diese APIs sind in Form eines Bundles verfügbar. Sie müssen dieses Bundle in Ihren Code aufnehmen, um diese APIs verwenden zu können.

**Paketdetails**:

- Gruppen-ID: **com.adobe.fmdita**

- Artefakt-ID: **api**

- Version: **.2**

- Paket: **com.adobe.fmdita.api.conversion**

- Klassendetails:

  ```JAVA
  public class ConversionUtils extends Object
  ```

  Die **ConversionUtils**-Klasse enthält Methoden zum Konvertieren von HTML- und Word-Dokumenten in das DITA-Format.


## HTML-Dokumente konvertieren

Mit der `convertHtmlToDita` Methode werden HTML-Dokumente in das DITA-Format konvertiert.

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
| `inputFile` | Zeichenfolge | Absoluter Pfad der Quell-HTML-Dateien im AEM-Repository |
| `destPath` | Zeichenfolge | Absoluter Pfad des Zielspeicherorts, an dem die konvertierten DITA-Dateien gespeichert werden. |
| `createRev` | Boolesch | Geben Sie an, ob eine Revision der Dateien \( `true`\) am angegebenen Ziel erstellt wird oder nicht \( `false`\). Dies wird nur berücksichtigt, wenn der Zielspeicherort eine vorhandene Version der konvertierten Dateien enthält. |

**Ausnahme**:
Löst `RepositoryException` aus.

## Word-Dokumente konvertieren

Die ``convertWordToDita``-Methode konvertiert Word-Dokumente in das DITA-Format.

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
| `inputFile` | Zeichenfolge | Absoluter Pfad der Word-Quelldateien im AEM-Repository. |
| `destPath` | Zeichenfolge | Absoluter Pfad des Zielspeicherorts, an dem die konvertierten DITA-Dateien gespeichert werden. |
| `style2tagMap` | Zeichenfolge | Absoluter Pfad der Stilzuordnungsdatei, die für die Konvertierung verwendet wird. |
| `createRev` | Boolesch | Geben Sie an, ob eine Revision der Dateien \( `true`\) am angegebenen Ziel erstellt wird oder nicht \( `false`\). Dies wird nur berücksichtigt, wenn der Zielspeicherort eine vorhandene Version der konvertierten Dateien enthält. |

**Ausnahme**:
Löst `RepositoryException` aus.
