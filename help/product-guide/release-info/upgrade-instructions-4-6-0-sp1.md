---
title: Versionshinweise | Upgrade-Anweisungen für Adobe Experience Manager Guides 4.6.0 Service Pack 1-Version
description: Erfahren Sie, wie Sie auf Version 4.6.0 Service Pack 1 von Adobe Experience Manager Guides aktualisieren.
role: Leader
source-git-commit: 2362870e0e3e6c08df03e8c547bb77de7faa0a02
workflow-type: tm+mt
source-wordcount: '529'
ht-degree: 1%

---

# Upgrade-Anweisungen für die Version 4.6.0 Service Pack 1 (Oktober 2024)

Dieser Artikel behandelt die Upgrade-Anweisungen und die Kompatibilitätsmatrix für Version 4.6.0 Service Pack 1 von Adobe Experience Manager Guides.

Eine Liste der in dieser Version behobenen Probleme finden Sie unter [Behobene Probleme in Version 4.6.0 Service Pack 1](fixed-issues-4-6-0-sp1.md).

## Kompatibilitätsmatrix

In diesem Abschnitt wird die Kompatibilitätsmatrix für die Softwareanwendungen aufgelistet, die von Experience Manager Guides 4.6.0 Service Pack 1 unterstützt werden.

### Adobe Experience Manager

**4.6.0 Service Pack 1 Non-UUID**
Version 6.5 Service Pack 21, 20 und 19

**4.6.0 Service Pack 1 UUID**
Version 6.5 Service Pack 21, 20 und 19

Weitere Informationen finden Sie im Abschnitt [Technische Anforderungen](../install-guide/download-install-technical-requirements.md) im On-Premise-Installations- und Konfigurationshandbuch.

### FrameMaker und FrameMaker Publishing Server

| Freigabe | FMPS 2022 | FMPS 2020 | FM 2022 | FM 2020 |
| --- | --- | --- | --- | --- |
| 4.6.0 Service Pack 1 (Nicht-UUID) | 2022 oder höher | 2020.2 oder höher* | 2022 oder höher | 2020.3 oder höher |
| 4.6.0 Service Pack 1 (UUID) | 2022 oder höher | 2020.2 oder höher* | 2022 oder höher | 2020.4 oder höher |
| | | | |

*Die in AEM erstellten Grundlinien und Bedingungen werden in FMPS-Versionen ab 2020.2 unterstützt.

### Sauerstoffanschluss

| Freigabe | Sauerstoff Connector Windows | Sauerstoff Connector Mac | In Oxygen Windows bearbeiten | In Oxygen Mac bearbeiten |
| --- | --- | --- |--- |--- |
| 4.6.0 Service Pack 1 (Nicht-UUID) | 2.8-normal-10 | 2.8-normal-10 | 1,6 | 1,6 |
| 4.6.0 Service Pack 1 (UUID) | 3.6-uuid.9 | 3.6-uuid.9 | 2,3 | 2,3 |
|  |  |   |

### Knowledgebase-Vorlagenversion

| Name des Komponentenpakets | Komponentenversion | Vorlagenversion |
|---|---|---|
| Experience Manager Guides Components Content Package for Cloud Service | dxml-components.all-1.2.2 | aem-site-template-dxml.all-1.0.15 |

### Neue AEM Site-Vorlagenversion

| Komponentenversion | Site-Version |
|---|---|
| guides-components.all-1.0.0 | aemg-docs.all-1.0.0 |

## Upgrade auf Version 4.6.0 Service Pack 1 von Experience Manager Guides

Sie können Ihre aktuelle Version von Guides einfach auf 4.6.0 Service Pack 1 aktualisieren. Bevor Sie mit der Aktualisierung fortfahren, müssen Sie die folgenden Punkte beachten:

- Wenn Sie Version 4.6.0 verwenden, können Sie direkt auf 4.6.0 Service Pack 1 aktualisieren.
- Wenn Sie Version 4.4, 4.3.1 oder 4.3.0 verwenden, müssen Sie auf Version 4.6.0 aktualisieren, bevor Sie auf Version 4.6.0 Service Pack 1 aktualisieren.
- Wenn Sie Version 4.2, 4.2.1 (Hotfix 4.2.1.3), 4.1 oder 4.1.x verwenden, müssen Sie auf Version 4.4 aktualisieren, bevor Sie auf Version 4.6.0 aktualisieren.
- Wenn Sie Version 4.0 verwenden, müssen Sie auf Version 4.2 aktualisieren, bevor Sie auf Version 4.3.x aktualisieren.
- Wenn Sie Version 3.8.5 verwenden, müssen Sie auf Version 4.0 aktualisieren, bevor Sie auf Version 4.2 aktualisieren.
- Wenn Sie eine Version vor 3.8.5 verwenden, lesen Sie den Abschnitt &quot;Aktualisieren von Experience Manager Guides&quot;im produktspezifischen Installationshandbuch, das im [Adobe Experience Manager Guides-PDF-Archiv](https://helpx.adobe.com/xml-documentation-for-experience-manager/archive.html) verfügbar ist.

>[!NOTE]
>
>Sie müssen AEM Service Pack installieren, bevor Sie die Experience Manager Guides-Version aktualisieren.

Der Aktualisierungsprozess für Version 4.6.0 Service Pack 1 folgt denselben Schritten wie für Version 4.6.0. Detaillierte Anweisungen finden Sie unter [Aktualisierungsanweisungen für die On-Premise-Versionen](../install-guide/upgrade-xml-documentation.md) von Experience Manager Guides.
