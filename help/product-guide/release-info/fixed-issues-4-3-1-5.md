---
title: Versionshinweise zu | Behobene Probleme in Adobe Experience Manager Guides 4.3.1.5
description: Erfahren Sie mehr über die Fehlerbehebungen in der 4.3.1.5 Version von Adobe Experience Manager Guides
role: Leader
exl-id: 082dca28-15da-417c-b511-74eb5ac68078
source-git-commit: e40ebf4122decc431d0abb2cdf1794ea704e5496
workflow-type: tm+mt
source-wordcount: '135'
ht-degree: 2%

---

# Es wurden Probleme in der 4.3.1.5 Version behoben


Dieser Artikel behandelt die in verschiedenen Bereichen 4.3.1.5 Version von Adobe Experience Manager Guides behobenen Fehler.



Erfahren Sie mehr [Upgrade-Anweisungen für die 4.3.1.5 Version](../release-info/upgrade-instructions-4-3-1-5.md).


## Authoring

- Das Hinzufügen von Leerzeichen zwischen Inline-Elementen innerhalb von `<codeblock>` führt zu einem Zeilenumbruch in der generierten Ausgabe. 15247)
- Beim Hinzufügen von Elementen aus dem Dialogfeld „Element einfügen“ treten Erlebnisprobleme auf. 15108)

## Veröffentlichung

- Fehlerprotokolle zeigen falsche Informationen zur Veröffentlichung von Inhalten mit externen Bereichen an. 15242)
- Interne Links zu DITA-Dateien, die mit `HTTP` beginnen, werden wie externe Links behandelt und verursachen Fehler im Umfang. 15155)
- Die Wiederherstellung der AEM-Site schlägt für DITA-Zuordnungen fehl. 14369)

## Verwaltung

- **fmditaTopicrefs**-Eigenschaft zeigt relative Pfade anstelle absoluter Pfade an. 15341)
