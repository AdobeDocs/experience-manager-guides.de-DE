---
title: Versionshinweise | Behobene Probleme in Adobe Experience Manager Guides Version 4.6.0
description: Erfahren Sie mehr über die Fehlerbehebungen in der Adobe Experience Manager Guides-Version 4.6.0
role: Leader
source-git-commit: 5a30d427fa579e37a18b0fca65dea96dc486c594
workflow-type: tm+mt
source-wordcount: '1946'
ht-degree: 0%

---


# Es wurden Probleme in Version 4.6.0 (September 2024) behoben


Dieser Artikel behandelt die Fehler, die in verschiedenen Bereichen der Version 4.6.0 von Adobe Experience Manager Guides behoben wurden.


Weitere Informationen zu den neuen Funktionen und Verbesserungen finden Sie unter [Neue Funktionen in Version 4.6.0](whats-new-4-6.md).

Erfahren Sie mehr über [Upgrade-Anweisungen für Version 4.6.0](../release-info/upgrade-instructions-4-6-0.md).

## Authoring

- Die Option **Suchen** funktioniert in der Ansicht **Source** nicht. (18610)
- Die Symbole **Auschecken** und **Einchecken** werden zusammen angezeigt, wenn `autocheckout` in xmleditor konfiguriert ist. (18088)
- Große DITA-Maps werden langsam geladen und benötigen Zeit, um zur Ansicht **Layout** zu wechseln.  (17590)
- Fehler bei doppelten Bild-IDs in den Themen beschränken das Speichern oder Bearbeiten eines Themas durch den Benutzer. (17528)
- Beim Kopieren und Einfügen von Themen mit einer Größe von mehr als 15 KB tritt ein unerwarteter Fehler auf. (17171)
- Die Funktion zum Ändern des Dokumentstatus im Bedienfeld **Dateieigenschaften** funktioniert nicht ordnungsgemäß und ändert sich in den Status *Entwurf* . (17088)
- Wenn Sie die Einstellungen des XML-Editors mit einem benutzerdefinierten Ordnerprofil ändern, wird `ui_config.json` mit einer falschen Datei aktualisiert. (17011)
- In wiederverwendbaren Inhaltsbereichen werden Elemente nicht aufgelistet, wenn die **Benutzereinstellungen** so eingestellt sind, dass Dateien mit **Dateiname** angezeigt werden. (16896)
- Unterelemente innerhalb des Tabellentitelelements werden im Modus **Vorschau** von Experience Manager Guides nicht dargestellt. (16691)
- **Sonderzeichen**, die mit Escape-Zeichen geschrieben wurden, werden nach dem Hochladen in Experience Manager Guides aus dem Thema entfernt. (16495)
- Vimeo-Videos unterstützen keine Vollbildfunktionalität in Experience Manager Guides. (1596)
- Das Einfügen langer vorformatierter Textzeilen in Elemente vom Typ `<pre>` oder `<codeblock>` führt zu abgeschnittenem Text. (15859)
- Das Löschen von Inhalten erfolgt aufgrund doppelter GUIDs, wenn Vorlagen über Code installiert, aber nicht verarbeitet werden. (15858)
- Experience Manager Guides hält im Modus **Vorschau** nicht das Attribut **Verarbeitungsrolle** ein. (15787)
- Der Editor löscht gelegentlich zusätzlichen Text, der über den ausgewählten Bereich hinausgeht. (15708)
- Es ist nicht möglich, große Tabellen aus Word-Dokumenten oder HTML in den Web-Editor zu kopieren und einzufügen. (15369)
- Fehlende APIs oder Ereignisse zum Erfassen von Attributen, die zu einem Element hinzugefügt oder ein neues Element eingefügt werden. (15351)
- Es ist nicht möglich, im Web Editor das Tag `<data>` innerhalb des Tags `<ol>` hinzuzufügen. (15161)
- Die Platzhalterkomponente **Element** friert die Benutzeroberfläche ein. (14957)
- Der Web Editor kann keine PPTX-Dateien hochladen. (14837)
- Beim Suchen eines Textes im Web Editor kehrt der Cursor beim Drücken der Eingabetaste zum ersten Vorkommen des gesuchten Textes zurück. (14820)
- Das automatische Speichern verursacht mehrere Probleme, es positioniert den Cursor neu und erfordert manuelle Klicks im Dokument. (14253)
- Wenn Sie die Taste **Enter** in einer Tabellenzelle innerhalb des Textes drücken, wird der Absatz nicht wie erwartet geteilt. (14251)
- Große Dateien werden nicht im Web Editor geladen und frieren den Browser ein. (13227)
- Die Suchergebnisse werden deaktiviert, nachdem eine Datei geöffnet wurde, die über globale **Suchen und Ersetzen** gefunden wurde. (12142)
- In der Quellansicht wird gelegentlich `</conbody>` an falschen Stellen eingefügt. (11305)
- Der Komponentenpfad `/libs/fmdita/components/versions` ist fest codiert und die Benutzer können ihn nicht überlagern. (8779)
- `<conref>` für ein Thema, auf das in einer DITA-Zuordnung verwiesen wird, wird nicht in der Vorschau im Editor angezeigt. (17794)
- Die Experience Manager-DITA-Anleitung kann nach Verwendung der Funktion zum automatischen Einzug nicht auf die Funktion &quot;Speichern&quot;Trigger werden. (16482)
- Die QuickInfo-Funktion kann das Source-Feld im XML-Editor nicht aktualisieren. (15847)
- Die Funktion **UUID-Link freigeben** funktioniert nicht für die Bilder in Adobe Experience Manager. (15598)
- In der Ansicht **Autor** tritt ein Problem beim Kopieren und Einfügen auf, wenn ununterbrochene Leerzeichen verwendet werden und Text überläuft. (15541)
- Überschneidende Textprobleme treten in den Tags `<reltable>` und `<fig>` auf. (15238)
- Flackernde Probleme treten im Bereich **Attribute** auf. (15237)
- Beim Hinzufügen eines `<conref>` -Elements zu einer anderen DITA-Zuordnung in `<topicmeta>` wird die Zuordnungs-ID ebenfalls an die ID des Elements angehängt. `<othermeta>` (15226)
- Der Cursor springt beim Löschen eines Zeichens oder Worts im Inhalt zwischen den Blockelementen. (15224)
- Die Fehlermeldung &quot;Datei ausgecheckt durch&quot; wird falsch angezeigt, wenn Dateien von einer anderen Registerkarte verschoben, Token abgelaufen oder der Benutzer abgemeldet wird. (15223)
- Der `<conref>` kann nicht über das Bedienfeld **Attribute** aktualisiert werden, wenn Änderungen vorgenommen werden. (15209)
- Die gesamte Zelle wird bei der Auswahl eines Bildes in einer Tabellenzelle ausgewählt. (15188)
- Der Bereich **Attribute** wird nicht in der Source-Ansicht des Web Editors angezeigt. (14387)
- `<Topicref>`, der mit `<keyref>` hinzugefügt wurde, wird nicht in nativer PDF angezeigt. (1974)
- Beim Bearbeiten am Ende eines Tags im Web Editor werden unerwünschte, geschützten Leerzeichen hinzugefügt. (11786)
- Der Inhalt wird beim Korrigieren der Rechtschreibfehler in DITA-Dateien gelöscht. (11610)
- Durch Öffnen eines DITA-Themas oder -Map in einer neuen Registerkarte zur Bearbeitung wird die Auswahlnavigation in der Assets-Benutzeroberfläche eingefroren. (4992)
- Das Löschen von Überprüfungsknoten beeinträchtigt die Möglichkeit, Kommentare in Adobe Experience Manager Guides zu öffnen und anzuzeigen. (15366)
- In der DITA-Version wird der Benutzername fälschlicherweise in der Assets-Benutzeroberfläche angezeigt. (17580)
- Das Element `<title>` wird automatisch hinzugefügt, wenn das Element `<fig>` als Ausschnitt eingefügt wird. (18562)
- Beim Hochladen einer großen Anzahl von Dateien mit dichten Datensätzen in Experience Manager Guides treten Probleme auf.(17008)
- Der Webeditor zeigt standardmäßig den richtigen Suchbegriff nicht an, insbesondere wenn der Suchbegriff in untergeordneten Maps unterschiedlich definiert ist. (14748)
- Der **Dokumentstatus** wird nicht angezeigt, wenn die Eigenschaften von mehr als 50 Dateien stapelweise in der Zuordnungsansicht des Web-Editors bearbeitet werden. (14574)
- Das Verhalten der Schaltfläche Schließen ist bei Verwendung der Funktion Automatisches Speichern inkonsistent. (1096)
- Beim Einfügen eines neuen Elements oder Ändern von Gleichungen treten in MathML-Elementen Validierungsprobleme auf. (10624)
- Die Funktion &quot;Änderungen verfolgen&quot;funktioniert nicht mit Text, der mit koreanischen Zeichen beginnt. (14538)



