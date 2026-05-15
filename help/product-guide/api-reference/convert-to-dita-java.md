---
title: Java-basierte APIs für Konvertierungs-Workflows
description: Erfahren Sie mehr über die Java-basierten APIs für den Konvertierungs-Workflow
exl-id: 807d9ffa-23e3-476c-992d-c1f495233892
feature: Java-Based API Conversion Workflow
role: Developer
level: Experienced
TQID: https://experienceleague.adobe.com/gAntb7T-OGlwRNInxAsV8orxL3H9qL19Dsjwf5FZ14I
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2:
  - id: a01bfd36-4ab8-4bf8-9dc0-5b45b890552e
  - id: c6d09140-3c91-45d3-b7ed-b681af752f43
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 324
ht-degree: 4%

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

Die `convertHtmlToDita`-Methode konvertiert HTML-Dokumente in das DITA-Format.

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
| `inputFile` | Zeichenfolge | Absoluter Pfad der HTML-Quelldateien im AEM-Repository. |
| `destPath` | Zeichenfolge | Absoluter Pfad des Zielspeicherorts, an dem die konvertierten DITA-Dateien gespeichert werden. |
| `createRev` | Boolescher Wert | Geben Sie an, ob eine Revision der Dateien \( `true`\) am angegebenen Ziel erstellt wird oder nicht \( `false`\). Dies wird nur berücksichtigt, wenn der Zielspeicherort eine vorhandene Version der konvertierten Dateien enthält. |

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
| `createRev` | Boolescher Wert | Geben Sie an, ob eine Revision der Dateien \( `true`\) am angegebenen Ziel erstellt wird oder nicht \( `false`\). Dies wird nur berücksichtigt, wenn der Zielspeicherort eine vorhandene Version der konvertierten Dateien enthält. |

**Ausnahme**:
Löst `RepositoryException` aus.
