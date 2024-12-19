---
title: Versionshinweise zu | Es wurden Probleme in der Version 2024.10.0 Service Pack 1 von Adobe Experience Manager Guides behoben
description: Erfahren Sie mehr über die Fehlerbehebungen in der Version 2024.10.0 Service Pack 1 von Adobe Experience Manager Guides as a Cloud Service.
exl-id: d5fa200b-1f15-4ec2-adf9-a29382afc3de
source-git-commit: 682eaf6f4a3a158f49a8f2ea91ce9cd2de3ff772
workflow-type: tm+mt
source-wordcount: '302'
ht-degree: 1%

---

# Es wurden Probleme in der Version 2024.10.0 von Service Pack 1 behoben

Dieser Artikel behandelt die in verschiedenen Bereichen der Version 2024.10.0 Service Pack 1 von Adobe Experience Manager Guides as a Cloud Service behobenen Fehler.

## Authoring

- Die Erstellung einer DITA-Zuordnung für eine UUID-Instanz schlägt fehl, wenn `xmleditor.uniquefilenames` in `XMLEditorConfig` aktiviert ist. 21201)
- Beim Schließen einer Datei werden im Dialogfeld **Änderungen speichern und Datei entsperren** hinzugefügte Kommentare und Beschriftungen nicht mit der neuen Version im Versionsverlauf gespeichert. Dies gilt speziell für einen Anwendungsfall, bei dem **Beim Schließen nach Einchecken fragen** oder **Beim Schließen nach neuer Version** fragen) in `XMLEditorConfig` aktiviert ist. 20065)
- Der als &quot;**&quot; markierte Dokumentstatus** vor dem Speichern einer neuen Version wieder auf **Entwurf** zurück, was dazu führt, dass der **Fertig**-Status in keiner Dokumentversion bestehen bleibt. 20006)
- Eine PDF-Datei kann nicht als Bildreferenz zu einem Thema im Web-Editor hinzugefügt werden. 21206)
- Wenn Sie in der Assets-Benutzeroberfläche eine DITA-Datei auswählen, wird die Option **Auf FrameMaker öffnen** angezeigt, auch wenn sie in der Konfiguration deaktiviert ist. 20082)

## Veröffentlichung

- In der nativen PDF-Ausgabe fehlen Kapiteltitel im Inhaltsverzeichnis, was zu einer falschen Hierarchie führt. 21840)


## Verwaltung

- Ressourcenlecks treten aufgrund von „Unclosed ResourceResolver **-Fehlern** Protokollen auf. 18488)
- Beim Erstellen einer neuen oder doppelten Baseline werden Kennzeichnungen in zufälliger Reihenfolge angezeigt. 19307)


## Grundlinie

- Nach einer Minute tritt beim Bearbeiten und anschließenden Speichern einer Baseline in einer Cloud-Einrichtung eine Zeitüberschreitung auf, wenn die Baseline eine große Anzahl von Themen oder Karten hat. 19558)

## Übersetzung

- Die Map-Übersetzung mithilfe der Baseline wird langsam und schlägt schließlich fehl beim Laden der Liste aller zugehörigen Themen und Zuordnungsdateien. 19733)
