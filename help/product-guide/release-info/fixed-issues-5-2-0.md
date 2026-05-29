---
title: Versionshinweise | Behobene Probleme in Adobe Experience Manager Guides Version 5.2.0
description: Erfahren Sie mehr über die Fehlerbehebungen in Version 5.2.0 von Adobe Experience Manager Guides.
source-git-commit: 5eee826022f798b4eb0014ea4b97d2916eb92f33
workflow-type: tm+mt
source-wordcount: '3559'
ht-degree: 0%

---

# Es wurden Probleme in Version 5.2.0 (Mai 2026) behoben

Dieser Artikel behandelt die in verschiedenen Bereichen von Version 5.2.0 von Adobe Experience Manager Guides behobenen Fehler.

Weitere Informationen zu den neuen Funktionen und Verbesserungen finden Sie unter [Neue Funktionen in Version 5.2.0](whats-new-5-2-0.md).

Erfahren Sie mehr [Upgrade-Anweisungen für Version 5.2.0](upgrade-instructions-5-2-0.md).


## Authoring

- Wenn ein leeres `prop` ohne Attribute oder Werte zu einer DITAVAL-Datei hinzugefügt wird, können keine zusätzlichen `prop` hinzugefügt werden. (GUIDES-33597)
- Nach dem Upgrade von Experience Manager Guides auf Version 2025.08.0 wird die Option zum Aktivieren oder Deaktivieren der benutzerdefinierten Registerkarte **Acrolinx** nicht mehr in den **Workspace-Einstellungen** angezeigt. (GUIDES-35261)
- Benutzerdefiniertes CSS, das auf ein Profil auf Ordnerebene für Themen oder Zuordnungen angewendet wird, wird bei der Browser-Aktualisierung im Vorschaumodus auf den Standardstil zurückgesetzt. (GUIDES-31098)
- **Vorgänge** Rückgängig“ und **Wiederholen** funktionieren in der Source-Ansicht des Editors für DITA-Dateien nicht wie erwartet. (GUIDES-24914, GUIDES-25034)
- Beim Referenzieren einer DITA-Zuordnung in einem Thema mithilfe des `Xref` wird der Dateiname der referenzierten Zuordnung anstelle des Titels der Zuordnung angezeigt. (GUIDES-21759)
- Beim Hinzufügen mehrerer Schematron-Dateien zur Validierung über das rechte Bedienfeld der Editor-Benutzeroberfläche wird ein Fehler **Schematron-Datei(en) existieren nicht oder weisen Fehler auf** angezeigt, selbst wenn die hinzugefügten Dateien gültig sind und keine Fehler aufweisen. (GUIDES-33731)
- Große oder komplexe MathML-Gleichungen werden im Editor nicht angezeigt. (GUIDES-29095)
- Wenn mehrere DITA-Zuordnungen oder -Themen geöffnet und eines der Themen geschlossen ist, wird die Schaltfläche **>>** , die alle offenen Registerkarten anzeigt, mit den verbleibenden offenen Registerkarten in der Registerkartenleiste überlagert. (GUIDES-31421)
- Wenn der **Genehmigungs** Workflow aktiviert ist, ist die Schaltfläche **Neue Version starten** in der Editor-Symbolleiste nicht sichtbar, wenn sowohl das linke Bedienfeld als auch das Bedienfeld Inhaltseigenschaften geöffnet sind. (GUIDES-29093)
- Wenn Snippet-Namen die Breite des Snippet-Bereichs überschreiten, werden sie falsch in die nächste Zeile eingeschlossen, was zu Überlappungen mit benachbarten Snippets führt und die Lesbarkeit beeinträchtigt. (GUIDES-22685)
- Wenn Sie dieselbe Referenz mehrmals zu einer DITA-Zuordnung hinzufügen, zeigt die **Map**-Ansicht den Titel nur für das letzte Vorkommen an, während die vorherigen die UUID der Referenz anzeigen. (GUIDES-9699)
- Die DITAVAL-Dateien bleiben bearbeitbar, auch wenn sie von einem anderen Benutzer gesperrt sind oder der Server **Bearbeitung deaktivieren, ohne die Datei zu sperren** aktiviert hat und die Datei im schreibgeschützten Modus geöffnet ist. (GUIDES-27754)
- Protokolle für fehlende Knoten werden aus internen Bereinigungsaufträgen generiert, die nicht erforderlich sind und fälschlicherweise als Fehler gekennzeichnet sind, was zu einer Überlastung der Protokolldateien führt. (GUIDES-31765)
- Beim Bearbeiten einer Schematron-Datei (`*.sch`) und bei Verwendung der Funktion zum Suchen und Ersetzen wird das Bedienfeld „Suchen und Ersetzen“ unten teilweise außerhalb des Bildschirms angezeigt, wodurch der Zugriff auf die Eingabefelder und Steuerelemente verhindert wird. (GUIDES-38412)
- Es können nicht mehrere **Versionsbezeichnungen** zu einem Thema im Dialogfeld **Als neue Version speichern** hinzugefügt werden. (GUIDES-32716)
- Wenn Sie ein Bild im Editor über das Dialogfeld **Datei auswählen** auswählen, werden nur Rasterformate (wie JPG, PNG und GIF) angezeigt. Vektordateien (z. B. .ai und .eps) werden nicht angezeigt und können nicht ausgewählt werden. (GUIDES-45110)
- Zum Zeitpunkt des Upgrades ist die `tagsView` standardmäßig deaktiviert, obwohl ihr Standardwert in `ui_config.json` auf `true` festgelegt ist. (GUIDES-44651)
- Im Editor werden Dateiverweise trotz der `xmleditor.uuid` als GUIDs anstelle von Dateipfaden angezeigt. (GUIDES-42438)
- Wenn Subjektschemata mit ähnlichen Schlüsselwerten in einem DITA-Thema angewendet werden, werden sie mit nahezu identischen Farben hervorgehoben, sodass es schwierig ist, sie zu unterscheiden und zu erkennen, welches Schema angewendet wird. (GUIDES-38472)
- Beim Bearbeiten einer Zuordnung eines Betreffschemas in der Autorenansicht wird durch Hinzufügen des `hasInstance` automatisch das Dateiauswahldialogfeld Trigger, sodass Autorinnen und Autoren eine unerwünschte `href` einfügen müssen, die auf ein AEM-Asset verweist. Darüber hinaus kann das Bedienfeld **Inhaltseigenschaften** für solche Zuordnungen nicht geladen werden. Dies verhindert, dass Autorinnen und Autoren Elementattribute in der Autorenansicht aktualisieren, und erfordert, dass sie die Source-Ansicht zum Aktualisieren von Attributen verwenden. (GUIDES-38164)
- Beim Bearbeiten einer `.ditaval` werden alle in der Source-Ansicht hinzugefügten XML-Kommentare entfernt, wenn Sie zur Autorenansicht wechseln und dann zur Source-Ansicht zurückkehren. (GUIDES-33228)
- Beim Aktualisieren einer Inline-MathML-Gleichung mit der Option MathML bearbeiten im Kontextmenü wird der aktualisierte Wert erst angezeigt, nachdem die Seite aktualisiert wurde. (GUIDES-38198)
- Wenn ein Thema viele wiederverwendbare Elemente (mit IDs) enthält, die im wiederverwendbaren Bereich hinzugefügt wurden, können einige Elemente aufgrund der festen Container-Höhe möglicherweise nicht aufgerufen werden. (GUIDES-37220)
- Beim Einfügen eines Querverweises in eine Datei werden die Symbole für Karten und Themen identisch angezeigt. (GUIDES-36662)
- Beim Bearbeiten einer Zuordnung werden in der `navtitle` keine Sondersymbole zur `topichead` in der Autorenansicht angezeigt. (GUIDES-35435)

