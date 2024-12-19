---
title: Versionshinweise zu | Es wurden Probleme in Adobe Experience Manager Guides 4.6.0 Service Pack 1 behoben
description: Erfahren Sie mehr über die Fehlerbehebungen in Version 4.6.0 Service Pack 1 von Adobe Experience Manager Guides
role: Leader
exl-id: ab45ac10-8a97-4ade-accc-2b884da0e973
source-git-commit: 682eaf6f4a3a158f49a8f2ea91ce9cd2de3ff772
workflow-type: tm+mt
source-wordcount: '316'
ht-degree: 0%

---

# Es wurden Probleme in Version 4.6.0 Service Pack 1 (Oktober 2024) behoben


Dieser Artikel behandelt die in verschiedenen Bereichen von Version 4.6.0 Service Pack 1 von Adobe Experience Manager Guides behobenen Fehler.

Erfahren Sie mehr über [Upgrade-Anweisungen für die Version 4.6.0 Service Pack 1](upgrade-instructions-4-6-0-sp1.md).

## Authoring

- Die Erstellung einer DITA-Zuordnung für eine UUID-Instanz schlägt fehl, wenn `xmleditor.uniquefilenames` in `XMLEditorConfig` aktiviert ist. 21201)
- Beim Schließen einer Datei werden im Dialogfeld **Änderungen speichern und Datei entsperren** hinzugefügte Kommentare und Beschriftungen nicht mit der neuen Version im Versionsverlauf gespeichert. Dies gilt speziell für einen Anwendungsfall, bei dem **Beim Schließen nach Einchecken fragen** oder **Beim Schließen nach neuer Version** fragen) in `XMLEditorConfig` aktiviert ist. 20065)
- Der als &quot;**&quot; markierte Dokumentstatus** vor dem Speichern einer neuen Version auf **Entwurf** zurück, was dazu führt, dass der **Fertig**-Status in keiner Dokumentversion bestehen bleibt. 20006)
- Eine PDF-Datei kann nicht als Bildreferenz zu einem Thema im Web-Editor hinzugefügt werden. 21206)
- Wenn Sie in der Assets-Benutzeroberfläche eine DITA-Datei auswählen, wird die Option **Auf FrameMaker öffnen** angezeigt, auch wenn sie in der Konfiguration deaktiviert ist. 20082)


## Veröffentlichung

- Das Hochladen von Anhängen in Salesforce schlägt fehl, wenn der Anlagenpfad die zulässige Länge überschreitet. 19420)
- Beim Veröffentlichen eines Themas in Salesforce können die PDF-Dateiverknüpfungen nicht aufgelöst werden. 19304)
- Der `DUPLICATE_VALUE` tritt gelegentlich auf, wenn versucht wird, einen vorhandenen Artikel in Salesforce erneut zu veröffentlichen. 17932)
- In der nativen PDF-Ausgabe fehlen Kapiteltitel im Inhaltsverzeichnis, was zu einer falschen Hierarchie führt. 21840)
- Beim Veröffentlichen von AEM Sites steht nur eine begrenzte Anzahl von Attributen zur Aufnahme in das Inhaltsverzeichnis zur Verfügung. (7483)

## Verwaltung

- Ressourcenlecks treten aufgrund nicht geschlossener Fehler **ResourceResolver** in Protokollen auf. 18488)
- Beim Erstellen einer neuen oder doppelten Baseline werden Kennzeichnungen in zufälliger Reihenfolge angezeigt. 19307)
