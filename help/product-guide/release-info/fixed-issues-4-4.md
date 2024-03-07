---
title: Versionshinweise | Behobene Probleme in Version 4.4.0 der Adobe Experience Manager-Handbücher
description: Erfahren Sie mehr über die Fehlerbehebungen in der Version 4.4.0 der Adobe Experience Manager-Handbücher.
role: Leader
source-git-commit: 8f8075b205725a55b93286c804b879353b4d965d
workflow-type: tm+mt
source-wordcount: '1434'
ht-degree: 0%

---

# Behobene Probleme in Version 4.4.0 (Januar 2024)


Dieser Artikel behandelt die Fehler, die in verschiedenen Bereichen der Version 4.4.0 von Adobe Experience Manager Guides behoben wurden.

Weitere Informationen zu den neuen Funktionen und Verbesserungen finden Sie unter [Neue Funktionen in Version 4.4.0](./whats-new-4-4.md).

Informationen zu [Upgrade-Anweisungen für Version 4.4.0](../release-info/upgrade-instructions-4-4.md).


## Authoring

- Die Rechtschreibprüfung im Editor lässt die Auswahl von Vorschlägen nicht zu. (15045)
- Die globale Navigationsschaltfläche funktioniert nicht und das Dashboard kann nicht geladen werden. (14968)
- Im Web Editor kann die Download-Zuordnungsfunktion keine Popup-Benachrichtigung Trigger werden, wenn sie zum Herunterladen bereit ist. (14626)
- Im Web Editor kann die Funktion zum Herunterladen von Landkarten keine Landkarte mit Grundlinie herunterladen. (14622)
- Ungültiger DTD-Fehler in den Experience Manager-Handbüchern. (14482)
- Der Titel auf der Registerkarte &quot;Web Editor&quot;wird nach einem Punkt (.) Zeichen. (14372)
- Fehlermeldungen für doppelte Zuordnungsnamen in der Assets-Benutzeroberfläche werden nicht aktualisiert. (14320)
- Bei der Versionserstellungslogik tritt beim Ziehen und Ablegen von Assets ein Fehler auf. (14291)
- Wiederverwendbarer Inhalt überspringt die Element-IDs. (14213)
- Das Einstellungssteuerelement zum Ausblenden **Sprachvariablen** Bereich unter **Ausgabe** fehlt. (14194)
- Der Web Editor gibt Anwendungsfehler aus, wenn ein neuer Verweis oder Thema mithilfe eines speziellen Schemas in der **Layout** anzeigen. (14094)
- Das Leerzeichen nach conref `<ph>` -Element beim Speichern des Themas verschwindet. (13642)
- Beim Versuch, DITA-Dateien zu speichern, bevor die Nachbearbeitung abgeschlossen ist, tritt ein Anwendungsfehler auf. (13571)
- Ein Ankerlink zu `<dlentry>` oder `<dt>` -Element kann den Link-Text nicht anzeigen. (13543)
- Die **Favoriten** -Sammlung im Web-Editor kann nicht geladen werden. (13495)
- Wenn der Titel eines Themas einen Schrägstrich enthält `/`, zeigt die Registerkarte im Web Editor nur die Buchstaben an, die danach folgen. (13455)
- Die Bildvorschau wird nach der Anzeige der Vorschau im Web Editor nicht ausgeblendet. (13454)
- Zitate zeigen nicht anklickbare Links an, wenn sie mit einer eindeutigen ID mit Leerzeichen erstellt werden. (13447)
- Wenn Sie ein Thema nach der Bearbeitung schließen, werden Sie zur AEM-Startseite weitergeleitet, anstatt zur Ordneransicht zurückzukehren. (13306)
- Das Popup-Fenster &quot;Keyword einfügen&quot;wird nicht angezeigt, wenn in anderen Themen Schlüssel mit der root-Map verwendet werden. (12950)
- Schließen-Symbole sind nicht sichtbar, wenn sehr große Grafiken in der Vorschau der **Versionsverlauf** Bedienfeld. (12867)
- Die Zeitzone von kann nicht geändert werden **Version erstellt am** für die Grundlinien. (12711)
- ZIP-Dateien werden im Web Editor nicht erkannt und können nicht per Drag-and-Drop eingefügt werden. (12709)
- Die **Versionsverlauf** in der Assets-Benutzeroberfläche einen falschen Zeitstempel für die **Aktuell** -Feld. (12624)
- Im **Layout** Ansicht für eine Lesekarte mit **Nach rechts** , um ein ausgewähltes Kapitel zu einem Unterelement zu machen, das nicht funktioniert. (12567)
- Das Erstellen einer DITA-Datei aus einer Vorlage mit einem Dateinamen, der mit numerischen Zeichen beginnt, führt zu einem Namespace-Fehler. (12188)
- Die Rootmap-Einstellung bleibt im Web Editor erhalten, auch wenn der Benutzer sie nicht explizit im **Benutzereinstellungen**. (11551)
- Der Inhalt mit einigen angewendeten Attributen wird in **Autor** oder **Vorschau** -Modus. (11063)
- Im Web-Editor wird die **Schlüsselverweise** beim Einfügen des `varname` -Tag. (10940)
- Wenn Sie ein Glossarthema aus dem Repository in eine Glossarzuordnung ziehen, wird `topicref`. (10767)
- Das Vorschaufenster des XML-Editors wird in Google Chrome- und Microsoft Edge-Browsern abgeschnitten. (10755)
- Der Web Editor kann ein Element nicht in die möglichen übergeordneten Elemente einschließen. (8791)
- Der Web Editor wird nach der Neuinstallation von Adobe Experience Manager Guides Version 4.3.1 deinstalliert. (14519)
- Beim Installationsprogramm von Version 4.3.1 tritt ein Filterkonflikt auf, der dazu führt, dass `apps/cq/core/content/projects/properties`. (14517)
- Unter der Liste von **Beschädigte Links** in Berichten. (13539)
- Der Vorschaubildschirm für Snippets ist gesperrt. (14840)
- Beim Erstellen der Codefragmente in koreanischer Sprache werden ungültige Zeichen angezeigt. (13489)