## Asset-Management

- Wenn Sie ein bearbeitetes Bild erneut über die Experience Manager Guides-Benutzeroberfläche hochladen, wird die ursprüngliche Ausgabedarstellung des Bildes aktualisiert, aber der zugehörige DITA-Inhalt zeigt weiterhin die vorherige Bildversion an. (GUIDES-33693)
- Beim Versuch, zwei oder mehr Ordner von ihrem Quellspeicherort an einen anderen Speicherort zu verschieben (mithilfe des Tools für die Massenverschiebung), schlägt der Vorgang fehl, wenn die Ordnernamen mit derselben Zeichenfolge beginnen (z. B. Product- und ProductImages). (GUIDES-29096)
- Beim Löschen eines gesuchten Assets aus der Omnisearch Assets-Benutzeroberfläche wird das Warndialogfeld **Löschen erzwingen** umgangen und das Asset wird direkt gelöscht, selbst wenn es in vorhandenen DITA-Inhalten referenziert wird. (GUIDES-17232)
- Versionsbeschriftungen können nicht aus dem Bedienfeld **Versionsverlauf** in der Assets-Benutzeroberfläche entfernt werden. (GUIDES-38276)
- Wenn Sie ein Thema in einem Ordner mit Leerzeichen im Namen erstellen, wird fälschlicherweise ein doppelter Ordner erstellt, in dem Leerzeichen durch Bindestriche ersetzt werden, und das Thema wird dort anstelle des ursprünglichen Ordners gespeichert. (GUIDES-41938)
- Bei der ersten Übersetzung großer Zuordnungen werden leere XML-Dateien für die Zielsprache erstellt, was zu erhöhter Serverlast und langsamerer Leistung führt. (GUIDES-41613)
- Bei der Assets-Suche werden Teil-Assets und Metadatenknoten (z. B. Bilder und PDFs) fälschlicherweise in die Ergebnisse eingeschlossen. Darüber hinaus gibt die Suche für eine Ausgabevorgabe, wenn DITAVAL-Filter angewendet werden, intern generierte DITAVAL-Dateien zurück, die aus Bedingungsvorgaben erstellt wurden. (GUIDES-35418)
- Beim Hochladen von Assets mit Dateinamen, die ungültige Zeichen enthalten, kann das Asset nicht hochgeladen werden und es wird eine falsche Meldung angezeigt **Datei wird von anderen Benutzern gesperrt** obwohl das Asset entsperrt wurde. (GUIDES-32680)

