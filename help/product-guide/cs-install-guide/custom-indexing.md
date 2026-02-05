---
title: Benutzerdefinierte Indizierungsbereitstellung
description: Erfahren Sie, wie Sie benutzerdefinierten Inhalt indizieren
feature: Web Editor Configuration
role: Admin
level: Experienced
source-git-commit: 9a4f0391c464d69ea65ecfdaac6ecdcb17d1a3da
workflow-type: tm+mt
source-wordcount: '425'
ht-degree: 3%

---

# Bereitstellen eines benutzerdefinierten Index für die Funktion Suchen und Ersetzen (Source-Ansicht)

## Übersicht

Dieses Handbuch enthält Schritt-für-Schritt-Anweisungen für die Bereitstellung des `guidesAssetLucene‑1‑custom‑1` benutzerdefinierten Index auf Adobe Experience Manager (AEM) as a Cloud Service. Während die standardmäßige Funktion zum Suchen und Ersetzen in der Autorenansicht ohne diesen Index funktioniert, ist der benutzerdefinierte Index speziell erforderlich, um Suchen und Ersetzen in der Source-Ansicht zu aktivieren. Mit der Ansicht „Suchen und Ersetzen“ (Source-Ansicht) können Sie nicht nur den sichtbaren erstellten Inhalt durchsuchen, sondern auch die zugrunde liegende XML-Struktur, einschließlich Elemente, Tags und Attributwerte.

## Voraussetzungen

Bevor Sie mit der Indexbereitstellung fortfahren, stellen Sie Folgendes sicher:

- **AEM as a Cloud Service-Umgebung** mit installiertem AEM Guides
- **Zugriff auf die Code-Basis Ihres Projekts** (Git-Repository)
- **Cloud Manager-Zugriff** mit Bereitstellungsberechtigungen

## Indexdefinition

Um die Funktion zum Suchen und Ersetzen (Source-Ansicht) zu aktivieren, müssen Sie einen benutzerdefinierten Index mit dem Namen **`guidesAssetLucene-1-custom-1`** in Ihrer AEM Cloud Service-Umgebung bereitstellen.

### Indexname

```
guidesAssetLucene-1-custom-1
```

### Indexdefinition (.content.xml)

Erstellen Sie die folgende Indexdefinition in Ihrem Projekt unter:

`ui.apps/src/main/content/jcr_root/_oak_index/guidesAssetLucene-1-custom-1/.content.xml`

```xml
<?xml version="1.0" encoding="UTF-8"?>
<jcr:root xmlns:jcr="http://www.jcp.org/jcr/1.0" xmlns:dam="http://www.day.com/dam/1.0"
          xmlns:nt="http://www.jcp.org/jcr/nt/1.0" xmlns:oak="http://jackrabbit.apache.org/oak/ns/1.0"
          xmlns:rep="internal"
          jcr:mixinTypes="[rep:AccessControllable]"
          jcr:primaryType="oak:QueryIndexDefinition"
          async="[async,nrt]"
          compatVersion="{Long}2"
          evaluatePathRestrictions="{Boolean}true"
          includedPaths="[/content/dam]"
          selectionPolicy="tag"
          tags="[ditaSearch]"
          type="lucene">

    <aggregates jcr:primaryType="nt:unstructured">
        <dam:Asset jcr:primaryType="nt:unstructured">
            <include0
                    jcr:primaryType="nt:unstructured"
                    path="jcr:content/renditions/original/jcr:content"
                    relativeNode="{Boolean}true"/>
        </dam:Asset>
    </aggregates>

    <analyzers jcr:primaryType="nt:unstructured">
        <default jcr:primaryType="nt:unstructured">
            <tokenizer
                    jcr:primaryType="nt:unstructured"
                    name="Whitespace"/>
        </default>
    </analyzers>

    <indexRules jcr:primaryType="nt:unstructured">
        <dam:Asset
                jcr:primaryType="nt:unstructured"
                indexNodeName="{Boolean}true">
            <properties jcr:primaryType="nt:unstructured">
                <cqTags
                        jcr:primaryType="nt:unstructured"
                        name="jcr:content/metadata/cq:tags"
                        nodeScopeIndex="{Boolean}true"
                        propertyIndex="{Boolean}true"
                        useInSpellcheck="{Boolean}true"
                        useInSuggest="{Boolean}true"/>
                <jcrLastModified
                        jcr:primaryType="nt:unstructured"
                        name="jcr:content/jcr:lastModified"
                        ordered="{Boolean}true"
                        propertyIndex="{Boolean}true"
                        type="Date"/>
                <jcrCreated
                        jcr:primaryType="nt:unstructured"
                        name="jcr:created"
                        ordered="{Boolean}true"
                        propertyIndex="{Boolean}true"
                        type="Date"/>
                <guidesParentMaps
                        jcr:primaryType="nt:unstructured"
                        name="jcr:content/guidesParentMaps"
                        propertyIndex="{Boolean}true"/>
                <guidesDirectParentMaps
                        jcr:primaryType="nt:unstructured"
                        name="jcr:content/guidesDirectParentMaps"
                        propertyIndex="{Boolean}true"/>
                <ditaClass
                        jcr:primaryType="nt:unstructured"
                        name="jcr:content/metadata/dita_class"
                        propertyIndex="{Boolean}true"/>
                <nodeNameLowerCase
                        jcr:primaryType="nt:unstructured"
                        function="fn:lower-case(fn:name())"
                        ordered="{Boolean}true"
                        propertyIndex="{Boolean}true"/>
                <cqDriveLock
                        jcr:primaryType="nt:unstructured"
                        name="jcr:content/cq:driveLock"
                        propertyIndex="{Boolean}true"
                        ordered="{Boolean}true"/>
                <docState
                        jcr:primaryType="nt:unstructured"
                        name="jcr:content/metadata/docstate"
                        propertyIndex="{Boolean}true"
                        ordered="{Boolean}true"/>
                <jcrPath
                        jcr:primaryType="nt:unstructured"
                        function="fn:path()"
                        ordered="{Boolean}true"/>
                <dcTitleLowerCase
                        jcr:primaryType="nt:unstructured"
                        function="fn:lower-case(jcr:first(jcr:content/metadata/@dc:title))"
                        propertyIndex="{Boolean}true"
                        ordered="{Boolean}true"/>
                <dcTitle
                        jcr:primaryType="nt:unstructured"
                        name="jcr:content/metadata/dc:title"
                        propertyIndex="{Boolean}true"/>
            </properties>
        </dam:Asset>
    </indexRules>

    <tika jcr:primaryType="nt:unstructured">
        <mimeTypes jcr:primaryType="nt:unstructured">
            <application jcr:primaryType="nt:unstructured">
                <xml
                        jcr:primaryType="nt:unstructured"
                        mappedType="application/dita+xml"/>
            </application>
            <text jcr:primaryType="nt:unstructured">
                <markdown
                        jcr:primaryType="nt:unstructured"
                        mappedType="text/markdown+source"/>
            </text>
        </mimeTypes>
    </tika>
</jcr:root>
```

