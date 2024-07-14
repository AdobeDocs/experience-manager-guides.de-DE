---
title: Versionshinweise | Behobene Probleme in Adobe Experience Manager Guides, Version 2024.2.0
description: Erfahren Sie mehr über die Fehlerkorrekturen in der Version 2024.2.0 von Adobe Experience Manager Guides as a Cloud Service.
exl-id: fae1ff07-6232-4e9a-a89e-5e760e807b9d
source-git-commit: e40ebf4122decc431d0abb2cdf1794ea704e5496
workflow-type: tm+mt
source-wordcount: '509'
ht-degree: 4%

---

# Behobene Probleme in Version 2024.2.0

In diesem Artikel werden die in verschiedenen Bereichen der Adobe Experience Manager Guides as a Cloud Service-Version 2024.2.0 behobenen Fehler behandelt.

Weitere Informationen zu den neuen Funktionen und Verbesserungen finden Sie unter [Neue Funktionen in Version 2024.2.0](whats-new-2024-2-0.md).

Erfahren Sie mehr über [Upgrade-Anweisungen für Version 2024.2.0](upgrade-instructions-2024-2-0.md).



## Authoring

- Die Rechtschreibprüfung im Editor lässt die Auswahl von Vorschlägen nicht zu. (15045)
- Die globale Navigationsschaltfläche funktioniert nicht und das Dashboard kann nicht geladen werden. (14968)
- Im Web Editor kann die Download-Zuordnungsfunktion keine Popup-Benachrichtigung Trigger werden, wenn sie zum Herunterladen bereit ist. (14626)
- Im Web Editor kann die Funktion zum Herunterladen von Landkarten keine Landkarte mit Grundlinie herunterladen. (14622)
- Ungültiger DTD-Fehler in der Experience Manager Guides as a Cloud Service-Version vom Oktober 2023. (14482)
- Wenn Sie ein Glossarthema aus dem Repository in eine Glossarzuordnung ziehen, wird `topicref` erstellt. (10767)
- Der Vorschaubildschirm für Snippets ist gesperrt. (14840)
- Beschriftungen aus der Datei `labels.json` werden im Web Editor in zufälliger Reihenfolge angezeigt. (10508)

## Veröffentlichung

- Beim nativen PDF-Publishing funktionieren benutzerdefinierte Attribute innerhalb von Bedingungsvorgaben nicht für das native PDF-Publishing. (14943)
- Bei der nativen PDF-Veröffentlichung werden Schlüsselverweise für die Adobe Experience Manager Guides-Version vom Dezember 2023 nicht aufgelöst. (15085)
- Die AEM Sites-Veröffentlichung schlägt fehl und verursacht Bereichsfehler für Dateien mit `xref` in der DITA-Datei, die mit &quot;HTTP&quot;beginnen. (15154)
- Benutzerdefinierte Vorlagen können nicht über die Registerkarte **Ausgaben** im Editor hinzugefügt werden. (14846)
- **AEM Site**-Vorgabe funktioniert aufgrund eines leeren Vorlagenpfads nicht. (14804)
- AEM Neuerstellung der Site schlägt bei DITA-Maps mit Themen fehl, die MathML-Gleichungen enthalten. (14790)
- Bei der nativen PDF-Veröffentlichung gibt die PDF-Generierung Fehler beim Abrufen von Abhängigkeiten für die `Node.js`-Veröffentlichung aus. (14445)
- AEM Vorgabe lässt die Auswahl einer Vorlage außerhalb der `/content`-Hierarchie im Web Editor nicht zu. (14260)
- In der AEM Sites-Ausgabe gingen der Stil oder die Zeilenumbrüche für das Element `<lines>` mit Unterelementen verloren. (12542)
- Benutzerdefinierte Metadaten sind in der endgültigen Ausgabe nicht verfügbar. (12116)
- Bei der nativen PDF-Veröffentlichung können die DITA-Map-Metadateneigenschaften nicht zum Ausfüllen der Metadaten für die PDF-Dateiausgabe verwendet werden. (15159)



## Verwaltung

- **Baseline-Filter**-Dateien funktionieren im Web Editor nicht mit dem Dateinamen. (13486)
- Die Deaktivierung der Indizierung der übergeordneten DITA-Zuordnung, um eine bessere Leistung zu erzielen, kann sich auf die Funktionalität bestimmter Funktionen auswirken.(12213)


## Überprüfung

- Kontextmenü mit Rechtsklick funktioniert nicht bei Verfolgungsänderungen von **Accept** oder **Reject**. (14607)
- Das Umschalten zum Schließen von DITA-Themen im Überprüfungsbildschirm funktioniert in der Adobe Experience Manager Guides-Version vom Dezember 2023 nicht. (14537)
- Das Anpassen von E-Mail-Vorlagen für den Review-Workflow funktioniert nicht mit Überlagerungen. (13954)

## Bekanntes Problem

Adobe hat das folgende bekannte Problem für die Version 2024.2.0 identifiziert:

- Version 1.0 wird nicht auf der Benutzeroberfläche für die duplizierte DITA-Datei angezeigt.
- Die Weitergabe von Asset-Metadaten funktioniert in der Version 2024.2.0 nicht, wobei der Microservice für eine Vorgabe aktiviert ist.
