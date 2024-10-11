---
title: Versionshinweise | Neue Funktionen in Adobe Experience Manager Guides 2024.10.0Version
description: Erfahren Sie mehr über die neuen und verbesserten Funktionen in der Adobe Experience Manager Guides-Version 2024.10.0
role: Leader
source-git-commit: 545e51cbd970aa3df01a0fe2461a2e730c0db66a
workflow-type: tm+mt
source-wordcount: '1025'
ht-degree: 1%

---

# Neue Funktionen in der Version 2024.10.0 (Oktober 2024)

In diesem Artikel werden die neuen und verbesserten Funktionen behandelt, die mit der Adobe Experience Manager Guides as a Cloud Services-Version 2024.10.0 eingeführt wurden.

Eine Liste der in dieser Version behobenen Probleme finden Sie im Artikel [Behobene Probleme in Version 2024.10.0](fixed-issues-2024-10-0.md).

Erfahren Sie mehr über die [Upgrade-Anweisungen für die Version 2024.10.0](../release-info/upgrade-instructions-2024-10-0.md).


## Verbesserungen bei der Veröffentlichung

Die folgenden Verbesserungen der Inhaltsveröffentlichung wurden in Version 2024.10.0 vorgenommen:




### Verbesserungen bei der Veröffentlichung von Inhaltsfragmenten

Experience Manager Guides bietet außerdem einige hilfreiche Verbesserungen bei Inhaltsfragmenten:

- Mit Experience Manager Guides können Sie ein Thema oder dessen Elemente in einem Inhaltsfragment veröffentlichen.

- Sie können die Inhaltsfragmente eines Themas im Abschnitt **Ausgaben** in den **Dateieigenschaften** veröffentlichen und anzeigen.


- Sie können Inhaltsfragmentvarianten einfach erstellen, indem Sie Inhalte mit Bedingungen filtern, während Sie sie in einem Inhaltsfragment veröffentlichen.

- Verwenden Sie die neue Zuordnungsschnittstelle, um die Elemente einfach auszuwählen und in einem Inhaltsfragment zu veröffentlichen.

Jetzt ersetzt die Inhaltsfragmentveröffentlichung nur den zugeordneten Inhalt, anstatt das vollständige Inhaltsfragment zu überschreiben. Diese Funktion ermöglicht es einem Inhaltsfragment, Daten aus mehreren Quellen wie mehreren Themen oder dem Inhaltsfragment-Editor zu enthalten.

![Fügen Sie das Fragmentmodell und die Zuordnungsdetails im Dialogfeld &quot;Publish als Inhaltsfragment&quot;hinzu](assets/content-fragment-mapping.png)

Weitere Informationen finden Sie unter [Publish-Inhaltsfragmente](../user-guide/publish-content-fragment.md).


### Publish Experience Fragment-Varianten basierend auf Bedingungsfiltern

Mit Experience Manager Guides können Sie ein Thema oder dessen Elemente in einem Experience Fragment veröffentlichen. Jetzt können Sie auch Experience Fragment-Varianten erstellen, indem Sie die Bedingungs- oder DITAVAL-Filter verwenden und sie über verschiedene Kanäle oder für verschiedene Zielgruppen wiederverwenden.

Erfahren Sie mehr über das [Publish-Erlebnisfragmente](../user-guide/publish-experience-fragment.md).


### AEM Sites-Vorgabe wurde neu organisiert, um die Verwendung zu erleichtern

Die Einstellungen wurden neu angeordnet, damit Sie die Ausgabevorgabe schnell konfigurieren und die AEM Sites-Ausgabe generieren können.
Sie können die vorhandenen AEM Sites-Vorgaben erstellen, indem Sie im Dialogfeld **Neue Ausgabevorgabe** die Option **Alte Komponentenzuordnung verwenden** auswählen.

Zeigen Sie die Registerkarten **Allgemein**, **Inhalt** und **Querverweis** in den AEM Sites-Vorgaben an:
- **Allgemein**: Enthält die allgemeinen Konfigurationen zum Generieren der Ausgabe. Sie können den Site- und Ausgabepfad angeben, vorhandene Ausgabeseiten löschen oder überschreiben, die zuvor generierten Seiten für entfernte Themen löschen, die Designvorlage auswählen, die temporären Dateien beibehalten und den Nachbearbeitungs-Workflow festlegen.
- **Inhalt**: Enthält die Einstellungen, die für den Inhalt zur Ausgabegenerierung gelten. Sie können die Filter, die Grundlinie der DITA-Zuordnung und die Metadateneigenschaften für die Veröffentlichung auswählen.
- **Querverweise**: Diese Liste enthält Themen, die Querverweise mit Umfang =&quot;Peer&quot;enthalten. Sie können den Veröffentlichungskontext für eine Liste von Querverweisen mit scope=&quot;peer&quot; zu Themen angeben, die in anderen DITA-Maps verfügbar sind. Diese Registerkarte wird angezeigt, wenn Sie die Experience Manager Guides-Version (UUID) verwenden.



