---
title: Native PDF Publish-Funktion | Verwenden von JavaScript zum Arbeiten mit Inhalten oder Stilen
description: Erfahren Sie, wie Sie Stylesheets erstellen, verwenden und Stile für Ihre Inhalte erstellen.
exl-id: 2f301f6a-0d1c-4194-84c2-0fddaef8d3ec
feature: Output Generation
role: Admin
level: Experienced
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '519'
ht-degree: 1%

---

# Verwenden von JavaScript zum Arbeiten mit Inhalten oder Stilen

Mit der nativen PDF-Veröffentlichungsfunktion können Sie JavaScript ausführen, um Ihre Inhalte oder Ihren Stil, die auf Inhalte angewendet werden, zu bearbeiten, bevor die endgültige PDF generiert wird. Mit dieser Funktion haben Sie die vollständige Kontrolle darüber, wie Ihre endgültige Ausgabe generiert wird. Sie können beispielsweise Informationen zu rechtlichen Hinweisen zur PDF-Ausgabe hinzufügen, die sich auf einer anderen PDF befindet. Mit JavaScript können Sie die Informationen zum rechtlichen Hinweis hinzufügen, sobald die PDF für den Basisinhalt erstellt wurde, jedoch bevor die endgültige PDF generiert wird.\
Um die Ausführung von JavaScript zu unterstützen, bietet die native PDF-Publishing-Funktion die folgenden Rückruffunktionen:

* `window.pdfLayout.onBeforeCreateTOC(callback)`: Diese Rückruffunktion wird ausgeführt, bevor das Inhaltsverzeichnis generiert wird.
* `window.pdfLayout.onBeforePagination(callback)`: Diese Rückruffunktion wird ausgeführt, nachdem das Inhaltsverzeichnis generiert wurde, jedoch bevor Seitenumbrüche auf der PDF hinzugefügt werden.
* `window.pdfLayout.onAfterPagination(callback)`: Diese Rückruffunktion wird ausgeführt, nachdem das Inhaltsverzeichnis und die Seitenumbrüche auf der PDF hinzugefügt wurden.

>[!NOTE]
>
>Intern wird für diese Callout-Funktionen ein Ausführungsablauf beibehalten. Zuerst wird onBeforeCreateTOC ausgeführt, dann onBeforePagination und schließlich onAfterPagination.

Je nach Typ des Inhalts oder der Stiländerung, den bzw. die Sie durchführen möchten, können Sie auswählen, welche Callback-Funktion verwendet werden soll. Wenn Sie beispielsweise Inhalte hinzufügen möchten, wird empfohlen, dies zu tun, bevor das Inhaltsverzeichnis generiert wird. Wenn Sie einige Stilaktualisierungen vornehmen möchten, können diese entweder vor oder nach der Paginierung vorgenommen werden.

Im folgenden Beispiel wird die Position der Abbildtitel von über den Bildern zu unter den Bildern geändert. Dazu müssen Sie die JavaScript-Ausführungsoption in der Voreinstellung aktivieren. Führen Sie dazu die folgenden Schritte aus:

1. Öffnen Sie die Voreinstellung zur Bearbeitung.
1. Wechseln Sie zur Registerkarte **Erweitert**.
1. Wählen Sie die Option **JavaScript aktivieren** aus.
1. Speichern Sie die Voreinstellung und schließen Sie sie.

Erstellen Sie anschließend eine JavaScript-Datei mit folgendem Code und speichern Sie sie im Ordner „Ressourcen“ Ihrer Vorlage:

```css
...
/*
* DITA only allows the figure title to be placed above images 
* This JavaScript code is used to move the figure title below the image
* */
window.addEventListener('DOMContentLoaded', function () {
    window.pdfLayout.onBeforeCreateTOC(function() {
        var titleNodes = document.querySelectorAll('.fig > .title')
        for (var i = 0; i < titleNodes.length; i++) {
            var titleNode = titleNodes[i]
            var figNode = titleNode.parentNode
            var imageNode = figNode.querySelector('.image')
            if(imageNode && imageNode.parentNode !== figNode) {
              imageNode = imageNode.parentNode
            }
            if (figNode && imageNode && imageNode.parentNode === figNode) {
                figNode.insertBefore(imageNode, titleNode)
            }
        }
    })
});
...
```

>[!NOTE]
>
>Die `window.addEventListener('DOMContentLoaded', function ()` muss aufgerufen werden, bevor die Callback-Funktionen verwendet werden.

Als Nächstes muss dieses Script aus einer Vorlagendatei aufgerufen werden, die zur Erzeugung der PDF-Ausgabe verwendet wird. In unserem Beispiel fügen wir es der Inhaltsverzeichnisvorlage hinzu. Stellen Sie sicher, dass das `<script>`-Tag innerhalb eines vordefinierten `<div>`-Tags im `<body>`-Tag hinzugefügt wird. Wenn Sie es im `<head>`-Tag oder außerhalb des `<body>`-Tags hinzufügen, wird das Skript nicht ausgeführt.

<img src="./assets/js-added-resources-template.png" width="500">

Die mit diesem Code generierte Ausgabe und die Vorlage zeigen den Abbildtitel unter dem Bild an:

<img src="./assets/fig-title-below-image.png" width="500">

## Hinzufügen eines Wasserzeichens zur PDF-Ausgabe für Entwurfsdokumente {#watermark-draft-document}

Sie können JavaScript auch verwenden, um bedingte Wasserzeichen hinzuzufügen. Diese Wasserzeichen werden Ihrem Dokument hinzugefügt, wenn die definierte Bedingung erfüllt ist.\
Sie können beispielsweise eine JavaScript-Datei mit folgendem Code erstellen, um ein Wasserzeichen für die PDF-Ausgabe des noch nicht genehmigten Dokuments zu erstellen. Dieses Wasserzeichen wird nicht angezeigt, wenn Sie die PDF für das Dokument im Dokumentstatus „Genehmigt“ generieren.

```css
...
/*
* This file can be used to add a watermark to the PDF output
* */

window.addEventListener('DOMContentLoaded', function () {
    var watermark = 'Draft'
    var metaTag = document.getElementsByTagName('meta')
    css = "@page {\n  @left-middle {\n    content: \"".concat(watermark, "\";\n    z-index: 100;\n    font-family: sans-serif;\n    font-size: 80pt;\n    font-weight: bold;\n    color: gray(0, 0.3);\n    text-align: center;\n    transform: rotate(-54.7deg);\n    position: absolute;\n    left: 0;\n    top: 0;\n    width: 100%;\n    height: 100%;\n  }\n}")
    head = document.head || document.getElementsByTagName('head')[0], style = document.createElement('style');
    style.appendChild(document.createTextNode(css));
    window.pdfLayout.onBeforePagination(function () {
        for (let i = 0; i < metaTag.length; i++) {
            if (metaTag[i].getAttribute('name') === 'docstate' && metaTag[i].getAttribute('value') !== 'Approved') {
                head.appendChild(style);
            }
        }
    })
});
...
```

Die mit diesem Code generierte PDF-Ausgabe zeigt ein Wasserzeichen *Entwurf* auf der Titelseite Ihres Dokuments an:

<img src="./assets/draft-watermark.png" width="500">
