---
title: Unterstützung von Schematronen im Web-Editor
description: Arbeiten mit Schematron im Web-Editor
exl-id: 3e61432f-d81e-446e-b0ad-560f5b9fa91a
feature: Web Editor
role: User, Admin
TQID: https://experienceleague.adobe.com/gF-ylj-r-PDXduhUU-60-hiJ4UaYEdsCYTaCIyUiT0s
product_v2: id: fae5e35a-80c9-4b94-9352-1a060a6aab1did: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2: id: ab01a588-7dea-43f2-a699-0b3f128465d6id: d90290ec-3e61-4ebd-8649-bcafe0836803
subfeature_v2: id: ad602516-aca3-4247-9ae8-f393d958efa9id: f89f75b0-cf2e-4e96-aec8-fe8c39cbd0ef
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: a004cc84-67b9-4a33-a3a7-8ec7273ef4dc
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 437
ht-degree: 0%

---

# Steuern der Inhaltsqualität im Web-Editor

Dieser Artikel bietet einen Überblick über die Validierungsmöglichkeiten innerhalb des AEM Guides-Web-Editors.
Der Web-Editor nutzt standardmäßig das im System eingerichtete DITA-Schema, um Benutzer dazu zu zwingen, DITA-konforme Inhalte zu erstellen. Damit sind alle im System gespeicherten Inhalte strukturierte, wiederverwendbare und gültige DITA-Inhalte.

Neben der Unterstützung für DITA-Regeln unterstützt der Web-Editor auch die Validierung von Inhalten, die auf &quot;*&quot;-* basieren.

&quot;*Schematron*&quot; bezieht sich auf eine regelbasierte Validierungssprache, die zum Definieren von Tests für eine XML-Datei verwendet wird. Sie können die Schematron-Dateien importieren und auch im Web-Editor bearbeiten. Mithilfe einer „Schematron“-Datei können Sie bestimmte Regeln definieren und diese dann für ein DITA-Thema oder eine Zuordnung validieren. Schematronregeln können die Konsistenz der XML-Struktur sicherstellen, indem sie als Regeln definierte Einschränkungen auferlegen. Diese Einschränkungen werden von KMUs gesteuert, die für die Qualität und Konsistenz der Inhalte verantwortlich sind.

HINWEIS: Der Web-Editor unterstützt ISO Schematron.


## Wissen, wie „Schematron“ im Web-Editor funktioniert

### Konfigurieren von Schematron-Regeln

Siehe Abschnitt „Unterstützung für Schematron-Dateien“ im [Benutzerhandbuch](https://helpx.adobe.com/content/dam/help/en/xml-documentation-solution/4-2/Adobe-Experience-Manager-Guides_UUID_User-Guide_EN.pdf#page=148)


### Durchsetzen von Validierungsregeln beim Speichern von Dateien

Mit den WebEditor-Einstellungen können Power-User Schematron-Regeln/-Dateien einrichten, die jedes Mal ausgeführt werden, wenn ein Benutzer den Inhalt aktualisiert. Weitere Informationen finden Sie im Abschnitt „Validierung“ im [Benutzerhandbuch](https://helpx.adobe.com/content/dam/help/en/xml-documentation-solution/4-2/Adobe-Experience-Manager-Guides_UUID_User-Guide_EN.pdf#page=58)

![Regeln über Web-Editor-Einstellungen festlegen](../../../assets/authoring/schematron-editorsettings-validation-tab.png)


### Kann die Validierung manuell ausgeführt werden?

Ja, als Autor/Benutzer können Sie beim Erstellen von Inhalten das Bedienfeld „Schematron“ im Web-Editor verwenden, um eine Schematron-Datei hochzuladen und Validierungen für die im Editor geöffnete Datei durchzuführen.

Damit dies funktioniert, muss der Ordnerprofiladministrator allen Benutzern erlauben, Schemtron-Dateien im Validierungsbereich hinzuzufügen. Siehe Editor-Einstellungen (Screenshot oben)

![Schematron-Datei auswählen](../../../assets/authoring/schematron-rightpanel-validation-addsch.png)
![Validierung ausführen](../../../assets/authoring/schematron-rightpanel-validation-runsch.png)


### Unterstützte Regeln

Die aktuelle Version von AEM Guides unterstützt nur die Validierung mithilfe von auf „Assertion“ basierenden Regeln. (Siehe [Asset vs. Bericht](https://schematron.com/document/205.html))
Regeln, die auf „Berichten“ basieren, werden noch nicht unterstützt.


### Beispiele und weitere Hilfen zu Schematron-Regeln

#### Beispiele für Anwendungsfälle

- Prüfen, ob ein Link extern ist und ob er den Bereich „extern“ hat

  ```
  <sch:pattern>
      <sch:rule context="xref[contains(@href, 'http') or contains(@href, 'https')]">
          <sch:assert test="@scope = 'external' and @format = 'html'">
              All external xref links must be with scope='external' and format='html'
          </sch:assert>
      </sch:rule>
  </sch:pattern>
  ```

- Überprüfen, ob mindestens eine „topicref“ in einer Karte oder mindestens eine „li“ unter einer „ul“ vorhanden ist

  ```
  <sch:pattern>
      <sch:rule context="map">
          <sch:assert test="count(topicref) > 0">
              There should be atleast one topicref in map
          </sch:assert>
      </sch:rule>
  
      <sch:rule context="ul">
          <sch:assert test="count(li) > 1" >
              A list must have more than one item.
          </sch:assert>
      </sch:rule>
  </sch:pattern>
  ```

- Das Element „indexTerm“ sollte immer in einem „prolog“ vorhanden sein

  ```
  <sch:pattern>
      <sch:rule context="*[contains(@class, ' topic/indexterm ')]">
          <sch:assert test="ancestor::node()/local-name() = 'prolog'">
              The indexterm element should be in a prolog.
          </sch:assert>
      </sch:rule>
  </sch:pattern>
  ```

#### Ressourcen

- Grundlagen [ Schematron](https://da2022.xatapult.com/#what-is-schematron)
- Weitere Informationen [Assertionsregeln im Schematron](https://www.xml.com/pub/a/2003/11/12/schematron.html#Assertions)
- [Beispieldatei für Schematron](../../../assets/authoring/sample_schematron.sch)
