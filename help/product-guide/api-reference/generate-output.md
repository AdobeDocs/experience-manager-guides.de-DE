---
title: Java-basierte API für die Ausgabegenerierung
description: Erfahren Sie mehr über die Java-basierte API für die Verwendung bei der Ausgabegenerierung
exl-id: e19439df-39ec-47fd-9da5-24f51750a7e5
feature: Java-Based API Publishing
role: Developer
level: Experienced
source-git-commit: ee4eb829ebe215315b05cd1f376e934c02a73b1e
workflow-type: tm+mt
source-wordcount: '201'
ht-degree: 2%

---

# Java-basierte API für die Ausgabegenerierung {#id175UB30E05Z}

>[!NOTE]
>
> Sie können die in Experience Manager Guides verfügbaren Java-basierten APIs verwenden, um benutzerdefinierte Plug-ins zu erstellen und vordefinierte Workflows zu erweitern. Dieser Artikel wird im November 2024 archiviert.
> In [![javadoc](https://javadoc.io/badge2/com.adobe.aem/aem-guides-sdk-api/javadoc.svg)](https://javadoc.io/doc/com.adobe.aem/aem-guides-sdk-api) finden Sie die neueste und detaillierte Dokumentation zur Verwendung der Java-basierten API.

Mit der folgenden Java-basierten API können Sie Ausgaben für eine DITA-Zuordnung generieren. Diese API ist in Form eines Bundles verfügbar. Sie müssen dieses Bundle in Ihren Code aufnehmen, um diese APIs verwenden zu können.

Paketdetails:

- Gruppen-ID: **com.adobe.fmdita**

- Artefakt-ID: **api**

- Version: **.4**

- Paket: ****com.adobe.fmdita.api.maps****

- Klassendetails:

  ```JAVA
  public class **PublishUtils** extends Object
  ```

  Die **`PublishUtils`**-Klasse enthält eine Methode zum Generieren von Ausgaben für eine oder mehrere Ausgabevorgaben.


## Ausgabe generieren

Die ``generateOutput``-Methode generiert die Ausgabe für eine DITA-Zuordnungsdatei unter Verwendung der angegebenen Ausgabevorgaben.

**Syntax**:

```JAVA
public static void generateOutput(Session session,
String sourcePath,
String outputName)
throws GuidesApiException
```

**Parameter**:

| Name | Typ | Beschreibung |
|----|----|-----------|
| `session` | javax.jcr.Session | Eine gültige JCR-Sitzung. |
| ``sourcePath`` | Zeichenfolge | Pfad \(im AEM-Repository\) der DITA-Map-Datei, für die die Ausgabe generiert werden muss. |
| ``outputName`` | Zeichenfolge | Name der für die Ausgabe zu verwendenden Ausgabevorgabe(n) Mehrere Ausgabevorgaben können mit einem senkrechten Strich (“\|&quot;\) angegeben werden, z. B. `aemsite\|pdfoutput`. |

**Ausnahme**:
Löst ``javax.jcr.RepositoryException``, `java.io.IOException` und `java.lang.Exception` aus.
