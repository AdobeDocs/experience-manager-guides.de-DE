---
title: Erstellen einer Zuordnung
description: Create a map with Map Editor in AEM Guides. Find the steps to create a map file based on a map template.
feature: Authoring, Map Editor
role: User
hide: true
exl-id: 981ecaeb-9b1f-4c7a-8336-7746a739bedc
source-git-commit: a70b3ce942b3e69445ad1d7ba6c8f7542e0ff176
workflow-type: tm+mt
source-wordcount: '472'
ht-degree: 0%

---

# Erstellen einer Zuordnung {#id176FEN0D05Z}

AEM Guides provides two out-of-the-box map templates - DITA map and Bookmap. You can also create your own map templates and share those with your authors to create map files.

Perform the following steps to create a map file:

1. In the Assets UI, navigate to the location where you want to create the map file.

1. Click **Create** \> **DITA Map**.

1. On the Blueprint page, select the type of map templates you want to use and click **Next**.

   >[!NOTE]
   >
   > The way the topics are referred in a map file depend on the map template. For example, if you select the Map template, then the topic references \(`topicref`\) are used to refer to topics. In case of a Bookmap, topic references are created using the `chapter` element in DITA.

   ![](images/map-template.png){width="650" align="left"}

1. On the Properties page, specify the map **Title**.

1. \(Optional\) Geben Sie die Datei **Name** an.

   Wenn Ihr Admin einen automatischen Dateinamen basierend auf einer UUID-Einstellung konfiguriert hat, wird die Option zum Angeben des Dateinamens nicht angezeigt. Ein UUID-basierter Dateiname wird der Datei automatisch zugewiesen.

   If the file naming option is available, then also the name is automatically suggested based on the Title of your map. If you want to manually specify the map file name, then ensure that the file name does not contain any spaces, apostrophe, or braces and ends with `.ditamap`.

1. Klicken Sie auf **Erstellen**.

   The Map Created message appears.

   Every new map file that you create from the Assets UI **Create** \> **DITA Map** or the Web Editor is assigned a unique map ID. Also, the new map is saved as the latest working copy in DAM. Until you save a revision of a newly created map, you will not see any version number in the Version History. If you open the map for editing, the version information is shown in the right top corner of the map file&#39;s tab:

   ![](images/first-version-map-none.png){width="650" align="left"}

   The version information for a newly created map is shown as *none*. Wenn Sie eine neue Version speichern, wird ihr eine Versionsnummer als 1.0 zugewiesen. Weitere Informationen zum Speichern einer neuen Version finden Sie unter [Als neue Version speichern](web-editor-features.md#save-as-new-version-id209ME400GXA).

   You can choose to open the map for editing in the configured map editor, or save the map file in the AEM repository.

   >[!NOTE]
   >
   > To use the Advanced Map Editor, access the map file in the Web Editor. In case your administrator has configured the Advanced Map Editor as the default editor in the map files, then the map file is opened directly in the Advanced Map Editor for editing. See *Set the Advanced Map Editor as default* section in Install and configure Adobe Experience Manager Guides as a Cloud Service.


**Parent topic:**&#x200B;[&#x200B; Work with the Map Editor](map-editor.md)
