---
title: Versionshinweise | Upgrade-Anweisungen für Adobe Experience Manager Guides 5.2.0 Service Pack 1
description: Erfahren Sie mehr über die Kompatibilitätsmatrix und das Upgrade auf Version 5.2.0 Service Pack 1 von Adobe Experience Manager Guides.
source-git-commit: 6841c373b75770e8691a2cac4d56aeb368b09480
workflow-type: tm+mt
source-wordcount: '926'
ht-degree: 3%
---
# Aktualisierungsanweisungen für die Version 5.2.0 Service Pack 1 (September 2026)

Dieser Artikel enthält die Upgrade-Anweisungen und die Kompatibilitätsmatrix für Version 5.2.0 Service Pack 1 von Adobe Experience Manager Guides.

Weitere Informationen zu den neuen Funktionen und Verbesserungen finden Sie unter [Neue Funktionen in Version 5.2.0 Service Pack 1](../release-info/whats-new-5-2-1.md).

Eine Liste der in dieser Version behobenen Probleme finden Sie unter [Behobene Probleme in Version 5.2.0 Service Pack 1](../release-info/fixed-issues-5-2-0-sp1.md).

## Kompatibilitätsmatrix

In diesem Abschnitt wird die Kompatibilitätsmatrix für die Softwareanwendungen aufgelistet, die von Experience Manager Guides 5.2.0 Service Pack 1 unterstützt werden.

| AEM Guides | AEM-Version | Service Pack |
| --- | --- | --- |
| 5.2.0 Service Pack 1 (UUID) | 6.5 LTS | 2 |
| 5.2.0 Service Pack 1 (UUID) | 6.5 | 24, 23, 22 |

Weitere Informationen finden Sie im Abschnitt [Technische Anforderungen](../install-conf-guide/aemg-technical-requirements.md) im On-Premise-Installations- und Konfigurationshandbuch.


### Java SDK-Ressourcen

Verwenden Sie die folgenden Ressourcen, wenn Sie benutzerdefinierte Java-Plug-ins oder Integrationen mit Experience Manager Guides entwickeln. Stellen Sie sicher, dass die SDK-Version Ihrer installierten Experience Manager Guides-Version entspricht.

