---
title: Konfigurieren zulässiger Sonderzeichen
description: Erfahren Sie, wie Sie zulässige Sonderzeichen konfigurieren
feature: Web Editor Configuration
role: Admin
level: Experienced
source-git-commit: 6f3f05419f4f5cdd45ab580cdee6fa869f20f01d
workflow-type: tm+mt
source-wordcount: '338'
ht-degree: 0%

---

# Konfigurieren zulässiger Sonderzeichen {#id20CIL600035}

Mit dem Web-Editor können Sie einige Sonderzeichen vorkonfiguriert einfügen. Sie können jedoch die Liste der Sonderzeichen anpassen, die Ihre Autoren in ihre Dokumente einfügen können. Wenn Sie die Liste der Sonderzeichen anpassen, wird der Standardsatz von Sonderzeichen überschrieben. Nur die Sonderzeichen, die Sie in Ihrer Konfiguration hinzufügen, werden den Autoren zur Verfügung gestellt.

Die folgenden Registerkarten enthalten Anweisungen zum Überschreiben der Standardliste von Sonderzeichen basierend auf Ihrer Experience Manager Guides-Einrichtung: Cloud Service oder On-Premise.

>[!BEGINTABS]

>[!TAB Cloud Service]

1. Erstellen Sie `symbols.json` Datei am folgenden Speicherort im Git-Repository Ihrer Cloud Manager:

   ```
   /apps/fmdita/xmleditor/
   ```

1. Fügen Sie die Sonderzeichendefinition in der `symbols.json` wie folgt hinzu:

   ```
   {"symbols": [{"label": "Arrows",
      "items": [
      {   "name": "←",   "title": "Left Arrow"   } 
      ,   
      {   "name": "↑",   "title": "Up Arrow"      } 
      ]   
      }   ]   }
   ```


Die Struktur der `symbols.json`-Datei wird nachfolgend erläutert:

- `"label": "Arrows"`: Dies legt die Kategorie für die Sonderzeichen fest. Im Snippet wird eine Kategorie mit dem Namen `"Arrows"` definiert.
- `"items"`: Dies definiert die Sammlung von Sonderzeichen in der Kategorie.
- `"name": "←", "title": "Left Arrow"`: Dies ist die Definition des Sonderzeichens. Sie beginnt mit dem `"name"`, der nicht geändert werden darf. Auf den Namen folgt das Sonderzeichen. Das `"title"` ist der Name oder Titel des Sonderzeichens, das als QuickInfo für dieses Sonderzeichen angezeigt wird.

  Sie können mehrere Definitionen von Sonderzeichen innerhalb einer Kategorie definieren.

>[!TAB On-Premise]

1. Melden Sie sich bei AEM an und öffnen Sie den CRXDE Lite-Modus.

1. Erstellen Sie `symbols.json` Datei am folgenden Speicherort:

   ```json
   /apps/fmdita/xmleditor/
   ```

1. Fügen Sie die Sonderzeichendefinition in der `symbols.json` wie folgt hinzu:

   ```json
   {"symbols": [{"label": "Arrows",
      "items": [
      {   "name": "←",   "title": "Left Arrow"   } 
      ,   
      {   "name": "↑",   "title": "Up Arrow"      } 
      ]   
      }   ]   }
   ```


Die Struktur der `symbols.json`-Datei wird nachfolgend erläutert:

- `"label": "Arrows"`: Dies legt die Kategorie für die Sonderzeichen fest. Im Snippet wird eine Kategorie mit dem Namen `"Arrows"` definiert.
- `"items"`: Dies definiert die Sammlung von Sonderzeichen in der Kategorie.
- `"name": "←", "title": "Left Arrow"`: Dies ist die Definition des Sonderzeichens. Sie beginnt mit dem `"name"`, der nicht geändert werden darf. Auf den Namen folgt das Sonderzeichen. Das `"title"` ist der Name oder Titel des Sonderzeichens, das als QuickInfo für dieses Sonderzeichen angezeigt wird.

Sie können mehrere Definitionen von Sonderzeichen innerhalb einer Kategorie definieren.

>[!ENDTABS]

**Übergeordnetes Thema:**[ Anpassen des Web-Editors](customize-overview.md)
