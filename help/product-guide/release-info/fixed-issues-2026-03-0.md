---
title: Versionshinweise | Behobene Probleme in Adobe Experience Manager Guides Version 2026.03.0
description: Erfahren Sie mehr über die Fehlerbehebungen in der Version 2026.03.0 von Adobe Experience Manager Guides as a Cloud Service.
exl-id: 6eca85f5-d7d3-4486-8b32-8af3a6cce4ee
hidefromtoc: true
source-git-commit: 22ea3fe3ccb974fe3795299f7815e7aae78d41e7
workflow-type: tm+mt
source-wordcount: '816'
ht-degree: 3%

---

# Es wurden Probleme in der Version 2026.03.0 behoben

Dieser Artikel behandelt die in verschiedenen Bereichen der Version 2026.03.0 von Adobe Experience Manager Guides as a Cloud Service behobenen Fehler.

Weitere Informationen zu den neuen Funktionen und Verbesserungen finden Sie unter [Neue Funktionen in Version 2026.03.0](whats-new-2026-03-0.md).

Erfahren Sie mehr [Upgrade-Anweisungen für die Version 2026.03.0](upgrade-instructions-2026-03-0.md).

## Authoring

- Beim Bearbeiten einer Schematron-Datei (`*.sch`) und bei Verwendung der Funktion zum Suchen und Ersetzen wird das Bedienfeld „Suchen und Ersetzen“ unten teilweise außerhalb des Bildschirms angezeigt, wodurch der Zugriff auf die Eingabefelder und Steuerelemente verhindert wird. (GUIDES-38412)

## Veröffentlichung

- Wenn dasselbe Thema in mehreren Zuordnungen mit unterschiedlichen bedingten Voreinstellungen wiederverwendet wird, überschreibt die Veröffentlichung der neuesten Zuordnung in Salesforce den Themeninhalt, was dazu führt, dass Benutzenden zuvor veröffentlichter Zuordnungen falsche Daten angezeigt werden. (GUIDES-37806)
- Beim Veröffentlichen eines nativen PDF für eine Zuordnung, die eine bedingte Verarbeitung oder bestimmte verschachtelte Zuordnungen enthält, wird die in der Zuordnung definierte `dc:title` nicht auf dem PDF-Cover angezeigt, was zu einem fehlenden Cover-Titel führt. (GUIDES-37733)
- Das Generieren der AEM-Site-Ausgabe (mithilfe der Zuordnung zusammengesetzter Komponenten) für eine Zuordnung schlägt fehl und führt zu einem Fehler, wenn die `map_title` Variable im Ausgabepfad vorhanden ist. (GUIDES-36968)
- Wenn in der nativen PDF-Ausgabevorgabe ein Ausgabepfad mit einem Schrägstrich angegeben ist, fügt die Benutzeroberfläche automatisch einen zusätzlichen Schrägstrich hinzu, was zu einem doppelten Schrägstrich-Pfad führt, der in bestimmten Szenarien dazu führt, dass der PDF-Upload fehlschlägt. (GUIDES-34932)
- Das Veröffentlichen von AEM Sites-Seiten, die aus DITA-Inhalten durch Quick Publish oder Veröffentlichung verwalten generiert wurden, veröffentlicht unbeabsichtigt die zugehörigen DITA-Assets. (GUIDES-27967)
- Beim Veröffentlichen einer Zuordnung in AEM Sites (mithilfe der Zuordnung veralteter Komponenten) werden Querverweise (`xrefs`) mit `scope = peer`, die auf Unterelemente eines Themas (z. B. Absätze) in einer anderen Zuordnung abzielen, nicht auf die spezifische Element-ID aufgelöst, sondern nur auf das übergeordnete Thema. Dadurch wird die Seite am Anfang des Themas geladen, anstatt zum gewünschten Abschnitt zu scrollen. (GUIDES-21802)


## Übersetzung

