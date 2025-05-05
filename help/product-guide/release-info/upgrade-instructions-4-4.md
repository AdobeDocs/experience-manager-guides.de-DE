---
title: Versionshinweise zu | Aktualisierungsanweisungen für Adobe Experience Manager Guides Version 4.4.0
description: Erfahren Sie, wie Sie auf Version 4.4.0 von Adobe Experience Manager Guides aktualisieren
role: Leader
exl-id: 884178b6-7a72-471a-a6e3-238a543fb227
source-git-commit: 47c06dcc30b34780cbd26ded1ca400a5056a59ba
workflow-type: tm+mt
source-wordcount: '461'
ht-degree: 5%

---

# Aktualisierungsanweisungen für die Version 4.4.0 (Januar 2024)

Dieser Artikel enthält die Upgrade-Anweisungen und die Kompatibilitätsmatrix für Version 4.4.0 von Adobe Experience Manager Guides.

Weitere Informationen zu den neuen Funktionen und Verbesserungen finden Sie unter [Neue Funktionen in Version 4.4.0](../release-info/whats-new-4-4.md).

Eine Liste der in dieser Version behobenen Probleme finden Sie unter [Behobene Probleme in Version 4.4.0](../release-info/fixed-issues-4-4.md).




## Kompatibilitätsmatrix

In diesem Abschnitt wird die Kompatibilitätsmatrix für die von Experience Manager Guides Version 4.4.0 unterstützten Softwareanwendungen aufgeführt.

### Adobe Experience Manager

**4.4.0 non-UUID**
Version 6.5 Service Pack 20, 19, 18 oder 17

**4.4.0 UUID**
Version 6.5 Service Pack 20, 19, 18 oder 17


Weitere Informationen finden Sie im Abschnitt [Technische Anforderungen](../install-guide/download-install-technical-requirements.md) im On-Premise-Installations- und Konfigurationshandbuch.

### FrameMaker und FrameMaker Publishing Server

| Freigabe | FMPS 2022 | FMPS 2020 | FM 2022 | FM 2020 |
| --- | --- | --- | --- | --- |
| 4.4.0 (non-UUID) | 2022 oder höher | 2020.2 oder höher* | 2022 oder höher | 2020.3 oder höher |
| 4.4.0 (UUID) | 2022 oder höher | 2020.2 oder höher* | 2022 oder höher | 2020.4 oder höher |
| | | | |

*Die in AEM erstellten Grundlinien und Bedingungen werden ab 2020.2 in FMPS-Versionen unterstützt.

### Sauerstoffanschluss

| Freigabe | Fenster des Sauerstoffanschlusses | Oxygen Connector Mac | In Oxygen Windows bearbeiten | In Oxygen Mac bearbeiten |
| --- | --- | --- |--- |--- |
| 4.4.0 (non-UUID) | 2.7-normal-1 | 2.7-normal-1 | 1,6 | 1,6 |
| 4.4.0 (UUID) | 3.4-uuid-1 | 3.4-uuid-1 | 2,3 | 2,3 |
|  |  |   |



### Version der Wissensdatenbankvorlage

| Paketname der Komponenten | Komponentenversion | Vorlagenversion |
|---|---|---|
| Experience Manager Guides-Komponenten-Inhaltspaket für Cloud Service | dxml-components.all-1.2.2 | aem-site-template-dxml.all-1.0.15 |



## Upgrade auf Version 4.4.0 von Experience Manager Guides


Sie können Ihre aktuelle Version von Guides einfach auf Version 4.4.0 aktualisieren. Bevor Sie mit dem Upgrade auf Version 4.4.0 von Experience Manager Guides fortfahren, müssen Sie die folgenden Punkte berücksichtigen:


- Wenn Sie Version 4.3.1, 4.3.0 oder 4.2.1 (Hotfix 4.2.1.3) verwenden, können Sie direkt auf Version 4.4.0 aktualisieren.
- Wenn Sie Version 4.2, 4.1 oder 4.1.x verwenden, müssen Sie auf Version 4.3.1, 4.3.0 oder 4.2.1 (Hotfix 4.2.1.3) aktualisieren, bevor Sie auf Version 4.4.0 aktualisieren.
- Wenn Sie Version 4.0 verwenden, müssen Sie auf Version 4.2 aktualisieren, bevor Sie auf Version 4.3.x aktualisieren.
- Wenn Sie Version 3.8.5 verwenden, müssen Sie auf Version 4.0 aktualisieren, bevor Sie auf Version 4.2 aktualisieren.
- Wenn Sie eine Version vor 3.8.5 verwenden, lesen Sie den Abschnitt zum Upgrade von Experience Manager Guides im produktspezifischen Installationshandbuch, das im PDF-Archiv für die Adobe Experience Manager Guides-Hilfe [verfügbar ist](https://helpx.adobe.com/de/xml-documentation-for-experience-manager/archive.html).



>[!NOTE]
>
>Sie müssen das AEM Service Pack installieren, bevor Sie die Experience Manager Guides-Version aktualisieren.

Weitere Informationen finden Sie unter [Upgrade-Anweisungen für On-Premise](../install-guide/upgrade-xml-documentation.md) von Experience Manager Guides.
