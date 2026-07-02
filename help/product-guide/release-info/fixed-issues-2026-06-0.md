---
title: Versionshinweise | Behobene Probleme in Adobe Experience Manager Guides Version 2026.06.0
description: Erfahren Sie mehr über die Fehlerbehebungen in der Version 2026.06.0 von Adobe Experience Manager Guides as a Cloud Service.
source-git-commit: 318f2b7a530e50ca4432313650801b2293d6697e
workflow-type: tm+mt
source-wordcount: '2171'
ht-degree: 0%

---

# Es wurden Probleme in der Version 2026.06.0 behoben

Dieser Artikel behandelt die in verschiedenen Bereichen der Version 2026.06.0 von Adobe Experience Manager Guides as a Cloud Service behobenen Fehler.

Weitere Informationen zu den neuen Funktionen und Verbesserungen finden Sie [Neue Funktionen in der Version 2026.06.0](whats-new-2026-06-0.md).

Erfahren Sie mehr [Upgrade-Anweisungen für die Version 2026.06.0](upgrade-instructions-2026-06-0.md).

## Authoring

- Wenn Sie den Fokus zwischen den Feldern **Breite** und **Höhe** im Dialogfeld Bildeigenschaften mithilfe von einheitsbasierten Größen wie `in`, `mm` oder `px` umschalten, erhöhen sich die Werte schrittweise, anstatt stabil zu bleiben. (GUIDES-45929)

## Editor 2.0

- Durch Kopieren und Einfügen von `<keywords>` innerhalb von `<topicmeta>` innerhalb eines `<keydef>` oder einer `<topicref>` werden die Keywords in unerwünschte fremde Tags eingefügt. (GUIDES-45800)
- Bildabmessungen, die mit Einheiten wie `mm` angegeben wurden, werden nicht korrekt gerendert, sodass Bilder mit ihrer Originalgröße anstelle der angegebenen Abmessungen angezeigt werden. (GUIDES-46275)
- Wenn Sie bei aktivierter Tag-Ansicht per Drag-and-Drop Inhalte mit partiellen XML- oder DITA-Tags auswählen, bleiben unerwünschte verwaiste Tags zurück, was zu falschen Inhalten oder Ansichten führt. (GUIDES-28191)
- In der Tag-Ansicht einer Tabelle wird durch Drücken der Nach-oben-Taste bei der Positionierung des Cursors in der Zelle direkt unter einem reduzierten Einstiegs-Tag das reduzierte Tag übersprungen und der Cursor an den Anfang des Dokuments bewegt. (GUIDES-45408)
- Wenn Sie einen Vorgang über die kontextuelle Symbolleiste der Tabelle ausführen, wird die Symbolleiste unerwartet geschlossen, wodurch nachfolgende Tabellenvorgänge unterbrochen werden. (GUIDES-45405)
- Nach Verwendung von **Einfügen nach** oder **Einfügen vor** in der Gliederungsansicht oder im Breadcrumb wird der Cursor an eine beliebige Position verschoben, anstatt innerhalb des neu hinzugefügten Tags. (GUIDES-45147)
- Wenn die **MathML bearbeiten**-Option im schreibgeschützten Modus nicht korrekt angezeigt wird oder wenn eine Datei von einem anderen Benutzer ausgecheckt wird, können Benutzende MathML-Inhalte aktualisieren, auch wenn die Datei nicht bearbeitbar sein sollte. (GUIDES-45172)
- Beim Löschen eines XML-Kommentars mithilfe der Rücktaste wird das Kommentar-Tag nicht entfernt, nachdem sein Inhalt gelöscht wurde, und der Löschvorgang wird im vorherigen Element fortgesetzt. (GUIDES-45240)
- Bei Verwendung der Option **Kopierpfad** oder **UUID kopieren** für Bilder wird der Pfad der vollständigen Ausgabedarstellung anstelle des ursprünglichen Asset-Pfads zurückgegeben. (GUIDES-45278)
- Durch Kopieren und Einfügen von Inhalten im selben Thema an eine ungültige Position im Editor wird ein unbeabsichtigtes `<foreign>`-Tag eingefügt. (GUIDES-45378)
- Unter Windows werden beim Kopieren und Einfügen einer Tabellenzeile unerwartete Attribute wie `data-pm-slice` zum Tabellenelement hinzugefügt, was zu Markupfehlern führt, die das Speichern des Dokuments verhindern. (GUIDES-45784)
- Durch Verwendung der **Kopieren**-Option aus dem Kontextmenü in einer Zuordnung oder einem Thema und anschließendes Einfügen des Inhalts werden zusätzliche `<data>`-Tags in die eingefügte Ausgabe eingefügt. (GUIDES-45703)
- Beim Ziehen einer partiellen Auswahl aus einem `cmd` kann der Inhalt nicht zwischen vorhandenem Text oder am Ende eines anderen `cmd` Elements abgelegt werden. (GUIDES-44883)
- Beim Anwenden eines `scale`-Attributs auf eine Tabelle wird die Tabelle im Autoren- und Vorschaumodus nicht in der konfigurierten Größe gerendert. (GUIDES-45984)
- Durch Einfügen von Bildern, die aus externen Quellen wie Paint oder dem Snipping Tool kopiert wurden, wird das Bild nicht in das Thema eingefügt. (GUIDES-45983)
- Der `keyref`, der in einem Thementitel verwendet wird, der von einer Keyword-Zuordnung abgeleitet wurde, wird nach dem Speichern nicht auf der Registerkarte „Inhaltsverzeichnis“ oder „Thema“ angezeigt, auch nicht nach einer Browser-Aktualisierung. (GUIDES-45799)
- Beim Öffnen einer Prüfungsaufgabe im Editor mithilfe der Seitenansicht für die kommentierte Version wird die Version als Keine anstelle der zugehörigen Version für das Thema angezeigt. (GUIDES-45127)
- Beim Zugriff auf die Aufgabenseite „Überprüfen“ werden Seitenumbrüche zwischen Themen nicht angezeigt, was zu einer kontinuierlichen Wiedergabe von Inhaltsabschnitten führt. (GUIDES-46777)
- Die Gestaltung der Überprüfungsseite stimmt nicht mit dem neuen Editor überein, was zu einem inkonsistenten visuellen Erlebnis führt (GUIDES-46061)

