---
title: Versionshinweise | Upgrade-Anweisungen für Adobe Experience Manager Guides 5.1.0 Service Pack 3
description: Erfahren Sie mehr über die Kompatibilitätsmatrix und das Upgrade auf Version 5.1.0 Service Pack 3 von Adobe Experience Manager Guides.
exl-id: 2452da05-36f2-4df3-aee9-918072a67d9c
TQID: https://experienceleague.adobe.com/qFrmvlpp7uxkLs2KXq3ItTVD6LxteJkMUuKdtmN9JY4
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
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 595
ht-degree: 4%

---

# Aktualisierungsanweisungen für die Version 5.1.0 Service Pack 3 (Dezember 2025)

Dieser Artikel enthält die Upgrade-Anweisungen und die Kompatibilitätsmatrix für Version 5.1.0 Service Pack 3 von Adobe Experience Manager Guides.

Eine Liste der in dieser Version behobenen Probleme finden Sie unter [Behobene Probleme in Version 5.1.0 Service Pack 3](../release-info/fixed-issues-5-1-0-sp3.md).

## Kompatibilitätsmatrix

In diesem Abschnitt wird die Kompatibilitätsmatrix für die Softwareanwendungen aufgelistet, die von Experience Manager Guides 5.1.0 Service Pack 3 unterstützt werden.

| AEM Guides | AEM-Version | Service Pack |
| --- | --- | --- |
| 5.1.0 Service Pack 3 (UUID) | 6.5 LTS | 1 |
| 5.1.0 Service Pack 3 (UUID) | 6.5 | 23, 22, 21 |

Weitere Informationen finden Sie im Abschnitt [Technische Anforderungen](../install-guide/download-install-technical-requirements.md) im On-Premise-Installations- und Konfigurationshandbuch.

### FrameMaker und FrameMaker Publishing Server

| Freigabe | FMPS | FM |
| --- | --- | --- |
| 5.1.0 Service Pack 3 (UUID) | Unterstützt | 2022 oder höher |

### Sauerstoffanschluss

| Freigabe | Fenster des Sauerstoffanschlusses | Oxygen Connector Mac | In Oxygen Windows bearbeiten | In Oxygen Mac bearbeiten |
| --- | --- | --- |--- |--- |
| 5.1.0 Service Pack 3 (UUID) | 3.8-uuid.1 | 3.8-uuid.1 | 2,3 | 2,3 |

### Version der Wissensdatenbankvorlage

| Paketname der Komponenten | Komponentenversion | Vorlagenversion |
|---|---|---|
| Experience Manager Guides-Komponenten-Inhaltspaket für Cloud Service | dxml-components.all-1.3.0 | aem-site-template-dxml.all-1.0.4 |

### Neue AEM Site-Vorlagenversion

| AEM Guides | AEM-Version | Komponentenversion | Site-Version |
|---|---|---| ---|
| 5.1.0 Service Pack 3 UUID | 6.5 LTS | guides-components.all-1.4.1 | aemg-docs.all-1.2.0 |
| 5.1.0 Service Pack 3 UUID | 6.5 | guides-components.all-1.4.0 | aemg-docs.all-1.2.0 |


## Voraussetzungen

Gemäß dem standardmäßigen DITA-Verhalten darf das Attribut scope=`external` nicht auf interne Links angewendet werden, da es nur für Verweise auf externe Ressourcen vorgesehen ist. Die Anwendung dieses Attributs auf interne Links kann Workflows stören. Verwenden Sie für in Experience Manager Guides verwaltete Inhalte stattdessen den Standardbereich `local` oder schlüsselbasierte Verweise.

## Upgrade auf Version 5.1.0 Service Pack 3 von Experience Manager Guides

Sie können Ihre aktuelle Version von Experience Manager Guides einfach auf Version 5.1.0 Service Pack 3 auf **AEM 6.5** oder **AEM 6.5 LTS** aktualisieren.

>[!NOTE]
>
> Wenn Sie derzeit AEM 6.5 verwenden und planen, zu AEM 6.5 LTS zu wechseln, lesen Sie [Upgrade auf Adobe Experience Manager (AEM) 6.5 LTS](https://experienceleague.adobe.com/en/docs/experience-manager-65-lts/content/implementing/deploying/upgrading/upgrade).

Bevor Sie mit dem Upgrade auf Version 5.1.0 Service Pack 3 von Experience Manager Guides fortfahren, müssen Sie die folgenden Punkte berücksichtigen:

- Wenn Sie Version 5.1.0 oder 5.1.x verwenden, können Sie direkt auf Version 5.1.0 Service Pack 3 aktualisieren.
- Wenn Sie Version 4.6.0, 4.6.x, 5.0.0 oder 5.0.x verwenden, müssen Sie auf Version 5.1.0 aktualisieren.
- Wenn Sie Version 4.6.3, 4.6.1, 4.6 oder 4.4 verwenden, müssen Sie auf Version 5.0.0 aktualisieren.
- Wenn Sie Version 4.3.x, 4.2, 4.2.1 (Hotfix 4.2.1.3), 4.1 oder 4.1.x verwenden, müssen Sie vor dem Upgrade auf Version 5.0.0 ein Upgrade auf Version 4.4 durchführen.
- Wenn Sie Version 4.0 verwenden, müssen Sie auf Version 4.2 aktualisieren, bevor Sie auf Version 4.3.x aktualisieren.
- Wenn Sie Version 3.8.5 verwenden, müssen Sie auf Version 4.0 aktualisieren, bevor Sie auf Version 4.2 aktualisieren.
- Wenn Sie eine Version vor 3.8.5 verwenden, lesen Sie den Abschnitt zum Upgrade von Experience Manager Guides im produktspezifischen Installationshandbuch, das auf der [Adobe Experience Manager Guides-Hilfe für PDF Archive](https://helpx.adobe.com/xml-documentation-for-experience-manager/archive.html) verfügbar ist.

>[!NOTE]
>
> Sie müssen das AEM Service Pack installieren, bevor Sie die Experience Manager Guides-Version aktualisieren.

Weitere Informationen finden Sie unter [Upgrade-Anweisungen für On-Premise](../install-guide/upgrade-xml-documentation.md) von Experience Manager Guides.
