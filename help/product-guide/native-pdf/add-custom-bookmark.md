---
title: Native PDF-Veröffentlichungsfunktion | Hinzufügen eines benutzerdefinierten Lesezeichens in der PDF-Ausgabe
description: Erfahren Sie, wie Sie Stylesheets erstellen, verwenden und Stile für Ihre Inhalte erstellen.
exl-id: 6e6dbba3-da41-4066-b7b2-735a3d92b70a
feature: Output Generation
role: Admin
level: Experienced
source-git-commit: 1c96f25c3b970d04d23e8faf94a8f39095f6bd2c
workflow-type: tm+mt
source-wordcount: '347'
ht-degree: 0%

---

# Hinzufügen eines benutzerdefinierten Lesezeichens in der PDF-Ausgabe

Im Allgemeinen wird das Inhaltsverzeichnis in einer DITA-Zuordnung als Lesezeichen in der endgültigen PDF-Ausgabe repliziert, einschließlich des Titels **Inhalt**, der das Inhaltsverzeichnis öffnet, wenn er ausgewählt wird. Dieses Inhaltsverzeichnis wird aus den Themen- oder Abschnittstiteln in Ihrer DITA-Karte erstellt.

Manchmal möchten Sie vielleicht ein benutzerdefiniertes Lesezeichen zu einem bestimmten Inhalt in Ihrer PDF-Ausgabe hinzufügen, um die Navigation zu erleichtern. Dies kann erreicht werden, indem ein `outputclass` Attribut zum Element hinzugefügt und das folgende Attribut darauf angewendet wird:

`bookmark-level: 3`

Hier ist der `bookmark-level` ein Attribut und die Zahl `3` der Wert, der die Ebene in der Lesezeichenhierarchie angibt, zu der das Lesezeichen hinzugefügt wird. Im folgenden Beispiel hat das Thema „Kontakte“ der ersten Ebene eine Tabelle, „Kontaktliste“, der wir ein `outputclass` Attribut mit dem Wert `custom-bookmark` hinzugefügt haben.


<img src="./assets/custom-bookmark-attribute.png" width="500">

Die folgende Definition der `custom-bookmark`-Klasse wird in der CSS-Datei hinzugefügt:

```css
…
/*Adding a custom bookmark*/
.custom-bookmark{
    bookmark-level: 2
}
…
```

In der PDF-Ausgabe *die Tabelle* Kontaktliste“ auf der zweiten Ebene in der PDF-Lesezeichenliste hinzugefügt, wie unten dargestellt:

![](assets/custom-bookmark-in-pdf-output.png) {width="300" align="left"}

>[!NOTE]
>
>Sie müssen die richtige Ebene auswählen, auf der das benutzerdefinierte Lesezeichen hinzugefügt wird. Wenn Sie eine Zahl angeben, die kleiner ist als das Lesezeichen des übergeordneten Themas, übernimmt das benutzerdefinierte Lesezeichen die Position des übergeordneten Lesezeichens, und alle anderen Lesezeichen werden als untergeordnete Elemente angezeigt. Dies kann zu einer unerwarteten Lesezeichenstruktur führen.

**Entfernen des Inhaltstitels aus den PDF-Ausgabe-Lesezeichen**

Wenn Sie den Titel **Inhalte“ nicht in** PDF-Ausgabe aufnehmen möchten, können Sie ihn entfernen, indem Sie die **Inhalte** in `<p>` Element anstelle `<h1>` Elements platzieren.

Der schrittweise Prozess zum Entfernen des Inhaltstitels aus Lesezeichen lautet wie folgt:

1. Öffnen Sie die PDF-Vorlage, die Sie für die PDF-Ausgabe verwenden.
2. Öffnen Sie die **Inhaltsverzeichnisseite** in **Seiten-Layouts**.
Das Inhaltsverzeichnis wird auf der rechten Seite angezeigt.
3. Wechseln Sie in den Modus **Source** und ändern Sie das Element, in dem sich die Inhalte befinden, von `<h1>` in `<p>`.

Vor der Änderung:

```
<h1 class="toc-title">Contents</h1>
```

Nach der Änderung:

```
<p class="toc-title">Contents</p>
```

Speichern Sie die Änderungen und generieren Sie die Ausgabe neu.





