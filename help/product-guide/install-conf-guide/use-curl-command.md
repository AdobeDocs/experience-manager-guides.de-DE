---
title: Verwenden von cURL-Befehlen
description: Erfahren Sie, wie Sie cURL-Befehle für hochgeladene Inhalte in Experience Manager Guides verwenden.
feature: Migration
role: Admin
level: Experienced
source-git-commit: 834959a6a0e22cd5d2b2c5d0e57ceb6d45c0c666
workflow-type: tm+mt
source-wordcount: '289'
ht-degree: 1%

---

# Verwenden von cURL-Befehlen

Sie können cURL-Befehle auch verwenden, um einen Ordner in DAM zu erstellen, Dateien hochzuladen und Metadaten zum hochgeladenen Inhalt hinzuzufügen.

## Erstellen eines Ordners

Führen Sie den folgenden Befehl aus, um einen Ordner im AEM-Repository zu erstellen:

```curl
curl --user <username>:<password> --data jcr:primaryType=sling:Folder "<server folder path>"
```

Geben Sie die folgenden Parameter an, um einen Ordner zu erstellen:

- `<username>:<passowrd>`: Geben Sie den Benutzernamen und das Kennwort für den Zugriff auf das AEM-Repository an. Dieser Benutzer muss über die Berechtigungen zum Erstellen von Ordnern verfügen.

- `jcr:primaryType=sling:Folder`: Geben Sie diesen *an* um eine Ressource vom Typ Ordner zu erstellen.

- `<server folder path>`: Vollständiger Ordnerpfad mit dem Namen des neuen Ordners, den Sie im AEM-Repository erstellen möchten. Wenn Sie beispielsweise den Pfad als `http://192.168.1.1:4502/content/dam/projects/AEM-Guides` angeben, wird der `AEM-Guides` im `projects` Ordner in DAM erstellt.


## Datei hochladen

Führen Sie den folgenden Befehl aus, um eine Datei in das AEM-Repository hochzuladen:

```curl
curl --user <username>:<password> -T "<local file path>" "<server folder path>"
```

Geben Sie die folgenden Parameter zum Hochladen einer Datei an:

- `<username>:<passowrd>`: Geben Sie den Benutzernamen und das Kennwort für den Zugriff auf das AEM-Repository an. Dieser Benutzer muss über Schreibrechte für den `server folder path` verfügen.

- ``local file path``: Vollständiger Dateipfad auf Ihrem lokalen System, den Sie hochladen möchten.

- `<server folder path>`: Vollständiger Ordnerpfad auf dem AEM-Server, auf den Sie die Datei hochladen möchten.


## Metadaten hinzufügen

Führen Sie den folgenden Befehl aus, um Metadaten zu einer Datei hinzuzufügen:

```curl
curl --user <username>:<password> -F<attribute name>=<value> <metadata node path>
```

Geben Sie die folgenden Parameter an, um Metadateninformationen hinzuzufügen:

- `<username>:<passowrd>`: Geben Sie den Benutzernamen und das Kennwort für den Zugriff auf das AEM-Repository an. Dieser Benutzer muss über Schreibrechte für den ``metadata node path`` verfügen.

- ``-F<attribute name>=<value>``: Der `<attribute name>` ist der Name des Metadatenattributs, z. B. `audience` und der `<value>` könnte `internal` sein. Sie können mehrere Name-Wert-Paare für Attribute angeben, die durch Leerzeichen getrennt sind.

- `<metadata node path>`: Vollständiger Ordnerpfad, einschließlich Dateiname und Metadatenknoten. Wenn Sie beispielsweise den Pfad als `http://192.168.1.1:4502/content/dam/projects/AEM-Guides/intro.xml/jcr:content/metadata` angeben, werden die angegebenen Metadateninformationen in `intro.xml` Datei festgelegt.