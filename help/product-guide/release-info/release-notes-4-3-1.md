---
title: Versionshinweise | Aktualisierungsanweisungen und behobene Probleme in Adobe Experience Manager Guides Version 4.3.1
description: Erfahren Sie mehr über die Fehlerbehebungen und das Upgrade auf Version 4.3.1 von Adobe Experience Manager Guides.
exl-id: 3fb6dc31-ec6e-40f5-ab3f-a6e591da315e
feature: Release Notes
role: Leader
source-git-commit: 1b25f1df67fa2442ab79830dc2ac5a6eabd0394c
workflow-type: tm+mt
source-wordcount: '1308'
ht-degree: 1%

---

# Version 4.3.1 von Adobe Experience Manager Guides (Oktober 2023)

In diesem Versionshinweis werden die Aktualisierungsanweisungen, die Kompatibilitätsmatrix und die in Version 4.3.1 von Adobe Experience Manager Guides behobenen Probleme (später als *Experience Manager Guides*) behandelt.

Weitere Informationen zu den neuen Funktionen und Verbesserungen finden Sie unter [Neue Funktionen in Version 4.3.1 von Adobe Experience Manager Guides](./whats-new-4-3-1-release.md).

## Aktualisierung auf Version 4.3.1 von Experience Manager Guides


Sie können Ihre aktuelle Version von Experience Manager Guides einfach auf Version 4.3.1 aktualisieren. Bevor Sie mit der Aktualisierung auf Version 4.3.1 von Experience Manager Guides fortfahren, müssen Sie die folgenden Punkte beachten:
Sie können Ihre aktuelle Version von Experience Manager Guides auf Version 4.3.1 aktualisieren.


- Wenn Sie Version 4.3.0, 4.2 oder 4.2.1 verwenden, können Sie direkt auf Version 4.3.1 aktualisieren.
- Wenn Sie Version 4.1 oder 4.1.x verwenden, müssen Sie auf Version 4.3.0, 4.2 oder 4.2.x aktualisieren, bevor Sie auf Version 4.3.1 aktualisieren.
- Wenn Sie Version 4.0 verwenden, müssen Sie vor der Aktualisierung auf Version 4.3.1 auf Version 4.2 aktualisieren.
- Wenn Sie Version 3.8.5 verwenden, müssen Sie auf Version 4.0 aktualisieren, bevor Sie auf Version 4.2 aktualisieren.
- Wenn Sie eine Version vor Version 3.8.5 verwenden, lesen Sie den Abschnitt &quot;Aktualisieren von Experience Manager Guides&quot;im produktspezifischen Installationshandbuch.


>[!NOTE]
>
>Sie müssen AEM Service Pack installieren, bevor Sie die Experience Manager Guides-Version aktualisieren.

Weitere Informationen finden Sie unter [Upgrade-Anweisungen](../install-guide/upgrade-xml-documentation.md).

## Kompatibilitätsmatrix

In diesem Abschnitt wird die Kompatibilitätsmatrix für die von Experience Manager Guides 4.3.1 unterstützten Softwareanwendungen aufgeführt.

### Adobe Experience Manager

**4.3.1 Nicht-UUID**
Version 6.5 Service Pack 18, 17, 16, 15 oder 14

**4.3.1 UUID**
Version 6.5 Service Pack 18, 17, 16, 15 oder 14

Weitere Informationen finden Sie im Abschnitt *Technische Anforderungen* im Handbuch &quot;Installieren und Konfigurieren von Adobe Experience Manager Guides&quot;.

### FrameMaker und FrameMaker Publishing Server

| Freigabe | FMPS 2022 | FMPS 2020 | FM 2022 | FM 2020 |
| --- | --- | --- | --- | --- |
| 4.3.1 (Nicht-UUID) | 2022 oder höher | 2020.2 oder höher* | 2022 oder höher | 2020.3 oder höher |
| 4.3.1 (UUID) | 2022 oder höher | 2020.2 oder höher* | 2022 oder höher | 2020.4 oder höher |
| | | | |

*Die in AEM erstellten Grundlinien und Bedingungen werden in FMPS-Versionen ab 2020.2 unterstützt.

### Sauerstoffanschluss

