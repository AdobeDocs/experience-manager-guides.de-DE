---
title: Versionshinweise | Upgrade-Anweisungen und behobene Probleme in Adobe Experience Manager Guides Version 2026.08.0
description: Erfahren Sie mehr über die Kompatibilitätsmatrix und das Upgrade auf die Version 2026.08.0 von Adobe Experience Manager Guides as a Cloud Service.
source-git-commit: 0de22d4883096f6a9f3b2ca8acfad4a10992f5e7
workflow-type: tm+mt
source-wordcount: '417'
ht-degree: 1%

---

# Aktualisierungsanweisungen für die Version 2026.08.0

Dieser Artikel behandelt die Upgrade-Anweisungen und die Kompatibilitätsmatrix für die Version 2026.08.0 von Adobe Experience Manager Guides as a Cloud Service.

Weitere Informationen zu den neuen Funktionen und Verbesserungen finden Sie [Neue Funktionen in der Version 2026.08.0](whats-new-2026-08-0.md).

Eine Liste der in dieser Version behobenen Probleme finden Sie unter [Behobene Probleme in Version 2026.08.0](fixed-issues-2026-08-0.md).

## Kompatibilitätsmatrix

In diesem Abschnitt wird die Kompatibilitätsmatrix für die Softwareanwendungen gezeigt, die von der Version 2026.08.0 von Experience Manager Guides as a Cloud Service unterstützt werden.

### Java SDK-Ressourcen

Verwenden Sie die folgenden Ressourcen, wenn Sie benutzerdefinierte Java-Plug-ins oder Integrationen mit Experience Manager Guides entwickeln. Stellen Sie sicher, dass die SDK-Version Ihrer installierten Experience Manager Guides-Version entspricht.

| Freigabe | Java SDK-Version | Maven Central | Java API-Referenz |
|---|---|---|----|
| 2026.08.0 | 2026.8.0 | [AEM Guides SDK API 2026.8.0](https://central.sonatype.com/artifact/com.adobe.aem/aem-dox-sdk-api/2026.8.0) | [Javadoc 2026.8.0](https://javadoc.io/doc/com.adobe.aem/aem-dox-sdk-api/latest/index.html) |

Weitere Informationen finden Sie unter [Konfigurieren und Verwenden der API-JAR-Datei aus dem Maven Central Repository](https://experienceleague.adobe.com/en/docs/experience-manager-guides/using/api-reference/introduction).

### FrameMaker und FrameMaker Publishing Server

| Experience Manager Guides as a Cloud Service-Version | FMPS | FrameMaker | Sauerstoff-Autor |
| --- | --- | --- | --- |
| 2026.08.0 | Nicht kompatibel | 2022 oder höher | 26.1 |


### Sauerstoffanschluss

| Experience Manager Guides as a Cloud Service-Version | Fenster des Sauerstoffanschlusses | Oxygen Connector Mac | In Oxygen Windows bearbeiten | In Oxygen Mac bearbeiten |
| --- | --- | --- | --- | --- |
| 2026.08.0 | 3.8 -uuid 1 | 3.8 -uuid 1 | 2,3 | 2,3 |


### AEM Site-Vorlagenversion

| Komponentenversion | Site-Version |
|---|---|
| guides-components.all-1.5.1 | aemg-sites-template-1.3.0 |

### Version der Wissensdatenbankvorlage

| Paketname der Komponenten | Komponentenversion | Vorlagenversion |
|---|---|---|
| Experience Manager Guides-Komponenten-Inhaltspaket für Cloud Service | guides-components.all-1.4.0 | aem-site-template-dxml-1.0.17 |

## Upgrade auf Version 2026.08.0

Experience Manager Guides wird beim Upgrade auf die neueste Version von Experience Manager as a Cloud Service automatisch aktualisiert.

>[!IMPORTANT]
>
> Die Version enthält Aktualisierungen der Ordnerprofileinstellungen (ui_config.json). Wenn Sie benutzerdefinierte Einstellungen verwenden, sollten Sie diese vor dem Upgrade sichern. Überprüfen und passen Sie Ihre Einstellungen nach der Aktualisierung entsprechend den Änderungen an, die in der neuesten Version eingeführt wurden.

Überprüfen und validieren Sie Ihre Setup-Konfigurationen, um sicherzustellen, dass sie korrekt implementiert sind. Wenn Sie benutzerdefinierte Konfigurationsänderungen eingeführt haben, finden Sie unter [Zusätzliche Konfiguration für das Upgrade von Cloud Service](../install-conf-guide/additional-config-for-upgrade.md) weitere Verfahren, die für die Version gelten, von der Sie ein Upgrade durchführen.
