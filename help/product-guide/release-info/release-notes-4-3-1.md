---
title: Versionshinweise zu | Upgrade-Anweisungen und behobene Probleme in Adobe Experience Manager Guides Version 4.3.1
description: Erfahren Sie mehr über die Fehlerbehebungen und das Upgrade auf Version 4.3.1 von Adobe Experience Manager Guides
exl-id: 3fb6dc31-ec6e-40f5-ab3f-a6e591da315e
feature: Release Notes
role: Leader
source-git-commit: 1b25f1df67fa2442ab79830dc2ac5a6eabd0394c
workflow-type: tm+mt
source-wordcount: '1308'
ht-degree: 1%

---

# Version 4.3.1 von Adobe Experience Manager Guides (Oktober 2023)

Diese Versionshinweise enthalten die Upgrade-Anweisungen, die Kompatibilitätsmatrix und behobene Probleme in Version 4.3.1 von Adobe Experience Manager Guides (später als *Experience Manager Guides* bezeichnet).

Weitere Informationen zu den neuen Funktionen und Verbesserungen finden Sie unter [Neue Funktionen in Version 4.3.1 von Adobe Experience Manager Guides](./whats-new-4-3-1-release.md).

## Upgrade auf Version 4.3.1 von Experience Manager Guides


Sie können Ihre aktuelle Version von Experience Manager Guides einfach auf Version 4.3.1 aktualisieren. Bevor Sie mit dem Upgrade auf Version 4.3.1 von Experience Manager Guides fortfahren, müssen Sie die folgenden Punkte berücksichtigen:
Sie können Ihre aktuelle Version von Experience Manager Guides auf Version 4.3.1 aktualisieren


- Wenn Sie Version 4.3.0, 4.2 oder 4.2.1 verwenden, können Sie direkt auf Version 4.3.1 aktualisieren.
- Wenn Sie Version 4.1 oder 4.1.x verwenden, müssen Sie auf Version 4.3.0, 4.2 oder 4.2.x aktualisieren, bevor Sie auf Version 4.3.1 aktualisieren.
- Wenn Sie Version 4.0 verwenden, müssen Sie auf Version 4.2 aktualisieren, bevor Sie auf Version 4.3.1 aktualisieren.
- Wenn Sie Version 3.8.5 verwenden, müssen Sie auf Version 4.0 aktualisieren, bevor Sie auf Version 4.2 aktualisieren.
- Wenn Sie eine Version vor 3.8.5 verwenden, lesen Sie den Abschnitt Upgrade von Experience Manager Guides im produktspezifischen Installationshandbuch.


>[!NOTE]
>
>Sie müssen das AEM Service Pack installieren, bevor Sie die Experience Manager Guides-Version aktualisieren.

Weitere Informationen finden Sie unter [Upgrade-Anweisungen](../install-guide/upgrade-xml-documentation.md).

## Kompatibilitätsmatrix

In diesem Abschnitt wird die Kompatibilitätsmatrix für die von Experience Manager Guides Version 4.3.1 unterstützten Softwareanwendungen aufgeführt.

### Adobe Experience Manager

**4.3.1 Nicht-UUID**
Version 6.5 Service Pack 18, 17, 16, 15 oder 14

**4.3.1 UUID**
Version 6.5 Service Pack 18, 17, 16, 15 oder 14

Weitere Informationen finden Sie im Abschnitt *Technische Anforderungen* im Handbuch zur Installation und Konfiguration von Adobe Experience Manager Guides.

### FrameMaker und FrameMaker Publishing Server

| Freigabe | FMPS 2022 | FMPS 2020 | FM 2022 | FM 2020 |
| --- | --- | --- | --- | --- |
| 4.3.1 (Nicht-UUID) | 2022 oder höher | 2020.2 oder höher* | 2022 oder höher | 2020.3 oder höher |
| 4.3.1 (UUID) | 2022 oder höher | 2020.2 oder höher* | 2022 oder höher | 2020.4 oder höher |
| | | | |

*Die in AEM erstellten Grundlinien und Bedingungen werden ab 2020.2 in FMPS-Versionen unterstützt.

### Sauerstoffanschluss

