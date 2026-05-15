---
title: Versionshinweise | Behobene Probleme in Adobe Experience Manager Guides Version 4.6.0
description: Erfahren Sie mehr über die Fehlerbehebungen in Version 4.6.0 von Adobe Experience Manager Guides
role: Leader
exl-id: fd12d627-5163-4edd-b28e-bef13267fcc9
TQID: https://experienceleague.adobe.com/zaQd6UfebgClEP7JxSWRwsGqIziDkIN3QLLP-iGufhM
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2:
  - id: a01bfd36-4ab8-4bf8-9dc0-5b45b890552e
  - id: a3bd6397-2eb2-4908-a61c-226e26855dca
  - id: ab01a588-7dea-43f2-a699-0b3f128465d6
  - id: c6d09140-3c91-45d3-b7ed-b681af752f43
  - id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
  - id: d90290ec-3e61-4ebd-8649-bcafe0836803
subfeature_v2:
  - id: ad602516-aca3-4247-9ae8-f393d958efa9
  - id: c38bc65b-dea9-4a6e-9de3-3daf1d2b388b
  - id: d4f22c6d-7923-41e5-9da3-527ff8df4bc8
  - id: d6596f3f-92a7-43ec-b444-237db6adad05
  - id: f89f75b0-cf2e-4e96-aec8-fe8c39cbd0ef
  - id: fd6cc9e1-e5e5-494e-b7b1-a32f2d6cd7c9
role_v2:
  - id: f8a45b24-4be7-4f1b-909b-60d06b483a20
topic_v2:
  - id: a004cc84-67b9-4a33-a3a7-8ec7273ef4dc
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 2019
ht-degree: 5%

---

# Es wurden Probleme in Version 4.6.0 (September 2024) behoben


Dieser Artikel behandelt die in verschiedenen Bereichen von Version 4.6.0 von Adobe Experience Manager Guides behobenen Fehler.


Weitere Informationen zu den neuen Funktionen und Verbesserungen finden Sie unter [Neue Funktionen in Version 4.6.0](whats-new-4-6.md).

Erfahren Sie mehr über [Upgrade-Anweisungen für die Version 4.6.0](../release-info/upgrade-instructions-4-6-0.md).

## Authoring

