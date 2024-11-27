---
title: Konversionsstatusbericht
description: Konvertieren Sie in AEM Guides Dokumente unterschiedlicher Formate in DITA. Erfahren Sie, wie Sie Filter hinzufügen und einen Konversionsstatusbericht anzeigen.
exl-id: 0a4699e5-865f-40e1-a17f-5e1a248ea955
feature: Report Generation
role: User
source-git-commit: 7db3df07fd17eecae1c502554118ca12f95fb5ab
workflow-type: tm+mt
source-wordcount: '319'
ht-degree: 0%

---

# Konversionsstatusbericht {#id205BBA00WZZ}

AEM Guides bietet eine zuverlässige Konvertierungsfunktion, um Dokumente mit verschiedenen Formaten in DITA zu konvertieren. Der Konversionsstatusbericht bietet eine konsolidierte Ansicht aller von AEM Guides ausgeführten Konversionsaufgaben.

Führen Sie die folgenden Schritte aus, um den Konversionsstatusbericht anzuzeigen:

1. Klicken Sie oben auf den Adobe Experience Manager-Link und wählen Sie **Tools** aus.

1. Wählen Sie **Guides** aus der Liste der Tools aus.

1. Klicken Sie auf die Kachel **Konversionsstatusbericht** .

   Der Konversionsstatusbericht wird für alle Konversionsaufgaben angezeigt, die auf dem System ausgeführt werden.

   ![](images/conversion-status-report.png){width="800" align="left"}

1. Die Berichtsseite ist in zwei Teile unterteilt:

   - **Filter:**

     Sie können die Berichtsdaten nach Dateityp und Konvertierungsstatus filtern. Im Dateityp können Sie die Berichtsdaten für Word-Dokumente, strukturierte HTML, XML und DocBook-Dokumenttypen anzeigen. Im Status können Sie festlegen, dass die Berichtsdaten für Aufgaben angezeigt werden, die erfolgreich, fehlgeschlagen, aktiv oder in Warteschlange ausgeführt wurden.

     Im folgenden Screenshot werden die Berichtsdaten für Konversionsaufgaben angezeigt, die den Status &quot;Fehlgeschlagen&quot;, &quot;Aktiv&quot;und &quot;In Warteschlange&quot;aufweisen.

     ![](images/conversion-report-failed-active-queued.png){width="800" align="left"}

   - **Berichtsdaten:**

     Die Berichtsdaten enthalten die folgenden Spalten:

      - **Dateiname**: Name der Quelldatei, für die der Konvertierungsprozess ausgeführt wurde. Durch Klicken auf den Link Dateiname gelangen Sie zum Speicherort des Quelldokuments.

      - **Dateityp**: Typ des Quelldokuments, das Word, strukturierte HTML, XML und DocBook sein kann.

      - **Hinzugefügt von**: Name des Benutzers, der die Konversionsaufgabe ausgeführt hat.

      - **Datum hinzugefügt**: Datum, an dem die Aufgabe ausgeführt wurde. Durch Klicken auf den Link Datum hinzugefügt wird die Protokolldatei heruntergeladen.

      - **Pfad**: Vollständiger Pfad des Quelldokuments.

      - **Status**: Status der Konversionsaufgaben - Erfolg, Fehlgeschlagen, Aktiv oder In Warteschlange.

      - **Ausgabe**: Pfad des erfolgreich konvertierten Dokuments. Wenn Sie auf den Link Ausgabe klicken, gelangen Sie zum Speicherort der Ausgabe.


**Übergeordnetes Thema:**[ Berichte](reports-intro.md)