## Publishing

- Beim Veröffentlichen einer DITA-Zuordnung mit Baseline auf AEM Sites (mit veralteter Komponentenzuordnung) werden auch die Zuordnungselemente mit dem Attribut `processing-role = resource-only` veröffentlicht. (GUIDES-37649)
- In einigen Fällen fehlt die `jcr:content/fmUuidOfSource`-Eigenschaft in den AEM Sites-Ausgabeseiten (mit veralteter Komponentenzuordnung), was dazu führt, dass neu erstellte Inhaltsseiten nicht auffindbar sind. (GUIDES-34242)
- Die Inhaltsfilterung über DITAVal-Filter und bedingte Vorgaben funktioniert für die Salesforce-Veröffentlichung nicht. (GUIDES-33515)
- Es kann keine native PDF-Voreinstellung für eine Zuordnung erstellt werden, wenn in der Inhaltshierarchie ein Ordner mit demselben Namen vorhanden ist. (GUIDES-33012)
- Wenn die native PDF-Ausgabe mithilfe einer dynamischen Baseline generiert wird, wird der **PDFProject** als PDF-Titel anstelle des eigentlichen Zuordnungstitels angezeigt. (GUIDES-31102)
- Das Generieren der nativen PDF-Ausgabe mit bestimmten `print` in Themenverweisen funktioniert nicht wie erwartet. (GUIDES-31101)
- Wenn ein Ordner, der DITA-Zuordnungen enthält, mithilfe der Benutzeroberfläche von Assets oder der Option **Massenverschieben** verschoben wird, können vorhandene Zuordnungssammlungen und Massenaktivierungssammlungen, die auf diese Zuordnungen verweisen, nicht geladen werden. (GUIDES-28355)
- Wenn Sie einen Ordner verschieben, der eine Zuordnung mit Bedingungsvorgaben enthält, werden die Bedingungen nach dem Verschieben nicht auf die generierte Ausgabe angewendet. (GUIDES-28352)
- Wenn Sie AEM Sites-Ausgaben mit der Zuordnung veralteter Komponenten generieren, werden Themen, die das `copy-to` verwenden, mit dem Namen des `copy-from` Themas anstelle des im `copy-to` festgelegten Namens veröffentlicht. (GUIDES-22155)
- Durch die Aktivierung einer oder mehrerer DITA-Zuordnungen über **Dashboard für die Massenveröffentlichung** werden zu große Protokolle generiert. (GUIDES-20746)
- Beim Generieren von PDFs werden die Filterregeln in einer DITAVAL-Datei ignoriert, wenn ein Eigenschaftsname einen Punkt enthält. (GUIDES-33229)
- Die Salesforce-Veröffentlichung zeigt in der Benutzeroberfläche den Status Erfolgreich an, auch wenn eine DITA-Zuordnung mit einem `topichead` die darin enthaltenen Themen nicht veröffentlichen kann. (GUIDES-32143)
- Für die HTML5-Ausgabevorgabe funktioniert die Suchfilterfunktion in AEM Assets nicht für die DITAVAL-Filterung, da die entsprechenden Dateien nicht angezeigt werden, wenn der DITAVAL-Filter ausgewählt ist. (GUIDES-28231)
- Wenn beim Generieren eines nativen PDF für eine DITA-Zuordnung mit mehreren Themen ein `fig` in einem `figgroup` zusammen mit einem `title` enthält, wird der `figgroup` fälschlicherweise als Kapiteltitel im Inhaltsverzeichnis gerendert. (GUIDES-23223)
- Beim Duplizieren von PDF-Vorlagen über die Benutzeroberfläche wird auch die UUID dupliziert, sodass Vorlagendateien gelöscht werden und PDF-Ausgaben falsch sind. (GUIDES-30456)
- Beim Generieren von nativem PDF für eine DITA-Zuordnung wird der Titel `example` Elements `h1` Überschriftenebene gerendert, was zu visueller Inkonsistenz und falscher Inhaltsverzeichnisstruktur führt. (GUIDES-19958)
- Wenn dasselbe Thema in mehreren Zuordnungen mit unterschiedlichen bedingten Voreinstellungen wiederverwendet wird, überschreibt die Veröffentlichung der neuesten Zuordnung in Salesforce den Themeninhalt, was dazu führt, dass Benutzenden zuvor veröffentlichter Zuordnungen falsche Daten angezeigt werden. (GUIDES-37806)
- Beim Veröffentlichen eines nativen PDF für eine Zuordnung, die eine bedingte Verarbeitung oder bestimmte verschachtelte Zuordnungen enthält, wird die in der Zuordnung definierte `dc:title` nicht auf dem PDF-Cover angezeigt, was zu einem fehlenden Cover-Titel führt. (GUIDES-37733)
- Das Generieren der AEM-Site-Ausgabe (mithilfe der Zuordnung zusammengesetzter Komponenten) für eine Zuordnung schlägt fehl und führt zu einem Fehler, wenn die `map_title` Variable im Ausgabepfad vorhanden ist. (GUIDES-36968)
- Wenn in der nativen PDF-Ausgabevorgabe ein Ausgabepfad mit einem Schrägstrich angegeben ist, fügt die Benutzeroberfläche automatisch einen zusätzlichen Schrägstrich hinzu, was zu einem doppelten Schrägstrich-Pfad führt, der in bestimmten Szenarien dazu führt, dass der PDF-Upload fehlschlägt. (GUIDES-34932)
- Das Veröffentlichen von AEM Sites-Seiten, die aus DITA-Inhalten durch Quick Publish oder Veröffentlichung verwalten generiert wurden, veröffentlicht unbeabsichtigt die zugehörigen DITA-Assets. (GUIDES-27967)
- Beim Veröffentlichen einer Zuordnung in AEM Sites (mithilfe der Zuordnung veralteter Komponenten) werden Querverweise (`xrefs`) mit `scope = peer`, die auf Unterelemente eines Themas (z. B. Absätze) in einer anderen Zuordnung abzielen, nicht auf die spezifische Element-ID aufgelöst, sondern nur auf das übergeordnete Thema. Dadurch wird die Seite am Anfang des Themas geladen, anstatt zum gewünschten Abschnitt zu scrollen. (GUIDES-21802)
- Beim Veröffentlichen einer DITA-Zuordnung mit Baseline auf AEM Sites (mit veralteter Komponentenzuordnung) werden auch die Zuordnungselemente mit dem Attribut `processing-role = resource-only` veröffentlicht. (GUIDES-34298)
- Wenn Änderungen an einer Ausgabevorgabe in einem Ordnerprofil auf bestehende Zuordnungen angewendet werden, wird der gespeicherte **Veröffentlichungskontext** für die AEM Sites-Vorgabe zurückgesetzt. (GUIDES-38377)
- Das Markensymbol (®) wird nicht auf der Titelseite der nativen PDF-Ausgabe gerendert, wenn das `tm` Element im Titel einer Zuordnung oder einer Lesekarte verwendet wird. (GUIDES-28832)
- Beim Veröffentlichen einer Zuordnung mit einer nativen PDF-Vorlage enthält der **Zuordnungstitel** keine Inhalte aus den untergeordneten Elementen, die in der `title` verwendet werden, und die entsprechende Inhaltsfilterung wird nicht auf den Titel angewendet. (GUIDES-33730)
- Kreuzzuordnungs-Peer-Links in der AEM Sites-Ausgabe können nicht aufgelöst werden, wenn sie auf einen `topicref` verweisen, der `chunk="to-content"` verwendet. (GUIDES-37873)
- Während der Veröffentlichung werden Dateien, die mit dem DITAVAL-basierten Flag verknüpft sind, in einen neuen systemgenerierten Ordner verschoben, anstatt an ihrem erwarteten relativen Speicherort in der Ausgabe zu bleiben. (GUIDES-37564)
- Wenn mehrere DITAVAL-Dateien mit widersprüchlichen Bedingungen verwendet werden, schlägt die native PDF-Ausgabe fehl. (GUIDES-37484)
- Beim Erstellen oder Bearbeiten eines Themas, das ein Zitat enthält, wird die PDF nicht generiert, wenn das Feld „Autor“ nicht im Zitatdialogfeld hinzugefügt wird. (GUIDES-37934)
- Beim Generieren der AEM Sites-Ausgabe werden die Zuordnungstitel, die Keywords und Thementitel mit `<ph>` Element enthalten, nicht in die veröffentlichte Ausgabe aufgenommen. (GUIDES-36641)
- Die CSS-Datei (`rhdefault.css`) wird falsch auf die PDF-Vorlage angewendet, obwohl kein CSS referenziert wird, was zu fehlenden CSS-Datei-Fehlerprotokollen führt. (GUIDES-31752)
- Beim Herunterladen temporärer Dateien für eine Zuordnung mit einer Grundlinie während der Veröffentlichung einer Vorgabe verweist die `metadata.xml`-Datei fälschlicherweise auf die `versionPath` statt auf die `dampath`. (GUIDES-29815)
- Für die native PDF-Ausgabe wird das `<alt>` für Bilder ignoriert, was verhindert, dass alternativer Text auf die Barrierefreiheit angewendet wird. (GUIDES-29087)
- In der nativen PDF-Ausgabe zeigt das `abbreviated-form` die `glossterm` anstelle der angegebenen `glossSurfaceForm` oder `glossAcronym` an. (GUIDES-26393)
- Bei der Massenaktivierung fügt die Paketerstellung Filter für alle Pfade hinzu, die unter der `fileReference`-Eigenschaft einer Seite aufgeführt sind, einschließlich externer und Peer-Pfade. (GUIDES-24887)
- Beim Veröffentlichen mit einer benutzerdefinierten Vorgabe mit Inhalten, die Links zu PDFs ohne den als extern festgelegten Umfang enthalten, kann der Prozess nicht abgeschlossen werden. (GUIDES-21708)
- Die Salesforce-Veröffentlichung schlägt mit einem Anwendungsfehler fehl, wenn bereits ein Thema mit demselben Namen und derselben URL vorhanden ist. (GUIDES-32390)
- Die automatische Silbentrennung wird in der nativen PDF-Ausgabe nicht angewendet, selbst wenn die Einstellung **Automatische Silbentrennung verwenden** für die Ausgabevorgabe aktiviert ist. (GUIDES-19703)

