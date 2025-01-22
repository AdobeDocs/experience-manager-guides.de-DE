---
title: Versionshinweise zu | Aktualisierungsanweisungen für Adobe Experience Manager Guides 4.6.0 Service Pack 3
description: Erfahren Sie, wie Sie auf Version 4.6.0 Service Pack 3 von Adobe Experience Manager Guides aktualisieren
role: Leader
source-git-commit: 8a24d2fd50b6b6ac93b5513e7a99953fdc1735b8
workflow-type: tm+mt
source-wordcount: '527'
ht-degree: 1%

---

# Aktualisierungsanweisungen für die Version 4.6.0 Service Pack 3 (Januar 2025)

Dieser Artikel enthält die Upgrade-Anweisungen und die Kompatibilitätsmatrix für Version 4.6.0 Service Pack 3 von Adobe Experience Manager Guides.

Eine Liste der in dieser Version behobenen Probleme finden Sie unter [Behobene Probleme in Version 4.6.0 Service Pack 3](fixed-issues-4-6-0-sp2.md).

## Kompatibilitätsmatrix

In diesem Abschnitt wird die Kompatibilitätsmatrix für die Softwareanwendungen aufgelistet, die von Experience Manager Guides 4.6.0 Service Pack 3 unterstützt werden.

### Adobe Experience Manager

**4.6.0 Service Pack 3 - Nicht-UUID**
Version 6.5 Service Pack 21, 20 und 19

**4.6.0 Service Pack 3 UUID**
Version 6.5 Service Pack 21, 20 und 19

Weitere Informationen finden Sie im Abschnitt [Technische Anforderungen](../install-guide/download-install-technical-requirements.md) im On-Premise-Installations- und Konfigurationshandbuch.

### FrameMaker und FrameMaker Publishing Server

| Freigabe | FMPS 2022 | FMPS 2020 | FM 2022 | FM 2020 |
| --- | --- | --- | --- | --- |
| 4.6.0 Service Pack 3 (nicht-UUID) | 2022 oder höher | 2020.2 oder höher* | 2022 oder höher | 2020.3 oder höher |
| 4.6.0 Service Pack 3 (UUID) | 2022 oder höher | 2020.2 oder höher* | 2022 oder höher | 2020.4 oder höher |
| | | | |

*Die in AEM erstellten Grundlinien und Bedingungen werden ab 2020.2 in FMPS-Versionen unterstützt.

### Sauerstoffanschluss

| Freigabe | Fenster des Sauerstoffanschlusses | Oxygen Connector Mac | In Oxygen Windows bearbeiten | In Oxygen Mac bearbeiten |
| --- | --- | --- |--- |--- |
| 4.6.0 Service Pack 3 (nicht-UUID) | 2.8-normal-10 | 2.8-normal-10 | 1,6 | 1,6 |
| 4.6.0 Service Pack 3 (UUID) | 3.6-uuid.9 | 3.6-uuid.9 | 2,3 | 2,3 |
|  |  |   |

### Version der Wissensdatenbankvorlage

| Paketname der Komponenten | Komponentenversion | Vorlagenversion |
|---|---|---|
| Experience Manager Guides-Komponenten-Inhaltspaket für Cloud Service | dxml-components.all-1.2.2 | aem-site-template-dxml.all-1.0.15 |

### Neue AEM-Site-Vorlagenversion

| Komponentenversion | Site-Version |
|---|---|
| guides-components.all-1.0.0 | aemg-docs.all-1.0.0 |

## Upgrade auf Version 4.6.0 Service Pack 3 von Experience Manager Guides

Sie können Ihre aktuelle Version von Guides einfach auf 4.6.0 Service Pack 3 aktualisieren. Bevor Sie mit dem Upgrade fortfahren, müssen Sie die folgenden Punkte berücksichtigen:

- Wenn Sie Version 4.6.0 oder 4.6.0 Service Pack 1 verwenden, können Sie direkt auf 4.6.0 Service Pack 3 aktualisieren.
- Wenn Sie Version 4.4, 4.3.1 oder 4.3.0 verwenden, müssen Sie auf Version 4.6.0 aktualisieren.
- Wenn Sie Version 4.2, 4.2.1 (Hotfix 4.2.1.3), 4.1 oder 4.1.x verwenden, müssen Sie auf Version 4.4 aktualisieren, bevor Sie auf Version 4.6.0 aktualisieren.
- Wenn Sie Version 4.0 verwenden, müssen Sie auf Version 4.2 aktualisieren, bevor Sie auf Version 4.3.x aktualisieren.
- Wenn Sie Version 3.8.5 verwenden, müssen Sie auf Version 4.0 aktualisieren, bevor Sie auf Version 4.2 aktualisieren.
- Wenn Sie eine Version vor 3.8.5 verwenden, lesen Sie den Abschnitt zum Upgrade von Experience Manager Guides im produktspezifischen Installationshandbuch, das im PDF-Archiv für die Adobe Experience Manager Guides-Hilfe [verfügbar ist](https://helpx.adobe.com/xml-documentation-for-experience-manager/archive.html).

>[!NOTE]
>
>Sie müssen das AEM Service Pack installieren, bevor Sie die Experience Manager Guides-Version aktualisieren.

Der Upgrade-Prozess für Version 4.6.0 Service Pack 3 folgt denselben Schritten wie für Version 4.6.0. Detaillierte Anweisungen finden Sie unter [Upgrade-Anweisungen für On-Premise-Versionen](../install-guide/upgrade-xml-documentation.md) von Experience Manager Guides.