- Die Option **Suchen** funktioniert in der Ansicht **Source** nicht. (18610)
- **Auschecken** und **Einchecken** werden zusammen angezeigt, wenn `autocheckout` im xmeditor konfiguriert ist. (18088)
- Große DITA-Karten werden langsam geladen und brauchen beim Wechsel zur **Layout**-Ansicht etwas Zeit.  (17590)
- Fehler für doppelte Bild-IDs in den Themen hindern den Benutzer daran, ein Thema zu speichern oder zu erstellen. (17528)
- Das Kopieren und Einfügen von Themen mit einer Größe von mehr als 15 KB schlägt mit einem unerwarteten Fehler fehl. (17171)
- Die Funktion zum Ändern des Dokumentstatus im Bedienfeld **Dateieigenschaften** funktioniert nicht ordnungsgemäß und ändert sich in den *Entwurf*. (17088)
- Beim Ändern der XML-Editor-Einstellungen mithilfe eines benutzerdefinierten Ordnerprofils wird der `ui_config.json` mit einer falschen Datei aktualisiert. (17011)
- Wiederverwendbare Inhaltsbedienfelder enthalten keine Elemente, wenn die **Benutzereinstellungen** so eingestellt sind, dass Dateien nach &quot;**&quot; angezeigt**. (16896)
- Unterelemente innerhalb des Tabellentitelelements können im **-Modus** Experience Manager Guides nicht gerendert werden. (16691)
- **Sonderzeichen** die mit Escape-Zeichen geschrieben wurden, werden aus dem Thema entfernt, nachdem sie in Experience Manager Guides hochgeladen wurden. (16495)
- Vimeo-Videos unterstützen in Experience Manager Guides keine Vollbildfunktion. (15996)
- Das Einfügen langer vorformatierter Textsequenzen in `<pre>` oder `<codeblock>` führt zu abgeschnittenem Text. (15859)
- Das Löschen von Inhalten erfolgt aufgrund doppelter GUIDs, wenn Vorlagen über Code installiert werden, aber nicht verarbeitet werden. (15858)
- Experience Manager Guides erfüllt das Attribut **Verarbeitungsrolle** im Modus **Vorschau** nicht. (15787)
- Der Editor löscht gelegentlich zusätzlichen Text über den ausgewählten Bereich hinaus. (15708)
- Es ist nicht möglich, große Tabellen aus Word-Dokumenten oder HTML zu kopieren und in den Web-Editor einzufügen. (15369)
- Fehlende APIs oder Ereignisse zur Erfassung des Hinzufügens eines Attributs zu einem Element oder zum Einfügen eines neuen Elements. (15351)
- Hinzufügen `<data>` Tags innerhalb `<ol>` Tags im Web-Editor nicht möglich. (15161)
- Die **Element**-Platzhalterkomponente bewirkt, dass die Benutzeroberfläche einfriert. (14957)
- Der Web-Editor kann keine PPTX-Dateien hochladen. (14837)
- Beim Suchen eines Textes im Web-Editor kehrt der Cursor beim Drücken der Eingabetaste zum ersten Vorkommen des gesuchten Textes zurück. (14820)
- Das automatische Speichern verursacht mehrere Probleme, positioniert den Cursor neu und erfordert manuelle Klicks im Dokument. (14253)
- Durch Drücken der **Eingabetaste** in einer Tabellenzelle innerhalb des Texts wird der Absatz nicht wie erwartet aufgeteilt. (14251)
- Große Dateien werden nicht in den Web-Editor geladen und bewirken, dass der Browser einfriert. (13227)
- Die Suchergebnisse werden nach dem Öffnen einer Datei, die über global (Suchen **Ersetzen) gefunden wurde,**. (12142)
- In der Quellansicht wird `</conbody>` gelegentlich an falschen Stellen eingefügt. (11305)
- Der Komponentenpfad `/libs/fmdita/components/versions` ist hartcodiert, und die Benutzer können ihn nicht überlagern. (8779)
- `<conref>` für ein Thema, auf das in einer DITA-Karte verwiesen wird, wird nicht in der Vorschau im Editor angezeigt. (17794)
- Das Experience Manager DITA-Handbuch schlägt nach Verwendung der Funktion zum automatischen Einrücken keinen Trigger bei der Speicherfunktion vor. (16482)
- Die QuickInfo-Funktion kann das Source-Feld im XML-Editor nicht aktualisieren. (15847)
- Die Funktion **UUID-Link freigeben** funktioniert nicht für die Bilder in Adobe Experience Manager. (15598)
- In der **Autoren** Ansicht tritt ein Problem beim Kopieren und Einfügen auf, wenn Leerzeichen ohne Unterbrechung verwendet werden, was zum Überlauf von Text führt. (15541)
- Überschneidende Textprobleme treten bei `<reltable>` und `<fig>` Tags auf. (15238)
- Flimmernde Probleme treten im Bedienfeld &quot;**&quot;**. (15237)
- In `<othermeta>` Element in `<topicmeta>` wird beim Hinzufügen eines `<conref>` zu einer anderen DITA-Zuordnung auch die Zuordnungs-ID zusammen mit der ID des Elements angehängt. (15226)
- Beim Löschen eines Zeichens oder Worts im Inhalt springt der Cursor zwischen den Blockelementen. (15224)
- Datei, die durch die Fehlermeldung „ausgecheckt“ wurde, wird falsch angezeigt, wenn Bearbeitungsdateien von einer anderen Registerkarte verschoben werden, wenn Token abgelaufen sind oder wenn der Benutzer abgemeldet wird. (15223)
- Die `<conref>` kann nicht über das Bedienfeld **Attribute** aktualisiert werden, wenn Änderungen vorgenommen werden. (15209)
- Bei der Auswahl eines Bildes in einer Tabellenzelle wird die gesamte Zelle ausgewählt. (15188)
- Das **Attribute**-Bedienfeld wird in der Source-Ansicht des Web-Editors nicht angezeigt. (14387)
- `<Topicref>`, die mit `<keyref>` hinzugefügt wurden, werden in nativen PDF nicht angezeigt. (11974)
- Unerwünschte, nicht umbrechende Leerzeichen werden beim Bearbeiten am Ende eines Tags im Web-Editor hinzugefügt. (11786)
- Der Inhalt wird beim Korrigieren der Rechtschreibfehler in DITA-Dateien gelöscht. (11610)
- Beim Öffnen eines DITA-Themas oder einer DITA-Zuordnung auf einer neuen Registerkarte zum Bearbeiten wird die Auswahlnavigation in der Assets-Benutzeroberfläche eingefroren. (4992)
- Durch das Löschen von Prüfungsknoten wird die Möglichkeit zum Öffnen und Anzeigen von Kommentaren in Adobe Experience Manager Guides beeinträchtigt. (15366)
- Die DITA-Version zeigt den Benutzernamen in der Assets-Benutzeroberfläche falsch an. (17580)
- Das `<title>` wird automatisch hinzugefügt, wenn das `<fig>` als Ausschnitt eingefügt wird. (18562)
- Beim Hochladen einer großen Anzahl von Dateien mit sehr vielen Datensätzen in Experience Manager Guides treten Probleme auf.(17008)
- Der Web-Editor zeigt standardmäßig nicht das richtige Keyword an, insbesondere wenn das Keyword in untergeordneten Zuordnungen anders definiert ist. (14748)
- Der **Dokumentstatus** wird nicht angezeigt, wenn die Eigenschaften von mehr als 50 Dateien stapelweise in der Zuordnungsansicht des Web-Editors bearbeitet werden. (14574)
- Das Verhalten der Schaltfläche Schließen ist bei Verwendung der Funktion zum automatischen Speichern inkonsistent. (10996)
- In MathML-Elementen treten beim Einfügen neuer Elemente oder beim Ändern von Gleichungen Validierungsprobleme auf. (10624)
- Die Funktion „Änderungen nachverfolgen“ funktioniert nicht bei Text, der mit koreanischen Zeichen beginnt. (14538)
- Verknüpfte Bilder aus den Themen werden nach der Erstellung der Version nicht in der Grundlinie angezeigt. (16931)

