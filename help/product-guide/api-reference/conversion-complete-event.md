---
title: Ereignishandler für Konversionsprozess
description: Erfahren Sie mehr über den Ereignis-Handler des Konversionsprozesses
exl-id: 8033935d-2113-4e39-ab74-b7431b89f948
feature: Conversion Process Event Handler
role: Developer
level: Experienced
source-git-commit: 83966cc9187b13dd3b5956821e0aa038b41db28e
workflow-type: tm+mt
source-wordcount: '189'
ht-degree: 3%

---

# Ereignishandler für Konversionsprozess {#id175UB30E05Z}

AEM Guides stellt das Ereignis com/adobe/fmdita/conversion/complete bereit, mit dem nach Abschluss eines Dokumentkonvertierungsprozesses Nachbearbeitungsvorgänge ausgeführt werden. Dieses Ereignis wird ausgelöst, wenn ein Nicht-DITA-Dokument in das DITA-Dateiformat migriert wird. Wenn Sie beispielsweise eine Konvertierung von Word in DITA oder von InDesign in DITA ausführen, wird dieses Ereignis nach dem Ende des Konvertierungsprozesses aufgerufen.

Sie müssen einen AEM-Ereignishandler erstellen, um die in diesem Ereignis verfügbaren Eigenschaften zu lesen und die Verarbeitung fortzusetzen.

Details zum Ereignis werden unten erläutert:

**Ereignisname**:

```HTTP
com/adobe/fmdita/conversion/complete 
```

**Parameter**:

| Name | Typ | Beschreibung |
|----|----|-----------|
| `status` | Zeichenfolge | Der Rückgabestatus für den ausgeführten Vorgang. Die möglichen Optionen sind: -   ERFOLGREICH: Der Konvertierungsprozess wurde erfolgreich abgeschlossen. <br> -   ABGESCHLOSSEN MIT FEHLERN: Der Konvertierungsprozess wurde abgeschlossen, allerdings mit einigen Fehlern. <br>-   FEHLGESCHLAGEN: Der Konvertierungsprozess ist aufgrund eines schwerwiegenden Fehlers fehlgeschlagen. |
| `filePath` | Zeichenfolge | Absoluter Pfad der Quelldatei \(zu konvertieren\) im AEM-Repository. |
| `outputPath` | Zeichenfolge | Absoluter Pfad des Zielspeicherorts, an dem die konvertierten DITA-Dateien gespeichert werden. |
| `logPath` | Zeichenfolge | Absoluter Pfad des Knotens, unter dem das Konvertierungsprotokoll gespeichert wird. |