## Übersetzung

- Beim Vergrößern des Bildschirms der Übersetzungs-Benutzeroberfläche bewegt sich die Schaltfläche **Zur Übersetzung senden** unter den Auslassungspunkten und wird aktiviert, auch ohne dass ein Asset ausgewählt wird. (GUIDES-33720)
- Bei der Auswahl von Dateien **Status** Nicht synchronisiert“ in der Übersetzungs-Benutzeroberfläche und eingeschränkter Bildschirmbreite aufgrund geöffneter linker und rechter Bedienfelder wird die Beschriftung **Zur Übersetzung senden** abgeschnitten. (GUIDES-33692)
- Wenn ein Bild, das anfänglich als sprachspezifisches Asset mit einer bestimmten Version verwaltet wurde (z. B. unter `/en/`), in einen globalen Ordner mit einer aktualisierten Version verschoben und ein Baseline-Export durchgeführt wird, verweist die neue Baseline weiterhin auf veraltete sprachspezifische Versionen dieses Bildes, was zu einem fehlgeschlagenen Baseline-Export führt. (GUIDES-39394)
- Bei der Verarbeitung von Übersetzungsprojekten, die außerhalb von Experience Manager Guides erstellt wurden, werden mehrere Fehlerprotokollmeldungen generiert, die darauf hinweisen, dass *`fmTarget`Eigenschaft nicht gefunden*. (GUIDES-37804)

