---
title: Versionshinweise zu | Aktualisierungsanweisungen für Adobe Experience Manager Guides Version 5.1.0
description: Erfahren Sie mehr über die Kompatibilitätsmatrix und das Upgrade auf Version 5.1.0 von Adobe Experience Manager Guides.
exl-id: 4b7b6756-d260-4baf-a9cb-d99fc02f020f
source-git-commit: 6e23f52fc9124d0f07f8108da1b5fe574f553469
workflow-type: tm+mt
source-wordcount: '520'
ht-degree: 7%

---

# Aktualisierungsanweisungen für die Version 5.1.0 (September 2025)

Dieser Artikel enthält die Upgrade-Anweisungen und die Kompatibilitätsmatrix für Version 5.1.0 von Adobe Experience Manager Guides.

Weitere Informationen zu den neuen Funktionen und Verbesserungen finden Sie unter [Neue Funktionen in Version 5.1.0](../release-info/whats-new-5-1-0.md).

Eine Liste der in dieser Version behobenen Probleme finden Sie unter [Behobene Probleme in Version 5.1.0](../release-info/fixed-issues-5-1-0.md).

## Kompatibilitätsmatrix

In diesem Abschnitt wird die Kompatibilitätsmatrix für die von Experience Manager Guides Version 5.1.0 unterstützten Softwareanwendungen aufgeführt.

| AEM Guides | AEM-Version | Service Pack |
| --- | --- | --- |
| 5.1.0 (UUID) | 6.5 LTS | 1 |
| 5.1.0 (UUID) | 6.5 | 23, 22, 21 |

Weitere Informationen finden Sie im Abschnitt [Technische Anforderungen](../install-guide/download-install-technical-requirements.md) im On-Premise-Installations- und Konfigurationshandbuch.

### FrameMaker und FrameMaker Publishing Server

| Freigabe | FMPS | FM |
| --- | --- | --- |
| 5.1.0 (UUID) | Unterstützt | 2022 oder höher |

### Sauerstoffanschluss

| Freigabe | Fenster des Sauerstoffanschlusses | Oxygen Connector Mac | In Oxygen Windows bearbeiten | In Oxygen Mac bearbeiten |
| --- | --- | --- |--- |--- |
| 5.1.0 (UUID) | 3.8-uuid.1 | 3.8-uuid.1 | 2,3 | 2,3 |

### Version der Wissensdatenbankvorlage

| Paketname der Komponenten | Komponentenversion | Vorlagenversion |
|---|---|---|
| Experience Manager Guides-Komponenten-Inhaltspaket für Cloud Service | dxml-components.all-1.3.0 | aem-site-template-dxml.all-1.0.4 |

### Neue AEM Site-Vorlagenversion


| AEM Guides | AEM-Version | Komponentenversion | Site-Version |
|---|---|---| ---|
| 5.1.0 UUID | 6.5 LTS | guides-components.all-1.4.1 | aemg-docs.all-1.2.0 |
| 5.1.0 UUID | 6.5 | guides-components.all-1.4.0 | aemg-docs.all-1.2.0 |

## Upgrade auf Experience Manager Guides 5.1.0

Sie können Ihre aktuelle Version von Experience Manager Guides einfach auf Version 5.1.0 auf **AEM 6.5** oder **AEM 6.5 LTS** aktualisieren.

>[!NOTE]
>
> Wenn Sie derzeit AEM 6.5 verwenden und planen, auf AEM 6.5 LTS zu wechseln, stellen Sie sicher, dass Sie zuerst das AEM-Upgrade abschließen, bevor Sie mit dem Experience Manager Guides 5.1.0-Upgrade fortfahren. Weitere Informationen finden Sie unter [Upgrade auf Adobe Experience Manager (AEM) 6.5 LTS](https://experienceleague.adobe.com/de/docs/experience-manager-65-lts/content/implementing/deploying/upgrading/upgrade).

Bevor Sie mit dem Upgrade auf Version 5.1.0 von Experience Manager Guides fortfahren, müssen Sie die folgenden Punkte berücksichtigen:

- Wenn Sie Version 4.6.3, 4.6.4, 5.0.0 oder 5.0.0 Service Pack 1 verwenden, können Sie direkt auf Version 5.1.0 aktualisieren.
- Wenn Sie Version 4.6.0, 4.6.1 verwenden, müssen Sie auf Version 4.6.3 oder 4.6.4 oder 5.0.0 aktualisieren, bevor Sie auf Version 5.1.0 aktualisieren.
- Wenn Sie Version 4.3.x, 4.2, 4.2.1 (Hotfix 4.2.1.3), 4.1 oder 4.1.x verwenden, müssen Sie vor dem Upgrade auf Version 5.1.0 ein Upgrade auf Version 4.4 durchführen.
- Wenn Sie Version 4.0 verwenden, müssen Sie auf Version 4.2 aktualisieren, bevor Sie auf Version 4.3.x aktualisieren.
- Wenn Sie Version 3.8.5 verwenden, müssen Sie auf Version 4.0 aktualisieren, bevor Sie auf Version 4.2 aktualisieren.
- Wenn Sie eine Version vor 3.8.5 verwenden, lesen Sie den Abschnitt zum Upgrade von Experience Manager Guides im produktspezifischen Installationshandbuch, das auf der [Adobe Experience Manager Guides-Hilfe für PDF Archive](https://helpx.adobe.com/de/xml-documentation-for-experience-manager/archive.html) verfügbar ist.

>[!NOTE]
>
>Sie müssen das AEM Service Pack installieren, bevor Sie die Experience Manager Guides-Version aktualisieren.

Weitere Informationen finden Sie unter [Upgrade-Anweisungen für On-Premise](../install-guide/upgrade-xml-documentation.md) von Experience Manager Guides.


