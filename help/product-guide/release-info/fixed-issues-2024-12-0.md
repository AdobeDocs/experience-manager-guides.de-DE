---
title: Versionshinweise zu | Es wurden Probleme in der Version 2024.12.0 von Adobe Experience Manager Guides behoben
description: Erfahren Sie mehr über die Fehlerbehebungen in der Version 2024.12.0 von Adobe Experience Manager Guides as a Cloud Service.
source-git-commit: f643a4a22151af2ff14288ab3885c1a6657a80ca
workflow-type: tm+mt
source-wordcount: '299'
ht-degree: 1%

---

# Es wurden Probleme in der Version 2024.12.0 behoben

Dieser Artikel behandelt die in verschiedenen Bereichen der Version 2024.12.0 von Adobe Experience Manager Guides as a Cloud Service behobenen Fehler.

Erfahren Sie mehr [Upgrade-Anweisungen für die Version 2024.12.0](./upgrade-instructions-2024-12-0.md).

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

- Beim Bearbeiten und anschließenden Speichern einer Baseline in einer Cloud-Einrichtung tritt nach einer Minute ein Timeout auf, wenn die Baseline eine große Anzahl von Themen oder Karten hat. 19558)

## Übersetzung

- Die Zuordnungsübersetzung mithilfe der Grundlinie wird langsam und schlägt schließlich fehl, die Liste aller zugehörigen Themen und Zuordnungsdateien zu laden. 19733)
