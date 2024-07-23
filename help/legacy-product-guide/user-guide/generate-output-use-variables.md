---
title: Verwenden Sie Variablen zum Festlegen der Optionen "Zielpfad", "Site-Name"oder "Dateiname"
description: Erfahren Sie, wie Sie Variablen zum Festlegen der Optionen für Zielpfad, Site-Name oder Dateiname verwenden. Erfahren Sie mehr über native Variablen, die in AEM Guides unterstützt werden.
feature: Publishing
role: User
source-git-commit: 76c731c6a0e496b5b1237b9b9fb84adda8fa8a92
workflow-type: tm+mt
source-wordcount: '409'
ht-degree: 0%

---

# Verwenden Sie Variablen zum Festlegen der Optionen &quot;Zielpfad&quot;, &quot;Site-Name&quot;oder &quot;Dateiname&quot;


Beim Generieren von Ausgaben in AEM Site oder PDF können Sie Variablen verwenden, um die Optionen Zielpfad, AEM Site-Name oder PDF-Dateiname zu definieren. Sie können eine einzelne oder eine Kombination von Variablen verwenden, um diese Optionen zu definieren.

In der folgenden Tabelle sind die Variablen aufgeführt, die standardmäßig unterstützt werden:

| Variable | Endziel-Pfad | Beispiel |
| --- | --- | --- |
| `${map_filename}` | Verwendet den Namen der DITA-Map-Dateien, um den Zielpfad zu erstellen. | **DITA-map-Dateiname**:<br>`AEMGuides.ditamap`<br><br>**Zielpfad** konfiguriert als:<br>`/content/output/sites/${map_filename}`<br><br>**Endgültiger Ausgabespeicherort**:<br>`/content/output/sites/aemGuides/AEMGuides.html` |
| `${map_title}` | Verwendet den DITA-Map-Titel, um den Zielpfad zu erstellen. | **DITA-map-Dateiname**:<br>`AEMGuides.ditamap`<br><br>**DITA-map-Titel**:<br>`AEMGuides`<br><br>**Ziel-Pfad** konfiguriert als:<br>`/content/output/sites/${map_title}`<br><br>**Endgültiger Ausgabespeicherort**:<br>`/content/output/sites/AEMGuides/AEMGuides.html` |
| `${preset_name}` | Verwendet den Namen der Ausgabevorgabe, um den Zielpfad zu erstellen. | **Name der Ausgabevorgabe**:<br>`AEM Guides PDF Output`<br><br>**Dateiname der DITA-Zuordnung**:<br>`SampleDita.ditamap`<br><br>**Zielpfad**, konfiguriert als:<br>`/content/output/sites/${preset_name}`<br><br>**Endgültiger Ausgabespeicherort**:<br>`/content/output/sites/AEM Guides PDF Output/SampleDita.html` |
| `${language_code}` | Verwendet den Sprachcode, in dem sich die Map-Datei befindet, um den Zielpfad zu erstellen. | **DITA-map-Dateiname**:<br>`SampleDita.ditamap`<br><br>**DITA-map-Dateipfad**:<br>`/content/dam/projects/AEM-Guides/en/user-guide/`<br><br>**Zielpfad** konfiguriert als:<br>`/content/output/sites/${language_code}`<br><br>**Endgültiger Ausgabespeicherort**:<br>`/content/output/sites/en/SampleDita.html` |
| `${map_parentpath}` | Verwendet den vollständigen Pfad der Map-Datei, um den Zielpfad zu erstellen.<br><br>**Hinweis**: Diese Variable kann nicht verwendet werden, um den AEM Site-Namen oder PDF-Dateinamen anzugeben. | **DITA-map-Dateiname**:<br>`SampleDita.ditamap`<br><br>**DITA-map-Dateipfad**:<br>`/content/dam/projects/AEM-Guides/en/user-guide`/<br><br>**Zielpfad** konfiguriert als:<br>`/content/output/sites/${map_parentpath}`<br><br>**Endgültiger Ausgabespeicherort**:<br>`/content/output/sites/content/dam/projects/AEM-Guides/en/user-guide/SampleDita.html` |
| `${path_after_langfolder}` | Verwendet den Pfad der Map-Datei nach dem Sprachordner, um den Zielpfad zu erstellen.<br><br>**Hinweis**: Diese Variable kann nicht verwendet werden, um den AEM Site-Namen oder PDF-Dateinamen anzugeben. | **DITA-map-Dateiname**:<br>`SampleDita.ditamap`<br><br>**DITA-map-Dateipfad**:<br>`/content/dam/projects/AEM-Guides/en/user-guide/`<br><br>**Zielpfad** konfiguriert als:<br>`/content/output/sites/${path\_after\_langfolder}`<br><br>**Endgültiger Ausgabespeicherort**:<br>`/content/output/sites/user-guide/SampleDita.html` |
| `${system_date}` | Verwendet das aktuelle Server-Datum, um den Zielpfad zu erstellen. | **DITA map file name**: <br> `SampleDita.ditamap` <br><br> **DITA-Map-Dateipfad:** <br> `/content/dam/projects/AEM-Guides/en/user-guide/` <br><br> **Zielpfad** konfiguriert als: <br> `/content/output/sites/${system_date}` <br> <br> **Endgültiger Ausgabespeicherort:** <br> /`content/output/sites/08252023/SampleDita.html` |
| `${system_time}` | Verwendet die aktuelle Serverzeit zum Erstellen des Zielpfads. | **DITA-Map-Dateiname:** <br>`SampleDita.ditamap` <br> <br> **DITA-Map-Dateipfad:** <br>`/content/dam/projects/AEM-Guides/en/user-guide/` <br><Br>**Zielpfad** konfiguriert als: <br> `/content/output/sites/${system_time}`<br><br>**Endgültiger Ausgabespeicherort:**<br>`/content/output/sites/055612/SampleDita.html` |

Darüber hinaus können Sie auch die für die DITA-Map- oder Bookmap-Datei definierten Metadaten als Variablen verwenden. Die Metadaten finden Sie unter dem Knoten &quot;`/jcr:content/metadata`&quot;der DITA-Map- oder Bookmap-Datei. Beispielsweise ist eine der Metadateneigenschaften, die im Knoten `/jcr:content/metadata` definiert werden, `dc:title`. Sie können `${dc:title}` angeben und der Titelwert wird in der endgültigen Ausgabe verwendet.
**Übergeordnetes Thema:**[ Ausgabegenerierung](generate-output.md)
