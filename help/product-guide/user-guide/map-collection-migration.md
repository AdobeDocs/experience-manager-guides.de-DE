---
title: Migrieren alter Zuordnungssammlungen zu neuen Zuordnungssammlungen
description: Erfahren Sie, wie Sie Zuordnungssammlungen von alten zu neuen Zuordnungssammlungen migrieren
source-git-commit: aa9f0768e2c6f23294f926c2ed9a1f7e51db7610
workflow-type: tm+mt
source-wordcount: '455'
ht-degree: 1%

---


# Migrieren alter Zuordnungssammlungen zu neuen Zuordnungssammlungen

Wenn Sie bereits Zuordnungssammlungen im alten Format eingerichtet haben, müssen Sie sie beim Wechsel zum neuen Erlebnis nicht von Grund auf neu erstellen. Sie können sie entweder manuell neu erstellen oder das integrierte Migrations-Tool verwenden, um alles in einem Schritt zu verschieben.

Das Migrations-Tool, das als neuer Prozesstyp im **Massenprozessor** hinzugefügt wurde, liest Ihre vorhandenen alten Zuordnungssammlungen und erstellt automatisch passende neue Zuordnungssammlungen für Sie. Dieser Artikel führt Sie durch die Ausführung der Migration und zeigt einige wichtige Verhaltensweisen auf, die Sie vor der Verwendung kennen sollten.

>[!NOTE]
>
> Die Massenaktivierungsfunktion wird nicht in die neue Zuordnungssammlung migriert. Erstellen Sie bei Bedarf alle Zuordnungssammlungen neu, die für die Massenaktivierung im neuen Zuordnungssammlungserlebnis verwendet werden.

## Zu neuer Zuordnungssammlung migrieren

Führen Sie die folgenden Schritte aus, um die alten Zuordnungssammlungen zu neuen Zuordnungssammlungen zu migrieren:

1. Klicken Sie auf das Adobe Experience Manager-Logo und anschließend auf **Tools**.
1. Wählen Sie im **Tools**-Bedienfeld **Guides** aus.
1. Wählen Sie die Kachel **Massenprozessor** aus.

   ![Markiert die Kachel „Massenprozessor“](images/flow-asset-processor.png)

1. Das Fenster Guides Bulk Processor wird mit den folgenden Details geöffnet:

   - **Feature Type**: Zeigt die Funktion des Prozesses an, der ausgeführt wird.

   - **Ausführungs-ID**: Dies ist die eindeutige ID für jede Migrationsaufgabe, die Sie durchführen.

   - **Erstellt von**: Zeigt an, wer die Aufgabe erstellt hat.

   - **Startzeit**: Zeigt das Datum und die Uhrzeit des Initiierens der Migration an.

   - **Endzeit**: Zeigt das Datum und die Uhrzeit an, zu der die Migration endet.

   - **Status**: Zeigt den Status der Migration als „In Bearbeitung“, „Abgeschlossen“ oder „Fehlgeschlagen“ an.

   ![Das Fenster Guides Bulk Processor](images/guides-asset-processor-migration.png)

1. Wählen Sie **Registerkarte** Neuer Prozess“ in der rechten oberen Ecke des Fensters aus, um eine neue Migrationsaufgabe zu starten.

   Das **Neuer Prozess**-Dialogfeld wird geöffnet.

   ![Dialogfeld „Neuer Prozess für Migration“](images/new-process-migration.png) {width="350"}

1. Wählen Sie **Zuordnungssammlung** aus der Dropdown-Liste **Merkmalstyp** aus.

   ![Zuordnungssammlungsfunktion für die Migrationsaufgabe](images/new-process.png) {width="350"}

1. Wählen Sie **Erstellen** aus.

Dadurch wird ein einzelner Auftrag ausgeführt, der alle vorhandenen alten Zuordnungssammlungen in neue Zuordnungssammlungen migriert. Es ist keine spezielle Konfiguration notwendig.

>[!NOTE]
>
> Wenn die Migrationsaufgabe fehlschlägt, können Sie die Option **Protokolle anzeigen** überprüfen, indem Sie den Mauszeiger über die Ausführungs-ID bewegen.

## Wichtige Überlegungen

- **Neuausführung der Migration:** Wenn der Migrationsprozess erneut ausgeführt wird, wird nicht auf Änderungen in den (alten) Quellzuordnungssammlungen geprüft. Die neuen Zuordnungssammlungen werden bedingungslos remigriert oder überschrieben.
- **Zeitstempel und Eindeutigkeit:** Jede migrierte Zuordnungssammlung speichert den Zeitstempel ab der ersten Migration. Dieser Zeitstempel wird verwendet, um die Eindeutigkeit des migrierten Eintrags zu wahren. Aus diesem Grund spiegelt die migrierte Zuordnungssammlung keine späteren Aktualisierungen der ursprünglichen (Quell-)Zuordnungssammlung wider, sondern nur den Status zum Zeitpunkt der Migration.