## Publishing

- Der Querverweis auf den -Schlüssel wird in der nativen PDF-Ausgabe nicht aufgelöst. (18087)
- Der Fehler **duplicate_value** tritt gelegentlich auf, wenn ein vorhandener Artikel in Salesforce erneut veröffentlicht wird. (17932)
- Die Validierung der Salesforce-Verbindung schlägt mit der Lightning-URL fehl. (17797)
- Bei Auswahl der Option **Im Topicmeta hinzugefügte Metadaten verwenden** werden die Metadateneigenschaften nicht in den Dokumenteigenschaften der nativen PDF-Ausgabe weitergegeben.(17283)
- Die Bedingungsfilterung in der nativen PDF-Ausgabe funktioniert im Vergleich zu DITA-OT nicht wie erwartet. (17095)
- Im Inhaltsverzeichnis werden `<sub>` oder `<sup>` Tags in der nativen PDF-Ausgabe nicht berücksichtigt. (17028)
- Bei der Crossmap-Verknüpfung werden nicht alle übergeordneten Karten in den Einstellungen des Veröffentlichungskontexts für einen Link mit dem `scope="peer"` angezeigt. (16700)
- Die AEM-Site-Generierung und die inkrementelle Veröffentlichungs-API funktionieren nicht erwartungsgemäß. (16666)
- Die Generierung der AEM-Site-Ausgabe schlägt fehl, wenn **Option „Verwaiste Site löschen** aktiviert ist. (15896)
- Die alten Attribute werden in den **Bedingungsvorgaben“ beibehalten** wenn neue oder vorhandene Attribute hinzugefügt oder entfernt werden. (15890)
- In der JSON-Ausgabe können Metadaten aus DITA-Zuordnungen oder Themen nicht an die JSON-Ausgabedateien übertragen werden. (15713)
- Der Inhalt der RTL-Sprache wird in der nativen PDF-Veröffentlichungsausgabe nicht korrekt verarbeitet. (15709)
- Die native Veröffentlichung von PDF schlägt fehl, wenn die Voreinstellung umbenannt wird. (15662)
- Die **sourcePath**-Eigenschaft ist in der veröffentlichten AEM-Site-Ausgabe falsch. (15502)
- Die Auswahl und Anpassung von Sprachvariablen funktioniert in der nativen PDF-Ausgabevorgabe nicht ordnungsgemäß. (15399)
- Die native PDF-Generierung schlägt bei der Verwendung einer großen Stylesheet- oder Layout-Vorlage fehl. (15344)
- Inhalte werden in der veröffentlichten Ausgabe nicht richtig gerendert, wenn `<conref>` mit einem absoluten Pfad verwendet wird. (15222)
- Die AEM Sites-URL-Verkürzung funktioniert aufgrund von Konflikten zwischen dem `fmdita rewriter` und `ResourceResolver` nicht. (14793)
- Die native PDF-Generierung schlägt mit einem Fehler im Zusammenhang mit dem Abrufen von Abhängigkeiten für Node.js fehl. (14445)
- Die **processing-role=„resource-only“**, **search=„no“** und **chunk=„to-content“** werden unabhängig in der AEM Sites-Ausgabe angezeigt. (14442)
- `<Conref>` wird im `Preview` des Web-Editors und in der nativen PDF-Ausgabe nicht aufgelöst. (17827)
- In nativem PDF werden verschachtelte DITA-Themen im Inhaltsverzeichnis (TOC) falsch angezeigt. (16742)
- Miniaturansichten, die von **Dynamic Media** für Videodateien generiert werden, bleiben in der veröffentlichten Ausgabe nicht erhalten. (15656)
- Die referenzierte PDF wird während der Massenaktivierung **veröffentlichten Inhalte nicht** dem Dashboard „Massenveröffentlichung“ aktiviert. (17793)
- Wenn ein Ordner, der 2K-Zuordnungen enthält, im Ordnerpfad innerhalb eines Ordnerprofils festgelegt ist, schlagen die auf die Ausgabevorgabe angewendeten Änderungen fehl. (14852)
- Die Themenwiederherstellung schlägt aufgrund des vorkonfigurierten Regenerierungsthemas oder eines inkrementellen Fehlers bei der Veröffentlichungs-API fehl. (18452)
- Die Bedingungsvoreinstellung ruft nach dem Upgrade von Experience Manager Guides keine aktualisierten Attribute ab. (18174)
- Inhaltsreferenzen werden für die native PDF-Ausgabe nicht korrekt aufgelöst, wenn sich die Datei mit den Schlüsseldefinitionen nicht im selben Ordner wie die DITA-Zuordnung befindet. (15062)
- Das Dashboard zur Massenveröffentlichung enthält leere Daten für Karten, die sich noch im Übersetzungsprozess befinden. (19352)
- Die Massenaktivierung von veröffentlichten Inhalten funktioniert nicht für lokalisierte Karten. (17638)



