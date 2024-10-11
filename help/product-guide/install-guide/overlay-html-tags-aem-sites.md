---
title: Überlagern Sie die HTML-Tags in der nicht älteren AEM Sites-Ausgabe.
description: Video- und Bildeinstellungen für die AEM Sites-Ausgabe basierend auf der Zuordnung der Kernkomponenten konfigurieren
feature: Installation
role: Admin
level: Experienced
source-git-commit: 8310ae8d2e2eeda0fcfba9ec50650c806263cd49
workflow-type: tm+mt
source-wordcount: '156'
ht-degree: 0%

---


# Überlagern von HTML-Tags in der AEM Sites-Ausgabe

Sie können HTML-Tags in der AEM Sites-Ausgabe hinzufügen und anpassen, die mithilfe der AEM Sites-Vorgabe basierend auf der Kernkomponenten-Zuordnung aus dem Web Editor generiert wurde. Um die HTML-Tags anzupassen, können Sie die `config.xml` -Datei überlagern. Sie können beispielsweise die Video- und Imagemaps in der AEM Sites-Ausgabe konfigurieren.

Führen Sie die folgenden Schritte aus, um die Datei `config.xml` zu überlagern und zu aktualisieren:

1. Melden Sie sich bei AEM an und öffnen Sie den CRXDE Lite-Modus.

1. Navigieren Sie zur Konfigurationsdatei, die unter folgendem Speicherort verfügbar ist:

   `/libs/fmdita/cq/xssprotection/config.xml`

1. Erstellen Sie einen Überlagerungsknoten des Ordners `xssprotection` im Anwendungsknoten.

1. Navigieren Sie zur Konfigurationsdatei, die im Knoten `apps` verfügbar ist:

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




Erfahren Sie mehr über die Best Practices für [Sicherheit](https://experienceleague.adobe.com/en/docs/experience-manager-65/content/implementing/developing/introduction/security).