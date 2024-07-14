---
title: Ausschluss von Absätzen innerhalb eines Themas aus der Übersetzung
description: So schließen Sie Absätze innerhalb eines Themas aus der Übersetzung aus
feature: Translation
role: User
exl-id: 21e41bb4-52f3-4352-92d9-4a60f636de99
source-git-commit: 5e0584f1bf0216b8b00f00b9fe46fa682c244e08
workflow-type: tm+mt
source-wordcount: '148'
ht-degree: 0%

---

# So schließen Sie Absätze innerhalb eines Themas aus der Übersetzung aus

Am einfachsten ist es, das Attribut translation=no zu verwenden.

+ Autoren können das zusätzliche Attribut als **translation=no** in die Absätze einfügen, die sie nicht übersetzen möchten. Der Übersetzungsanbieter muss informiert werden und er kann am Ende eine Konfiguration vornehmen, um den Text mit diesem Attribut zu ignorieren.
+ Die maschinelle OOTB-Übersetzung (mit Microsoft Translation Connector zum Testen) weist das gleiche Verhalten auf.
+ Testen mit Microsoft-Übersetzung : Wenn Sie das Attribut **translate=no** auf Absatzebene definieren, wird der vollständige Absatz nicht übersetzt. Dieses Attribut kann für jedes Element definiert werden und der Inhalt innerhalb dieses Elements wird nicht übersetzt.


Im Folgenden finden Sie einige Screenshots, die dies weiter erklären:

**Source-Inhalt**

![Source-Inhalt](assets/source-content.jpg)

**Übersetzter Inhalt auf Spanisch**

![Übersetzter Inhalt auf Spanisch](assets/trans-content.jpg)
