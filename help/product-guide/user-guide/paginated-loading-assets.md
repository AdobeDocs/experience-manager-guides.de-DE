---
title: Grundlegendes zu den Leistungsverbesserungen in Experience Manager Guides
description: Erfahren Sie, wie das paginierte Laden von Dateien und Ordnern die Leistung in Experience Manager Guides verbessert.
feature: Authoring, Publishing
role: User
source-git-commit: e4019ae1e605bd26f7df676a4fab8c632fd8fa8e
workflow-type: tm+mt
source-wordcount: '644'
ht-degree: 0%
---

## Paginiertes Laden von Dateien und Ordnern

>[!NOTE]
>
> Diese Funktion ist standardmäßig aktiviert. Wenden Sie sich zur Deaktivierung an Ihr Customer Success-Team.

Experience Manager Guides verwendet eine paginierte API zum Laden von Dateien und Ordnern. Anstatt den gesamten Inhalt auf einmal zu laden, werden die Ordner schrittweise in Stapeln geladen, wobei zusätzliche Assets automatisch beim Scrollen oder durch Auswahl der Option **Mehr laden** abgerufen werden.

Die Sortierung erfolgt Server-seitig. Das Anwenden einer Sortierreihenfolge ruft also frisch sortierte Ergebnisse ab, anstatt bereits im Browser geladene Daten neu zu sortieren. Bei gängigen Vorgängen wie Umbenennen, Löschen, Hinzufügen und Verschieben wird nicht mehr der gesamte Ordner neu geladen. Stattdessen aktualisieren sie nur das betroffene Element oder aktualisieren die erste Ergebnisseite. Die *Datei immer im Explorer suchen*-Funktion ist ebenfalls nicht mehr verfügbar. Für jedes Asset können Sie weiterhin das Kontextmenü verwenden, um die Datei im Explorer zu finden.

In den folgenden Abschnitten wird beschrieben, wie sich diese auf verschiedene Schnittstellen, Bedienfelder und Dialogfelder anwenden lassen.

### Startseiten-Repository-Tabelle

- **Durchsuchen**: Verwendet unendliches Scrollen. Der erste Asset-Stapel wird zunächst geladen. Die nachfolgenden Stapel werden beim Scrollen automatisch angehängt. Beim Wechsel von Ordnern wird die aktuelle Liste gelöscht und die Assets werden aus dem neu ausgewählten Ordner geladen.
- **Umbenennen**: im Kontext; keine Aktualisierung des Ordners.
- **Löschen**: Der Stammordner wird aktualisiert, um den ersten Asset-Batch anzuzeigen.
- **Hinzufügen**: Die neue Datei wird oben (im aktuellen Ordner) eingefügt. Zusätzliche Metadaten wie Dokumentstatus, Sperrstatus, Dateityp, Erstellungsdatum und andere Details werden in einer einzigen Batch-Hintergrundanfrage abgerufen und nach einiger Zeit automatisch ausgefüllt.
- **Verschieben**: Wenn Sie eine Datei in den aktiven Ordner verschieben, wird sie oben hinzugefügt. Wenn Sie eine Datei aus dem aktiven Ordner verschieben, wird der Ordner auf den ersten Asset-Stapel aktualisiert.
- **Schaltfläche „Aktualisieren**: Lädt den aktiven Ordner neu und zeigt den ersten Asset-Batch an.
- **Sortieren**: Die erste sortierte Seite mit unendlichem Bildlauf anzeigen.
- **Navigationsbereich für Ordner**: Beim Öffnen eines Ordners wird der erste Asset-Batch geladen, wobei bei **nachfolgenden Batches** Option „Mehr laden“ angehängt wird.

  ![Seitenumbruch für das Navigationsfenster des Ordners](images/home-tree-pagination.png){width="650"}

### Sammlungen

- Durch Hinzufügen einer Datei wird diese am Anfang des Ordners eingefügt, ohne dass der Ordner aktualisiert wird.
- Beim Öffnen eines Ordners wird der erste Asset-Batch geladen, wobei für nachfolgende **eine Option** Mehr laden“ angehängt wird.

  ![Seitenumbruch für Sammlung](images/collections-paginated.png){width="650"}


### Explorer

- **Stammordner**: Unendliches Scrollen. Der erste Asset-Batch wird zunächst geladen. Die nachfolgenden Batches werden beim Scrollen automatisch angehängt.
- **Untergeordnete Ordner**: Durch Erweitern eines Ordners wird der erste Asset-Stapel geladen, wobei bei nachfolgenden **eine Option** Mehr laden“ angefügt wird.

  ![Paginierung für Explorer](images/explorer-pagination.png){width="650"}

- **Umbenennen**: Dies geschieht im Kontext ohne Ordneraktualisierung.
- **Löschen**: Der Stammordner wird aktualisiert, um den ersten Asset-Batch anzuzeigen.
- **Hinzufügen oder**: Die neue Datei wird oben im Ordner angezeigt.
- **Verschieben**: Beim Wechseln zwischen nicht verwandten Ordnern wird der Quellordner auf den ersten Asset-Batch aktualisiert und das Element am Anfang des Ziels hinzugefügt (dabei wird der erste Asset-Batch des Ziels geladen, falls er noch nicht geöffnet war).
- **Aktualisieren**: Eine neue Aktualisierungsschaltfläche in der Kopfzeile des Explorer-Bedienfelds lädt die Stammebene neu und zeigt den ersten Asset-Batch an.

### Suchbereich

- Beim Durchsuchen von Suchergebnissen wird unendliches Scrollen verwendet. Der erste Asset-Batch wird zunächst geladen. Die nachfolgenden Batches werden beim Scrollen automatisch angehängt.

### Bedienfeld „Vorlage“

- Auf der Stammebene werden nur die Kategorien **Zuordnung** und **Thema** angezeigt. Durch Erweitern eines Unterordners wird der erste Asset-Batch geladen, wobei für nachfolgende **eine Option** Weitere laden“ angehängt wird.

### Dialogfeld „Pfad auswählen“

- Jeder Ordnerknoten lädt den ersten Asset-Batch, wobei für nachfolgende **eine Option** Mehr laden“ angehängt wird.

  ![Paginierung für Dialogfeld „Pfad auswählen“](images/select-path-pagination.png){width="650"}

- Wenn das Dialogfeld geöffnet wird und zu einem bestimmten Zielpfad navigiert, wird die Baumstruktur automatisch vom Stamm zum Ziel erweitert. Ordner entlang des Pfads werden mit einer größeren Seitengröße geladen, während der Zielordner mit der standardmäßigen Batch-Größe geladen wird.