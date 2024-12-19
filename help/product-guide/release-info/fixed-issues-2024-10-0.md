---
title: Versionshinweise zu | Es wurden Probleme in Adobe Experience Manager Guides Version 2024.10.0 behoben
description: Erfahren Sie mehr über die Fehlerbehebungen in der Version 2024.10.0 von Adobe Experience Manager Guides as a Cloud Service.
exl-id: d23552a1-8f15-4a05-9317-f383dea3253d
source-git-commit: 682eaf6f4a3a158f49a8f2ea91ce9cd2de3ff772
workflow-type: tm+mt
source-wordcount: '1166'
ht-degree: 2%

---

# Es wurden Probleme in der Version 2024.10.0 behoben

Dieser Artikel behandelt die in verschiedenen Bereichen der Version 2024.10.0 von Adobe Experience Manager Guides as a Cloud Service behobenen Fehler.

Weitere Informationen zu den neuen Funktionen und Verbesserungen finden Sie unter [Neue Funktionen in Version 2024.10.0](whats-new-2024-10-0.md).

Erfahren Sie mehr [Upgrade-Anweisungen für die Version 2024.10.0](upgrade-instructions-2024-10-0.md).


## Authoring

- Die Option **Suchen** funktioniert in der Ansicht **Source** nicht. 18610)
- Das `<title>` wird automatisch hinzugefügt, wenn das `<fig>` als Ausschnitt eingefügt wird. 18562)
- Die Themenwiederherstellung schlägt aufgrund des vorkonfigurierten Regenerierungsthemas oder eines inkrementellen Fehlers bei der Veröffentlichungs-API fehl. 18452)
- Die Experience Manager Guides-Instanz wird instabil und die Fehlerprotokolle vergrößern sich nach dem Zugriff auf die Assets-Benutzeroberfläche auf bis zu 30-40 GB. 18414)
- **Auschecken** und **Einchecken** werden zusammen angezeigt, wenn `autocheckout` im xmeditor konfiguriert ist. 18088)
- Das Kopieren und Einfügen von Bildern aus der Autorenansicht funktioniert in Adobe Experience Manager Guides as a Cloud Service-Version 2024.06.0 nicht.18062)
- `<conref>` für ein Thema, auf das in einer DITA-Karte verwiesen wird, wird nicht in der Vorschau im Editor angezeigt. 17794)
- Große DITA-Karten werden langsam geladen und brauchen beim Wechsel zur **Layout**-Ansicht etwas Zeit. 17590)
- Die DITA-Version zeigt den Benutzernamen in der Assets-Benutzeroberfläche falsch an. 17580)
- Fehler für doppelte Bild-IDs in den Themen hindern den Benutzer daran, ein Thema zu speichern oder zu erstellen. 17528)
- Beim Hochladen einer großen Anzahl von Dateien mit großen Datensätzen in Experience Manager Guides treten Probleme auf.17008)
- Zeitweise treten Fehler bei der PDF-Rendering-Funktion in Experience Manager Guides as a Cloud Service auf. 16966)
- Beim Erstellen einer DITA-Zuordnung basierend auf einer Vorlage verursacht der vorkonfigurierte DXML-Workflow Prozessunterbrechungen und führt zu 503 nicht bearbeitbaren Fehlern. 16529)
- **Sonderzeichen** die mit Escape-Zeichen geschrieben wurden, werden aus dem Thema entfernt, nachdem sie in Experience Manager Guides hochgeladen wurden. 16495)
- Datei, die durch die Fehlermeldung „ausgecheckt“ wurde, wird falsch angezeigt, wenn Bearbeitungsdateien von einer anderen Registerkarte verschoben werden, wenn Token abgelaufen sind oder wenn der Benutzer abgemeldet wird. 15223)
- Große Dateien werden nicht in den Web-Editor geladen und bewirken, dass der Browser einfriert. 13227)
- `<Topicref>`, die mit `<keyref>` hinzugefügt wurden, werden in nativen PDF nicht angezeigt. 11974)
- Der Komponentenpfad `/libs/fmdita/components/versions` ist hartcodiert, und die Benutzer können ihn nicht überlagern. (8 779)
- Beim Öffnen eines DITA-Themas oder einer DITA-Zuordnung auf einer neuen Registerkarte zum Bearbeiten wird die Auswahlnavigation in der Assets-Benutzeroberfläche eingefroren. (4992)
- Beim Herunterladen einer DITA-Zuordnung mit großen Videodateien tritt in den Protokollen ein Speicherfehler auf, und Trigger schlagen in der Benutzeroberfläche fehl. 18884)
- Beim Einfügen einer MathML-Gleichung mit dem Symbol &quot;&lt;&quot; wird **Fehler „Ungültiges**&quot; erzeugt. 18742)
- Eine falsche UUID-Generierung während der Inhaltsaufnahme führt zu fehlerhaften Submap-Referenzen in der aufgenommenen Zuordnung. 18308)
- In einigen Fällen treten bei der Erstellung eines neuen DITA-Themas im Web-Editor Verzögerungen auf. 16836)
- Die Suche nach Dateien im **Repository** innerhalb des Web-Editors dauert zu lange und schlägt manchmal fehl beim Laden der Ergebnisse. 16837)