| Freigabe | Java SDK-Version | Maven Central | Java API-Referenz |
|---|---|---|----|
| 5.2.0 Service Pack 1 (UUID) | 5.2.2 | [AEM Guides SDK-API 5.2.2](https://central.sonatype.com/artifact/com.adobe.aem/aem-guides-sdk-api/5.2.2/) | [Javadoc 5.2.2](https://javadoc.io/doc/com.adobe.aem/aem-guides-sdk-api/latest/index.html) |

Weitere Informationen finden Sie unter [Konfigurieren und Verwenden der API-JAR-Datei aus dem Maven Central Repository](https://experienceleague.adobe.com/de/docs/experience-manager-guides/using/api-reference/introduction).


### FrameMaker und FrameMaker Publishing Server

| Freigabe | FMPS | FM |
| --- | --- | --- |
| 5.2.0 Service Pack 1 (UUID) | Unterstützt | 2026 oder höher |

### Sauerstoffanschluss

| Freigabe | Fenster des Sauerstoffanschlusses | Oxygen Connector Mac | In Oxygen Windows bearbeiten | In Oxygen Mac bearbeiten |
| --- | --- | --- |--- |--- |
| 5.2.0 Service Pack 1 (UUID) | 3.8-uuid.1 | 3.8-uuid.1 | 2,3 | 2,3 |

### Version der Wissensdatenbankvorlage

| Paketname der Komponenten | Komponentenversion | Vorlagenversion |
|---|---|---|
| Experience Manager Guides-Komponenten-Inhaltspaket für Cloud Service | guides-components.all-1.4.0 | aem-site-template-dxml-1.0.17 |

### Neue AEM Site-Vorlagenversion


| AEM Guides | AEM-Version | Komponentenversion | Site-Version |
|---|---|---| ---|
| 5.2.0 Service Pack 1 UUID | 6.5 LTS | guides-components.all-1.4.1 | nicht vorhanden |
| 5.2.0 Service Pack 1 UUID | 6.5 | guides-components.all-1.4.0 | aemg-sites-template-1.3.0 |

## Voraussetzungen

Stellen Sie vor dem Start des Upgrades auf Experience Manager Guides 5.2.0 Service Pack 1 Folgendes sicher:

1. Aktualisierung auf Experience Manager Guides Version 5.2.0.
1. (Optional) Alle Übersetzungsaufgaben wurden geschlossen.
1. Protokollebene für `com.adobe.fmdita.translationservices.TranslationMapUpgradeScript` Klasse in &quot;**&quot;** und diese Protokolle in einer neuen Protokolldatei anhängen, z. B. `logs/translation_upgrade.log`.

## Aktualisierungspfad für Experience Manager Guides 5.2.0 Service Pack 1

Sie können Ihre aktuelle Version von Experience Manager Guides einfach auf Version 5.2.0 Service Pack 1 auf **AEM 6.5** oder **AEM 6.5 LTS** aktualisieren.

>[!IMPORTANT]
>
> - **Für AEM 6.5 LTS**: Experience Manager Guides 5.2.0 Service Pack 1 wird nur mit AEM 6.5 LTS Service Pack 2 unterstützt.
> - **Für AEM 6.5**: Experience Manager Guides 5.2.0 Service Pack 1 wird nur mit AEM 6.5 Service Pack 24, 23 und 22 unterstützt.
> - Wenn Sie derzeit AEM 6.5 verwenden und planen, auf AEM 6.5 LTS zu wechseln, stellen Sie sicher, dass Sie zuerst das AEM-Upgrade abschließen, bevor Sie mit dem Experience Manager Guides 5.2.0-Upgrade fortfahren. Weitere Informationen finden Sie unter [Upgrade auf Adobe Experience Manager (AEM) 6.5 LTS](https://experienceleague.adobe.com/de/docs/experience-manager-65-lts/content/implementing/deploying/upgrading/upgrade).
> - Wenn Sie derzeit AEM 6.5 verwenden und planen, auf AEM 6.5 Service Pack 24 oder höher zu wechseln, stellen Sie sicher, dass Sie zuerst das AEM-Upgrade abschließen. Installieren Sie anschließend Experience Manager Guides 5.2.0 neu. Vor der Installation von Experience Manager Guides 5.2.1.

Bevor Sie mit dem Upgrade auf Version 5.2.0 Service Pack 1 von Experience Manager Guides fortfahren, müssen Sie die folgenden Punkte berücksichtigen:

- Wenn Sie Version 5.2.0 verwenden, können Sie direkt auf Version 5.2.0 Service Pack 1 aktualisieren.
- Wenn Sie Version 5.0.0, 5.0.3, 5.1.0, 5.1.3 oder 5.1.4 verwenden, können Sie direkt auf Version 5.2.0 aktualisieren.
- Wenn Sie Version 4.6.3, 4.6.4, 5.0.x verwenden, können Sie direkt auf Version 5.1.0 aktualisieren.
- Wenn Sie Version 4.6.0, 4.6.1 verwenden, müssen Sie auf Version 4.6.3 oder 4.6.4 oder 5.0.0 aktualisieren, bevor Sie auf Version 5.1.0 aktualisieren.
- Wenn Sie Version 4.3.x, 4.2, 4.2.1 (Hotfix 4.2.1.3), 4.1 oder 4.1.x verwenden, müssen Sie vor dem Upgrade auf Version 5.1.0 ein Upgrade auf Version 4.4 durchführen.
- Wenn Sie Version 4.0 verwenden, müssen Sie auf Version 4.2 aktualisieren, bevor Sie auf Version 4.3.x aktualisieren.
- Wenn Sie Version 3.8.5 verwenden, müssen Sie auf Version 4.0 aktualisieren, bevor Sie auf Version 4.2 aktualisieren.
- Wenn Sie eine Version vor 3.8.5 verwenden, lesen Sie den Abschnitt zum Upgrade von Experience Manager Guides im produktspezifischen Installationshandbuch, das auf der [Adobe Experience Manager Guides-Hilfe für PDF Archive](https://helpx.adobe.com/xml-documentation-for-experience-manager/archive.html) verfügbar ist.

## Upgrade-Prozess für Experience Manager Guides 5.2.0 Service Pack 1

>[!IMPORTANT]
>
> Die Nachbearbeitung und Indizierung kann einige Stunden dauern. Es wird empfohlen, das Upgrade-Verfahren außerhalb der Spitzenzeiten zu starten.

1. Laden Sie das Versionspaket 5.2.0 Service Pack 1 vom [Adobe Software Distribution-Portal](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html) herunter.
1. Installieren Sie das Versionspaket, auf dem Sie das Upgrade durchführen möchten, und warten Sie, bis das Paket installiert ist.
1. *(Optional)* Upgrade des Oxygen Connector-Plug-ins, das mit der Version veröffentlicht wurde, auf die Sie ein Upgrade durchführen.
1. Löschen Sie den Browser-Cache nach der Installation des Pakets.
1. Wenn Sie die Einstellung `Enable markup find and replace` für den Zugriff auf die Funktion zum Suchen und Ersetzen in der Quellansicht für zuvor erfasste Inhalte aktiviert haben, müssen Sie den `guidesAssetLucene` neu indizieren. Weitere Informationen finden Sie unter [Neuindizierung für Suchen und Ersetzen](../install-conf-guide/custom-indexing-on-prem.md).







