---
title: Überlagern der HTML-Tags in der nicht veralteten AEM Sites-Ausgabe
description: Konfigurieren Sie die Video- und Bildeinstellungen für die AEM Sites-Ausgabe basierend auf der Zuordnung der Kernkomponenten.
feature: Installation
role: Admin
level: Experienced
exl-id: 726420e0-fe52-4334-b72a-8eb8bcae4d6c
TQID: https://experienceleague.adobe.com/wWeg9MdnMPXIIQWSjrr5oiQKIqEroCHZY6Oph0wAQ38
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2:
  - id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: d095671a-1355-40aa-8b5f-06c33c68080b
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 168
ht-degree: 0%

---

# Überlagern von HTML-Tags in der AEM Sites-Ausgabe

Sie können HTML-Tags in der AEM Sites-Ausgabe hinzufügen und anpassen, die mithilfe der AEM Sites-Vorgabe generiert wurde, die auf der Zuordnung von Kernkomponenten aus dem Web-Editor basiert. Um die HTML-Tags anzupassen, können Sie die `config.xml`-Datei überlagern. Sie können beispielsweise die Video- und Imagemaps in der AEM Sites-Ausgabe konfigurieren.

Führen Sie die folgenden Schritte aus, um die `config.xml`-Datei zu überlagern und zu aktualisieren:

1. Melden Sie sich bei AEM an und öffnen Sie den CRXDE Lite-Modus.

1. Navigieren Sie zu der Konfigurationsdatei, die am folgenden Speicherort verfügbar ist:

   `/libs/cq/xssprotection/config.xml`

1. Erstellen Sie einen Überlagerungsknoten des `xssprotection` Ordners im Apps-Knoten.

1. Navigieren Sie zu der Konfigurationsdatei, die im Knoten `apps` verfügbar ist:

   `/apps/fmdita/config/config.xml`

1. Aktualisieren Sie die folgenden Tags für die Videos und Bilder. Speichern Sie dann die Datei.

Videos:

```XML
    <tag name="video" action="validate">
    <attribute name="src">
      <regexp-list>
        <regexp name="anything"/>
      </regexp-list>
    </attribute>
    <attribute name="width">
       <regexp-list>
           <regexp name="anything"/>
       </regexp-list>
    </attribute>
    <attribute name="height">
       <regexp-list>
          <regexp name="anything"/>
       </regexp-list>
     </attribute>
     <attribute name="data">
       <regexp-list>
         <regexp name="anything"/>
       </regexp-list>
    </attribute>
    <attribute name="class">
       <regexp-list>
           <regexp name="anything"/>
       </regexp-list>
    </attribute>
    <attribute name="poster">
      <regexp-list>
        <regexp name="anything"/>
        </regexp-list>
    </attribute>
    <attribute name="controls">
        <regexp-list>
            <regexp name="anything"/>
        </regexp-list>
    </attribute>
    </tag>
    <tag name="source" action="validate">
      <attribute name="src">
        <regexp-list>
           <regexp name="anything"/>
        </regexp-list>
      </attribute>
    </tag>
```

Imagemaps:

```XML
        <tag name="map" action="validate">
    <attribute    name="name">
        <regexp-list>
            <regexp name="anything"/>
        </regexp-list>
    </attribute>
    </tag>
    <!-- Image & image related tags -->
    <tag name="img" action="validate">
    <attribute name="src" onInvalid="removeTag">
        <regexp-list>
            <regexp name="onsiteURL"/>
            <regexp name="offsiteURL"/>
        </regexp-list>
    </attribute>
    <attribute name="name"/>
    <attribute name="alt"/>
    <attribute name="height"/>
    <attribute name="width"/>
    <attribute name="border"/>
    <attribute name="align"/>
    <attribute name="usemap">
        <regexp-list>
            <regexp name="anything"/>
        </regexp-list>
    </attribute>
    <attribute name="hspace">
        <regexp-list>
            <regexp name="number"/>
        </regexp-list>
    </attribute>
    <attribute name="vspace">
        <regexp-list>
            <regexp name="number"/>
        </regexp-list>
    </attribute>
    </tag>
    <tag name="area" action="validate">
    <attribute name="shape">
        <regexp-list>
            <regexp name="anything"/>
        </regexp-list>
    </attribute>
    <attribute name="coords">
        <regexp-list>
            <regexp name="anything"/>
        </regexp-list>
    </attribute>
    <attribute name="href">
        <regexp-list>
            <regexp name="anything"/>
        </regexp-list>
    </attribute>
   </tag>
```




Erfahren Sie mehr über die Best Practices für [Sicherheit](https://experienceleague.adobe.com/de/docs/experience-manager-65/content/implementing/developing/introduction/security).
