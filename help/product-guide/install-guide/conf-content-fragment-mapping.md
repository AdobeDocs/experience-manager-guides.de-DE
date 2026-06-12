---
title: Konfigurieren der JSON-basierten Zuordnung zwischen einem Thema und einem Inhaltsfragmentmodell.
description: Erfahren Sie, wie Sie die JSON-basierte Zuordnung zwischen einem Thema und einem Inhaltsfragmentmodell konfigurieren.
exl-id: 21446bcb-e7df-4823-acc3-1fdc7473f0d1
feature: Output Generation
role: Admin
level: Experienced
hidefromtoc: yes
TQID: https://experienceleague.adobe.com/RQfBAqnFbJwbscxdqkuPFf8N8HnXXy-Z-SuiwlleofY
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2:
  - id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
subfeature_v2:
  - id: b1ef4d86-3917-4b76-a0bc-4a4771f9b3b0
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 239
ht-degree: 0%

---

# Erstellen einer Zuordnung zwischen einem Thema und einem Inhaltsfragment

AEM Guides bietet die Funktion zum Erstellen einer JSON-basierten Zuordnung zwischen einem Thema und einem Inhaltsfragmentmodell. Sie können diese Zuordnung verwenden, um Inhalte, die in einigen oder allen Elementen innerhalb eines Themas vorhanden sind, in einem Inhaltsfragment zu veröffentlichen.

1. Um die Datei *contentFragmentMapping.json* herunterzuladen, melden Sie sich bei Adobe Experience Manager als Administrator an.
1. Klicken Sie oben auf den Adobe Experience Manager-Link und anschließend auf **Tools**.
1. Wählen Sie Guides aus der Liste der Tools und wählen Sie den **Ordnerprofile** aus.
1. Wählen Sie die Kachel **Globales Profil** aus.
1. Wählen Sie die Registerkarte **XML** Editor-Konfiguration) und klicken Sie oben auf **Symbol** Bearbeiten“.
1. Wählen Sie das Symbol **Herunterladen** aus, um die *contentFragmentMapping.json*-Datei auf Ihr lokales System herunterzuladen. Anschließend können Sie Änderungen an der Datei vornehmen und diese dann hochladen.

1. Sie müssen die folgenden Validierungen durchführen:

   1. Es sollte eine JSON-Datei sein
   2. Sie sollte ein -Array enthalten, das mindestens ein Objekt enthält, und jedes Objekt sollte Folgendes enthalten:


      `"name": string `

      `"mapping": array`

      Jedes Zuordnungsobjekt muss Folgendes enthalten:

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

Sie können das gesamte Thema mit der Standardzuordnung veröffentlichen. Wählen Sie die `Full Topic` Zuordnung aus der Dropdown-Liste im Dialogfeld **Als Inhaltsfragment veröffentlichen** und haben Sie das Feld „topicData“ im Inhaltsfragmentmodell.