## Verwaltung


- Die Konvertierung von InDesign nach DITA weist einen hartcodierten Konfigurationspfad auf, sodass die benutzerdefinierten Konfigurationsdateien nicht ausgewählt werden. (16891)
- Nicht geschlossene **Resource Resolver** führen nach der Version 4.3.1 von Experience Manager Guides zu einer zunehmenden Anzahl von Sitzungen und `PathNotFoundException`. (15604)
- Fehler beim Installieren von Handbuchpaketen in großen Repositorys. (15160)
- Das Erstellen einer Grundlinie mit der Java-API funktioniert nicht mit Experience Manager Guides. (14787)
- Die `/bin/fmdita/import`-API bleibt unbegrenzt in der ausstehenden Anfrage hängen, wenn das Hochladen von Assets 500 MB überschreitet. (14743)
- Bearbeiten einer bestehenden Baseline und Auswählen einer bestimmten Version Trigger-Anwendungsfehler. (14451)
- Die Ausführung des Nachbearbeitungs-Skripts schlägt aufgrund eines Ausnahmefehlers **FileNotFoundException** fehl. (16517)
- Dynamische Titel mit `<conkeyref>` werden nicht in der Berichtsthemenliste angezeigt. (16967)
- Die ungenaue Anzahl **Themenliste** tritt in der Benutzeroberfläche für Experience Manager Guides-Berichte aufgrund der nicht gepatchten Eigenschaften beim Kopieren von DITA-Assets auf. (15529)
- Themen, die externe Verweise mit %20 in der URL enthalten, zeigen beschädigte Dateiverweise an. (15347)
- Die Eigenschaften fmditaMaprefs und fmditakeydefrefs zeigen relative Pfade an, obwohl absolute Pfade für die DITA-Zuordnung und Themen festgelegt wurden. (18353)
- Der Pfad für die Überlagerungsfunktion ist für die koreanische Sprachdatei hartcodiert und nicht korrekt ausgewählt. (17089)
- Die Standardzeit bei der Baseline-Erstellung im Web-Editor wird als 00:00 anstelle der aktuellen Zeit angezeigt. (15215)

