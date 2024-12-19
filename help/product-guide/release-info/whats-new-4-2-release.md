---
title: Versionshinweise zu | Neue Funktionen in Adobe Experience Manager Guides Version 4.2
description: Erfahren Sie mehr über die neuen und erweiterten Funktionen in Version 4.2 von Adobe Experience Manager Guides
exl-id: 46367ccf-58ff-4889-8314-cdd5bf5d0f1d
feature: What's New
role: Leader
source-git-commit: 6d8c01f20f7b59fed92c404561b647d9ebecb050
workflow-type: tm+mt
source-wordcount: '2423'
ht-degree: 0%

---

# Neue Funktionen in Version 4.2 von Adobe Experience Manager Guides (Februar 2023)

Dieser Artikel behandelt die neuen und erweiterten Funktionen in Version 4.2 von Adobe Experience Manager Guides (später *AEM Guides*).

Weitere Informationen zu den Upgrade-Anweisungen, der Kompatibilitätsmatrix und den in dieser Version behobenen Problemen finden Sie im Artikel [Versionshinweise](release-notes-4-2.md) .

## Erstellen von Berichten im Web-Editor

AEM Guides verfügt über eine Funktion im Web-Editor, mit der Sie die Vollständigkeit Ihrer technischen Dokumente insgesamt überprüfen und Berichte für sie generieren können.
Sie können die Themenliste anzeigen und die Metadaten aller Verweise für die aktuelle Zuordnung in der
Registerkarte **Berichte** im Web-Editor.

**Generieren der Themenlistenansicht**

Sie können die Themenliste generieren, die detaillierte Informationen zu Ihren Themen bereitstellt, z. B. den Referenztyp, den Dokumentstatus und den Autor. Sie können auch die CSV-Datei generieren, um den aktuellen Schnappschuss der Themen in der DITA-Karte herunterzuladen.

**Verwalten von Metadaten und Ändern des Dokumentstatus**

Sie können Tags auf ein einzelnes Thema anwenden oder die Bulk-Tagging-Funktion verwenden, um mehrere Tags auf mehrere Themen, eine DITA-Karte oder eine Unterzuordnung anzuwenden. Sie können auch den Dokumentstatus aller ausgewählten Themen in den nächstmöglichen allgemeinen Dokumentstatus ändern.

<img src="assets/web-editor-metadata-panel.png" alt="Verwalten von Metadaten" width="600">

## Überarbeiteter UX für die Überprüfungsfunktion

Jetzt bieten AEM-Handbücher eine verbesserte Benutzeroberfläche, mit der Sie die freigegebenen Themen zur Überprüfung überprüfen können. In der neuesten Version wurden für die Überprüfungsfunktion folgende Verbesserungen vorgenommen:

* Aktualisierte Benutzeroberfläche
* Bedienfeld „Bedingungen“, mit dem Sie den Inhalt entsprechend den verfügbaren Bedingungen im Thema markieren können.
* Jeder Kommentar im Kommentarbereich ist mit dem entsprechenden Text im aktuellen Thema verknüpft. Damit können Sie den kommentierten Text leichter identifizieren.
* Die Kommentare werden in der Reihenfolge des kommentierten Texts im Dokument angezeigt.
* Der Name der Prüfungsaufgabe wird im Prüfungs-Workflow angezeigt.
* Wählen Sie die Rootmap für die Prüfungsaufgabe aus, die zum Auflösen aller wichtigen Verweise und Glossarbegriffe verwendet wird, die im Prüfungsinhalt verwendet werden.
* Kontextuelle Symbolleiste zum schnellen Hervorheben oder Durchstreichen von Text.
* Optionsmenü zum Bearbeiten oder Löschen eigener Kommentare.
* Bei veralteten Kommentaren haben Sie Zugriff auf eine Ansicht, in der Sie die vorherige Version des Themas mit der aktuellen Überprüfungsversion vergleichen können
* Bei Verwendung der Filter werden die Kommentare im rechten Bedienfeld entsprechend der Auswahl gefiltert und die
Die Anzahl der Kommentare im linken Bereich wird entsprechend aktualisiert.


<img alt="Prüfungsaufgabe" src="assets/comment-pop-up-panel.png" width="600">


Weitere Informationen finden Sie im Abschnitt *Themen oder Karten überprüfen* im Handbuch Verwenden von Adobe Experience Manager Guides .

## Verbesserungen an der Übersetzung

