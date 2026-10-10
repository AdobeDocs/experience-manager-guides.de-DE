---
title: Arbeiten mit bedingten Inhalten
description: Erfahren Sie, wie Sie Bedingungen erstellen und dann die bedingte Inhaltserstellung in [!DNL AEM Guides] einrichten
role: User
exl-id: a86007e3-48d1-458b-84a7-b683e113e5b2
feature: Publishing
TQID: 'https://experienceleague.adobe.com/3Gz6-sJn7dvzJSlnKgRoRqpFTqtj5fiVlAjOv0lbD1o'
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
    internal-label: Experience Manager Guides
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
    internal-label: Experience Manager
feature_v2:
  - id: a3bd6397-2eb2-4908-a61c-226e26855dca
    internal-label: Publishing
  - id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
    internal-label: Configuration
  - id: f59890ff-de81-47d5-9ef8-7ab2dd10c6c3
    internal-label: Authoring and publishing content
subfeature_v2:
  - id: b1ef4d86-3917-4b76-a0bc-4a4771f9b3b0
    internal-label: Profiles
  - id: f901afa4-5613-4581-add5-219fa5f03fb5
    internal-label: Publishing
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
source-git-commit: 81a0e7f0736ba4970673dd87a888a4c60d3c1b4e
workflow-type: tm+mt
source-wordcount: '262'
ht-degree: 3%
---
# Arbeiten mit bedingten Inhalten

**Anwendungsfall**

* Autoren können Bedingungen für einen Inhalt festlegen, damit sie steuern können, ob er in der Ausgabe angezeigt wird.

* Autoren können beim Veröffentlichen auswählen, ob sie unterschiedliche Bedingungen anzeigen/ausblenden möchten.

* Autoren können beispielsweise Attribute als Version 1.0 und Version 2.0 im Inhalt hinzufügen und Bedingungen verwenden, um Version 1.0 für Version 1.0 einzuschließen und Version 2.0 auszuschließen.

**Schritt 1**

Definieren Sie Bedingungen, die für die Dokumentation in [!UICONTROL Ordnerprofile] relevant sind:
Siehe Abschnitt **Konfigurieren von bedingten Attributen für globale Profile oder Profile auf Ordnerebene** in [Seite 69 des Installations- und Konfigurationshandbuchs](https://helpx.adobe.com/content/dam/help/en/xml-documentation-solution/4-2/Adobe-Experience-Manager-Guides_Installation-Configuration-Guide_EN.pdf)

![Konfigurieren von Bedingungen in Ordnerprofilen](assets/conditions-in-profiles.png)

**Schritt 2**

Wählen Sie das **[!UICONTROL Ordnerprofil]** aus, das in Schritt 1 unter **Benutzereinstellungen** im XML-Editor definiert ist:
Siehe Abschnitt **Benutzereinstellungen** in [Seite 41 des Benutzerhandbuchs](https://helpx.adobe.com/content/dam/help/en/xml-documentation-solution/4-2/Adobe-Experience-Manager-Guides_User-Guide_EN.pdf)


**Schritt 3**

Verwenden Sie die Bedingungen, um Inhaltsabschnitte an Bedingungen zu knüpfen:
Siehe Abschnitt **Bedingungen** in [Seite 90 des Benutzerhandbuchs](https://helpx.adobe.com/content/dam/help/en/xml-documentation-solution/4-2/Adobe-Experience-Manager-Guides_User-Guide_EN.pdf)

![Verwenden von Bedingungen im Editor](assets/conditions-in-web-editor.png)

**Schritt 4**

Definieren Sie Bedingungsvorgaben auf Zuordnungsebene, um zu entscheiden, welche Bedingungen in der Ausgabe aktiviert werden sollen:
Siehe Abschnitt **Verwenden von** in [Seite 249 des Benutzerhandbuchs](https://helpx.adobe.com/content/dam/help/en/xml-documentation-solution/4-2/Adobe-Experience-Manager-Guides_User-Guide_EN.pdf)
