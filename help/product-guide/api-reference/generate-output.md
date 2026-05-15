---
title: Java-basierte API für die Ausgabegenerierung
description: Erfahren Sie mehr über die Java-basierte API für die Verwendung bei der Ausgabegenerierung
exl-id: e19439df-39ec-47fd-9da5-24f51750a7e5
feature: Java-Based API Publishing
role: Developer
level: Experienced
TQID: https://experienceleague.adobe.com/i5mTM1VtBg3QFUa-sBmF2pH8BITRn9j-efw2dr8VwCU
product_v2: id: fae5e35a-80c9-4b94-9352-1a060a6aab1did: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2: id: a01bfd36-4ab8-4bf8-9dc0-5b45b890552eid: a3bd6397-2eb2-4908-a61c-226e26855dcaid: c6d09140-3c91-45d3-b7ed-b681af752f43
subfeature_v2: id: fd6cc9e1-e5e5-494e-b7b1-a32f2d6cd7c9
role_v2: id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 225
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
| ``sourcePath`` | Zeichenfolge | Pfad \(im AEM-Repository\) der DITA-Zuordnungsdatei, für die die Ausgabe generiert werden muss. |
| ``outputName`` | Zeichenfolge | Name der für die Ausgabe zu verwendenden Ausgabevorgabe(n) Mehrere Ausgabevorgaben können mit einem senkrechten Strich (“\|&quot;\) angegeben werden, z. B. `aemsite\|pdfoutput`. |

**Ausnahme**:
Löst ``javax.jcr.RepositoryException``, `java.io.IOException` und `java.lang.Exception` aus.