Jetzt verfügen Sie über benutzerfreundlichere Verbesserungen im Übersetzungs-Dashboard, mit denen Sie Ihre Dokumente aus dem Web-Editor einfach übersetzen können.


**Spalte „Versionsbezeichnung“ wurde zum Übersetzungs-Dashboard hinzugefügt**

Im Übersetzungs-Dashboard wird auch die Spalte Versionsbezeichnung angezeigt. Dadurch wird der Titel für die ausgewählte Version der Quelldatei angezeigt. Auf diese Weise können Sie alle Dateien mit einem bestimmten Titel auswählen und in einem Schritt übersetzen.

**Zeigen Sie Versionsunterschiede bei Dateien mit unzureichender Synchronisierung im Übersetzungs-Dashboard an**

Jetzt können Sie die Unterschiede zwischen der ausgewählten Version und der letzten übersetzten Quellversion der Themen überprüfen. Sie können auch festlegen, dass die **nicht synchron** Dateien basierend auf den Änderungen übersetzt werden, die zwischen den beiden Versionen eines Themas vorgenommen wurden.

<img src="assets/translation-version-diff.png" alt="Übersetzungsgremium" width="600">



**Übergeben Sie die Versionsbezeichnung an die Zielversion**

Mit AEM Guides können Sie die Bezeichnung der Quelldatei an die Zieldatei übergeben. Auf diese Weise können Sie die Quellversion für die übersetzte Datei leicht identifizieren.

<img alt="Übersetzungsbeschriftungen" src="assets/translation-pass-source-label.png" width="600">

Wenn Sie beispielsweise Quelldateien haben, auf die die Bezeichnung Version 1.0 angewendet wurde, können Sie die Bezeichnung Quelle (Version 1.0) auch an die übersetzte Datei weitergeben.

**Erzwingt die Synchronisierung für nicht synchronisierte Assets**

Wenn Sie Änderungen an einigen Assets vornehmen, werden diese von AEM Guides als nicht synchronisiert markiert. Sie können die geänderten Assets entweder erneut übersetzen oder den Status „Nicht synchronisiert“ verwerfen. Wenn Sie zum Beispiel einige kleinere Änderungen vorgenommen haben, die wirklich keine Übersetzung benötigen, können Sie deren Status als „Synchronisiert“ markieren.

**In Bearbeitung befindliche Übersetzungsprojekte für ein Thema oder eine Karte anzeigen**

Einige der Verweise auf Ihrem Übersetzungs-Dashboard sind möglicherweise in Bearbeitung. Jetzt bietet AEM Guides eine Funktion, mit der Sie die Liste aller laufenden Übersetzungsprojekte (zusammen mit der Zielsprache) anzeigen können, die die ausgewählte Referenz enthalten.

Weitere Informationen finden Sie im Abschnitt *Übersetzen von Dokumenten aus dem Web* Editor im Handbuch Verwenden von Adobe Experience Manager Guides .

## Generieren von Ausgaben in verschiedenen Formaten aus dem Web-Editor

Jetzt können Sie die Ausgabe für Ihre Themen oder DITA-Map einfach aus dem Web-Editor generieren. Sie können verschiedene Ausgabevorgaben wie AEM-Site, PDF, HTML5,
JSON (ein Headless-Ausgabeformat) und benutzerdefinierte Ausgabe. Verwenden Sie diese, um die entsprechenden Ausgaben zu generieren. Sie können Attribute in Ihren DITA-Themen definieren und dann die Bedingungsvorgabe verwenden, um eine Bedingung beim Veröffentlichen der Ausgabe anzuwenden. Sie können die Funktion „Baseline-Veröffentlichung“ auch verwenden, um eine bestimmte Version Ihrer DITA-Karte oder Ihres Themas selektiv zu veröffentlichen.

**Globale Ausgabevorgaben und Ordnerprofile verwalten**

AEM Guides bietet die Funktion zum Erstellen und Verwalten von Ausgabevoreinstellungen für die globalen Profile und Ordnerprofile. Anschließend können Sie diese Ausgabevorgaben einfach verwenden, um eine Ausgabe für alle Zuordnungen zu generieren, die mit diesem globalen Profil oder Ordnerprofil verknüpft sind.

<img alt="Voreinstellung hinzufügen" src="assets/add-global-output-preset.png" width="400">


