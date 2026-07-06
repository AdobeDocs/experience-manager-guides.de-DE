---
title: Versionshinweise für Adobe Experience Manager Guides 3.8 und 3.8.5
description: Die wichtigsten neuen Funktionen und Verbesserungen in den Versionen 3.8 und 3.8.5 von Adobe Experience Manager Guides (früher als XML Documentation-Lösung bezeichnet).
source-git-commit: ff3d35832b80f6221f1261498934ab74261b282b
workflow-type: tm+mt
source-wordcount: '1589'
ht-degree: 0%

---


# Versionshinweise | Adobe Experience Manager Guides 3.8

**Haftungsausschluss**:

*Adobe Experience Manager Guides* wurde zuvor als *XML Documentation für Adobe Experience Manager* gekennzeichnet. Beachten Sie, dass sich bestimmte Verweise in der Dokumentation weiterhin auf das vorherige Branding beziehen können, aber dennoch für das aktuelle Angebot gelten.

In diesen Versionshinweisen sind die wichtigsten neuen Funktionen und Verbesserungen in Version 3.8.x von XML Documentation für Adobe Experience Manager aufgeführt.

## Neue Funktionen und Verbesserungen in Version 3.8.5

### Fehlerbehebungen

Die in Version 3.8.5 behobenen Fehler sind unten aufgeführt:

- Grundlegende Unterstützung für die PDF-Ausgabe über FrameMaker Publishing Server fehlt.
- Die Ein- und Auschecken-API für FrameMaker oder Oxygen funktioniert nicht ordnungsgemäß, wenn die Berechtigungen auf Ordnerebene für verschiedene Gruppen in AEM eingerichtet wurden.
- Die Inhaltsvorschau wird nicht auf der Seite der Assets-Benutzeroberfläche angezeigt.
- Die Schaltfläche &quot;Source&quot; funktioniert nicht auf der Seite der Assets-Benutzeroberfläche.
- Wenn ein Bild über die Funktion Bild einfügen des Web-Editors eingefügt wird, ändert sich der relative Pfad des eingefügten Bildes in seinen absoluten Pfad.
- Die Dropdown-Liste FMPS-Voreinstellung wird in der Benutzeroberfläche der neuesten Version 3.8 nicht angezeigt.
- Das Bedienfeld Favoriten wird nicht angezeigt, wenn es eine große Anzahl von Assets in DAM enthält und ein neues Favoritenelement aus dem XML-Web-Editor hinzugefügt wird.
- Interne Umleitung *Sling:mapping* die alle Links umleitet funktioniert nicht und zeigt lange URLs (mit internen Pfaden) anstelle der kurzen URLs für die Web-Seiten an.
- In der Listenansicht zeigt die Spalte Geändert „Externer Benutzer“ anstelle des Benutzernamens an, wenn Assets hochgeladen oder aus der Assets-Benutzeroberflächenseite importiert werden (außer über den Package Manager).
- Der Titel wird auf der Registerkarte Themen im Karten-Dashboard nicht korrekt angezeigt.
- Bei Aktivierung der Funktion zum Reduzieren von Knoten werden einige unerwünschte Junk-Zeichen in der HTML-Ausgabe gespeichert.
- Änderungen am Profilordner aufgrund der Benutzereinstellungen werden für eine bereits geöffnete Datei nicht automatisch neu geladen, der Browser muss jedoch aktualisiert werden.
- Die über die Option Zuordnung herunterladen generierte Ausgabe enthält einige fehlende Themen, wenn einige Validierungsfehler vorliegen.

## Neue Funktionen und Verbesserungen in Version 3.8

### Konfigurationsaktualisierungen für die Dateibenennung

Beim Erstellen von DITA-Themen in der XML Documentation-Lösung dürfen Benutzende Sonderzeichen als Teil von Dateinamen verwenden. Dies führte zu kodierten URLs bei der Erstellung von AEM-Site-Seiten. Um diese Konvertierung in URL zu vermeiden, ermöglicht die Version 3.8 von XML Documentation-Lösungen einem Administrator, eine Liste von Sonderzeichen zu definieren, die nicht den standardmäßigen Dateinamenkonfigurationen entsprechen (a-z A-Z 0-9 - _). Dies bedeutet, dass Sie zwar eine Liste von Sonderzeichen in einem Dateinamen einschließlich eines Leerzeichens konfigurieren können, sie jedoch durch einen Bindestrich (-) ersetzt wird.

### Änderungen bei der Namenserstellung für AEM-Sites

Beim Authoring ist es möglich, denselben Dateinamen für eine oder mehrere Dateien in verschiedenen Ordnern zu verwenden. Während des Veröffentlichungsprozesses der AEM-Site wurden die Seitennamen mit einem Suffix versehen, wenn mindestens ein doppelter Dateiname vorhanden war. Mit Version 3.8 der XML Documentation-Lösung wurde der Prozess zur Namenserstellung für die AEM-Site behoben. Das -Suffix wird nur dann an den generierten Seitennamen angehängt, wenn ein doppelter Dateiname vorhanden ist.

