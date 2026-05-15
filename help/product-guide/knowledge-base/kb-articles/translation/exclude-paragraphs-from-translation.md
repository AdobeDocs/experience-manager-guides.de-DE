---
title: Ausschließen von Absätzen innerhalb eines Themas aus der Übersetzung
description: Ausschließen von Absätzen innerhalb eines Themas aus der Übersetzung
feature: Translation
role: User
exl-id: 21e41bb4-52f3-4352-92d9-4a60f636de99
TQID: https://experienceleague.adobe.com/IAY5PLpWlHEpMygjmHI-BqS75-VqAU5x1o9mdiu4Aac
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2:
  - id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 148
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