Diese globalen Vorgaben werden auf der Registerkarte **Ausgabe** aller zugehörigen Zuordnungen angezeigt. Sie können sie verwenden, um die Ausgabe für alle zugehörigen Zuordnungen zu generieren. Sie können die Vorgabe als Standard-PDF-Vorgabe auswählen, um die PDF-Ausgabe zu generieren. Sie können auch **Bearbeiten**, **Umbenennen**, **Duplizieren** oder **Löschen** eine vorhandene Ausgabevorgabe aus dem Menü **Optionen**.

>[!NOTE]
>
>Nur Benutzer mit Administratorrechten auf Ordnerebene können globale Vorgaben und Ordnerprofilvorgaben erstellen.

## Suchen und Ersetzen des Textes auf Kartenebene

Sie können jetzt in einer Zuordnung nach Dateien suchen, die bestimmten Text enthalten. Der gesuchte Text wird in den Dateien hervorgehoben. Sie können das gesuchte Wort oder die gesuchte Wortgruppe in den Dateien auch durch ein anderes Wort oder eine andere Wortgruppe ersetzen. Wählen Sie das Symbol **Einzelnes Vorkommen ersetzen**, um das aktuelle Vorkommen zu ersetzen, und das Symbol **Alle in Datei**, um alle Vorkommen in der ausgewählten Datei zu ersetzen. Sie können das Symbol **Alle ersetzen** auswählen, um alle Vorkommen des gesuchten Begriffs in allen Dateien zu ersetzen.

<img src="assets/map-find-replace.png" alt="Map Find Replace" width="600">


Standardmäßig sind die Optionen **Datei vor dem Ersetzen auschecken** und **Neue Version nach dem Ersetzen erstellen** ausgewählt, sodass eine Datei ausgecheckt wird, bevor Sie den Text ersetzen, und eine neue Version erstellt wird, nachdem der Text ersetzt wurde. Sie können die Zeichenfolge auch in den indirekten Referenzen innerhalb der DITA-Zuordnung suchen. Standardmäßig ist dies deaktiviert, sodass die Suche nur für die direkten Verweise durchgeführt wird.

## Layout-Ansicht im Karten-Editor


Jetzt können Sie das vollständige Layout einer DITA-Karte im Karten-Editor anzeigen. Wenn Sie eine Karte zur Bearbeitung öffnen, wird die Layout-Ansicht des Karten-Editors geöffnet. In dieser Ansicht sehen Sie die Zuordnungshierarchie in einer Baumansicht. Sie können die Themen auch in einer Karte bearbeiten und organisieren oder strukturieren.

<img src="assets/layout-view-map.png" alt=" Zuordnungs-Layout-Ansicht" width="600">

Die Layout-Ansicht enthält eine separate Symbolleiste, mit der Sie viele Aufgaben zu den in einer Karte vorhandenen Themen ausführen können.
Sie können Themenreferenzen, Themengruppe und Schlüsseldefinitionen in eine Zuordnung einfügen. Sie können die in einer Karte vorhandenen Themen neu organisieren, indem Sie sie nach oben, unten, links oder rechts verschieben. Sie können die Themen auch per Drag-and-Drop in eine Karte verschieben. Der Zuordnungs-Editor bietet außerdem die Symbole zum Sperren oder Entsperren von Dateien, zum Überprüfen des Versionsverlaufs und zum Ausführen einer Versionskennzeichenverwaltung.


Die Layout-Ansicht enthält auch die **Ansichtsoptionen** zum Ein- oder Ausblenden der Zeilennummer, zum Ein- oder Ausblenden der Kontrollkästchen oder zum Anzeigen des Dateinamens oder des Titels für die Themen in einer Karte.
Sie können die Themen auch basierend auf den auf sie angewendeten bedingten Filtern anzeigen.

Zusätzlich zur Organisation von Themen in der Zuordnungsdatei können Sie Verweise auch über das Menü **Optionen** hinzufügen, verschieben, kopieren, einfügen oder löschen, das für ein Element in der Layout-Ansicht verfügbar ist.

<img src="assets/layout-inline-attributes.png" alt=" Zuordnen von Layoutattributen" width="600">


Im rechten Bedienfeld werden die Inhaltseigenschaften und die Zuordnungseigenschaften in der Layout-Ansicht des Zuordnungs-Editors angezeigt. Jetzt können Sie auch die Metadateninformationen für die Themen oder die Zuordnung festlegen. Sie können den Navigationstitel, den Link-Text, die Kurzbeschreibung und die Keywords für das ausgewählte Thema oder die ausgewählte Karte definieren.

