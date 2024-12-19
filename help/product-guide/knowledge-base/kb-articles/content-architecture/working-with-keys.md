---
title: Arbeiten mit Schlüsseln
description: Erstellen von Schlüsseln zur Verwendung in allen Unternehmensinhalten
role: Admin
exl-id: b8e3a6d2-ea82-4fdb-bd16-3f4b6594af52
feature: Use Keys in AEM Guides
source-git-commit: 47e6c57b8a61f02dc4f03594d91ee842bdccef90
workflow-type: tm+mt
source-wordcount: '179'
ht-degree: 0%

---

# Schlüssel erstellen

Unternehmen sollten Schlüssel in Fällen verwenden, in denen sie wiederverwendbaren und gemeinsamen Text haben, z. B. Produktname oder Produktpräsentation, der an vielen Stellen verwendet wird, aber zu Änderungen neigt. Durch die Verwendung von Schlüsseln für diesen wiederverwendbaren Text können Sie eine Aktualisierung an mehreren Stellen pushen, indem Sie die Änderung an einer einzigen Stelle vornehmen, z. B. im Schlüsselwert.

## Schritt 1: Erstellen Sie eine globale Zuordnung zum Speichern Ihrer Schlüssel

Erstellen Sie eine Zuordnung und fügen Sie das [!UICONTROL keyRef]-Element hinzu.

```
<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE map PUBLIC "-//OASIS//DTD DITA Map//EN" "technicalContent/dtd/map.dtd">
<mapid="map.ditamap_ffbdbf06-8658-4311-ad84-1c631bba904f">
  <title>global-keys-map</title>
  <keydefkeys="adobe">
    <topicmeta>
      <linktext>Adobe Systems</linktext>
    </topicmeta>
  </keydef>
  <keydefkeys="AEM">
    <topicmeta>
      <linktext>Adobe Experience Manager</linktext>
    </topicmeta>
  </keydef>
</map>
```

Hier haben Sie, wie oben gezeigt, zwei Definitionen definiert und eine [!UICONTROL keyRef] als _AEM_ für den Text _Adobe Experience Manager_ bereitgestellt.

## Schritt 2: Diese Karte zur Veröffentlichungszuordnung hinzufügen

```
<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE map PUBLIC "-//OASIS//DTD DITA Map//EN" "technicalContent/dtd/map.dtd">
<mapid="map.ditamap_cbf4a96d-e382-4e8c-8830-bcc093fe6638">
  <title>sample-map</title>
  <topicrefhref="sample-topic-using-the-keys.dita"type="topic">
  </topicref>
  <maprefformat="ditamap"href="global-keys-map.ditamap"type="map">
  </mapref>
</map>
```

## Schritt 3: Verwenden Sie die Schlüssel, um auf die in der globalen Schlüsselzuordnung definierten Variablen zu verweisen

+ Bearbeiten Sie das Thema und fügen Sie den Schlüsselwert mit der [!UICONTROL keyref] hinzu.
+ Wie im Screenshot gezeigt, wird ein kleines Fenster angezeigt, in dem Schlüsselwörter ausgewählt werden können. Dies wird angezeigt, wenn Sie das Element „keyword“ hinzufügen.
  ![Element einfügen](assets/insert_element.png)
  ![Schlüssel-REF](assets/key_ref.png)

```
<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE topic PUBLIC "-//OASIS//DTD DITA Topic//EN" "technicalContent/dtd/topic.dtd">
<topicid="topic.dita_31b00e61-04b5-4193-af7a-68503e88b087">
  <title>sample-topic-using-the-keys</title>
  <shortdesc></shortdesc>
  <body>
    <p>This is a sample topic using the keys defined in the global map</p>
    <p>here i am using the key definition for AEM :<keyword keyref="AEM"></keyword></p>
  </body>
</topic>
```
