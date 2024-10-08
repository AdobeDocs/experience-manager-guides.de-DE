---
title: Konvertierungs-Prozess-Ereignishandler
description: Erfahren Sie mehr über den Konversionsprozess-Ereignishandler
exl-id: 8033935d-2113-4e39-ab74-b7431b89f948
feature: Conversion Process Event Handler
role: Developer
level: Experienced
source-git-commit: 83966cc9187b13dd3b5956821e0aa038b41db28e
workflow-type: tm+mt
source-wordcount: '189'
ht-degree: 3%

---

# Konvertierungs-Prozess-Ereignishandler {#id175UB30E05Z}

AEM Guides stellt das com/adobe/fmdita/conversion/complete -Ereignis bereit, das nach Abschluss eines Dokumentkonvertierungsprozesses für alle Nachbearbeitungsvorgänge verwendet wird. Dieses Ereignis wird ausgelöst, wenn ein Nicht-DITA-Dokument in das DITA-Dateiformat migriert wird. Wenn Sie beispielsweise eine Konvertierung von Word nach DITA oder von InDesign nach DITA durchführen, wird dieses Ereignis nach Abschluss des Konvertierungsprozesses aufgerufen.

Sie müssen einen AEM Ereignishandler erstellen, um die in diesem Ereignis verfügbaren Eigenschaften zu lesen und eine weitere Verarbeitung durchzuführen.

Ereignisdetails werden nachfolgend erläutert:

**Ereignisname**:

```HTTP
com/adobe/fmdita/conversion/complete 
```

**Parameter**:

| Name | Typ | Beschreibung |
|----|----|-----------|
| `status` | Zeichenfolge | Der Rückgabestatus für den ausgeführten Vorgang. Die möglichen Optionen sind: -   ERFOLG: Der Konvertierungsprozess wurde erfolgreich abgeschlossen. <br> -   MIT FEHLERN ABGESCHLOSSEN: Der Konvertierungsprozess ist abgeschlossen, allerdings mit einigen Fehlern. <br>-   FEHLGESCHLAGEN: Der Konvertierungsprozess schlug aufgrund eines schwerwiegenden Fehlers fehl. |
| `filePath` | Zeichenfolge | Absoluter Pfad der Quelldatei \(zu konvertieren\) im AEM Repository. |
| `outputPath` | Zeichenfolge | Absoluter Pfad des Zielorts, an dem die konvertierten DITA-Dateien gespeichert werden. |
| `logPath` | Zeichenfolge | Absoluter Pfad des Knotens, in dem das Konvertierungsprotokoll gespeichert wird. |
