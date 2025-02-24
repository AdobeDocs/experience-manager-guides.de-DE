---
title: Einführung
description: Einführung in das API-Referenzhandbuch für AEM Guides
exl-id: d8ee9cf7-1d67-4b4a-aa80-64e893a99463
feature: API Introduction
role: Developer
level: Experienced
source-git-commit: 00a926e82f7d848e0c8041de758f20e79758b01b
workflow-type: tm+mt
source-wordcount: '760'
ht-degree: 0%

---

# Einführung {#id1761C0007W7}

Adobe Experience Manager Guides \(später als *AEM Guides*\ bezeichnet) ist eine End-to-End-Unternehmenslösung, mit der Adobe Experience Manager \(AEM\) über Funktionen der Komponenten-Content-Management-Lösung \(CCMS\) für die DITA-basierte Inhaltserstellung und -bereitstellung verfügen kann. Kunden können über die AEM Guides-APIs programmgesteuert auf AEM Guides-Workflows zugreifen, um sie in andere Unternehmensanwendungen zu integrieren. Diese APIs können auch von Adobe-Partnern verwendet werden, um das Wertversprechen von AEM Guides durch Erweitern der Funktionalität oder Integration in andere Programme oder Services zu verbessern.

## AEM Guides-APIs

Die AEM Guides-APIs sind in zwei Formaten verfügbar: HTTP und Java. Diese APIs stellen Anwendungsentwicklern Schlüsselfunktionen von AEM Guides zur Verfügung. Mithilfe dieser Funktionen können Entwickler ihre eigenen Plug-ins erstellen, um die vordefinierten Workflows zu erweitern. Die APIs sind für die Verwaltung von Ausgaben für DITA-Inhalte, die Arbeit mit DITA-Zuordnungen, das Hinzufügen bedingter Attribute zu Profilen auf Ordnerebene und das Konvertieren von HTML- und Word-Dokumenten in das DITA-Format verfügbar.

## Installieren der JARs auf Ihrem lokalen Apache Maven-Repository {#install-jar-local}

Um die von AEM Guides bereitgestellten JAR-Dateien verwenden zu können, müssen Sie sie in Ihrem lokalen Apache Maven-Repository installieren. Führen Sie die folgenden Schritte aus, um die JARs in Ihrem Maven-Repository zu installieren:

1. Extrahieren Sie den Inhalt der AEM Guides-Paketdatei \(.zip\) auf Ihrem lokalen System.

2. Wechseln Sie in der Eingabeaufforderung zum folgenden Ordner im Pfad des extrahierten Inhalts:

   ```
   \jcr_root\libs\fmdita\osgi-bundles\install
   ```

3. Führen Sie den folgenden Befehl aus, um das API-Bundle in Ihrem lokalen Maven-Repository zu installieren:

   ```
   mvn install:install-file -Dfile=api-X.x.jar -DgroupId=com.adobe.fmdita -DartifactId=api -Dversion=X.x -Dpackaging=jar**
   ```

   >[!NOTE]
   >
   > Im obigen Befehl sollte X.x durch die tatsächliche Versionsnummer in den Parametern dfile und dversion ersetzt werden.

4. \(*Optional*\) Installieren Sie die Abhängigkeit im Repository Ihres lokalen Maven-Projekts. Sie können dies erreichen, indem Sie einen Ordner in Ihrem Maven-Projekt erstellen und dann den im vorherigen Schritt angegebenen `mvn install`-Befehl mit dem folgenden zusätzlichen Parameter ausführen:

   ```
   -DlocalRepositoryPath=<path_to_project_repository>
   ```

   Um anschließend den lokalen Repository-Ordner des Projekts für den Maven-Build-Prozess verfügbar zu machen, fügen Sie der übergeordneten pom.xml-Datei ein `repository`-Element hinzu, wie unten dargestellt:

   ```XML
   <repositories>
      <repository>
         <id>project-repository</id>
         <url>file://${project.basedir}/repository</url>
      </repository>
   </repositories>
   ```


Durch diesen Prozess werden die API-JARs im lokalen Maven-Repository installiert.

## Verwenden der Service-API-JAR-Datei in einem Maven-Projekt

Nachdem Sie die API-JARs in Ihrem lokalen Maven-Repository installiert haben, führen Sie die folgenden Schritte aus, um die JAR-Datei in Ihren Projekten zu verwenden:

