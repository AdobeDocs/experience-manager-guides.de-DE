---
title: Versionshinweise | Behobene Probleme in Adobe Experience Manager Guides Version 2026.09.0
description: Erfahren Sie mehr über die Fehlerbehebungen in der Version 2026.09.0 von Adobe Experience Manager Guides as a Cloud Service.
source-git-commit: 71ddd55d2a6848449d5810701b60e9f69a29112b
workflow-type: tm+mt
source-wordcount: '1241'
ht-degree: 0%

---

# Es wurden Probleme in der Version 2026.09.0 behoben

Dieser Artikel behandelt die in verschiedenen Bereichen der Version 2026.09.0 von Adobe Experience Manager Guides as a Cloud Service behobenen Fehler.

Weitere Informationen zu den neuen Funktionen und Verbesserungen finden Sie [Neue Funktionen in der Version 2026.09.0](./whats-new-2026-09-0.md).

Erfahren Sie mehr [Upgrade-Anweisungen für die Version 2026.09.0](./upgrade-instructions-2026-09-0.md).

## Editor 2.0

- Wenn Sie eine Tabelle aus dem Autorenmodus kopieren und in den Autorenmodus einfügen, werden Attribute wie `colwidth` und alle anderen in `colspec` definierten Attribute entfernt, wodurch die Spaltenbreiteneinstellungen verloren gehen. (GUIDES-52916)
- Leerzeichen, die unmittelbar vor dem Löschen eines Inline-Tags in einer Tabellenzelle eingegeben `<entry>`. (GUIDES-49144)

## Authoring

In diesem Abschnitt werden die in Authoring behobenen Fehler behandelt, die sowohl in Editor 1.0 als auch in Editor 2.0 auftreten.

- Auf Bildschirmen mit niedriger Auflösung wird das Dialogfeld Keyword einfügen nicht angezeigt, wenn ein Keyword aus der Symbolleiste eingefügt wird, während es bei Verwendung der Option **Mehr** wie erwartet geöffnet wird. (GUIDES-48304)
- Beim Speichern eines Themas, wenn die Schematron-Validierung mit einer leeren Regeldatei konfiguriert wird, wird eine ungenaue, allgemeine Fehlermeldung angezeigt. (GUIDES-48106)
- Schematronregeln, die einen Textknotenkontext verwenden, führen keine Trigger-Validierung durch. (GUIDES-14500)
- Durch Einfügen eines Querverweises mit der Option **Weblink** wird ein `scope=local` Link hinzugefügt und der `href` geändert, anstatt wie erwartet einen `scope=external` einzufügen. (GUIDES-48457)
- Das Speichern einer referenzierenden Zuordnung führt zu einem fehlerhaften Verweis, anstatt zur richtigen Zuordnung aufgelöst zu werden, wenn ein Autor die referenzierte Zuordnung verschiebt, während ein anderer Autor gleichzeitig einen Verweis zu ihr in einer nicht gespeicherten Zuordnung hinzufügt. (GUIDES-47467)

## Asset-Management

- Die Asset-Status-API gibt nicht den richtigen Status für Assets zurück, deren Pfad ein Komma enthält. (GUIDES-49065)
- Der DITA-Elementfilter in der Assets Admin-Suchleiste wendet den eingegebenen Wert nicht an, sodass die Suchergebnisse nicht gefiltert werden. (GUIDES-48450)
- Die Versionsbereinigung kann in mehreren Szenarien nicht abgeschlossen werden, darunter bestimmte Dateitypen, Assets mit fehlenden Metadaten und große Berichte, anstatt die Bereinigung abzuschließen und einen genauen Bericht zu generieren. (GUIDES-43453)
- Beim Umbenennen eines Assets mit einem GUID-basierten Dateinamen in eine andere GUID mithilfe des Vorgangs Verschieben in der Assets-Benutzeroberfläche wird die ursprüngliche eindeutige GUID des Assets durch die neue GUID ersetzt. (GUIDES-43006)

## Publishing

