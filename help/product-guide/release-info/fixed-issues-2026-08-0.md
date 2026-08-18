---
title: Versionshinweise | Behobene Probleme in Adobe Experience Manager Guides Version 2026.08.0
description: Erfahren Sie mehr über die Fehlerbehebungen in der Version 2026.08.0 von Adobe Experience Manager Guides as a Cloud Service.
source-git-commit: 6872e4298df8e51a3c46845793d4dad23f92eddb
workflow-type: tm+mt
source-wordcount: '1200'
ht-degree: 1%

---

# Es wurden Probleme in der Version 2026.08.0 behoben

Dieser Artikel behandelt die Fehler, die in den verschiedenen Bereichen der Version 2026.08.0 von Adobe Experience Manager Guides as a Cloud Service behoben wurden.

Weitere Informationen zu den neuen Funktionen und Verbesserungen finden Sie [Neue Funktionen in der Version 2026.08.0](whats-new-2026-08-0.md).

Erfahren Sie mehr [Upgrade-Anweisungen für die Version 2026.08.0](upgrade-instructions-2026-08-0.md).

## Authoring

- Themen können nicht im Editor geöffnet werden, wenn sie über Themenberichte im Zuordnungs-Dashboard aufgerufen werden. (GUIDES-45277)


## Editor 2.0

- Wenn eine MathML-Gleichung als `conref` eingefügt wird, wird sie nicht korrekt dargestellt. (GUIDES-46601)
- Durch Kopieren und Einfügen von `<keywords>` innerhalb von `<topicmeta>` innerhalb eines `<keydef>` oder einer `<topicref>` werden die Keywords in unerwünschte fremde Tags eingefügt. (GUIDES-45800)
- Bei Verwendung von `Ctrl+click` auf einem fehlerhaften Link in einem Zuordnungs-Editor wird ein Anwendungsfehler Trigger. (GUIDES-45544)
- Beim Kopieren einer Tabelle aus einer Excel-Tabelle und Einfügen in den neuen Editor wird der gesamte kopierte Zelleninhalt in eine einzige Tabellenzelle eingefügt, anstatt ihn auf die entsprechenden Zellen zu verteilen. (GUIDES-47435)
- Eine benutzerdefinierte Schaltfläche **Als PDF exportieren** die über `editor_toolbar.json` konfiguriert wurde, wird gerendert und bleibt im Vorschaumodus klickbar, führt jedoch beim Klicken keine Aktion aus. (GUIDES-47402)
- MathML- und SVG-Elemente rendern nicht den vollständigen Satz von Attributen, sodass benutzerdefinierte CSS-Klassen und auf diese Elemente angewendete bedingte Attribute beschädigt werden. (GUIDES-46371)
- Das Öffnen bestimmter Themen, die Tabellen enthalten, fügt ein unerwartetes `<foreign>`-Tag mit zwei neuen Spalten hinzu, auch wenn am Thema keine Änderungen vorgenommen wurden. (GUIDES-46748)
- Das **scale**-Attribut gilt nicht für Bilder in der Autorenansicht. (GUIDES-45996)
- Durch Ziehen und Ablegen eines Elements, das eine `keyref` enthält, wird der `keyref` in einen absoluten Pfad konvertiert. (GUIDES-45701)
- Beim Einfügen eines Elements an der `tgroup` Position wird eine **#text-Warnung angezeigt** die verhindert, dass eine normale Tabelle an dieser Position eingefügt wird. (GUIDES-47446)
- Zum Wörterbuch hinzugefügte alphanumerische Begriffe werden von der AEM-Rechtschreibprüfung weiterhin gekennzeichnet, anstatt ignoriert zu werden. (GUIDES-48587)

## Asset-Management

- Die Massenverarbeitung von Assets umfasst fälschlicherweise Inhaltsfragment-Assets, was zu Fehlerprotokollen und Fehlern in den Verarbeitungsberichten führt. (GUIDES-47085)
- Im Zuordnungsbereich können untergeordnete Themen nicht geladen werden und das Erweiterungssymbol wird ausgeblendet, wenn das Zuordnungs-Kontrollkästchen aktiviert und wiederholt deaktiviert wird. (GUIDES-43546)

## Publishing

**AEM Sites**

