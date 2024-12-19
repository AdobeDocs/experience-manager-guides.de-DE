---
title: Native PDF Publish-Funktion | Hinzufügen eines benutzerdefinierten Lesezeichens in der PDF-Ausgabe
description: Erfahren Sie, wie Sie Stylesheets erstellen, verwenden und Stile für Ihre Inhalte erstellen.
exl-id: 6e6dbba3-da41-4066-b7b2-735a3d92b70a
feature: Output Generation
role: Admin
level: Experienced
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '230'
ht-degree: 0%

---

# Hinzufügen eines benutzerdefinierten Lesezeichens in der PDF-Ausgabe

Im Allgemeinen wird das Inhaltsverzeichnis in einer DITA-Zuordnung als Lesezeichen in der endgültigen PDF-Ausgabe repliziert. Dieses Inhaltsverzeichnis wird aus den Themen- oder Abschnittstiteln in Ihrer DITA-Karte erstellt. Manchmal möchten Sie vielleicht ein benutzerdefiniertes Lesezeichen zu einem bestimmten Inhalt in Ihrer PDF-Ausgabe hinzufügen, um die Navigation zu erleichtern. Dies kann erreicht werden, indem ein `outputclass` Attribut zum Element hinzugefügt und das folgende Attribut darauf angewendet wird:

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

In der PDF-Ausgabe wird die *Kontaktliste* auf der 2. Ebene in die PDF-Lesezeichenliste eingefügt, wie unten dargestellt:

<img src="./assets/custom-bookmark-in-pdf-output.png" width="500">

>[!NOTE]
>
>Sie müssen die richtige Ebene auswählen, auf der das benutzerdefinierte Lesezeichen hinzugefügt wird. Wenn Sie eine Zahl angeben, die kleiner ist als das Lesezeichen des übergeordneten Themas, übernimmt das benutzerdefinierte Lesezeichen die Position des übergeordneten Lesezeichens, und alle anderen Lesezeichen werden als untergeordnete Elemente angezeigt. Dies kann zu einer unerwarteten Lesezeichenstruktur führen.