## Bereitstellungsschritte

Detaillierte Anweisungen zum Bereitstellen benutzerdefinierter Indizes in AEM as a Cloud Service finden Sie unter [Inhaltssuche und -indizierung - AEM as a Cloud Service](https://experienceleague.adobe.com/de/docs/experience-manager-cloud-service/content/operations/indexing).

### Wichtige Punkte für diesen Index

Verwenden Sie beim Befolgen des Bereitstellungshandbuchs die folgenden Spezifikationen für den Index „Suchen und Ersetzen“:

- **Indexname**: `guidesAssetLucene-1-custom-1`
- **Indextyp**: Vollständig benutzerdefinierter Index (keine Anpassung des vorkonfigurierten Index)
- **Standort**: `ui.apps/src/main/content/jcr_root/_oak_index/guidesAssetLucene-1-custom-1/.content.xml`
- **Paketeigenschaften erforderlich**:
   - `noIntermediateSaves=true`
   - `allowIndexDefinitions=true`

## Neuindizierung

Die Neuindizierung wird **automatisch** von AEM as a Cloud Service vorgenommen, wenn Sie den Index über die CI/CD-Pipeline von Cloud Manager bereitstellen.

Die Indizierung wird in der Regel automatisch durchgeführt. Wenn die alten Daten jedoch auch nach der ordnungsgemäßen Bereitstellung und dem Abschluss des Indizierungsprozesses nicht durchsuchbar sind, sollte einmal eine manuelle Neuindizierung des Index durchgeführt werden.

### Was zu erwarten ist

- Der Indizierungsauftrag wird nach der Bereitstellung automatisch gestartet.
- Sie können den Fortschritt auf der Seite Cloud Manager-Build überwachen.
- Die Umgebung bleibt während der Indizierung voll funktionsfähig.

## Überprüfung

Überprüfen Sie nach Abschluss der Bereitstellung und Indizierung, ob der Index ordnungsgemäß funktioniert.

### Überprüfen der Indexbereitstellung

In Ihrer Entwicklungsumgebung (sofern CRXDE Lite verfügbar ist):

1. Navigieren Sie zu `/oak:index/guidesAssetLucene-1-custom-1`.
2. Überprüfen Sie, ob der Knoten mit der erwarteten Konfiguration vorhanden ist.

### Testen der Funktion „Suchen und Ersetzen“

Die primäre Verifizierung besteht darin, die Funktion zu testen:

1. Öffnen Sie AEM Guides.
2. Navigieren Sie zu **Tools** > **Handbücher** > **Suchen und Ersetzen im Repository**.
3. Konfigurieren Sie eine Suche nach Text in Ihren DITA- oder Markdown-Dateien.
4. Stellen Sie sicher, dass Suchergebnisse korrekt zurückgegeben werden.
5. Testen der Ersetzungsfunktion in einer Testdatei.

## Zusätzliche Ressourcen

- [AEM as a Cloud Service-Indizierungsdokumentation](https://experienceleague.adobe.com/de/docs/experience-manager-cloud-service/content/operations/indexing)
- [Apache Jackrabbit Oak-Indizierungshandbuch](https://jackrabbit.apache.org/oak/docs/query/indexing.html)
- [Dokumentation zu AEM Guides](https://experienceleague.adobe.com/en/docs/experience-manager-guides)
- [Dokumentation für Cloud Manager](https://experienceleague.adobe.com/en/docs/experience-manager-cloud-manager)
