---
title: Symbol für benutzerdefinierte Datentypen konfigurieren
description: Erfahren Sie, wie Sie ein Symbol für benutzerdefinierte Dittypen definieren, um deren Symbol in verschiedenen Benutzeroberflächen in AEM anzuzeigen
exl-id: 5a259ea0-3b5f-4c6e-b488-1586767aa991
source-git-commit: 7355f48ba8ad0ac15c54be183d9aa91bb88724e8
workflow-type: tm+mt
source-wordcount: '491'
ht-degree: 0%

---

# Konfigurieren des Symbols für benutzerdefinierte/spezialisierte Datentypen (Thema oder Zuordnung)


## Problembeschreibung

Wenn in AEM Guides ein benutzerdefiniertes Schema verwendet wird, können Sie benutzerdefinierte Themen- oder Zuordnungstypen erstellen. Dabei kann es vorkommen, dass die benutzerdefinierten Themen-/Zuordnungstypen in der Web-Editor- oder Assets-Benutzeroberfläche nicht mit einem Symbol gekennzeichnet sind. Siehe Screenshot unten als Referenz

![Screenshot als Referenz](../assets/authoring/custom-ditatype-icon-notshown.png)


Um also den benutzerdefinierten Themen-/Zuordnungstypen ein Symbol zuzuweisen, müssen Sie Folgendes tun:
- Suchen des benutzerdefinierten Themen-/Zuordnungstyps
- Stile schreiben, um das gewünschte Symbol für den benutzerdefinierten Typ hinzuzufügen


Wir können die oben genannten Schritte implementieren, um das Symbol im Web-Editor (Repository-Ansicht) sowie in der Assets-Benutzeroberfläche anzuzeigen. Im Folgenden finden Sie die Schritte für beide


## Symbol für benutzerdefiniertes Thema/Zuordnung wird in der Web-Editor-Ansicht angezeigt

_Schritt 1:_ Bestimmen Sie den DITA-Typ für das benutzerdefinierte DITA-Thema/die benutzerdefinierte DITA-App
- Öffnen Sie die Repository-Ansicht im Web-Editor > Öffnen Sie die Entwicklerkonsole im Browser.
- Inspect Der Symbolbereich neben dem aufgelisteten Thema/der aufgelisteten Karte
- Überprüfen der dem benutzerdefinierten Thema zugewiesenen Klasse
- Weitere Informationen finden Sie im folgenden Screenshot ![siehe Screenshot](../assets/authoring/custom-ditatype-icon-knowditatype.png)
- Wir werden diese Klasse verwenden, um ein Symbol zuzuweisen und CSS dafür zu schreiben

_Schritt 2:_ Erstellen Sie CSS und weisen Sie diesem DITA-Typ das Symbol zu.
- Erstellen Sie eine Client-Bibliothek unter /apps, beispielsweise erstellen Sie einen cq:ClientLibraryFolder unter dem gewünschten Pfad.
   - Fügen Sie Kategorien „apps.fmdita.xml_editor.page“ hinzu
- Erstellen Sie unter diesem Verzeichnis einen Ordner „Assets“ und fügen Sie alle Symbole hinzu, die Sie für benutzerdefinierte Datentypen verwenden möchten
- Fügen Sie unter dem Client-Bibliotheksordner eine CSS-Datei hinzu, beispielsweise „tree-icons.css“
   - Fügen Sie folgenden Code hinzu

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

- Fügen Sie css.txt unter dem Client-Bibliotheksordner hinzu und fügen Sie den Verweis auf die soeben erstellte Datei „tree-icon.css“ hinzu
- Speichern/Bereitstellen dieser Änderungen

Weitere Informationen finden Sie im folgenden Screenshot.
![Verweis-Screenshot](../assets/authoring/custom-ditatype-icon-define-webeditor-styles.png)

Die endgültige Ausgabe wird im folgenden Screenshot gezeigt
![im Screenshot gezeigt](../assets/authoring/custom-ditatype-icon-webeditor-showstyles.png)


## Symbol für benutzerdefiniertes Thema/Zuordnung wird in der Assets-Benutzeroberfläche angezeigt

_Schritt 1:_ des DITA-Typs des benutzerdefinierten DITA-Themas/der benutzerdefinierten DITA-Zuordnung
- Dies wird in Schritt 1 der vorherigen Methoden erläutert

_Schritt 2:_ Erstellen Sie JavaScript, um zu definieren, welche Symbole für den benutzerdefinierten DITA-Typ für benutzerdefinierte Themen-/Zuordnungstypen geladen werden sollen
- Erstellen Sie eine Client-Bibliothek unter /apps, beispielsweise erstellen Sie einen cq:ClientLibraryFolder unter dem gewünschten Pfad.
   - Fügen Sie folgende Eigenschaften hinzu:
      - Wert von „categories“ (mehrwertige Zeichenfolge) als „dam.gui.admin.coral“
      - Wert von „dependencies„(mehrwertige Zeichenfolge) als „libs.fmDitta.versionControl“
- Erstellen Sie eine Kopie der Datei &quot;/libs/fmdita/clientlibs/clientlibs/xmleditor/clientlib-dam/topic_type.js&quot; in diesem Verzeichnis /apps
   - Bearbeiten Sie das kopierte „topic_type.js“ und ändern/fügen Sie „customtopictype“ unter der Variablen „typeImageNameMap“ hinzu
   - Sie können auch den Pfad des Bildordners ändern, indem Sie den Wert der Variablen „parentImagePath“ ändern, in der benutzerdefinierte Symbole gespeichert werden
- Erstellen Sie eine Datei mit dem Namen „js.txt“ im Client-Bibliotheksordner und fügen Sie einen Verweis auf „topic_type.js“ hinzu.
- Speichern/Bereitstellen dieser Änderungen
Weitere Informationen finden Sie im folgenden Screenshot.
  ![Verweis-Screenshot](../assets/authoring/custom-ditatype-icon-define-assetsui-styles.png)

Und die endgültige Ausgabe wird wie im Screenshot gezeigt ![im Screenshot gezeigt](../assets/authoring/custom-ditatype-icon-assetsui-showstyles.png)
