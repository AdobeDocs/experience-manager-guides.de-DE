---
title: Einführung
description: Einführung in das API-Referenzhandbuch für AEM Guides
exl-id: d8ee9cf7-1d67-4b4a-aa80-64e893a99463
feature: API Introduction
role: Developer
level: Experienced
source-git-commit: 6e23f52fc9124d0f07f8108da1b5fe574f553469
workflow-type: tm+mt
source-wordcount: '594'
ht-degree: 1%

---

# Einführung {#id1761C0007W7}

Adobe Experience Manager Guides \(später als *AEM Guides*\ bezeichnet) ist eine End-to-End-Unternehmenslösung, mit der Adobe Experience Manager \(AEM\) über Funktionen der Komponenten-Content-Management-Lösung \(CCMS\) für die DITA-basierte Inhaltserstellung und -bereitstellung verfügen kann. Kunden können über die AEM Guides-APIs programmgesteuert auf AEM Guides-Workflows zugreifen, um sie in andere Unternehmensanwendungen zu integrieren. Diese APIs können auch von Adobe-Partnern verwendet werden, um das Wertversprechen von AEM Guides durch Erweitern der Funktionalität oder Integration in andere Programme oder Services zu verbessern.

## AEM Guides-APIs

Die AEM Guides-APIs sind in zwei Formaten verfügbar:

- [Java-basierte APIs](#java-based-apis)
- [REST-basierte APIs](#rest-based-apis)

Diese APIs stellen Anwendungsentwicklern Schlüsselfunktionen von AEM Guides zur Verfügung. Mithilfe dieser Funktionen können Entwickler ihre eigenen Plug-ins erstellen, um die vordefinierten Workflows zu erweitern. Die APIs sind für die Verwaltung von Ausgaben für DITA-Inhalte, die Arbeit mit DITA-Zuordnungen, das Hinzufügen bedingter Attribute zu Profilen auf Ordnerebene und das Konvertieren von HTML- und Word-Dokumenten in das DITA-Format verfügbar.


### Java-basierte APIs

Sie können die in Experience Manager Guides verfügbaren Java-basierten APIs verwenden, um benutzerdefinierte Plug-ins zu erstellen und vordefinierte Workflows zu erweitern.

**Konfigurieren von SDK über das Maven Central Repository für AEM Guides as a Cloud Service**

>[!INFO]
>
>In [![javadoc](./images/javadoc-cs-icon.svg)](https://javadoc.io/doc/com.adobe.aem/aem-dox-sdk-api/latest/index.html) finden Sie die neueste und detaillierte Dokumentation zur Verwendung der Java-basierten API für Experience Manager Guides as a Cloud Service.

Um die Service-API-JARs aus dem Maven-Repository in Ihren Projekten zu konfigurieren und zu verwenden, fügen Sie die API-SDK als Projektabhängigkeit in der `pom.xml` Ihres Projekts hinzu, wie unten dargestellt.

```XML
<dependency>
<groupId>com.adobe.aem</groupId>
<artifactId>aem-dox-sdk-api</artifactId>
<version>${RELEASE}</version>
</dependency>
```

>[!NOTE]
>
> Stellen Sie sicher, dass Sie dieselbe Version der API-JAR-Datei verwenden wie das auf Ihrem Server installierte AEM Guides-Paket.

**Konfigurieren und Verwenden der API-JAR-Datei aus dem Maven Central Repository (On-Premise)**

>[!INFO]
>
>In [![javadoc](https://javadoc.io/badge2/com.adobe.aem/aem-guides-sdk-api/javadoc.svg)](https://javadoc.io/doc/com.adobe.aem/aem-guides-sdk-api/latest/index.html) finden Sie die neueste und detaillierte Dokumentation zur Verwendung der Java-basierten API für die On-Premise-Einrichtung von Experience Manager Guides.

Um die Service-API-JARs für On-Premise-Bereitstellungen zu konfigurieren und zu verwenden, fügen Sie die Service-API-JAR-Datei wie unten dargestellt als Projektabhängigkeit in die `pom.xml` Ihres Projekts ein:

```XML
<dependency>
<groupId>com.adobe.aem</groupId>
<artifactId>aem-guides-sdk-api</artifactId>
<version>${RELEASE}</version>
</dependency>
```

>[!NOTE]
>
> Stellen Sie sicher, dass Sie dieselbe Version der API-JAR-Datei verwenden wie das auf Ihrem Server installierte AEM Guides-Paket.


**Konfigurieren und Verwenden der API-JAR-Datei aus dem öffentlichen AEM Guides-Maven-Repository (On-Premise)**

>[!NOTE]
>
> Das öffentliche AEM Guides Maven-Repository wird nach der Version 5.3.0 von Experience Manager Guides nicht mehr unterstützt. Die API-JAR-Datei ist danach nur noch im zentralen Maven-Repository verfügbar.

Führen Sie die folgenden Schritte aus, um die Service-API-JARs aus dem öffentlichen Maven-Repository zu verwenden:

1. Konfigurieren Sie das öffentliche AEM Guides-Maven-Repository in Ihrer `pom.xml`- oder `settings.xml` wie unten dargestellt:

   ```XML
   <repository>
       <id>fmdita-public</id>
       <name>fmdita-public</name>
       <url>https://repo.aem-guides.com/repository/fmdita-public</url>
    </repository>
   ```

1. Fügen Sie nach dem Einrichten des Repositorys die Service-API-JAR-Datei als Projektabhängigkeit in die `pom.xml` des Projekts ein.

   ```XML
   <dependency>
       <groupId>com.adobe.fmdita</groupId>
       <artifactId>api</artifactId>
       <version>${RELEASE}</version>
   </dependency>
   ```

   >[!NOTE]
   >
   > Verwenden Sie dieselbe Version der API-JAR-Datei wie das AEM Guides-Paket, das Sie auf dem Server installiert haben.

Sobald die Dienst-API-JAR-Datei als Projektabhängigkeit zur `pom.xml` des Projekts hinzugefügt wurde, können Sie AEM Guides-Java-APIs in Ihrem Projekt erstellen und verwenden.


### REST-basierte APIs

Experience Manager Guides bietet einen umfassenden Satz an REST-basierten APIs, mit denen Entwickler über HTTP auf Kernfunktionen zugreifen und mit ihnen interagieren können.

Diese APIs eignen sich ideal für:

- Integrieren von Experience Manager Guides mit anderen Unternehmenssystemen
- Automatisieren von Veröffentlichungs- und Überprüfungs-Workflows
- Erstellen benutzerdefinierter Programme und Erweiterungen

Ausführliche Informationen zur API-Nutzung, zu Parametern und Beispielanfragen finden Sie in den entsprechenden Themen im Abschnitt **API-Referenz** der Dokumentation zu Experience Manager Guides.

## Zusätzliche Ressourcen

Im Folgenden finden Sie eine Liste weiterer hilfreicher Ressourcen von AEM Guides, die auf der Seite [Lernen und Support](https://helpx.adobe.com/de/support/xml-documentation-for-experience-manager.html) verfügbar sind:

- Benutzerhandbuch
- Installations- und Konfigurationshandbuch
- Schnellstartanleitung
- [Hilfe-Archivierungsseite](https://helpx.adobe.com/de/xml-documentation-for-experience-manager/archive.html) \(Zugriff auf die ältere Versionsdokumentation\)
