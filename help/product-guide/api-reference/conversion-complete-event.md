---
title: Ereignishandler für Konversionsprozess
description: Erfahren Sie mehr über den Ereignis-Handler des Konversionsprozesses
exl-id: 8033935d-2113-4e39-ab74-b7431b89f948
feature: Conversion Process Event Handler
role: Developer
level: Experienced
TQID: 'https://experienceleague.adobe.com/VhlUaVSMTZpfyh5MiJI0WHFpc46s41xjLbuLMUnKH58'
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
    internal-label: Experience Manager Guides
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
    internal-label: Experience Manager
feature_v2:
  - id: c6d09140-3c91-45d3-b7ed-b681af752f43
    internal-label: APIs
subfeature_v2:
  - id: bb416568-e09c-46e3-b3e9-fa7154401215
    internal-label: Conversion process event handler
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
level_v2:
  - id: d378ca77-2da1-4f39-ad92-1917fe974a38
    internal-label: Experienced
source-git-commit: 81a0e7f0736ba4970673dd87a888a4c60d3c1b4e
workflow-type: tm+mt
source-wordcount: '191'
ht-degree: 3%
---
# Ereignishandler für Konversionsprozess {#id175UB30E05Z}

AEM Guides stellt das Ereignis com/adobe/fmdita/conversion/complete bereit, mit dem nach Abschluss eines Dokumentkonvertierungsprozesses Nachbearbeitungsvorgänge ausgeführt werden. Dieses Ereignis wird ausgelöst, wenn ein Nicht-DITA-Dokument in das DITA-Dateiformat migriert wird. Wenn Sie beispielsweise eine Konvertierung von Word in DITA oder von InDesign in DITA ausführen, wird dieses Ereignis nach dem Ende des Konvertierungsprozesses aufgerufen.

Sie müssen einen AEM-Ereignishandler erstellen, um die in diesem Ereignis verfügbaren Eigenschaften zu lesen und weitere Verarbeitungsschritte durchzuführen.

Details zum Ereignis werden unten erläutert:

**Ereignisname**:

```HTTP
com/adobe/fmdita/conversion/complete 
```

**Parameter**:

| Name | Typ | Beschreibung |
|----|----|-----------|
| `status` | Zeichenfolge | Der Rückgabestatus für den ausgeführten Vorgang. Die möglichen Optionen sind: - ERFOLG: Der Konvertierungsprozess wurde erfolgreich abgeschlossen. <br> - ABGESCHLOSSEN MIT FEHLERN: Der Konvertierungsprozess wurde abgeschlossen, allerdings mit einigen Fehlern. <br>- FEHLGESCHLAGEN: Der Konvertierungsprozess ist aufgrund eines schwerwiegenden Fehlers fehlgeschlagen. |
| `filePath` | Zeichenfolge | Absoluter Pfad der Quelldatei \(zu konvertieren\) im AEM-Repository. |
| `outputPath` | Zeichenfolge | Absoluter Pfad des Zielspeicherorts, an dem die konvertierten DITA-Dateien gespeichert werden. |
| `logPath` | Zeichenfolge | Absoluter Pfad des Knotens, unter dem das Konvertierungsprotokoll gespeichert wird. |
