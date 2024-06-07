---
title: Konfigurieren Sie die JSON-basierte Zuordnung zwischen einem Thema und einer Experience Fragment-Vorlage.
description: Erfahren Sie, wie Sie die JSON-basierte Zuordnung zwischen einem Thema und einer Experience Fragment-Vorlage konfigurieren.
feature: Output Generation
role: Admin
level: Experienced
source-git-commit: f252537d15d7e8f8651dddb0ae635905705e4adf
workflow-type: tm+mt
source-wordcount: '402'
ht-degree: 0%

---

# Erstellen einer Zuordnung zwischen einem Thema und einem Experience Fragment

Adobe Experience Manager-Handbücher bieten die Funktion zum Erstellen einer JSON-basierten Zuordnung zwischen einem Thema und einer Experience Fragment-Vorlage. Sie können diese Zuordnung verwenden, um Inhalte, die in einigen oder allen Elementen innerhalb eines Themas vorhanden sind, in einem Experience Fragment zu veröffentlichen.

1. So laden Sie die *experienceFragmentMapping.json*, melden Sie sich als Administrator bei Adobe Experience Manager an.
1. Wählen Sie oben den Link Adobe Experience Manager aus und wählen Sie **Instrumente**.
1. Wählen Sie in der Liste der Tools die Option Guides aus und wählen Sie die **Ordnerprofile**.
1. Wählen Sie die Profilkachel aus, die Sie konfigurieren möchten. Sie können die Zuordnung für das globale Profil oder ein Profil auf Ordnerebene konfigurieren. Wählen Sie beispielsweise die **Globales Profil** Kachel.
1. Wählen Sie die **Konfiguration des XML-Editors** und wählen Sie die **Bearbeiten** Symbol oben.
1. Wählen Sie die **Herunterladen** zum Herunterladen des *experienceFragmentMapping.json*  -Datei auf Ihrem lokalen System. Anschließend können Sie Änderungen an der Datei vornehmen und diese dann hochladen.

1. Sie müssen die folgenden Validierungen befolgen:

   1. Es sollte sich um eine JSON-Datei handeln
   2. Sie sollte ein Array enthalten, das mindestens ein Objekt enthält. Jedes Objekt sollte Folgendes enthalten:


      `"template": string `

      `"mapping": array`

      Jedes Objekt der Zuordnung muss Folgendes enthalten:

      `"name": string`

      `"class": string`

      `"resourceType": string`

      `"attributeMap": array`


1. Speichern Sie die Datei und laden Sie sie hoch.

Experience Manager-Handbücher konvertieren das gesamte Thema in HTML, das dann den im Experience Fragment verwendeten Kernkomponenten zugeordnet werden kann. Zum Beispiel der Inhalt in einer `<p>` -Tag zugeordnet werden, um eine Textkomponente im Experience Fragment zu erstellen.
* `name`: Geben Sie das HTML-Element an. Zum Beispiel `<div>`, `<img>`
* `class`: Geben Sie das DITA-Element-Tag an, das dem HTML-Element entspricht. Beispiel: `<p>` `<image>`
* `resourceType`: Geben Sie den Ressourcentyp an, der für die in Experience Fragment verwendete Komponente gilt. Beispiel: `wcm/foundation/components/text` ist der resourceType für den wcm `text` -Komponente.
* `attributeMap`: Stellen Sie zusätzliche Informationen für die Komponente bereit, z. B. ob eine Textkomponente als `RichText` oder enthält `fileReference` einer Bildkomponente.




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



Wählen Sie beim Veröffentlichen der Experience Fragments im Web Editor die `Template` aus dem Dropdown-Menü im **Experience Fragment generieren** Dialogfeld zum Anzeigen der für die Vorlage verfügbaren Zuordnung im **Zuordnung** -Feld. Wenn keine benutzerdefinierte Zuordnung für eine Vorlage vorhanden ist, wird die Standardzuordnung aufgelistet. Sie können die Standardzuordnung verwenden, um das gesamte Thema als Experience Fragment zu veröffentlichen.

Weitere Informationen finden Sie unter [Experience Fragments veröffentlichen](../user-guide/publish-experience-fragment.md).

