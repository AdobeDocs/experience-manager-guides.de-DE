---
title: Java-basierte API für die Verwendung mit der Ausgabegenerierung
description: Erfahren Sie mehr über die Java-basierte API für die Verwendung mit der Ausgabegenerierung.
exl-id: e19439df-39ec-47fd-9da5-24f51750a7e5
source-git-commit: 5e0584f1bf0216b8b00f00b9fe46fa682c244e08
workflow-type: tm+mt
source-wordcount: '160'
ht-degree: 0%

---

# Java-basierte API für die Verwendung mit der Ausgabegenerierung {#id175UB30E05Z}

Mit der folgenden Java-basierten API können Sie die Ausgabe für eine DITA-Zuordnung generieren. Diese API ist in Form eines Bundles verfügbar. Sie müssen dieses Bundle in Ihren Code aufnehmen, um diese APIs verwenden zu können.

Paketdetails:

- Gruppen-ID: **com.adobe.fmdita**

- Artefakt-ID: **api**

- Version: **3,4**

- Package: ****com.adobe.fmdita.api.maps****

- Klassendetails:

  ```JAVA
  public class **PublishUtils** extends Object
  ```

  Die **`PublishUtils`** -Klasse enthält eine Methode zum Generieren der Ausgabe für eine oder mehrere Ausgabevorgaben.


## Ausgabe generieren

Die ``generateOutput`` -Methode generiert die Ausgabe für eine DITA-Map-Datei mithilfe der angegebenen Ausgabevorgaben.

**Syntax**:

```JAVA
public static void generateOutput(Session session,
String sourcePath,
String outputName)
throws GuidesApiException
```

**Parameter**: |Name|Typ|Beschreibung| |—|—|—| |`session`|javax.jcr.Session|Eine gültige JCR-Sitzung.| |``sourcePath``|String|Pfad \(im AEM Repository\) der DITA-Map-Datei, für die die Ausgabe generiert werden muss.| |``outputName``|Zeichenfolge|Name der Ausgabevorgabe\(n\), die zum Generieren der Ausgabe verwendet werden soll. Es können mehrere Ausgabevorgaben mit einem senkrechten Strich (&quot;\|&quot;\) angegeben werden, z. B. `aemsite\|pdfoutput`.|

**Ausnahme**: Threads ``javax.jcr.RepositoryException``, `java.io.IOException`, und `java.lang.Exception`.