| Freigabe | Fenster des Sauerstoffanschlusses | Oxygen Connector Mac | In Oxygen Windows bearbeiten | In Oxygen Mac bearbeiten |
| --- | --- | --- |--- |--- |
| 4.3.1 (Nicht-UUID) | 2.3-normal-5 | 2.3-normal-5 | 1,6 | 1,6 |
| 4.3.1 (UUID) | 3.2-uuid-5 | 3.2-uuid-5 | 2,3 | 2,3 |
|  |  |   |



### Version der Wissensdatenbankvorlage

| Paketname der Komponenten | Komponentenversion | Vorlagenversion |
|---|---|---|
| Experience Manager Guides-Komponenten-Inhaltspaket für Cloud Service | dxml-components.all-1.2.2 | aem-site-template-dxml.all-1.0.15 |

## Behobene Probleme

Die in verschiedenen Bereichen behobenen Fehler sind unten aufgeführt:

### Authoring

- Nachmittagsstunden sind in der **Datum) nicht** die Erstellung von Baselines festgelegt. 12712)
- Der JSON-Code kann nicht in das `<codeblock>` des Web-Editors eingefügt werden. 12326)
- Nicht gespeicherte Versionsänderungen und die zugehörigen Indikatoren werden bei großen Dateien nicht angezeigt. 11784)
- Beim Bearbeiten in koreanischer Sprache wird das erste Zeichen in die Standardeinstellung geändert. 10049)

- Das Präfix wird im Vorschaumodus des Web-Editors dupliziert. 13133)
- `Choicetable` Zeilen werden nicht angezeigt oder können nicht ausgewählt werden. 12616)
- Der Web-Editor gibt bei der Erstellung eines Themas mithilfe eines benutzerdefinierten Schemas Validierungsfehler in bestimmten Szenarien aus. 12576)
- Die Verweise auf die ditavale Themenvorlage erstellen beim Erstellen einer Zuordnung aus der Zuordnungsvorlage keine Kopie im Inhaltsordner. 12150)

- Das Suchfeld in DITA-Karten verfügt über keine Schaltfläche zum Schließen. 11867)
- Beim Speichern langer Dateien im Web-Editor löst `DirtyChecker` eine Ausnahme mit einer langen Stapelablaufverfolgung aus und füllt die Protokolldateien. 11860)
- Zum Erstellen von DITA-Themen ist die Berechtigung Löschen für den entsprechenden Ordnerknoten erforderlich, obwohl die Zuordnung mit der Schreibberechtigung erstellt werden kann. 11706)
- Im Web-Editor wird ein falscher Titel angezeigt, wenn ein Schrägstrich vorhanden ist. 10949)

- Wenn der Titel eines Themas einen Schrägstrich &quot;/&quot; enthält, werden auf der Registerkarte im Editor nur die nachfolgenden Briefe angezeigt. 13455)
- Die Bildvorschau verschwindet nicht, nachdem die Vorschau im Editor angezeigt wurde. 13454)
- Einige der vorhandenen Versionen oder deren Bezeichnungen werden nach dem Upgrade auf 4.x nicht im Versionsverlauf angezeigt. 13247)
- Das Bedienfeld Versionsverlauf in der Assets-Benutzeroberfläche zeigt einen falschen Zeitstempel für das Feld **Aktuell** an. 12624)
- Thema mit dem conref-Titel wird in der Repository- oder Zuordnungsansicht nicht aufgelöst.13304)


### Veröffentlichung

- Native PDF | Die Reihenfolge der Themen ist nicht festgelegt, wenn die PDF-Ausgabe generiert wird. 13157)
- Natives PDF| Für das Element `<p>` ist kein Standardstil-Tag verfügbar. 12559)
- Native PDF | Inline-Stile, die auf den Inhaltsbereich angewendet werden, werden nicht auf die Themen in Vorder- und Rückseite angewendet. 13510)
- Das `DeliveryTarget`-Attribut wird beim Generieren der AEM-Site-Ausgabe nicht weitergegeben.  13132)
- Der Workflow **Publish** bleibt beim Generieren der AEM-Site-Ausgabe für Inhalte mit bestimmten Fehlern hängen. 12000)

