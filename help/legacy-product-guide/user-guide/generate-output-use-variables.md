---
title: Verwenden von Variablen zum Festlegen der Optionen Zielpfad, Site-Name oder Dateiname
description: Erfahren Sie, wie Sie Variablen zum Festlegen der Optionen „Zielpfad“, „Site-Name“ oder „Dateiname“ verwenden. Kenntnis der in AEM Guides unterstützten vordefinierten Variablen.
feature: Publishing
role: User
hide: true
exl-id: 19d9121f-6b72-445c-a7d9-07f00026b654
source-git-commit: 1426cdaecdd358f06e76908b09330e65997e8452
workflow-type: tm+mt
source-wordcount: '409'
ht-degree: 0%

---

# Verwenden von Variablen zum Festlegen der Optionen Zielpfad, Site-Name oder Dateiname


Beim Generieren von Ausgaben in AEM Site oder PDFs können Sie Variablen verwenden, um die Optionen Zielpfad, AEM Site-Name oder PDF-Dateiname zu definieren. Sie können eine einzelne oder eine Kombination von Variablen verwenden, um diese Optionen zu definieren.

In der folgenden Tabelle sind die Variablen aufgeführt, die standardmäßig unterstützt werden:

| Variable | Endgültiger Zielpfad | Beispiel |
| --- | --- | --- |
| `${map_filename}` | Verwendet den Namen der DITA-Zuordnungsdateien , um den Zielpfad zu erstellen. | **DITA Map-Dateiname**:<br>`AEMGuides.ditamap`<br><br>**Zielpfad** konfiguriert als:<br>`/content/output/sites/${map_filename}`<br><br>**Endgültiger Ausgabespeicherort**:<br>`/content/output/sites/aemGuides/AEMGuides.html` |
| `${map_title}` | Verwendet den Titel der DITA-Zuordnung, um den Zielpfad zu erstellen. | **DITA-Map-Dateiname**:<br>`AEMGuides.ditamap`<br><br>**DITA-Map-Titel**:<br>`AEMGuides`<br><br>**Zielpfad** konfiguriert als:<br>`/content/output/sites/${map_title}`<br><br>**Endgültiger Ausgabespeicherort**:<br>`/content/output/sites/AEMGuides/AEMGuides.html` |
| `${preset_name}` | Verwendet den Namen der Ausgabevorgabe, um den Zielpfad zu erstellen. | **Name der Ausgabevorgabe**:<br>`AEM Guides PDF Output`<br><br>**Name der DITA-Zuordnungsdatei**:<br>`SampleDita.ditamap`<br><br>**Zielpfad** konfiguriert als:<br>`/content/output/sites/${preset_name}`<br><br>**Endgültiger Ausgabespeicherort**:<br>`/content/output/sites/AEM Guides PDF Output/SampleDita.html` |
| `${language_code}` | Verwendet den Sprachcode, in dem sich die Zuordnungsdatei befindet, um den Zielpfad zu erstellen. | **DITA-Zuordnungsdateiname**:<br>`SampleDita.ditamap`<br><br>**DITA-Zuordnungsdateipfad**:<br>`/content/dam/projects/AEM-Guides/en/user-guide/`<br><br>**Zielpfad** konfiguriert als:<br>`/content/output/sites/${language_code}`<br><br>**Endgültiger Ausgabespeicherort**:<br>`/content/output/sites/en/SampleDita.html` |
| `${map_parentpath}` | Verwendet den vollständigen Pfad der Zuordnungsdatei, um den Zielpfad zu erstellen.<br><br>**Hinweis**: Diese Variable kann nicht verwendet werden, um den AEM-Site- oder PDF-Dateinamen anzugeben. | **DITA-Zuordnungsdateiname**:<br>`SampleDita.ditamap`<br><br>**DITA-Zuordnungsdateipfad**:<br>`/content/dam/projects/AEM-Guides/en/user-guide`/<br><br>**Zielpfad** konfiguriert als:<br>`/content/output/sites/${map_parentpath}`<br><br>**Endgültiger Ausgabespeicherort**:<br>`/content/output/sites/content/dam/projects/AEM-Guides/en/user-guide/SampleDita.html` |
| `${path_after_langfolder}` | Verwendet den Pfad der Zuordnungsdatei nach dem Sprachordner, um den Zielpfad zu erstellen.<br><br>**Hinweis**: Diese Variable kann nicht verwendet werden, um den AEM-Site- oder PDF-Dateinamen anzugeben. | **DITA-Zuordnungsdateiname**:<br>`SampleDita.ditamap`<br><br>**DITA-Zuordnungsdateipfad**:<br>`/content/dam/projects/AEM-Guides/en/user-guide/`<br><br>**Zielpfad** konfiguriert als:<br>`/content/output/sites/${path\_after\_langfolder}`<br><br>**Endgültiger Ausgabespeicherort**:<br>`/content/output/sites/user-guide/SampleDita.html` |
| `${system_date}` | Verwendet das aktuelle Serverdatum, um den Zielpfad zu erstellen. | **DITA Map-Dateiname**: <br> `SampleDita.ditamap` <br><br> **DITA Map-Dateipfad:** <br> `/content/dam/projects/AEM-Guides/en/user-guide/` <br><br> **Zielpfad** wie folgt konfiguriert: <br> `/content/output/sites/${system_date}` <br> <br> **Endgültiger Ausgabespeicherort:** <br> /`content/output/sites/08252023/SampleDita.html` |
| `${system_time}` | Verwendet die aktuelle Serverzeit, um den Zielpfad zu erstellen. | **DITA Map Dateiname:** <br>`SampleDita.ditamap` <br> <br> **DITA Map-Dateipfad:** <br>`/content/dam/projects/AEM-Guides/en/user-guide/` <br><Br>**Zielpfad** konfiguriert als: <br> `/content/output/sites/${system_time}`<br><br>**Endgültiger Ausgabespeicherort:**<br>`/content/output/sites/055612/SampleDita.html` |

Darüber hinaus können Sie auch die für die DITA-Map- oder Bookmap-Datei definierten Metadaten als Variablen verwenden. Die Metadaten befinden sich unter dem Knoten `/jcr:content/metadata` der DITA-Map- oder Bookmap-Datei. Eine der im `/jcr:content/metadata` definierten Metadateneigenschaften ist beispielsweise `dc:title`. Sie können `${dc:title}` angeben, und der Wert des Titels wird in der endgültigen Ausgabe verwendet.
**Übergeordnetes Thema:**&#x200B;[ Ausgabegenerierung](generate-output.md)
