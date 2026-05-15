---
title: Bericht zum Konversionsstatus
description: Konvertieren von Dokumenten verschiedener Formate in AEM Guides in DITA. Erfahren Sie, wie Sie Filter hinzufügen und einen Konversionsstatusbericht anzeigen.
feature: Report Generation
role: User
hide: true
exl-id: f6bf1033-9c2f-42c7-9ad5-e1060e2c9770
TQID: https://experienceleague.adobe.com/TBeg61eVmHydID-z3dGoQcHJtAY0EzwhuJD9SHpuhwI
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2:
  - id: d90290ec-3e61-4ebd-8649-bcafe0836803
subfeature_v2:
  - id: cdab8659-8d50-4417-b6fd-762f347c13ee
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
topic_v2:
  - id: f5c2a4bb-71ca-4d7e-8efd-442250e6ba48
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 318
ht-degree: 0%

---

# Bericht zum Konversionsstatus {#id205BBA00WZZ}

AEM Guides bietet eine leistungsstarke Konvertierungsfunktion zum Konvertieren von Dokumenten in verschiedene Formate in DITA. Der Konversionsstatusbericht bietet eine konsolidierte Ansicht aller von AEM Guides ausgeführten Konversionsaufgaben.

Führen Sie die folgenden Schritte aus, um den Konversionsstatusbericht anzuzeigen:

1. Klicken Sie oben auf den Adobe Experience Manager-Link und wählen Sie **Tools** aus.

1. Wählen Sie **Guides** aus der Liste der Tools aus.

1. Klicken Sie auf die **Konversionsstatusbericht**.

   Der Konversionsstatusbericht wird für alle im System ausgeführten Konvertierungsaufgaben angezeigt.

   ![](images/conversion-status-report.png){width="800"}

1. Die Berichtseite ist in zwei Teile unterteilt:

   - **filter:**

     Sie können die Berichtsdaten nach Dateityp und Konvertierungsstatus filtern. Im Bereich Dateityp können Sie die Berichtsdaten für Word-Dokumente, strukturierte HTML-, XML- und DocBook-Dokumente anzeigen. Im Status können Sie auswählen, ob die Berichtsdaten für Aufgaben angezeigt werden sollen, die erfolgreich ausgeführt wurden, fehlgeschlagen sind, aktiv sind oder sich in der Warteschlange befinden.

     Im folgenden Screenshot werden die Berichtsdaten für Konvertierungsaufgaben mit dem Status Fehlgeschlagen, Aktiv und In Warteschlange angezeigt.

     ![](images/conversion-report-failed-active-queued.png){width="800"}

   - **Berichtsdaten:**

     Die Berichtsdaten enthalten die folgenden Spalten:

      - **Dateiname**: Name der Quelldatei, für die der Konvertierungsprozess ausgeführt wurde. Durch Klicken auf den Link Dateiname gelangen Sie zum Speicherort des Quelldokuments.

      - **Dateityp**: Typ des Quelldokuments, bei dem es sich um Word, strukturierte HTML, XML und DocBook handeln kann.

      - **Hinzugefügt von**: Name des Benutzers, der die Konvertierungsaufgabe ausgeführt hat.

      - **Datum hinzugefügt**: Datum, an dem die Aufgabe ausgeführt wurde. Durch Klicken auf den Link Datum hinzugefügt wird die Protokolldatei heruntergeladen.

      - **Path**: Vollständiger Pfad des Quelldokuments.

      - **Status**: Status der Konversionsaufgaben - Erfolg, Fehlgeschlagen, Aktiv oder In Warteschlange.

      - **Ausgabe**: Pfad des erfolgreich konvertierten Dokuments. Durch Klicken auf den Link Ausgabe gelangen Sie zu dem Speicherort, an dem die Ausgabe gespeichert wird.


**Übergeordnetes Thema:**&#x200B;[&#x200B; Reports](reports-intro.md)