## Asset-Management

- Wenn eine Zuordnung einen externen `topicref` enthält, der auf eine Nicht-DITA-Ressource verweist (z. B. `.html`), wird ihre Vorschau nicht in der Assets-Benutzeroberfläche angezeigt. (GUIDES-45409)
- Das Dialogfeld „Tool für die Massenverschiebung“ überläuft und verfügt nicht über eine Bildlaufleiste, wenn eine große Anzahl von Quellordnern ausgewählt ist, sodass das Zielpfadfeld und die Aktionsschaltflächen nur für Benutzende mit Maus zugänglich sind. (GUIDES-45805)
- Wenn ein Asset aus der Assets-Benutzeroberfläche kopiert wird, erhalten wir eine Benachrichtigung für `DXML reprocessing failure`. Diese Benachrichtigung ist irreführend und trägt seit dem Erfolg der Kopie zur Überlastung des Posteingangs bei. (GUIDES-45012)
- Beim Öffnen des Bedienfelds „Filter“ in der linken Leiste von Assets in einem Ordner bleiben das Suchfeld und die Facetten deaktiviert, bis das Bedienfeld geschlossen und erneut geöffnet wird. (GUIDES-42652)
- Inhaltsfragmente und Assets mit Zwischenübersetzung, die während des Übersetzungs-Workflows erstellt werden, werden unbeabsichtigt durch den geplanten Asset-Verarbeitungsauftrag verarbeitet, was zu Ausnahmen in den Protokollen und einer falschen Verarbeitung von Assets führt, die noch nicht bereit sind. (GUIDES-42582)

## Publishing

