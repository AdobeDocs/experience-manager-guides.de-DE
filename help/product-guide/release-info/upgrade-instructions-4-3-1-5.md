---
title: Versionshinweise | Upgrade-Anweisungen für Adobe Experience Manager Guides Version 4.3.1.5
description: Erfahren Sie, wie Sie auf die Adobe Experience Manager Guides-Version 4.3.1.5 aktualisieren.
role: Leader
exl-id: 856970ef-9f50-4452-b589-ba1f5ee73322
source-git-commit: e40ebf4122decc431d0abb2cdf1794ea704e5496
workflow-type: tm+mt
source-wordcount: '437'
ht-degree: 2%

---

# Upgrade-Anweisungen für Version 4.3.1.5

In diesem Artikel werden die Upgrade-Anweisungen und die Kompatibilitätsmatrix für Version 4.3.1.5 von Adobe Experience Manager Guides beschrieben.


Sehen Sie für die Liste der in dieser Version behobenen Probleme [Behobene Probleme in Version 4.3.1.5](../release-info/fixed-issues-4-3-1-5.md).




## Kompatibilitätsmatrix

In diesem Abschnitt wird die Kompatibilitätsmatrix für die von Experience Manager Guides 4.3.1.5 unterstützten Softwareanwendungen aufgeführt.

### Adobe Experience Manager

**4.3.1.5 Nicht-UUID**
Version 6.5 Service Pack 18, 17, 16, 15, 14

**4.3.1.5 UUID**
Version 6.5 Service Pack 18, 17, 16, 15, 14

Weitere Informationen finden Sie im Abschnitt *Technische Anforderungen* im On-Premise-Installations- und Konfigurationshandbuch .

### FrameMaker und FrameMaker Publishing Server

| Freigabe | FMPS 2022 | FMPS 2020 | FM 2022 | FM 2020 |
| --- | --- | --- | --- | --- |
| 4.3.1.5 (Nicht-UUID) | 2022 oder höher | 2020.2 oder höher* | 2022 oder höher | 2020.3 oder höher |
| 4.3.1.5 (UUID) | 2022 oder höher | 2020.2 oder höher* | 2022 oder höher | 2020.4 oder höher |
| | | | |

*Die in AEM erstellten Grundlinien und Bedingungen werden in FMPS-Versionen ab 2020.2 unterstützt.

### Sauerstoffanschluss

| Freigabe | Sauerstoff Connector Windows | Sauerstoff Connector Mac | In Oxygen Windows bearbeiten | In Oxygen Mac bearbeiten |
| --- | --- | --- |--- |--- |
| 4.3.1.5 (Nicht-UUID) | 2.3-normal-5 | 2.3-normal-5 | 1,6 | 1,6 |
| 4.3.1.5 (UUID) | 3.2-uuid-5 | 3.2-uuid-5 | 2,3 | 2,3 |
|  |  |   |



### Knowledgebase-Vorlagenversion

| Name des Komponentenpakets | Komponentenversion | Vorlagenversion |
|---|---|---|
| Experience Manager Guides Components Content Package for Cloud Service | dxml-components.all-1.2.2 | aem-site-template-dxml.all-1.0.15 |



## Aktualisierung auf Version 4.3.1.5 von Experience Manager Guides


Sie können Ihre aktuelle Version von Guides einfach auf Version 4.3.1.5 aktualisieren. Bevor Sie mit der Aktualisierung auf Version 4.3.1.5 von Experience Manager Guides fortfahren, müssen Sie die folgenden Punkte beachten:


- Wenn Sie Version 4.3.1 oder 4.3.1.x verwenden, können Sie direkt auf Version 4.3.1.5 aktualisieren.
- Wenn Sie Version 4.3.0 oder 4.2 (Hotfix 4.2.1.3) verwenden, müssen Sie vor der Aktualisierung auf Version 4.3.1 auf Version 4.3.1 aktualisieren.

- Wenn Sie Version 4.1 oder 4.1.x verwenden, müssen Sie vor der Aktualisierung auf Version 4.3.1 auf Version 4.3.1 aktualisieren.


- Wenn Sie Version 4.0 verwenden, müssen Sie auf Version 4.2 aktualisieren, bevor Sie auf Version 4.3.x aktualisieren.
- Wenn Sie Version 3.8.5 verwenden, müssen Sie auf Version 4.0 aktualisieren, bevor Sie auf Version 4.2 aktualisieren.
- Wenn Sie eine Version vor 3.8.5 verwenden, lesen Sie den Abschnitt &quot;Aktualisieren von Experience Manager Guides&quot;im produktspezifischen Installationshandbuch, das im [Adobe Experience Manager Guides-PDF-Archiv](https://helpx.adobe.com/xml-documentation-for-experience-manager/archive.html) verfügbar ist.



>[!NOTE]
>
>Sie müssen AEM Service Pack installieren, bevor Sie die Experience Manager Guides-Version aktualisieren.

Weitere Informationen finden Sie unter [Upgrade-Anweisungen für die On-Premise-Versionen](../install-guide/upgrade-xml-documentation.md) von Experience Manager Guides.
