---
title: Native PDF Publish-Funktion | Arbeiten mit benutzerdefinierten Änderungsbalkenstilen
description: Erfahren Sie, wie Sie Stile auf Änderungsleisten anwenden.
exl-id: a81ec56c-ccbb-4599-a696-8edef7a73cdd
feature: Output Generation
role: Admin
level: Experienced
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '348'
ht-degree: 0%

---

# Arbeiten mit benutzerdefinierten Änderungsbalkenstilen

Ein Änderungsbalken ist eine vertikale Linie, die neue oder überarbeitete Inhalte visuell identifiziert. Mit AEM Guides können Sie links neben dem geänderten Inhalt innerhalb der Themen und auch die geänderten Themen im Inhaltsverzeichnis der PDF-Ausgabe eine Änderungsleiste anzeigen.

Weitere Informationen zum Anzeigen der Änderungsleiste finden Sie unter der Einstellung *PDF mit Änderungsleiste zwischen veröffentlichten Versionen erstellen* in der Einstellung [Publish PDF Output](../web-editor/native-pdf-web-editor.md).

## Inhalt innerhalb von Themen geändert

Die Änderungsleiste wird links neben dem Inhalt in den Themen angezeigt, die eingefügt, geändert oder gelöscht wurden.

Sie können die folgenden Stile ändern, um den geänderten Inhalt und darunter mit den Änderungsleisten anzuzeigen.


>[!NOTE]
>
>Diese Stile sind Teil der Datei &quot;`layout.css`&quot;, die Sie nach Bedarf bearbeiten können.

Beispielsweise können Sie mit dem Farbattribut im Stil `.inserted-block` festlegen, wie der eingefügte Inhalt in der veröffentlichten PDF-Ausgabe angezeigt wird.


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

Auf ähnliche Weise können Sie den Stil `.deleted-block` verwenden, um festzulegen, wie der gelöschte Inhalt in der veröffentlichten PDF-Ausgabe angezeigt wird.

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

Sie können den Stil `.inserted-change-bar` und `.deleted-change-bar` verwenden, um das Erscheinungsbild der Änderungsbalken zu ändern, die links neben dem aktualisierten Inhalt angezeigt werden.

Beispielsweise können Sie das Attribut `-ro-change-bar-color` im Stil `.inserted-change-bar` verwenden, um die eingefügte Änderungsleiste in grüner Farbe anzuzeigen. Sie können auch das Attribut `-ro-change-bar-color` im Stil `.deleted-change-bar` verwenden, um die gelöschte Änderungsleiste in roter Farbe anzuzeigen.

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

<img src="./assets/changed-bar-content.png" alt="Geänderter Inhalt des Balkendiagramms" width="500">

## Geändertes Thema im Inhaltsverzeichnis (Inhaltsverzeichnis)

Sie können auch eine Änderungsleiste links von den geänderten Themen im Inhaltsverzeichnis der PDF-Ausgabe hinzufügen. Sie können das Attribut `-ro-change-bar-color` im Stil `.changed-topic` verwenden, um eine Änderungsleiste in der Farbe Ihrer Wahl für die aktualisierten Themen in der Liste &quot;Inhaltsverzeichnis&quot;hinzuzufügen.

Sie können beispielsweise einen Änderungsbalken mit grüner Farbe hinzufügen.

```css
...
.changed-topic { 
 -ro-change-bar-color: #2ECC40; 
}  
...
```


Dies zeigt eine grüne Änderungsleiste für alle Themen im Inhaltsverzeichnis, an denen einige Änderungen vorgenommen wurden. Sie können auf das geänderte Thema im Inhaltsverzeichnis klicken und die detaillierten Änderungen anzeigen.

<img src="./assets/changed-bar-TOC.png" alt="Inhaltsverzeichnis der geänderten Leiste" width="500">
