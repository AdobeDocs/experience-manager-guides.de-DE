---
title: Ereignishandler für Konversionsprozess
description: Erfahren Sie mehr über den Ereignis-Handler des Konversionsprozesses
exl-id: 8033935d-2113-4e39-ab74-b7431b89f948
feature: Conversion Process Event Handler
role: Developer
level: Experienced
TQID: https://experienceleague.adobe.com/VhlUaVSMTZpfyh5MiJI0WHFpc46s41xjLbuLMUnKH58
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 191
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
