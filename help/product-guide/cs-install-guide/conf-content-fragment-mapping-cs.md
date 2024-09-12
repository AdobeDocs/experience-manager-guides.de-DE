---
title: Konfigurieren Sie die JSON-basierte Zuordnung zwischen einem Thema und einem Inhaltsfragmentmodell.
description: Erfahren Sie, wie Sie die JSON-basierte Zuordnung zwischen einem Thema und einem Inhaltsfragmentmodell konfigurieren.
exl-id: 438e2964-b9c7-462a-a68c-8031bd97911c
feature: Output Generation
role: Admin
level: Experienced
source-git-commit: 97d7776c81e7776d0248d6711ae5d05c46c44239
workflow-type: tm+mt
source-wordcount: '271'
ht-degree: 0%

---

# Erstellen einer Zuordnung zwischen einem Thema und einem Inhaltsfragment



Mit Adobe Experience Manager Guides können Sie eine JSON-basierte Zuordnung zwischen einem Thema und einem Inhaltsfragmentmodell erstellen. Sie können die JSON-basierte Zuordnung verwenden, um Inhalte in einigen oder allen Elementen innerhalb eines Themas in einem Inhaltsfragment zu veröffentlichen.

>[!NOTE]
> 
> Wenn Sie Version 4.6 oder neuere Versionen verwenden, müssen Sie diese Zuordnung nicht erstellen. Sie können die Themenelemente auf die Felder im Inhaltsfragmentmodell ziehen.
> Erfahren Sie mehr über das [Veröffentlichen von Inhaltsfragmenten](../user-guide/publish-content-fragment.md).


1. Um die Datei *contentFragmentMapping.json* herunterzuladen, melden Sie sich als Administrator bei Adobe Experience Manager an.
1. Wählen Sie oben den Adobe Experience Manager-Link und dann **Tools** aus.
1. Wählen Sie in der Liste der Tools die Option &quot;Guides&quot;aus und wählen Sie **Ordnerprofile** aus.
1. Wählen Sie die Kachel **Globales Profil** aus.
1. Wählen Sie die Registerkarte **XML-Editor-Konfiguration** und dann oben das Symbol **Bearbeiten** aus.
1. Wählen Sie das Symbol **Download** aus, um die Datei *contentFragmentMapping.json* auf Ihr lokales System herunterzuladen. Anschließend können Sie Änderungen an der Datei vornehmen und diese dann hochladen.

1. Sie müssen die folgenden Validierungen befolgen:

   1. Es sollte sich um eine JSON-Datei handeln
   2. Sie sollte ein Array enthalten, das mindestens ein Objekt enthält. Jedes Objekt sollte Folgendes enthalten:


      `"name": string `

      `"mapping": array`

      Jedes Objekt der Zuordnung muss Folgendes enthalten:

      `"modelField": string`

      `"xpath": string`

      `"outputType": string`
1. Speichern Sie die Datei und laden Sie sie hoch.

Beispieldatei:

```
[
  {
    "mapping": [
      {
        "modelField": "title",
        "xpath": "/topic[1]/title[1]",
        "outputType": "textContent"
      },
      {
        "modelField": "shortdesc",
        "xpath": "/topic[1]/shortdesc[1]",
        "outputType": "textContent"
      },
      {
        "modelField": "topicData",
        "xpath": "/topic[1]/body[1]",
        "outputType": "outerHTML"
      }
    ],
    "name": "Full Topic"
  },
  {
    "mapping": [
      {
        "modelField": "title",
        "xpath": "/topic[1]/title[1]",
        "outputType": "textContent"
      },
      {
        "modelField": "shortdesc",
        "xpath": "/topic[1]/shortdesc[1]",
        "outputType": "textContent"
      },
      {
        "modelField": "heroImage",
        "xpath": "/topic[1]/body[1]/p[1]/image[1]",
        "outputType": "outerHTML"
      },
      {
        "modelField": "dataTable",
        "xpath": "/topic[1]/body[1]/table[1]",
        "outputType": "outerHTML"
      }
    ],
    "name": "Sample Example with XPath"
  }
]
```

Sie können das gesamte Thema mit der Standardzuordnung veröffentlichen. Wählen Sie die `Full Topic` -Zuordnung aus dem Dropdown-Dialogfeld **Inhaltsfragment erzeugen** aus und weisen Sie im Inhaltsfragmentmodell das Feld &quot;topicData&quot;auf.
