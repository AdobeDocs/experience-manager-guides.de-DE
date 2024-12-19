---
title: Versionshinweise zu | Es wurden Probleme in Adobe Experience Manager Guides Version 4.4.0 behoben
description: Erfahren Sie mehr über die Fehlerbehebungen in Version 4.4.0 von Adobe Experience Manager Guides
role: Leader
exl-id: ff3083d3-062b-4a79-875f-86991978a18e
source-git-commit: e40ebf4122decc431d0abb2cdf1794ea704e5496
workflow-type: tm+mt
source-wordcount: '1434'
ht-degree: 0%

---

# Es wurden Probleme in Version 4.4.0 (Januar 2024) behoben


Dieser Artikel behandelt die in verschiedenen Bereichen von Version 4.4.0 von Adobe Experience Manager Guides behobenen Fehler.

Weitere Informationen zu den neuen Funktionen und Verbesserungen finden Sie unter [Neue Funktionen in Version 4.4.0](./whats-new-4-4.md).

Erfahren Sie mehr [Upgrade-Anweisungen für Version 4.4.0](../release-info/upgrade-instructions-4-4.md).


## Authoring

- Die Rechtschreibprüfung im Editor erlaubt keine Auswahl von Vorschlägen. 15045)
- Die Schaltfläche für die globale Navigation funktioniert nicht und das Dashboard kann nicht geladen werden. 14968)
- Im Web-Editor kann mit der Funktion „Zuordnung herunterladen“ keine Popup-Benachrichtigung Trigger werden, wenn sie zum Herunterladen bereit ist. 14626)
- Im Web-Editor kann mit der Funktion „Karte herunterladen“ keine Karte mit Grundlinie heruntergeladen werden. 14622)
- Ungültiger DTD-Fehler in der Experience Manager Guides. 14482)
- Der Titel auf der Registerkarte „Webeditor“ wird nach einem Punkt (.) abgeschnitten. 14372)
- Die Fehlermeldung für doppelte Zuordnungsnamen in der Assets-Benutzeroberfläche wird nicht aktualisiert. 14320)
- Bei der Versionserstellungslogik tritt während des Drag-and-Drop von Assets ein Fehler auf. 14291)
- Wiederverwendbarer Inhalt überspringt die Element-IDs. 14213)
- Das Einstellungssteuerelement zum Ausblenden des **Sprachvariablen** Bedienfelds auf **Ausgabe**-Registerkarte fehlt. 14194)
- Der Web-Editor gibt Anwendungsfehler aus, wenn ein neuer Verweis oder ein neues Thema mithilfe eines speziellen Schemas in der Layout **Ansicht hinzugefügt**. 14094)
- Das Leerzeichen nach dem `<ph>` conref-Element verschwindet beim Speichern des Themas. 13642)
- Beim Versuch, DITA-Dateien zu speichern, bevor die Nachbearbeitung abgeschlossen ist, tritt ein Anwendungsfehler auf. 13571)
- Ein Ankerlink zu `<dlentry>` oder `<dt>` Element zeigt den Link-Text nicht an. 13543)
- Die **Favoriten**-Sammlung im Web-Editor kann nicht geladen werden. 13495)
- Wenn der Titel eines Themas einen Schrägstrich `/`, werden auf der Registerkarte im Web-Editor nur die nachfolgenden Briefe angezeigt. 13455)
- Die Bildvorschau verschwindet nicht, nachdem die Vorschau im Web-Editor angezeigt wurde. 13454)
- Zitate zeigen nicht anklickbare Links an, wenn sie mit einer eindeutigen ID mit Leerzeichen erstellt wurden. 13447)
- Wenn Sie ein Thema nach der Bearbeitung schließen, werden Sie zur AEM-Startseite weitergeleitet, anstatt zur Ordneransicht zurückzukehren. 13306)
- Das Popup-Fenster zum Einfügen von Keywords wird nicht angezeigt, wenn in anderen Themen Schlüssel verwendet werden, die für die Stammzuordnung definiert sind. 12950)
- Schließen-Symbole sind nicht sichtbar, wenn sehr hohe Grafiken im Bedienfeld **Versionsverlauf** in der Vorschau angezeigt werden. 12867)
- Die Zeitzone der Spalte **Version erstellt am** für die Baselines kann nicht geändert werden. 12711)
- Zip-Dateien werden im Web-Editor nicht erkannt und können nicht per Drag-and-Drop eingefügt werden. 12709)
- Das **Versionsverlauf** in der Assets-Benutzeroberfläche zeigt einen falschen Zeitstempel für das Feld **Aktuell** an. 12624)
- In der **Layout**-Ansicht für eine Bookmap funktioniert die Verwendung von **Nach rechts verschieben**, um ein ausgewähltes Kapitel zu einem Unterelement zu machen, nicht. 12567)
- Das Erstellen einer DITA-Datei aus einer Vorlage mit einem Dateinamen, der mit numerischen Zeichen beginnt, führt zu einem Namespace-Fehler. 12188)
- Die Rootmap-Einstellung bleibt im Web-Editor erhalten, auch wenn sie nicht explizit in den **Benutzereinstellungen“ festgelegt**. 11551)
- Der Inhalt mit einigen angewendeten Attributen wird im **Autor** oder **Vorschau** nicht hervorgehoben. 11063)
- Im Web-Editor wird das Fenster **Schlüsselverweise** beim Einfügen des `varname`-Tags geöffnet. 10940)
- Wenn Sie ein Glossarthema aus dem Repository in eine Glossarzuordnung ziehen, wird `topicref` erstellt. 10767)
- Das Vorschaufenster des XML-Editors ist in den Browsern Google Chrome und Microsoft Edge abgeschnitten. 10755)
- Dem Web-Editor fehlt die Fähigkeit, ein Element in die möglichen übergeordneten Elemente einzuschließen. (8791)
- Der Web-Editor wird nach der Neuinstallation von Adobe Experience Manager Guides Version 4.3.1 deinstalliert. 14519)
- Das Installationsprogramm von Version 4.3.1 stößt auf einen Filterkonflikt, der dazu führt, dass `apps/cq/core/content/projects/properties` überschrieben wird. 14517)
- Unter der Liste der (fehlerhaften Links **in Berichten wird ein** angezeigt. 13539)
- Der Vorschaubildschirm für Snippets ist eingefroren. 14840)
- Beim Erstellen der Snippets in koreanischer Sprache werden fehlerhafte Zeichen angezeigt. 13489)

