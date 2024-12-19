---
title: Arbeiten mit bedingten Inhalten
description: Erfahren Sie, wie Sie Bedingungen erstellen und dann die bedingte Inhaltserstellung in einrichten [!DNL AEM Guides]
role: User
exl-id: a86007e3-48d1-458b-84a7-b683e113e5b2
feature: Publishing
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '199'
ht-degree: 5%

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

![Verwenden von Bedingungen im Web-Editor](assets/conditions-in-web-editor.png)

**Schritt 4**

Definieren Sie Bedingungsvorgaben auf Zuordnungsebene, um zu entscheiden, welche Bedingungen in der Ausgabe aktiviert werden sollen:
Siehe Abschnitt **Verwenden von** in [Seite 249 des Benutzerhandbuchs](https://helpx.adobe.com/content/dam/help/en/xml-documentation-solution/4-2/Adobe-Experience-Manager-Guides_User-Guide_EN.pdf)