Weitere Informationen finden Sie *Abschnitt* Layout-Ansicht“ im Handbuch Verwenden von Adobe Experience Manager Guides .

## Bedienfeld „Schnellgenerierung“

Jetzt bietet AEM Guides das Bedienfeld „Schnell generieren“, mit dem Sie schnell die Ausgabe für Vorgaben generieren und anzeigen können, die für Ihre DITA-Zuordnung erstellt wurden.

<img src="assets/quick-generate-map-view.png" alt=" Bedienfeld „Schnellgenerierung“" width="600">

Im Bedienfeld **Schnellgenerierung** wird die Liste aller für Ihre DITA-Zuordnung erstellten Ausgabevorgaben angezeigt. Sie können auch schnell die für die Voreinstellungen generierte Ausgabe anzeigen. Nach Abschluss der Ausgabegenerierung wird eine Erfolgs- oder Fehlermeldung angezeigt. Sie können auch das Fehlerprotokoll anzeigen, das Details zu dem Fehler enthält, der beim Generierungsprozess aufgetreten ist.

## Erstellen einer dynamischen Baseline basierend auf Kennzeichnungen

Jetzt bietet AEM Guides die Funktion, dynamische Baselines basierend auf Beschriftungen zu erstellen. Wenn Sie eine Baseline generieren, eine Baseline herunterladen oder ein Übersetzungsprojekt mithilfe einer Baseline erstellen, werden die Dateien basierend auf den aktualisierten Beschriftungen dynamisch ausgewählt. Diese Funktion ist praktisch, da Sie die Grundlinie beim Aktualisieren der Beschriftungen nicht ändern müssen.

<img src="assets/dynamic-baseline.png" alt=" Dynamische Baseline" width="400">

## Löschen und Duplizieren von Dateien aus dem Repository-Bereich

Jetzt können Sie Dateien (jeweils nur eine Datei) einfach über das Menü **Optionen** der ausgewählten Datei im Repository-Bereich löschen. Vor dem Löschen der Datei wird eine Bestätigungsaufforderung angezeigt. Wenn keine andere Datei auf die Datei verweist, wird sie gelöscht und eine Erfolgsmeldung wird angezeigt.

<img src="assets/options-menu-repo-view-file-level.png" alt="Menü „Dateioptionen“ " width="500">

Sie können auch ein Duplikat oder eine Kopie der ausgewählten Datei erstellen. Standardmäßig wird die Datei erstellt mit
Ein Suffix (wie filename_1.extension).


## Weitere Verbesserungen am Web-Editor

* In AEM Guides können Sie mithilfe des Kontextmenüs einige allgemeine Vorgänge für Bilder und Mediendateien ausführen. Jetzt können Sie auch das ausgewählte Bild oder die ausgewählten Medien im Repository finden oder die Vorschau der Datei in der Assets-Benutzeroberfläche anzeigen.

* Der Name des aktuellen Ordnerprofils wird als Bezeichnung für das Symbol Benutzereinstellungen in der Hauptsymbolleiste angezeigt. Auf diese Weise können Sie das Ordnerprofil identifizieren, an dem Sie arbeiten.

* Wenn Sie eine Karte in der Kartenansicht öffnen, wird der Titel der aktuellen Karte in der Mitte der Symbolleiste angezeigt. Dies ist hilfreich, um Benutzenden mitzuteilen, welche Karte derzeit geöffnet ist.

## Bereinigen ausgewählter Versionen von Dateien

Wenn Sie Ihre Inhalte erstellen und verwalten, werden möglicherweise viele Versionen für Ihre DITA-Dateien in Ihrem Repository erstellt. Mit AEM Guides können Sie ältere Versionen Ihrer DITA-Dateien aus dem Repository bereinigen und Speicherplatz freigeben.

<img src="assets/preview-purge-report.png" alt="Vorschau des Bereinigungsberichts" width="500">

AEM Guides löscht nicht die erste Version der Datei oder eine Version, die in einer Baseline enthalten ist, oder auf die eine Kennzeichnung angewendet wurde. Der Bereinigungsvorgang löscht nicht einmal Dateien, die in einer Übersetzung oder einem Überprüfungs-Workflow enthalten sind. Sie können die Anzahl der beizubehaltenden Versionen auswählen und auch die Dateien löschen, die älter als die definierte Anzahl von Tagen sind.

Vor Beginn des Bereinigungsvorgangs können Sie eine Vorschau des Berichts anzeigen, um die Versionen anzuzeigen, die bereinigt werden sollen. Sie können dann den Bereinigungsvorgang starten oder abbrechen.

