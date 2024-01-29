---
title: Versionshinweise | Neue Funktionen in der Adobe Experience Manager-Anleitung, Version Dezember 2023
description: Erfahren Sie mehr über die neuen und verbesserten Funktionen in der Version von Adobe Experience Manager Guides as a Cloud Service im Dezember 2023.
feature: What's New
role: Leader
source-git-commit: 6006cabdc11b80179833a21b4d99d2f6c3f968ee
workflow-type: tm+mt
source-wordcount: '966'
ht-degree: 0%

---

# Neue Funktionen in der Version von Adobe Experience Manager Guides as a Cloud Service vom Dezember 2023

Dieser Artikel behandelt die neuen und verbesserten Funktionen in der Version Dezember 2023 der Adobe Experience Manager-Handbücher (später auch als *Experience Manager Guides as a Cloud Service*).

Weitere Informationen zu den Upgrade-Anweisungen, der Kompatibilitätsmatrix und den in dieser Version behobenen Problemen finden Sie unter [Versionshinweise](release-notes-2023.12.0.md).


## Variablen in der PDF-Ausgabe verwenden

Mithilfe von Variablen können Sie wiederverwendbare Informationen dynamisch einfügen und verwalten. Experience Manager-Handbücher helfen Ihnen beim Erstellen, Bearbeiten und Anzeigen einer Vorschau von Variablen beim Generieren der PDF-Ausgabe. Sie können die Werte von Variablen schnell ändern und Ihre Dokumente portabel und einfach zu aktualisieren.

![native PDF-Variablen](assets/add-variable-default.png){width="800" align="left"}

*Erstellen und verwalten Sie Variablen im Web Editor.*

Sie können auch Variablensätze erstellen, die die Standardwerte außer Kraft setzen und Ihren Variablen alternative Werte zuweisen. Fügen Sie diese Variablen in das Seitenlayout ein und verwenden Sie dasselbe PDF-Layout. Sie müssen nicht für jeden Wertesatz separate Layouts erstellen. Sie können beispielsweise für jede Produktversion einen Variablensatz erstellen. Dieser Variablensatz kann aus Variablen für verschiedene Produktdetails wie Produktname, Versionsnummer und Veröffentlichungsdatum bestehen. Anschließend können Sie für diese Variablen unterschiedliche Werte hinzufügen.

**Variable festgelegt 1: Adobe-set1**

* ProductName: Experience Manager-Handbücher
* VersionNumber: 2311
* Releasedatum: 20.11.2023

**Variable festgelegt 2: Adobe-set2**

* ProductName: Experience Manager-Handbücher
* VersionNumber: 2310
* ReleaseDate: 27.09.2023



<img src="./assets/native-pdf-variable-output.png" alt="Fußzeile in PDF-Ausgabe" width="500" border="2px">

*Generieren Sie die PDF-Ausgabe mithilfe von Variablen im PDF-Layout.*

Sie können Stile anwenden und HTML Markup verwenden, um die Variablen zu formatieren.  Sie können die Werte für alle Variablen bei Bedarf auch schnell aktualisieren und die Ausgabe neu generieren. Wenn Sie beispielsweise die Details für eine Version aktualisieren müssen, können Sie den Wert der Version in der Variablen VersionNumber bearbeiten und die Ausgabe neu generieren.


Erfahren Sie mehr über die Verwendung [Variablen in der PDF-Ausgabe](../native-pdf/native-pdf-variables.md).





## Umgestaltetes Erlebnis zur Bearbeitung der Attribute

Jetzt erhalten Sie ein überarbeitetes Erlebnis, um die Attribute für ein Element aus der **Inhaltseigenschaften** im Web Editor angezeigt.

![Bedienfeld &quot;Attribute&quot;](assets/attributes-multiple-properties.png){width="300" align="left"}

*Fügen Sie im Bereich &quot;Inhaltseigenschaften&quot;Attribute hinzu.*

Sie können die Attribute auch einfach bearbeiten und löschen.

