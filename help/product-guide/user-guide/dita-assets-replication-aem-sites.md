---
title: Verwalten der Replikation von DITA-Quell-Assets
description: Erfahren Sie, wie Sie DITA-Quell-Assets replizieren
feature: Publishing
role: User
exl-id: 71aec782-2cc1-4fd5-b35b-97a603c3dd48
product_v2:
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
    internal-label: Experience Manager
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
    internal-label: Experience Manager Guides
feature_v2:
  - id: f59890ff-de81-47d5-9ef8-7ab2dd10c6c3
    internal-label: Authoring and publishing content
subfeature_v2:
  - id: f901afa4-5613-4581-add5-219fa5f03fb5
    internal-label: Publishing
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
source-git-commit: 81a0e7f0736ba4970673dd87a888a4c60d3c1b4e
workflow-type: tm+mt
source-wordcount: '156'
ht-degree: 0%
---
# Verwalten der Replikation von DITA-Quell-Assets

Wenn die aus DITA-Inhalten generierten Ausgaben mit **Quick Publish** oder **Veröffentlichung verwalten** in einer Veröffentlichungsumgebung veröffentlicht werden, versucht AEM auch, die zugehörigen DITA-Quell-Assets zu veröffentlichen, z. B. DITA-Zuordnungen und in einigen Fällen DITA-Themen. Dies tritt auf, weil AEM DITA-Assets als Abhängigkeiten der generierten Sites-Seiten behandelt.

![](images/quick-publish-site-instance.png){width="350"}

Um die unbeabsichtigte Replikation von DITA-Inhalten in der Veröffentlichungsumgebung zu verhindern und Leistungsprobleme zu vermeiden, müssen Administratoren die DITA-Asset-Replikation explizit über den Configuration Manager verwalten. Diese Konfiguration ermöglicht es Admins, die Replikation unterstützter DITA-Asset-Typen zu steuern, einschließlich DITA-Zuordnungen, DITA-Themen, XML-Dateien und Markdown-Dateien (.md).

Um die DITA-Asset-Replikationsfunktion zu konfigurieren, zeigen Sie je nach [ Konfiguration &quot;-Asset-Replikation für Cloud Service konfigurieren](../cs-install-guide/configure-dita-assets-replication.md) oder [DITA-Asset-Replikation für On-Premise konfigurieren](../install-guide/configure-dita-asset-replication.md) an
