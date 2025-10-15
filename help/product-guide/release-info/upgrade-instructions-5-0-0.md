---
title: Versionshinweise zu | Aktualisierungsanweisungen für Adobe Experience Manager Guides Version 5.0.0
description: Erfahren Sie mehr über die Kompatibilitätsmatrix und das Upgrade auf Version 5.0.0 von Adobe Experience Manager Guides.
exl-id: 763db247-133e-40c0-807a-2f965b1ddb2f
source-git-commit: ef8de789f8d6cf0cabc55f4d12c72b164619231c
workflow-type: tm+mt
source-wordcount: '413'
ht-degree: 6%

---

# Aktualisierungsanweisungen für die Version 5.0.0 (März 2025)

Dieser Artikel behandelt die Upgrade-Anweisungen und die Kompatibilitätsmatrix für Version 5.0.0 von Adobe Experience Manager Guides.

Weitere Informationen zu den neuen Funktionen und Verbesserungen finden Sie unter [Neue Funktionen in Version 5.0.0](../release-info/whats-new-5-0-0.md).

Eine Liste der in dieser Version behobenen Probleme finden Sie unter [Behobene Probleme in Version 5.0.0](../release-info/fixed-issues-5-0-0.md).

## Kompatibilitätsmatrix

In diesem Abschnitt wird die Kompatibilitätsmatrix für die von Experience Manager Guides Version 5.0.0 unterstützten Softwareanwendungen aufgeführt.

### Adobe Experience Manager

**5.0.0 UUID**

Version 6.5 Service Pack 22, Service Pack 21 und Service Pack 20

Weitere Informationen finden Sie im Abschnitt [Technische Anforderungen](../install-guide/download-install-technical-requirements.md) im On-Premise-Installations- und Konfigurationshandbuch.

### FrameMaker und FrameMaker Publishing Server

| Freigabe | FMPS | FM |
| --- | --- | --- |
| 5.0.0 (UUID) | Unterstützt | 2022 oder höher |

### Sauerstoffanschluss

| Freigabe | Fenster des Sauerstoffanschlusses | Oxygen Connector Mac | In Oxygen Windows bearbeiten | In Oxygen Mac bearbeiten |
| --- | --- | --- |--- |--- |
| 5.0.0 (UUID) | 3.7-uuid.2 | 3.7-uuid.2 | 2,3 | 2,3 |

### Version der Wissensdatenbankvorlage

| Paketname der Komponenten | Komponentenversion | Vorlagenversion |
|---|---|---|
| Experience Manager Guides-Komponenten-Inhaltspaket für Cloud Service | dxml-components.all-1.3.0 | aem-site-template-dxml.all-1.0.4 |

### Neue AEM Site-Vorlagenversion


| Komponentenversion | Site-Version |
|---|---|
| guides-components.all-1.3.0 | aemg-docs.all-1.2.0 |


## Upgrade auf Version 5.0.0 von Experience Manager Guides

Sie können Ihre aktuelle Version von Guides einfach auf Version 5.0.0 aktualisieren. Bevor Sie mit dem Upgrade auf Version 5.0.0 von Experience Manager Guides fortfahren, müssen Sie die folgenden Punkte berücksichtigen:

- Wenn Sie Version 4.6.3, 4.6.1, 4.6 oder 4.4 verwenden, können Sie direkt auf Version 5.0.0 aktualisieren.
- Wenn Sie Version 4.3.x, 4.2, 4.2.1 (Hotfix 4.2.1.3), 4.1 oder 4.1.x verwenden, müssen Sie vor dem Upgrade auf Version 5.0.0 ein Upgrade auf Version 4.4 durchführen.
- Wenn Sie Version 4.0 verwenden, müssen Sie auf Version 4.2 aktualisieren, bevor Sie auf Version 4.3.x aktualisieren.
- Wenn Sie Version 3.8.5 verwenden, müssen Sie auf Version 4.0 aktualisieren, bevor Sie auf Version 4.2 aktualisieren.
- Wenn Sie eine Version vor 3.8.5 verwenden, lesen Sie den Abschnitt zum Upgrade von Experience Manager Guides im produktspezifischen Installationshandbuch, das auf der [Adobe Experience Manager Guides-Hilfe für PDF Archive](https://helpx.adobe.com/de/xml-documentation-for-experience-manager/archive.html) verfügbar ist.

>[!NOTE]
>
>Sie müssen das AEM Service Pack installieren, bevor Sie die Experience Manager Guides-Version aktualisieren.

Weitere Informationen finden Sie unter [Upgrade-Anweisungen für On-Premise](../install-guide/upgrade-xml-documentation.md) von Experience Manager Guides.
