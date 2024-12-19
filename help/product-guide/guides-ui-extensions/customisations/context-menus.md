---
title: Kontextmenüs
description: Kontextmenüs anpassen
role: User, Admin
exl-id: 25aa76dd-ef05-41ed-b980-14bbc1626059
source-git-commit: 492f72768e0de74a91eb7acc9db8264e21bfc810
workflow-type: tm+mt
source-wordcount: '154'
ht-degree: 1%

---

# Kontextmenüs anpassen

Die folgenden Kontextmenüs können angepasst werden:

- `file_options`
Controller:
   - Kartenansicht: `ditamap_viewer_controller`
   - Repository-Bedienfeld: `repository_panel_controller`
   - Bedienfeld „Favoriten“: `collection_tree_controller`
   - Referenzlinks für Dateieigenschaften: `file_references_links_controller`
   - Repository-Suchbereich: `repository_search_controller`
   - Bedienfeld „Betreff-Schema“: `subject_scheme_tree_controller`

- `folder_options`
Controller:
   - Repository-Bedienfeld: `repository_panel_controller`
   - Bedienfeld „Favoriten“: `collection_tree_controller`

- `collection_options`
Controller:
   - Bedienfeld „Favoriten“: `collection_tree_controller`

- `map_view_options`
Controller:
   - Kartenansicht: `ditamap_viewer_controller`

- `baseline_panel_menu`
Controller:
   - Baseline-Bedienfeld: `baseline_panel`

- `preset_item_menu`
Controller:
   - Voreinstellungsfenster: `preset_panel`

Sie können auch ein eigenes Kontextmenü erstellen, indem Sie eine neue eindeutige ID definieren.

Nun ist jedem Kontextmenü ein `controller id` zugeordnet. Dieser Controller übernimmt die `on-event` Funktionen für die verschiedenen Kontextmenüoptionen

Nehmen wir ein Beispiel, um das zu verstehen

```js title=customise_context_menu.js"
const loadDitaFile = (filePath, uuid) =>{
  return $.ajax({
    type: 'POST',
    url: '/bin/referencelistener',
    data: {
        operation: 'getdita',
        path: filePath,
        type: uuid ? 'UUID' : 'PATH',
        cache: false,
    },
  })
}

const fileOptions = {
    id: "file_options",
    contextMenuWidget: "repository_panel",
    view: {
            items: [
                {
                    component: "div",
                    target: {
                        key:"displayName",value: "Delete",                    
                        viewState: VIEW_STATE.REPLACE
                    }
                },
                {
                    component: "div",
                    target: {
                        key:"displayName",value: "Edit",                    
                        viewState: VIEW_STATE.REPLACE
                    }
                },
                {
                    "displayName": "Download",
                    "data": {
                      "eventid": "downloadFile"
                    },
                    "icon": "downloadFromCloud",
                    "class": "menu-separator",         
                    target: {
                        key:"displayName",value: "Duplicate",                    
                        viewState: VIEW_STATE.REPLACE
                    }
                },
            ]

    },

    controller: {
        downloadFile(){
            const path  = this.getValue('selectedItems')[0].path
            loadDitaFile(path).then((file) => {
              function download_file(name, contents) {
                const mime_type = "text/plain";
        
                const blob = new Blob([contents], {type: mime_type});
        
                const dlink = document.createElement('a');
                dlink.download = name;
                dlink.href = window.URL.createObjectURL(blob);
                dlink.onclick = function() {
                    // revokeObjectURL needs a delay to work properly
                    const that = this;
                    setTimeout(function() {
                        window.URL.revokeObjectURL(that.href);
                    }, 1500);
                };
        
                dlink.click();
                dlink.remove();
            }
            download_file(path,file.xml)
            });
          }
    }
}
```

Lassen Sie uns nun verstehen, was dieser Code tut.

1. `id` wird verwendet, um das Kontextmenü zu identifizieren, das angepasst werden soll.
2. `contextMenuWidget` wird verwendet, um die `widget id` oder die `component` zu definieren, die das Kontextmenü aufruft und die `events` verarbeitet.

Der Rest bleibt gleich, wobei `view` verwendet wird, um die Elemente zu definieren, `target` angibt, wo die Option ersetzt, angehängt oder vorangestellt werden soll, und der `contextMenuWidget`-Controller die `on-click` behandelt.
