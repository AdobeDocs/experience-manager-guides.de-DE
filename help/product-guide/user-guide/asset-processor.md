---
title: Verarbeitung von Assets
description: Erfahren Sie, wie Sie Assets verarbeiten
feature: Migration
role: Admin
level: Experienced
exl-id: 27786098-119c-4b7a-8275-8a89d435294f
source-git-commit: 62221031e445ccdbf1f2567f38fa888ff52017d4
workflow-type: tm+mt
source-wordcount: '651'
ht-degree: 0%

---

# Verarbeiten von Assets

In datenintensiven Workflows wie der Veröffentlichung ist ein effizientes Asset-Management entscheidend für die Aufrechterhaltung von Leistung und Zuverlässigkeit. Der Asset-Verarbeitungs-Workflow dient zum Verwalten benutzerspezifischer Assets, die intensive Datenvorgänge erfordern. Sie gilt in erster Linie für zwei Fälle: wenn die anfängliche Verarbeitung aufgrund von Fehlern fehlschlägt oder wenn Dateien unverarbeitet bleiben, da kein Asset-Verarbeitungs-Trigger initiiert wurde. Durch die Aktivierung einer zielgerichteten Verarbeitung auf Ordnerebene können Benutzer nur die erforderlichen Assets isolieren und verarbeiten und so den Verwaltungsaufwand für unnötige Berechnungen vermeiden. Dieser selektive Ansatz verbessert die Leistung erheblich und verringert den Zeitaufwand für kritische Vorgänge wie die Veröffentlichung und die Berichterstellung. Insgesamt trägt sie zu mehr Effizienz und Geschwindigkeit bei der Bearbeitung komplexer Datenaufgaben bei.

>[!NOTE]
>
> - Bei großen Datensätzen ist es am besten, die Verarbeitung außerhalb der Spitzenzeiten auszuführen, um eine Beeinträchtigung der Systemleistung zu vermeiden. Nachdem die Verarbeitungsaufgabe abgeschlossen ist, können Sie die Details überprüfen, um die Ergebnisse zu analysieren.<br>
>- Die Asset-Verarbeitung für den `/content/dam`-Trigger erfolgt alle 15 Minuten. Während jedes Zyklus werden Assets aufgenommen, die innerhalb des letzten 15-Minuten-Intervalls neu hinzugefügt wurden oder unverarbeitet blieben, und erneut verarbeitet. Um die Ansicht der Funktion für die automatische Asset-Verarbeitung zu konfigurieren, [&#x200B; Sie „Asset-Verarbeitungsfunktion konfigurieren](../cs-install-guide/configure-asset-processing-cs.md).

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

   Das **Neuer Prozess**-Dialogfeld wird geöffnet.

   ![New-process-asset-processor](images/new-asset-processor.png){width="350" align="left"}

1. Geben Sie die folgenden Details im Dialogfeld an:

   1. **Funktionstyp**: Wählen Sie **Asset-Verarbeitung** aus der Dropdown-Liste aus.
   1. **Ordner und Dateien auswählen**: Navigieren Sie zu und wählen Sie einen oder mehrere Ordner und Dateien aus, die verarbeitet werden sollen.
   1. **Zu ignorierende Ordner auswählen** Wählen Sie optional Unterordner im ausgewählten übergeordneten Ordner aus, die von der Verarbeitung ausgeschlossen werden sollen.
   1. **Asset-Typ**: Wählen Sie aus der Dropdown-Liste den spezifischen Asset-Typ aus, der verarbeitet werden soll (z. B. DITA Topic, DITA Map, Markdown, HTML/CSS, DITAVAL oder andere Dateien). Nur der ausgewählte Asset-Typ wird aus den zuvor angegebenen Ordnern verarbeitet.
Beispiel: Durch Auswahl von DITA Topic werden nur DITA-Themen innerhalb des ausgewählten Ordners verarbeitet, was eine zielgerichtete Filterung ermöglicht.
   1. **Erstellt nach/Erstellt vor**: Wenden Sie Datumsfilter an, um Assets zu verarbeiten, die innerhalb des angegebenen Zeitraums erstellt wurden.

   >[!NOTE]
   >
   > Wenn bereits ein Prozess für einen Ordner ausgeführt wird, können Sie für denselben Ordner erst dann einen neuen Prozess starten, wenn die aktuelle Aufgabe abgeschlossen ist.

1. Wählen Sie **Erstellen**. Es erscheint ein Popup mit der Meldung **Erfolg und der Prozess wurde erfolgreich ausgelöst**. Im Fenster wird der Status der Verarbeitungsaufgabe angezeigt.

   ![Message-Asset-Processor](images/message-asset-processor.png){width="350" align="left"}


## Zusätzliche Optionen für Asset-Verarbeitungsaufgaben

Zusätzliche Optionen stehen für die Verarbeitungsaufgabe zur Verfügung, sobald sie initiiert wurde. Sie können auf diese Optionen zugreifen, indem Sie den Mauszeiger über die Ausführungs-ID Ihrer Aufgabe bewegen. Details zu diesen Optionen finden Sie unten:

- **Neu starten** : Startet die zuvor erfolgreiche Asset-Verarbeitungsaufgabe neu.

  ![restart-asset-processor](images/restart-asset-processor.png){width="650" align="left"}

- **Fortsetzen** : Setzt die zuvor abgebrochene oder fehlgeschlagene Asset-Verarbeitungsaufgabe fort.

  ![resume-asset-processor](images/resume-asset-processor.png){width="650" align="left"}

- **Abbrechen** : Bricht die derzeit ausgeführte Asset-Verarbeitungsaufgabe ab.

  ![cancel-asset-processor](images/cancel-asset-processor.png){width="650" align="left"}

- **Protokolle anzeigen**: Zeigt die Protokolle für die Asset-Verarbeitungsaufgabe an. Für laufende Aufgaben zeigt das Protokoll detaillierte Verarbeitungsinformationen an, einschließlich der geschätzten verbleibenden Zeit und des Asset-Status. Diese Protokollliste zeigt die neuesten 500 Einträge an. Das vollständige Protokoll kann heruntergeladen werden.

  ![logs-asset-processor](images/logs-asset-processor.png){width="650" align="left"}
