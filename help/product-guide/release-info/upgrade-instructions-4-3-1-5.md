---
title: Versionshinweise | Upgrade-Anweisungen für Adobe Experience Manager Guides 4.3.1.5 Version
description: Erfahren Sie, wie Sie auf 4.3.1.5 Version von Adobe Experience Manager Guides aktualisieren
role: Leader
exl-id: 856970ef-9f50-4452-b589-ba1f5ee73322
TQID: https://experienceleague.adobe.com/wN9EyxDaR5dSTnaUQIqKV-8jhbw2LUj36vpeUd8Obc4
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2:
  - id: a3bd6397-2eb2-4908-a61c-226e26855dca
  - id: afb45297-4313-4f67-818e-bc0b03abe086
  - id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
subfeature_v2:
  - id: d5ea0417-7932-4688-a3e2-4d3b2e7076a3
role_v2:
  - id: f8a45b24-4be7-4f1b-909b-60d06b483a20
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 434
ht-degree: 2%

---

# Aktualisierungsanweisungen für die 4.3.1.5 Version

Dieser Artikel enthält die Upgrade-Anweisungen und die Kompatibilitätsmatrix für 4.3.1.5 Version von Adobe Experience Manager Guides.


Eine Liste der in dieser Version behobenen Probleme finden Sie unter [Behobene Probleme in der 4.3.1.5 Version](../release-info/fixed-issues-4-3-1-5.md).




## Kompatibilitätsmatrix

In diesem Abschnitt finden Sie die Kompatibilitätsmatrix für die von Experience Manager Guides 4.3.1.5 unterstützten Softwareanwendungen.

### Adobe Experience Manager

Nicht-UUID **4.3.1.5**
Version 6.5 Service Pack 18, 17, 16, 15, 14

**4.3.1.5UUID**
Version 6.5 Service Pack 18, 17, 16, 15, 14

Weitere Informationen finden Sie im Abschnitt *Technische Anforderungen* im On-Premise-Installations- und Konfigurationshandbuch .

### FrameMaker und FrameMaker Publishing Server

| Freigabe | FMPS 2022 | FMPS 2020 | FM 2022 | FM 2020 |
| --- | --- | --- | --- | --- |
| 4.3.1.5 (NICHT-UUID) | 2022 oder höher | 2020.2 oder höher* | 2022 oder höher | 2020.3 oder höher |
| 4.3.1.5 (UUID) | 2022 oder höher | 2020.2 oder höher* | 2022 oder höher | 2020.4 oder höher |
| | | | | |

*Die in AEM erstellten Grundlinien und Bedingungen werden ab 2020.2 in FMPS-Versionen unterstützt.

### Sauerstoffanschluss

| Freigabe | Fenster des Sauerstoffanschlusses | Oxygen Connector Mac | In Oxygen Windows bearbeiten | In Oxygen Mac bearbeiten |
| --- | --- | --- |--- |--- |
| 4.3.1.5 (NICHT-UUID) | 2.3-normal-5 | 2.3-normal-5 | 1,6 | 1,6 |
| 4.3.1.5 (UUID) | 3.2-uuid-5 | 3.2-uuid-5 | 2,3 | 2,3 |
|  |  |   | | |



### Version der Wissensdatenbankvorlage

| Paketname der Komponenten | Komponentenversion | Vorlagenversion |
|---|---|---|
| Experience Manager Guides-Komponenten-Inhaltspaket für Cloud Service | dxml-components.all-1.2.2 | aem-site-template-dxml.all-1.0.15 |



## Upgrade auf 4.3.1.5 Version von Experience Manager Guides


Sie können Ihre aktuelle Version von Guides einfach auf Version 4.3.1.5 aktualisieren. Bevor Sie mit dem Upgrade auf Version 4.3.1.5 von Experience Manager Guides fortfahren, müssen Sie die folgenden Punkte berücksichtigen:


- Wenn Sie Version 4.3.1 oder 4.3.1.x verwenden, können Sie direkt auf Version 4.3.1.5 aktualisieren.
- Wenn Sie Version 4.3.0 oder 4.2 (Hotfix 4.2.1.3) verwenden, müssen Sie auf Version 4.3.1 aktualisieren, bevor Sie auf Version 4.3.1.5 aktualisieren.

- Wenn Sie Version 4.1 oder 4.1.x verwenden, müssen Sie auf Version 4.3.1 aktualisieren, bevor Sie auf Version 4.3.1.5 aktualisieren.


- Wenn Sie Version 4.0 verwenden, müssen Sie auf Version 4.2 aktualisieren, bevor Sie auf Version 4.3.x aktualisieren.
- Wenn Sie Version 3.8.5 verwenden, müssen Sie auf Version 4.0 aktualisieren, bevor Sie auf Version 4.2 aktualisieren.
- Wenn Sie eine Version vor 3.8.5 verwenden, lesen Sie den Abschnitt zum Upgrade von Experience Manager Guides im produktspezifischen Installationshandbuch, das auf der [Adobe Experience Manager Guides-Hilfe für PDF Archive](https://helpx.adobe.com/de/xml-documentation-for-experience-manager/archive.html) verfügbar ist.



>[!NOTE]
>
>Sie müssen das AEM Service Pack installieren, bevor Sie die Experience Manager Guides-Version aktualisieren.

Weitere Informationen finden Sie unter [Upgrade-Anweisungen für On-Premise](../install-guide/upgrade-xml-documentation.md) von Experience Manager Guides.