- Beim Arbeiten mit `.plt`- und `.css` in PDF-Vorlagen ist die Option **IDs generieren** im Kontextmenü der rechten Maustaste verfügbar, obwohl sie für diese Dateitypen nicht anwendbar ist. (GUIDES-45254)
- Die Schaltfläche **Speichern** wird beim erneuten Öffnen einer neu erstellten nativen AEM Sites-Vorgabe nach einer Browser-Aktualisierung fälschlicherweise standardmäßig aktiviert, selbst wenn keine Änderungen vorgenommen wurden. (GUIDES-45171)
- Beim Duplizieren einer nativen PDF-Vorgabe, die als Standard markiert ist, wird das Duplikat ebenfalls als Standardvorgabe festgelegt. Es sollte immer nur eine Voreinstellung als Standard festgelegt werden. (GUIDES-44786)
- Das `outputclass`-Attribut wird nicht an die generierte HTML- oder native PDF-Ausgabe weitergegeben, was verhindert, dass benutzerdefinierte Klassen, die auf MathML-Gleichungen angewendet werden, die gerenderte Ausgabe beeinflussen. (GUIDES-44393)
- Die Massenaktivierung von AEM Sites-Ausgaben, die mit der neuen AEM Sites-Vorlage generiert wurden, schlug fehl und verhinderte eine erfolgreiche Replikation auf die Veröffentlichungsinstanz. (GUIDES-44049)
- JARs für anfällige `jackson-databind` (Version 2.9.8) im Paket mit AEM Guides im DITA-OT-Paket wurden identifiziert. (GUIDES-43081)
- Das Öffnen einer nativen AEM Sites-Ausgabe aus einer Zuordnungssammlung führt zu einem Fehler, der angibt, dass die Ressource nicht gefunden wurde, und verhindert den Zugriff auf die generierte Ausgabe. (GUIDES-42065)
- Das `<reltable>`-Element in einer DITA-Zuordnung wird während der nativen PDF-Generierung ignoriert, was dazu führt, dass „Zugehörige Konzepte“, „Zugehörige Aufgaben“ und ähnliche automatisch generierte Querverweisabschnitte in der Ausgabe fehlen. (GUIDES-38333)
- Beim Veröffentlichen einer DITA-Zuordnung mit `processing-role=resource-only` in AEM Sites (mit Zuordnung veralteter Komponenten) werden für diese Elemente in zusätzlichen Szenarien, wie z. B. `topicgroup` und bestimmten Inhaltskonfigurationen, verwaiste Sites-Seiten generiert. (GUIDES-37650)
- Wenn eine Zuordnung mit einem langen Namen zu einer Zuordnungssammlung hinzugefügt wird, wird die Zuordnungssammlungs-Benutzeroberfläche in einem verzerrten Layout gerendert. Dieses Problem wurde mit der neuen Zuordnungssammlung behoben. (GUIDES-42062)
- Veröffentlichung mit der nativen PDF-Engine v1:
   - Beim Generieren der nativen PDF-Ausgabe für bestimmte Inhalte wird nur die erste Seite in der PDF gerendert, obwohl die dazwischenliegende HTML den vollständigen Inhalt auf mehreren Seiten enthält. (GUIDES-28270)
   - Die Lesereihenfolge von Inhalten in der nativen PDF-Ausgabe mit aktivierten Barrierefreiheitseinstellungen ist falsch. Seitenzahlen in Fußzeilen werden vor dem Hauptinhalt und nicht am Ende gelesen. (GUIDES-27790)
   - Die Farbleiste in der nativen PDF-Ausgabe erstreckt sich nicht über die gesamte Seitenbreite und überschneidet sich bei der Anpassung der Seitengröße, wodurch einige Farbfelder ausgeblendet werden. (GUIDES-15505)
   - Der CSS- `:is()` Pseudoklassenselektor wird in der nativen PDF-Ausgabe nicht berücksichtigt, was zu Stilunterschieden im Vergleich zum Browser-Rendering führt. (GUIDES-11328)

  >[!NOTE]
  >
  > Die oben genannten Probleme wurden mit der nativen PDF-Engine v2 behoben. Weitere Informationen finden Sie unter [Arbeiten mit der nativen PDF Engine v2](../native-pdf/new-pdf-engine.md).

## Übersetzung

- Das Anwenden einer Grundlinie auf eine Zuordnung mit vielen Assets verzögert das Laden des Übersetzungsberichts für die ausgewählte Sprache, was manchmal zu einer Zeitüberschreitung der Anfrage führt, bevor der Bericht gerendert wird. (GUIDES-45508)
- Sprachgruppen in der Registerkarte Übersetzung in den Workspace-Einstellungen werden nicht beibehalten, wenn der ausgewählte Sprachordner einen Code mit Trennzeichen für das Gebietsschema (z. B. `da-DK`) anstelle eines Unterstrichs (`da_dk`) verwendet. (GUIDES-37843)

## Überprüfung

