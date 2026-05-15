---
title: Versionshinweise | Behobene Probleme in Adobe Experience Manager Guides 4.6.0 Service Pack 1
description: Erfahren Sie mehr über die Fehlerbehebungen in Version 4.6.0 Service Pack 1 von Adobe Experience Manager Guides
role: Leader
exl-id: ab45ac10-8a97-4ade-accc-2b884da0e973
TQID: https://experienceleague.adobe.com/-PGxudGeachzaYoru1fHTObZcwRuXzle5s7KRRJlfBA
product_v2: id: fae5e35a-80c9-4b94-9352-1a060a6aab1did: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2: id: a3bd6397-2eb2-4908-a61c-226e26855dcaid: ab01a588-7dea-43f2-a699-0b3f128465d6id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
subfeature_v2: id: ad602516-aca3-4247-9ae8-f393d958efa9id: d4f22c6d-7923-41e5-9da3-527ff8df4bc8id: f89f75b0-cf2e-4e96-aec8-fe8c39cbd0ef
role_v2: id: f8a45b24-4be7-4f1b-909b-60d06b483a20
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 312
ht-degree: 4%

---

# Es wurden Probleme in Version 4.6.0 Service Pack 1 (Oktober 2024) behoben


Dieser Artikel behandelt die in verschiedenen Bereichen von Version 4.6.0 Service Pack 1 von Adobe Experience Manager Guides behobenen Fehler.

Erfahren Sie mehr über [Upgrade-Anweisungen für die Version 4.6.0 Service Pack 1](upgrade-instructions-4-6-0-sp1.md).

## Authoring

- Die Erstellung einer DITA-Zuordnung für eine UUID-Instanz schlägt fehl, wenn `xmleditor.uniquefilenames` in `XMLEditorConfig` aktiviert ist. (21201)
- Beim Schließen einer Datei werden im Dialogfeld **Änderungen speichern und Datei entsperren** hinzugefügte Kommentare und Beschriftungen nicht mit der neuen Version im Versionsverlauf gespeichert. Dies gilt speziell für einen Anwendungsfall, bei dem **Beim Schließen nach Einchecken fragen** oder **Beim Schließen nach neuer Version** fragen) in `XMLEditorConfig` aktiviert ist. (20065)
- Der als &quot;**&quot; markierte Dokumentstatus** vor dem Speichern einer neuen Version auf **Entwurf** zurück, was dazu führt, dass der **Fertig**-Status in keiner Dokumentversion bestehen bleibt. (20006)
- Es ist nicht möglich, eine PDF-Datei als Bildreferenz zu einem Thema im Web-Editor hinzuzufügen. (21206)
- Wenn Sie in der Assets-Benutzeroberfläche eine DITA-Datei auswählen, wird die Option **In FrameMaker öffnen** angezeigt, auch wenn sie in der Konfiguration deaktiviert ist. (20082)


## Publishing

- Das Hochladen von Anhängen in Salesforce schlägt fehl, wenn der Anlagenpfad die zulässige Länge überschreitet. (19420)
- Beim Veröffentlichen eines Themas in Salesforce können die PDF-Dateiverknüpfungen nicht aufgelöst werden. (19304)
- Der `DUPLICATE_VALUE` tritt gelegentlich auf, wenn versucht wird, einen vorhandenen Artikel in Salesforce erneut zu veröffentlichen. (17932)
- In der nativen PDF-Ausgabe fehlen Kapiteltitel im Inhaltsverzeichnis, was zu einer falschen Hierarchie führt. (21840)
- Beim Veröffentlichen von AEM Sites steht nur eine begrenzte Anzahl von Attributen zur Aufnahme in das Inhaltsverzeichnis zur Verfügung. (7483)

## Verwaltung

- Ressourcenlecks treten aufgrund nicht geschlossener Fehler **ResourceResolver** in Protokollen auf. (18488)
- Beim Erstellen einer neuen oder doppelten Baseline werden Kennzeichnungen in zufälliger Reihenfolge angezeigt. (19307)
