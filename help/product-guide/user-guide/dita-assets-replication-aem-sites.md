---
title: Verwalten der Replikation von DITA-Quell-Assets
description: Erfahren Sie, wie Sie DITA-Quell-Assets replizieren
feature: Publishing
role: User
source-git-commit: 52921a33d30817434424772ff32b1b31d4878497
workflow-type: tm+mt
source-wordcount: '155'
ht-degree: 0%

---

# Verwalten der Replikation von DITA-Quell-Assets

Wenn die aus DITA-Inhalten generierten Ausgaben mit **Quick Publish** oder **Veröffentlichung verwalten** in einer Veröffentlichungsumgebung veröffentlicht werden, versucht AEM auch, die zugehörigen DITA-Quell-Assets zu veröffentlichen, z. B. DITA-Zuordnungen und in einigen Fällen DITA-Themen. Dies tritt auf, weil AEM DITA-Assets als Abhängigkeiten der generierten Sites-Seiten behandelt.

![](images/quick-publish-site-instance.png){width="350" align="left"}

Um die unbeabsichtigte Replikation von DITA-Inhalten in der Veröffentlichungsumgebung zu verhindern und Leistungsprobleme zu vermeiden, müssen Administratoren die DITA-Asset-Replikation explizit über den Configuration Manager verwalten. Diese Konfiguration ermöglicht es Admins, die Replikation unterstützter DITA-Asset-Typen zu steuern, einschließlich DITA-Zuordnungen, DITA-Themen, XML-Dateien und Markdown-Dateien (.md).

Um die DITA-Asset-Replikationsfunktion zu konfigurieren, zeigen Sie je nach [&#x200B; Konfiguration &quot;-Asset-Replikation für Cloud Service konfigurieren](../cs-install-guide/configure-dita-assets-replication.md) oder [DITA-Asset-Replikation für On-Premise konfigurieren](../install-guide/configure-dita-asset-replication.md) an