| Freigabe | Sauerstoff Connector Windows | Sauerstoff Connector Mac | In Oxygen Windows bearbeiten | In Oxygen Mac bearbeiten |
| --- | --- | --- |--- |--- |
| 4.3.1 (Nicht-UUID) | 2.3-normal-5 | 2.3-normal-5 | 1,6 | 1,6 |
| 4.3.1 (UUID) | 3.2-uuid-5 | 3.2-uuid-5 | 2,3 | 2,3 |
|  |  |   |



### Knowledgebase-Vorlagenversion

| Name des Komponentenpakets | Komponentenversion | Vorlagenversion |
|---|---|---|
| Experience Manager Guides Components Content Package for Cloud Service | dxml-components.all-1.2.2 | aem-site-template-dxml.all-1.0.15 |

## Behobene Probleme

Die in verschiedenen Bereichen behobenen Fehler sind unten aufgeführt:

### Authoring

- Nachmittagsstunden werden nicht im **Datum** für die Erstellung von Grundlinien festgelegt. (12712)
- Der JSON-Code kann nicht in das Element `<codeblock>` des Web-Editors eingefügt werden. (12326)
- Nicht gespeicherte Versionsänderungen und die zugehörigen Indikatoren werden nicht für große Dateien angezeigt. (11784)
- Bei der Bearbeitung in koreanischer Sprache wird das erste Zeichen in den Standard geändert. (10049)

- Das Präfix wird im Vorschaumodus des Web-Editors dupliziert. (13133)
- `Choicetable` -Zeilen werden nicht angezeigt oder können nicht ausgewählt werden. (12616)
- Der Web Editor gibt bei der Erstellung eines Themas mit einem benutzerdefinierten Schema in bestimmten Szenarien Validierungsfehler aus. (12576)
- Die Referenzen auf die ditaval-Themenvorlage erstellen beim Erstellen einer Zuordnung aus der Zuordnungsvorlage keine Kopie im Inhaltsordner. (12150)

- Das Suchfeld in DITA-Maps hat keine Schließen-Schaltfläche. (11867)
- Beim Speichern langer Dateien im Web Editor gibt `DirtyChecker` eine Ausnahme mit einer langen Stacktrace aus und füllt die Protokolldateien. (11860)
- Für das Erstellen von DITA-Themen ist eine Löschberechtigung für den entsprechenden Ordnerknoten erforderlich, obwohl die Zuordnung mit Schreibberechtigung erstellt werden kann. (11706)
- Der Web Editor zeigt einen falschen Titel an, wenn ein Schrägstrich vorhanden ist. (10949)

- Wenn der Titel eines Themas einen Schrägstrich (/) enthält, werden auf der Registerkarte im Editor nur die folgenden Buchstaben angezeigt. (13455)
- Die Bildvorschau wird nach der Anzeige der Vorschau im Editor nicht ausgeblendet. (13454)
- Einige der vorhandenen Versionen oder deren Beschriftungen werden nach dem Upgrade auf 4.x nicht im Versionsverlauf angezeigt. (13247)
- Der Bereich Versionsverlauf in der Benutzeroberfläche von Assets zeigt einen falschen Zeitstempel für das Feld **Aktuell** an. (12624)
- Das Thema mit conref title wird in der Repository-Ansicht oder Kartenansicht nicht aufgelöst.(13304)


### Veröffentlichung

- Native PDF | Die Reihenfolge der Themen wird bei der Erzeugung der PDF-Ausgabe nicht festgelegt. (13157)
- Native PDF| Für das Element `<p>`ist kein standardmäßiges Stil-Tag verfügbar. (12559)
- Native PDF | Inline-Stile, die auf den Inhaltsbereich angewendet werden, werden nicht auf die Themen in der Vordergrund- und in der Rückseite angewendet. (13510)
- Das Attribut `DeliveryTarget` wird beim Generieren der AEM Site-Ausgabe nicht übernommen.  (13132)
- Der Arbeitsablauf **Publish** hängt beim Generieren AEM Site-Ausgabe für Inhalte mit bestimmten Fehlern. (12000)

