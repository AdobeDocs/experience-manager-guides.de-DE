---
title: Ausschließen von Absätzen innerhalb eines Themas aus der Übersetzung
description: Ausschließen von Absätzen innerhalb eines Themas aus der Übersetzung
feature: Translation
role: User
exl-id: 21e41bb4-52f3-4352-92d9-4a60f636de99
source-git-commit: 5e0584f1bf0216b8b00f00b9fe46fa682c244e08
workflow-type: tm+mt
source-wordcount: '148'
ht-degree: 0%

---

# Ausschließen von Absätzen innerhalb eines Themas aus der Übersetzung

Die einfachste Möglichkeit besteht darin, das Attribut translation=no zu verwenden.

+ Autoren können das zusätzliche Attribut als **translation=no** in die Absätze einfügen, die sie nicht übersetzen möchten. Der Übersetzungsanbieter muss informiert werden und er kann an seinem Ende eine Konfiguration durchführen, um den Text mit diesem Attribut zu ignorieren.
+ Die vorkonfigurierte maschinelle Übersetzung (mit dem Microsoft-Übersetzungs-Test-Connector) zeigt dasselbe Verhalten.
+ Testen mit Microsoft Translation : Wenn Sie **translate=no** auf Absatzebene definieren, wird nicht der gesamte Absatz übersetzt. Dieses Attribut kann bei jedem Element definiert werden und der Inhalt in diesem Element wird nicht übersetzt.


Im Folgenden finden Sie einige Screenshots, die dies näher erläutern:

**Source-Inhalte**

![Source-Inhalte](assets/source-content.jpg)

**Übersetzte Inhalte auf Spanisch**

![Übersetzte Inhalte auf Spanisch](assets/trans-content.jpg)
