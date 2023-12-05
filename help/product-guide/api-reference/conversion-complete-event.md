---
title: Konvertierungs-Prozess-Ereignishandler
description: Erfahren Sie mehr über den Konversionsprozess-Ereignishandler
exl-id: 8033935d-2113-4e39-ab74-b7431b89f948
source-git-commit: 5e0584f1bf0216b8b00f00b9fe46fa682c244e08
workflow-type: tm+mt
source-wordcount: '189'
ht-degree: 0%

---

# Konvertierungs-Prozess-Ereignishandler {#id175UB30E05Z}

AEM Guides stellen das com/adobe/fmdita/conversion/complete-Ereignis bereit, das nach Abschluss eines Dokumentkonvertierungsprozesses für alle Nachbearbeitungsvorgänge verwendet wird. Dieses Ereignis wird ausgelöst, wenn ein Nicht-DITA-Dokument in das DITA-Dateiformat migriert wird. Wenn Sie beispielsweise eine Konvertierung von Word nach DITA oder von InDesign nach DITA durchführen, wird dieses Ereignis nach Abschluss des Konvertierungsprozesses aufgerufen.

Sie müssen einen AEM Ereignishandler erstellen, um die in diesem Ereignis verfügbaren Eigenschaften zu lesen und eine weitere Verarbeitung durchzuführen.

Ereignisdetails werden nachfolgend erläutert:

**Ereignisname**:

```HTTP
com/adobe/fmdita/conversion/complete 
```

**Parameter**:\
|Name|Typ|Beschreibung| |—|—|—| |`status`|String|Der Rückgabestatus für den ausgeführten Vorgang. Die möglichen Optionen sind: - SUCCESS: Der Konvertierungsprozess wurde erfolgreich abgeschlossen. <br> - MIT FEHLERN ABGESCHLOSSEN: Der Konvertierungsprozess wurde abgeschlossen, jedoch mit einigen Fehlern. <br>- FEHLGESCHLAGEN: Der Konvertierungsprozess schlug aufgrund eines schwerwiegenden Fehlers fehl.| |`filePath`|Zeichenfolge|Absoluter Pfad der Quelldatei \(zu konvertieren\) im AEM Repository.| |`outputPath`|Zeichenfolge|Absoluter Pfad des Zielorts, an dem die konvertierten DITA-Dateien gespeichert werden.| |`logPath`|String|Absoluter Pfad des Knotens, in dem das Konvertierungsprotokoll gespeichert wird.|
