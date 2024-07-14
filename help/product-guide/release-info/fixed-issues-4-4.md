---
title: Versionshinweise | Behobene Probleme in Adobe Experience Manager Guides Version 4.4.0
description: Erfahren Sie mehr über die Fehlerbehebungen in der Adobe Experience Manager Guides-Version 4.4.0
role: Leader
exl-id: ff3083d3-062b-4a79-875f-86991978a18e
source-git-commit: e40ebf4122decc431d0abb2cdf1794ea704e5496
workflow-type: tm+mt
source-wordcount: '1434'
ht-degree: 0%

---

# Behobene Probleme in Version 4.4.0 (Januar 2024)


Dieser Artikel behandelt die Fehler, die in verschiedenen Bereichen der Version 4.4.0 von Adobe Experience Manager Guides behoben wurden.

Weitere Informationen zu den neuen Funktionen und Verbesserungen finden Sie unter [Neue Funktionen in Version 4.4.0](./whats-new-4-4.md).

Erfahren Sie mehr über [Upgrade-Anweisungen für Version 4.4.0](../release-info/upgrade-instructions-4-4.md).


## Authoring

- Die Rechtschreibprüfung im Editor lässt die Auswahl von Vorschlägen nicht zu. (15045)
- Die globale Navigationsschaltfläche funktioniert nicht und das Dashboard kann nicht geladen werden. (14968)
- Im Web Editor kann die Download-Zuordnungsfunktion keine Popup-Benachrichtigung Trigger werden, wenn sie zum Herunterladen bereit ist. (14626)
- Im Web Editor kann die Funktion zum Herunterladen von Landkarten keine Landkarte mit Grundlinie herunterladen. (14622)
- Ungültiger DTD-Fehler in der Experience Manager Guides. (14482)
- Der Titel auf der Registerkarte &quot;Web Editor&quot;wird nach einem Punkt (.) Zeichen. (14372)
- Fehlermeldungen für doppelte Zuordnungsnamen in der Assets-Benutzeroberfläche werden nicht aktualisiert. (14320)
- Bei der Versionserstellungslogik tritt beim Ziehen und Ablegen von Assets ein Fehler auf. (14291)
- Wiederverwendbarer Inhalt überspringt die Element-IDs. (14213)
- Das Einstellungssteuerelement zum Ausblenden des Bereichs **Sprachvariablen** auf der Registerkarte **Ausgabe** fehlt. (14194)
- Der Web Editor gibt Anwendungsfehler aus, wenn ein neuer Verweis oder Thema mithilfe eines speziellen Schemas in der Ansicht **Layout** hinzugefügt wird. (14094)
- Das Leerzeichen nach dem Element conref `<ph>` verschwindet beim Speichern des Themas. (13642)
- Beim Versuch, DITA-Dateien zu speichern, bevor die Nachbearbeitung abgeschlossen ist, tritt ein Anwendungsfehler auf. (13571)
- Ein Ankerlink zum Element `<dlentry>` oder `<dt>` zeigt den Link-Text nicht an. (13543)
- Die Sammlung **Favoriten** im Web Editor kann nicht geladen werden. (13495)
- Wenn der Titel eines Themas einen Schrägstrich `/` enthält, werden auf der Registerkarte im Web Editor nur die Buchstaben angezeigt, die danach folgen. (13455)
- Die Bildvorschau wird nach der Anzeige der Vorschau im Web Editor nicht ausgeblendet. (13454)
- Zitate zeigen nicht anklickbare Links an, wenn sie mit einer eindeutigen ID mit Leerzeichen erstellt werden. (13447)
- Wenn Sie ein Thema nach der Bearbeitung schließen, werden Sie zur AEM-Startseite weitergeleitet, anstatt zur Ordneransicht zurückzukehren. (13306)
- Das Popup-Fenster &quot;Keyword einfügen&quot;wird nicht angezeigt, wenn in anderen Themen Schlüssel mit der root-Map verwendet werden. (12950)
- Schließen-Symbole sind nicht sichtbar, wenn sehr hohe Grafiken im Bedienfeld **Versionsverlauf** in der Vorschau angezeigt werden. (12867)
- Die Zeitzone der Spalte &quot;**Version erstellt am**&quot; für die Grundlinien kann nicht geändert werden. (12711)
- ZIP-Dateien werden im Web Editor nicht erkannt und können nicht per Drag-and-Drop eingefügt werden. (12709)
- Der Bereich **Versionsverlauf** in der Assets-Benutzeroberfläche zeigt einen falschen Zeitstempel für das Feld **Aktuell** an. (12624)
- In der Ansicht **Layout** für eine Lesekarte funktioniert die Verwendung von **Nach rechts verschieben**, um ein ausgewähltes Kapitel so zu gestalten, dass ein Unterelement nicht funktioniert. (12567)
- Das Erstellen einer DITA-Datei aus einer Vorlage mit einem Dateinamen, der mit numerischen Zeichen beginnt, führt zu einem Namespace-Fehler. (12188)
- Die Rootmap-Einstellung bleibt im Web Editor erhalten, auch wenn der Benutzer sie nicht explizit in den **Benutzereinstellungen** festgelegt hat. (11551)
- Der Inhalt mit einigen angewendeten Attributen wird im Modus **Autor** oder **Vorschau** nicht hervorgehoben. (11063)
- Im Web Editor wird beim Einfügen des Tags `varname` das Fenster **Schlüsselverweise** geöffnet. (10940)
- Wenn Sie ein Glossarthema aus dem Repository in eine Glossarzuordnung ziehen, wird `topicref` erstellt. (10767)
- Das Vorschaufenster des XML-Editors wird in Google Chrome- und Microsoft Edge-Browsern abgeschnitten. (10755)
- Der Web Editor kann ein Element nicht in die möglichen übergeordneten Elemente einschließen. (8791)
- Der Web Editor wird nach der Neuinstallation von Adobe Experience Manager Guides Version 4.3.1 deinstalliert. (14519)
- Beim Installationsprogramm von Version 4.3.1 tritt ein Filterkonflikt auf, der dazu führt, dass `apps/cq/core/content/projects/properties` überschrieben wird. (14517)
- Unter der Liste der **fehlerhaften Links** in Berichten wird ein Selbstverweis-Link angezeigt. (13539)
- Der Vorschaubildschirm für Snippets ist gesperrt. (14840)
- Beim Erstellen der Codefragmente in koreanischer Sprache werden ungültige Zeichen angezeigt. (13489)

