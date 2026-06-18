---
title: Versionshinweise | Behobene Probleme in Adobe Experience Manager Guides 4.6.0 Service Pack 3
description: Erfahren Sie mehr über die Fehlerbehebungen in der Version 4.6.0 Service Pack 3 von Adobe Experience Manager Guides
role: Leader
exl-id: 8ff26c28-4a88-4eb2-b359-5b1b0138dd4b
TQID: https://experienceleague.adobe.com/bsiTHK--FPkvfF4bdYUnL-HbAMuhtBKj7wT2eCmd7hM
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2:
  - id: a3bd6397-2eb2-4908-a61c-226e26855dca
  - id: ab01a588-7dea-43f2-a699-0b3f128465d6
subfeature_v2:
  - id: ad602516-aca3-4247-9ae8-f393d958efa9
  - id: f89f75b0-cf2e-4e96-aec8-fe8c39cbd0ef
role_v2:
  - id: f8a45b24-4be7-4f1b-909b-60d06b483a20
source-git-commit: cc73b81787a3c3dbe8390d93e558064327e59965
workflow-type: tm+mt
source-wordcount: 370
ht-degree: 4%

---

# Es wurden Probleme in Version 4.6.0 Service Pack 3 (Januar 2025) behoben


Dieser Artikel behandelt die in verschiedenen Bereichen von Version 4.6.0 Service Pack 3 von Adobe Experience Manager Guides behobenen Fehler.

Erfahren Sie mehr [Upgrade-Anweisungen für Version 4.6.0 Service Pack 3](upgrade-instructions-4-6-0-sp2.md).

## Authoring

- Alle Bedingungsgruppen gehen verloren und die Bedingungen werden reduziert, wenn die Bedingungen aus dem Ordnerprofil aktualisiert werden. (23526)
- Beim Ändern des Werts der Kopfzeilen für eine Tabelle im Bedienfeld **Inhaltseigenschaften** wird der aktualisierte Wert nicht angewendet. (23213)
- Beim Hinzufügen neuer Themenverweise in DITA Map mit dem Elementdialog **Themenreferenz** in der Layout-Ansicht werden die hinzugefügten Verweise als beschädigter Link angezeigt. (22859)
- Beim Hinzufügen von Themen in DITA Map mit dem **Themenreferenz** Elementdialog in der Autorenansicht werden die ausgewählten Themen in umgekehrter Reihenfolge der Auswahl eingefügt. (22858)
- Wenn Sie ein Bild aus einem externen Produkt (z. B. MS PowerPoint) kopieren und in Handbücher einfügen, wird die Funktion zum schnellen Hochladen des Assets für die Verwendung in der Datei unterbrochen. (24983)
- Bei der Suche nach Dateien im Repository mit **Search &amp; Filter**-Funktion können nicht mehrere Dateien ausgewählt werden. (25104)

## Publishing

- Das Veröffentlichen in Salesforce schlägt fehl, wenn Inhalte Leerzeichen enthalten. (23664)
- Bei Themen mit Fehlern wie fehlerhaften Links schlägt die Salesforce-Veröffentlichung fehl und die Fortschrittsleiste wird unbegrenzt angezeigt. (22985)
- Bei Karten mit fehlerhaften Links schlägt die Salesforce-Veröffentlichung fehl und die Fortschrittsleiste wird unbegrenzt angezeigt. (24963)
- Wenn ein externer Link eine UUID enthält, wird er in der Nachbearbeitung verwendet und der externe Link wird in den UUID-Link konvertiert, wodurch der Link im Editor und auch auf den Veröffentlichungs-Sites unterbrochen wird. (22574)
- Die `xref` wird auch dann in einen relativen Link konvertiert, wenn **Umfang** des Links auf &quot;**&quot;**. (23059)
- Die native PDF-Generierung schlägt für Inhalte fehl **wobei das Attribut** chunk“ auf &quot;**-content“**. (21772)
- Das **Eigenschaften bearbeiten** für eine Baseline zeigt nicht die zuvor gespeicherten Kriterien für eine dynamische Baseline an. (23964)


## Übersetzung

- Bei einer nicht-veralteten Übersetzung (für Nicht-UUID) führt das Verschieben eines Themas im Quellpfad in einen anderen Ordner zu fehlerhaften Verweisen im Zielgebietsschema. (24152)
