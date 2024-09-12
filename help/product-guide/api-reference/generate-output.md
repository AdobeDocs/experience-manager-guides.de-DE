---
title: Java-basierte API für die Verwendung mit der Ausgabegenerierung
description: Erfahren Sie mehr über die Java-basierte API für die Verwendung mit der Ausgabegenerierung.
exl-id: e19439df-39ec-47fd-9da5-24f51750a7e5
feature: Java-Based API Publishing
role: Developer
level: Experienced
source-git-commit: ee4eb829ebe215315b05cd1f376e934c02a73b1e
workflow-type: tm+mt
source-wordcount: '201'
ht-degree: 2%

---

# Java-basierte API für die Verwendung mit der Ausgabegenerierung {#id175UB30E05Z}

>[!NOTE]
>
> Sie können in Experience Manager Guides verfügbare Java-basierte APIs verwenden, um benutzerdefinierte Plug-ins zu erstellen und native Workflows zu erweitern. Dieser Artikel wird im November 2024 archiviert.
> Die aktuelle und detaillierte Dokumentation zur Verwendung der Java-basierten API finden Sie unter [![javadoc](https://javadoc.io/badge2/com.adobe.aem/aem-guides-sdk-api/javadoc.svg)](https://javadoc.io/doc/com.adobe.aem/aem-guides-sdk-api) .

Mit der folgenden Java-basierten API können Sie die Ausgabe für eine DITA-Zuordnung generieren. Diese API ist in Form eines Bundles verfügbar. Sie müssen dieses Bundle in Ihren Code aufnehmen, um diese APIs verwenden zu können.

Paketdetails:

- Gruppen-ID: **com.adobe.fmdita**

- Artefakt-ID: **api**

- Version: **3.4**

- Paket: ****com.adobe.fmdita.api.maps****

- Klassendetails:

  ```JAVA
  public class **PublishUtils** extends Object
  ```

  Die Klasse **`PublishUtils`** enthält eine Methode zum Generieren der Ausgabe für eine oder mehrere Ausgabevorgaben.


## Ausgabe generieren

Die Methode ``generateOutput`` generiert die Ausgabe für eine DITA-Map-Datei mithilfe der angegebenen Ausgabevorgaben.

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
| ``sourcePath`` | Zeichenfolge | Pfad \(im AEM Repository\) der DITA-Map-Datei, für die die Ausgabe generiert werden muss. |
| ``outputName`` | Zeichenfolge | Name der Ausgabevorgabe\(n\), die zum Generieren der Ausgabe verwendet werden soll. Es können mehrere Ausgabevorgaben mit einem senkrechten Strich (&quot;\|&quot;\) angegeben werden, z. B. &quot;`aemsite\|pdfoutput`&quot;. |

**Exception**:
Löst ``javax.jcr.RepositoryException``, `java.io.IOException` und `java.lang.Exception` aus.
