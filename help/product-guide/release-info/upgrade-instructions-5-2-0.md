---
title: Versionshinweise | Upgrade-Anweisungen für Adobe Experience Manager Guides Version 5.2.0
description: Erfahren Sie mehr über die Kompatibilitätsmatrix und das Upgrade auf Version 5.2.0 von Adobe Experience Manager Guides.
source-git-commit: 1dc529ba8913c30fba876f101c3b52474e8a71dd
workflow-type: tm+mt
source-wordcount: '859'
ht-degree: 4%

---

# Aktualisierungsanweisungen für die Version 5.2.0 (Mai 2026)

Dieser Artikel enthält die Upgrade-Anweisungen und die Kompatibilitätsmatrix für Version 5.2.0 von Adobe Experience Manager Guides.

Weitere Informationen zu den neuen Funktionen und Verbesserungen finden Sie unter [Neue Funktionen in Version 5.2.0](../release-info/whats-new-5-2-0.md).

Eine Liste der in dieser Version behobenen Probleme finden Sie unter [Behobene Probleme in Version 5.2.0](../release-info/fixed-issues-5-2-0.md).

## Kompatibilitätsmatrix

In diesem Abschnitt wird die Kompatibilitätsmatrix für die von Experience Manager Guides Version 5.2.0 unterstützten Softwareanwendungen aufgeführt.

| AEM Guides | AEM-Version | Service Pack |
| --- | --- | --- |
| 5.2.0 (UUID) | 6.5 LTS | 2 |
| 5.2.0 (UUID) | 6.5 | 24, 23, 22 |

Weitere Informationen finden Sie im Abschnitt [Technische Anforderungen](../install-guide/download-install-technical-requirements.md) im On-Premise-Installations- und Konfigurationshandbuch.

### FrameMaker und FrameMaker Publishing Server

| Freigabe | FMPS | FM |
| --- | --- | --- |
| 5.2.0 (UUID) | Unterstützt | 2026 oder höher |

### Sauerstoffanschluss

| Freigabe | Fenster des Sauerstoffanschlusses | Oxygen Connector Mac | In Oxygen Windows bearbeiten | In Oxygen Mac bearbeiten |
| --- | --- | --- |--- |--- |
| 5.2.0 (UUID) | 3.8-uuid.1 | 3.8-uuid.1 | 2,3 | 2,3 |

### Version der Wissensdatenbankvorlage

| Paketname der Komponenten | Komponentenversion | Vorlagenversion |
|---|---|---|
| Experience Manager Guides-Komponenten-Inhaltspaket für Cloud Service | guides-components.all-1.4.0 | aem-site-template-dxml-1.0.17 |

### Neue AEM Site-Vorlagenversion


| AEM Guides | AEM-Version | Komponentenversion | Site-Version |
|---|---|---| ---|
| 5.2.0 UUID | 6.5 LTS | guides-components.all-1.4.1 | nicht vorhanden |
| 5.2.0 UUID | 6.5 | guides-components.all-1.4.0 | aemg-sites-template-1.3.0 |

## Voraussetzungen

Stellen Sie vor dem Start des Upgrades auf Experience Manager Guides 5.2.0 Folgendes sicher:

1. Auf Experience Manager Guides Version 5.0.0, 5.0.3, 5.1.0, 5.1.3 oder 5.1.4 aktualisiert.
1. (Optional) Alle Übersetzungsaufgaben wurden geschlossen.
1. Protokollebene für `com.adobe.fmdita.translationservices.TranslationMapUpgradeScript` Klasse in &quot;**&quot;** und diese Protokolle in einer neuen Protokolldatei anhängen, z. B. `logs/translation_upgrade.log`.

## Aktualisierungspfad für Experience Manager Guides 5.2.0

Sie können Ihre aktuelle Version von Experience Manager Guides einfach auf Version 5.2.0 auf **AEM 6.5** oder **AEM 6.5 LTS** aktualisieren.