## Veröffentlichung

- Querverweise auf den Schlüssel werden in der nativen PDF-Ausgabe nicht aufgelöst. (18087)
- Der Fehler **duplicate_value** tritt gelegentlich auf, wenn ein vorhandener Artikel in Salesforce erneut veröffentlicht wird. (17932)
- Die Salesforce-Verbindungsprüfung schlägt mit der Blitzer-URL fehl. (17797)
- Bei Auswahl der Option **In der topicmeta** hinzugefügte Metadaten verwenden werden die Metadateneigenschaften nicht in den Dokumenteigenschaften der nativen PDF-Ausgabe weitergeleitet.(17283)
- Die Bedingungsfilterung in der nativen PDF-Ausgabe funktioniert nicht erwartungsgemäß im Vergleich zu DITA-OT. (17095)
- Das Inhaltsverzeichnis berücksichtigt in der Ausgabe des nativen PDF keine `<sub>` - oder `<sup>` -Tags. (17028)
- Die Zuordnung von Zuordnungen zwischen Zuordnungen kann nicht alle übergeordneten Zuordnungen in den Einstellungen des Veröffentlichungskontexts für einen Link mit dem Wert `scope="peer"` anzeigen. (16700)
- AEM Site-Generierung und inkrementelle Publish-API funktionieren nicht erwartungsgemäß. (16666)
- AEM Erzeugung der Site-Ausgabe schlägt fehl, wenn die Option **Orphan-Site löschen** aktiviert ist. (15896)
- Die alten Attribute werden beim Hinzufügen oder Entfernen neuer oder vorhandener Attribute in den **Bedingungsvorgaben** beibehalten. (15890)
- In der JSON-Ausgabe werden Metadaten aus der DITA-Zuordnung oder Themen nicht in die JSON-Ausgabedateien übertragen. (15713)
- Der RTL-Sprachinhalt wird in der Ausgabe der nativen PDF-Veröffentlichung nicht korrekt verarbeitet. (15709)
- Die native PDF-Veröffentlichung schlägt fehl, wenn die Vorgabe umbenannt wird. (15662)
- Die Eigenschaft **sourcePath** ist in der Ausgabe der veröffentlichten AEM nicht korrekt. (15502)
- Die Auswahl und Anpassung von Sprachvariablen funktioniert in der Nativen PDF-Ausgabevorgabe nicht ordnungsgemäß. (15399)
- Die native PDF-Erstellung schlägt bei Verwendung eines großen Stylesheets oder einer Layoutvorlage fehl. (15344)
- Inhalte werden in der veröffentlichten Ausgabe nicht ordnungsgemäß gerendert, wenn `<conref>` mit einem absoluten Pfad verwendet wird. (1522)
- Die Verkürzung der AEM Sites-URL funktioniert aufgrund von Konflikten zwischen `fmdita rewriter` und `ResourceResolver` nicht. (14793)
- Die native PDF-Generierung schlägt mit einem Fehler bezüglich der Abrufen von Abhängigkeiten für Node.js fehl. (14445)
- Die Attribute **processing-role=&quot;resource-only&quot;**, **search=&quot;no&quot;** und **chunk=&quot;to-content&quot;** erscheinen in der AEM Sites-Ausgabe nicht bzw. nicht. (14442)
- `<Conref>` wird im `Preview` -Modus des Web Editors und der nativen PDF-Ausgabe nicht aufgelöst. (17827)
- In nativer PDF werden verschachtelte DITA-Themen im Inhaltsverzeichnis (Inhaltsverzeichnis) falsch angezeigt. (16742)
- Miniaturansichten, die von **Dynamic Media** für Videodateien generiert wurden, bleiben in der veröffentlichten Ausgabe nicht erhalten. (15656)
- Die referenzierte PDF wird während der Massenaktivierung veröffentlichter Inhalte nicht im **Bulk Publish Dashboard** aktiviert. (17793)
- Wenn ein Ordner mit 2k-Maps im Ordnerpfad innerhalb eines Ordnerprofils festgelegt ist, schlagen die auf die Ausgabevorgabe angewendeten Änderungen fehl. (14852)
- Die Themenneuerstellung schlägt aufgrund des Fehlers der OOTB-Regenerate Topic oder der inkrementellen Publish-API fehl. (18452)
- Die Bedingungsvorgabe ruft nach der Aktualisierung von Experience Manager Guides keine aktualisierten Attribute ab. (18174)
- Inhaltsreferenzen werden für die Ausgabe nativer PDF nicht korrekt aufgelöst, wenn sich die Datei mit Schlüsseldefinitionen nicht im selben Ordner wie die DITA-Zuordnung befindet. (15062)