## Veröffentlichung

- Der Querverweis auf den -Schlüssel wird in der nativen PDF-Ausgabe nicht aufgelöst. 18087)
- Der Fehler **duplicate_value** tritt gelegentlich auf, wenn ein vorhandener Artikel in Salesforce erneut veröffentlicht wird. 17932)
- Stil und Inhaltsformatierung in Kundenvorlagen ändern sich automatisch, wenn das Layout Metadatenfelder enthält, was zu einer falschen Formatierung in veröffentlichten PDF führt. 17900)
- Die Validierung der Salesforce-Verbindung schlägt mit der Lightning-URL fehl. 17797)
- Die referenzierte PDF wird während der Massenaktivierung **veröffentlichten Inhalte nicht über** Publish-Dashboard aktiviert. 17793)
- Die Massenaktivierung von veröffentlichten Inhalten funktioniert nicht für lokalisierte Karten. 17638)
- Bei Auswahl der Option **Im Topicmeta hinzugefügte Metadaten verwenden** werden die Metadateneigenschaften nicht in den Dokumenteigenschaften der nativen PDF-Ausgabe übertragen. 17283)
- Die Bedingungsfilterung in der nativen PDF-Ausgabe funktioniert im Vergleich zu DITA-OT nicht wie erwartet. 17095)
- Das Inhaltsverzeichnis berücksichtigt keine `<sub>` oder `<sup>` Tags in der nativen PDF-Ausgabe. 17028)
- Die AEM-Site-Generierung und die inkrementelle Veröffentlichungs-API funktionieren nicht wie erwartet. 16666)
- Die native PDF-Generierung schlägt mit einem Fehler im Zusammenhang mit dem Abrufen der Abhängigkeiten für Node.js fehl. 14445)
- `<Conref>` wird im `Preview` des Web-Editors und der nativen PDF-Ausgabe nicht aufgelöst. 17827)
- Inhaltsreferenzen werden für die native PDF-Ausgabe nicht korrekt aufgelöst, wenn sich die Datei mit den Schlüsseldefinitionen nicht im selben Ordner wie die DITA-Zuordnung befindet. 15062)
- Wenn eine DITA-Zuordnung Überschriftenebenen bis zu 7 oder höher enthält, wird die Überschrift der Ebene 7 in der nativen PDF-Ausgabe fälschlicherweise als Überschrift der Ebene 1 behandelt. 19698)
- Wenn ein Inhaltselement (Text) in ein Element eingeschlossen wird, werden die Leerzeichen vor und nach dem Text in den Vorschau- oder Ausgabeformaten nicht angezeigt. 19308)
- Manuell ausgelöste Nachgenerierungs-Workflows schlagen aufgrund einer NULL POINTER EXCEPTION im Workflow fehl, was dazu führt, dass der Inhalt 11-mal hochgeladen wird. 18880)
- **Publish-Dashboard** wird für Karten, die sich noch im Übersetzungsprozess befinden, leer angezeigt. 19352)


