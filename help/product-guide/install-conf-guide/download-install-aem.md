---
title: Installieren von Adobe Experience Manager
description: Erfahren Sie, wie Sie Adobe Experience Manager installieren
feature: Introduction, Installation
role: Admin
level: Experienced
source-git-commit: 6f3f05419f4f5cdd45ab580cdee6fa869f20f01d
workflow-type: tm+mt
source-wordcount: '168'
ht-degree: 0%

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
> Es gibt eine Reihe von Empfehlungen zur Leistungsoptimierung, die Sie zur Verbesserung der Systemleistung in Betracht ziehen können. Weitere Informationen finden [&#x200B; unter „Empfehlungen &#x200B;](./perf-optimization-on-prem.md) Leistungsoptimierung“.
