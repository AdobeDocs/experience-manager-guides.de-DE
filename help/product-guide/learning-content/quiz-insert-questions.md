---
title: Fragen in ein Quiz einfügen
description: Erfahren Sie, wie Sie im Produktschulungs- und -lernprogramm Fragen in ein Quiz einfügen können.
feature: Authoring
role: User
exl-id: dff38476-c078-4970-b967-05a902430015
TQID: https://experienceleague.adobe.com/2VGxq0TrCbvFXYL44fOo5xIjP6GBLi9aKfVSTfLD3jg
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2:
  - id: a3bd6397-2eb2-4908-a61c-226e26855dca
  - id: ab01a588-7dea-43f2-a699-0b3f128465d6
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 649
ht-degree: 0%

---

# Einfügen von Fragen in ein Quiz

Führen Sie die folgenden Schritte aus, um Fragen in ein Quiz einzufügen:

1. Wählen Sie den gewünschten Fragetyp aus dem Dropdown **Menü &quot;**&quot; in der Symbolleiste aus. Basierend auf Ihren Anforderungen können Sie Fragen mithilfe eines der vier verfügbaren Formate hinzufügen: „true“ oder „false“, „single correct“, „multiple correct“, „match the following“ und „short answer“, wie unten dargestellt. Weitere Informationen finden Sie unter [Fragetypen](#question-types).

   ![](assets/question-types.png){width="650"}

   Wenn sich der Cursor beim Einfügen einer Frage in einem Fragenblock befindet, wird die neue Frage standardmäßig direkt danach hinzugefügt.

   Um eine Frage zwischen den beiden vorhandenen Fragen einzufügen, fügen Sie zunächst [Absatz einfügen](#insert-paragraph-within-the-quiz) und dann Fragen ein.

1. Eine Frage wird im ausgewählten Format eingefügt. Anschließend können Sie die Frage entsprechend Ihren Anforderungen bearbeiten.

1. Sie können eine beliebige Frage auswählen und ihre Eigenschaften mithilfe des Bedienfelds **Inhaltseigenschaften** konfigurieren.

   ![](assets/question-properties.png){width="650"}

1. Speichert alle Änderungen, die ihr im Quiz vorgenommen habt.


## Frageeigenschaften

Sie können die Fragen mithilfe der folgenden Frageneigenschaften im Bedienfeld **Inhaltseigenschaften** konfigurieren:

![](assets/question-properties-new.png){width="350"}

- **Optionen**: Geben Sie die richtige Antwort auf die Frage an
- **Frage-ID**: Gibt die Frage-ID für jede Frage an. Wenn keine Frage-ID vorhanden ist, wird empfohlen, sie immer hinzuzufügen.
- **Punkte für richtige Antwort**: Geben Sie die Punkte an, die für die richtige Antwort vergeben werden sollen.
- **Strafe für falsche Antwort**: Geben Sie die Punkte an, die bei einer falschen Antwort abgezogen werden sollen.
- **Fragebezeichnung**: Aktivieren Sie diese Option, um eine Fragebezeichnung hinzuzufügen.
- **Feedback**: Ermöglicht es Ihnen, Feedback für eine korrekte oder falsche Antwort zu geben.
- **Option an Position anheften**: Wenn eine bestimmte Option für eine Frage angeheftet wird, bleibt sie an der angegebenen Position in der Optionsliste fixiert, auch wenn **Zufallsbasierte Antwortauswahl für jeden Versuch** in der Konfiguration der SCORM-Voreinstellung aktiviert ist, was andernfalls die verfügbaren Optionen neu mischen würde. Sie können den Mauszeiger über die gewünschte Option einer Frage im Bedienfeld Inhaltseigenschaften bewegen und sie anheften.

  ![](assets/pin-question.png){width="350"}

## Fügen Sie einen Absatz innerhalb des Quiz ein

Wenn Sie den Cursor auf eine fragenspezifische Frage oder einen Leerraum zwischen den beiden Fragen platzieren, wird eine blaue horizontale Linie mit einem blauen Pfeil in der rechten Ecke des Bildschirms angezeigt. Durch Auswahl des blauen Pfeils können Sie einen Absatz in die Quiz-Authoring-Oberfläche einfügen.

![](assets/insert-paragraph-here-arrow.png){width="650"}

- Wenn es in einer Frage verwendet wird, können Sie der Frage weitere Elemente wie Bilder, Tabellen, Textelemente und mehr hinzufügen.
- Wenn es zwischen den Fragen verwendet wird, können Sie wie oben erwähnt eine weitere Frage einfügen oder andere Authoring-Elemente hinzufügen.

## Frage oder Option löschen

Führen Sie folgende Schritte aus, um eine Frage oder eine bestimmte Option aus einem Quiz zu löschen:

1. Klicken Sie mit der rechten Maustaste auf die Frage oder Option, die Sie entfernen möchten.
1. Wählen Sie im Kontextmenü die Option **Frage löschen** (um die gesamte Frage zu entfernen) oder **Option Löschen** (um nur die ausgewählte Option zu entfernen) aus.

![](assets/delete-options-lc.png){width="650"}

## Fragetypen

Die folgenden Fragetypen werden in einem Quiz unterstützt:

- **Einzel richtig**: Eine Frage mit mehreren Optionen, bei der nur eine Antwort richtig ist.

  ![](assets/single-correct.png){width="650"}

- **True/False**: Eine auf einer Anweisung basierende Frage, bei der die Lernenden auswählen, ob sie „True“ oder „False“ ist.

  ![](assets/true-false.png){width="650"}


- **Mehrere richtig**: Eine Frage mit mehreren Optionen, bei denen mehr als eine Antwort korrekt sein kann.

  ![](assets/multi-correct.png){width="650"}

- **Folgende zuordnen**: Ermöglicht es den Teilnehmern, Elemente aus zwei Listen abzugleichen, um korrekte Paare zu bilden. Sie können neue Optionssätze über das Bedienfeld **Inhaltseigenschaften** hinzufügen. Um die Komplexität zu erhöhen, können Sie eine Option aus der ersten Liste entfernen und eine zusätzliche Übereinstimmung in die Übereinstimmungsspalte aufnehmen. Dies schafft ein Element der Schwierigkeit, da die Lernenden kritisch darüber nachdenken müssen, welche Option kein direktes Paar hat.

  ![](assets/match-the-following.png){width="650"}

  In der veröffentlichten Ausgabe wird für jedes Element die **Übereinstimmung mit der folgenden** Frage mit einem Dropdown-Menü angezeigt, sodass Sie die richtige Übereinstimmung aus den verfügbaren Optionen auswählen können.

  ![](assets/question-type-publishing.png){width="650"}


- **Kurze Antwort**: Ermöglicht Teilnehmern, mit einer kurzen Texteingabe zu antworten. Er akzeptiert alphanumerische Antworten, gleicht Antworten ohne Unterscheidung der Groß-/Kleinschreibung ab und bietet für sehr lange Antworten einen horizontalen Bildlaufbalken.

  ![](assets/short-answer.png){width="650"}
