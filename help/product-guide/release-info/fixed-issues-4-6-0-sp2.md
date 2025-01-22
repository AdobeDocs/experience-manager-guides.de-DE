---
title: Versionshinweise zu | Es wurden Probleme in Adobe Experience Manager Guides 4.6.0 Service Pack 3 behoben
description: Erfahren Sie mehr über die Fehlerbehebungen in der Version 4.6.0 Service Pack 3 von Adobe Experience Manager Guides
role: Leader
source-git-commit: d60fea16831af458c479df24c877ef7095b2fd15
workflow-type: tm+mt
source-wordcount: '373'
ht-degree: 0%

---

# Es wurden Probleme in Version 4.6.0 Service Pack 3 (Januar 2025) behoben


Dieser Artikel behandelt die in verschiedenen Bereichen von Version 4.6.0 Service Pack 3 von Adobe Experience Manager Guides behobenen Fehler.

Erfahren Sie mehr [Upgrade-Anweisungen für Version 4.6.0 Service Pack 3](upgrade-instructions-4-6-0-sp2.md).

## Authoring

- Alle Bedingungsgruppen gehen verloren und die Bedingungen werden reduziert, wenn die Bedingungen aus dem Ordnerprofil aktualisiert werden. 23526)
- Beim Ändern des Werts der Kopfzeilen für eine Tabelle im Bedienfeld **Inhaltseigenschaften** wird der aktualisierte Wert nicht angewendet. 23213)
- Beim Hinzufügen neuer Themenverweise in DITA Map mit dem Elementdialog **Themenreferenz** in der Layout-Ansicht werden die hinzugefügten Verweise als beschädigter Link angezeigt. 22859)
- Beim Hinzufügen von Themen in DITA Map mit dem **Themenreferenz** Elementdialog in der Autorenansicht werden die ausgewählten Themen in umgekehrter Reihenfolge der Auswahl eingefügt. 22858)
- Wenn Sie ein Bild aus einem externen Produkt (z. B. MS PowerPoint) kopieren und in Handbücher einfügen, wird die Funktion zum schnellen Hochladen des Assets für die Verwendung in der Datei unterbrochen. 24983)
- Bei der Suche nach Dateien im Repository mit **Search &amp; Filter**-Funktion können nicht mehrere Dateien ausgewählt werden. 25104)

## Veröffentlichung

- Das Veröffentlichen in Salesforce schlägt fehl, wenn Inhalte Leerzeichen enthalten. 23664)
- Bei Themen mit Fehlern wie fehlerhaften Links schlägt die Salesforce-Veröffentlichung fehl und die Fortschrittsleiste wird unbegrenzt angezeigt. 22985)
- Bei Karten mit fehlerhaften Links schlägt die Salesforce-Veröffentlichung fehl und die Fortschrittsleiste wird unbegrenzt angezeigt. 24963)
- Wenn ein externer Link eine UUID enthält, geht er in die Nachbearbeitung und konvertiert den externen Link in einen UUID-Link, wodurch der Link im Web-Editor und auch auf den Veröffentlichungsseiten unterbrochen wird. 22574)
- Die `xref` wird auch dann in einen relativen Link konvertiert, wenn **Umfang** des Links auf &quot;**&quot;**. 23059)
- Die native PDF-Generierung schlägt für Inhalte fehl **wobei das Attribut** chunk“ auf &quot;**-content“**. 21772)
- Das **Eigenschaften bearbeiten** für eine Baseline zeigt nicht die zuvor gespeicherten Kriterien für eine dynamische Baseline an. 23964)


## Übersetzung

- Bei einer nicht-veralteten Übersetzung (für Nicht-UUID) führt das Verschieben eines Themas im Quellpfad in einen anderen Ordner zu fehlerhaften Verweisen im Zielgebietsschema. 24152)
