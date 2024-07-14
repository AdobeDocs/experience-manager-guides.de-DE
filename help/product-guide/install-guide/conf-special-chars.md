---
title: Zulässige Sonderzeichen konfigurieren
description: Erfahren Sie, wie Sie zulässige Sonderzeichen konfigurieren
exl-id: 3dd7752e-0836-480a-b1e1-6fa2099d404f
feature: Web Editor Configuration
role: Admin
level: Experienced
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '209'
ht-degree: 0%

---

# Zulässige Sonderzeichen konfigurieren {#id20CIL600035}

Mit dem Web Editor können Sie einige Sonderzeichen direkt einfügen. Sie können jedoch die Liste der Sonderzeichen anpassen, die Ihre Autoren in ihre Dokumente einfügen können. Wenn Sie die Liste der Sonderzeichen anpassen, wird der Standardsatz der Sonderzeichen überschrieben. Den Autoren werden nur die Sonderzeichen zur Verfügung gestellt, die Sie in Ihrer Konfiguration hinzufügen.

Führen Sie die folgenden Schritte aus, um die Standardliste mit Sonderzeichen zu überschreiben:

1. Melden Sie sich bei AEM an und öffnen Sie den CRXDE Lite-Modus.

1. Erstellen Sie die Datei &quot;`symbols.json`&quot; am folgenden Speicherort:

   ```json
   /apps/fmdita/xmleditor/
   ```

1. Fügen Sie die Sonderzeichendefinition in der Datei `symbols.json` wie folgt hinzu:

   ```json
   {"symbols": [{"label": "Arrows",
      "items": [
      {   "name": "←",   "title": "Left Arrow"   } 
      ,   
      {   "name": "↑",   "title": "Up Arrow"      } 
      ]   
      }   ]   }
   ```


Die Struktur der Datei `symbols.json` wird nachfolgend beschrieben:

- `"label": "Arrows"`: Gibt die Kategorie für die Sonderzeichen an. Im Snippet wird eine Kategorie mit dem Namen `"Arrows"` definiert.
- `"items"`: Damit wird die Sammlung von Sonderzeichen in der Kategorie definiert.
- `"name": "←", "title": "Left Arrow"`: Dies ist die Definition des Sonderzeichens. Sie beginnt mit der Bezeichnung `"name"` , die nicht geändert werden darf. Dem Namen folgt das Sonderzeichen. Die `"title"` ist der Name oder Titel des Sonderzeichens, das als QuickInfo für dieses Sonderzeichen angezeigt wird.

  Sie können mehrere Definitionen von Sonderzeichen innerhalb einer Kategorie definieren.


**Übergeordnetes Thema:**[ Web-Editor anpassen](conf-web-editor.md)
