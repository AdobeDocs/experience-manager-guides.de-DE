---
title: Versionshinweise zu | Neue Funktionen in Adobe Experience Manager Guides Version 2024.10.0
description: Erfahren Sie mehr über die neuen und erweiterten Funktionen der Version 2024.10.0 von Adobe Experience Manager Guides
role: Leader
exl-id: 13135928-f0fe-4147-83ac-8b06ca241ed7
source-git-commit: 682eaf6f4a3a158f49a8f2ea91ce9cd2de3ff772
workflow-type: tm+mt
source-wordcount: '1025'
ht-degree: 1%

---

# Neue Funktionen in der Version 2024.10.0 (Oktober 2024)

Dieser Artikel behandelt die neuen und erweiterten Funktionen, die mit Version 2024.10.0 von Adobe Experience Manager Guides as a Cloud Service eingeführt wurden.

Eine Liste der in dieser Version behobenen Probleme finden Sie im Artikel [Behobene Probleme in Version 2024.10.0](fixed-issues-2024-10-0.md).

Erfahren Sie mehr [Upgrade-Anweisungen für die Version 2024.10.0](../release-info/upgrade-instructions-2024-10-0.md).


## Verbesserungen beim Veröffentlichen

In der Version 2024.10.0 wurden die folgenden Inhaltsveröffentlichungsverbesserungen vorgenommen:




### Verbesserungen bei der Veröffentlichung von Inhaltsfragmenten

Experience Manager Guides bietet auch einige hilfreiche Verbesserungen bei Inhaltsfragmenten:

- Mit Experience Manager Guides können Sie ein Thema oder seine Elemente in einem Inhaltsfragment veröffentlichen.

- Sie können die Inhaltsfragmente eines Themas veröffentlichen und im Abschnitt **Ausgaben** der Seite **Dateieigenschaften** anzeigen.


- Sie können auf einfache Weise Varianten von Inhaltsfragmenten erstellen, indem Sie Inhalte beim Veröffentlichen in einem Inhaltsfragment nach Bedingungen filtern.

- Verwenden Sie die neue Zuordnungsschnittstelle, um die Elemente einfach auszuwählen und in einem Inhaltsfragment zu veröffentlichen.

Jetzt ersetzt die Veröffentlichung von Inhaltsfragmenten nur den zugeordneten Inhalt, anstatt das gesamte Inhaltsfragment zu überschreiben. Mit dieser Funktion kann ein Inhaltsfragment Daten aus mehreren Quellen enthalten, z. B. aus mehreren Themen oder aus dem Inhaltsfragment-Editor.

![Fügen Sie das Fragmentmodell und die Zuordnungsdetails im Dialogfeld Publish als Inhaltsfragment hinzu](assets/content-fragment-mapping.png)

Weitere Informationen finden Sie unter [Publish-Inhaltsfragmente](../user-guide/publish-content-fragment.md).


### Varianten von Publish Experience Fragments basierend auf Bedingungsfiltern

Mit Experience Manager Guides können Sie ein Thema oder seine Elemente in einem Experience Fragment veröffentlichen. Jetzt können Sie Experience Fragment-Varianten auch mithilfe der Bedingungs- oder DITAVAL-Filter erstellen und über verschiedene Kanäle oder für verschiedene Zielgruppen hinweg wiederverwenden.

Weitere Informationen zum [Erstellen von Publish Experience Fragments](../user-guide/publish-experience-fragment.md).


### AEM Sites-Voreinstellung neu angeordnet für einfache Verwendung

Die Einstellungen wurden neu angeordnet, damit Sie die Ausgabevorgabe schnell konfigurieren und die AEM Sites-Ausgabe generieren können.
Sie können die vorhandenen AEM Sites-Vorgaben erstellen, indem Sie die Option **Alte Komponentenzuordnung verwenden** im Dialogfeld **Neue**&quot; auswählen.

Zeigen Sie die Registerkarten **Allgemein**, **Inhalt** und **Kartenreferenz** in den AEM Sites-Vorgaben an:
- **Allgemein**: Enthält die allgemeinen Konfigurationen zum Generieren der Ausgabe. Sie können die Site und den Ausgabepfad angeben, vorhandene Ausgabeseiten löschen oder überschreiben, die zuvor generierten Seiten für entfernte Themen löschen, die Design-Vorlage auswählen, die temporären Dateien beibehalten und den Nachgenerierungs-Workflow angeben.
- **Content**: Enthält die Einstellungen, die für den Inhalt für die Ausgabegenerierung gelten. Sie können die Filter, die Baseline der DITA-Zuordnung und die Metadateneigenschaften für die Veröffentlichung auswählen.
- **Cross-Map-Verweise**: Diese Liste enthält Themen mit Cross-Map-Verweisen mit scope =„peer“. Sie können den Veröffentlichungskontext für eine Liste von Querverweisen mit scope=„peer“ zu Themen angeben, die in anderen DITA-Zuordnungen verfügbar sind. Diese Registerkarte wird angezeigt, wenn Sie die Experience Manager Guides-Version (UUID) verwenden.



### Kreuzzuordnungsverweise aus AEM Sites-Vorgaben im Web-Editor