## Überprüfung

- Das Abrufen der Benutzerliste beim Erstellen einer Prüfungsaufgabe schlägt fehl, wenn die Benutzeranzahl 25 überschreitet. (17329)
- Prüfungsthemen werden nicht in der richtigen Reihenfolge angezeigt. (16319)
- Im Web-Editor wird das Überprüfungsfeld langsam geladen. (14680)
- Reviewer können bei der Durchführung einer Dokumentüberprüfung in Experience Manager Guides keine Leerzeichen hinzufügen, hervorheben oder ausstreichen. (14752)
- Wenn ein(e) Benutzende(r) eine Prüfungsaufgabe aktualisiert, erhalten nicht alle zugewiesenen Reviewer eine Benachrichtigung über die Aktualisierung. (9496)

## Übersetzung

- Die Verweise von übersetzten Assets werden nicht aktualisiert. (18086)
- XLIFF-Projekte mit menschlicher Übersetzung können nicht erstellt werden. (16964)
- Der Titel mit `<conref>` oder `<conkeyref>` wird in den Baseline- und Übersetzungs-Dashboards des Web-Editors nicht aufgelöst. (16961, 16879)
- Übersetzungsprojekte können mit der Version 4.3.1 von Experience Manager Guides keine neuen Sprachaufträge zu Adobe Experience Manager 6.5 SP18 hinzufügen. (15398)
- **Übersetzung akzeptieren** kann die Übersetzung von temporären Dateien nicht abschließen. (14665)
- Das Hinzufügen eines aktualisierten Themas zu einem aktiven Übersetzungsprojekt führt zu einem doppelten Thema und der Prozess schlägt fehl. (7688)
- Verweise werden bei der Übersetzung in mehrere Sprachen nicht korrekt als direkt oder indirekt gefiltert. (17891)
- Die XLIFF-basierte Übersetzung schlägt für Benutzer ohne Administratorrechte mit dem Fehler fehl.(17296)
- Der Titel der übersetzten Dateien kehrt nach der zweiten Übersetzung ins Englische zurück, obwohl die Inhalte übersetzt wurden. (15200)
- Wenn Sie ein Übersetzungsprojekt mit dem **Übersetzungsstatus** als **In Bearbeitung** auswählen, wird eine falsche Seite geöffnet. (13248)
- Den Übersetzungsprojekten, die durch Auswahl der Option **Nur Struktur erstellen** erstellt wurden, werden keine UUIDs zugewiesen. (18980)


## Bekannte Probleme

Adobe hat die folgenden bekannten Probleme in Version 4.6.0 identifiziert:
- Das Öffnen einer **AEM Sites**-Vorgabe (nicht veraltet) kennzeichnet das Thema als beschädigt.
- Das ausgewählte Bedienfeld wird bei der Browser-Aktualisierung auf der Registerkarte **Ausgabe** nicht beibehalten.
- Themen können nicht zwischen zwei `topicrefs` in der Ansicht **Autor** gezogen werden.
- Die in der Voreinstellung angewendete Bedingungsfilterung wird nicht über &quot;**als PDF herunterladen“**.
- Bei der Erstellung eines einzelnen Themas im Zuordnungsbereich werden alle Themen generiert, die in der Vorgabe **AEM Sites** ausgewählt wurden (nicht veraltet).
- Der Verweis des Themas erscheint in der Benutzeroberfläche fehlerhaft, wenn er in der oberen Symbolleiste der DITA-Zuordnung eingefügt wird.
- Die native PDF-Generierung schlägt für eine DITA-Zuordnung fehl, wenn Verweise fehlen.
- Sobald der Dokumentstatus eines Themas auf „Fertig **aktualisiert wurde** ist das Symbol **Neue Version starten** nur im **Vorschau** des Themas verfügbar.
- Bei Auswahl einer DITA-Datei in der Asset-Benutzeroberfläche wird die Option **In FrameMaker öffnen** angezeigt, auch wenn sie in den Konfigurationseinstellungen deaktiviert ist.
