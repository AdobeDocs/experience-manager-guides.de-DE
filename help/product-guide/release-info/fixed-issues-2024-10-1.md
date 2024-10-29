---
title: Versionshinweise | Behobene Probleme in der Adobe Experience Manager Guides-Version 2024.10.1
description: Erfahren Sie mehr über die Fehlerkorrekturen in der Version 2024.10.1 von Adobe Experience Manager Guides as a Cloud Service.
source-git-commit: f74362c78532ddd7721faf66789281a8c0704194
workflow-type: tm+mt
source-wordcount: '290'
ht-degree: 1%

---

# Behobene Probleme in Version 2024.10.1

In diesem Artikel werden die in verschiedenen Bereichen der Version 2024.10.1 von Adobe Experience Manager Guides as a Cloud Service behobenen Fehler behandelt.

## Authoring

- Die Erstellung von DITA-Maps auf einer UUID-Instanz schlägt fehl, wenn `xmleditor.uniquefilenames` in `XMLEditorConfig` aktiviert ist. (21201)
- Beim Schließen einer Datei werden Kommentare und Beschriftungen, die im Dialogfeld **Änderungen speichern und Datei entsperren** hinzugefügt wurden, nicht mit der neuen Version im Versionsverlauf gespeichert. Dies ist spezifisch für einen Anwendungsfall, bei dem **Check-in bei Close** oder **Ask for New Version on Close** in `XMLEditorConfig` aktiviert ist. (2006)
- Der Dokumentstatus, der als **Fertig** markiert ist, wird vor dem Speichern einer neuen Version wieder auf **Entwurf** zurückgesetzt, was dazu führt, dass der Status **Fertig** in keiner Dokumentversion beibehalten wird. (2006)
- Eine PDF-Datei kann in einem Thema im Web Editor nicht als Bildverweis hinzugefügt werden. (21206)
- Wenn Sie eine DITA-Datei in der Assets-Benutzeroberfläche auswählen, wird die Option **In FrameMaker öffnen** angezeigt, selbst wenn sie in der Konfiguration deaktiviert ist. (2008)

## Veröffentlichung

- In der nativen PDF-Ausgabe fehlen Kapiteltitel im Inhaltsverzeichnis, was zu einer falschen Hierarchie führt. (21840)


## Verwaltung

- Ressourcenlecks treten aufgrund von **Unclosed ResourceResolver** -Fehlern in Protokollen auf. (18488)
- Beim Erstellen einer neuen oder doppelten Grundlinie werden die Bezeichnungen in zufälliger Reihenfolge angezeigt. (19307)


## Grundlinie

- Bearbeiten und Speichern einer Grundlinie in einer Cloud-Setup-Zeitüberschreitung nach einer Minute, wenn die Grundlinie über eine große Anzahl von Themen oder Maps verfügt. (1958)

## Übersetzung

- Die Übersetzung von Zuordnungen mithilfe von Baseline wird langsam und lädt schließlich nicht die Liste aller zugehörigen Themen und Zuordnungsdateien. (1973)