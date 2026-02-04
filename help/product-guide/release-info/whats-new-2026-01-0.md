---
title: Versionshinweise zu | Neue Funktionen in Adobe Experience Manager Guides Version 2026.01.0
description: Erfahren Sie mehr über die neuen und erweiterten Funktionen in der Version 2026.01.0 von Adobe Experience Manager Guides
role: Leader
source-git-commit: cb3b06e18391fdfc53eb5abd4096553781eab0b8
workflow-type: tm+mt
source-wordcount: '1551'
ht-degree: 1%

---

# Neue Funktionen in der Version 2026.01.0 (Februar 2026)

Dieser Artikel behandelt die neuen und erweiterten Funktionen, die mit der Version 2026.01.0 von Adobe Experience Manager Guides as a Cloud Service eingeführt wurden.

Eine Liste der in dieser Version behobenen Probleme finden Sie im Artikel [Behobene Probleme in Version 2026.01.0](fixed-issues-2026-01-0.md).

Erfahren Sie mehr [Upgrade-Anweisungen für die Version 2026.01.0](../release-info/upgrade-instructions-2026-01-0.md).


## Einführung in den Source-Suchmodus in Suchen und Ersetzen

Experience Manager Guides hat verschiedene Verbesserungen an der Funktion Suchen und Ersetzen eingeführt, die im linken Bereich der Editor-Benutzeroberfläche verfügbar ist. Neben einer verbesserten Benutzeroberfläche für bessere Benutzerfreundlichkeit führt diese Version einen neuen Umschalter **Quellmodus verwenden** im Bedienfeld **Suchen und Ersetzen** ein.

Wenn dieser Modus aktiviert ist, können Sie eine globale Suche nicht nur nach dem sichtbaren Inhalt durchführen, sondern auch nach dem zugrunde liegenden Quellinhalt (XML-Struktur, einschließlich Elementen, Tags und Attributwerten) für die gesuchte Zeichenfolge. Dieser Modus stellt eine umfassende Suche über den gesamten Inhalt hinweg sicher.

![](assets/map-find-replace-with-source-mode.png){width="650" align="left"}

In diesem Modus können Sie Filter anwenden, um Ihre Suche nach Dateityp, Dokumentstatus, Datum der letzten Änderung und mehr einzugrenzen. Sie haben außerdem die Möglichkeit, nach Durchführung des Vorgangs „Alle ersetzen“ einen detaillierten CSV-Bericht herunterzuladen, der einen Schnappschuss aller durchgeführten Ersetzungsaktionen zusammen mit ihrem Erfolgs- und Fehlerstatus enthält.

