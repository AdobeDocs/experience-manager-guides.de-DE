---
title: Native PDF Publish-Funktion | Hinzufügen eines benutzerdefinierten Lesezeichens in der PDF-Ausgabe
description: Erfahren Sie, wie Sie Stile für Ihren Inhalt erstellen und Stile erstellen.
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

Im Allgemeinen wird das Inhaltsverzeichnis in einer DITA-Zuordnung als Lesezeichen in der endgültigen PDF-Ausgabe repliziert. Dieses Inhaltsverzeichnis wird aus den Themen- oder Abschnittstiteln in Ihrer DITA-Zuordnung erstellt. Sie können in der PDF-Ausgabe gelegentlich ein benutzerdefiniertes Lesezeichen zu einem bestimmten Inhalt hinzufügen, um die Navigation zu erleichtern. Dies kann durch Hinzufügen des Attributs `outputclass` zum Element und Anwenden des folgenden Attributs erreicht werden:

`bookmark-level: 3`

Hier ist `bookmark-level` ein Attribut und die Zahl `3` ist der Wert, der die Ebene in der Lesezeichenhierarchie angibt, auf der das Lesezeichen hinzugefügt wird. Im folgenden Beispiel enthält das Thema &quot;Kontakte&quot;der ersten Ebene die Tabelle &quot;Kontaktliste&quot;, in der das Attribut `outputclass` mit dem Wert `custom-bookmark` hinzugefügt wurde.


<img src="./assets/custom-bookmark-attribute.png" width="500">

Die folgende Definition der Klasse `custom-bookmark` wird der CSS-Datei hinzugefügt:

```css
…
/*Adding a custom bookmark*/
.custom-bookmark{
    bookmark-level: 2
}
…
```

In der PDF-Ausgabe wird die Tabelle *Kontaktliste* wie unten gezeigt auf der zweiten Ebene in der PDF-Lesezeichenliste hinzugefügt:

<img src="./assets/custom-bookmark-in-pdf-output.png" width="500">

>[!NOTE]
>
>Sie müssen die richtige Ebene auswählen, auf der das benutzerdefinierte Lesezeichen hinzugefügt wird. Wenn Sie eine Zahl angeben, die kleiner als das Lesezeichen des übergeordneten Themas ist, nimmt das benutzerdefinierte Lesezeichen die Position des übergeordneten Lesezeichens an, und alle anderen Lesezeichen werden als untergeordnete Elemente angezeigt. Dies kann zu einer unerwarteten Lesezeichenstruktur führen.
