---
title: Vorhandenen DITA-Inhalt hochladen
description: Erfahren Sie, wie Sie vorhandene DITA-Inhalte hochladen
exl-id: 2b385eef-00a7-4c25-9e78-367a0c9e44ba
feature: Migration
role: Admin
level: Experienced
TQID: https://experienceleague.adobe.com/oVLPpwMXyeRGo-1QO553dthsza05mbnRIedaIYpQ1Vg
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2:
  - id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: a004cc84-67b9-4a33-a3a7-8ec7273ef4dc
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 511
ht-degree: 0%

---

# Vorhandenen DITA-Inhalt hochladen {#id176FF000JUI}

Wahrscheinlich hätten Sie ein Repository mit vorhandenen DITA-Inhalten, die Sie mit der AEM Guides verwenden möchten. Für solche vorhandenen Inhalte können Sie eine der unterstützten Methoden verwenden, die unter [Hinzufügen digitaler Assets zu Adobe Experience Manager as a Cloud Service Assets](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/assets/manage/add-assets.html) erläutert werden.

## Konfigurieren des UUID-Dateinamenmusters

Beim Importieren von Inhalten ist es nicht erforderlich, dass Ihre Dateinamen auf der UUID basieren. In einem System, das UUID-basierte Dateinamen verwendet, ist es obligatorisch, dass alle Dateien mit ihren UUIDs und nicht mit ihren ursprünglichen Dateinamen referenziert werden. Wenn eine importierte Datei keine UUID-basierten Dateinamen hat, können Sie das System so konfigurieren, dass seiner Dateieigenschaft eine UUID hinzugefügt wird. Diese UUID wird dann verwendet, um auf solche Dateien zu verweisen, bei denen die UUID nicht für die Benennung der Dateien verwendet wird.

Verwenden Sie die Anweisungen unter [Konfigurationsüberschreibungen](download-install-additional-config-override.md#), um die Konfigurationsdatei zu erstellen. Geben Sie in der Konfigurationsdatei die folgenden \(property\)-Details an, um das UUID-Dateinamenmuster zu konfigurieren:

| PID | Eigenschaftsschlüssel | Eigenschaftswert |
|---|------------|--------------|
| `com.adobe.fmdita.config.ConfigManager` | `uuid.regex` | Zeichenfolge, die den Regex für das UUID-Dateinamenmuster angibt. <br> Wenn eine Datei nicht dem angegebenen Muster folgt, wird eine UUID zur -Eigenschaft der Datei hinzugefügt und alle Verweise auf die Datei werden mit der der Datei zugewiesenen UUID aktualisiert. <br> **Standardwert**: `"^GUID-(?<id>.*)"` |

## Verwenden von cURL-Befehlen

Sie können cURL-Befehle auch verwenden, um einen Ordner in DAM zu erstellen, Dateien hochzuladen und Metadaten zum hochgeladenen Inhalt hinzuzufügen.

**Erstellen eines Ordners**

Führen Sie den folgenden Befehl aus, um einen Ordner im AEM-Repository zu erstellen:

```
curl --user <username>:<password> --data jcr:primaryType=sling:Folder "<server folder path>"
```

Geben Sie die folgenden Parameter an, um einen Ordner zu erstellen:

- `<username>:<passowrd>`: Geben Sie den Benutzernamen und das Kennwort für den Zugriff auf das AEM-Repository an. Dieser Benutzer muss über die Berechtigungen zum Erstellen von Ordnern verfügen.

- `jcr:primaryType=sling:Folder`: Geben Sie diesen *an* um eine Ressource vom Typ Ordner zu erstellen.

- `<server folder path>`: Vollständiger Ordnerpfad mit dem Namen des neuen Ordners, den Sie im AEM-Repository erstellen möchten. Wenn Sie beispielsweise den Pfad als `http://192.168.1.1:4502/content/dam/projects/AEM-Guides` angeben, wird der `AEM-Guides` im `projects` Ordner in DAM erstellt.


**Datei hochladen**

Führen Sie den folgenden Befehl aus, um eine Datei in das AEM-Repository hochzuladen:

```
curl --user <username>:<password> -T "<local file path>" "<server folder path>"
```

Geben Sie die folgenden Parameter zum Hochladen einer Datei an:

- `<username>:<passowrd>`: Geben Sie den Benutzernamen und das Kennwort für den Zugriff auf das AEM-Repository an. Dieser Benutzer muss über Schreibrechte für den `server folder path` verfügen.

- ``local file path``: Vollständiger Dateipfad auf Ihrem lokalen System, den Sie hochladen möchten.

- `<server folder path>`: Vollständiger Ordnerpfad auf dem AEM-Server, auf den Sie die Datei hochladen möchten.


**Metadaten hinzufügen**

Führen Sie den folgenden Befehl aus, um Metadaten zu einer Datei hinzuzufügen:

```
curl --user <username>:<password> -F<attribute name>=<value> <metadata node path>
```

Geben Sie die folgenden Parameter an, um Metadateninformationen hinzuzufügen:

- `<username>:<passowrd>`: Geben Sie den Benutzernamen und das Kennwort für den Zugriff auf das AEM-Repository an. Dieser Benutzer muss über Schreibrechte für den ``metadata node path`` verfügen.

- ``-F<attribute name>=<value>``: Der `<attribute name>` ist der Name des Metadatenattributs, z. B. `audience` und der `<value>` könnte `internal` sein. Sie können mehrere Name-Wert-Paare für Attribute angeben, die durch Leerzeichen getrennt sind.

- `<metadata node path>`: Vollständiger Ordnerpfad, einschließlich Dateiname und Metadatenknoten. Wenn Sie beispielsweise den Pfad als `http://192.168.1.1:4502/content/dam/projects/AEM-Guides/intro.xml/jcr:content/metadata` angeben, werden die angegebenen Metadateninformationen in `intro.xml` Datei festgelegt.


**Übergeordnetes Thema:**&#x200B;[&#x200B; Migrieren vorhandener Inhalte](migrate-content.md)
