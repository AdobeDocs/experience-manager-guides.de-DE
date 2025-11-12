---
title: Verarbeitung von Assets
description: Erfahren Sie, wie Sie Assets verarbeiten
feature: Migration
role: Admin
level: Experienced
exl-id: 27786098-119c-4b7a-8275-8a89d435294f
source-git-commit: 32ed6c47f8193f955df8a60fc8cdc931b28fa7a4
workflow-type: tm+mt
source-wordcount: '563'
ht-degree: 1%

---

# Verarbeiten von Assets

In datenintensiven Workflows wie der Veröffentlichung ist ein effizientes Asset-Management entscheidend für die Aufrechterhaltung von Leistung und Zuverlässigkeit. Der Asset-Verarbeitungs-Workflow dient zum Verwalten benutzerspezifischer Assets, die intensive Datenvorgänge erfordern. Sie gilt in erster Linie für zwei Fälle: wenn die anfängliche Verarbeitung aufgrund von Fehlern fehlschlägt oder wenn Dateien unverarbeitet bleiben, da kein Asset-Verarbeitungs-Trigger initiiert wurde. Durch die Aktivierung einer zielgerichteten Verarbeitung auf Ordnerebene können Benutzer nur die erforderlichen Assets isolieren und verarbeiten und so den Verwaltungsaufwand für unnötige Berechnungen vermeiden. Dieser selektive Ansatz verbessert die Leistung erheblich und verringert den Zeitaufwand für kritische Vorgänge wie die Veröffentlichung und die Berichterstellung. Insgesamt trägt sie zu mehr Effizienz und Geschwindigkeit bei der Bearbeitung komplexer Datenaufgaben bei.

>[!NOTE]
>
> - Bei großen Datensätzen ist es am besten, die Verarbeitung außerhalb der Spitzenzeiten auszuführen, um eine Beeinträchtigung der Systemleistung zu vermeiden. Nachdem die Verarbeitungsaufgabe abgeschlossen ist, können Sie die Details überprüfen, um die Ergebnisse zu analysieren.<br>
>- Die Asset-Verarbeitung für den `/content/dam`-Trigger erfolgt alle 15 Minuten. Während jedes Zyklus werden Assets aufgenommen, die innerhalb des letzten 15-Minuten-Intervalls neu hinzugefügt wurden oder unverarbeitet blieben, und erneut verarbeitet. Um die Ansicht der Funktion für die automatische Asset-Verarbeitung zu konfigurieren, [ Sie „Asset-Verarbeitungsfunktion konfigurieren](../cs-install-guide/configure-asset-processing-cs.md).

## Verarbeiten der Assets

Gehen Sie wie folgt vor, um die Assets zu verarbeiten:

1. Klicken Sie oben auf das Adobe Experience Manager-Logo und anschließend auf **Tools**.
1. Wählen Sie im Bedienfeld **Tools** die Option **Guides** aus.
1. Wählen Sie die Kachel **Massenprozessor** aus.

   ![flow-asset-processor](images/flow-asset-processor.png){align="left"}

1. Das Fenster Guides Bulk Processor wird mit den unten angezeigten Details geöffnet. Außerdem werden in diesem Fenster nur die Informationen zu den letzten fünf Migrationen angezeigt.

   - **Feature Type**: Zeigt die Funktion des Prozesses an, der ausgeführt wird.

   - **Ausführungs-ID**: Dies ist die eindeutige ID für jede Verarbeitungsaufgabe, die Sie ausführen.

   - **Ordner**: Zeigt den für die Verarbeitung ausgewählten Ordner an.

   - **Ausgeschlossene Ordner**: Zeigt den Ordner an, der von der Verarbeitung ausgeschlossen ist.

   - **Erstellt von**: Zeigt an, wer die Aufgabe oder den Prozess erstellt hat. Das können sowohl Sie als auch das System sein.

   - **Startzeit:** Zeigt das Datum und die Uhrzeit an, zu der der Verarbeitungsprozess gestartet wurde.

   - **Endzeit**: Zeigt das Datum und die Uhrzeit an, zu der der Verarbeitungsprozess endet.

   - **Status**: Zeigt den Status der Verarbeitung als In Bearbeitung, Abgeschlossen oder Abgebrochen an.

   ![Guides-asset-processor](images/guides-asset-processor-new.png){align="left"}

1. Wählen Sie **Registerkarte** Neuer Prozess“ in der oberen rechten Ecke des Fensters, um eine neue Verarbeitungsaufgabe zu starten.

   ![New-process-asset-processor](images/new-asset-processor.png){width="350" align="left"}

1. Wählen Sie den Ordner aus, den Sie verarbeiten möchten. Sie können auch die Ordner (innerhalb des übergeordneten ausgewählten Ordners) auswählen, die Sie ausschließen oder ignorieren möchten.

   >[!NOTE]
   >
   >Es kann jeweils nur ein Ordner für die Verarbeitung ausgewählt werden. Für bestimmte Vorgänge können Sie mehrere Ordner ausschließen.

1. Wählen Sie **Erstellen**. Es erscheint ein Popup mit der Meldung **Erfolg und der Prozess wurde erfolgreich ausgelöst** wie im Ausschnitt dargestellt. Dasselbe spiegelt sich in der Liste wider. Im Fenster wird der Status der Verarbeitungsaufgabe angezeigt.

   ![Message-Asset-Processor](images/message-asset-processor.png){width="350" align="left"}


## Zusätzliche Optionen für die Verarbeitungsaufgaben

Zusätzliche Optionen stehen für die Verarbeitungsaufgabe zur Verfügung, sobald sie initiiert wurde. Sie können auf diese Optionen zugreifen, indem Sie den Mauszeiger über die Ausführungs-ID Ihrer Aufgabe bewegen. Details zu diesen Optionen finden Sie unten:

- **Neu starten** : Startet die zuvor erfolgreiche Asset-Verarbeitungsaufgabe neu.

  ![restart-asset-processor](images/restart-asset-processor.png){width="650" align="left"}

- **Fortsetzen** : Setzt die zuvor abgebrochene oder fehlgeschlagene Asset-Verarbeitungsaufgabe fort.

  ![resume-asset-processor](images/resume-asset-processor.png){width="650" align="left"}

- **Abbrechen** : Bricht die derzeit ausgeführte Asset-Verarbeitungsaufgabe ab.

  ![cancel-asset-processor](images/cancel-asset-processor.png){width="650" align="left"}

- **Protokolle anzeigen**: Zeigt die Protokolle für die Asset-Verarbeitungsaufgabe an. Für laufende Aufgaben zeigt das Protokoll detaillierte Verarbeitungsinformationen an, einschließlich der geschätzten verbleibenden Zeit und des Asset-Status. Diese Protokollliste zeigt die neuesten 500 Einträge an. Das vollständige Protokoll kann heruntergeladen werden.

  ![logs-asset-processor](images/logs-asset-processor.png){width="650" align="left"}
