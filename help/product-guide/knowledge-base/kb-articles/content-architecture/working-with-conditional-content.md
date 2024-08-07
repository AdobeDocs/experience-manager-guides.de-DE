---
title: Arbeiten mit bedingten Inhalten
description: Erfahren Sie, wie Sie Bedingungen erstellen und dann die Generierung von bedingtem Inhalt in [!DNL AEM Guides] einrichten.
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


* Autoren können Bedingungen für ein Inhaltselement festlegen, damit sie steuern können, ob es in der Ausgabe angezeigt wird.

* Autoren können bei der Veröffentlichung auswählen, ob unterschiedliche Bedingungen angezeigt oder ausgeblendet werden sollen.

* Beispielsweise können Autoren Attribute als Version 1.0 und Version 2.0 zum Inhalt hinzufügen und Bedingungen verwenden, um Version 1.0 für Version 1.0 einzubeziehen und Version 2.0 auszuschließen.

**Schritt 1**

Definieren Sie Bedingungen, die für die Dokumentation in [!UICONTROL Ordnerprofile] relevant sind:
Siehe Abschnitt **Bedingte Attribute für globale Profile oder Profile auf Ordnerebene konfigurieren** auf Seite 4}Seite 69 des Installations- und Konfigurationshandbuchs](https://helpx.adobe.com/content/dam/help/en/xml-documentation-solution/4-2/Adobe-Experience-Manager-Guides_Installation-Configuration-Guide_EN.pdf)[

![Bedingungen in Ordnerprofilen konfigurieren](assets/conditions-in-profiles.png)

**Schritt 2**

Wählen Sie das in Schritt 1 definierte **[!UICONTROL Ordnerprofil]** in den **Benutzereinstellungen** im XML-Editor aus:
Siehe Abschnitt **Benutzereinstellungen** in [Seite 41 des Benutzerhandbuchs](https://helpx.adobe.com/content/dam/help/en/xml-documentation-solution/4-2/Adobe-Experience-Manager-Guides_User-Guide_EN.pdf)


**Schritt 3**

Verwenden Sie die Bedingungen, um Abschnitte des Inhalts mit Bedingungen zu versehen:
Siehe Abschnitt **Bedingungen** in [Seite 90 des Benutzerhandbuchs](https://helpx.adobe.com/content/dam/help/en/xml-documentation-solution/4-2/Adobe-Experience-Manager-Guides_User-Guide_EN.pdf).

![Nutzungsbedingungen im Web-Editor](assets/conditions-in-web-editor.png)

**Schritt 4**

Definieren Sie Bedingungsvorgaben auf Zuordnungsebene, um zu wählen, welche Bedingungen in der Ausgabe aktiviert werden sollen:
Siehe Abschnitt **Bedingungsvorgaben verwenden** in [Seite 249 des Benutzerhandbuchs](https://helpx.adobe.com/content/dam/help/en/xml-documentation-solution/4-2/Adobe-Experience-Manager-Guides_User-Guide_EN.pdf).
