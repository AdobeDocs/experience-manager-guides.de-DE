---
title: Versionshinweise zu | Adobe Experience Manager Guides Version 4.2
description: Erfahren Sie mehr über die Fehlerbehebungen und das Upgrade auf Version 4.2 von Adobe Experience Manager Guides
exl-id: 8a7fef77-63af-462f-89c5-054ab31e079b
feature: Release Notes
role: Leader
source-git-commit: 6e23f52fc9124d0f07f8108da1b5fe574f553469
workflow-type: tm+mt
source-wordcount: '1390'
ht-degree: 1%

---

# Version 4.2 von Adobe Experience Manager Guides (Februar 2023)

Diese Versionshinweise enthalten die Upgrade-Anweisungen, die Kompatibilitätsmatrix und behobene Probleme in Version 4.2 von Adobe Experience Manager Guides (später *AEM Guides*).

Weitere Informationen zu den neuen Funktionen und Verbesserungen finden Sie unter [Neue Funktionen in Version 4.2 von Adobe Experience Manager Guides](whats-new-4-2-release.md).

## Upgrade auf Version 4.2 von AEM Guides

Sie können Ihre aktuelle Version von AEM Guides einfach auf Version 4.2 aktualisieren. Bevor Sie mit dem Upgrade auf Version 4.2 von AEM Guides fortfahren, müssen Sie die folgenden Punkte berücksichtigen:
* Wenn Sie Version 4.0, 4.1 oder 4.1.x verwenden, können Sie direkt auf Version 4.2 aktualisieren.
* Wenn Sie Version 3.8.5 verwenden, müssen Sie auf Version 4.0 aktualisieren, bevor Sie auf Version 4.2 aktualisieren.
* Wenn Sie eine Version vor 3.8.5 verwenden, lesen Sie den Abschnitt *Upgrade von AEM Guides* im produktspezifischen Installationshandbuch.

>[!NOTE]
>
>Sie müssen das AEM Service Pack installieren, bevor Sie die AEM Guides-Version aktualisieren.

Weitere Informationen finden Sie unter [Upgrade-Anweisungen](assets/Adobe-Experience-Manager-Guides-Upgrade-Instructions-EN.pdf).

## Kompatibilitätsmatrix

In diesem Abschnitt wird die Kompatibilitätsmatrix für die von AEM Guides Version 4.2 unterstützten Softwareanwendungen aufgeführt.

### Adobe Experience Manager

**NICHT-UUID**
Version 6.5 Service Pack 15, 14, 13 oder 12

**UUID**
Version 6.5 Service Pack 15, 14, 13 oder 12

Weitere Informationen finden Sie im Abschnitt *Technische Anforderungen* im Handbuch zur Installation und Konfiguration von Adobe Experience Manager Guides.

### FrameMaker und FrameMaker Publishing Server

| Freigabe | FMPS 2022 | FMPS 2020 | FM 2022 | FM 2020 |
| --- | --- | --- | --- | --- |
| 4.2 (Nicht-UUID) | 2022 oder höher | 2020.2 oder höher* | 2022 oder höher | 2020.3 oder höher |
| 4.2 (UUID) | 2022 oder höher | 2020.2 oder höher* | 2022 oder höher | 2020.4 oder höher |
| | | | | |

*Die in AEM erstellten Grundlinien und Bedingungen werden ab 2020.2 in FMPS-Versionen unterstützt.

### Sauerstoffanschluss

| Freigabe | Fenster des Sauerstoffanschlusses | Oxygen Connector Mac | In Oxygen Windows bearbeiten | In Oxygen Mac bearbeiten |
| --- | --- | --- |--- |--- |
| 4.2 (Nicht-UUID) | 2.1-normal-4 | 2.1-normal-4 | 1,6 | 1,6 |
| 4.2 (UUID) | 2.8-uuid-8 | 2.8-uuid-8 | 2,3 | 2,3 |
|  |  |   |  |  |

## Behobene Probleme

Die in verschiedenen Bereichen behobenen Fehler sind unten aufgeführt:

### Authoring

