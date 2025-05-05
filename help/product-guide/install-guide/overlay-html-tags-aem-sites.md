---
title: Überlagern der HTML-Tags in der nicht veralteten AEM Sites-Ausgabe
description: Konfigurieren Sie die Video- und Bildeinstellungen für die AEM Sites-Ausgabe basierend auf der Zuordnung der Kernkomponenten.
feature: Installation
role: Admin
level: Experienced
exl-id: 726420e0-fe52-4334-b72a-8eb8bcae4d6c
source-git-commit: 682eaf6f4a3a158f49a8f2ea91ce9cd2de3ff772
workflow-type: tm+mt
source-wordcount: '156'
ht-degree: 0%

---

# Überlagern von HTML-Tags in der AEM Sites-Ausgabe

Sie können mithilfe der AEM Sites-Voreinstellung generierte HTML-Tags in der AEM Sites-Ausgabe hinzufügen und anpassen, die auf der Zuordnung der Kernkomponenten aus dem Web-Editor basieren. Um die HTML-Tags anzupassen, können Sie die `config.xml`-Datei überlagern. Sie können beispielsweise die Video- und Imagemaps in der AEM Sites-Ausgabe konfigurieren.

Führen Sie die folgenden Schritte aus, um die `config.xml`-Datei zu überlagern und zu aktualisieren:

1. Melden Sie sich bei AEM an und öffnen Sie den CRXDE Lite-Modus.

1. Navigieren Sie zu der Konfigurationsdatei, die am folgenden Speicherort verfügbar ist:

   `/libs/fmdita/cq/xssprotection/config.xml`

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
