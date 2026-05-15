---
title: Bericht zum Konversionsstatus
description: Konvertieren von Dokumenten verschiedener Formate in AEM Guides in DITA. Erfahren Sie, wie Sie Filter hinzufügen und einen Konversionsstatusbericht anzeigen.
exl-id: 0a4699e5-865f-40e1-a17f-5e1a248ea955
feature: Report Generation
role: User
TQID: https://experienceleague.adobe.com/-Jgxys5YiwelOf7jQHYQ4Y9ARYzwLCZ8lNStdnT4oLI
product_v2: id: fae5e35a-80c9-4b94-9352-1a060a6aab1did: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2: id: a3bd6397-2eb2-4908-a61c-226e26855dcaid: d90290ec-3e61-4ebd-8649-bcafe0836803
subfeature_v2: id: cdab8659-8d50-4417-b6fd-762f347c13ee
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554
topic_v2: id: f5c2a4bb-71ca-4d7e-8efd-442250e6ba48
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 318
ht-degree: 0%

---

# Bericht zum Konversionsstatus {#id205BBA00WZZ}

Adobe Experience Manager Guides bietet eine leistungsstarke Konvertierungsfunktion zum Konvertieren von Dokumenten in verschiedene Formate in DITA. Der Konversionsstatusbericht bietet eine konsolidierte Ansicht aller von Experience Manager Guides ausgeführten Konversionsaufgaben.

Führen Sie die folgenden Schritte aus, um den Konversionsstatusbericht anzuzeigen:

1. Klicken Sie oben auf das Adobe Experience Manager-Logo und anschließend auf **Tools**.

1. Wählen Sie **Guides** aus der Liste der Tools aus.

1. Wählen Sie die **Konversionsstatusbericht** aus.

   Der Konversionsstatusbericht wird für alle im System ausgeführten Konvertierungsaufgaben angezeigt.

   ![](images/conversion-status-report-new.png)

1. Die Berichtseite ist in zwei Teile unterteilt:

   - **filter:**

     Sie können die Berichtsdaten nach Dateityp und Konvertierungsstatus filtern. In der Datei können Sie die Berichtsdaten für Word-Dokumente, strukturierte HTML-, XML-, DocBook- und IDML-Dokumente anzeigen. Im Status können Sie die Berichtsdaten für Aufgaben anzeigen, die erfolgreich ausgeführt wurden, fehlgeschlagen sind, aktiv sind oder sich in der Warteschlange befinden.

     Im folgenden Screenshot werden die Berichtsdaten für Konversionsaufgaben mit dem Status Erfolgreich angezeigt.

     ![](images/conversion-report-failed-active-queued-new.png)

   - **Berichtsdaten:**

     Die Berichtsdaten enthalten die folgenden Spalten:

      - **Dateiname**: Name der Quelldatei, für die der Konvertierungsprozess ausgeführt wurde. Wenn Sie den Link Dateiname auswählen, gelangen Sie zum Speicherort des Quelldokuments.

      - **Dateityp**: Typ des Quelldokuments, bei dem es sich um Word, strukturierte HTML, XML, IDML und DocBook handeln kann.

      - **Hinzugefügt von**: Name des Benutzers, der die Konvertierungsaufgabe ausgeführt hat.

      - **Datum hinzugefügt**: Datum, an dem die Aufgabe ausgeführt wurde. Durch Klicken auf den Link Datum hinzugefügt wird die Protokolldatei heruntergeladen.

      - **Path**: Vollständiger Pfad des Quelldokuments.

      - **Status**: Status der Konversionsaufgaben - Erfolg, Fehlgeschlagen, Aktiv oder In Warteschlange.

      - **Ausgabe**: Pfad des erfolgreich konvertierten Dokuments. Wenn Sie auf den Link Ausgabe klicken, gelangen Sie an den Speicherort, an dem die Ausgabe gespeichert wird.


**Übergeordnetes Thema:**[ Einführung in Berichte](reports-intro.md)