## Veröffentlichung

- Die AEM Sites-Veröffentlichung schlägt fehl und verursacht Bereichsfehler für Dateien, die mit der DITA-Datei `xref` sind, die mit „HTTP“ beginnt. 15154)
- In der nativen PDF-Veröffentlichung können die Metadateneigenschaften der DITA-Zuordnung nicht zum Ausfüllen der Metadaten für die PDF-Dateiausgabe verwendet werden. 15159)
- In der nativen PDF-Veröffentlichung funktionieren benutzerdefinierte Attribute innerhalb von Bedingungsvorgaben nicht für die native PDF-Veröffentlichung. 14943)
- Es kann keine benutzerdefinierte Vorlage über die Registerkarte **Ausgaben** im Editor hinzugefügt werden. 14846)
- **AEM-Site**-Voreinstellung funktioniert nicht, da der Vorlagenpfad leer ist. 14804)
- Die AEM-Site-Regenerierung schlägt für DITA-Zuordnungen mit Themen fehl, die MathML-Gleichungen enthalten. 14790)
- Bei der nativen PDF-Veröffentlichung gibt die PDF-Generierung Fehler beim Abrufen von Abhängigkeiten für die `Node.js`-Veröffentlichung aus. 14445)
- Die Vorgabe für **** AEM-Site`/content` erlaubt keine Auswahl einer Vorlage außerhalb der Vorlagenhierarchie im Web-Editor. 14260)
- Die Funktion zum Veröffentlichen als Inhaltsfragment funktioniert nicht für Dateien, die in Suchergebnissen aufgelistet sind. 14090)
- FMDITA-Komponenten haben einen hartcodierten Pfad von `delegator.jsp`, der die Überlagerung von AEM Sites-Komponenten verhindert. 13993)
- Die getaggte Ansicht von PDF Reactor in der nativen PDF-Veröffentlichungsausgabe funktioniert nicht wie erwartet. 13622)
- Bei der nativen PDF-Veröffentlichung ist für die Hintergrundfarbauswahl im Layout **Vorlage** beim Zurücksetzen auf `None` ein erneutes Laden der Seite erforderlich. 13621)
- Bei der AEM-Site-Veröffentlichung tritt beim Übertragen großer Zuordnungen mit Umfang und Peer-Links ein Problem auf. 13531)
- Problem beim Übertragen in den Datenspeicher für eine große DITA-Zuordnung mit Umfang und Peer-Links in der AEM-Site-Veröffentlichung. 13530)
- In der Symbolleiste **Seitenlayouts** der Vorlagen, die in der nativen PDF-Veröffentlichung verwendet werden, werden für die Option Inhalt bearbeiten **ein falsches Symbol und eine falsche QuickInfo**. 13492)
- Eine Site kann nicht mit Experience Manager Guides aktiviert werden (**Publish Dashboard**. 13439)
- In der nativen PDF-Veröffentlichung ist die Barrierefreiheit beeinträchtigt, da Bilder in Kopf- und Fußzeile keinen Alternativtext anzeigen. 12829)
- In der AEM Sites-Ausgabe gingen der Stil bzw. die Zeilenumbrüche für das `<lines>` mit Unterelementen verloren.12542)
- Das Duplizieren des Seiten-Layouts im nativen PDF funktioniert nicht, wenn automatisch keine Erweiterung hinzugefügt wird. 12534)
- Die Lokalisierung der Elementbeschriftungen funktioniert in der AEM Sites-Ausgabe nicht ordnungsgemäß. 12144)
- Benutzerdefinierte Metadaten sind in der endgültigen Ausgabe nicht verfügbar. 12116)
- `fmdita rewriter` steht im Konflikt mit der Rewriter-Konfiguration des Benutzers und führt zur Anzeige langer URLs anstelle der Links. 12076)
- Fehlende Option **ditaval** in den über die Benutzeroberfläche des Web-Editors erstellten Ausgabevorgaben auf Ordnerprofilebene. 11903)
- In der Voreinstellung **AEM** Site **ist die Option „Separate PDF für jedes Thema generieren** nicht funktionsfähig. 11555)
- Die native PDF-Veröffentlichung bietet keine Unterstützung für die CMYK-Farbraumkonvertierung. 10754)
- Beim Upgrade auf Version 4.3.1 treten einige Ausnahmen im nativen PDF-Knoten auf. 14492)
- Beim Generieren der PDF-Ausgabe mit nativer PDF-Veröffentlichung wird der Dateiname nach einem bestimmten Zeitraum abgeschnitten. 13620)


