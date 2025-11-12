---
title: Versionshinweise zu | Neue Funktionen in Adobe Experience Manager Guides Version 2025.11.0
description: Erfahren Sie mehr über die neuen und erweiterten Funktionen der Version 2025.11.0 von Adobe Experience Manager Guides
role: Leader
source-git-commit: a13fdb36efb5cfb548f8e128977469763836537a
workflow-type: tm+mt
source-wordcount: '510'
ht-degree: 3%

---

# Neue Funktionen in der Version 2025.11.0 (November 2025)

Dieser Artikel behandelt die neuen und erweiterten Funktionen, die mit der Version 2025.11.0 von Adobe Experience Manager Guides as a Cloud Service eingeführt wurden.

Eine Liste der in dieser Version behobenen Probleme finden Sie im Artikel [Behobene Probleme in Version 2025.11.0](fixed-issues-2025-11-0.md).

Erfahren Sie mehr [Upgrade-Anweisungen für die Version 2025.11.0](../release-info/upgrade-instructions-2025-11-0.md).


## Einführung des neuen Repositorys auf der Startseite und verbessertes Sucherlebnis

Das Repository, auf das jetzt direkt über die Startseite zugegriffen werden kann, dient als zentralisierter Bereich für eine verbesserte Auffindbarkeit von Ordnern und Dateien. Es bietet einen speziellen **Ordner-Navigationsbereich** und eine anpassbare **Tabellenansicht des Repositorys**. Das überarbeitete Such- und Filtererlebnis erleichtert das Suchen und Auffinden von Dateien erheblich. Weitere Informationen finden Sie unter [Kennenlernen der Repository-Oberfläche](../user-guide/home-page-repository-view.md).

![](assets/repository-view-home.png){align="left"}

Im -Editor ist das Erlebnis Suchen und Filtern nach Dateien jetzt mit der Startseite konsistent. Ein neues [Suchfeld](../user-guide/search-panel-explorer.md), das sich unten in der Editor-Benutzeroberfläche befindet, wird eingeführt, um Suchergebnisse anzuzeigen. Darüber hinaus wird das Repository jetzt im Editor in **Explorer** umbenannt, sodass Sie Ordner und Dateien wie zuvor durchsuchen können.

![](assets/search-panel-explorer.png){align="left"}


## Verbesserte Indizierung für Smart-Vorschläge im KI-Assistenten

Sie können jetzt den Status jedes Indizierungsversuchs für Smart-Vorschläge im KI-Assistenten mit neuen Statusindikatoren einfach verfolgen: Indizierung abgeschlossen, Nicht synchronisiert, In Bearbeitung und Indizierung fehlgeschlagen. Der letzte Zeitstempel der Indizierung wird jetzt auf Ordnerprofilebene aufgezeichnet, um die Rückverfolgbarkeit zu verbessern. Darüber hinaus werden Beschränkungen für übergeordnete und untergeordnete Ordner erzwungen, wenn ein Ordner oder ein Dateipfad für die Indizierung angegeben wird.

Weitere Informationen finden Sie unter [Konfigurieren des KI-Assistenten für intelligente Hilfe und Authoring](../cs-install-guide/conf-folder-level.md#configure-ai-assistant-for-smart-help-and-authoring).

## Leistungsverbesserungen

### Automatisierte B-Tree-Bereinigung für optimale Leistung

Um die Systemeffizienz zu erhalten und Ressourcenengpässe zu vermeiden, werden die B-Bäume auf Systemebene regelmäßig durch einen neuen Hintergrundprozess bereinigt. Dadurch wird sichergestellt, dass Assets, die nicht mehr vorhanden sind oder vorübergehend hinzugefügt wurden, keinen unnötigen Speicherplatz belegen.

Das System erkennt auf intelligente Weise die Bereinigungskandidaten und führt eine automatisierte Entfernung durch. Darüber hinaus ist diese Funktion konfigurierbar, sodass Administratoren das Verhalten auf der Grundlage betrieblicher Anforderungen steuern können.

Weitere Informationen finden Sie unter [Konfigurieren der B-Baumbereinigung](../cs-install-guide/configure-btree-cleanup-cs.md).

### Verbesserte Handhabung von DITA-Maps mit einer großen Anzahl von Schlüsseln

Sie können jetzt nahtlos mit DITA-Karten arbeiten, die eine große Anzahl von Schlüsseln enthalten. Diese Verbesserung sorgt für schnelleres Laden und verbesserte Leistung und erleichtert so die Verwaltung komplexer Karten ohne Unterbrechungen.

Nach dem Build-Upgrade kann es zu einem temporären Anstieg der Auslastung des Systems kommen, was zu einer Verzögerung bei der Nachbearbeitung neu hochgeladener Daten führt. Dies liegt an einem automatisierten Einmalskript (OTS), das im Hintergrund ausgeführt wird. Sobald das Skript abgeschlossen ist, wird die Systemleistung wieder normal.

### Verbesserte Asset-Verarbeitung

Es wird ein automatisierter Prozess eingeführt, um Assets im `/content/dam` auf dem neuesten Stand zu halten. Alle 15 Minuten erfolgt eine erneute Verarbeitung des Asset-Trigger durch das System. In jedem Zyklus werden Assets aufgenommen, die innerhalb des letzten 15-Minuten-Intervalls neu hinzugefügt wurden oder unverarbeitet blieben, und erneut verarbeitet. Dies verbessert die Effizienz und Konsistenz in Ihrem gesamten Content-Repository.

Weitere Informationen finden Sie unter [Assets verarbeiten](../user-guide/asset-processor.md).




