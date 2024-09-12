---
title: Einführung
description: Einführung in das API-Referenzhandbuch für AEM Guides
exl-id: d8ee9cf7-1d67-4b4a-aa80-64e893a99463
feature: API Introduction
role: Developer
level: Experienced
source-git-commit: 9024b552fd470344ba7b0068a147c37084ae0d13
workflow-type: tm+mt
source-wordcount: '760'
ht-degree: 0%

---

# Einführung {#id1761C0007W7}

Adobe Experience Manager Guides \(später als *AEM Guides*\) ist eine End-to-End-Unternehmenslösung, mit der Adobe Experience Manager \(AEM\) über Funktionen zur Komponenteninhaltsverwaltung \(CCMS\) für die DITA-basierte Inhaltserstellung und -bereitstellung verfügen kann. Kunden können über die AEM Guides-APIs programmgesteuert auf AEM Guides-Workflows zugreifen, um sie in andere Unternehmensanwendungen zu integrieren. Diese APIs können auch von Adobe-Partnern verwendet werden, um das Wertversprechen von AEM Guides zu verbessern, indem deren Funktionalität erweitert oder in andere Anwendungen oder Dienste integriert wird.

## AEM Guides-APIs

Die AEM Guides-APIs sind in zwei Formaten verfügbar: HTTP und Java. Diese APIs stellen Anwendungsentwicklern wichtige Funktionen von AEM Guides zur Verfügung. Mit diesen Funktionen können Entwickler eigene Plug-ins erstellen, um die vordefinierten Workflows zu erweitern. Die APIs stehen zur Verwaltung von Ausgaben für DITA-Inhalte, zum Arbeiten mit DITA-Maps, zum Hinzufügen bedingter Attribute zu Profilen auf Ordnerebene und zum Konvertieren von HTML- und Words-Dokumenten in das DITA-Format zur Verfügung.

## Installieren der JARs auf Ihrem lokalen Apache Maven-Repository {#install-jar-local}

Um die von AEM Guides bereitgestellten JAR-Dateien verwenden zu können, müssen Sie sie in Ihrem lokalen Apache Maven-Repository installieren. Führen Sie die folgenden Schritte aus, um die JARs auf Ihrem Maven-Repository zu installieren:

1. Extrahieren Sie den Inhalt der AEM Guides-Paketdatei \(.zip\) auf Ihrem lokalen System.

2. Navigieren Sie in der Eingabeaufforderung zum folgenden Ordner im Pfad des extrahierten Inhalts:

   ```
   \jcr_root\libs\fmdita\osgi-bundles\install
   ```

3. Führen Sie den folgenden Befehl aus, um das API-Bundle in Ihrem lokalen Maven-Repository zu installieren:

   ```
   mvn install:install-file -Dfile=api-X.x.jar -DgroupId=com.adobe.fmdita -DartifactId=api -Dversion=X.x -Dpackaging=jar**
   ```

   >[!NOTE]
   >
   > Im obigen Befehl sollte X.x durch die tatsächliche Versionsnummer in den Dfile - und Dversion -Parametern ersetzt werden.

4. \(*Optional*\) Installieren Sie die Abhängigkeit im Repository Ihres lokalen Maven-Projekts. Sie können dies erreichen, indem Sie einen Ordner in Ihrem Maven-Projekt erstellen und dann den im vorherigen Schritt angegebenen Befehl `mvn install` mit dem folgenden zusätzlichen Parameter ausführen:

   ```
   -DlocalRepositoryPath=<path_to_project_repository>
   ```

   Um anschließend den lokalen Repository-Ordner des Projekts für den Maven-Build-Prozess verfügbar zu machen, fügen Sie ein `repository` -Element in die übergeordnete pom.xml-Datei hinzu, wie unten dargestellt:

   ```XML
   <repositories>
      <repository>
         <id>project-repository</id>
         <url>file://${project.basedir}/repository</url>
      </repository>
   </repositories>
   ```


Durch diesen Prozess werden die API-JARs im lokalen Maven-Repository installiert.

## Verwenden der Dienst-API-JAR-Datei in einem Maven-Projekt

Führen Sie nach der Installation der API-JARs in Ihrem lokalen Maven-Repository die folgenden Schritte aus, um die JAR-Datei in Ihren Projekten zu verwenden:

1. Fügen Sie die JAR-Datei zu Ihrer Codebasis hinzu und übertragen Sie sie in das Code-Basis-Repository unter einem Ordner, z. B. &quot;Abhängigkeiten&quot;. Beachten Sie, dass der Ordnername von Ihrer Code-Basis-Hierarchie abhängt.