<img src="assets/download-purge-report.png" alt="PDownload-Bereinigungsbericht" width="500">

Sobald der Bereinigungsvorgang abgeschlossen ist, können Sie den Bereinigungsbericht überprüfen, um die bereinigten Dateien anzuzeigen.

## Titel anstelle von UUID im Sauerstoff-Editor anzeigen

Jetzt können Sie in AEM Guides die Option **Titel im Editor verwenden und Zuordnungs** Manager in den Einstellungen auswählen. Wenn Sie diese Option auswählen, wird der Titel der Datei auf der Registerkarte der Datei angezeigt, wenn sie im Editor oder DITA Maps Manager geöffnet wird. Wenn Sie diese Option nicht auswählen, wird die UUID der Datei auf der Registerkarte der Datei angezeigt.

## Metadaten-Benutzeroberfläche für das PDF von Voreinstellungen verfügbar

Sie können die Metadaten aus der Ausgabevorgabe einer DITA-Zuordnung festlegen. Sie können die Metadaten für Titel, Autor, Betreff und Keywords festlegen. Diese Metadaten werden den Metadaten in den Dateieigenschaften der Ausgabe-PDF zugeordnet. Diese Metadaten setzen die auf Buchebene definierten Metadaten außer Kraft. Sie können die Metadaten in jeder Ausgabevorgabe spezifisch definieren und an die Ausgabe-PDF weitergeben.

## Native PDF | PDF mit Änderungsleiste, die den Unterschied zwischen Dokumentversionen anzeigt

Jetzt können Sie mit der Änderungsleiste eine PDF erstellen, die die Inhaltsunterschiede zwischen zwei Versionen anzeigt. Sie können die aktuelle Version mit einer Baseline der vorherigen Version vergleichen oder zwischen den beiden ausgewählten Baseline-Versionen vergleichen.

<img src="assets/pdf-change-version.png" alt="pdf-change-version" width="600">

Auf der PDF wird eine Änderungsleiste angezeigt, die den geänderten, eingefügten oder gelöschten Inhalt angibt. Sie haben außerdem die Möglichkeit, Folgendes durchzuführen:
* Den eingefügten Inhalt grün und unterstrichen anzeigen
* Gelöschte Inhalte in roter Farbe anzeigen und mit einem Durchgestrichen markieren

## Native PDF | Variablenunterstützung für Ausgabepfad und PDF-Dateiname

Jetzt können Sie auch die folgenden vordefinierten Variablen verwenden, um den Ausgabepfad und die PDF-Datei zu definieren. Sie können eine einzelne oder eine Kombination von Variablen verwenden, um diese Optionen zu definieren:
* `${map_filename}`
* `${map_title}`
* `${preset_name}`
* `${language_code}`
* `${map_parentpath}` (nur für Ausgabepfad)
* `${path_after_langfolder}` (nur für Ausgabepfad)

## Native PDF | Inhaltsverzeichnis für DITA-Zuordnungen generieren und Seiten-Layouts neu anordnen

Jetzt können Sie das Inhaltsverzeichnis auch in DITA-Zuordnungen generieren, indem Sie eine erweiterte PDF-Einstellung der Vorlage verwenden. Sie können die Anzeige der verschiedenen Seiten-Layouts aktivieren oder deaktivieren und auch ihre Position neu anordnen.

## Native PDF | Hinzufügen eines benutzerdefinierten Lesezeichens in der PDF-Ausgabe

Jetzt können Sie ein benutzerdefiniertes Lesezeichen zu einem bestimmten Inhalt in Ihrer endgültigen PDF-Ausgabe hinzufügen, um die Navigation zu erleichtern. Dies wird dem Inhaltsverzeichnis hinzugefügt, das aus den Themen- oder Abschnittstiteln in Ihrer DITA-Karte erstellt wird.

## Native PDF | Anwenden eines benutzerdefinierten Stils auf Inhaltsverzeichniseinträge und Themeninhalte

AEM Guides bietet die Funktion, benutzerdefinierte Stile auf Inhaltsverzeichniseinträge oder ein bestimmtes Thema in der PDF-Ausgabe anzuwenden. Sie können beispielsweise die Farbe des Textes im Inhaltsverzeichnis und den Titel des Themas ändern. Sie können auch Stile auf den gesamten Inhalt innerhalb des Themas anwenden.
