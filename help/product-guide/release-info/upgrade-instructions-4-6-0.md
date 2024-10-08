---
title: Versionshinweise | Upgrade-Anweisungen für Adobe Experience Manager Guides Version 4.6.0
description: Erfahren Sie, wie Sie auf die Adobe Experience Manager Guides-Version 4.6.0 aktualisieren.
role: Leader
source-git-commit: 1880d889dc9063ef05c4f856d6082d1ea03b7946
workflow-type: tm+mt
source-wordcount: '465'
ht-degree: 5%

---

# Upgrade-Anweisungen für Version 4.6.0 (September 2024)

In diesem Artikel werden die Upgrade-Anweisungen und die Kompatibilitätsmatrix für Version 4.6.0 von Adobe Experience Manager Guides beschrieben.

Weitere Informationen zu den neuen Funktionen und Verbesserungen finden Sie unter [Neue Funktionen in Version 4.6.0](../release-info/whats-new-4-6.md).

Eine Liste der in dieser Version behobenen Probleme finden Sie unter [Behobene Probleme in Version 4.6.0](../release-info/fixed-issues-4-6-0.md).

## Kompatibilitätsmatrix

In diesem Abschnitt wird die Kompatibilitätsmatrix für die von Experience Manager Guides 4.6.0 unterstützten Softwareanwendungen aufgeführt.

### Adobe Experience Manager

**4.6.0 Nicht-UUID**
Version 6.5 Service Pack 21, 20 und 19

**4.6.0 UUID**
Version 6.5 Service Pack 21, 20 und 19

Weitere Informationen finden Sie im Abschnitt [Technische Anforderungen](../install-guide/download-install-technical-requirements.md) im On-Premise-Installations- und Konfigurationshandbuch.

### FrameMaker und FrameMaker Publishing Server

| Freigabe | FMPS 2022 | FMPS 2020 | FM 2022 | FM 2020 |
| --- | --- | --- | --- | --- |
| 4.6.0 (Nicht-UUID) | 2022 oder höher | 2020.2 oder höher* | 2022 oder höher | 2020.3 oder höher |
| 4.6.0 (UUID) | 2022 oder höher | 2020.2 oder höher* | 2022 oder höher | 2020.4 oder höher |
| | | | |

*Die in AEM erstellten Grundlinien und Bedingungen werden in FMPS-Versionen ab 2020.2 unterstützt.

### Sauerstoffanschluss

| Freigabe | Sauerstoff Connector Windows | Sauerstoff Connector Mac | In Oxygen Windows bearbeiten | In Oxygen Mac bearbeiten |
| --- | --- | --- |--- |--- |
| 4.6.0 (Nicht-UUID) | 2.8-normal-10 | 2.8-normal-10 | 1,6 | 1,6 |
| 4.6.0 (UUID) | 3.6-uuid.9 | 3.6-uuid.9 | 2,3 | 2,3 |
|  |  |   |

### Knowledgebase-Vorlagenversion

| Name des Komponentenpakets | Komponentenversion | Vorlagenversion |
|---|---|---|
| Experience Manager Guides Components Content Package for Cloud Service | dxml-components.all-1.2.2 | aem-site-template-dxml.all-1.0.15 |

### Neue AEM Site-Vorlagenversion


| Komponentenversion | Site-Version |
|---|---|
| guides-components.all-1.0.0 | aemg-docs.all-1.0.0 |

## Aktualisierung auf Version 4.6.0 von Experience Manager Guides

Sie können Ihre aktuelle Version von Guides einfach auf Version 4.6.0 aktualisieren. Bevor Sie mit der Aktualisierung auf Version 4.6.0 von Experience Manager Guides fortfahren, müssen Sie die folgenden Punkte beachten:

- Wenn Sie Version 4.4, 4.3.1 oder 4.3.0 verwenden, können Sie direkt auf Version 4.6.0 aktualisieren.
- Wenn Sie Version 4.2, 4.2.1 (Hotfix 4.2.1.3), 4.1 oder 4.1.x verwenden, müssen Sie auf Version 4.4 aktualisieren, bevor Sie auf Version 4.6.0 aktualisieren.
- Wenn Sie Version 4.0 verwenden, müssen Sie auf Version 4.2 aktualisieren, bevor Sie auf Version 4.3.x aktualisieren.
- Wenn Sie Version 3.8.5 verwenden, müssen Sie auf Version 4.0 aktualisieren, bevor Sie auf Version 4.2 aktualisieren.
- Wenn Sie eine Version vor 3.8.5 verwenden, lesen Sie den Abschnitt &quot;Aktualisieren von Experience Manager Guides&quot;im produktspezifischen Installationshandbuch, das im [Adobe Experience Manager Guides-PDF-Archiv](https://helpx.adobe.com/xml-documentation-for-experience-manager/archive.html) verfügbar ist.

>[!NOTE]
>
>Sie müssen AEM Service Pack installieren, bevor Sie die Experience Manager Guides-Version aktualisieren.

Weitere Informationen finden Sie unter [Upgrade-Anweisungen für die On-Premise-Versionen](../install-guide/upgrade-xml-documentation.md) von Experience Manager Guides.