Beim Veröffentlichen der AEM Sites-Ausgabe mit der Zuordnung zusammengesetzter Komponenten:

- Eine leere **Themenliste** wird angezeigt, wenn eine neue Grundlinie in der AEM Sites-Vorgabe mit Zuordnung zusammengesetzter Komponenten verwendet wird. (GUIDES-46480)
- Querverweis(`xref`)-Links zu nicht-DITA-Assets wie PDF-, ZIP-, DOCX- und Bilddateien werden nicht korrekt aufgelöst, was zu fehlerhaften Links auf der generierten Seite führt. (GUIDES-44108)

Beim Veröffentlichen der AEM Sites-Ausgabe mit der Zuordnung veralteter Komponenten:

- Nicht englische Dateinamen in den generierten Seitennamen werden durch Bindestriche ersetzt, sodass es schwierig ist, das Thema oder die Datei zu identifizieren, mit der sie verknüpft sind. (GUIDES-48387)

**Native PDF**

- In der nativen PDF-Ausgabe sind Themenverweise, die mit `toc="no"` Attribut gekennzeichnet sind, weiterhin im Inhaltsverzeichnis enthalten, was zu einem langen und überladenen Inhaltsverzeichnis führt. (GUIDES-37940, GUIDES-20156)

**Zuordnen von Sammlungen und Massenaktivierung**