1. Fügen Sie die JAR-Datei zu Ihrer Code-Basis hinzu und übertragen Sie sie in das Code-Basis-Repository in einem Ordner, z. B. „dependencies“. Beachten Sie, dass der Ordnername von Ihrer Code-Basis-Hierarchie abhängt.

2. Konfigurieren Sie die pom.xml-Dateien des Projekts wie folgt:

   Die Datei „pom.xml“ des übergeordneten Projekts:

   >[!IMPORTANT]
   >
   > Im folgenden Code-Snippet sollte X.x durch die tatsächliche Versionsnummer und den Dateinamen der API-JAR ersetzt werden. Diese Informationen entsprechen denen, die in Schritt 3 des [Installationsprozesses“ angegeben ](#install-jar-local).

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

   Datei „pom.xml“ des untergeordneten Moduls:

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


## Konfigurieren und Verwenden der Service-API-JAR-Datei aus dem öffentlichen Maven-Repository

Führen Sie die folgenden Schritte aus, um die Service-API-JARs aus dem öffentlichen Maven-Repository in Ihren Projekten zu konfigurieren und zu verwenden:

1. Um die Service-API-JAR in einem Projekt zu verwenden, konfigurieren Sie das öffentliche AEM Guides-Maven-Repository in Ihrer pom.xml-Datei.
2. Konfigurieren Sie das öffentliche Maven-Repository in der Datei settings.xml von Maven wie folgt:

   ```XML
   <repository>
      <id>fmdita-public</id>
      <name>fmdita-public</name>
      <url>https://repo.aem-guides.com/repository/fmdita-public</url>
   </repository>
   ```

3. Fügen Sie nach dem Einrichten des Repositorys die Service-API-JAR-Datei als Projektabhängigkeit in der Datei „pom.xml“ des Projekts hinzu.

   >[!NOTE]
   >
   > Verwenden Sie dieselbe Version der API-JAR-Datei wie das AEM Guides-Paket, das Sie auf dem Server installiert haben.

4. Konfigurieren Sie die Maven-Abhängigkeit wie unten gezeigt:

   ```XML
   <dependency>
      <groupId>com.adobe.fmdita</groupId>
      <artifactId>api</artifactId>
      <version>4.0</version>
   </dependency>
   ```


Sobald die Dienst-API-JAR-Datei als Projektabhängigkeit in der Datei „pom.xml“ des Projekts hinzugefügt wurde, können Sie AEM Guides Java-APIs in Ihrem Projekt erstellen und verwenden.

## Verwenden der API JAR aus dem Maven Central Repository für AEM Guides as a Cloud Service

Für AEM Guides as a Cloud Service wurde die API-JAR-Datei in Maven Central bereitgestellt. Sie können die API-JAR-Datei ohne Setup verwenden.

>[!NOTE]
>
> Die Namenskonvention der API-JAR-Datei wurde gemäß der Namenskonvention für Cloud-Add-ons aktualisiert.

Um die API-JAR-Datei zu verwenden, müssen Sie der pom.xml Ihres Projekts die Abhängigkeit hinzufügen, wie unten dargestellt:

```XML
<dependency>
   <groupId>com.adobe.aem</groupId>
   <artifactId>aem-dox-sdk-api</artifactId>
   <version>${RELEASE}</version>
</dependency>
```

>[!NOTE]
>
> Da die Pakete in der API-JAR weiterhin identisch sind, ist keine Code-Änderung erforderlich, um diese API-JAR in den vorhandenen Cloud-Projekten zu verwenden.

### Java-basierte APIs

Sie können die in Experience Manager Guides verfügbaren Java-basierten APIs verwenden, um benutzerdefinierte Plug-ins zu erstellen und vordefinierte Workflows zu erweitern. In [![javadoc](https://javadoc.io/badge2/com.adobe.aem/aem-guides-sdk-api/javadoc.svg)](https://javadoc.io/doc/com.adobe.aem/aem-guides-sdk-api) finden Sie die neueste und detaillierte Dokumentation zur Verwendung der Java-basierten API.



## Zusätzliche Ressourcen

Im Folgenden finden Sie eine Liste weiterer hilfreicher Ressourcen von AEM Guides, die auf der Seite [Lernen und Support](https://helpx.adobe.com/support/xml-documentation-for-experience-manager.html) verfügbar sind:

- Benutzerhandbuch
- Installations- und Konfigurationshandbuch
- Schnellstartanleitung
- [Hilfe-Archivierungsseite](https://helpx.adobe.com/xml-documentation-for-experience-manager/archive.html) \(Zugriff auf die ältere Versionsdokumentation\)