- Native PDF | Das Einschließen mehrerer XRefs erweitert den Text über die Spaltenbreite hinaus. 13004)
- Native PDF | Wenn Thema und Titel dieselbe ID haben, führt dies zu einer fehlerhaften Generierung der PDF-Ausgabe. 12644)
- Native PDF | Beim Hinzufügen einer Output-Klasse zu einem übergeordneten `<topicref>` in einer DITA-Zuordnung und beim Anwenden eines benutzerdefinierten Stils auf die Output-Klasse wird der Stil auf Elemente innerhalb des Themenkörpers angewendet, einschließlich Abschnittstiteln. 12166)
- Die inkrementelle Veröffentlichung funktioniert nicht, wenn eine DITA-Zuordnung mehrere ditavalrefs enthält. 12117)
- AEM-Site | Beim Erstellen einer Zuordnung mit keydef, die auf ein Thema als Variable verweist, und beim Hinzufügen von processing-role=resource-only werden einige unerwartete Seiten erstellt. 12099)
- Wenn Assets aus dem DAM von AEM in einer anderen Ausgabe als der AEM-Site verwendet werden, spiegeln die Metadaten „jcr:createdBy“ weder den Namen des Herausgebers noch den Namen des Benutzers wider, der die DITA-Zuordnung oder das Thema zuletzt geändert hat. 12090)
- AEM Sites | DITA-Map mit topichead im navtitle (mit nicht unterstützten Zeichen) führt zu fehlerhaften Seiten-URLs. 11978)
- Native PDF | Probleme treten bei der Unterstützung von topichead / topicmeta / navtitle in Frontmatter und Backmatter auf. 11969)
- Native PDF | Das Generieren von PDF für große Dokumente ist zeitaufwendig. 11955)
- Native PDF | Beim Umbenennen einer Vorgabe wird beim Generieren einer PDF-Ausgabe eine NullPointerException ausgelöst. 11889)
- Der `<conref>` wird nicht in der PDF-Ausgabe angezeigt. 11131)
- In den `<div>` wird beim Umschalten zwischen der Authoring- und der Source-Ansicht im Seitenlayout-Editor ein zusätzlicher Leerraum hinzugefügt. 10750)
- Der auf AEM Cloud Manager replizierte Inhalt ist auf der Publish-Instanz nicht sichtbar. (9564)


### Verwaltung

- Der Versionsverlauf wird nicht angezeigt, auch wenn die `dc:format`-Eigenschaft für ein Asset nicht vorhanden ist. 10463)
- Inhaltsreferenz ist fehlerhaft. Kopieren Sie DITA-Dateien, und fügen Sie sie ein, wenn die Themen-ID nicht mit der GUID übereinstimmt. 12614)
- Bei dynamischen Baselines wird die Beschriftungsliste nicht aus den direkten Referenzen der Arbeitskopie einer DITA-Zuordnung abgerufen. 11917)
- Baseline zeigt die falsche Anzahl von Dateien im Zuordnungs-Dashboard an, wenn die Funktion Alle Themen durchsuchen verwendet wird. 13265)
- Im Web-Editor zeigt die Grundlinie den Titel für die vorherige Version anstelle der ausgewählten Version der DITA-Datei an. 13444)

### Überprüfung

- Die Überprüfung eines Themas zeigt falsche Kommentare an. 13453)
- Die Schaltfläche Schließen auf der Überprüfungsseite in der Experience Manager Guides führt Benutzende zur AEM-Homepage. 13535)
- Anhänge werden für ein Thema in der Überprüfung nicht im rechten Bedienfeld des Editors angezeigt. 13011)



### Übersetzung

- Die vom Dashboard **Übersetzung** exportierte Baseline schlägt fehl und wird nicht in der Zielsprache geöffnet. 13466)

- Neue Übersetzungsprojekte werden erstellt, anstatt neue Aufträge zu den ausgewählten vorhandenen Übersetzungsprojekten hinzuzufügen.  10214)
- Der Titel der übersetzten Datei wird anstelle des Titels der Quelldatei angezeigt. 11630)
- Die automatische Genehmigung funktioniert manchmal nicht und es treten Ausnahmen auf, wenn für den Übersetzungsstatus ein falscher Wert festgelegt ist. 13607)
- Die vom Übersetzungs-Dashboard exportierte Baseline schlägt fehl und wird nicht in der Zielsprache geöffnet. 12993)
- Einige Dateien fehlen bei der Verwendung von Baselines in der Übersetzung. 13021)