## Veröffentlichung

- AEM Sites-Veröffentlichung schlägt fehl und verursacht Bereichsfehler bei Dateien mit `xref` in die DITA-Datei, die mit &quot;HTTP&quot;beginnt. (15154)
- Bei der nativen PDF-Veröffentlichung können die DITA-Map-Metadateneigenschaften nicht zum Ausfüllen der Metadaten für die PDF-Dateiausgabe verwendet werden. (15159)
- Bei der nativen PDF-Veröffentlichung funktionieren benutzerdefinierte Attribute innerhalb von Bedingungsvorgaben nicht für die native PDF-Veröffentlichung. (14943)
- Benutzerdefinierte Vorlage kann nicht aus der **Ausgaben** im Editor. (14846)
- **AEM Site** aufgrund eines leeren Vorlagenpfads nicht funktioniert. (14804)
- AEM Neuerstellung der Site schlägt bei DITA-Maps mit Themen fehl, die MathML-Gleichungen enthalten. (14790)
- Bei nativer PDF-Veröffentlichung gibt die PDF-Generierung Fehler beim Abrufen von Abhängigkeiten für aus `Node.js` Publishing. (14445)
- **AEM Site** -Vorgabe erlaubt nicht die Auswahl einer Vorlage außerhalb der `/content` Hierarchie im Web-Editor. (14260)
- Die Funktion zum Veröffentlichen als Inhaltsfragment funktioniert nicht für Dateien, die in den Suchergebnissen aufgelistet sind. (14090)
- Fmdita-Komponenten haben einen fest programmierten Pfad von `delegator.jsp`verhindert die Überlagerung von AEM Sites-Komponenten. (13993)
- Die getaggte Ansicht des PDF-Reaktors in der Ausgabe der nativen PDF-Veröffentlichung funktioniert nicht erwartungsgemäß. (13622)
- Bei nativer PDF-Veröffentlichung die Hintergrundfarbauswahl auf der **Vorlage** Das Layout erfordert eine erneute Ladezeit der Seite, wenn auf `None`. (13621)
- AEM Site-Veröffentlichung tritt beim Übertragen an den Datenspeicher für große Maps mit Perimeter-Peer-Links auf ein Problem auf. (13531)
- Es tritt ein Problem beim Übertragen auf den Datenspeicher für eine große DITA-Zuordnung mit Perimeter-Links in AEM Site-Veröffentlichung auf. (13530)
- Falsches Symbol und falsche QuickInfos werden angezeigt für  **Inhalt bearbeiten** in der **Seitenlayouts** Symbolleiste der Vorlagen, die bei der nativen PDF-Veröffentlichung verwendet werden. (13492)
- Website kann nicht mithilfe von Experience Manager-Handbüchern aktiviert werden **Massen-Veröffentlichungs-Dashboard**. (13439)
- Bei der nativen PDF-Veröffentlichung ist die Barrierefreiheit beeinträchtigt, da Bilder in der Kopf- und Fußzeile keinen alternativen Text anzeigen. (12829)
- In der AEM Sites-Ausgabe gingen der Stil oder die Zeilenumbrüche für die `<lines>` -Element mit Unterelementen.(12542)
- Das Duplizieren des Seitenlayouts im nativen PDF funktioniert nicht, ohne dass automatisch eine Erweiterung hinzugefügt wird. (12534)
- Die Lokalisierung der Elementbeschriftungen funktioniert in der AEM Sites-Ausgabe nicht ordnungsgemäß. (12144)
- Benutzerdefinierte Metadaten sind in der endgültigen Ausgabe nicht verfügbar. (12116)
- `fmdita rewriter` führt zu Konflikten mit der Rewriter-Konfiguration des Benutzers und zur Anzeige langer URLs anstelle der Links. (12076)
- Fehlt **Ditaval** -Option in Ausgabevorgaben auf Ordnerprofilebene, die über die Benutzeroberfläche des Web-Editors erstellt wurden. (1903)
- Im **AEM Site**  voreingestellt, die Option **Separate PDF für jedes Thema generieren** nicht funktionsfähig ist. (11555)
- Für die Konvertierung von CMYK-Farbräumen wird bei der nativen PDF-Veröffentlichung nicht unterstützt. 10754)
- Beim Upgrade auf Version 4.3.1 treten im Knoten Native PDF einige Ausnahmen auf. (14492)
- Beim Generieren der PDF-Ausgabe mit nativer PDF-Veröffentlichung wird der Dateiname nach einem Punkt abgeschnitten. (13620)


