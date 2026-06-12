---
title: Versionshinweise | Behobene Probleme in Adobe Experience Manager Guides Version 2025.07.0
description: Erfahren Sie mehr über die Fehlerbehebungen in der Version 2025.07.0 von Adobe Experience Manager Guides as a Cloud Service.
exl-id: 0744e821-5aee-432b-a6c8-7ed6538935db
TQID: https://experienceleague.adobe.com/xzYzEvtyVvvIpq3tfLftkCDuiC08hahdNhr5ZXcQPo8
product_v2: id: fae5e35a-80c9-4b94-9352-1a060a6aab1did: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2: id: a3bd6397-2eb2-4908-a61c-226e26855dcaid: ab01a588-7dea-43f2-a699-0b3f128465d6
subfeature_v2: id: ad602516-aca3-4247-9ae8-f393d958efa9
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554
topic_v2: id: a004cc84-67b9-4a33-a3a7-8ec7273ef4dcid: ce44533e-8ec8-4e11-a9e9-78b0fe561832
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 520
ht-degree: 4%

---

# Es wurden Probleme in der Version 2025.07.0 behoben

Dieser Artikel behandelt die in verschiedenen Bereichen der Version 2025.07.0 von Adobe Experience Manager Guides as a Cloud Service behobenen Fehler.

Weitere Informationen zu den neuen Funktionen und Verbesserungen finden Sie unter [Neue Funktionen in Version 2025.07.0](whats-new-2025-07-0.md).

Erfahren Sie mehr [Upgrade-Anweisungen für die Version 2025.07.0](upgrade-instructions-2025-07-0.md).

## Authoring

- Wenn ein XML-Kommentar innerhalb eines Elements in der Source-Ansicht hinzugefügt wird, gehen die führenden und nachfolgenden Leerzeichen um den Kommentar verloren, wenn die Ansicht gewechselt wird. (GUIDES-29781)
- Multimediaoptionen funktionieren nicht, wenn sie auf dem Symbol mit den Auslassungspunkten (dem **Mehr**-Menü) in der Symbolleiste vorhanden sind. (GUIDES-29583)
- Beim Erstellen eines neuen Themas über die Assets-Benutzeroberfläche oder den Editor wird das Thema nicht automatisch im Editor geöffnet, wenn die `xmleditor.uniquefilenames` in `XMLEditorConfig` auf „true“ festgelegt ist. (GUIDES-28171)
- Leerzeichen, die innerhalb einer MathML-Gleichung in der Source-Ansicht hinzugefügt werden, bleiben beim Wechseln der Editor-Ansichten nicht erhalten. (GUIDES-26111)

## Asset-Management

- Beim Öffnen eines Themas in der Autorenansicht nach einer Browser-Aktualisierung werden zuvor angewendete Tags im Bedienfeld Dateieigenschaften nicht beibehalten und das Hinzufügen neuer Tags überschreibt die vorhandenen, insbesondere wenn eine große Anzahl von Tags zur Auswahl verfügbar ist. (GUIDES-29078)
- Beim Generieren eines Metadatenberichts für eine DITA-Zuordnung, die eine große Anzahl von Assets enthält, reagiert die Schaltfläche **Verwalten** nicht mehr oder zeigt eine verzögerte Antwort an. (GUIDES-28443)

## Überprüfung

- Versuche, Überprüfungsaufgaben über den AEM-Workflow zu erstellen, schlagen konsequent fehl, da der Überprüfungsknoten nicht erstellt wird. (GUIDES-28214)

## Publishing

- Bei der Bereitstellung des Pakets der AEM Sites-Veröffentlichungskomponenten `guides-components.all-1.3.0.zip` über Cloud Manager tritt ein Code-Qualitätsfehler auf. (GUIDES-28873)
- Beim Veröffentlichen einer DITA-Zuordnung mit `chunk=to-content` Attribut werden doppelte JCR-Knoten in der neuen AEM Sites-Ausgabe erstellt, was zu einer redundanten Inhaltsstruktur in AEM Sites führt. (GUIDES-28104)
- Wenn beim Veröffentlichen einer DITA-Zuordnung mit der neuen AEM Sites-Ausgabe ein Thema das `chunk =to-content` hat und die Ausgabe so eingestellt ist, dass Thementitel als Seitennamen verwendet werden, wird im generierten Seitennamen fälschlicherweise das Wort **Chunk** angezeigt, anstatt den ursprünglichen Themennamen beizubehalten. (GUIDES-28102)
- Die `cq:template` -Eigenschaft, die in der AEM Guides-Themenvorlage für neue AEM Sites-Veröffentlichungen festgelegt ist, zeigt einen falschen Wert an, was sich auf die Vorlagenstruktur und das Rendern von Inhalten auswirkt. (GUIDES-27789)


## Platform

- Bei der Arbeit mit großen Sammlungen treten Leistungsprobleme wie längere Ladezeiten und zeitweise auftretende Zeitüberschreitungen auf. (GUIDES-29065, GUIDES-28793)
- Schwachstellen im Zusammenhang mit der veralteten Guava-Bibliothek, die in auf Experience Manager Guides hochgeladenen AEM Guides-Komponenten verwendet wird. (GUIDES-27402)

## Bekannte Probleme

Adobe hat die folgenden bekannten Probleme in Version 2025.07.0 identifiziert:

- Beim Arbeiten mit Markdown-Themen wird in **Editor-Symbolleiste eine Schaltfläche** Themenreferenz“ angezeigt, sie funktioniert jedoch nicht. (GUIDES-31038)
- Ordner-Knotennamen werden im Editor fälschlicherweise anstelle von Ordnertiteln angezeigt. (GUIDES-30909)
- Im Dialogfeld **Zusammenführen** wird in der Dropdown-Liste fälschlicherweise **Hauptinhalt** angezeigt, anstatt die verfügbaren Versionen des ausgewählten Themas anzuzeigen. (GUIDES-30820)
- Beim Öffnen einer DITA-Map mit aktivierter Unified Shell wird der Editor gelegentlich aktualisiert. (GUIDES-26919)