- Wenn Sie eine Ausgabe von AEM Sites (mit Composite Component Mapping) mit einer Grundlinie generieren, die auf eine ältere Version abzielt, wird der Seiteninhalt korrekt auf diese ältere Version angezeigt, aber die Seitenmetadaten zeigen stattdessen die aktuelle Version an. (GUIDES-49325)
- Wenn Seiten mithilfe der Massenaktivierung repliziert werden, werden die Replikations-Tracking-Eigenschaften nur auf der Stammseite und nicht auf untergeordneten Seiten festgelegt, sodass es schwierig ist zu bestimmen, welche Inhalte seit der letzten Replikation geändert wurden. (GUIDES-37871)
- Wenn das Feld **label** im Dialogfeld „Baseline erstellen/bearbeiten“ zum ersten Mal den Fokus erhält, werden die Vorschläge für die automatische Vervollständigung durch Einfügen oder Eingabe nicht korrekt gefiltert und das Feld zeigt alle Vorschläge anstelle der gefilterten Ergebnisse an. (GUIDES-50143)
- Die Verzweigungsfilterung erzeugt zusätzliche Seiten für unerwünschte Themen, die als `keydef` verwendet werden (die durch DITA-OT `resource-only ="true"` sind). (GUIDES-19701)
- Die Zuordnungssammlung aktiviert die Option **Veröffentlichen** für Vorgaben, die noch nicht generiert wurden. (GUIDES-50510)
- Im Abschnitt Veröffentlichungsverlauf wird kein Platzhaltertext angezeigt, wenn eine neu erstellte Zuordnungssammlung keine Veröffentlichungsdatensätze enthält. (GUIDES-50366)
- Das Anwenden eines ICC-Farbprofils auf eine native PDF-Vorgabe führt dazu, dass die Ausgabegenerierung fehlschlägt, und CMYK-Farben werden auch dann nicht korrekt gerendert, wenn ein direkter Profilpfad verwendet wird. (GUIDES-47137)
- Die für eine native PDF-Vorgabe konfigurierte Anschnitteeinstellung wird nicht in der generierten Ausgabe angezeigt. (GUIDES-47034)
- Das Feld **Text vor Umbruch** für die Fortsetzung der Tabelle rendert nur die lokalisierte Zeichenfolge und ersetzt nicht den Platzhalter für die Seitenzahl. (GUIDES-32872)
- Der ICC-Profil-Browser zeigt fälschlicherweise DITA-Dateien an, anstatt nur ICC-Dateien anzuzeigen. (GUIDES-25017)
- Entwurfskommentare werden in der nativen PDF-Ausgabe nicht gerendert. (GUIDES-47044)
- Ein innerhalb eines `title` platzierter Kommentar-Entwurf wird unerwartet in der veröffentlichten Ausgabe angezeigt. (GUIDES-10686)
- Wenn Sie im Zuordnungs-Dashboard eine andere Voreinstellung auswählen, wird ein Aufruf zum Abrufen von Peer-Links ausgeführt, was zu einer zusätzlichen Verarbeitung führt. (GUIDES-53703)

## Übersetzung

- Beim Starten einer Übersetzung mit einem XLIFF-Projekt wird ein leeres Projekt erstellt, das nie in den Status „In Bearbeitung“ wechselt. (GUIDES-51759)
- Das Verschieben von Inhalten von einem Sprachordner in einen anderen mithilfe des Vorgangs zum Verschieben von Assets verhindert, dass Autoren diese Inhalte für die Übersetzung im Bedienfeld Übersetzung auswählen. (GUIDES-49386)
- Das Senden von Assets zur Übersetzung mit der Option **Zu vorhandenem Übersetzungsprojekt hinzufügen** während eine andere Übersetzungsanfrage (entweder die Erstellung eines neuen Projekts oder *Zu vorhandener* hinzufügen) für dasselbe Projekt noch verarbeitet wird, führt zu einem Konflikt. (GUIDES-49354)

## Grundlinie

- Die gespeicherte Baseline-Auswahl einer Voreinstellung wird fälschlicherweise als *Keine Baseline* angezeigt, nachdem die Baseline gelöscht wurde oder während eine dynamische Baseline noch erstellt wird. (GUIDES-52690)