Die folgenden Probleme wurden mit der Funktion [Neue Zuordnungssammlung](../user-guide/generate-output-use-new-map-collection-output-generation.md#use-new-map-collection-for-output-generation-beta) behoben, die in der Experience Manager Guides-Version 2020.08.0 verfügbar ist:

- Eine Zuordnungssammlung mit mehr als 100 Zuordnungseinträgen kann aufgrund eines Netzwerkfehlers nicht geladen werden. (GUIDES-34007)
- Es können nicht mehrere Zuordnungen gleichzeitig aus einem Ordner in der Zuordnungssammlungs-Benutzeroberfläche ausgewählt werden. (GUIDES-29581)
- In der Benutzeroberfläche „Zuordnungssammlungen“ können Sie keine Zuordnungssammlungen suchen oder filtern. (GUIDES-27723)
- Das Dashboard für Massenveröffentlichung/Aktivierung kann nicht geschlossen werden oder zurück zur **Tools** oder zur Homepage navigiert werden, ohne die Schaltfläche „Zurück“ des Browsers zu verwenden. (GUIDES-26797)
- Es ist nicht möglich, Kartensammlungen mit einer großen Anzahl von Karten oder Sprachen einfach zu verwalten. (GUIDES-21735)
- Die generierte Ausgabe kann nicht direkt über die Dashboard-Schnittstellen für Zuordnungssammlung oder Massenaktivierung angezeigt oder veröffentlicht werden. (GUIDES-18712)
- Es ist nicht möglich, eine einzige Sammlung zum Generieren und Aktivieren von Zuordnungen zu verwenden, da Zuordnungssammlungen und das Dashboard für die Massenaktivierung separate Sammlungssätze verwalten. (GUIDES-12730)

## Überprüfung

- In der Überprüfungs-Benutzeroberfläche zeigt die Tagging-Liste alle Benutzenden in der Überprüfungsaufgabe an, was die Auswahl des richtigen Benutzers in einem Kommentar oder einer Antwort erschwert. (GUIDES-33420)
- Beim Öffnen **nebeneinanderliegenden** im Kommentarbedienfeld wird die Arbeitskopie neben der kommentierten Version angezeigt, die Bereiche werden jedoch nicht horizontal synchronisiert gescrollt, und durch Klicken auf einen Kommentar wird der Cursor nicht zum entsprechenden Text bewegt. (GUIDES-44083)

## Datenbank

- `DatabaseConfiguratorService` gibt einen Fehler in den Protokollen aus, selbst wenn er nicht konfiguriert oder aktiviert ist. (GUIDES-43481)

## Bekannte Probleme

Adobe hat die folgenden bekannten Probleme in Version 2026.08.0 identifiziert:

## Authoring

- Das Schließen einer DITAVAL-Datei, die an einen anderen Speicherort verschoben wurde, führt zu einer `ERROR IN FETCHING VERSION DETAILS`. (GUIDES-51420)
- Die Konflikt-API schlägt fehl und führt zu einem Anwendungsfehler, wenn der Repository-Ordnerpfad mit einem Schrägstrich endet. (GUIDES-51006)

## Editor 2.0


- Wenn Sie in der Gliederungsansicht ein Verarbeitungsanweisungselement auswählen, wird das gesamte übergeordnete Tag anstelle des ausgewählten Elements hervorgehoben. (GUIDES-48318)
- Beim Bearbeiten eines Keywords innerhalb eines `keyref` in der Quellansicht wird das Keyword unterbrochen, wenn die Ansicht zu einer anderen Ansicht gewechselt wird. (GUIDES-49998)
- Eine MathML-Gleichung, die in einen `foreign`- und `equation`-Block eingeschlossen ist, führt zu unerwünschten Abständen, und die Eingabe in die Gleichung verursacht Probleme, selbst wenn die Einrückung angepasst wird. (GUIDES-46606)
- Es ist nicht möglich, einen Cursor innerhalb eines `topicref` innerhalb eines `reltable` zu platzieren, wenn die Option **Tags anzeigen** aktiviert ist und die Option **Attribute anzeigen** in den Editor-Einstellungen deaktiviert ist. (GUIDES-46565)

- Leerzeichen, die unmittelbar vor dem Löschen eines Inline-Tags in einer Tabellenzelle eingegeben `<entry>`. (GUIDES-49144)

## Publishing

- Wenn Sie **Ausgabe anzeigen** nach dem Generieren der Edge Delivery Services-Ausgabe auswählen, wird eine `hlx.live`-URL geöffnet, die anstelle der `aem.live`-URL einen 403-Fehler „Verboten“ zurückgibt. (GUIDES-51572)
- Beim Hinzufügen eines Bildes, eines Hyperlinks oder eines iFrames aus der Symbolleiste einer Vorlage werden auf der Seite `common.plt` ungültige Komponenten angezeigt. (GUIDES-51165)
- Durch das Veröffentlichen einer Zuordnung, die mit dem `copy-to`-Attribut auf ein Thema verweist, wird der Link zum Peer-Bereich aus dem entsprechenden Thema in der Quellzuordnung entfernt. (GUIDES-50701)
- Wenn eine PDF als `xref` referenziert wird, deren Umfang auf `Peer` festgelegt ist, wird sie auf der AEM-Site veröffentlicht (unter Verwendung der veralteten Komponentenzuordnung) und nicht von der Querzuordnung bezogen. (GUIDES-50213)

**Sammlungen zuordnen**

- Das Löschen einer Zuordnungssammlung schlägt manchmal fehl, wenn Sie zwischen Registerkarten wechseln (z. B. Repository oder Übersicht) und dann zur Seite „Zuordnungssammlung“ zurückkehren, bevor Sie sie löschen. (GUIDES-50997)
- Beim Generieren derselben Vorgabe während der Ausführung einer vorherigen Generierung wird keine Meldung mehr angezeigt, die angibt, dass die vorherige Generierung ausgeführt wird. (GUIDES-50523)
- Der Zeitstempel der letzten Generierung wird in der Zuordnungssammlungs-Benutzeroberfläche nicht angezeigt oder aktualisiert, nachdem eine Zuordnung generiert wurde. Wenn Sie eine zuvor entfernte Vorgabe erneut hinzufügen, geht ihr Generierungsverlauf erneut verloren. (GUIDES-50511)
- Bei der Veröffentlichung über **Generierungsverlauf** wird immer die neueste Ausgabe einer Vorgabe anstelle der ausgewählten Generation veröffentlicht. (GUIDES-50508)
- Der Veröffentlichungsstatus wird für neu erstellte Zuordnungssammlungen nicht automatisch aktualisiert. (GUIDES-50367)

## Übersetzung

- Beim Starten einer Übersetzung mit der Option **Nur Struktur erstellen** wird ein Fehler zurückgegeben. (GUIDES-51261)

## Überprüfung

- Wenn Sie mit einem Tastaturbefehl über Text, der ausgeblendete bedingte Inhalte enthält, durchstreichen, wird auch der ausgeblendete Inhalt durchgestrichen. (GUIDES-49837)