- Wenn ein Bild, das anfänglich als sprachspezifisches Asset mit einer bestimmten Version verwaltet wurde (z. B. unter `/en/`), in einen globalen Ordner mit einer aktualisierten Version verschoben und ein Baseline-Export durchgeführt wird, verweist die neue Baseline weiterhin auf veraltete sprachspezifische Versionen dieses Bildes, was zu einem fehlgeschlagenen Baseline-Export führt. (GUIDES-39394)
- Bei der Verarbeitung von Übersetzungsprojekten, die außerhalb von Experience Manager Guides erstellt wurden, werden mehrere Fehlerprotokollmeldungen generiert, die darauf hinweisen, dass *`fmTarget`Eigenschaft nicht gefunden*. (GUIDES-37804)

## Grundlinie

- Beim Erstellen einer dynamischen Baseline reagiert der Editor manchmal aufgrund mehrerer gleichzeitiger API-Anfragen nicht mehr, wodurch alle anderen Vorgänge angehalten werden. (GUIDES-39054)

## Überprüfung

- Beim Zuweisen eines Benutzers zu einer Prüfungsaufgabe werden in der Dropdown-Liste alle Benutzer und nicht nur die mit den ausgewählten Projekten verknüpften aufgelistet, was zu ungültigen Benutzeroptionen führt. (GUIDES-37781)

## Berichte

- Beim Öffnen eines Berichts für eine Zuordnung tritt beim Laden des Bedienfelds „Filter“ eine Verzögerung auf (GUIDES-39385)

## Bekannte Probleme

Adobe hat die folgenden bekannten Probleme in Version 2026.03.0 identifiziert:

- Beim Erstellen einer doppelten ServiceNow-Knowledgebase-Voreinstellung wird ein leerer Bildschirm geladen. (GUIDES-42732)
- Die API zum Abrufen des Dokumentstatus gibt für einige Dateien eine Nullantwort zurück, wodurch in der Benutzeroberfläche falsche Dokumentstatus angezeigt werden. (GUIDES-42561)
- UI-Anpassungen, die auf Registerkartennamen im Zuordnungs-Dashboard basieren, werden nicht angewendet. (GUIDES-42285)
- Wenn eine Datei sowohl im Editor als auch im Suchbereich geöffnet ist, wird beim Löschen aus dem Explorer-Bereich die Datei entfernt und die Explorer-Liste aktualisiert. Beim Aktualisieren der Seite wird die Datei jedoch weiterhin im Suchbereich angezeigt. (GUIDES-41935)
- Wenn beim Aktualisieren einer aktiven Prüfungsaufgabe ein Thema, das bereits Teil der Überprüfung ist, entfernt und dann erneut hinzugefügt wird, ohne auf **Aktualisieren** zu klicken, gehen die Informationen zu Überprüfenden auf der Registerkarte Überprüfende verloren.   (GUIDES-38774)
- Wenn Sie ein Thema im Vorschaumodus auswählen, wird es in der Zuordnungsansicht nicht hervorgehoben, wenn das Thema in Bookmap-Tags (Frontmatter, Kapitel, Teil oder Backmatter) oder Teilen von zyklischen Inhalten enthalten ist. (GUIDES-42416)
- In der Assets-Benutzeroberfläche wird **Schaltfläche „Verschieben** beim ersten Versuch nicht aktiviert, wenn mehr als zwei Dateien oder Ordner ausgewählt sind. (GUIDES-42721) <br> **Problemumgehung**: Nachdem Sie mehr als zwei Dateien oder Ordner ausgewählt haben, warten Sie einige Sekunden, bevor Sie den Zielordner auswählen.
- Wenn Sie im Editor zu **Benutzereinstellungen** navigieren und die Stammzuordnung aktualisieren, während der Vorschaumodus im Editor geöffnet ist, wird die Zuordnungsvorschau als leerer Bildschirm geladen, wenn Sie zum Editor zurückkehren. (GUIDES-42412) <br> **Problemumgehung**: Durch Aktualisieren der Vorschau mit dem Symbol **Aktualisieren** im Vorschaumodus wird das Problem behoben.
- Beim Umbenennen einer vorhandenen Vorlage wird der Name im Bedienfeld **Ausgabevorlagen** erst aktualisiert, wenn die Seite manuell aktualisiert wird. (GUIDES-42528)<br> **Problemumgehung**: Aktualisieren Sie den Browser, um den aktualisierten Vorlagennamen im Bedienfeld „Ausgabevorlagen“ anzuzeigen.
