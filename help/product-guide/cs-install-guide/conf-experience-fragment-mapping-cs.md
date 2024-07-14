---
title: Konfigurieren Sie die JSON-basierte Zuordnung zwischen einem Thema und einer Experience Fragment-Vorlage.
description: Erfahren Sie, wie Sie die JSON-basierte Zuordnung zwischen einem Thema und einer Experience Fragment-Vorlage konfigurieren.
feature: Output Generation
role: Admin
level: Experienced
exl-id: 2b59db60-61b5-4a7e-bbf1-35cab8b89323
source-git-commit: d525775afeeb89754762ff514126b1c3a3307b3f
workflow-type: tm+mt
source-wordcount: '402'
ht-degree: 0%

---

# Erstellen einer Zuordnung zwischen einem Thema und einem Experience Fragment

Adobe Experience Manager Guides bietet die Funktion zum Erstellen einer JSON-basierten Zuordnung zwischen einem Thema und einer Experience Fragment-Vorlage. Sie können diese Zuordnung verwenden, um Inhalte, die in einigen oder allen Elementen innerhalb eines Themas vorhanden sind, in einem Experience Fragment zu veröffentlichen.

1. Melden Sie sich zum Herunterladen von *experienceFragmentMapping.json* bei Adobe Experience Manager als Administrator an.
1. Wählen Sie oben den Adobe Experience Manager-Link und dann **Tools** aus.
1. Wählen Sie in der Liste der Tools die Option &quot;Guides&quot;aus und wählen Sie **Ordnerprofile** aus.
1. Wählen Sie die Profilkachel aus, die Sie konfigurieren möchten. Sie können die Zuordnung für das globale Profil oder ein Profil auf Ordnerebene konfigurieren. Wählen Sie beispielsweise die Kachel **Globales Profil** aus.
1. Wählen Sie die Registerkarte **XML-Editor-Konfiguration** und dann oben das Symbol **Bearbeiten** aus.
1. Wählen Sie das Symbol **Download** aus, um die Datei *experienceFragmentMapping.json* auf Ihr lokales System herunterzuladen. Anschließend können Sie Änderungen an der Datei vornehmen und diese dann hochladen.

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

Experience Manager Guides konvertiert das gesamte Thema in HTML, das dann den im Experience Fragment verwendeten Kernkomponenten zugeordnet werden kann. Beispielsweise kann der Inhalt in einem `<p>` -Tag zugeordnet werden, um eine Textkomponente im Experience Fragment zu erstellen.
* `name`: Geben Sie das HTML-Element an. Zum Beispiel `<div>`, `<img>`
* `class`: Geben Sie das DITA-Element-Tag an, das dem HTML-Element entspricht. Beispiel: `<p>` `<image>`
* `resourceType`: Geben Sie den Ressourcentyp an, der für die im Experience Fragment verwendete Komponente gilt. Beispielsweise ist `wcm/foundation/components/text` der resourceType für die wcm `text` -Komponente.
* `attributeMap`: Geben Sie zusätzliche Informationen für die Komponente ein, z. B. ob eine Textkomponente als `RichText` gerendert werden soll oder die `fileReference` einer Bildkomponente enthält.




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



Wählen Sie beim Veröffentlichen der Experience Fragments im Web Editor im Dropdown-Menü im Dialogfeld **Erlebnisfragment erzeugen** die Option `Template` aus, um die für die Vorlage verfügbare Zuordnung im Feld **Zuordnung** anzuzeigen. Wenn keine benutzerdefinierte Zuordnung für eine Vorlage vorhanden ist, wird die Standardzuordnung aufgelistet. Sie können die Standardzuordnung verwenden, um das gesamte Thema als Experience Fragment zu veröffentlichen.

Weitere Informationen finden Sie unter [Publish Experience Fragments](../user-guide/publish-experience-fragment.md).