Die neueste Verbesserung an Experience Manager Guides führt Querverweisreferenzen in den AEM Sites-Vorgaben des Web-Editors ein.
Querverweise auf Zuordnungen in Experience Manager Guides helfen, die Inhaltsnavigation zu verbessern, die Wiederverwendung von Inhalten zu steigern und das Benutzererlebnis zu verbessern.


Mit scope=„peer“ können Sie den Veröffentlichungskontext für eine Liste von Querverweisen auf Themen angeben, die in anderen DITA-Zuordnungen verfügbar sind. Beispielsweise enthält Thema 1 in Karte A einen Verweis auf Thema 2. Thema 2 kann in einzelnen oder mehreren Karten vorhanden sein.  Sie können für jeden Link die übergeordnete Zuordnung und eine bestimmte Vorgabe oder die zuletzt veröffentlichte Ausgabe auswählen.

Wenn dasselbe Thema mehrmals in einer Datei referenziert wird, können Sie für jede Instanz einen anderen Veröffentlichungskontext hinzufügen. Dies bietet mehr Flexibilität und Kontrolle über ihre Inhalte. Beispielsweise ist Thema 3 sowohl in Karte B als auch in Karte C vorhanden. Thema 1 enthält zwei Verweise auf Thema 3. Sie können Zuordnung B als übergeordnete Zuordnung für den ersten Link und Zuordnung C als übergeordnete Zuordnung für den zweiten Link auswählen.

![Alte AEM Sites-Vorgabe](assets/aem-sites-legacy.png)

*Geben Sie auf der Registerkarte **Cross-Map-Referenzen**&#x200B;der Vorgabe **AEM Sites**&#x200B;den Veröffentlichungskontext für die verknüpften Themen an.*

Weitere Informationen zu [AEM Sites-Vorgaben](../user-guide/generate-output-aem-site.md).

### Option zur Auswahl einer flachen oder verschachtelten Dateihierarchie für die HTML5-Ausgabe

Jetzt können Sie mit Experience Manager Guides die flache Ordnerhierarchie für die temporären Dateien beibehalten, bei denen der gesamte Inhalt im HTML5-Ausgabeformat veröffentlicht und in einem einzigen Ordner gespeichert wird.
Wenn Sie die Dateihierarchie nicht reduzieren möchten, wird die HTML5-Ausgabe in einer verschachtelten Ordnerhierarchie generiert. Dies bedeutet, dass die ursprüngliche Ordnerstruktur des Inhalts mit Dateien, die in Unterordnern organisiert sind, in der Ausgabe repliziert wird. Diese verschachtelte Ordnerhierarchie ermöglicht eine komplexere Organisation und Kategorisierung von Dateien, wodurch die Verwaltung und Navigation großer Datenmengen erleichtert wird.


Erfahren Sie mehr über das [Generieren einer HTML5-Ausgabe](../user-guide/generate-output-html5.md).


## Verbesserungen am Editor

In der Version 2024.10.0 wurden die folgenden Editor-Verbesserungen hinzugefügt:

### Schreibgeschützter Zugriff auf den Authoring- und Source-Modus für gesperrte Dateien

Wenn eine DITA- oder Markdown-Datei von einem anderen Benutzer gesperrt oder ausgecheckt wird, können Sie den Inhalt nicht bearbeiten oder ändern. Neben der Vorschau können Sie sie auch als schreibgeschützte Datei im Authoring- oder Source-Modus anzeigen.
Im schreibgeschützten Modus können Sie den Inhalt zusammen mit den Tags und Attributen im Modus **Author** oder **Source** anzeigen und die Dateieigenschaften bearbeiten.

Sie können auch auf die **Layout**-Ansicht für schreibgeschützte DITA-Zuordnungen zugreifen.
>[!NOTE]
>
> Ihre Ordnerprofiladministrierenden müssen *ui_config.json* aktualisieren, damit Sie im Autoren-, Source- und Layout-Modus einheitlich auf die schreibgeschützten Dateien zugreifen können.

![Gesperrter Datei-Editor](./assets/locked-file-editor.png)
*Anzeigen der gesperrten Dateien im Authoring- und Source-Modus.*


Erfahren Sie, wie [ Dateien im Authoring- und Source-Modus öffnen ](../user-guide/web-editor-edit-topics.md#open-locked-files-in-author-and-source-modes).


### Gruppierte Bedingungen für die erweiterte Inhaltsorganisation

Mit Experience Manager Guides können Sie jetzt Bedingungen gruppieren und in einer verschachtelten Hierarchie darstellen, sodass Sie einer einzigen Gruppe mehrere Bedingungen hinzufügen können. Durch Gruppieren von Bedingungen können Sie diese besser organisieren und auf Ihre gesamten Inhalte anwenden.

![Bedingungen in einer verschachtelten Hierarchie organisiert](assets/conditions-nested-hierarchy.png){width="300" align="left"}

Weitere Informationen zur Funktionsbeschreibung **Bedingungen** finden Sie im Abschnitt [Linkes ](../user-guide/web-editor-features.md#id2051EA0M0HS)).