### Neue Funktionen und Verbesserungen

In den folgenden Bereichen des Produkts wurden eine Reihe neuer Funktionen und Verbesserungen eingeführt.

#### Web-Editor

- Sie können jetzt beim Erstellen einer Version eines Themas im Web-Editor eine Bezeichnung aus einer Dropdown-Liste auswählen.

  ![Beschriftungen in einer Dropdown-Liste](assets/labels-drop-down-saving-topic-res.avif)

- Das Überprüfungsbedienfeld im Web-Editor ist jetzt leistungsfähiger, sodass Sie ein Thema auf eine Version zurücksetzen können, die zur Überprüfung freigegeben wurde. Sie können Prüfungskommentare problemlos in die überprüfte Version integrieren, ohne sich daran erinnern zu müssen, welche Version des Themas zur Überprüfung freigegeben wurde.

  ![Thema auf Review-Version zurücksetzen](assets/revert-review-topic.avif)

- Es wurde ein neuer visueller Hinweis eingeführt, der angibt, ob Sie mit der neuesten Version eines Themas oder einer früheren Version arbeiten.

  ![Versions-Cue](assets/old-version-icon.avif)

- In dieser Version wurde eine neue Funktion zum Versionsverlauf eingeführt. Verwenden Sie die Funktion Versionsverlauf für Folgendes:
   - Zeigt eine Liste aller Versionen des aktuell aktiven Themas zusammen mit Beschriftungen an, die für jede Version hinzugefügt wurden.
   - Wiederherstellen einer früheren Version des Themas

  ![Versionsverlauf](assets/version-history.avif)

- Es wurde eine neue Funktion zur Versionsbeschriftungsverwaltung hinzugefügt, mit der Sie Beschriftungen auf die aktuelle oder frühere Versionen eines Themas anwenden können.

  ![Versionskennzeichenverwaltung](assets/version-label-management.avif)

- Eine neue Funktion wurde hinzugefügt: „Zur Veröffentlichung genehmigen“, mit der ein Autor ein Asset als genehmigt markieren und es weiter zur Bearbeitung sperren kann.
- Beim Initiieren eines Überprüfungsprozesses können Sie jetzt Themen nach ihrem Status filtern.

  ![Auswahl von Prüfungsthemen basierend auf ihrem Status](assets/review-select-topic-on-state.avif)

- Der `<navtitle>` in einer Zuordnung wird automatisch mit dem Titel eines Themas ausgefüllt, der der Zuordnungsdatei hinzugefügt wird. Sie können die `<navtitle>` auch einfach über den Web-Editor aktualisieren.
- Im Seitenbereich wird jetzt eine Vorschau einer Tabelle mit einer großen Anzahl von Spalten angezeigt.
- Sie können mehrere Ausgabeklassen gleichzeitig über das Bedienfeld Eigenschaften (Mehrfachauswahl) anwenden.
- Bei der Vorschau eines Themas können Sie auch direkt im Web-Editor eine (bedingungslose) PDF-Ausgabe eines einzelnen Themas generieren.

  ![PDF-Ausgabe aus der Vorschau](assets/pdf-output-from-preview.avif)

- Blockieren Sie eine Veröffentlichungsanfrage, wenn gerade die Ausgabe derselben Voreinstellung generiert wird.
- Es wurde die Möglichkeit hinzugefügt, dass nur eine Gruppe berechtigter Benutzer Assets löschen kann, die aktive Rückverweise haben.
- Es wurde eine Funktion hinzugefügt, mit der der XML-Code aus der Source-Ansicht in der Assets-Benutzeroberfläche angezeigt oder kopiert werden kann, selbst wenn die Datei von einem anderen Benutzer ausgecheckt wurde.

  ![XML-Source-Ansicht](assets/xml-source-view-from-assets-ui.avif)

- Der Dateiname wird jetzt im Dialogfeld „Speichern“, im Bedienfeld „Wiederverwendbarer Inhalt“ und im Bedienfeld „Suchen und Ersetzen“ durch den Titel der Datei ersetzt.

#### Publishing

- **Konfiguration von Bereinigungsregeln für generierte Site-Seiten zulassen**: Als Administrator können Sie die Bereinigungsregeln für die Dateinamen der generierten AEM-Site- oder DITA-OT-Ausgabe definieren. Wenn Sie eine Ausgabe oder Ausgabe einer AEM-Site mit DITA-OT generieren, können Sie die folgenden Regeln konfigurieren, um die ausgangsgenerierten URLs oder Dateinamen zu bereinigen:
   - Wandeln Sie alle Zeichen in Kleinbuchstaben um.
   - Ersetzen Sie Sonderzeichen durch ein Trennzeichen.
   - Beschränken Sie einen langen Dateinamen auf eine vordefinierte Anzahl von Zeichen.