Weitere Informationen finden Sie im Abschnitt [Suchen und Ersetzen](../user-guide/web-editor-left-panel.md#find-and-replace) unter _Linkes Bedienfeld im Editor_.

>[!NOTE]
>
> Für **Funktion „Quellmodus verwenden** im Bedienfeld „Suchen und Ersetzen“ muss zunächst eine benutzerdefinierte Indexbereitstellung abgeschlossen werden. Wenden Sie sich nach der Indizierung an Ihr Customer Success-Team, um diese Funktion zu aktivieren.

## Verbessertes Erlebnis beim Durchsuchen von Dateien und Ordnern

Diese Version bietet eine übersichtlichere, intuitivere Benutzeroberfläche zum Durchsuchen von Dateien und Ordnerpfaden in Experience Manager Guides.

Beim Durchsuchen von Dateien bietet das neu gestaltete Dialogfeld **Datei auswählen** jetzt ein Layout mit Registerkarten mit zwei Ansichten - **Repository** zum Navigieren im gesamten Inhalts-Repository in einem tabellarischen Format und **Sammlungen** für den schnellen Zugriff auf häufig verwendete Themen, Karten und Bilder.

![](assets/select-file.png){width="650" align="left"}

Zu den wichtigsten Verbesserungen gehören:

- Tabellenansicht von Dateien und Ordnern für die organisierte Navigation.
- Breadcrumbs und Ordnernavigationsfenster zum einfachen Durchsuchen der Ordner.
- Unterstützung für die Auswahl mehrerer Dateien für wiederverwendbare Inhalte, Themenreferenzen, Schematron, Ausgabevorgaben (mit DITAVAL) und Workfront.
- Vorschau ausgewählter Dateien zur einfachen Überprüfung; für mehrere Auswahlen sollten Sie alle Dateien in der Vorschau anzeigen und alle Dateien nach Bedarf aus dem Bedienfeld „Vorschau“ entfernen.
- Such- und Filteroptionen zur Eingrenzung der Ergebnisse nach Name, Titel, Dateityp, Dokumentstatus und Tags.

Das **Pfad auswählen**-Dialogfeld bietet außerdem eine verbesserte baumstrukturierte Ansicht für die Ordnernavigation, die eine übersichtlichere und effizientere Methode zur Auswahl von Pfaden im gesamten Inhalts-Repository gewährleistet.

![](assets/select-path-dialog-new.png){width="350" align="left"}

Experience Manager Guides Weitere Informationen finden Sie [&#x200B; Abschnitt „Durchsuchen von Dateien und Ordnern in &#x200B;](../user-guide/web-editor-other-features.md#browse-files-and-folders-in-experience-manager-guides)&quot; unter _Weitere Funktionen im Editor_.

## Verbesserungen bei der Repository-Suche und -Filterung

### Unterstützung für den Dokumentstatusfilter

Filtern Sie jetzt Ihre Repository-Suchergebnisse basierend auf dem aktuellen Dokumentstatus der Dateien. Mit dem neuen Filter **Dokumentstatus** können Sie Ihre Suche mithilfe der verfügbaren Filterwerte eingrenzen, die in der `ui_config.json`-Datei in Ihrem Ordnerprofil definiert sind.

![](assets/document-state-filter-repository.png){align="left"}

Die für den Status des Dokuments verfügbaren Standardfilterwerte sind: Entwurf, Bearbeiten, In-Überprüfung, Genehmigt, Überprüft und Fertig. Details zum Anpassen der Standardwerte für Dokumentstatusfilter finden Sie unter [Konfigurieren von Dokumentstatusfiltern](../cs-install-guide/config-doc-state-filters.md).

>[!NOTE]
>
> Wenn Sie benutzerdefinierte Einstellungen für verwenden, `ui_config.json` Sie sicherstellen, dass Sie diese vor dem Upgrade sichern. Überprüfen und passen Sie Ihre Einstellungen nach der Aktualisierung entsprechend den Änderungen an, die in der neuesten Version eingeführt wurden.

### Miniaturbildsymbol für Multimedia

Alle Multimediadateien werden jetzt mit Miniaturansichten angezeigt, wodurch die visuelle Identifizierung und Suche nach Bildern im **Repository)** wird. Diese Verbesserung gilt auch für die Suche nach Dateien im **Suchbereich**, sodass Sie Multimedia-Assets schnell von anderen Dateitypen unterscheiden können.

![](assets/thumbnail-repository.png){align="left"}

## Verbesserungen am Editor

Im Rahmen dieser Version wurden die folgenden Editor-Verbesserungen vorgenommen:

### Themen oder Zuordnung im Vorschaumodus aktualisieren

Einführung der neuen **Aktualisieren**-Funktion für Karten, die bereits im Vorschaumodus geöffnet sind. Mit dieser neuen Funktion können Sie den Inhalt der gesamten Karte oder einzelner darin vorhandener Themen einfach aktualisieren.

- Um die gesamte Karte (einschließlich aller Themen) zu aktualisieren **wird oben links im Editor eine neue Schaltfläche** Aktualisieren“ angezeigt.

  ![](assets/refresh-map.png){width="600" align="left"}

- Um den Inhalt einzelner Themen zu aktualisieren, wird **neue Option** Thema aktualisieren“ im Kontextmenü eingeführt.

  ![](assets/refresh-topic.png){width="600" align="left"}

Weitere Informationen finden Sie unter [Funktionen des Zuordnungs-Editors](../user-guide/map-editor-advanced-map-editor.md).

### Arbeitskopie-Indikator für Metadatenänderungen

Bei allen Änderungen an den Metadatenfeldern, die unter **Dateieigenschaften** verfügbar sind, wird jetzt der Trigger Arbeitskopie erstellt. Eine Dokumentversion wird als _(*) gekennzeichnet_ wenn Sie standardmäßige oder benutzerdefinierte Metadatenfelder hinzufügen, löschen oder ändern. Durch diese Verbesserung wird sichergestellt, dass alle Metadatenänderungen präzise verfolgt werden, was die Sichtbarkeit und Kontrolle über Dokumentversionen verbessert.

### Wortzahl für Themen und Karten

Sie können jetzt die Wortzahl in einer Zuordnungs- oder Themendatei verfolgen. Das neue Feld **Wortzahl** im rechten Bereich würde die Gesamtzahl der Wörter innerhalb eines Themas (oder einer Karte) anzeigen, wobei Wörter, die durch Leerzeichen getrennt sind, als einzelne Wörter gezählt werden. Es wird jedes Mal automatisch aktualisiert, wenn Sie Änderungen speichern. Bei Querverweisen ist nur der Anzeigetext enthalten, während Schlüssel ausgeschlossen sind.

![](assets/file-properties-new.png){width="350" align="left"}

Weitere Informationen finden Sie unter [Rechtes Bedienfeld im Editor](../user-guide/web-editor-right-panel.md#file-properties).

### Verbesserte Handhabung für schreibgeschützte Dateien

Das Bearbeiten von Dateieigenschaften ist jetzt auf Dateien beschränkt, die sich im **Schreibgeschützt**-Modus befinden. Wenn eine Datei von einem anderen Benutzer gesperrt wird (im schreibgeschützten Modus verfügbar), können Sie keine Metadateneigenschaft ändern, weder über den [rechten Bereich](../user-guide/web-editor-right-panel.md#file-properties) noch über die Option **Eigenschaften** im [Kontextmenü einer Datei](../user-guide/web-editor-other-features.md#context-menu-functions-on-a-files-tab) oder im [Metadatenbericht](../user-guide/reports-web-editor.md#metadata-report). Dadurch wird verhindert, dass Dateien versehentlich geändert werden.

## Verbesserungen bei Überprüfungen

### Themen zu einer laufenden Prüfungsaufgabe hinzufügen oder daraus entfernen

Jetzt können Sie einer laufenden Prüfungsaufgabe neue Themen hinzufügen (wenn diese noch nicht zur Überprüfung gesendet wurden) oder Themen aus einer laufenden Prüfungsaufgabe entfernen, ohne den Prüfungs-Workflow zu beeinflussen.

Auf der Seite **Aufgabendetails** können Sie einfach Themen auswählen oder die Auswahl aufheben, um die Themenliste zu ändern. Reviewer werden (über AEM und E-Mail) über Änderungen an ihren zugewiesenen Themen durch AEM- und E-Mail-Benachrichtigungen benachrichtigt. Weitere Informationen finden Sie unter [Themen zur Überprüfung senden](../user-guide/review-send-topics-for-review.md).

![](assets/modify-review-topics.png){width="650" align="left"}

## Verbesserungen an der Übersetzung

### Indikator für nicht versionierte Assets, die zur Übersetzung gesendet werden

Bei der Verwaltung von Übersetzungen ist es wichtig sicherzustellen, dass alle Inhalte versioniert werden, bevor sie zur Verarbeitung gesendet werden. Um Ihnen dabei zu helfen, bietet Experience Manager Guides jetzt einen eindeutigen Indikator für Themen, die Änderungen gespeichert haben, aber noch nicht versioniert sind.

Wenn eine Datei nicht versionierte Änderungen enthält (nicht als neue Version in Ihrer Zuordnung gespeichert), wird neben der Datei ein _info_-Symbol angezeigt, das angibt, dass Aktualisierungen vorhanden sind. Um sich schnell auf diese Dateien zu konzentrieren, aktivieren Sie die Option **Nur Assets mit nicht versionierten Änderungen anzeigen** im Bedienfeld Filter .

Weitere Informationen finden Sie unter [Übersetzen von Dokumenten in der Zuordnungskonsole](../user-guide/translate-documents-web-editor.md).

![](assets/unversioned-changes-translation.png){width="650" align="left"}

## Verbesserungen beim Veröffentlichen

### Benutzerdefinierte Bildausgabedarstellungen für bestimmte Ausgabevorgaben

Sie können jetzt mithilfe des `outputName`-Attributs in `renditionmapping.xml` verschiedene Bildausgabedarstellungen für einzelne Ausgabevorgaben unter demselben Ausgabetyp konfigurieren. Diese Verbesserung bietet Ihnen mehr Flexibilität bei der Veröffentlichung von Inhalten, die unterschiedliche Bildauflösungen für verschiedene Szenarien erfordern. Beispielsweise könnten Sie ein hochauflösendes Bild für Ihre HTML5-Hauptausgabe benötigen, während Sie eine kleinere Miniaturansicht für eine einfache Vorgabe verwenden.

Weitere Informationen finden Sie unter [Verarbeiten von Bildausgabedarstellungen bei der Ausgabegenerierung](../cs-install-guide/conf-output-generation.md#handle-image-rendition-during-output-generation).


### Protokolle für generierte Ausgabe herunterladen

Beim Generieren einer Ausgabe über die Assets-Benutzeroberfläche ist jetzt eine neue Schaltfläche **Protokolle herunterladen** verfügbar, mit der Sie das Protokoll auf Ihr lokales Gerät herunterladen können, um den Zugriff und die Überprüfung zu erleichtern.


### Sprachvariablen für Querverweise in der nativen PDF-Ausgabe

Beim Veröffentlichen der nativen PDF-Ausgabe können Sie [Sprachvariablen](../native-pdf/native-pdf-language-variables.md) verwenden, um statischen Querverweistext zu übersetzen, z. B. _Siehe Kapitel_ oder _Siehe Seite_. Die Variable verwendet die Sprache, die im Thema durch das Attribut `xml:lang` definiert ist.

Weitere Informationen zur Konfiguration der nativen PDF-Ausgabevorgabe und der Querverweiseinstellungen finden Sie unter [Native PDF-Ausgabevorgabe](../web-editor/native-pdf-web-editor.md).


### Unterstützung für die Komponentenzuordnung auf Elementebene in der Veröffentlichung von New AEM Sites (mit der Zuordnung zusammengesetzter Komponenten)

Experience Manager Guides unterstützt jetzt die Komponentenzuordnung auf Elementebene in der AEM Sites-Ausgabe (unter Verwendung der zusammengesetzten Komponentenzuordnung), sodass Teams genau steuern können, wie DITA-Elemente mithilfe von `componentmapping.json` gerendert werden. Wenn Sie `topicref`, Titel, Bilder, Tabellen und mehr den entsprechenden AEM-Kernkomponenten zuordnen, erhalten Sie eine sauberere Struktur, anstatt dass alles standardmäßig auf die Textkomponente festgelegt wird. Dies führt zu einer besseren Leistung und erschließt umfassendere, modernere Sites-Erlebnisse.

Weitere Informationen finden Sie unter [Komponentenzuordnung in AEM Sites](../cs-install-guide/component-mapping.md).

## Verbesserungen bei der Asset-Verarbeitung

Diese Version führt die folgenden Verbesserungen bei der Asset-Verarbeitung ein:

- Ausführen der Asset-Verarbeitung auf Ordner- und Einzeldateiebene
- Filtern Sie Assets, indem Sie bestimmte Asset-Typen wie Themen, Karten, Markdown, HTML/CSS, DITAVAL oder andere unterstützte Dateien auswählen, um nur die benötigten Dateien zu verarbeiten.
- Wenden Sie datumsbasierte Filter an, um den Verarbeitungsbereich für einen bestimmten Zeitrahmen zu begrenzen.
- Verarbeiten Sie Assets erneut mit der neuen Option **Assets erneut verarbeiten** die im Kontextmenü von Dateien und Ordnern in der Repository-Ansicht und im Explorer-Bedienfeld verfügbar ist.

Weitere Informationen zur Verarbeitung von Assets finden Sie unter [Assets verarbeiten](../user-guide/asset-processor.md).

## API-Verbesserungen

Im Rahmen dieser Version wurden die folgenden API-Verbesserungen vorgenommen:

- Es werden neue APIs eingeführt, um ein neues Übersetzungsprojekt zu erstellen und dessen Status zu verfolgen. Diese APIs helfen bei der Automatisierung des Übersetzungsprozesses, reduzieren den manuellen Aufwand und verbessern die Effizienz. Weitere Informationen finden Sie unter [Übersetzungsprojekt erstellen](../api-reference/translation-project.md)
- Verbesserte Asset-Verarbeitungs-APIs mit verbesserter Filterfunktion für Dateien und Ordner. Weitere Informationen finden Sie unter [Assets verarbeiten](../api-reference/bulk-assets-processing.md).
