## Verwaltung

- Der Inhaltsverweis ist beim Kopieren und Einfügen der DITA-Dateien mit Selbstverweis-Links ohne GUID fehlerhaft. 13540)
- **Grundlinienfilter**-Dateien funktionieren im Web-Editor nicht mit Dateinamen. 13486)
- Im Web-Editor zeigt die Grundlinie den Titel für die vorherige Version anstelle der ausgewählten Version der DITA-Datei an. 13444)
- Wenn Sie die Indizierung der übergeordneten DITA-Zuordnung deaktivieren, um eine bessere Leistung zu erzielen, kann dies Auswirkungen auf die Funktionalität bestimmter Funktionen haben.12213)
- Bedingungsvorgaben für große DITA-Zuordnungen werden nicht erstellt. 10936)
- Die Voreinstellungen für die ersten Zuordnungen der Sammlung können beim Bearbeiten einer Zuordnungssammlung nicht bearbeitet werden. 10649)
- Kennzeichnungen aus der `labels.json`-Datei werden im Web-Editor in zufälliger Reihenfolge angezeigt. 10508)
- Dynamische Baseline-Aufrufe verwenden den Namen anstelle des Titels, was dazu führt, dass die Export-DITA-Zuordnungs-API fehlschlägt. 14268)

## Überprüfung

- Das Kontextmenü mit der rechten Maustaste funktioniert nicht für **Akzeptieren** oder **Ablehnen** Tracking von Änderungen. 14607)
- Der Umschalter zum Schließen von DITA-Themen im Überprüfungsbildschirm funktioniert in Version 4.3.1 von Adobe Experience Manager Guides nicht. 14537)
- Symmetrieprobleme treten in den Seitenansichtsbereichen der vorherigen und aktuellen Versionen im Web-Editor auf. 14156)
- Das Anpassen von E-Mail-Vorlagen für den Überprüfungs-Workflow funktioniert nicht mit Überlagerung. 13954)
- Koreanische Anhänge im Experience Manager Guides-Überprüfungsbildschirm sind nicht anklickbar. 13436)
- Der Map-Titel wird im Bildschirm Überprüfung und Zusammenarbeit abgeschnitten, ohne Option zum Anzeigen des vollständigen Titels. 13012)

## Übersetzung

- Die Schaltflächen **Akzeptieren/Ablehnen** werden fälschlicherweise für die automatisch genehmigte menschliche Übersetzung angezeigt. 14318)
- Bei der Umwandlung nichtenglischer DITA-Dateien in AEM-Seiten treten Internationalisierungsprobleme (i18n) auf. 14286)
- Die automatische Genehmigung funktioniert manchmal nicht und es treten Ausnahmen auf, wenn ein falscher Wert für „Übersetzungsstatus **festgelegt**. 13607)
- Die vom Übersetzungs-Dashboard exportierte Baseline schlägt fehl und wird nicht in der Zielsprache geöffnet. 12993)
- Übersetzte Inhalte können nicht mit temporären Übersetzungsprojekten synchronisiert werden, und der DITA XML Editor-Übersetzungs-Assistent zeigt fälschlicherweise den Status **In Bearbeitung** für genehmigte Aufträge an. (9938)

## Bekanntes Problem

Adobe hat das folgende bekannte Problem in Version 4.4.0 festgestellt:

- Version 1.0 wird für die duplizierte DITA-Datei nicht auf der Benutzeroberfläche angezeigt.
