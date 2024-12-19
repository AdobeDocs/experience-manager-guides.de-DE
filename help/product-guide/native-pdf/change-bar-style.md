---
title: Native PDF Publish-Funktion | Arbeiten mit benutzerdefinierten Änderungs-Balkenstilen
description: Erfahren Sie, wie Sie Stile auf Änderungsbalken anwenden.
exl-id: a81ec56c-ccbb-4599-a696-8edef7a73cdd
feature: Output Generation
role: Admin
level: Experienced
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '348'
ht-degree: 0%

---

# Arbeiten mit benutzerdefinierten Änderungs-Balkenstilen

Eine Änderungsleiste ist eine vertikale Linie, die neue oder überarbeitete Inhalte visuell identifiziert. AEM Guides ermöglicht es Ihnen, links neben dem geänderten Inhalt innerhalb von Themen und auch den geänderten Themen im Inhaltsverzeichnis der PDF-Ausgabe eine Änderungsleiste anzuzeigen.

Weitere Informationen zum Anzeigen der Änderungsleiste finden Sie unter *Erstellen von PDF mit Änderungsleiste zwischen veröffentlichten Versionen* in der [Publish PDF-Ausgabe](../web-editor/native-pdf-web-editor.md).

## Geänderter Inhalt innerhalb von Themen

Die Änderungsleiste wird auf der linken Seite des Inhalts in den Themen angezeigt, die eingefügt, geändert oder gelöscht wurden.

Sie können die folgenden Stile ändern, um die geänderten Inhalte und zwischen den mit den Änderungsleisten anzuzeigen.


>[!NOTE]
>
>Diese Stile sind Teil `layout.css` Datei, und Sie können sie nach Bedarf bearbeiten.

Sie können beispielsweise das Farbattribut im `.inserted-block`-Stil verwenden, um zu definieren, wie Ihr eingefügter Inhalt in der veröffentlichten PDF-Ausgabe angezeigt wird.


```css
...
.inserted-block { 
  color: #2ECC40; 
  display: inline; 
  -ro-comment-content: " "; 
  -ro-comment-style: underline; 
  -ro-comment-title: "Inserted"; 
  -ro-comment-date: attr(data-time); 
  -ro-comment-dateformat: "yyyy/dd/MM HH:mm:ss"; 
} 
...
```

Ebenso können Sie den `.deleted-block`-Stil verwenden, um zu definieren, wie der gelöschte Inhalt in der veröffentlichten PDF-Ausgabe angezeigt wird.

```css
...
.deleted-block { 
  display: inline; 
  color: #FF6961; 
  text-decoration: line-through; 
  -ro-comment-content: " "; 
  -ro-comment-style: strikeout; 
  -ro-comment-title: "Deleted"; 
  -ro-comment-date: attr(data-time); 
  -ro-comment-dateformat: "yyyy/dd/MM HH:mm:ss"; 
} 
...
```

Sie können `.inserted-change-bar` und `.deleted-change-bar` Stil verwenden, um das Erscheinungsbild der Änderungsleisten zu ändern, die links neben dem aktualisierten Inhalt angezeigt werden.

Beispielsweise können Sie `-ro-change-bar-color` -Attribut `.inserted-change-bar` Stil verwenden, um den eingefügten Änderungsbalken grün anzuzeigen. Sie können auch `-ro-change-bar-color` Attribut im `.deleted-change-bar`-Stil verwenden, um den gelöschten Änderungsbalken rot anzuzeigen.

```css
...
.inserted-change-bar { 
  -ro-change-bar-color: #2ECC40; 
} 

.deleted-change-bar { 
  -ro-change-bar-color: #FF6961; 
  } 
...
```

<img src="./assets/changed-bar-content.png" alt="Inhalt des geänderten Balkenthemas" width="500">

## Geändertes Thema im Inhaltsverzeichnis (TOC)

Sie können auch eine Änderungsleiste links neben den geänderten Themen im Inhaltsverzeichnis der PDF-Ausgabe hinzufügen. Sie können `-ro-change-bar-color` Attribut im `.changed-topic` verwenden, um eine Änderungsleiste in der Farbe Ihrer Wahl für die aktualisierten Themen in der Inhaltsverzeichnisliste hinzuzufügen.

Sie können beispielsweise einen Änderungsbalken mit grüner Farbe hinzufügen.

```css
...
.changed-topic { 
 -ro-change-bar-color: #2ECC40; 
}  
...
```


Dies zeigt eine grüne Änderungsleiste für alle Themen im Inhaltsverzeichnis, bei denen einige Aktualisierungen vorgenommen wurden. Sie können auf das geänderte Thema im Inhaltsverzeichnis klicken und die detaillierten Änderungen anzeigen.

<img src="./assets/changed-bar-TOC.png" alt="Geändertes Balken-Inhaltsverzeichnis" width="500">
