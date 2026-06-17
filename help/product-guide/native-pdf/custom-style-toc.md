---
title: Native PDF-Veröffentlichungsfunktion | Anwenden eines benutzerdefinierten Stils auf Inhaltsverzeichniseinträge und Themeninhalte
description: Erfahren Sie, wie Sie Stylesheets erstellen, verwenden und Stile für Ihre Inhalte erstellen.
exl-id: f65c9683-a1fc-432a-854b-83e8f39d7dae
feature: Output Generation
role: Admin
level: Experienced
TQID: https://experienceleague.adobe.com/cqknNhuPThhuNTsLZzwnrUzPJguIPs4J-3rX6PVR2V8
product_v2: id: fae5e35a-80c9-4b94-9352-1a060a6aab1did: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: febac97b369bad427f0f650f2cdc69b0ca6c9f69
workflow-type: tm+mt
source-wordcount: 460
ht-degree: 0%

---

# Anwenden eines benutzerdefinierten Stils auf Inhaltsverzeichniseinträge und Themeninhalte

Sie können benutzerdefinierte Stile auf Inhaltsverzeichniseinträge, Themenüberschriften oder einzelne Themen anwenden, indem Sie das Attribut `outputclass` für unterstützte Zuordnungselemente wie `<topicref>` und `<topichead>` verwenden. Um eine benutzerdefinierte Formatierung auf ein ganzes Thema anzuwenden, erweitern Sie die Stildefinition des `outputclass` in Ihrem CSS.

## Formatieren eines Themas, auf das über `<topicref>` verwiesen wird

Sie können ein `outputclass` auf ein `<topicref>` anwenden, um den Inhaltsverzeichniseintrag, den Thementitel oder den gesamten Themeninhalt in der generierten PDF zu gestalten.

Um beispielsweise ein Thema zu identifizieren, das überprüft werden muss, fügen Sie dem entsprechenden `<topicref>`-Element in Ihrer DITA-Zuordnung ein OutputClass-Attribut hinzu und definieren Sie die zugehörigen Stile in Ihrer CSS.

Im folgenden Beispiel wurde dem Thema *Verlauf von Flügen* ein `outputclass` mit dem Wert `new-topic` zugewiesen.

<img src="./assets/new-topic-attribute-in-map.png" width="500">

Die `new-topic`-Klasse kann verwendet werden, um Stile für Folgendes zu definieren:

* Der Haupteintrag im Inhaltsverzeichnis oder im Mini-Inhaltsverzeichnis
* Der Titel des Themas im Hauptinhalt
* Gesamter Inhalt des Themas einschließlich Titel

Die folgende CSS-Definition ändert die Textfarbe für den Inhaltsverzeichniseintrag und den Thementitel:

```css
.new-topic {
  color:#CC5309
}
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
  color:#CC3509
}

/* for styling topic's title */
.new-topic.title {
  color:#092ACC
}
...
```

Um Stile auf den gesamten Themeninhalt anzuwenden, hängen Sie das `-content` Suffix an den Klassennamen an. Im folgenden Beispiel wird eine Änderungsleiste zum Themeninhalt hinzugefügt:

```css
...
/* for styling the topic's content */
.new-topic-content {
  -ro-change-bar-color:#A609CC;
}
...
```

Unter Verwendung der oben genannten Stilattribute wird links neben dem Thema &quot;*des Fluges“ eine* hinzugefügt, wie unten dargestellt:

<img src="./assets/pdf-output-topic-content.jpg" width="500">

## Anwenden von Stilen auf `topichead`

Sie können das Attribut `outputclass` für ein `<topichead>`-Element verwenden, um verschiedene Stile auf den Inhaltsverzeichniseintrag und die für die `topichead` generierte Überschrift anzuwenden.

Wenn Sie beispielsweise die folgenden `topichead` in Ihrer DITA-Zuordnung definieren:

```xml
<topichead navtitle="Getting Started" outputclass="new-topichead">
    ...
</topichead>
```

Die `new-topichead`-Klasse wird auf den Eintrag „topichead“ im Inhaltsverzeichnis und auf die für den „topichead“ generierte Überschrift angewendet.

Wenn Sie einen anderen Stil auf die Überschrift anwenden möchten, definieren Sie eine separate Klasse dafür, ähnlich wie `<topicref>` separate Formatierung für den Inhaltsverzeichniseintrag und den Thementitel unterstützt:

```css
...
/* Style for the topichead TOC entry */
.new-topichead {
  color: #CC5309;
}

/* Style for the topichead heading */
.new-topichead.title {
  color: #092ACC;
}...
```

Wenn Sie den mit dem Topichead verknüpften Inhalt formatieren möchten, hängen Sie das `- content` Suffix an den Klassennamen an:

```css
.new-topichead-content {
    border-left: 2px solid #cccccc;
    padding-left: 8px;
}
```



## Leere Zeilen aus dem Inhaltsverzeichnis entfernen

Wenn Sie den Titel für keine Themen definiert haben, werden für diese Themen im Inhaltsverzeichnis leere Zeilen angezeigt.

Um die leeren Zeilen aus dem Inhaltsverzeichnis und dem Mini-Inhaltsverzeichnis zu entfernen, fügen Sie dem `layout.css` den folgenden Stil hinzu:

```css
.toc-body a:empty,
.chaptoc-body a:empty {
    display: none;
} 
```

