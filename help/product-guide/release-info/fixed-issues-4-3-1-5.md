---
title: Versionshinweise | Behobene Probleme in Adobe Experience Manager Guides Version 4.3.1.5
description: Erfahren Sie mehr über die Fehlerbehebungen in der Adobe Experience Manager Guides-Version 4.3.1.5
role: Leader
exl-id: 082dca28-15da-417c-b511-74eb5ac68078
source-git-commit: e40ebf4122decc431d0abb2cdf1794ea704e5496
workflow-type: tm+mt
source-wordcount: '135'
ht-degree: 2%

---

# Behobene Probleme in Version 4.3.1.5


Dieser Artikel behandelt die Fehler, die in verschiedenen Bereichen der Version 4.3.1.5 von Adobe Experience Manager Guides behoben wurden.



Erfahren Sie mehr über [Upgrade-Anweisungen für Version 4.3.1.5](../release-info/upgrade-instructions-4-3-1-5.md).


## Authoring

- Das Hinzufügen von Leerzeichen zwischen Inline-Elementen innerhalb von `<codeblock>` verursacht einen Zeilenumbruch in der generierten Ausgabe. (15247)
- Beim Hinzufügen von Elementen aus dem Dialogfeld &quot;Element einfügen&quot;treten Erlebnisprobleme auf. (15108)

## Veröffentlichung

- Fehlerprotokolle zeigen falsche Informationen zum Veröffentlichen von Inhalten mit externen Bereichen an. (15242)
- Interne Links zu DITA-Dateien, die mit `HTTP` beginnen, werden wie externe Links behandelt und verursachen Perimeter. (15155)
- AEM Neuerstellung der Site schlägt für DITA-Maps fehl. (14369)

## Verwaltung

- Die Eigenschaft **fmditaTopicrefs** zeigt relative Pfade anstelle absoluter Pfade an. (15341)