### Querverweise von AEM Sites-Vorgaben im Web Editor

Die neueste Verbesserung von Experience Manager Guides führt Querverweise in den AEM Sites-Vorgaben des Web Editors ein.
Querverweise in Experience Manager Guides helfen bei der Verbesserung der Inhaltsnavigation, der verbesserten Wiederverwendung von Inhalten und der Verbesserung des Benutzererlebnisses.


Sie können den Veröffentlichungskontext für eine Liste von Querverweisen auf Themen festlegen, die in anderen DITA-Maps mit scope=&quot;peer&quot; verfügbar sind. Beispielsweise enthält Thema 1 in Karte A einen Verweis auf Thema 2. Thema 2 kann in einer oder mehreren Maps vorhanden sein.  Sie können für jeden Link die übergeordnete Zuordnung und eine bestimmte Vorgabe oder die zuletzt veröffentlichte Ausgabe auswählen.

Wenn dasselbe Thema mehr als einmal in einer Datei referenziert wird, können Sie für jede Instanz einen anderen Veröffentlichungskontext hinzufügen. Dies bietet mehr Flexibilität und Kontrolle über den Inhalt. Zum Beispiel ist Thema 3 sowohl in Karte B als auch in Karte C vorhanden. Thema 1 enthält zwei Verweise auf Thema 3. Sie können Map B als übergeordnete Zuordnung für den ersten Link und Map C als übergeordnete Zuordnung für den zweiten Link auswählen.

![Veraltete AEM Sites-Vorgabe](assets/aem-sites-legacy.png)

*Geben Sie den Veröffentlichungskontext für die verknüpften Themen auf der Registerkarte **Querverweise**der Vorgabe **AEM Sites**an.*

Erfahren Sie mehr über [AEM Sites-Vorgaben](../user-guide/generate-output-aem-site.md).

### Option zur Auswahl einer flachen oder verschachtelten Dateihierarchie für die HTML5-Ausgabe

Jetzt können Sie mit Experience Manager Guides die flache Ordnerhierarchie für die temporären Dateien beibehalten, wobei der gesamte Inhalt im HTML5-Ausgabeformat veröffentlicht und in einem einzigen Ordner gespeichert wird.
Wenn Sie die Dateihierarchie nicht reduzieren möchten, wird die HTML5-Ausgabe in einer verschachtelten Ordnerhierarchie generiert. Dies bedeutet, dass die ursprüngliche Ordnerstruktur des Inhalts mit in Unterordner unterteilten Dateien in der Ausgabe repliziert wird. Diese verschachtelte Ordnerhierarchie ermöglicht eine komplexere Organisation und Kategorisierung von Dateien, was die Verwaltung und Navigation großer Datenmengen erleichtert.


Erfahren Sie mehr darüber, wie Sie [HTML5-Ausgabe generieren](../user-guide/generate-output-html5.md).


## Editor-Verbesserungen

Die folgenden Editor-Verbesserungen wurden in Version 2024.10.0 hinzugefügt:

### Schreibgeschützter Zugriff auf den Author- und Source-Modus für gesperrte Dateien

Wenn eine DITA- oder Markdown-Datei von einem anderen Benutzer gesperrt oder ausgecheckt wurde, können Sie den Inhalt nicht bearbeiten oder ändern. Neben der Vorschau können Sie sie auch als schreibgeschützte Datei im Author- oder Source-Modus anzeigen.
Im schreibgeschützten Modus können Sie den Inhalt zusammen mit den Tags und Attributen im Modus **Autor** oder **Source** anzeigen und die Dateieigenschaften bearbeiten.

Sie können auch auf die Ansicht **Layout** für schreibgeschützte DITA-Maps zugreifen.
>[!NOTE]
>
> Ihre Ordnerprofiladministratoren müssen *ui_config.json* aktualisieren, damit Sie harmonisch auf die schreibgeschützten Dateien im Author-, Source- und Layout-Modus zugreifen können.

![gesperrter Dateieditor](./assets/locked-file-editor.png)
*Zeigen Sie die gesperrten Dateien im Author- und Source-Modus an.*


Erfahren Sie, wie Sie &quot;[gesperrte Dateien im Author- und Source-Modus öffnen](../user-guide/web-editor-edit-topics.md#open-locked-files-in-author-and-source-modes)&quot;.


### Gruppierung von Bedingungen für eine erweiterte Inhaltsorganisation

Mit Experience Manager Guides können Sie jetzt Bedingungen gruppieren und in einer verschachtelten Hierarchie darstellen, sodass Sie einer Gruppe mehrere Bedingungen hinzufügen können. Durch die Gruppierung von Bedingungen können Sie diese besser organisieren und über Ihren Inhalt hinweg anwenden.

![Bedingungen, die in einer verschachtelten Hierarchie organisiert sind](assets/conditions-nested-hierarchy.png){width="300" align="left"}

Weitere Informationen zur Funktionsbeschreibung für **Bedingungen** finden Sie im Abschnitt [Linkes Bedienfeld](../user-guide/web-editor-features.md#id2051EA0M0HS) .




