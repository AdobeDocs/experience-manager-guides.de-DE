---
title: Versionshinweise | Es wurden Probleme in der Version 2024.10.0 Service Pack 1 von Adobe Experience Manager Guides behoben
description: Erfahren Sie mehr über die Fehlerbehebungen in der Version 2024.10.0 Service Pack 1 von Adobe Experience Manager Guides as a Cloud Service.
exl-id: d5fa200b-1f15-4ec2-adf9-a29382afc3de
TQID: https://experienceleague.adobe.com/ziRAAFKf5Dl-6Hd7ziXwSJepbiVzkXLGz5jDWIILPkU
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2:
  - id: a3bd6397-2eb2-4908-a61c-226e26855dca
  - id: ab01a588-7dea-43f2-a699-0b3f128465d6
  - id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
subfeature_v2:
  - id: ad602516-aca3-4247-9ae8-f393d958efa9
  - id: d4f22c6d-7923-41e5-9da3-527ff8df4bc8
  - id: f89f75b0-cf2e-4e96-aec8-fe8c39cbd0ef
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 299
ht-degree: 5%

---

# Es wurden Probleme in der Version 2024.10.0 von Service Pack 1 behoben

Dieser Artikel behandelt die in verschiedenen Bereichen der Version 2024.10.0 Service Pack 1 von Adobe Experience Manager Guides as a Cloud Service behobenen Fehler.

## Authoring

- Die Erstellung einer DITA-Zuordnung für eine UUID-Instanz schlägt fehl, wenn `xmleditor.uniquefilenames` in `XMLEditorConfig` aktiviert ist. (21201)
- Beim Schließen einer Datei werden im Dialogfeld **Änderungen speichern und Datei entsperren** hinzugefügte Kommentare und Beschriftungen nicht mit der neuen Version im Versionsverlauf gespeichert. Dies gilt speziell für einen Anwendungsfall, bei dem **Beim Schließen nach Einchecken fragen** oder **Beim Schließen nach neuer Version** fragen) in `XMLEditorConfig` aktiviert ist. (20065)
- Der als &quot;**&quot; markierte Dokumentstatus** vor dem Speichern einer neuen Version wieder auf **Entwurf** zurück, was dazu führt, dass der **Fertig**-Status in keiner Dokumentversion bestehen bleibt. (20006)
- Es ist nicht möglich, eine PDF-Datei als Bildreferenz zu einem Thema im Web-Editor hinzuzufügen. (21206)
- Wenn Sie in der Assets-Benutzeroberfläche eine DITA-Datei auswählen, wird die Option **In FrameMaker öffnen** angezeigt, auch wenn sie in der Konfiguration deaktiviert ist. (20082)

## Publishing

- In der nativen PDF-Ausgabe fehlen Kapiteltitel im Inhaltsverzeichnis, was zu einer falschen Hierarchie führt. (21840)


## Verwaltung

- Ressourcenlecks treten aufgrund von „Unclosed ResourceResolver **-Fehlern** Protokollen auf. (18488)
- Beim Erstellen einer neuen oder doppelten Baseline werden Kennzeichnungen in zufälliger Reihenfolge angezeigt. (19307)


## Grundlinie

- Nach einer Minute tritt beim Bearbeiten und anschließenden Speichern einer Baseline in einer Cloud-Einrichtung eine Zeitüberschreitung auf, wenn die Baseline eine große Anzahl von Themen oder Karten hat. (19558)

## Übersetzung

- Die Map-Übersetzung mithilfe der Baseline wird langsam und schlägt schließlich fehl beim Laden der Liste aller zugehörigen Themen und Zuordnungsdateien. (19733)
