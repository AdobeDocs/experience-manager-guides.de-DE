---
title: Konfigurieren der JSON-basierten Zuordnung zwischen einem Thema und einer Experience Fragment-Vorlage.
description: Erfahren Sie, wie Sie die JSON-basierte Zuordnung zwischen einem Thema und einer Experience Fragment-Vorlage konfigurieren.
feature: Output Generation
role: Admin
level: Experienced
exl-id: 2b59db60-61b5-4a7e-bbf1-35cab8b89323
TQID: https://experienceleague.adobe.com/bV5SVF5pLwakZ-0auAHQc8dRH6e7axDGZQufU0i9p14
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2:
  - id: a3bd6397-2eb2-4908-a61c-226e26855dca
  - id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
subfeature_v2:
  - id: b1ef4d86-3917-4b76-a0bc-4a4771f9b3b0
  - id: fd6cc9e1-e5e5-494e-b7b1-a32f2d6cd7c9
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 406
ht-degree: 0%

---

# Erstellen einer Zuordnung zwischen einem Thema und einem Experience Fragment

Adobe Experience Manager Guides bietet die Funktion zum Erstellen einer JSON-basierten Zuordnung zwischen einem Thema und einer Experience Fragment-Vorlage. Sie können diese Zuordnung verwenden, um Inhalte, die in einigen oder allen Elementen innerhalb eines Themas vorhanden sind, in einem Experience Fragment zu veröffentlichen.

1. Um die Datei *experienceFragmentMapping.json* herunterzuladen, melden Sie sich bei Adobe Experience Manager als Administrator an.
1. Klicken Sie oben auf den Adobe Experience Manager-Link und anschließend auf **Tools**.
1. Wählen Sie Guides aus der Liste der Tools und wählen Sie den **Ordnerprofile** aus.
1. Wählen Sie die Profilkachel aus, die Sie konfigurieren möchten. Sie können die Zuordnung für das globale Profil oder ein Profil auf Ordnerebene konfigurieren. Wählen Sie beispielsweise die Kachel **Globales Profil** aus.
1. Wählen Sie die Registerkarte **XML** Editor-Konfiguration) und klicken Sie oben auf **Symbol** Bearbeiten“.
1. Wählen Sie das Symbol **Herunterladen** aus, um die *experienceFragmentMapping.json*-Datei auf Ihr lokales System herunterzuladen. Anschließend können Sie Änderungen an der Datei vornehmen und diese dann hochladen.

1. Sie müssen die folgenden Validierungen durchführen:

   1. Es sollte eine JSON-Datei sein
   2. Sie sollte ein -Array enthalten, das mindestens ein Objekt enthält, und jedes Objekt sollte Folgendes enthalten:


      `"template": string `

      `"mapping": array`

      Jedes Zuordnungsobjekt muss Folgendes enthalten:

      `"name": string`

      `"class": string`

      `"resourceType": string`

      `"attributeMap": array`


1. Speichern Sie die Datei und laden Sie sie hoch.

Experience Manager Guides konvertiert das gesamte Thema in HTML, das dann den im Experience Fragment verwendeten Kernkomponenten zugeordnet werden kann. Beispielsweise kann der Inhalt in einem `<p>`-Tag zugeordnet werden, um eine Textkomponente im Experience Fragment zu erstellen.
* `name`: Geben Sie das HTML-Element an. Zum Beispiel `<div>`, `<img>`
* `class`: Geben Sie das DITA-Element-Tag an, das dem HTML-Element entspricht. Beispiel: `<p>` `<image>`
* `resourceType`: Geben Sie den Ressourcentyp an, der für die in Experience Fragment verwendete Komponente gilt. Beispielsweise ist `wcm/foundation/components/text` der resourceType für die wcm-`text`.
* `attributeMap`: Geben Sie zusätzliche Informationen für die Komponente an, z. B. ob eine Textkomponente als `RichText` gerendert werden soll oder die `fileReference` einer Bildkomponente enthält.




Beispieldatei:

```
[
  {
    "template": "default",
    "mapping": [
      {
        "name": "#element",
        "resourceType": "wcm/foundation/components/text",
        "attributeMap": [
          {
            "from": "outerHTML",
            "to": "text"
          },
          {
            "value": true,
            "to": "textIsRich"
          }
        ]
      }
    ]
  },
  {
    "template": "/conf/we-retail/settings/wcm/templates/experience-fragment-web-variation",
    "mapping": [
      {
        "name": "div",
        "class": "title",
        "resourceType": "wcm/foundation/components/text",
        "attributeMap": [
          {
            "from": "outerHTML",
            "to": "text"
          },
          {
            "value": true,
            "to": "textIsRich"
          }
        ]
      },
      {
        "name": "h1, h2, h3, h4, h5, h6",
        "resourceType": "wcm/foundation/components/text",
        "attributeMap": [
          {
            "from": "outerHTML",
            "to": "text"
          },
          {
            "value": true,
            "to": "textIsRich"
          }
        ]
      },
      {
        "name": "div",
        "class": "p",
        "resourceType": "wcm/foundation/components/text",
        "attributeMap": [
          {
            "from": "outerHTML",
            "to": "text"
          },
          {
            "value": true,
            "to": "textIsRich"
          }
        ]
      },
      {
        "name": "img",
        "class": "image",
        "resourceType": "wcm/foundation/components/image",
        "attributeMap": [
          {
            "from": "outerHTML",
            "to": "fileReference"
          }
        ]
      },
      {
        "name": "#element",
        "resourceType": "wcm/foundation/components/text",
        "attributeMap": [
          {
            "from": "outerHTML",
            "to": "text"
          },
          {
            "value": true,
            "to": "textIsRich"
          }
        ]
      }
    ]
  }
]
```



Wählen Sie beim Veröffentlichen der Experience Fragments über den Web-Editor die `Template` aus der Dropdown-Liste im Dialogfeld **Experience Fragment generieren** aus, um die für die Vorlage verfügbare Zuordnung im Feld **Zuordnung** anzuzeigen. Wenn für eine Vorlage keine benutzerdefinierte Zuordnung vorhanden ist, wird die Standardzuordnung aufgelistet. Sie können die Standardzuordnung verwenden, um das gesamte Thema als Experience Fragment zu veröffentlichen.

Weitere Informationen finden Sie unter [Veröffentlichen von Experience Fragments](../user-guide/publish-experience-fragment.md).
