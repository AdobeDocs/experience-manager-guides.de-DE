---
title: Symbol für benutzerdefinierte Datentypen konfigurieren
description: Erfahren Sie, wie Sie ein Symbol für benutzerdefinierte Dittypen definieren, um deren Symbol auf verschiedenen Benutzeroberflächen in AEM anzuzeigen
exl-id: 5a259ea0-3b5f-4c6e-b488-1586767aa991
TQID: https://experienceleague.adobe.com/OFZePwGXAKS5XhsNcrCqOya-bgEHmtO4yl1IciNUxdQ
product_v2: id: fae5e35a-80c9-4b94-9352-1a060a6aab1did: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2: id: ab01a588-7dea-43f2-a699-0b3f128465d6id: d90290ec-3e61-4ebd-8649-bcafe0836803
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554
topic_v2: id: a004cc84-67b9-4a33-a3a7-8ec7273ef4dc
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 496
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

_Schritt 1: :_des DITA-Typs für das benutzerdefinierte DITA-Thema/AP
- Öffnen Sie die Repository-Ansicht im Web-Editor > Öffnen Sie die Entwicklerkonsole im Browser.
- Überprüfen Sie den Symbolbereich neben dem aufgelisteten Thema/der aufgelisteten Karte
- Überprüfen der dem benutzerdefinierten Thema zugewiesenen Klasse
- Weitere Informationen finden Sie im folgenden Screenshot ![siehe Screenshot](../assets/authoring/custom-ditatype-icon-knowditatype.png)
- Wir werden diese Klasse verwenden, um ein Symbol zuzuweisen und CSS dafür zu schreiben

_Schritt 2 :_Erstellen Sie CSS und weisen Sie diesem DITA-Typ das Symbol zu
- Erstellen Sie eine Client-Bibliothek unter /apps, beispielsweise erstellen Sie ein CQ:ClientLibraryFolder unter dem gewünschten Pfad
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

_Schritt 1 :_Bestimmen des DITA-Typs des benutzerdefinierten DITA-Themas/-Mapps
- Dies wird in Schritt 1 der vorherigen Methoden erläutert

_Schritt 2 :_Erstellen Sie JavaScript, um zu definieren, welche Symbole für den benutzerdefinierten DITA-Typ für benutzerdefinierte Themen-/Zuordnungstypen geladen werden sollen
- Erstellen Sie eine Client-Bibliothek unter /apps, beispielsweise erstellen Sie ein CQ:ClientLibraryFolder unter dem gewünschten Pfad
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