## Verwaltung


- InDesign zu DITA-Konvertierungen haben einen fest programmierten Konfigurationspfad, sodass die benutzerdefinierten Konfigurationsdateien nicht ausgewählt werden. (16891)
- Nicht geschlossene **Ressourcen-Resolver** führen zu einer Erhöhung der Sitzungsanzahl und `PathNotFoundException` Fehlern nach der Version 4.3.1 von Experience Manager Guides. (15604)
- Fehler bei der Installation von Guides-Paketen in großen Repositorys. (15160)
- Das Erstellen einer Grundlinie mithilfe der Java-API funktioniert nicht mit Experience Manager Guides. (14787)
- Die `/bin/fmdita/import` -API bleibt in ausstehender Anfrage unbegrenzt erhalten, wenn das Hochladen von Assets 500 MB überschreitet. (14743)
- Beim Bearbeiten einer bestehenden Grundlinie und Auswählen einer bestimmten Version werden Anwendungsfehler Trigger. (14451)
- Die Ausführung des Postprozessskripts schlägt aufgrund der Ausnahme **FileNotFoundException** fehl. (16517)
- Dynamische Titel mit `<conkeyref>` werden nicht in der Themenliste &quot;Bericht&quot;angezeigt. (16967)
- Die ungenauen Zahlen für die **Themenliste** in der Benutzeroberfläche für Experience Manager Guides-Berichte treten aufgrund der nicht gepatchten Eigenschaften beim Kopieren von DITA-Assets auf. (15529)
- Themen mit externen Verweisen mit %20 in der URL zeigen fehlerhafte Dateiverweise an. (15347)
- Die Eigenschaften fmditaMaprefs und fmditakeydefrefs zeigen relative Pfade an, obwohl absolute Pfade für die DITA-Zuordnung und Themen festgelegt wurden. (18353)
- Der Pfad für die Überlagerungsfunktion ist für die koreanische Sprachdatei hartcodiert und nicht korrekt ausgewählt. (17089)
- Der Standardzeitpunkt bei der Erstellung einer Grundlinie im Web Editor wird als 00:00 anstelle der aktuellen Zeit angezeigt. (15215)

