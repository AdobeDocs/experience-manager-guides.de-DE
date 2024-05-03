---
title: Symbol für benutzerdefinierte Datentypen konfigurieren
description: Erfahren Sie, wie Sie das Symbol für benutzerdefinierte Datentypen definieren, um deren Symbol auf verschiedenen Benutzeroberflächen in AEM anzuzeigen.
source-git-commit: ce2f5e4ab6b05fbce7b8384ff59091ebf9bab7be
workflow-type: tm+mt
source-wordcount: '484'
ht-degree: 0%

---

# Symbol für benutzerdefinierte Diatetypen (Thema oder Zuordnung) konfigurieren


## Problem-Anweisung

Mit dem benutzerdefinierten Schema, das in AEM Guides verwendet wird, können Sie benutzerdefinierte Themen- oder Zuordnungstypen erstellen. Dabei können Sie bemerken, dass die benutzerdefinierten Themen/Zuordnungen im Web-Editor oder in der Assets-Benutzeroberfläche nicht als Symbol angezeigt werden. Siehe Screenshot als Referenz  (../assets/authoring/custom-ditatype-icon-notshown.png)

Um den benutzerdefinierten Themen-/Zuordnungstypen ein Symbol zuzuweisen, müssen Sie Folgendes tun:
- Suchen Sie den benutzerdefinierten Themen-/Zuordnungstyp
- Stile schreiben, um das gewünschte Symbol für den benutzerdefinierten Typ hinzuzufügen


Wir können die oben genannten Schritte implementieren, um das Symbol im Web-Editor (Repository-Ansicht) sowie in der Assets-Benutzeroberfläche anzuzeigen. Im Folgenden finden Sie die Schritte für beide


## Symbol für benutzerdefiniertes Thema/Zuordnung in der Ansicht des Web-Editors anzeigen

Schritt 1: Bestimmen Sie den Datentyp für das benutzerdefinierte Datenthema/die benutzerdefinierte Datenzuordnung - Öffnen Sie die Repository-Ansicht im Web-Editor > Entwicklerkonsole im Browser öffnen - Inspect den Symbolbereich neben dem aufgelisteten Thema/der aufgelisteten Zuordnung - Überprüfen Sie die dem benutzerdefinierten Thema zugewiesene Klasse - Siehe Screenshot  (../assets/authoring/custom-ditatype-icon-knowditatype.png) für weitere Details - Diese Klasse wird verwendet, um ein Symbol zuzuweisen und CSS für diese zu schreiben.

Schritt 2: Erstellen Sie CSS und weisen Sie diesem Datentyp ein Symbol zu - Erstellen Sie eine Client-Bibliothek unter /apps, beispielsweise erstellen Sie einen cq:ClientLibraryFolder unter dem gewünschten Pfad - fügen Sie Kategorien &quot;apps.fmdita.xml_editor.page&quot;hinzu - erstellen Sie einen Ordner &quot;assets&quot;unter diesem Verzeichnis und fügen Sie alle Symbole hinzu, die Sie für benutzerdefinierte Ordnerbaumtypen verwenden möchten - fügen Sie eine CSS-Datei unter dem Client-Bibliotheksordner hinzu, z. - icons.css&quot; - Fügen Sie folgenden Code hinzu

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
    - Speichern/Bereitstellen dieser Änderungen
Screenshot anzeigen  (../assets/authoring/custom-ditatype-icon-define-webeditor-styles.png) für weitere Details.

Und die endgültige Ausgabe wird im Screenshot angezeigt  (../assets/authoring/custom-ditatype-icon-webeditor-showstyles.png)


## Symbol für benutzerdefiniertes Thema/Zuordnung in der Assets-Benutzeroberfläche anzeigen

Schritt 1: Bestimmen des Datentyps des benutzerdefinierten Datenthemas/der benutzerdefinierten Datenzuordnung - dies wird in Schritt 1 der vorherigen Methoden erläutert

Schritt 2: JavaScript erstellen, um zu definieren, welche Symbole für den benutzerdefinierten Datentyp für benutzerdefinierte Themen-/Zuordnungstypen geladen werden sollen - Erstellen Sie eine Client-Bibliothek unter /apps, können Sie beispielsweise einen cq:ClientLibraryFolder unter dem gewünschten Pfad erstellen - Fügen Sie ihm folgende Eigenschaften hinzu: - &quot;categories&quot;(multivalue string) value as &quot;dam.gui.admin.coral&quot;- &quot;dependencies&quot;(multivalue string) value as &quot;libs.fbs.fal mdita.versioncontrol&quot; - Erstellen Sie eine Kopie der Datei &quot;/libs/fmdita/clientlibs/clientlibs/xmleditor/clientlib-dam/topic_type.js&quot; in dieses Verzeichnis /apps - bearbeiten Sie die kopierte Datei &quot;topic_type.js&quot;und ändern/fügen Sie customtopictype unter der Variablen &quot;typeImageNameMap&quot; - Sie können auch den Pfad des Ordners &quot;images&quot;ändern, indem Sie den Wert der Variablen &quot;parentImagePath&quot;ändern, in der benutzerdefinierte Symbole gespeichert werden - Erstellen Sie eine Datei mit dem Ordner js.txt-Client-Bibliothek und Verweis auf &quot;topic_type.js&quot;hinzufügen - Speichern/Bereitstellen dieser Änderungen Siehe Screenshot .  (../assets/authoring/custom-ditatype-icon-define-assetsui-styles.png) für weitere Details.

Die endgültige Ausgabe wird wie im Screenshot gezeigt angezeigt  (../assets/authoring/custom-ditatype-icon-assetsui-showstyles.png)