## Grundlinie

- Beim Erstellen einer dynamischen Baseline reagiert der Editor manchmal aufgrund mehrerer gleichzeitiger API-Anfragen nicht mehr, wodurch alle anderen Vorgänge angehalten werden. (GUIDES-39054)
- Themenreferenzen innerhalb einer Zuordnung werden bei Verwendung eines benutzerdefinierten DITA-OT fälschlicherweise als indirekt angezeigt, obwohl sie direkt referenziert werden. Dieses Problem wurde mit der neuen Basiserfahrung behoben. (GUIDES-19286)
- Verweise mit `scope="peer"` werden fälschlicherweise in den Grundlinienkontext eingeschlossen, sodass die Veröffentlichung länger dauert als erwartet. Dieses Problem wurde mit der neuen Basiserfahrung behoben. (GUIDES-41823)


## Überprüfung

- Beim Zuweisen eines Benutzers zu einer Prüfungsaufgabe werden in der Dropdown-Liste alle Benutzer und nicht nur die mit den ausgewählten Projekten verknüpften aufgelistet, was zu ungültigen Benutzeroptionen führt. (GUIDES-37781)
- Wenn ein Reviewer eine Überprüfungsaufgabe abschließt oder der Initiator die Überprüfungsaufgabe aktualisiert, ohne Kommentare einzugeben, zeigt die gesendete Benachrichtigungs-E-Mail den letzten vorherigen Kommentar an. (GUIDES-33590)