- Die QuickInfo für das Symbol **Versionsverlauf** fehlt im linken Bereich der Benutzeroberfläche „Überprüfen“ neben dem Themennamen. (GUIDES-45511)
- Wenn beim Bearbeiten einer aktiven Prüfungsaufgabe ein Thema, das bereits Teil der Überprüfung ist, entfernt und dann erneut hinzugefügt wird, ohne **Aktualisieren** auszuwählen, gehen die Reviewer-Informationen für dieses Thema verloren. (GUIDES-38774)
- Der Inhaltsbereich in der Review-Benutzeroberfläche zeigt auf bestimmten Bildschirmauflösungen, einschließlich der empfohlenen Auflösung von 1600 Pixel, eine horizontale Bildlaufleiste an, sodass Überprüfungskommentare ausgeblendet werden, wenn der Inhalt die Fensterbreite überschreitet. (GUIDES-44082)

## Lerninhalte

- Beim Hinzufügen von Fragen zu einem Quiz mithilfe der Option Aus Fragenbank einfügen werden kurze Antwortfragen nicht aufgelistet, obwohl eine gültige Frage-ID vorhanden ist. (GUIDES-44942)
- Beim Einfügen von Fragen mit der Option Aus Fragenbank einfügen flackert das Dialogfeld Aus Fragenbank einfügen beim Öffnen unerwartet oder ändert seine Größe. (GUIDES-45524)
- Beim Einfügen von Fragen mit der Option Aus Fragenbank einfügen tritt ein Fehler auf, wenn der Fragetitel ein Bild enthält. (GUIDES-45383)
- Die Auswahl einer SCORM-Ausgabevorlage führt zu einem Anwendungsfehler, wenn der Vorlagentitel geändert wurde. (GUIDES-45521)
- Untertiteldateien (`.vtt`) sind nach dem Hochladen in einen Ordner nicht in der Repository- oder Explorer-Ansicht sichtbar. (GUIDES-46014)
- Beim Laden von Videoinhalten in der HTML-Vorschau enthält der Quellpfad (`src`) einen angehängten Ausgabedarstellungspfad, anstatt den Originaldateipfad beizubehalten, sodass das Video nicht korrekt gerendert werden kann. (GUIDES-41776)
- Die Veröffentlichung der SCORM-Ausgabe vom Safari-Browser führt dazu, dass das Paket als Ordner anstelle einer ZIP-Datei heruntergeladen wird, zusammen mit Rendering- und Funktionsproblemen im generierten Inhalt (z. B. gestreckter Inhalt, nicht funktionierendes Akkordeon und mehr). (GUIDES-45119)
- Es tritt eine Verzögerung auf, bevor die Schaltfläche Weiter für Kurse aktiviert wird, was sich auf das Navigationserlebnis für Teilnehmer auswirkt. (GUIDES-45113)
- Stile für kurze Antwortfragen werden in der Veröffentlichungsausgabe falsch gerendert, obwohl sie in der Vorschau korrekt angezeigt werden. (GUIDES-46478)
- Beim Generieren der PDF-Ausgabe für Kurse, die Videos enthalten, wird der Videoinhalt nicht gerendert, sondern nur der Dateipfad anstelle eines Platzhalterbilds wie Videominiatur oder Posterbild angezeigt. Dieses Problem wurde behoben, indem die Option **Multimediadateien einbetten** in der nativen PDF-Ausgabevorgabe aktiviert wurde. (GUIDES-45117)
- CSS-Pseudoklassen und -Elemente werden im Editor des Handbuchs in Weiß gerendert, sodass sie unsichtbar oder vor dem Editor-Hintergrund schwer lesbar sind. (GUIDES-45116)

## Bekannte Probleme

Adobe hat die folgenden bekannten Probleme in Version 2026.06.0 identifiziert:

## Editor 2.0

- Das Wechseln zwischen Source- und Autorenmodus führt zu Inhaltsinkonsistenzen, wobei Teile des Themas verschwinden oder nicht in allen Modi angezeigt werden. (GUIDES-47432)

- Bei der Arbeit mit Änderungen nachverfolgen werden bei Ablehnung einer importierten Texteinfügung alle Inhalte innerhalb des Tags entfernt, anstatt nur die spezifischen eingefügten Inhalte zurückzuweisen. (GUIDES-48319)

- Die **Als PDF exportieren** Schaltfläche im Vorschaumodus führt keine Aktion aus, wenn die Editor-Symbolleiste mithilfe von `editor_toolbar.json` in einem Ordnerprofil angepasst wird. (GUIDES-47525)