## Überprüfung

- Das Abrufen der Benutzerliste beim Erstellen einer Prüfungsaufgabe schlägt fehl, wenn die Benutzeranzahl 25 überschreitet. (17329)
- Prüfungsthemen werden nicht in der richtigen Reihenfolge angezeigt. (16319)
- Im Web Editor wird das Überprüfungsbedienfeld langsam geladen. (14680)
- Überprüfer können beim Ausführen einer Dokumentüberprüfung in Experience Manager Guides keine Leerzeichen hinzufügen, hervorheben oder ausblenden. (14752)
- Wenn ein Benutzer eine Überprüfungsaufgabe aktualisiert, erhalten nicht alle zugewiesenen Überprüfer eine Benachrichtigung über die Aktualisierung. (9496)

## Übersetzung

- Die Referenzen übersetzter Assets werden nicht aktualisiert. (18086)
- Es können keine XLIFF-Projekte mit menschlicher Übersetzung erstellt werden. (16964)
- Der Titel mit `<conref>` oder `<conkeyref>` wird nicht in den Dashboards &quot;Grundlinie&quot;und &quot;Übersetzung&quot;des Webeditors aufgelöst. (16961, 16879)
- Bei Übersetzungsprojekten werden mit der Experience Manager Guides-Version 4.3.1 keine neuen Sprachaufträge zu Adobe Experience Manager 6.5 SP18 hinzugefügt. (15398)
- **Accept Translation** kann die Übersetzung temporärer Dateien nicht abschließen. (14665)
- Das Hinzufügen eines aktualisierten Themas in einem aktiven Übersetzungsprojekt führt zu einem doppelten Thema und der Prozess schlägt fehl. (7688)
- Verweise werden beim Übersetzen in mehrere Sprachen nicht korrekt als Direkt oder Indirect gefiltert. (17891)
- XLIFF-basierte Übersetzung schlägt bei Benutzern ohne Administratorrechte mit Fehler fehl.(17296)
- Der Titel der übersetzten Dateien wird nach der zweiten Übersetzung auf Englisch zurückgesetzt, obwohl der Inhalt übersetzt wurde. (15200)
- Wenn Sie ein Übersetzungsprojekt mit dem **Übersetzungsstatus** als **Gestartet** auswählen, wird eine falsche Seite geöffnet. (13248)
- Den Übersetzungsprojekten, die durch Auswahl der Option **Nur Struktur erstellen** erstellt wurden, werden keine UUIDs zugewiesen. (18980)