## Berichte

- Beim Öffnen eines Berichts für eine Zuordnung tritt beim Laden des Bedienfelds „Filter“ eine Verzögerung auf (GUIDES-39385)
- Der Bericht Beschädigte Liste enthält fälschlicherweise externe Links, gültige `keyrefs` und Schlüsselwörter, die im Rahmen der aktuellen Zuordnung ordnungsgemäß aufgelöst werden. (GUIDES-27774)

## Platform

- Fehlerprotokolle, die beim Hochladen eines Assets über die Assets-Benutzeroberfläche oder beim Erstellen einer neuen Datei über die Editor-Benutzeroberfläche generiert werden, verwenden fälschlicherweise den Begriff `predecessor` anstelle von `successor` in der Protokollmeldung. (GUIDES-35607)
- Wenn Sie `scope="external"` für einen Verweis auf DAM-Inhalte in einem Thema oder einer Zuordnung verwenden, wird der relative Pfad des Assets durch eine GUID ersetzt. (GUIDES-38783)
- Wenn ein Thema eine große Anzahl von Verweisen enthält, die von Ordnern mit vielen Dateien verknüpft sind, kann die Autoreninstanz langsam werden oder nicht mehr reagieren. In einigen Fällen ist ein Neustart der Instanz erforderlich. (GUIDES-43547)
- Beim Versuch, ein Thema oder eine Zuordnung zu speichern, kann der Vorgang gelegentlich mit einem Fehler **Datei konnte nicht gespeichert werden** fehlschlagen, insbesondere während intensiver Asset-Verarbeitungsaufgaben oder Übersetzungs-Workflows, die im Hintergrund ausgeführt werden. (GUIDES-37837)


## Gelöste Probleme mit Editor 2.0

Die folgenden Probleme wurden behoben und treten bei Verwendung des Editors 2.0 (auch als neuer Editor bezeichnet) nicht mehr auf:

