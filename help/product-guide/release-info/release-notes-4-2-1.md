---
title: Versionshinweise | Upgrade-Anweisungen und behobene Probleme in Adobe Experience Manager Guides Version 4.2.1
description: Erfahren Sie mehr über die Fehlerbehebungen und das Upgrade auf Version 4.2.1 von Adobe Experience Manager Guides
exl-id: a75ec83f-564b-4243-b5c5-341049521adb
feature: Release Notes
role: Leader
TQID: https://experienceleague.adobe.com/nuIWAZRdaGgE-lpjfhk2ptAOeglH8cVhxKZMVPcncYY
product_v2: id: fae5e35a-80c9-4b94-9352-1a060a6aab1did: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2: id: a3bd6397-2eb2-4908-a61c-226e26855dcaid: ab01a588-7dea-43f2-a699-0b3f128465d6id: d90290ec-3e61-4ebd-8649-bcafe0836803
subfeature_v2: id: ad602516-aca3-4247-9ae8-f393d958efa9id: d5ea0417-7932-4688-a3e2-4d3b2e7076a3id: f89f75b0-cf2e-4e96-aec8-fe8c39cbd0ef
role_v2: id: f8a45b24-4be7-4f1b-909b-60d06b483a20
topic_v2: id: a004cc84-67b9-4a33-a3a7-8ec7273ef4dc
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 874
ht-degree: 5%

---

# Version 4.2.1 von Adobe Experience Manager Guides (Mai 2023)

Diese Versionshinweise enthalten die Upgrade-Anweisungen, die Kompatibilitätsmatrix und behobene Probleme in Version 4.2.1 von Adobe Experience Manager Guides (später als *AEM Guides* bezeichnet).

Weitere Informationen zu den neuen Funktionen und Verbesserungen finden Sie unter [Neue Funktionen in Version 4.2.1 von Adobe Experience Manager Guides](whats-new-4-2-1-release.md).

## Upgrade auf Version 4.2.1 von AEM Guides


Sie können Ihre aktuelle Version von AEM Guides einfach auf Version 4.2.1 aktualisieren. Bevor Sie mit der Aktualisierung auf Version 4.2.1 von AEM Guides fortfahren, müssen Sie die folgenden Punkte berücksichtigen:
Sie können Ihre aktuelle Version von AEM Guides auf Version 4.2.1 aktualisieren
* Wenn Sie Version 4.1, 4.1.x oder 4.2 verwenden, können Sie direkt auf Version 4.2.1 aktualisieren.
* Wenn Sie Version 4.0 verwenden, müssen Sie auf Version 4.2 aktualisieren, bevor Sie auf Version 4.2.1 aktualisieren.
* Wenn Sie Version 3.8.5 verwenden, müssen Sie auf Version 4.0 aktualisieren, bevor Sie auf Version 4.2 aktualisieren.
* Wenn Sie eine Version vor 3.8.5 verwenden, lesen Sie den Abschnitt Upgrade von AEM Guides im produktspezifischen Installationshandbuch.

>[!NOTE]
>
>Sie müssen das AEM Service Pack installieren, bevor Sie die AEM Guides-Version aktualisieren.

Weitere Informationen finden Sie unter [Upgrade-Anweisungen](../install-guide/upgrade-xml-documentation.md).

## Kompatibilitätsmatrix

In diesem Abschnitt finden Sie die Kompatibilitätsmatrix für die von AEM Guides 4.2 unterstützten Softwareanwendungen. -Version 1.

### Adobe Experience Manager

**Nicht-UUID**
Version 6.5 Service Pack 15, 14, 13 oder 12

**UUID**
Version 6.5 Service Pack 15, 14, 13 oder 12

Weitere Informationen finden Sie im Abschnitt *Technische Anforderungen* im Handbuch zur Installation und Konfiguration von Adobe Experience Manager Guides.

### FrameMaker und FrameMaker Publishing Server

| Freigabe | FMPS 2022 | FMPS 2020 | FM 2022 | FM 2020 |
| --- | --- | --- | --- | --- |
| 4.2.1 (Nicht-UUID) | 2022 oder höher | 2020.2 oder höher* | 2022 oder höher | 2020.3 oder höher |
| 4.2.1 (UUID) | 2022 oder höher | 2020.2 oder höher* | 2022 oder höher | 2020.4 oder höher |
| | | | |  |

*Die in AEM erstellten Grundlinien und Bedingungen werden ab 2020.2 in FMPS-Versionen unterstützt.

### Sauerstoffanschluss

| Freigabe | Fenster des Sauerstoffanschlusses | Oxygen Connector Mac | In Oxygen Windows bearbeiten | In Oxygen Mac bearbeiten |
| --- | --- | --- |--- |--- |
| 4.2.1 (Nicht-UUID) | 2.2-normal-3 | 2.2-normal-3 | 1,6 | 1,6 |
| 4.2.1 (UUID) | 2.9-uuid-2 | 2.9-uuid-2 | 2,3 | 2,3 |
|  |  |   |  |  |

