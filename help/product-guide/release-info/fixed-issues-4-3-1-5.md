---
title: Versionshinweise | Behobene Probleme in Adobe Experience Manager Guides 4.3.1.5
description: Erfahren Sie mehr über die Fehlerbehebungen in der 4.3.1.5 Version von Adobe Experience Manager Guides
role: Leader
exl-id: 082dca28-15da-417c-b511-74eb5ac68078
TQID: https://experienceleague.adobe.com/ujQFyhAp5bIB1OJnmqvbHCaiDip7T2qsjlVAWevykK8
product_v2: id: fae5e35a-80c9-4b94-9352-1a060a6aab1did: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2: id: a3bd6397-2eb2-4908-a61c-226e26855dcaid: ab01a588-7dea-43f2-a699-0b3f128465d6
role_v2: id: f8a45b24-4be7-4f1b-909b-60d06b483a20
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 130
ht-degree: 6%

---

# Es wurden Probleme in der 4.3.1.5 Version behoben


Dieser Artikel behandelt die in verschiedenen Bereichen 4.3.1.5 Version von Adobe Experience Manager Guides behobenen Fehler.



Erfahren Sie mehr [Upgrade-Anweisungen für die 4.3.1.5 Version](../release-info/upgrade-instructions-4-3-1-5.md).


## Authoring

- Das Hinzufügen von Leerzeichen zwischen Inline-Elementen innerhalb von `<codeblock>` führt zu einem Zeilenumbruch in der generierten Ausgabe. (15247)
- Beim Hinzufügen von Elementen aus dem Dialogfeld „Element einfügen“ treten Erlebnisprobleme auf. (15108)

## Publishing

- Fehlerprotokolle zeigen falsche Informationen zur Veröffentlichung von Inhalten mit externen Bereichen an. (15242)
- Interne Links zu DITA-Dateien, die mit `HTTP` beginnen, werden wie externe Links behandelt und verursachen Fehler im Umfang. (15155)
- Die AEM-Site-Regenerierung schlägt für DITA-Zuordnungen fehl. (14369)

## Verwaltung

- **fmditaTopicrefs**-Eigenschaft zeigt relative Pfade anstelle absoluter Pfade an. (15341)
