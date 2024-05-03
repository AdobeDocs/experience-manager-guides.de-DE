---
title: Symbol für benutzerdefinierte Datentypen konfigurieren
description: Erfahren Sie, wie Sie das Symbol für benutzerdefinierte Datentypen definieren, um deren Symbol auf verschiedenen Benutzeroberflächen in AEM anzuzeigen.
source-git-commit: 40b4c0803c87dbf1d3c2756e7974848100b5e56e
workflow-type: tm+mt
source-wordcount: '482'
ht-degree: 0%

---

# Symbol für benutzerdefinierte Diatetypen (Thema oder Zuordnung) konfigurieren


## Problem-Anweisung

Mit dem benutzerdefinierten Schema, das in AEM Guides verwendet wird, können Sie benutzerdefinierte Themen- oder Zuordnungstypen erstellen. Dabei können Sie bemerken, dass die benutzerdefinierten Themen/Zuordnungen im Web-Editor oder in der Assets-Benutzeroberfläche nicht als Symbol angezeigt werden. Siehe Screenshot als Referenz ![Screenshot als Referenz](../assets/authoring/custom-ditatype-icon-notshown.png)

Um den benutzerdefinierten Themen-/Zuordnungstypen ein Symbol zuzuweisen, müssen Sie Folgendes tun:
- Suchen Sie den benutzerdefinierten Themen-/Zuordnungstyp
- Stile schreiben, um das gewünschte Symbol für den benutzerdefinierten Typ hinzuzufügen


Wir können die oben genannten Schritte implementieren, um das Symbol im Web-Editor (Repository-Ansicht) sowie in der Assets-Benutzeroberfläche anzuzeigen. Im Folgenden finden Sie die Schritte für beide


## Symbol für benutzerdefiniertes Thema/Zuordnung in der Ansicht des Web-Editors anzeigen

*Schritt 1 *: Bestimmen Sie den Datentyp für das benutzerdefinierte Datenthema/die benutzerdefinierte Datenzuordnung.
- Öffnen Sie die Repository-Ansicht im Web-Editor > Öffnen der Entwicklerkonsole im Browser.
- Inspect den Symbolraum neben dem aufgelisteten Thema/der aufgelisteten Zuordnung
- Überprüfen Sie die dem benutzerdefinierten Thema zugewiesene Klasse.
- Screenshot anzeigen ![Screenshot anzeigen](../assets/authoring/custom-ditatype-icon-knowditatype.png) für weitere Details
- Wir werden diese Klasse verwenden, um Symbol zuzuweisen und CSS für diese Klasse zu schreiben.

*Schritt 2 *: Erstellen Sie CSS und weisen Sie diesem Datentyp ein Symbol zu.
- Erstellen Sie eine Client-Bibliothek unter /apps, beispielsweise Sie erstellen einen cq:ClientLibraryFolder unter dem gewünschten Pfad
   - Fügen Sie Kategorien &quot;apps.fmdita.xml_editor.page&quot;hinzu.
- Erstellen Sie unter diesem Verzeichnis den Ordner &quot;assets&quot;und fügen Sie alle Symbole hinzu, die Sie für benutzerdefinierte Datentypen verwenden möchten
- Fügen Sie eine CSS-Datei im Client-Bibliotheksordner hinzu, z. B. &quot;tree-icons.css&quot;.
   - Hinzufügen des folgenden Codes

```
            .tree-item-icon {
                &.custommaptype {
                    background-image: url('assets/custommap.svg')
                }
                &.customtopictype {
                    background-image: url('assets/customtopic.svg')
                }
            }
```

- Fügen Sie css.txt im Client-Bibliotheksordner hinzu und fügen Sie einen Verweis zu &quot;tree-icon.css&quot;hinzu, der gerade erstellt wurde.
- diese Änderungen speichern/bereitstellen

Screenshot anzeigen ![Screenshot anzeigen](../assets/authoring/custom-ditatype-icon-define-webeditor-styles.png) für weitere Details.

Und die endgültige Ausgabe wird im Screenshot angezeigt ![im Screenshot gezeigt](../assets/authoring/custom-ditatype-icon-webeditor-showstyles.png)


## Symbol für benutzerdefiniertes Thema/Zuordnung in der Assets-Benutzeroberfläche anzeigen

*Schritt 1*: Bestimmung des Datentyps des benutzerdefinierten Datenthemas/der benutzerdefinierten Zuordnung
- Dies wird in Schritt 1 der vorherigen Methoden erläutert.

*Schritt 2*: Erstellen Sie ein JavaScript, um zu definieren, welche Symbole für den benutzerdefinierten Datentyp für benutzerdefinierte Themen-/Zuordnungstypen geladen werden sollen
- Erstellen Sie eine Client-Bibliothek unter /apps, beispielsweise Sie erstellen einen cq:ClientLibraryFolder unter dem gewünschten Pfad
   - Fügen Sie die folgenden Eigenschaften hinzu:
      - &quot;categories&quot;(multivalue string)-Wert als &quot;dam.gui.admin.coral&quot;
      - &quot;dependencies&quot;(multivalue string)-Wert als &quot;libs.fmdita.versioncontrol&quot;
- Erstellen Sie eine Kopie der Datei &quot;/libs/fmdita/clientlibs/clientlibs/xmleditor/clientlib-dam/topic_type.js&quot;in dieses Verzeichnis /apps .
   - Bearbeiten Sie den kopierten &quot;topic_type.js&quot;und ändern/fügen Sie customtopictype unter der Variablen &quot;typeImageNameMap&quot;hinzu.
   - Sie können auch den Pfad des Ordners &quot;images&quot;ändern, indem Sie den Wert der Variablen &quot;parentImagePath&quot;an die Stelle ändern, an der benutzerdefinierte Symbole gespeichert werden
- Erstellen Sie eine Datei mit dem Namen js.txt im Client-Bibliotheksordner und fügen Sie &quot;topic_type.js&quot;einen Verweis hinzu.
- diese Änderungen speichern/bereitstellen Siehe Screenshot ![Screenshot anzeigen](../assets/authoring/custom-ditatype-icon-define-assetsui-styles.png) für weitere Details.

Die endgültige Ausgabe wird wie im Screenshot gezeigt angezeigt ![im Screenshot gezeigt](../assets/authoring/custom-ditatype-icon-assetsui-showstyles.png)