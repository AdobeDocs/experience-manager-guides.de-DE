---
title: Versionshinweise zu | Neue Funktionen in Adobe Experience Manager Guides Version 2024.2.0
description: Erfahren Sie mehr über die neuen und erweiterten Funktionen der Version 2024.2.0 von Adobe Experience Manager Guides as a Cloud Service.
exl-id: 234d430a-d775-484a-aea8-6e422b0a01eb
source-git-commit: b1bb2b9da71bf0551fe40c84ac382df0e78e007b
workflow-type: tm+mt
source-wordcount: '1066'
ht-degree: 2%

---

# Neue Funktionen in der Version 2024.2.0

Dieser Artikel behandelt die neuen und erweiterten Funktionen der Version 2024.2.0 von Adobe Experience Manager Guides.

Eine Liste der in dieser Version behobenen Probleme finden Sie im Artikel [Behobene Probleme in Version 2024.2.0](fixed-issues-2024-2-0.md).


Erfahren Sie mehr [Upgrade-Anweisungen für die Version 2024.2.0](upgrade-instructions-2024-2-0.md).



## KI-gestützte Smart Suggestions zum Hinzufügen von Inhaltsreferenzen beim Erstellen von Inhalten

Jetzt können Sie Ihren Authoring-Journey mit Smart Suggestions verbessern, einer neuen KI-basierten Funktion im Web-Editor. Während Sie Ihre Inhalte erstellen, bietet diese intelligente Funktion Echtzeitvorschläge für Inhaltsreferenzen, die Ihren Workflow verbessern, die Genauigkeit erhöhen und eine beispiellose Effizienz sicherstellen.


Um Ihre Inhalte korrekt und konsistent zu halten, sind die Suche und die Vorschläge auf die Inhalte Ihrer Organisation beschränkt und werden eng mit den Keywords abgeglichen, nach denen Sie suchen.

![Bedienfeld „Intelligente Vorschläge“ im Web-Editor ](assets/web-editor-smart-suggestion.png) {width="800" align="left"}


*Zeigen Sie intelligente Vorschläge an, um passende Inhaltsreferenzen aus Ihrem Inhalts-Repository zu finden und hinzuzufügen.*

Sie können den aktuellen Inhalt auch mit ähnlichen Inhalten in anderen Themen vergleichen. Anschließend können Sie einfach die Inhaltselemente aus verschiedenen Themen auswählen und sie als Inhaltsreferenzen zu Ihrem aktuellen Thema hinzufügen. Durch Hinzufügen der Inhaltsreferenzen können Aktualisierungen leichter verwaltet werden, insbesondere in größeren Dokumentationsprojekten. Sie erstellen beispielsweise eine Broschüre über die neuesten Funktionen Ihres Produkts. In diesem Fall können Sie die aktualisierten Spezifikationen schnell als Inhaltsreferenzen aus den zugehörigen Funktionsdokumenten hinzufügen.

Die Verwendung dieser intelligenten Funktion reduziert den manuellen Aufwand für die Suche nach verwandten Inhalten und hilft Ihnen, sich auf die Erstellung neuer Inhalte zu konzentrieren.  Dies trägt auch zur Konsistenz bei und erleichtert die Zusammenarbeit im Team.

Erfahren Sie mehr über [KI-gestützte intelligente Vorschläge zum Erstellen von Inhalten](../user-guide/authoring-ai-based-smart-suggestions.md).

## Neu gestaltete Funktion „Versionsverlauf“ im Web-Editor

Jetzt bietet Experience Manager Guides eine erweiterte Funktion zum Versionsverlauf, mit der Sie die an einem Dokument vorgenommenen Änderungen im Zeitverlauf vergleichen können. In der neuen Seitenansicht können Sie den Inhalt und die Metadaten der aktuellen Version einfach mit einer beliebigen früheren Version desselben Dokuments vergleichen. Sie können auch die Beschriftungen und Kommentare für die verglichenen Versionen anzeigen. Als Admin können Sie die Versionsmetadaten des Themas und deren Werte steuern, die im Dialogfeld **Versionsverlauf** angezeigt werden.

![Dialogfeld „Versionsverlauf“](assets/version-history-dialog-web-editor.png){width="800" align="left"}
*Vorschau der Änderungen in den verschiedenen Versionen eines Themas.*


