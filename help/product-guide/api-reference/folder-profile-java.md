---
title: Java-basierte API zum Arbeiten mit Ordnerprofilen
description: Erfahren Sie mehr über die Java-basierte API zum Arbeiten mit Ordnerprofilen
exl-id: 388ae654-c4f9-4bb7-ba98-370b8919e3a6
feature: Java-Based API Folder Profiles
role: Developer
level: Experienced
source-git-commit: 8c80a4da8e61909aab0f2db81ef97149774b36c4
workflow-type: tm+mt
source-wordcount: '286'
ht-degree: 3%

---

# Java-basierte API zum Arbeiten mit Ordnerprofilen {#id175UB30E05Z}

>[!NOTE]
>
> Sie können die in Experience Manager Guides verfügbaren Java-basierten APIs verwenden, um benutzerdefinierte Plug-ins zu erstellen und vordefinierte Workflows zu erweitern. Dieser Artikel wird im November 2024 archiviert.
> In [![javadoc](https://javadoc.io/badge2/com.adobe.aem/aem-guides-sdk-api/javadoc.svg)](https://javadoc.io/doc/com.adobe.aem/aem-guides-sdk-api) finden Sie die neueste und detaillierte Dokumentation zur Verwendung der Java-basierten API.




Mit der folgenden Java-basierten API können Sie einem Profil auf Ordnerebene bedingte Attribute hinzufügen. Diese API ist in Form eines Bundles verfügbar. Sie müssen dieses Bundle in Ihren Code aufnehmen, um diese APIs verwenden zu können.

Paketdetails:

- Gruppen-ID: **com.adobe.fmdita**

- Artefakt-ID: **api**

- Version: **.2**

- Paket: **com.adobe.fmdita.api.profiles**

- Klassendetails:

  ```JAVA
  public class FolderProfileUtils extends Object
  ```

  Die **`FolderProfileUtils`**-Klasse enthält eine Methode zum Hinzufügen bedingter Attribute in einem Ordnerprofil.


## Hinzufügen bedingter Attribute zu einem Ordnerprofil

Die ``addAttributeProfiles``-Methode fügt einem Profil auf Ordnerebene bedingte Attribute hinzu.

**Syntax**:

```JAVA
public static boolean addAttributeProfiles
(List
<String> attributeNames, 
List
    <String> values, 
List
        <String> labels,
String profileName, 
Session session) throws GuidesApiException
```

**Parameter**:

| Name | Typ | Beschreibung |
|----|----|-----------|
| ``attributeNames`` | Zeichenfolge | Eine Liste von Attributnamen. |
| ``values`` | Zeichenfolge | Eine Liste von Werten für die angegebenen Attribute. |
| `labels` | Zeichenfolge | Eine Liste von Beschriftungen für die `attribute`- `value`. [1](#fntarg_1) |
| `profileName` | Zeichenfolge | Der Name des Profils auf Ordnerebene, auf das diese Attribute, Werte und Beschriftungen angewendet werden müssen. **Wichtig:** Alle im Profil definierten vorhandenen Attribute-Werte-Bezeichnungen werden überschrieben. |
| `session` | javax.jcr.Session | Eine gültige JCR-Sitzung. |

**Rückgabe**:
`true` für den Erfolg. Im Falle eines Fehlers wird eine Ausnahme ausgelöst.

**Ausnahme**:
Löst ``java.lang.Exception`` in den folgenden Szenarien aus:

- Wenn die API `resourceResolverFactory` Objekt nicht abrufen konnte. In diesem Fall sollten Sie das Bundle neu starten.
- Wenn an die API übergebene Parameter ungültig sind.
- Wenn die API über eine nicht autorisierte Benutzersitzung aufgerufen wird, z. B. über den Benutzer, der für das angegebene Ordnerprofil kein Administrator ist.

[1](#fnsrc_1) Die `attributeNames`, `values` und `labels` im selben Index in einer Array-Liste müssen demselben Eintrag entsprechen.