Weitere Informationen finden Sie im Abschnitt **Inhaltseigenschaften** Funktionsbeschreibung innerhalb der [Rechter Bereich](../user-guide/web-editor-features.md#id2051EB003YK) Abschnitt.


## Bearbeiten von Metadaten beim Authoring

Jetzt können Sie beim Authoring die Metadaten-Tags der Datei mithilfe des Dropdown-Menüs **Dateieigenschaften** im rechten Bereich. Sie können auch **Weitere Eigenschaften bearbeiten** , um weitere Metadaten zu aktualisieren.

![file-properties](assets/file-properties-general.png){width="300" align="left"}

*Aktualisieren Sie die Metadaten und bearbeiten Sie die Dateieigenschaften im rechten Bereich.*

Weitere Informationen finden Sie im Abschnitt **Dateieigenschaften** Funktionsbeschreibung innerhalb der [Rechter Bereich](../user-guide/web-editor-features.md#id2051EB003YK) Abschnitt.

## Möglichkeit der Veröffentlichung von Inhalten in der ServiceNow-Wissensdatenbank

Sie können Ihre Inhalte jetzt auch in der ServiceNow Knowledge Base-Plattform veröffentlichen.

Mit der Version von Dezember 2023 können Sie als Administrator ein Veröffentlichungsprofil für den ServiceNow Knowledge Base-Server erstellen. Als Autor oder Herausgeber können Sie dann dieses ServiceNow-Veröffentlichungsprofil in der Ausgabevorgabe auswählen, um die Ausgabe in der angegebenen Wissensdatenbank zu veröffentlichen.

Mit dieser Funktion können Sie Inhalte wie Text, Videos und Bilder in der ServiceNow Knowledge Base-Plattform veröffentlichen und ein umfassendes Repository verwalten.


![Service now Knowledge Base-Vorgabe](assets/knowledgebase--output-preset.png){width="300" align="left"}

*Erstellen Sie eine Ausgabevorgabe für die ServiceNow-Wissensdatenbank.*

Weitere Informationen zum [Wissensdatenbank](../user-guide/generate-output-knowledge-base.md) Ausgabevorgaben.

## Verbessertes Landkartenkollektions-Dashboard

Experience Manager-Handbücher bieten ein erweitertes Dashboard für die Zuordnungssammlung. In einer Zuordnungssammlung können Sie die Metadateneigenschaften für die DITA-Maps schnell stapelweise konfigurieren. Diese Funktion ist praktisch, da Sie die Metadateneigenschaften nicht für jede DITA-Zuordnung einzeln aktualisieren müssen.

Jetzt können Sie den Dateinamen der DITA-Map anzeigen. Sie können auch die Grundlinien anzeigen. Auf diese Weise können Sie schnell die für eine Vorgabe verwendete Grundlinie finden.

![Sammlungs-Dashboard zuordnen](assets/map-collection-dashboard.png){width="800" align="left"}

*Anzeigen, Bearbeiten und Generieren der Ausgabe über das Dashboard der Zuordnungssammlung.*

Erfahren Sie, wie [Verwenden der Kartensammlung für die Ausgabegenerierung](../user-guide/generate-output-use-map-collection-output-generation.md).

## Anzeigen von Schlüsselattributen in der Kartenansicht

Wenn Sie Schlüsselattribute für das Thema oder die Zuordnungsreferenzen definieren, können Sie auch den Titel, das entsprechende Symbol und den Schlüssel im linken Bereich anzeigen. Der Schlüssel wird angezeigt als `key=<key-name>`.

Weitere Informationen finden Sie im Abschnitt **Kartenansicht** Funktionsbeschreibung in [Linke Leiste](../user-guide/web-editor-features.md#id2051EA0M0HS) Abschnitt.

![Schlüssel in der Kartenansicht](assets/view-key-title-map-view.png) {width="300" align="left"}

*Zeigen Sie das Schlüsselattribut in der Kartenansicht an.*

## Möglichkeit, eine Grundlinie basierend auf der Bezeichnung zu duplizieren

Experience Manager-Handbücher bieten jetzt ein verbessertes Benutzererlebnis zum Erstellen der Grundlinien im Web-Editor.\
![Erstellen neuer Grundlinien](assets/create-new-baseline.png) {width="300" align="left"}
*Erstellen Sie eine Grundlinie im Web Editor.*

Außerdem können Sie damit eine Grundlinie basierend auf der Bezeichnung duplizieren. Die Referenzversion wird beim Duplizieren anhand der angegebenen Bezeichnung ausgewählt (sofern vorhanden) oder wählt die Version aus der duplizierten Grundlinie aus.


![Grundlinie duplizieren ](assets/duplicate-baseline.png) {width="300" align="left"}

*Duplizieren Sie eine Grundlinie basierend auf einem Titel oder erstellen Sie eine exakte Kopie.*

Erfahren Sie mehr über das [Erstellen und Verwalten von Grundlinien im Web-Editor](../user-guide/web-editor-baseline.md).

## Auflösen von Cross-Map-Links in der Ausgabe der AEM Site

Cross-Map-Links (XREF mit Perimeter Peer), die in der AEM Site-Ausgabe gerendert werden, werden jetzt gemäß dem Dateinamen des Veröffentlichungskontexts aufgelöst, der für die generierte Zuordnung festgelegt wurde.


## URL der Ausgabe der AEM Site zur Verwendung des Dokumenttitels konfigurieren

Mit Experience Manager-Handbüchern können Sie als Administrator die URL der AEM Site-Ausgabe konfigurieren. Wenn der Dateiname nicht vorhanden ist oder alle Sonderzeichen enthält, können Sie konfigurieren, dass er in der URL der AEM Site-Ausgabe durch ein Trennzeichen ersetzt wird. Sie können sie auch durch den Namen des ersten untergeordneten Themas ersetzen. Erfahren Sie, wie [die URL der AEM Site-Ausgabe zur Verwendung des Dokumenttitels konfigurieren](../cs-install-guide/conf-output-generation.md#configure-the-url-of-the-aem-site-output-to-use-the-document-title).

