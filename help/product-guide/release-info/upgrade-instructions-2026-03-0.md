---
title: Versionshinweise | Upgrade-Anweisungen und behobene Probleme in Adobe Experience Manager Guides Version 2026.03.0
description: Erfahren Sie mehr über die Kompatibilitätsmatrix und das Upgrade auf Version 2026.03.0 von Adobe Experience Manager Guides as a Cloud Service.
exl-id: 5700e649-104d-4caf-a195-6e667a71faee
hidefromtoc: true
source-git-commit: 22ea3fe3ccb974fe3795299f7815e7aae78d41e7
workflow-type: tm+mt
source-wordcount: '332'
ht-degree: 11%

---

# Aktualisierungsanweisungen für die Version 2026.03.0

Dieser Artikel behandelt die Upgrade-Anweisungen und die Kompatibilitätsmatrix für die Version 2026.03.0 von Adobe Experience Manager Guides as a Cloud Service.

Weitere Informationen zu den neuen Funktionen und Verbesserungen finden Sie unter [Neue Funktionen in Version 2026.03.0](whats-new-2026-03-0.md).

Eine Liste der in dieser Version behobenen Probleme finden Sie im Artikel [Behobene Probleme in Version 2026.03.0](fixed-issues-2026-03-0.md).

## Kompatibilitätsmatrix

In diesem Abschnitt wird die Kompatibilitätsmatrix für die Softwareanwendungen gezeigt, die von der Version 2026.03.0 von Experience Manager Guides as a Cloud Service unterstützt werden.

### FrameMaker und FrameMaker Publishing Server

| Experience Manager Guides as a Cloud Service-Version | FMPS | FrameMaker | Sauerstoff-Autor |
| --- | --- | --- | --- |
| 2 026,03,0 | Nicht kompatibel | 2022 oder höher | 26,1 |


### Sauerstoffanschluss

| Experience Manager Guides as a Cloud Service-Version | Fenster des Sauerstoffanschlusses | Oxygen Connector Mac | In Oxygen Windows bearbeiten | In Oxygen Mac bearbeiten |
| --- | --- | --- | --- | --- |
| 2 026,03,0 | 3.8 -uuid 1 | 3.8 -uuid 1 | 2,3 | 2,3 |


### AEM Site-Vorlagenversion

| Komponentenversion | Site-Version |
|---|---|
| guides-components.all-1.4.0 | aemg-sites-template-1.3.0 |

### Version der Wissensdatenbankvorlage

| Paketname der Komponenten | Komponentenversion | Vorlagenversion |
|---|---|---|
| Experience Manager Guides-Komponenten-Inhaltspaket für Cloud Service | guides-components.all-1.4.0 | aem-site-template-dxml-1.0.17 |

## Upgrade auf Version 2026.03.0

Experience Manager Guides wird beim Upgrade auf die neueste Version von Experience Manager as a Cloud Service automatisch aktualisiert.

>[!IMPORTANT]
>
> Diese Version enthält Aktualisierungen der Ordnerprofileinstellungen (ui_config.json). Wenn Sie benutzerdefinierte Einstellungen verwenden, sollten Sie diese vor dem Upgrade sichern. Überprüfen und passen Sie Ihre Einstellungen nach der Aktualisierung entsprechend den Änderungen an, die in der neuesten Version eingeführt wurden.

Überprüfen und validieren Sie Ihre Setup-Konfigurationen, um sicherzustellen, dass sie korrekt implementiert sind. Wenn Sie benutzerdefinierte Konfigurationsänderungen eingeführt haben, finden Sie unter [Zusätzliche Konfiguration für das Upgrade von Cloud Service](../cs-install-guide/additional-config-for-cloud-service.md) weitere Verfahren, die für die Version gelten, von der Sie ein Upgrade durchführen.