- Wenn zwei oder mehr Spalten aus einer Tabelle gelöscht werden, wird die Tabellenstruktur inkonsistent oder beschädigt. (GUIDES-35438)
- Wenn eine Spalte aus einer Tabelle gelöscht wird, die zusammengeführte Zellen enthält, wird eine neue leere Spalte hinzugefügt. (GUIDES-30147)
- Wenn eine neue Zeile aus dem Breadcrumbs-Menü in eine vorhandene Tabelle eingefügt wird, ändert sich die Tabellenstruktur unerwartet, was zu fehlenden Rahmen und einer zusätzlichen Spalte führt. (GUIDES-29194)
- Durch Kopieren und Einfügen einer Tabellenzeile wird der Inhalt in der Autorenansicht außerhalb der Tabelle platziert, anstatt ihn als neue Zeile in die Tabelle einzufügen. (GUIDES-24372)
- Wenn ein im Autorenmodus mit dem Mauszeiger ausgewähltes Schnittelement kopiert und eingefügt wird, wird es in `(<p>)` umgewandelt, anstatt die Abschnittsstruktur beizubehalten. (GUIDES-30023)
- Wenn markierter Text innerhalb von Elementen wie „step“ oder „uicontrol“ bearbeitet wird, wird der ausgewählte Text nicht korrekt ersetzt, sondern an den Text angehängt oder ihm vorangestellt, was zu Validierungsfehlern führt. (GUIDES-24371)
- Wenn eine Tabellenspaltenbreite mit relativen Werten festgelegt wird, werden die übrigen Spalten nicht proportional angepasst, was zu einem falsch ausgerichteten Tabellen-Layout führt. (GUIDES-26109)
- Wenn ein kopierter Thementitel eingefügt und Tags deaktiviert sind, wird beim ersten Einfügen ein falscher Stil angewendet und der Typ in den Inhaltseigenschaften als Thema anstelle des Titels zugewiesen. (GUIDES-28838)
- Wenn große Inhaltsbereiche bearbeitet werden, führt eine unbeabsichtigte Bildlaufbewegung dazu, dass die Editor-Ansicht vom aktiven Inhalt weg springt. (GUIDES-35436)
- Wenn die Rücktaste für Elemente verwendet wird, scrollt der Editor unabhängig von der Cursorposition zum Anfang des Themas. (GUIDES-32520)
- Wenn mit der Nach-links- oder Nach-rechts-Taste aus Inline-Tags heraus gewechselt wird, springt der Cursor beim ersten Versuch unerwartet. (GUIDES-26363)
- Die AEM-Rechtschreibprüfung funktioniert nur für die Standardsprache en-US und berücksichtigt keine anderen Gebietsschemata. (GUIDES-14731)
- Wenn große DITA-Themen im Editor entsperrt werden, wird dasselbe Thema erneut in einer doppelten Registerkarte geöffnet. Darüber hinaus wird eine Warnung zu Tag-Grenzwerten ausgelöst, bei der anstelle der tatsächlichen Tag-Anzahl `NaN` angezeigt wird. (GUIDES-34008)
- Acrolinx-Vorschläge werden im Editor für schreibgeschützte oder gesperrte Themen nicht korrekt hervorgehoben. (GUIDES-29614)
- Beim Erstellen eines neuen `reltable` ohne Kopfzeile in der Autorenansicht ändert sich das Tabellenlayout, nachdem ein Thema zur ersten Zelle hinzugefügt wurde. Dadurch wird die nächste Spalte ausgeblendet, was die Platzierung verwandter Themen erschwert. (GUIDES-19555)
- Wenn eine `xref` Relation zu einer kleinen Tabellenzelle im Autorenmodus hinzugefügt wird, bleibt die Relation nicht in der Zelle enthalten und wird über benachbarte Zellen in derselben Zeile angezeigt. (GUIDES-5489)
- Beim Wechseln von der Authoring- zur Source-Ansicht wird die Cursorposition nicht beibehalten und der Editor scrollt zurück nach oben. Darüber hinaus geht in langen Themen die Cursorposition verloren und springt beim Wechseln zwischen Authoring- und Source-Ansichten zufällig in die Mitte oder nach oben. (GUIDES-18114, GUIDES-21164)
- Wenn Sie *Eingabetaste* innerhalb eines `<li>` Elements drücken, wird ein neues `<li>` erstellt, aber durch Zurücknavigieren zu einem vorherigen `<li>` und Drücken der *Eingabetaste* wird der Inhalt des aktuellen Elements fälschlicherweise in ein `<p>` Element konvertiert, wodurch die Listenstruktur beschädigt wird. (GUIDES-27505)

## Bekannte Probleme

### Authoring

