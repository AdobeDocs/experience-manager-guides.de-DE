---
title: Versionshinweise | Behobene Probleme in der Adobe Experience Manager Guides-Version 4.6.0 Service Pack 1
description: Erfahren Sie mehr über die Fehlerbehebungen in der Version 4.6.0 Service Pack 1 von Adobe Experience Manager Guides.
role: Leader
source-git-commit: 2362870e0e3e6c08df03e8c547bb77de7faa0a02
workflow-type: tm+mt
source-wordcount: '316'
ht-degree: 0%

---


# Es wurden Probleme in der Version 4.6.0 Service Pack 1 (Oktober 2024) behoben


Dieser Artikel behandelt die Fehler, die in verschiedenen Bereichen der Version 4.6.0 Service Pack 1 von Adobe Experience Manager Guides behoben wurden.

Erfahren Sie mehr über [Upgrade-Anweisungen für Version 4.6.0 Service Pack 1](upgrade-instructions-4-6-0-sp1.md).

## Authoring

- Die DITA-Zuordnungserstellung für eine UUID-Instanz schlägt fehl, wenn `xmleditor.uniquefilenames`in `XMLEditorConfig` aktiviert ist. (21201)
- Beim Schließen einer Datei werden Kommentare und Beschriftungen, die im Dialogfeld **Änderungen speichern und Datei entsperren** hinzugefügt wurden, nicht mit der neuen Version im Versionsverlauf gespeichert. Dies ist spezifisch für einen Anwendungsfall, bei dem **Check-in bei Close** oder **Ask for New Version on Close** in `XMLEditorConfig` aktiviert ist. (2006)
- Der Dokumentstatus, der als **Fertig** markiert ist, wird vor dem Speichern einer neuen Version auf **Entwurf** zurückgesetzt, was dazu führt, dass der Status **Fertig** in keiner Dokumentversion beibehalten wird. (2006)
- Eine PDF-Datei kann in einem Thema im Web Editor nicht als Bildverweis hinzugefügt werden. (21206)
- Wenn Sie eine DITA-Datei in der Assets-Benutzeroberfläche auswählen, wird die Option **In FrameMaker öffnen** angezeigt, selbst wenn sie in der Konfiguration deaktiviert ist. (2008)


## Veröffentlichung

- Das Hochladen von Anlagen in Salesforce schlägt fehl, wenn der Anlagenpfad die zulässige Länge überschreitet. (19420)
- Beim Veröffentlichen eines Themas in Salesforce können die PDF-Dateilinks nicht aufgelöst werden. (19304)
- Der Fehler `DUPLICATE_VALUE` tritt gelegentlich auf, wenn versucht wird, einen vorhandenen Artikel in Salesforce erneut zu veröffentlichen. (17932)
- In der nativen PDF-Ausgabe fehlen Kapiteltitel im Inhaltsverzeichnis, was zu einer falschen Hierarchie führt. (21840)
- Beim Veröffentlichen von AEM Sites ist nur eine begrenzte Anzahl von Attributen für die Einbeziehung in das Inhaltsverzeichnis verfügbar. (7483)

## Verwaltung

- Ressourcenlecks treten aufgrund von nicht geschlossenen **ResourceResolver** -Fehlern in Protokollen auf. (18488)
- Beim Erstellen einer neuen oder doppelten Grundlinie werden die Bezeichnungen in zufälliger Reihenfolge angezeigt. (19307)