## Behobene Probleme

Die in verschiedenen Bereichen behobenen Fehler sind unten aufgeführt:

### Authoring

* Navtitle wird aus dem Inhalt entfernt, wenn von der Layout-Ansicht zur Autoren- oder Quellansicht gewechselt wird. (12174)
* Die Schaltfläche „Schließen“ im Web-Editor führt nicht zur AEM-Navigationsseite. (11948)
* Manchmal tritt beim Klicken auf eine DITA-Map ein Anwendungsfehler auf. (11842)
* Problem tritt beim Verschieben (Ziehen und Ablegen) anstelle eines vorhandenen Listenelements auf, bei dem Änderungen nachverfolgen aktiviert ist. (11570)
* Problem beim Verschieben (Ziehen und Ablegen) als neues Listenelement mit aktiviertem „Änderungen verfolgen“. (11569)
* Ein- oder Ausrücken von Listenelementen funktioniert nicht wie erwartet, wenn Änderungen nachverfolgt werden. (11568)
* Beim Hinzufügen von Inhalten zu einer Zeile mit aktivierter Option „Änderungen verfolgen“ und beim Deaktivieren der Option „Änderungen verfolgen“ wird die Option nicht deaktiviert. (11567)
* Schwierigkeiten beim Ziehen und Ablegen eines Listenelements, Text wird anstelle des Listenelements verschoben. (11566)
* Beim Authoring im grün angezeigten Element (Änderungen verfolgen) wird der neue Inhalt als Tracking-Änderung angezeigt, obwohl die Track-Änderung deaktiviert ist. (7021)
* Der Browser (Web-Editor) friert das Laden von Inhalten mit benutzerdefiniertem Schema ein. (11211)
* Native PDF | Beim Erstellen einer Ausgabevorgabe mit der Option „Zu Ordnerprofil hinzufügen“ schlägt die PDF-Generierung mit einer Null Pointer-Ausnahme fehl. (10950)
* Das native Tag &quot;PDF | Image“ fügt allen Bildern das Attribut „display-inline“ hinzu. (10653)
* Das Einfügen von Audio- und Videomultimediadateien schlägt im YouTube-Format unter dem Symbol **Multimedia einfügen** fehl. (11320)
* Ein Validierungsfehler tritt auf, wenn eine Zuordnung mithilfe der Vorlage erstellt wird, die über ein spezielles Titelelement verfügt. (11212)
* Webeditor | Im XML-Editor wird beim Bearbeiten eines Themas ein Leerzeichen ohne Unterbrechung hinzugefügt. (11786)

### Verwaltung

* Die Registerkarte „Berichte“ in der Benutzeroberfläche des Web-Editors zeigt nicht die Themenliste alter DITA-Zuordnungen an, die vor dem Upgrade auf 4.2 erstellt wurden. (11708)

* Die Funktion Dateien hochladen , mit der auf die Schaltfläche „Dateien hochladen“ in der Assets-Benutzeroberfläche zugegriffen werden kann, funktioniert nicht mehr in Version 4.2. (11633)


### Publishing

* Native PDF | Veröffentlichung von Inhalten mit einer Ausgabeklasse mit Brackets() führt zu einem Veröffentlichungsstopp. (11936)
* JSON-Ausgabe | Zuordnen von Metadaten mit Eigenschaftswert als `"value in spaces and double quotes"` führt zu einem Veröffentlichungsfehler. (11933)
* Das Problem tritt bei der AEM-Site-Suche auf (funktioniert nicht über zwei- bis dreistufige Knoten hinaus). (11352)
* Web-Editor | Ausgabepfad und Vorlage können in der AEM-Voreinstellung nicht ausgewählt werden. (11530)
* Beim Upgrade von Version 4.1.x auf Version 4.2 funktioniert die native PDF-Engine nicht und löst sogar für das unterstützte Betriebssystem eine NullPointerException aus.(11526)
* Der PDF-Download-Prozess funktioniert im Web-Editor nicht ordnungsgemäß. (11496)
* Native PDF | Entwurfskommentare sind in der generierten Ausgabe standardmäßig ausgeblendet. (10560)
* Native PDF | navtitle wird nicht für Topichead geehrt. (10509)
* Native PDF | Beim Hinzufügen von `xref` zu einem Bild wird das Bild auf der generierten PDF nicht gerendert. (11346)
* Die native Fußnote in PDF | in der Tabellenkopfzeile führt zu fett und zentriert ausgerichtetem Text in der entsprechenden Fußzeile in der PDF-Ausgabe. (10610)

### Übersetzung

* Beim Upgrade auf 4.2 werden alle Übersetzungsinhalte als nicht synchron oder als fehlende Kopie angezeigt. (11834)

### Überprüfung

* Abgeschlossene Überprüfung wird nicht im schreibgeschützten Modus geöffnet. (11387)