- Beim Ausführen von Löschvorgängen können einige geringfügige Inkonsistenzen in der Cursorbewegung und Navigation zwischen Imagemaps, strukturierten Elementen, Inline-Formatierungs-Tags und nicht zusammenführbaren Blöcken auftreten, was gelegentlich zu unerwartetem Cursor- oder Löschverhalten führt. (GUIDES-46756)

- Bei Verwendung von `Ctrl+click` auf einem fehlerhaften Link in einem Zuordnungs-Editor wird ein Anwendungsfehler Trigger. (GUIDES-45544)

- Durch Drücken der Rücktaste am Anfang eines Absatzes unmittelbar nach dem schreibgeschützten Inhalt (z. B. eines `conref` Absatzes) kann der bearbeitbare Absatz unerwartet gelöscht oder zusammengeführt werden, was zu einem unerwarteten Löschen des bearbeitbaren Absatzes führt. (GUIDES-45049)

- Wenn Bedingungsindikatoren auf Elemente wie `bodydiv` angewendet werden, fließen die Indikatoren in der Ansicht „Vollständige Tags“ in angrenzende Tags über, was zu falschem visuellen Rendering führt. (GUIDES-44971)

- Beim Arbeiten im Editor können Sie keine `keyrefs` oder Schlüssel auswählen, die von Zuordnungen abgeleitet wurden (einschließlich Glossareinträgen in Zuordnungen, auf die in `term`- oder `abbreviated-form`-Elementen verwiesen wird), was zu einem eingeschränkten Authoring-Erlebnis führt. (GUIDES-45790) <br> **Problemumgehung**: Sie können den Wert von `keyref` im rechten Bedienfeld mithilfe der Attributwerte ändern.

- In der Gliederungsansicht wird bei erneuter Aktivierung **Text anzeigen** nach dem Schließen und erneuten Öffnen eines Themas kein Text neben Element-Tags angezeigt. (GUIDES-48320) <br> **Problemumgehung**: Aktivieren Sie die Option **Text anzeigen** und öffnen Sie das Thema dann erneut. Nach dem erneuten Öffnen wird der Text neben den Element-Tags korrekt angezeigt.

- Wenn ein Inline-Tag mit der Option **Element umbenennen** umbenannt wird, wird der Breadcrumb nicht sofort aktualisiert und spiegelt die Änderung erst wider, nachdem der Cursor in das Tag verschoben oder der Ansichtsmodus geändert wurde. (GUIDES-44993) <br> **Problemumgehung**: Aktualisieren Sie den Browser, nachdem Sie das Inline-Tag umbenannt haben, um den Breadcrumb zu aktualisieren.

- Wenn eine MathML-Gleichung als `conref` eingefügt wird, wird sie nicht korrekt dargestellt. (GUIDES-46601) <br> **Problemumgehung**: Betten Sie die MathML-Gleichung in ein `<p>` ein und verwenden Sie dieses `<p>` als conref-Quelle.

## Überprüfung

- Wenn eine Prüfungsaufgabe einem Benutzer außerhalb des Projektteams neu zugewiesen wird, kann der Benutzer trotz fehlender Projektmitgliedschaft Prüfungsaktionen durchführen, während die Sichtbarkeit der Prüfer, die Nachverfolgung des Prüfungsstatus und die Delegierungsbenachrichtigungen nicht ordnungsgemäß funktionieren. (GUIDES-46602)

## Publishing

- Beim Veröffentlichen von Inhalten mit DITAVAL-Filterung, durch die alle Listenelemente mit Aufzählungszeichen durch bedingte Profilerstellung ausgeschlossen werden, wird in der Ausgabe fälschlicherweise eine leere Aufzählungsmarkierung beibehalten, anstatt die gesamte Listenstruktur zu entfernen. (GUIDES-47238)

- Beim Veröffentlichen einer nativen AEM-Site-Ausgabe mit einer neuen Grundlinie erscheint die Themenliste leer und zeigt die in der ausgewählten Grundlinie enthaltenen Themen nicht an. (GUIDES-46480) <br> **Problemumgehung**: Veröffentlichen Sie die native AEM-Site-Ausgabe unter Verwendung der alten Grundlinie, die über den Konfigurations-Manager konfiguriert werden kann.