* Linker Bereich wird beim Hinzufügen einer Registerkarte unterbrochen. 11126)
* Änderungen im HTML-Editor des Web-Editors führen zu Problemen mit `<dl>` und `<dlentry>`. 11024)
* Einige Attribute werden nicht als bedingt behandelt und verursachen Probleme. 10895)
* Mindestens drei Ebenen verschachtelter `<indexterm>` sind nicht im nativen PDF-Export verschachtelt. 10799)
* Der Inhalt verschwindet beim Wechsel von der Authoring- zur Source-Ansicht im Hauptteil einer Aufgabe. 10735)
* Überprüfungskommentare werden in einer Überprüfungsaufgabe verlegt. 10625)
* `<conref>` Hinweis in einem para-Tag wird im Vorschaumodus nicht angezeigt. 10559)
* Durch Drücken der Rücktaste am Ende eines Listenelements wird die gesamte Liste entfernt. 10540)
* Der Bildschirm wird in Chrome v106 beim Ziehen und Ablegen eines Elements aus der Benutzeroberfläche (z. B. im Bedienfeld Bedingungen ) als leer angezeigt. 10524)
* Die Schaltfläche zum automatischen Einrücken fehlt in der Symbolleiste in der Ansicht **Source**. 10448)
* Das erste Zeichen eines Listenelements geht manchmal verloren, wenn die Liste im Editor erstellt wird.( 10447)
* **Rückgängig** oder **Wiederholen** funktioniert bei einigen Dateien nicht ordnungsgemäß. 10373)
* Benutzerdefinierte Metadaten werden beim Kopieren und Einfügen nicht beibehalten. 10367)
* Beim Kopieren (Strg+C) und Einfügen (Strg+V) von Inhalten tritt ein Fehler auf. 10304)
* Das Gliederungsbedienfeld zeigt beim Wechsel vom Authoring- zum Source-Modus keine Inhalte an. 10296)
* Eine Unterzuordnung wird nicht erstellt, wenn sie auf eine Hauptzuordnung in DITA-Vorlagen verweist. 10231)
* Navigationsprobleme treten im Web-Editor nach dem Upgrade auf 4.0 auf. 10159)
* Die Option „Rückgängig machen“ im XML-Editor führt den Benutzer zum Seitenanfang. 10091)
* Knoteneigenschaften werden nach dem Kopieren und Einfügen eines Assets entfernt. 10053)
* Zu DITA-Themen hinzugefügte SVG-Dateien werden im Vorschaumodus des Editors nicht angezeigt. 10010)
* Suchergebnisse für Suchen und Ersetzen im Web-Editor können im Dunkelmodus nicht gelesen werden. (9978)
* Beim Erstellen einer Zuordnung aus der Zuordnungsvorlage ist kein Ladeprogramm vorhanden. (9891)
* Der Kontext in der Themenvorlage funktioniert nicht und die kopierte Hash-ID wird in der Inhaltskopie nicht aktualisiert. (9 890)
* Es wird keine Option zum Durchsuchen der Themen oder der Zuordnungsvorlage in den Unterordnern des Themas oder des Zuordnungsordners angezeigt. (9 889)
* Keine Option zum Erstellen einer neuen Vorlage für die Unterordner von Themen oder Karten. (9 888)
* Im XML-Editor werden die Bilder zu Themen nicht aktualisiert. (9500)
* mimeType ist für die Erstellung und Aktualisierung von DITA-Assets hartcodiert. (8979)
* Ein normaler Bindestrich wird eingefügt, wenn Sie im Dialogfeld **Sonderzeichen einfügen“ den** Bindestrich auswählen. (8919)
* Der Name des Versionserstellers im Versionsverlauf lautet „fmdita-serviceuser“ für die Dateien, die über die Assets-Benutzeroberfläche hochgeladen wurden. (8910)
* Die Option „Bearbeiten“ funktioniert nicht für Bilder, wenn sie in der Spaltenansicht der Assets-Benutzeroberfläche arbeiten. (8 758)
* Das DITA-Thema wird nicht automatisch mit Änderungen aktualisiert, die auf der Seite **Eigenschaften** vorgenommen wurden. (8 745)
* Beim Verschieben von Elementen innerhalb des Themas im Web-Editor werden die zugewiesenen IDs für Elemente durch automatisch zugewiesene IDs überschrieben. (7 895)

### Verwaltung

* Das Kopieren eines DITA Map-Assets (über die Asset-Benutzeroberfläche ) verursacht fehlerhafte Baselines im kopierten Asset. 11218)
* Beim Hochladen einer Datei, die den in AEM zulässigen Grenzwert (standardmäßig 2 GB) überschreitet, wird keine Warnmeldung angezeigt. 10817)
* Web-Editor-Baseline | Das Verhalten der letzten Spalte im neuen Baseline-Dashboard im Web-Editor ist anders. 10808)
* Übersetzung | Der Übersetzungsauftrag wird aufgrund von ungültigem /libs/fmdita/i18n/ja.json nicht gestartet. 10543)
* Übersetzung | In einem über das Übersetzungs-Dashboard (Menschliche Übersetzung) erstellten Projekt zur Berechnung des Umfangs tritt ein Fehler auf. 10526)
* Übersetzung | Die Nachbearbeitung ist für den gesamten Sprachordner blockiert, dessen Assets in einem aktiven Übersetzungsprojekt vorhanden sind. 10332)
* Übersetzung| Metadaten und Tags werden nicht an die übersetzten Kopien weitergegeben. (4696)
* Für jedes Asset werden mehrere Popups angezeigt, wenn die Version geändert und im Baseline-Editor gespeichert wird. 10399)
* Sitzungsleck tritt unter com.day.cq.search.impl.builder.QueryBuilderImpl.createResourceResolver(QueryBuilderImpl.java:210) auf. 10279)
* Die Videodatei fehlt in der Grundlinie, wenn der übergeordnete Ordner im Namen Leerzeichen enthält. 10031)