## Veröffentlichung

- Die AEM Sites-Veröffentlichung schlägt fehl und verursacht Bereichsfehler für Dateien mit `xref` in der DITA-Datei, die mit &quot;HTTP&quot;beginnen. (15154)
- Bei der nativen PDF-Veröffentlichung können die DITA-Map-Metadateneigenschaften nicht zum Ausfüllen der Metadaten für die PDF-Dateiausgabe verwendet werden. (15159)
- Bei der nativen PDF-Veröffentlichung funktionieren benutzerdefinierte Attribute innerhalb von Bedingungsvorgaben nicht für die native PDF-Veröffentlichung. (14943)
- Benutzerdefinierte Vorlagen können nicht über die Registerkarte **Ausgaben** im Editor hinzugefügt werden. (14846)
- **AEM Site**-Vorgabe funktioniert aufgrund eines leeren Vorlagenpfads nicht. (14804)
- AEM Neuerstellung der Site schlägt bei DITA-Maps mit Themen fehl, die MathML-Gleichungen enthalten. (14790)
- Bei der nativen PDF-Veröffentlichung gibt die PDF-Generierung Fehler beim Abrufen von Abhängigkeiten für die `Node.js`-Veröffentlichung aus. (14445)
- Die Vorgabe **AEM Site** erlaubt nicht die Auswahl einer Vorlage außerhalb der `/content` -Hierarchie im Web Editor. (14260)
- Die Funktion zum Veröffentlichen als Inhaltsfragment funktioniert nicht für Dateien, die in den Suchergebnissen aufgelistet sind. (14090)
- Fmdita-Komponenten haben einen fest programmierten Pfad von `delegator.jsp`, wodurch die Überlagerung von AEM Sites-Komponenten verhindert wird. (13993)
- Die getaggte Ansicht des PDF-Reaktors in der Ausgabe der nativen PDF-Veröffentlichung funktioniert nicht erwartungsgemäß. (13622)
- Bei nativer PDF-Veröffentlichung erfordert die Hintergrundfarbauswahl im Layout **Vorlage** eine erneute Seitenladung, wenn auf `None` zurückgegriffen wird. (13621)
- AEM Site-Veröffentlichung tritt beim Übertragen an den Datenspeicher für große Maps mit Perimeter-Peer-Links auf ein Problem auf. (13531)
- Es tritt ein Problem beim Übertragen auf den Datenspeicher für eine große DITA-Zuordnung mit Perimeter-Links in AEM Site-Veröffentlichung auf. (13530)
- Das falsche Symbol und die falsche QuickInfo werden für die Option **Inhalt bearbeiten** in der Symbolleiste **Seitenlayouts** der Vorlagen angezeigt, die beim nativen PDF-Publishing verwendet werden. (13492)
- Eine Site kann nicht mit dem Experience Manager Guides **Bulk Publish Dashboard** aktiviert werden. (13439)
- Bei der nativen PDF-Veröffentlichung ist die Barrierefreiheit beeinträchtigt, da Bilder in der Kopf- und Fußzeile keinen alternativen Text anzeigen. (12829)
- In der AEM Sites-Ausgabe gingen der Stil oder die Zeilenumbrüche für das Element `<lines>` mit Unterelementen verloren.(12542)
- Das Duplizieren des Seitenlayouts im nativen PDF funktioniert nicht, ohne dass automatisch eine Erweiterung hinzugefügt wird. (12534)
- Die Lokalisierung der Elementbeschriftungen funktioniert in der AEM Sites-Ausgabe nicht ordnungsgemäß. (12144)
- Benutzerdefinierte Metadaten sind in der endgültigen Ausgabe nicht verfügbar. (12116)
- `fmdita rewriter` steht in Konflikt mit der Rewriter-Konfiguration des Benutzers und führt zur Anzeige langer URLs anstelle der Links. (12076)
- Fehlende Option **ditaval** in Ausgabevorgaben auf Ordnerprofilebene, die über die Web Editor-Benutzeroberfläche erstellt wurden. (1903)
- In der Vorgabe **AEM Site** ist die Option zum **Separaten PDF für jedes Thema erzeugen** nicht funktionsfähig. (11555)
- Für die Konvertierung von CMYK-Farbräumen wird bei der nativen PDF-Veröffentlichung nicht unterstützt. 10754)
- Beim Upgrade auf Version 4.3.1 treten im Knoten Native PDF einige Ausnahmen auf. (14492)
- Beim Generieren der PDF-Ausgabe mit nativer PDF-Veröffentlichung wird der Dateiname nach einem Punkt abgeschnitten. (13620)