## Verwaltung

- Die Inhaltsreferenz beim Kopieren und Einfügen der DITA-Dateien mit Selbstverweis-Links ohne GUID ist fehlerhaft. (13540)
- **Baseline-Filter** -Dateien funktionieren nicht mit dem Dateinamen im Web-Editor. (13486)
- Im Web-Editor zeigt die Grundlinie den Titel der vorherigen Version anstelle der ausgewählten Version der DITA-Datei an. (13444)
- Die Deaktivierung der Indizierung der übergeordneten DITA-Zuordnung, um eine bessere Leistung zu erzielen, kann sich auf die Funktionalität bestimmter Funktionen auswirken.(12213)
- Bedingungsvorgaben für große DITA-Maps werden nicht erstellt. (10936)
- Die Vorgaben für die ersten Zuordnungen der Sammlung können beim Bearbeiten einer Zuordnungssammlung nicht bearbeitet werden. (10649)
- Beschriftungen aus der `labels.json` -Datei in zufälliger Reihenfolge im Web-Editor angezeigt. (10508)
- Dynamische Grundlinien-Aufrufe verwenden den Namen anstelle des Titels, was zu einem Fehler bei der Export von DITA Map-API führt. (14268)

## Überprüfung

- Kontextmenü mit Rechtsklick funktioniert nicht für **Accept** oder **Ablehnen** Änderungen verfolgen. (14607)
- Das Umschalten zum Schließen von DITA-Themen im Überprüfungsbildschirm funktioniert in Version 4.3.1 der Adobe Experience Manager-Handbücher nicht. (14537)
- Symmetrische Probleme treten in den seitlichen Überprüfungsfeldern der vorherigen und der aktuellen Versionen im Web Editor auf. (14156)
- Das Anpassen von E-Mail-Vorlagen für den Review-Workflow funktioniert nicht mit Überlagerungen. (13954)
- Koreanische Anlagen im Bildschirm &quot;Überprüfung der Experience Manager-Guides&quot;können nicht angeklickt werden. (13436)
- Der Titel der Karte wird im Bildschirm für Überprüfung und Zusammenarbeit abgeschnitten, ohne dass eine Option zum Anzeigen des vollständigen Titels verfügbar ist. (13012)

## Übersetzung

- Die **Akzeptieren/Ablehnen** Fehlerhafte Schaltflächen werden für die automatische menschliche Übersetzung angezeigt. (14318)
- Internationalisierungsprobleme (i18n) treten während der Transformation nicht-englischer DITA-Dateien auf AEM Seiten auf. (14286)
- Die automatische Genehmigung funktioniert manchmal nicht und es treten Ausnahmen auf, wenn ein falscher Wert auf **Übersetzungsstatus**. (13607)
- Die über das Dashboard &quot;Übersetzung&quot;exportierte Grundlinie schlägt fehl und wird nicht in der Zielsprache geöffnet. (12993)
- Übersetzte Inhalte können nicht mit temporären Übersetzungsprojekten synchronisiert werden, und der DITA XML-Editor-Übersetzungs-Assistent zeigt fälschlicherweise **Gestartet** Status für genehmigte Aufträge. (9938)

## Bekanntes Problem

Adobe hat das folgende bekannte Problem für die Version 4.4.0 identifiziert:

- Version 1.0 wird nicht auf der Benutzeroberfläche für die duplizierte DITA-Datei angezeigt.