### Publishing

* Die Themenregenerierung funktioniert in einigen Szenarien nicht. 10635)
* Die PDF-Veröffentlichung schlägt beim Generieren der Ausgabe für eine doppelte Vorgabe (einer vorhandenen Vorgabe) fehl. 10584)
* Die Schaltfläche Protokoll anzeigen funktioniert nicht, wenn die PDF-Generierung für eine Voreinstellung fehlschlägt. 10576)
* PublishListener zeigt die angeforderten Daten nicht in Informationsprotokollen an und enthält auch einige Junk-Protokolle.( 10567)
* Native PDF | Die PDF-Generierung schlägt mit einer Null Pointer-Ausnahme fehl. 10950)
* Native PDF | conkeyref wird in der generierten Ausgabe nicht aufgelöst. 10564)
* Native PDF | Probleme treten bei den Metadaten einer Zuordnung auf, auf die in der PDF-Ausgabe verwiesen werden muss.( 10556)
* Native PDF | Beim Drehen der Tabellenüberschrift treten Probleme auf. 10555)
* Native PDF | Probleme treten beim Entfernen von Themen auf, die die Verarbeitungsrolle „nur Ressource“ aufweisen. 10554)
* Native PDF | Leere Keyrefs werden in der PDF-Ausgabe angezeigt. 10553)
* Native PDF | Verschachtelte `<indexterm>` werden nicht im nativen PDF-Export verschachtelt. 10521)
* Native PDF | Der native PDF verwendet für die generierten Tags einen Inline-Stil anstelle eines Klassennamens. 10498)
* Native PDF | Verschachtelte topicref in den Anhängen werden im temporären HTML alle in h1 umgewandelt.( 10454)
* Native PDF | Themen mit Textformatierung können nicht aus dem Inhaltsverzeichnis ausgeblendet werden. 10355)
* Native PDF | Das Tabellenrahmenattribut wird nicht an den temporären HTML weitergegeben (als Klasse). 10353)
* Native PDF | Temporäre HTML-Dateien fügen die Klassen closeSp und rowsep zu hinzu. <td> und <th> auch wenn ihr Wert in der Quell-DITA 0 ist. 10352)
* Native PDF | Beim Neustarten der Seitenzahlen im Kapitellayout erfolgt die Nummerierung nach dem Zufallsprinzip am Ende des vorherigen Kapitels. 10154)
* Native PDF | Die wichtigsten Referenzen für Schlüsselwörter mit Bild- oder externen Links werden nicht aufgelöst. 10063)
* Native PDF | Der Anhang wird als Kapitel in der generierten PDF angezeigt. (9 829)
* Die Registerkarte „Vorlage“ im XML-Editor wird den Ordnerprofiladministratoren nicht angezeigt. 10266)
* Die Baseline-Veröffentlichung schlägt für PDF fehl, das mit FrameMaker Publishing Server 2020 generiert wurde. 10551)
* Der Anwendungsfehler tritt auf, wenn auf die Schaltfläche Bearbeiten geklickt wird, nachdem das Kontrollkästchen Alle Vorgaben über Ausgabevorgaben im Popup-Fenster „Schnellgenerierung“ ausgewählt wurde. 10388)
* Wenn die Registerkarte „Ausgabe“ im Web-Editor über mehr Vorgaben verfügt, kann im Abschnitt „Vorgaben“ nicht vertikal gescrollt werden und es werden nicht alle verfügbaren Vorgaben angezeigt. (9 787)
* Vorgaben können während der Veröffentlichung über den Editor nicht aus dem Ausgabe-Workflow gelöscht werden. (9100)
* Peer-Link wird auf der generierten Seite als normaler Text anstatt als Link gerendert. (7774)

## Bekanntes Problem

Adobe hat das folgende bekannte Problem in AEM Guides Version 4.2 festgestellt:

* Benutzer können Überprüfungsvorgänge auch dann durchführen, wenn die Überprüfungsaufgabe abgeschlossen ist.