## Überprüfung

- Das Öffnen des Prüfungsbereichs oder das Anwenden eines Projektfilters dauert einige Zeit, bis die Aufgabenliste geladen ist. (GUIDES-48893)

## Berichte

- Durch das Generieren des Berichts über fehlerhafte Links für eine Zuordnung mit einer großen Anzahl von Themen bleibt die Berichtsoberfläche auf unbestimmte Zeit bei der Meldung **Details für fehlerhafte Links abrufen** hängen, was dazu führt, dass der Browser nicht reagiert und schließlich abstürzt. (GUIDES-37845)

## Lerninhalte

- Wenn ein neues Lernthema mit einer HTML oder Lernvorlage mit einer benutzerdefinierten Kopfzeile erstellt wird, wird der Thementitel nicht in der benutzerdefinierten Kopfzeile angezeigt. (GUIDES-52343)
- Der berechnete Genauigkeitsprozentsatz für ein Kursquiz unterscheidet sich geringfügig vom erwarteten Wert. (GUIDES-52346)
- Bei einem Kurs, bei dem ein Quiz versucht wird, unterscheiden sich die Punktzahlen geringfügig von der erwarteten berechneten Punktzahl. (GUIDES-52345)

## Bekannte Probleme

Adobe hat die folgenden bekannten Probleme in Version 2026.09.0 identifiziert:

- Durch das Ändern des Dokumentstatus eines bereits gesperrten Themas wird das gesamte Dokument aktualisiert. (GUIDES-53905)
- Bei Verwendung der Funktion „Vorschau mit Grundlinie“ beträgt das Zeitlimit für Vorschauanfragen für große Karten (mehr als 10.000 Themen) oder Karten mit einer hohen Anzahl von `keydefs` (z. B. 100 `keydefs` und 3.500 Themen). (GUIDES-54147)
- Bei DB-Servern wird die `keydef` nicht aufgelöst, wenn eine Zuordnung mit einem `keydef` ohne `href` mit aktivierter Option Vorschau mit Grundlinie angezeigt wird. (GUIDES-53878)
- Hotspot-Regionen, die für ein Imagemap-Asset konfiguriert sind, sind im Vorschaumodus nicht interaktiv, was verhindert, dass Autoren Hotspot-Links vor der Veröffentlichung validieren. (GUIDES-53398)<br>**Problemumgehung**: Fügen Sie das Bild ein, das Sie in eine Imagemap konvertieren möchten, wählen Sie **Imagemap bearbeiten** aus dem Kontextmenü aus und konfigurieren Sie die Hotspot-Links.
- Wenn Sie eine Karte mit einer vorhandenen Grundlinie in einen anderen Ordner verschieben, während die Karte geöffnet ist, bleibt der Umschalter **Vorschau mit Grundlinie** im Vorschaumodus ausgewählt, aber die Grundlinie wird nicht mehr in der Dropdown-Liste angezeigt. (GUIDES-54284)<br>**Problemumgehung**: Sie können die Zuordnung schließen und erneut öffnen, um das Problem zu beheben.
- In einer neu konfigurierten AEM Cloud Service-Umgebung (AEM as a Cloud Service SDK) führt der Versuch, eine Zuordnungs- oder Themendatei zu erstellen, zu einem *Fehler beim Erstellen der* oder *Fehler beim Abrufen der DTD-Regel*. (GUIDES-53904)<br>**Workaround**: Sie können die AEM Cloud Service-Umgebung neu starten.
- Wenn zwei Autoren gleichzeitig an demselben Thema arbeiten, werden beim Sperren eines Themas, das bereits seit einiger Zeit von einem Autor geöffnet ist, die Metadateneigenschaften wie Versionsnummer, Beschriftungen, Dokumentstatus, Tags und andere nicht aktualisiert, selbst nachdem sie von dem anderen Autor geändert wurden, sodass veraltete Werte weiterhin angezeigt werden. (GUIDES-54810)<br>**Problemumgehung**: Schließen Sie das Thema und öffnen Sie es erneut, um die Metadaten zu aktualisieren und die neuesten Werte anzuzeigen.