2. Konfigurieren Sie die Projektdateien &quot;pom.xml&quot;wie folgt:

   Datei &quot;pom.xml&quot;des übergeordneten Projekts:

   >[!IMPORTANT]
   >
   > Im folgenden Codefragment sollte X.x durch die tatsächliche Versionsnummer und den Dateinamen der API-JAR-Datei ersetzt werden. Diese Informationen entsprechen den Angaben in Schritt 3 des [Installationsprozesses](#install-jar-local).

   ```XML
   <plugin>
   
       <groupId>org.apache.maven.plugins</groupId>
   
      <artifactId>maven-install-plugin</artifactId>
   
       <version>2.5.2</version>
   
       <configuration>
   
               <groupId>com.adobe.fmdita</groupId>
   
               <artifactId>api</artifactId>
   
               <version>X.x</version>
   
               <file>${basedir}/dependencies/fmdita/api-X.x.jar</file>
   
               <packaging>jar</packaging>
   
               <generatePom>true</generatePom>
   
       </configuration>
   
       <executions>
   
           <execution>
   
               <id>inst_fmdita</id>
   
                   <goals>
   
                       <goal>install-file</goal>
   
                   </goals>
   
                   <phase>clean</phase>
   
           </execution>
   
       </executions>
   </plugin>
   ```

   Datei pom.xml des untergeordneten Moduls:

   ```XML
   <plugin>
      <groupId>org.apache.maven.plugins</groupId>
   
      <artifactId>maven-install-plugin</artifactId>
   
      <configuration>
   
         <groupId>com.adobe.fmdita</groupId>
   
         <artifactId>api</artifactId>
   
         <version>3.6</version>
   
         <file>${basedir}/../dependencies/fmdita/api-3.6.jar</file>
   
         <packaging>jar</packaging>
   
         <generatePom>true</generatePom>
   
      </configuration>
   
      <executions>
   
         <execution>
   
            <id>inst_fmdita</id>
   
            <goals>
   
               <goal>install-file</goal>
   
            </goals>
   
            <phase>clean</phase>
   
         </execution>
   
      </executions>
   
   </plugin>
   ```


## Dienst-API-JAR aus öffentlichem Maven-Repository konfigurieren und verwenden

Führen Sie die folgenden Schritte aus, um die Service-API-JARs aus dem öffentlichen Maven-Repository in Ihren Projekten zu konfigurieren und zu verwenden:

1. Um die Dienst-API-JAR in einem Projekt zu verwenden, konfigurieren Sie das öffentliche AEM Guides-Maven-Repository in Ihrer pom.xml-Datei.
2. Konfigurieren Sie das öffentliche Maven-Repository in der Maven-Datei settings.xml wie folgt:

   ```XML
   <repository>
      <id>fmdita-public</id>
      <name>fmdita-public</name>
      <url>https://repo.aem-guides.com/repository/fmdita-public</url>
   </repository>
   ```

3. Nachdem das Repository eingerichtet wurde, fügen Sie die JAR-Datei für die Dienst-API als Projektabhängigkeit in der Datei &quot;pom.xml&quot;des Projekts hinzu.

   >[!NOTE]
   >
   > Verwenden Sie dieselbe Version der API-JAR-Datei wie das AEM Guides-Paket, das Sie auf dem Server installiert haben.

4. Konfigurieren Sie die Maven-Abhängigkeit wie unten dargestellt:

   ```XML
   <dependency>
      <groupId>com.adobe.fmdita</groupId>
      <artifactId>api</artifactId>
      <version>4.0</version>
   </dependency>
   ```


Sobald die Service-API-JAR-Datei als Projektabhängigkeit in der Datei &quot;pom.xml&quot;des Projekts hinzugefügt wurde, können Sie AEM Guides-Java-APIs in Ihrem Projekt erstellen und verwenden.

## Verwenden von API JAR aus dem Maven Central Repository für AEM Guides as a Cloud Service

Für AEM Guides as a Cloud Service wurde die API-JAR in Maven Central bereitgestellt. Sie können die API-JAR-Datei ohne Einrichtung verwenden.

>[!NOTE]
>
> Die Namenskonvention der API-JAR-Datei wurde gemäß der Namenskonvention für Cloud-Add-ons aktualisiert.

Um die API-JAR-Datei zu verwenden, müssen Sie die Abhängigkeit zur pom.xml Ihres Projekts hinzufügen, wie unten dargestellt:

```XML
<dependency>
   <groupId>com.adobe.aem</groupId>
   <artifactId>aem-guides-sdk-api</artifactId>
   <version>2022.5</version>
</dependency>
```

>[!NOTE]
>
> Da die Pakete innerhalb der API-JAR immer noch dieselben sind, ist keine Codeänderung erforderlich, um diese API-JAR in den vorhandenen Cloud-Projekten zu verwenden.

### Java-basierte APIs

Sie können in Experience Manager Guides verfügbare Java-basierte APIs verwenden, um benutzerdefinierte Plug-ins zu erstellen und native Workflows zu erweitern. Die aktuelle und detaillierte Dokumentation zur Verwendung der Java-basierten API finden Sie unter [![javadoc](https://javadoc.io/badge2/com.adobe.aem/aem-guides-sdk-api/javadoc.svg)](https://javadoc.io/doc/com.adobe.aem/aem-guides-sdk-api) .



## Zusätzliche Ressourcen

Im Folgenden finden Sie eine Liste weiterer hilfreicher Ressourcen von AEM Guides, die auf der Seite [Lernen und Support](https://helpx.adobe.com/support/xml-documentation-for-experience-manager.html) verfügbar sind:

- Benutzerhandbuch
- Handbuch zur Installation und Konfiguration
- Schnellstartanleitung
- [Hilfe-Archivierungsseite](https://helpx.adobe.com/xml-documentation-for-experience-manager/archive.html) \(Zugriff auf die ältere Versionsdokumentation\)
