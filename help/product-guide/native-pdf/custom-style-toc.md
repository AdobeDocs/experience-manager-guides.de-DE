---
title: Native PDF Publish-Funktion | Anwenden eines benutzerdefinierten Stils auf Inhaltsverzeichniseinträge und Themeninhalte
description: Erfahren Sie, wie Sie Stylesheets erstellen, verwenden und Stile für Ihre Inhalte erstellen.
exl-id: f65c9683-a1fc-432a-854b-83e8f39d7dae
feature: Output Generation
role: Admin
level: Experienced
source-git-commit: db4c823e592e249e1d828a7071fc0848a5e68c0f
workflow-type: tm+mt
source-wordcount: '399'
ht-degree: 0%

---

# Anwenden eines benutzerdefinierten Stils auf Inhaltsverzeichniseinträge und Themeninhalte

Gelegentlich empfiehlt es sich, benutzerdefinierte Stile auf die Inhaltsverzeichniseinträge oder ein bestimmtes Thema anzuwenden. Dies kann erreicht werden, indem ein `outputclass`-Attribut mit dem `<topicref>`-Element in Ihrer DITA-Zuordnung verknüpft wird. Wenn Sie ein benutzerdefiniertes Format auf ein ganzes Thema anwenden möchten, kann dies auch durch Erweitern der Stildefinition des Attributs in CSS erreicht werden.

Nehmen wir ein Beispiel für ein neues Thema, das Sie zur Überprüfung senden möchten. Um das aktualisierte Thema leicht zu identifizieren, müssen Sie dem `<topicref>`-Element in Ihrer DITA-Zuordnung ein `outputclass`-Attribut hinzufügen und dann einen benutzerdefinierten Stil für dasselbe Element in CSS definieren.

Im folgenden Beispiel wurde dem Thema *Verlauf von Flügen* ein `outputclass` mit dem Wert `new-topic` zugewiesen.

<img src="./assets/new-topic-attribute-in-map.png" width="500">

Mit der Klassendefinition des `new-topic` in einem CSS können Sie den Stil für die folgenden Elemente definieren:
* Der Haupteintrag im Inhaltsverzeichnis oder im Mini-Inhaltsverzeichnis
* Der Titel des Themas im Hauptinhalt
* Gesamter Inhalt des Themas einschließlich Titel

Sehen wir uns an, wie jedes dieser Szenarien im CSS definiert werden kann. In der folgenden CSS-Definition der `new-topic` wurde die Textfarbe geändert.

```css
…
.new-topic {
  color: #CC5309
}
…
```

Diese Definition steuert die Textfarbe im Inhaltsverzeichnis und den Titel des Themas. Die folgende PDF-Ausgabe zeigt die verschiedenen Farben, die auf den Inhaltsverzeichniseintrag angewendet wurden:

<img src="./assets/pdf-output-toc-entry.jpg" width="500">

Der Titel des Themas wird ebenfalls in derselben Farbe formatiert.

<img src="./assets/pdf-output-topic-title.jpg" width="500">

Wenn Sie für den Inhaltsverzeichniseintrag und den Titel des Themas unterschiedliche Stile verwenden möchten, können Sie diese separat definieren, wie unten dargestellt:

```css
...
/*for styling TOC entry */
.new-topic {
  color: #CC3509
}

/* for styling topic's title */
.new-topic.title {
  color: #092ACC
}
...
```

Schließlich können Sie auch Stile auf den gesamten Inhalt innerhalb des Themas anwenden. Dazu müssen Sie dem Klassennamen das Suffix &quot;`-content`&quot; hinzufügen. Im folgenden Beispiel wurde eine Änderungsleiste zum gesamten Inhalt des Themas hinzugefügt:

```css
...
/* for styling the topic's content */
.new-topic-content {
  -ro-change-bar-color: #A609CC;
}
...
```

Unter Verwendung der oben genannten Stilattribute wird links neben dem Thema &quot;*des Fluges“ eine* hinzugefügt, wie unten dargestellt:

<img src="./assets/pdf-output-topic-content.jpg" width="500">

## Leere Zeilen aus dem Inhaltsverzeichnis entfernen

Wenn Sie den Titel für keine Themen definiert haben, werden für diese Themen im Inhaltsverzeichnis leere Zeilen angezeigt.

Um die leeren Zeilen aus dem Inhaltsverzeichnis und dem Mini-Inhaltsverzeichnis zu entfernen, fügen Sie dem `layout.css` den folgenden Stil hinzu:

```css
.toc-body a:empty,
.chaptoc-body a:empty {
    display: none;
} 
```