Weitere Informationen zur Beschreibung der Funktion **Versionsverlauf** finden Sie [ Abschnitt ](../user-guide/web-editor-features.md#id2051EA0M0HS)Linkes Bedienfeld“.

## Verbessertes Benutzererlebnis im Übersetzungs-Panel

Das Bedienfeld **Übersetzung** wurde verbessert.  Sie können die Liste **Verfügbare Sprachen** anzeigen und schnell das Gebietsschema auswählen, in das Sie Ihr Projekt übersetzen möchten. Mit einer einzigen Auswahl können Sie auch **Alle auswählen** um Ihr Projekt in alle verfügbaren Sprachen zu übersetzen.

![Übersetzungsbedienfeld](assets/translation-languages-4.4.png){width="300" align="left"}

*Wählen Sie die Gebietsschemata aus, in die Sie Ihr Projekt übersetzen möchten. Wählen Sie die Standardversion, die Baseline oder die neueste Version der zu übersetzenden Dateien aus.*

Erfahren Sie mehr über die [Übersetzung von Inhalten](../user-guide/translation.md).


## Verbesserte Suchlogik im Dialogfeld „Element einfügen“

Die Elemente sind jetzt im Dialogfeld Element einfügen leicht zu finden.  Sie können eine Zeichenfolge in das Suchfeld eingeben und eine Liste aller gültigen Elemente abrufen, die mit der eingegebenen Zeichenfolge beginnen.

Beispiel: Beim Bearbeiten eines Absatzes, für den Sie ein Element einfügen möchten, können Sie nach dem Zeichen „t“ suchen, um Folgendes zu erhalten
alle gültigen Elemente, die mit „t“ beginnen.


![Dialogfeld „Einfügen](assets/insert-element.png){width="300" align="left"}

*Geben Sie ein Zeichen ein, um nach allen gültigen Elementen zu suchen, die mit dem Zeichen beginnen.*


Weitere Informationen finden Sie in der Beschreibung **Element einfügen** im Abschnitt [Linkes Bedienfeld](../user-guide/web-editor-features.md#id2051EA0M0HS).


## Möglichkeit, die aktuelle Liste zu teilen und mit einem neuen Listenelement auf derselben Ebene zu beginnen

Jetzt können Sie Ihre Liste im Web-Editor einfach aufteilen. Wählen Sie die **Liste teilen** aus dem Kontextmenü eines Listenelements aus, um die aktuelle Liste zu teilen. Eine neue Liste wird auf derselben Ebene erstellt, beginnend mit dem Listenelement, das Sie für die Aufspaltung ausgewählt haben.

![Übersetzungsbedienfeld](assets/context-menu-split-list.png){width="300" align="left"}

*Wählen Sie die Option aus, um die aktuelle Liste zu teilen.*

Weitere Informationen finden Sie in der **Liste einfügen** Funktionsbeschreibung im Abschnitt [Linkes Bedienfeld](../user-guide/web-editor-features.md#id2051EA0M0HS).

## Zugreifen auf Dateieigenschaften im Quellmodus der Bearbeitung

Jetzt können Sie auf die Funktion **Dateieigenschaften“ des rechten Bedienfelds** allen vier Modi oder Ansichten zugreifen: Layout, Autor, Source und Vorschau.  Auf diese Weise können Sie die Eigenschaften Ihrer Datei auch dann anzeigen, wenn Sie zwischen den verschiedenen Modi wechseln.

Weitere Informationen finden Sie in der **Dateieigenschaften** Funktionsbeschreibung im Abschnitt [Rechtes Bedienfeld](../user-guide/web-editor-features.md#id2051EB003YK).

## Möglichkeit, mehrere Ausgabevorgaben mit dynamischen Baselines parallel zu veröffentlichen

Experience Manager bietet die Funktion, Baselines zu erstellen, indem die Themen automatisch entsprechend der ihnen zugewiesenen Beschriftung ausgewählt werden. Jetzt können Sie auch mehrere Ausgabevorgaben mit automatischen Baselines derselben DITA-Zuordnung nahtlos veröffentlichen. Sie müssen nicht immer nur eine Vorgabe gleichzeitig veröffentlichen, sondern können auch einfach mehrere Ausgabevorgaben parallel veröffentlichen.


## Native PDF-Verbesserungen

In der Version 2024.2.0 wurden die folgenden nativen PDF-Verbesserungen vorgenommen:

### Übergeben von Asset-Metadaten an die PDF-Ausgabe

Experience Manager bietet jetzt die Möglichkeit, die Metadateneigenschaften der Assets aus der DITA-Zuordnung an die PDF-Ausgabe zu übergeben.
Über die native PDF-Ausgabevorgabe können Sie die Metadaten auswählen, die Sie an den PDF-Veröffentlichungsprozess übergeben möchten. Sie können sowohl die benutzerdefinierten als auch die Standardeigenschaften auswählen.  Die ausgewählten Metadateneigenschaften werden an die PDF-Datei übergeben, die mit dem nativen PDF generiert wurde.

Diese Funktion ist praktisch, da sie Ihnen dabei hilft, Ihre Asset-Eigenschaften wie Autor, Erstellungsdatum oder Dokumenttitel konsistent zu halten. Dies erleichtert die Organisation, Suche und Kategorisierung Ihrer Dokumente.

Weitere Informationen finden Sie unter **Erweitert** in der Ausgabe [Publish PDF](../web-editor/native-pdf-web-editor.md).


### Verwenden der im `topicmeta` hinzugefügten Metadaten für die PDF-Ausgabe

Die Metadatenfunktion in der nativen PDF-Veröffentlichung hilft bei der Inhaltsverwaltung und bei der Suche nach Dateien im Internet.
<img src="assets/pdf-metadata-4-4.png" alt="Registerkarte Metadaten" width="800">

*Wählen Sie eine Option aus, um Metadatenoptionen hinzuzufügen und anzupassen.*

Jetzt bietet Experience Manager Guides die Möglichkeit, die Metadaten zu verwenden, die Sie im `topicmeta` der DITA-Zuordnung hinzugefügt haben, um die Metadatenfelder der PDF-Ausgabe zu befüllen. Standardmäßig ist diese Option aktiviert.

Diese Funktion trägt zu einer besseren Dokumentverwaltung bei, sorgt für Konsistenz und macht Ihre Dokumente durchsuchbar.

Weitere Informationen finden Sie auf der Registerkarte **Metadaten** in der [Publish PDF-Ausgabe](../web-editor/native-pdf-web-editor.md).
