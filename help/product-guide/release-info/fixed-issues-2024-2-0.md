---
title: Versionshinweise | Fehlerkorrektur - Adobe Experience Manager-Handbücher, Version 2024.2.0 - jetzt verfügbar
description: Erfahren Sie mehr über die Fehlerbehebungen in der Version 2024.2.0 der Adobe Experience Manager-Handbücher as a Cloud Service.
source-git-commit: 3da78dd90bd219809d0a47bcdc2775b2c5ba29e1
workflow-type: tm+mt
source-wordcount: '509'
ht-degree: 0%

---

# Behobene Probleme in Version 2024.2.0

Dieser Artikel behandelt die Fehler, die in verschiedenen Bereichen der Version 2024.2.0 von Adobe Experience Manager Guides as a Cloud Service behoben wurden.

Weitere Informationen zu den neuen Funktionen und Verbesserungen finden Sie unter [Neue Funktionen in Version 2024.2.0](whats-new-2024-2-0.md).

Informationen zu [Upgrade-Anweisungen für die Version 2024.2.0](upgrade-instructions-2024-2-0.md).



## Authoring

- Die Rechtschreibprüfung im Editor lässt die Auswahl von Vorschlägen nicht zu. (15045)
- Die globale Navigationsschaltfläche funktioniert nicht und das Dashboard kann nicht geladen werden. (14968)
- Im Web Editor kann die Download-Zuordnungsfunktion keine Popup-Benachrichtigung Trigger werden, wenn sie zum Herunterladen bereit ist. (14626)
- Im Web Editor kann die Funktion zum Herunterladen von Landkarten keine Landkarte mit Grundlinie herunterladen. (14622)
- Ungültiger DTD-Fehler in der as a Cloud Service Version der Experience Manager-Handbücher vom Oktober 2023. (14482)
- Wenn Sie ein Glossarthema aus dem Repository in eine Glossarzuordnung ziehen, wird `topicref`. (10767)
- Der Vorschaubildschirm für Snippets ist gesperrt. (14840)
- Beschriftungen aus der `labels.json` -Datei in zufälliger Reihenfolge im Web-Editor angezeigt. (10508)

## Veröffentlichung

- Beim nativen PDF-Publishing funktionieren benutzerdefinierte Attribute innerhalb von Bedingungsvorgaben nicht für das native PDF-Publishing. (14943)
- Beim nativen PDF-Publishing werden Schlüsselverweise für die Adobe Experience Manager-Handbücher vom Dezember 2023 nicht aufgelöst. (15085)
- AEM Sites-Veröffentlichung schlägt fehl und verursacht Bereichsfehler bei Dateien mit `xref` in die DITA-Datei, die mit &quot;HTTP&quot;beginnt. (15154)
- Benutzerdefinierte Vorlage kann nicht aus der **Ausgaben** im Editor. (14846)
- **AEM Site** aufgrund eines leeren Vorlagenpfads nicht funktioniert. (14804)
- AEM Neuerstellung der Site schlägt bei DITA-Maps mit Themen fehl, die MathML-Gleichungen enthalten. (14790)
- Bei nativer PDF-Veröffentlichung gibt die PDF-Generierung Fehler beim Abrufen von Abhängigkeiten für aus `Node.js` Publishing. (14445)
- AEM Vorgabe erlaubt die Auswahl einer Vorlage außerhalb der `/content` Hierarchie im Web-Editor. (14260)
- In der AEM Sites-Ausgabe gingen der Stil oder die Zeilenumbrüche für die `<lines>` -Element mit Unterelementen. (12542)
- Benutzerdefinierte Metadaten sind in der endgültigen Ausgabe nicht verfügbar. (12116)
- Bei der nativen PDF-Veröffentlichung können die DITA-Map-Metadateneigenschaften nicht zum Ausfüllen der Metadaten für die PDF-Dateiausgabe verwendet werden. (15159)



## Verwaltung

- **Baseline-Filter** -Dateien funktionieren nicht mit dem Dateinamen im Web-Editor. (13486)
- Die Deaktivierung der Indizierung der übergeordneten DITA-Zuordnung, um eine bessere Leistung zu erzielen, kann sich auf die Funktionalität bestimmter Funktionen auswirken.(12213)


## Überprüfung

- Kontextmenü mit Rechtsklick funktioniert nicht für **Accept** oder **Ablehnen** Änderungen verfolgen. (14607)
- Das Umschalten zum Schließen von DITA-Themen im Überprüfungsbildschirm funktioniert in der Adobe Experience Manager-Handbücher vom Dezember 2023 nicht. (14537)
- Das Anpassen von E-Mail-Vorlagen für den Review-Workflow funktioniert nicht mit Überlagerungen. (13954)

## Bekanntes Problem

Adobe hat das folgende bekannte Problem für die Version 2024.2.0 identifiziert:

- Version 1.0 wird nicht auf der Benutzeroberfläche für die duplizierte DITA-Datei angezeigt.
- Die Weitergabe von Asset-Metadaten funktioniert in der Version 2024.2.0 nicht, wobei der Microservice für eine Vorgabe aktiviert ist.

