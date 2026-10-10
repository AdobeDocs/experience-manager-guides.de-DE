---
title: Konfigurieren zusätzlicher Sonderzeichen in der Editor-Symbolleiste
description: Erfahren Sie, wie Sie zusätzliche Sonderzeichen im Editor von AEM Guides konfigurieren.
feature: Web Editor
role: User
exl-id: 4007eb03-c100-4892-b293-f22b3f0082e2
product_v2:
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
    internal-label: Experience Manager
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
    internal-label: Experience Manager Guides
feature_v2:
  - id: ab01a588-7dea-43f2-a699-0b3f128465d6
    internal-label: Authoring
subfeature_v2:
  - id: f89f75b0-cf2e-4e96-aec8-fe8c39cbd0ef
    internal-label: Web Editor
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
source-git-commit: 81a0e7f0736ba4970673dd87a888a4c60d3c1b4e
workflow-type: tm+mt
source-wordcount: '270'
ht-degree: 0%
---
# Konfigurieren zusätzlicher Sonderzeichen in der Editor-Symbolleiste für On-Premise

In der Symbolleiste des Web-Editors gibt es eine Verknüpfungsoption, mit der der Autor die Sonderzeichen bereits einfügen kann.
Dasselbe kann im folgenden Screenshot gezeigt werden:

![Sonderzeichen](assets/special-chars.png)


Diese Liste von Zeichen kann hier konfiguriert werden. Wenn Sie mehr Zeichen zu diesem Feld hinzufügen müssen, führen Sie die folgenden Schritte aus:

+ Melden Sie sich bei AEM an und öffnen Sie den CRXDE Lite-Modus.

+ Erstellen Sie die Datei „symbols.json“ am folgenden Speicherort: &quot;/apps/fmdita/xmeditor/&quot; (Sie können den Standardwert vom Speicherort &quot;/libs/fmdita/clientlibs/clientlibs/xmleditor/symbols.json&quot; kopieren)

+ Fügen Sie die Sonderzeichendefinition in der Datei „symbols.json“ wie folgt hinzu:

```
{
      "label": "Logical Symbols",
      "items": [
        {
          "name": "≥",
          "title": "Greater-Than or Equal To"
        },
        {
          "name": "≤",
          "title": "Smaller-Than or Equal To"
        }
      ]
}
```

Die Struktur der Datei „symbols.json“ wird nachfolgend erläutert:

+ „label“: „Logical Symbols“: Legt die Kategorie der Sonderzeichen fest. Im Snippet wird eine Kategorie mit dem Namen „Logisches Symbol“ definiert.

+ „items“: Damit wird die Sammlung von Sonderzeichen in der Kategorie definiert.

+ „name“: &quot;≥&quot;, „title“: „größer oder gleich“: Dies ist die Definition des Sonderzeichens. Sie beginnt mit der Bezeichnung „Name“, die nicht geändert werden darf. Auf den Namen folgt das Sonderzeichen. Der „Titel“ ist der Name oder Titel des Sonderzeichens, das als QuickInfo für dieses Sonderzeichen angezeigt wird.

Sie können mehrere Definitionen von Sonderzeichen innerhalb einer Kategorie definieren.

Dadurch wird eine weitere Kategorie in das Dialogfeld Sonderzeichen eingefügt:

![Sonderzeichenkategorie](assets/special-char-category.png)

![Sonderzeichen einfügen](assets/insert-special-char.png)

>[!MORELIKETHIS]
>
>+ [Installations- und Konfigurationshandbuch](https://helpx.adobe.com/content/dam/help/en/xml-documentation-solution/3-6/XML-Documentation-for-Adobe-Experience-Manager_Installation-Configuration-Guide_EN.pdf)
