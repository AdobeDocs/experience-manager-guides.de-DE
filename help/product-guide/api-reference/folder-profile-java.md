---
title: Java-basierte API für die Arbeit mit Ordnerprofilen
description: Erfahren Sie mehr über die Java-basierte API für die Arbeit mit Ordnerprofilen
exl-id: 388ae654-c4f9-4bb7-ba98-370b8919e3a6
feature: Java-Based API Folder Profiles
role: Developer
level: Experienced
source-git-commit: 83966cc9187b13dd3b5956821e0aa038b41db28e
workflow-type: tm+mt
source-wordcount: '245'
ht-degree: 3%

---

# Java-basierte API für die Arbeit mit Ordnerprofilen {#id175UB30E05Z}

Mit der folgenden Java-basierten API können Sie bedingte Attribute zu einem Profil auf Ordnerebene hinzufügen. Diese API ist in Form eines Bundles verfügbar. Sie müssen dieses Bundle in Ihren Code aufnehmen, um diese APIs verwenden zu können.

Paketdetails:

- Gruppen-ID: **com.adobe.fmdita**

- Artefakt-ID: **api**

- Version: **3.2**

- Paket: **com.adobe.fmdita.api.profiles**

- Klassendetails:

  ```JAVA
  public class FolderProfileUtils extends Object
  ```

  Die Klasse **`FolderProfileUtils`** enthält eine Methode zum Hinzufügen bedingter Attribute zu einem Ordnerprofil.


## Hinzufügen bedingter Attribute zu einem Ordnerprofil

Die Methode ``addAttributeProfiles`` fügt einem Profil auf Ordnerebene bedingte Attribute hinzu.

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
| `labels` | Zeichenfolge | Eine Liste von Bezeichnungen für die `attribute` - `value`-Paare. [1](#fntarg_1) |
| `profileName` | Zeichenfolge | Der Name des Profils auf Ordnerebene, auf das diese Attribute, Werte und Beschriftungen angewendet werden müssen. **Wichtig:** Alle im Profil definierten vorhandenen attribute-values-label werden überschrieben. |
| `session` | javax.jcr.Session | Eine gültige JCR-Sitzung. |

**Gibt** zurück:
`true` für den Erfolg. Im Falle eines Fehlers wird eine Ausnahme ausgelöst.

**Exception**:
Gibt ``java.lang.Exception`` in den folgenden Szenarien aus:

- Wenn die API kein `resourceResolverFactory` -Objekt abrufen konnte. In diesem Fall sollten Sie das Bundle neu starten.
- Wenn an die API übergebene Parameter ungültig sind.
- Wenn die API über eine nicht autorisierte Benutzersitzung aufgerufen wird, z. B. der Benutzer, der kein Administrator für das angegebene Ordnerprofil ist.

[1](#fnsrc_1) Die `attributeNames`, `values` und `labels` am selben Index in einer Array-Liste müssen demselben Eintrag entsprechen.