>[!IMPORTANT]
>
> - **Für AEM 6.5 LTS**: Experience Manager Guides 5.2.0 wird nur mit AEM 6.5 LTS Service Pack 2 unterstützt.
> - **Für AEM 6.5**: Experience Manager Guides 5.2.0 wird nur mit AEM 6.5 Service Pack 24, 23 und 22 unterstützt.
> - Wenn Sie derzeit AEM 6.5 verwenden und planen, auf AEM 6.5 LTS zu wechseln, stellen Sie sicher, dass Sie zuerst das AEM-Upgrade abschließen, bevor Sie mit dem Experience Manager Guides 5.2.0-Upgrade fortfahren. Weitere Informationen finden Sie unter [Upgrade auf Adobe Experience Manager (AEM) 6.5 LTS](https://experienceleague.adobe.com/en/docs/experience-manager-65-lts/content/implementing/deploying/upgrading/upgrade).

Bevor Sie mit dem Upgrade auf Version 5.2.0 von Experience Manager Guides fortfahren, müssen Sie die folgenden Punkte berücksichtigen:

- Wenn Sie Version 5.0.0, 5.0.3, 5.1.0, 5.1.3 oder 5.1.4 verwenden, können Sie direkt auf Version 5.2.0 aktualisieren.
- Wenn Sie Version 4.6.3, 4.6.4, 5.0.x verwenden, können Sie direkt auf Version 5.1.0 aktualisieren.
- Wenn Sie Version 4.6.0, 4.6.1 verwenden, müssen Sie auf Version 4.6.3 oder 4.6.4 oder 5.0.0 aktualisieren, bevor Sie auf Version 5.1.0 aktualisieren.
- Wenn Sie Version 4.3.x, 4.2, 4.2.1 (Hotfix 4.2.1.3), 4.1 oder 4.1.x verwenden, müssen Sie vor dem Upgrade auf Version 5.1.0 ein Upgrade auf Version 4.4 durchführen.
- Wenn Sie Version 4.0 verwenden, müssen Sie auf Version 4.2 aktualisieren, bevor Sie auf Version 4.3.x aktualisieren.
- Wenn Sie Version 3.8.5 verwenden, müssen Sie auf Version 4.0 aktualisieren, bevor Sie auf Version 4.2 aktualisieren.
- Wenn Sie eine Version vor 3.8.5 verwenden, lesen Sie den Abschnitt zum Upgrade von Experience Manager Guides im produktspezifischen Installationshandbuch, das auf der [Adobe Experience Manager Guides-Hilfe für PDF Archive](https://helpx.adobe.com/xml-documentation-for-experience-manager/archive.html) verfügbar ist.

## Upgrade-Prozess für Experience Manager Guides 5.2.0

>[!IMPORTANT]
>
> Die Nachbearbeitung und Indizierung kann einige Stunden dauern. Es wird empfohlen, den Upgrade-Prozess außerhalb der Spitzenzeiten zu starten.

1. Laden Sie das Versionspaket 5.2.0 vom [Adobe Software Distribution Portal](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html) herunter.
1. Installieren Sie das Versionspaket, auf dem Sie das Upgrade durchführen möchten, und warten Sie, bis das Paket installiert ist.
1. *(Optional)* Upgrade des Oxygen Connector-Plug-ins, das mit der Version veröffentlicht wurde, auf die Sie ein Upgrade durchführen.
1. Löschen Sie den Browser-Cache nach der Installation des Pakets.
1. Wenn Sie die Einstellung `Enable markup find and replace` für den Zugriff auf die Funktion zum Suchen und Ersetzen in der Quellansicht für zuvor erfasste Inhalte aktiviert haben, müssen Sie den `guidesAssetLucene` neu indizieren. Weitere Informationen finden Sie unter [Neuindizierung für Suchen und Ersetzen](../install-conf-guide/custom-indexing-on-prem.md).
1. Aktualisieren Sie die Systemkonfiguration, um die neuen Einstellungen einzubinden, die in Version 5.2.0 eingeführt wurden, und stellen Sie sicher, dass die folgenden Verbesserungen unterstützt werden:


| Konfigurationen hinzugefügt | Konfigurationsdatei | Titel der Einstellung anzeigen | Name der Einstellung |
|-----|-----|------|-----|
| Aktivieren oder Deaktivieren des neuen Editors | `com.adobe.fmdita.config.ConfigManager` | Editor 2.0 aktivieren | `enable.markup.editor` |
| Aktivieren oder Deaktivieren der neuen Baseline | `com.adobe.fmdita.config.ConfigManager` | Schnellere Baseline aktivieren (v2) | `enable.baseline.v2` |
| Metadateneigenschaften ignorieren, um eine Version als verändert zu markieren | `com.adobe.fmdita.xmleditor.config.XmlEditorConfig` | Metadateneigenschaft für unsaubere Version ignorieren | `xmleditor.dirtychecker.ignoremetadata` |
| Funktion zum Suchen und Ersetzen in der Source-Ansicht | `com.adobe.fmdita.config.ConfigManager` | Markup zum Suchen und Ersetzen aktivieren | `enable.markup.findreplace` |
| Aktivieren oder Deaktivieren des Überspringens von Peer-Links für alte Baseline | `com.adobe.fmdita.config.ConfigManager` | Peer-Links für Baseline V1 überspringen | `guides.baseline.v1.skip.peer.links` |
| Aktivieren oder deaktivieren Sie die Initialisierung von Zielkopien mit Quellinhalten im Übersetzungs-Workflow. Dies gilt nur, wenn der alte Übersetzungs-Workflow deaktiviert ist.  | `com.adobe.fmdita.config.ConfigManager` | Initialisieren der Zielsprachkopie mit Quellinhalten | `translation.workflow.propagate.source.content` |
| Bereinigung des Referenzspeichers | `com.adobe.fmdita.config.ConfigManager` | Handbücher zum Löschen aktiviert | `btree.deletion.enabled` |
| Replikation von DITA-Assets | `com.adobe.fmdita.config.ConfigManager` | Replizieren von DITA-Assets | `publish.replicate` |
| Asset-Verarbeitung | `com.adobe.fmdita.config.ConfigManager` | Handbücher zur Asset-Verarbeitung für geplanten Auftrag aktivieren | `enable.asset.processing.scheduler` |

Ausführliche Informationen zu diesen Konfigurationseinstellungen finden Sie unter [Konfigurationsaktualisierungen](../install-conf-guide/configuration-on-prem.md).







