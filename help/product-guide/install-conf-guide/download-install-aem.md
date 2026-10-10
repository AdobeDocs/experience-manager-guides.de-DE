---
title: Installieren von Adobe Experience Manager
description: Erfahren Sie, wie Sie Adobe Experience Manager installieren
feature: Introduction, Installation
role: Admin
level: Experienced
exl-id: d72b007c-9f0a-41be-bca2-2d6b54c30de1
product_v2:
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
    internal-label: Experience Manager
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
    internal-label: Experience Manager Guides
feature_v2:
  - id: e88e74c7-6080-446a-8eb0-496f1ac5f7e6
    internal-label: Administration
subfeature_v2:
  - id: c5fd2af0-6cbb-4746-ab0d-40ecb093af12
    internal-label: Introduction
  - id: e557051c-ff02-4ff8-9421-cf452af0edd5
    internal-label: Installation
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
level_v2:
  - id: d378ca77-2da1-4f39-ad92-1917fe974a38
    internal-label: Experienced
source-git-commit: 81a0e7f0736ba4970673dd87a888a4c60d3c1b4e
workflow-type: tm+mt
source-wordcount: '213'
ht-degree: 5%
---
# Installieren von Adobe Experience Manager {#id213BCI020E8}

AEM Guides ist ein Plug-in, das auf Adobe Experience Manager installiert wird. Für die Installation von AEM müssen Sie einige grundlegende AEM-Konzepte und empfohlene Bereitstellungsszenarien verstehen. Die folgenden Link-Ressourcen helfen Ihnen bei den ersten Schritten bei der Installation von AEM:

- [Grundlegende AEM-Konzepte](https://helpx.adobe.com/experience-manager/6-5/sites/deploying/using/deploy.html#BasicConcepts)

- [Empfohlene AEM-Bereitstellungen](https://helpx.adobe.com/experience-manager/6-5/sites/deploying/using/recommended-deploys.html)

>[!IMPORTANT]
>
> Wenn Sie Java 11 mit AEM 6.5.x verwenden, liegt möglicherweise ein Problem vor: *JDK 11 verursacht`NoClassDefFoundError`*. Lesen Sie [JDK 11 Ursachen NoClassDefFoundError \| AEM 6.5](https://helpx.adobe.com/experience-manager/kb/jdk-11-causes-noclassdeffounderror---aem-6-5.html)-Artikel, um dieses Problem zu beheben.

Nachdem Sie die Bereitstellungsstrategie ermittelt haben, die für Ihr Unternehmen am besten geeignet ist, führen Sie den Installationsprozess wie im Abschnitt *[Erste Schritte](https://helpx.adobe.com/de/experience-manager/6-5/sites/deploying/using/deploy.html#GettingStarted)* in der Dokumentation zu AEM beschrieben durch.

Wenn Sie ein Upgrade Ihrer AEM-Instanz durchführen möchten, müssen Sie die folgende Sequenz verwenden:

1. AEM Guides deinstallieren.
1. Aktualisieren Sie Ihre AEM-Instanz.
1. Installieren Sie AEM Guides neu.

>[!IMPORTANT]
>
> Es gibt eine Reihe von Empfehlungen zur Leistungsoptimierung, die Sie zur Verbesserung der Systemleistung in Betracht ziehen können. Weitere Informationen finden [ unter „Empfehlungen ](./perf-optimization-on-prem.md) Leistungsoptimierung“.