## Verwaltung

- Der Pfad für die Überlagerungsfunktion ist für die koreanische Sprachdatei hartcodiert und nicht korrekt ausgewählt. 17089)
- Änderungen/Anpassungen, die im Dialogfeld **Version speichern** vorgenommen wurden, werden bei der Verwendung des Handbücher-Erweiterungs-Frameworks nicht berücksichtigt. 17828)
- Die Konvertierung von InDesign in DITA weist einen hartcodierten Konfigurationspfad auf, sodass die benutzerdefinierten Konfigurationsdateien nicht ausgewählt werden. 16891)
- Vollständige Verweise/Assets werden nicht heruntergeladen, wenn eine DITA-Zuordnung mit großen Abhängigkeiten/Verweisen über die Baseline heruntergeladen wird. 19099)


### Überprüfung

- Das Abrufen der Benutzerliste beim Erstellen einer Prüfungsaufgabe schlägt fehl, wenn die Benutzeranzahl 25 überschreitet. 17329)
- Wenn ein Aufgabenthema `<cmd>` Tag in einem oder mehreren Schritten enthält, zeigt das Überprüfungsfenster das Attribut `importance` als Präfix in allen Schritten an, die das Tag enthalten. 19699)

## Übersetzung

- Die Verweise von übersetzten Assets werden nicht aktualisiert. 18086)
- Verweise werden bei der Übersetzung in mehrere Sprachen nicht korrekt als direkt oder indirekt gefiltert. 17891)
- XLIFF-Projekte mit menschlicher Übersetzung können nicht erstellt werden. 16964)
- Das Hinzufügen eines aktualisierten Themas zu einem aktiven Übersetzungsprojekt führt zu einem doppelten Thema und der Prozess schlägt fehl. (7688)
- Den Übersetzungsprojekten, die durch Auswahl der Option **Nur Struktur erstellen** erstellt wurden, werden keine UUIDs zugewiesen. 18980)
- Wenn Sie ein Übersetzungsprojekt mit dem **Übersetzungsstatus** als **In Bearbeitung** auswählen, wird eine falsche Seite geöffnet. 13248)
- Der Titel mit `<conref>` wird in den Baseline- und Übersetzungs-Dashboards des Web-Editors nicht aufgelöst. 16961)

## Bekannte Probleme

- Das Öffnen einer AEM Sites-Vorgabe (nicht veraltet) kennzeichnet das Thema als beschädigt.
- Das ausgewählte Bedienfeld wird bei der Browser-Aktualisierung auf der Registerkarte „Ausgabe“ nicht beibehalten.
- Thema kann nicht zwischen zwei TopicRefs in der Ansicht **Autor** gezogen werden.
- Die in der Voreinstellung angewendete Bedingungsfilterung wird nicht über (**als PDF herunterladen)**.
- Bei der Erstellung eines einzelnen Themas im Zuordnungsbereich werden alle Themen generiert, die in der AEM Sites-Voreinstellung ausgewählt wurden (nicht veraltet).
- Der Verweis des Themas erscheint in der Benutzeroberfläche fehlerhaft, wenn er in der oberen Symbolleiste der DITA-Zuordnung eingefügt wird.
- Die native PDF-Generierung schlägt für eine DITA-Zuordnung fehl, wenn Referenzen fehlen.
- Die Veröffentlichung eines einzelnen Themas einer AEM-Site mit Bedingungen schlägt in einer Umgebung mit aktivierten Microservices fehl.
- Sobald der Dokumentstatus eines Themas auf „Fertig **aktualisiert wurde** ist das Symbol **Neue Version starten** nur im **Vorschau** des Themas verfügbar.