- Native PDF | Durch die Verwendung mehrerer xrefs wird der Text über die Spaltenbreite hinaus erweitert. (13004)
- Native PDF | Wenn das Thema und der Titel dieselbe ID aufweisen, führt dies zu einer fehlerhaften Generierung der PDF-Ausgabe. (12644)
- Native PDF | Beim Hinzufügen einer Ausgabeklasse zu einem übergeordneten Element `<topicref>` in einer DITA-Zuordnung und Anwenden eines benutzerdefinierten Stils auf die Ausgabeklasse wird der Stil auf Elemente im Themenhauptteil angewendet, einschließlich Abschnittstiteln. (12166)
- Inkrementelle Veröffentlichung funktioniert nicht, wenn eine DITA-Map über mehrere Ditavalrefs verfügt. (12117)
- AEM Site | Beim Erstellen einer Zuordnung mit Keydef, die auf ein Thema als Variable verweist, und beim Hinzufügen von processing-role=resource-only werden einige unerwartete Seiten erstellt. (1209)
- Wenn Assets aus AEM DAM in einer anderen Ausgabe als der AEM-Site verwendet werden, spiegeln die Metadaten &quot;jcr:createdBy&quot;nicht den Namen des Herausgebers oder den Namen des Benutzers wider, der die DITA-Zuordnung oder das Thema zuletzt geändert hat. (12090)
- AEM Sites | DITA-Zuordnung mit topichead im Navigationstitel (mit nicht unterstützten Zeichen) führt zu fehlerhaften Seiten-URLs. (1978)
- Native PDF | Probleme treten zur Unterstützung von topichead/topicmeta/navtitle in Frontmatter und Backmatter auf. (1969)
- Native PDF | Das Generieren von PDF für große Dokumente ist zeitaufwendig. (11955)
- Native PDF | Beim Umbenennen einer Vorgabe wird beim Generieren einer PDF-Ausgabe eine NullPointerException ausgelöst. (11889)
- Der Inhalt von `<conref>` wird nicht in der PDF-Ausgabe angezeigt. (11131)
- Innerhalb der `<div>` -Elemente wird beim Umschalten zwischen der Autoren- und der Source-Ansicht im Seitenlayout-Editor ein zusätzlicher Platz hinzugefügt. (10750)
- Der im AEM Cloud Manager replizierte Inhalt ist nicht in der Publish-Instanz sichtbar. 9564


### Verwaltung

- Der Versionsverlauf wird nicht angezeigt, selbst wenn die Eigenschaft `dc:format` für ein Asset nicht vorhanden ist. (10463)
- Der Inhaltsverweis ist beim Kopieren und Einfügen von DITA-Dateien beschädigt, wenn die Themen-ID nicht mit der GUID übereinstimmt. (12614)
- In dynamischen Grundlinien wird die Liste der Beschriftungen nicht aus den direkten Verweisen der Arbeitskopie einer DITA-Zuordnung abgerufen. (1917)
- Die Grundlinie zeigt die falsche Anzahl von Dateien im Map Dashboard an, wenn die Funktion &quot;Alle Themen durchsuchen&quot;verwendet wird. (13265)
- Im Web-Editor zeigt die Grundlinie den Titel der vorherigen Version anstelle der ausgewählten Version der DITA-Datei an. (13444)

### Überprüfung

- Die Themenüberprüfung zeigt falsche Kommentare an. (13453)
- Über die Schaltfläche Schließen auf der Überprüfungsseite in Experience Manager Guides gelangen die Benutzer zur AEM-Startseite. (13535)
- Anlagen werden nicht im rechten Bereich des Editors für ein Thema im Review angezeigt. (13011)



### Übersetzung

- Die vom Dashboard **Übersetzung** exportierte Grundlinie schlägt fehl und wird nicht in der Zielsprache geöffnet. (13466)

- Anstatt den ausgewählten Übersetzungsprojekten neue Aufträge hinzuzufügen, werden neue Übersetzungsprojekte erstellt.  (10214)
- Der Titel der übersetzten Datei wird anstelle des Titels der Quelldatei angezeigt. (11630)
- Die automatische Genehmigung funktioniert manchmal nicht und es treten Ausnahmen auf, wenn für den Übersetzungsstatus ein falscher Wert festgelegt ist. (13607)
- Die über das Dashboard &quot;Übersetzung&quot;exportierte Grundlinie schlägt fehl und wird nicht in der Zielsprache geöffnet. (12993)
- Einige Dateien fehlen bei der Verwendung von Grundlinien in der Übersetzung. (13021)