- Pushen Sie die Ausgabe einfach von Ihrer Autoreninstanz an die Veröffentlichungsinstanz, indem Sie das Dashboard für die Massenaktivierung verwenden. Sie können mit einer einzelnen Zuordnung oder einer Zuordnungssammlung arbeiten und die Ausgabevorgabe auswählen, die Sie für die Veröffentlichung verwenden möchten.

  ![Dashboard für Massenveröffentlichung](assets/bulk-publish-dashboard.avif)

#### Leistungsverbesserungen

- Knotenreduzierung für die AEM Sites-Ausgabe: Zuvor war die Site-Knotenstruktur der AEM Sites-Ausgabe zu tief. Jetzt haben Sie die Kontrolle, die Knotenstruktur zu reduzieren, um eine bessere Leistung zu erzielen.
- Unterstützung für die neueste Version der FrameMaker Publishing Server-Version vom Sommer 2020.
- Die während der Übersetzung generierten temporären Dateien werden jetzt entfernt, was den Übersetzungsprozess verbessert.

#### Weitere Verbesserungen

- Die Abhängigkeit des Workflows DAM-Update-Asset beim Nachverarbeiten von DITA-Inhalten wurde entfernt. Wenn im Workflow DAM-Update-Asset benutzerdefinierte Prozessschritte definiert sind, müssen Sie diese aktualisieren, um sie nach Abschluss der Nachbearbeitung auszuführen.
- Der Initiator des Übersetzungsprozesses erhält jetzt eine Benachrichtigung in seinem Posteingang, wenn der Übersetzungsauftrag erfolgreich erstellt wurde.

### Fehlerbehebungen

Die in Version 3.8 behobenen Fehler sind unten aufgeführt:

- Audioobjekte werden nicht in der HTML-Ausgabe angezeigt.
- Beim Löschen eines DITA-Themas angezeigtes Fenster „Löschen erzwingen“ zeigt mehrere Schaltflächen „Löschen erzwingen“.
- Die Übertragung von Grundlinien-Sprachkopien in -Sprachkopien funktioniert nicht für Grundlinien, die mithilfe der Server-seitigen Ansicht erstellt wurden.
- Manchmal wird Version 3.0 eines Themas als 3 nebeneinander in der Ansicht angezeigt, sodass keine Prüfungskommentare importiert werden können.
- Langsames Laden der referenzierten Inhaltsdetails auf der Registerkarte „Baselines“ für verschobene DITA-Zuordnungen.
- Die Wiederherstellung auf eine frühere Version funktioniert bei Assets, die keine Daten sind, nicht.
- Viele leere _text-Knoten werden mit der Generierung der AEM Sites-Ausgabe erstellt.
- XML-Editor - Link-Auflösung in Imagemaps nach der Seitenerstellung funktioniert nicht.
- Das Anwenden von Kennzeichnungen auf der Registerkarte „Baselines“ fügt keine Kennzeichnungen wie Bilder auf die referenzierten Inhalte an.
- SVG-Dateien werden über die Option Download Map in falschem Format heruntergeladen.
- Inhaltsfragment kann in einer Listenansicht nicht bearbeitet werden.
- Dateien in Oxygen XML Author können nicht über den Connector ausgecheckt und geöffnet werden.
- Der Text des `<alt>` Elements ist in der Authoring-Ansicht nicht sichtbar.
- Das Bild-Asset wird auch dann immer als veraltet angezeigt, wenn eine übersetzte Kopie vorhanden ist.
- Der Titel der benutzerdefinierten Zuordnungsvorlage ist falsch und die Miniaturansicht wird nicht angezeigt.
- Angewendete Markenelemente werden nicht in der Authoring-Ansicht des Web-Editors angezeigt.
- Verknüpfte Fußnoten sind im Inhalt nicht sichtbar.
- Die Farbcodierung im Web-Editor funktioniert nicht mit speziellen bedingten Attributen.
- Die Dropdown-Liste für @keyref ist nicht benutzerfreundlich und wird für Kunden mit einer großen Anzahl von @keyref als nahezu unbrauchbar erachtet.
- Der Variablentext, auf den @keyref verweist, wird nicht gerendert.
- Oxygen Connector || Schaltfläche „In Sauerstoff bearbeiten“ öffnet die Datei jetzt im Bearbeitungsmodus, auch wenn die Datei nicht ausgecheckt ist.
- Benutzerdefinierte Ausgabevorgaben werden nicht mit einer benutzerdefinierten Zuordnungsvorlage erstellt.
- Bei der Konvertierung von Microsoft Word (.docx) in DITA wird kein jcr:content-Knoten erstellt, sodass für Ordnernamen Sonderzeichen zulässig sind.
- Wenn eine MAP verschoben wurde (mit mehr als 150 Verweisen), werden die Verweise beschädigt und beim Öffnen von Themen treten Fehler auf.
- Die Auflösung eines Bildes wird falsch berechnet, wenn die Breite des Bildes geändert wird.
- Wenn ein Bild in einem `<codeblock>` hinzugefügt wird, werden unerwünschte Leerzeichen in der Ausgabe der AEM-Site gefunden.