## Verwaltung

- Die Inhaltsreferenz beim Kopieren und Einfügen der DITA-Dateien mit Selbstverweis-Links ohne GUID ist fehlerhaft. (13540)
- **Baseline-Filter**-Dateien funktionieren im Web Editor nicht mit dem Dateinamen. (13486)
- Im Web-Editor zeigt die Grundlinie den Titel der vorherigen Version anstelle der ausgewählten Version der DITA-Datei an. (13444)
- Die Deaktivierung der Indizierung der übergeordneten DITA-Zuordnung, um eine bessere Leistung zu erzielen, kann sich auf die Funktionalität bestimmter Funktionen auswirken.(12213)
- Bedingungsvorgaben für große DITA-Maps werden nicht erstellt. (10936)
- Die Vorgaben für die ersten Zuordnungen der Sammlung können beim Bearbeiten einer Zuordnungssammlung nicht bearbeitet werden. (10649)
- Beschriftungen aus der Datei `labels.json` werden im Web Editor in zufälliger Reihenfolge angezeigt. (10508)
- Dynamische Grundlinien-Aufrufe verwenden den Namen anstelle des Titels, was zu einem Fehler bei der Export von DITA Map-API führt. (14268)

## Überprüfung

- Kontextmenü mit Rechtsklick funktioniert nicht bei Verfolgungsänderungen von **Accept** oder **Reject**. (14607)
- Das Umschalten zum Schließen von DITA-Themen im Überprüfungsbildschirm funktioniert in Version 4.3.1 von Adobe Experience Manager Guides nicht. (14537)
- Symmetrische Probleme treten in den seitlichen Überprüfungsfeldern der vorherigen und der aktuellen Versionen im Web Editor auf. (14156)
- Das Anpassen von E-Mail-Vorlagen für den Review-Workflow funktioniert nicht mit Überlagerungen. (13954)
- Koreanische Anlagen im Experience Manager Guides-Überprüfungsbildschirm können nicht angeklickt werden. (13436)
- Der Titel der Karte wird im Bildschirm für Überprüfung und Zusammenarbeit abgeschnitten, ohne dass eine Option zum Anzeigen des vollständigen Titels verfügbar ist. (13012)

## Übersetzung

- Die Schaltflächen **Akzeptieren/Ablehnen** werden fälschlicherweise für die automatische menschliche Übersetzung angezeigt. (14318)
- Internationalisierungsprobleme (i18n) treten während der Transformation nicht-englischer DITA-Dateien auf AEM Seiten auf. (14286)
- Die automatische Genehmigung funktioniert manchmal nicht und es treten Ausnahmen auf, wenn ein falscher Wert auf **Übersetzungsstatus** festgelegt ist. (13607)
- Die über das Dashboard &quot;Übersetzung&quot;exportierte Grundlinie schlägt fehl und wird nicht in der Zielsprache geöffnet. (12993)
- Übersetzte Inhalte können nicht mit temporären Übersetzungsprojekten synchronisiert werden. Der DITA XML-Editor-Übersetzungs-Assistent zeigt fälschlicherweise den Status **Gestartet** für genehmigte Aufträge an. (9938)

## Bekanntes Problem

Adobe hat das folgende bekannte Problem für die Version 4.4.0 identifiziert:

- Version 1.0 wird nicht auf der Benutzeroberfläche für die duplizierte DITA-Datei angezeigt.
