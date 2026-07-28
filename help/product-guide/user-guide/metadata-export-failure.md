---
title: Der Metadatenexport schlägt in Experience Manager Guides mit der Ausnahme „Zeichenfolge ist zu lang“ fehl
description: Erfahren Sie, warum der Metadatenexport für Inhaltsleitfäden in der Assets-Benutzeroberfläche fehlschlagen kann.
feature: Authoring, Publishing
role: User
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2:
  - id: a3bd6397-2eb2-4908-a61c-226e26855dca
  - id: ab01a588-7dea-43f2-a699-0b3f128465d6
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
topic_v2:
  - id: c1579802-ddd4-4214-8a91-97b2066abe11
source-git-commit: 1c61df4820e559417410d25c81800637481b040c
workflow-type: tm+mt
source-wordcount: 274
ht-degree: 0%

---

# Warum schlägt der Metadatenexport für einen Ordner mit der Ausnahme „Zeichenfolge ist zu lang“ fehl?

Wenn Sie [Metadaten exportieren](https://experienceleague.adobe.com/de/docs/experience-manager-65/content/assets/using/metadata#export-metadata) für einen Ordner über die Assets-Benutzeroberfläche, kann der Exportvorgang mit `String is too long` Ausnahme fehlschlagen. Dies geschieht normalerweise, wenn der Ordner Experience Manager Guides-spezifische Eigenschaften enthält, die nicht Zeichenfolgenwerte speichern, z. B. `baselineObj`.

**Warum passiert das?**

Einige Eigenschaften, die unter dem Metadatenknoten eines Assets gespeichert sind, werden intern von Experience Manager Guides verwendet und enthalten Daten wie JSON-Objekte anstelle von einfachen Zeichenfolgenwerten. Wenn beim Exportieren von Metadaten für einen Ordner **Zu exportierende Eigenschaften** auf **Alle** festgelegt ist, versucht der Exportvorgang, jede Eigenschaft in eine Zeichenfolge zu konvertieren, was bei Eigenschaften mit diesen Daten fehlschlägt.

**Wie lässt sich dies verhindern?**

Um diesen Fehler zu vermeiden, werden in der Asset-Metadaten-Exporter-Konfiguration die folgenden Eigenschaften **Metadaten-Export ausgeschlossen**:

- `baseline`
- `namedoutputs`
- `conditionpresets`
- `nextgenbaselinestore`

**Kann ich diese Eigenschaften trotzdem exportieren?**

Ja. Wenn Sie eine oder mehrere dieser Eigenschaften im Export benötigen, können Sie die **Asset-Metadaten-Exporter-Konfiguration** bearbeiten und aus der Ausschlussliste entfernen.

Wenn Sie eine Eigenschaft aus der Ausschlussliste entfernen, wird nicht garantiert, dass der Export erfolgreich ist. Je nach Größe und Inhalt der zugrunde liegenden Daten kann der Vorgang mit derselben Ausnahme weiterhin fehlschlagen. Wenn dies nach der erneuten Aktivierung einer Eigenschaft auftritt, fügen Sie sie wieder zur Ausschlussliste hinzu, um das standardmäßige, zuverlässige Exportverhalten wiederherzustellen.