## Bekannte Probleme

Adobe hat die folgenden bekannten Probleme für Version 4.6.0 identifiziert:
- Wenn Sie eine Vorgabe vom Typ **AEM Sites** öffnen (nicht veraltet), wird das Thema als verschmutzt markiert.
- Das ausgewählte Bedienfeld wird beim Aktualisieren des Browsers auf der Registerkarte **Ausgabe** nicht beibehalten.
- Themen können nicht zwischen zwei `topicrefs` in die Ansicht **Autor** gezogen und dort abgelegt werden.
- Die in der Vorgabe angewendete Bedingungsfilterung wird nicht über **Als PDF herunterladen** angewendet.
- Die Erstellung eines einzelnen Themas aus dem Zuordnungsbereich generiert alle in der Vorgabe **AEM Sites** ausgewählten Themen (nicht veraltet).
- Die Referenz zum Thema scheint in der Benutzeroberfläche fehlerhaft zu sein, wenn sie von der oberen Symbolleiste der DITA-Map eingefügt wird.
- Die native PDF-Generierung schlägt für eine DITA-Zuordnung fehl, wenn sie fehlende Verweise aufweist.
- Sobald der Dokumentstatus eines Themas auf **Fertig** aktualisiert wurde, ist das Symbol **Neue Version starten** nur im Modus **Vorschau** des Themas verfügbar.



