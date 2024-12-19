---
title: Bericht zum Konversionsstatus
description: Konvertieren von Dokumenten verschiedener Formate in AEM Guides in DITA. Erfahren Sie, wie Sie Filter hinzufügen und einen Konversionsstatusbericht anzeigen.
exl-id: 0a4699e5-865f-40e1-a17f-5e1a248ea955
feature: Report Generation
role: User
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '319'
ht-degree: 0%

---

# Bericht zum Konversionsstatus {#id205BBA00WZZ}

AEM Guides bietet eine leistungsstarke Konvertierungsfunktion zum Konvertieren von Dokumenten in verschiedene Formate in DITA. Der Konversionsstatusbericht bietet eine konsolidierte Ansicht aller von AEM Guides ausgeführten Konversionsaufgaben.

Führen Sie die folgenden Schritte aus, um den Konversionsstatusbericht anzuzeigen:

1. Klicken Sie oben auf den Adobe Experience Manager-Link und wählen Sie **Tools** aus.

1. Wählen Sie **Guides** aus der Liste der Tools aus.

1. Klicken Sie auf die **Konversionsstatusbericht**.

   Der Konversionsstatusbericht wird für alle im System ausgeführten Konvertierungsaufgaben angezeigt.

   ![](images/conversion-status-report.png){width="800" align="left"}

1. Die Berichtseite ist in zwei Teile unterteilt:

   - **filter:**

     Sie können die Berichtsdaten nach Dateityp und Konvertierungsstatus filtern. Im Bereich Dateityp können Sie die Berichtsdaten für Word-Dokumente, strukturierte HTML-, XML- und DocBook-Dokumente anzeigen. Im Status können Sie auswählen, ob die Berichtsdaten für Aufgaben angezeigt werden sollen, die erfolgreich ausgeführt wurden, fehlgeschlagen sind, aktiv sind oder sich in der Warteschlange befinden.

     Im folgenden Screenshot werden die Berichtsdaten für Konvertierungsaufgaben mit dem Status Fehlgeschlagen, Aktiv und In Warteschlange angezeigt.

     ![](images/conversion-report-failed-active-queued.png){width="800" align="left"}

   - **Berichtsdaten:**

     Die Berichtsdaten enthalten die folgenden Spalten:

      - **Dateiname**: Name der Quelldatei, für die der Konvertierungsprozess ausgeführt wurde. Durch Klicken auf den Link Dateiname gelangen Sie zum Speicherort des Quelldokuments.

      - **Dateityp**: Typ des Quelldokuments, z. B. Word, strukturiertes HTML, XML und DocBook.

      - **Hinzugefügt von**: Name des Benutzers, der die Konvertierungsaufgabe ausgeführt hat.

      - **Datum hinzugefügt**: Datum, an dem die Aufgabe ausgeführt wurde. Durch Klicken auf den Link Datum hinzugefügt wird die Protokolldatei heruntergeladen.

      - **Path**: Vollständiger Pfad des Quelldokuments.

      - **Status**: Status der Konversionsaufgaben - Erfolg, Fehlgeschlagen, Aktiv oder In Warteschlange.

      - **Ausgabe**: Pfad des erfolgreich konvertierten Dokuments. Durch Klicken auf den Link Ausgabe gelangen Sie zu dem Speicherort, an dem die Ausgabe gespeichert wird.


**Übergeordnetes Thema:**[ Reports](reports-intro.md)