- Beim Hochladen von gekennzeichneten Bildern in DITAVAL-Dateien werden die Bilder nach einer Browser-Aktualisierung beschädigt, wenn die `Enable UUIDs` deaktiviert ist. (GUIDES-45853)
- Im Editor können `.ditval`- und `.md`-Dateien nicht mehr bearbeitet werden, wenn *Genehmigungs-Workflow* aktiviert ist. (GUIDES-42037)
- Wenn Sie ein Thema im Vorschaumodus auswählen, wird es in der Zuordnungsansicht nicht hervorgehoben, wenn das Thema in Bookmap-Tags (Frontmatter, Kapitel, Teil oder Batter) oder Teil von zyklischen Inhalten ist. (GUIDES-42416)
- Wenn eine Datei sowohl im Editor als auch im Suchbereich geöffnet ist, wird beim Löschen aus dem Explorer-Bereich die Datei entfernt und die Explorer-Liste aktualisiert. Beim Aktualisieren der Seite wird die Datei jedoch weiterhin im Suchbereich angezeigt. (GUIDES-41935)

### Asset-Management

- In der Assets-Benutzeroberfläche wird **Schaltfläche „Verschieben** beim ersten Versuch nicht aktiviert, wenn mehr als zwei Dateien oder Ordner ausgewählt sind. (GUIDES-42721) <br> **Problemumgehung**: Nachdem Sie mehr als zwei Dateien oder Ordner ausgewählt haben, warten Sie einige Sekunden, bevor Sie den Zielordner auswählen.

### Überprüfung

- Wenn beim Aktualisieren einer aktiven Prüfungsaufgabe ein Thema, das bereits Teil der Überprüfung ist, entfernt und dann erneut hinzugefügt wird, ohne auf Aktualisieren zu klicken, gehen die Informationen zu Überprüfenden auf der Registerkarte Überprüfende verloren. (GUIDES-38774)
- Wenn ein zu überprüfendes Thema aus einer laufenden Prüfungsaufgabe entfernt wird, bleibt sein Dokumentstatus weiterhin **In Überprüfung**, auch wenn das Thema nicht mehr Teil einer Prüfungsaufgabe ist. (GUIDES-38709)<br>**Problemumgehung**: Ändern Sie den Dokumentstatus des Themas von **In Überprüfung** in den entsprechenden Status auf der Seite Eigenschaften oder im Bedienfeld Dateieigenschaften .

### Editor 2.0

- Durch Kopieren und Einfügen von Inhalten im selben Thema an eine ungültige Stelle im Editor wird ein unbeabsichtigtes fremdes Tag eingefügt. (GUIDES-45378)
- Durch Kopieren und Einfügen von `<keywords>` in `<topicmeta>` innerhalb von `<keydef>` oder `<topicref>` werden unbeabsichtigte fremde Tags eingefügt. (GUIDES-45800)
- Wenn Inhalte mit der Option Kopieren im Kontextmenü aus einer Karte oder einem Thema kopiert und dann eingefügt werden, werden unerwartete zusätzliche `<data>`-Tags in den eingefügten Inhalt eingefügt. (GUIDES-45703)
- Unter Windows werden durch Kopieren und Einfügen einer Tabellenzeile unerwünschte Attribute zur Tabelle hinzugefügt, was zu Markupfehlern führt und das Speichern des Dokuments verhindert. (GUIDES-45784)
- Auswahl durch Ziehen um eine Tabelle oder einfache Tabelle funktioniert nicht wie erwartet. (GUIDES-45406)
- Bilder aus externen Quellen werden nicht in das Thema eingefügt. (GUIDES-45983)
- MathML-Inhalte, auf die über `conref` verwiesen wird, werden nicht korrekt dargestellt. (GUIDES-46601)
- Beim unvollständigen Attribut-Rendering für MathML- und SVG-Elemente werden benutzerdefinierte CSS-Klassen und die Behandlung von Bedingungsattributen unterbrochen. (GUIDES-46371)
- MathML-Gleichungen, die in `foreign`- und `equation-block`-Tags eingeschlossen sind, führen zu unerwünschten Leerzeichen und stören das Bearbeitungsverhalten. (GUIDES-46606)
- Durch Ziehen und Ablegen eines Elements, das einen Schlüsselverweis enthält, wird der `keyref` in einen absoluten Pfad umgewandelt. (GUIDES-45701)
- Im Zuordnungs-Editor wird bei der `Ctrl+click` eines fehlerhaften Links ein Anwendungsfehler Trigger. (GUIDES-45544)
