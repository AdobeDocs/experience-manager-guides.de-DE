---
title: Versionshinweise | Behobene Probleme in Adobe Experience Manager Guides, Version 2024.10.0
description: Erfahren Sie mehr über die Fehlerkorrekturen in der Version 2024.10.0 von Adobe Experience Manager Guides as a Cloud Service.
source-git-commit: 64c5318a064d28a42f3f11d2fe5b7d8548e341d8
workflow-type: tm+mt
source-wordcount: '1166'
ht-degree: 2%

---

# Behobene Probleme in Version 2024.10.0

Dieser Artikel behandelt die Fehler, die in verschiedenen Bereichen der Version 2024.10.0 von Adobe Experience Manager Guides as a Cloud Service behoben wurden.

Weitere Informationen zu den neuen Funktionen und Verbesserungen finden Sie unter [Neue Funktionen in Version 2024.10.0](whats-new-2024-10-0.md).

Erfahren Sie mehr über die [Upgrade-Anweisungen für die Version 2024.10.0](upgrade-instructions-2024-10-0.md).


## Authoring

- Die Option **Suchen** funktioniert in der Ansicht **Source** nicht. (18610)
- Das Element `<title>` wird automatisch hinzugefügt, wenn das Element `<fig>` als Ausschnitt eingefügt wird. (18562)
- Die Themenneuerstellung schlägt aufgrund des Fehlers der OOTB-Regenerate Topic oder der inkrementellen Publish-API fehl. (18452)
- Die Experience Manager Guides-Instanz ist instabil und die Fehlerprotokolle werden nach dem Zugriff auf die Assets-Benutzeroberfläche auf bis zu 30 bis 40 GB größer. (18414)
- Die Symbole **Auschecken** und **Einchecken** werden zusammen angezeigt, wenn `autocheckout` in xmleditor konfiguriert ist. (18088)
- Das Kopieren und Einfügen von Bildern aus der Autorenansicht funktioniert in Version 2024.06.0 von Adobe Experience Manager Guides as a Cloud Service nicht.(18062)
- `<conref>` für ein Thema, auf das in einer DITA-Zuordnung verwiesen wird, wird nicht in der Vorschau im Editor angezeigt. (17794)
- Große DITA-Maps werden langsam geladen und benötigen Zeit, um zur Ansicht **Layout** zu wechseln. (17590)
- In der DITA-Version wird der Benutzername fälschlicherweise in der Assets-Benutzeroberfläche angezeigt. (17580)
- Fehler bei doppelten Bild-IDs in den Themen beschränken das Speichern oder Bearbeiten eines Themas durch den Benutzer. (17528)
- Beim Hochladen einer großen Anzahl von Dateien mit dichten Datensätzen in Experience Manager Guides treten Probleme auf.(17008)
- Bei der PDF-Rendering-Funktion in Experience Manager Guides as a Cloud Service treten gelegentlich Fehler auf. (16966)
- Beim Erstellen einer DITA-Zuordnung basierend auf einer Vorlage verursacht der OOTB-DXML-Workflow Prozessunterbrechungen und führt zu 503 nicht zustellbaren Fehlern. (16529)
- **Sonderzeichen**, die mit Escape-Zeichen geschrieben wurden, werden nach dem Hochladen in Experience Manager Guides aus dem Thema entfernt. (16495)
- Die Fehlermeldung &quot;Datei ausgecheckt durch&quot; wird falsch angezeigt, wenn Dateien von einer anderen Registerkarte verschoben, Token abgelaufen oder der Benutzer abgemeldet wird. (15223)
- Große Dateien werden nicht im Web Editor geladen und frieren den Browser ein. (13227)
- `<Topicref>`, der mit `<keyref>` hinzugefügt wurde, wird nicht in nativer PDF angezeigt. (1974)
- Der Komponentenpfad `/libs/fmdita/components/versions` ist fest codiert und die Benutzer können ihn nicht überlagern. (8779)
- Durch Öffnen eines DITA-Themas oder -Map in einer neuen Registerkarte zur Bearbeitung wird die Auswahlnavigation in der Assets-Benutzeroberfläche eingefroren. (4992)
- Beim Herunterladen einer DITA-Zuordnung mit großen Videodateien tritt in den Protokollen ein Speicherfehler auf und die Benutzeroberfläche schlägt fehl. Trigger ist nicht speicherfähig. (18884)
- Beim Einfügen einer MathML-Gleichung mit dem Symbol &quot;&lt;&quot;wird ein Fehler vom Typ **Ungültiges Zeichen** erzeugt. (18742)
- Eine fehlerhafte UUID-Generierung während der Inhaltsaufnahme führt zu fehlerhaften Unterzuordnungsverweisen in der aufgenommenen Zuordnung. (18308)
- In einigen Fällen treten Verzögerungen bei der Verarbeitung eines neuen DITA-Themas auf, wenn es über den Web-Editor erstellt wird. (16836)
- Das Durchsuchen von Dateien im **Repository** im Web Editor dauert zu lange und kann manchmal nicht geladen werden. (16837)

## Veröffentlichung

- Querverweise auf den Schlüssel werden in der nativen PDF-Ausgabe nicht aufgelöst. (18087)
- Der Fehler **duplicate_value** tritt gelegentlich auf, wenn ein vorhandener Artikel in Salesforce erneut veröffentlicht wird. (17932)
- Die Formatierung und Inhaltsformatierung in Kundenvorlagen ändern sich automatisch, wenn das Layout Metadatenfelder enthält, was zu einer fehlerhaften Formatierung in veröffentlichten PDF führt. (17900)
- Die Salesforce-Verbindungsprüfung schlägt mit der Blitzer-URL fehl. (17797)
- Die referenzierte PDF wird während der Massenaktivierung veröffentlichter Inhalte nicht im **Bulk Publish Dashboard** aktiviert. (17793)
- Die Massenaktivierung von veröffentlichten Inhalten funktioniert nicht für lokalisierte Maps. (17638)
- Bei Auswahl der Option **In der topicmeta** hinzugefügte Metadaten verwenden werden die Metadateneigenschaften nicht in den Dokumenteigenschaften der nativen PDF-Ausgabe weitergeleitet. (17283)
- Die Bedingungsfilterung in der nativen PDF-Ausgabe funktioniert nicht erwartungsgemäß im Vergleich zu DITA-OT. (17095)
- Das Inhaltsverzeichnis berücksichtigt in der Ausgabe des nativen PDF keine `<sub>` - oder `<sup>` -Tags. (17028)
- AEM Site-Generierung und inkrementelle Publish-API funktionieren nicht erwartungsgemäß. (16666)
- Die native PDF-Generierung schlägt mit einem Fehler bezüglich der Abrufen von Abhängigkeiten für Node.js fehl. (14445)
- `<Conref>` wird im `Preview` -Modus des Web Editors und der nativen PDF-Ausgabe nicht aufgelöst. (17827)
- Inhaltsreferenzen werden für die Ausgabe nativer PDF nicht korrekt aufgelöst, wenn sich die Datei mit Schlüsseldefinitionen nicht im selben Ordner wie die DITA-Zuordnung befindet. (15062)
- Wenn eine DITA-Zuordnung Überschriftenebenen bis zu 7 oder höher enthält, wird die Überschrift der Stufe 7 in der nativen PDF-Ausgabe fälschlicherweise als Überschrift der Ebene 1 behandelt. (19698)
- Wenn ein Inhaltselement (Text) in ein Element eingeschlossen ist, werden die Leerzeichen vor und nach dem Text nicht im Vorschau- oder Ausgabeformat angezeigt. (19308)
- Workflows, die nach der Erstellung manuell ausgelöst wurden, schlagen aufgrund einer NULL-POINTER-AUSNAHME im Workflow fehl, was dazu führt, dass der Inhalt elf Mal hochgeladen wird. (18880)
- **Massen-Publish-Dashboard** zeigt leere Maps an, die sich noch im Übersetzungsprozess befinden. (19352)


## Verwaltung

- Der Pfad für die Überlagerungsfunktion ist für die koreanische Sprachdatei hartcodiert und nicht korrekt ausgewählt. (17089)
- Änderungen/Anpassungen, die am Dialogfeld **Version speichern** vorgenommen wurden, werden bei Verwendung des Guides Extension Framework nicht berücksichtigt. (17828)
- InDesign zu DITA-Konvertierungen haben einen fest programmierten Konfigurationspfad, sodass die benutzerdefinierten Konfigurationsdateien nicht ausgewählt werden. (16891)
- Vollständige Verweise/Assets werden nicht heruntergeladen, wenn eine DITA-Zuordnung mit großen Abhängigkeiten/Verweisen über die Grundlinie heruntergeladen wird. (1909)


### Überprüfung

- Das Abrufen der Benutzerliste beim Erstellen einer Prüfungsaufgabe schlägt fehl, wenn die Benutzeranzahl 25 überschreitet. (17329)
- Wenn ein Aufgabenthema in einem oder mehreren Schritten das Tag `<cmd>` enthält, zeigt das Überprüfungsbedienfeld das Attribut `importance` als Präfix in allen Schritten an, die das Tag enthalten. (1969)

## Übersetzung

- Die Referenzen übersetzter Assets werden nicht aktualisiert. (18086)
- Verweise werden beim Übersetzen in mehrere Sprachen nicht korrekt als Direkt oder Indirect gefiltert. (17891)
- Es können keine XLIFF-Projekte mit menschlicher Übersetzung erstellt werden. (16964)
- Das Hinzufügen eines aktualisierten Themas in einem aktiven Übersetzungsprojekt führt zu einem doppelten Thema und der Prozess schlägt fehl. (7688)
- Den Übersetzungsprojekten, die durch Auswahl der Option **Nur Struktur erstellen** erstellt wurden, werden keine UUIDs zugewiesen. (18980)
- Wenn Sie ein Übersetzungsprojekt mit dem **Übersetzungsstatus** als **Gestartet** auswählen, wird eine falsche Seite geöffnet. (13248)
- Der Titel mit &quot;`<conref>`&quot; wird in den Dashboards &quot;Grundlinie&quot;und &quot;Übersetzung&quot;des Web Editors nicht aufgelöst. (16961)

## Bekannte Probleme

- Wenn Sie eine AEM Sites-Vorgabe öffnen (nicht veraltet), wird das Thema als verschmutzt markiert.
- Das ausgewählte Bedienfeld wird beim Aktualisieren des Browsers auf der Registerkarte &quot;Ausgabe&quot;nicht beibehalten.
- Thema kann nicht zwischen zwei Topicrefs in der Ansicht **Autor** gezogen und abgelegt werden.
- Die in der Vorgabe angewendete Bedingungsfilterung wird nicht über **Als PDF herunterladen** angewendet.
- Die Erstellung eines einzelnen Themas aus dem Zuordnungsbereich generiert alle in der AEM Sites-Vorgabe ausgewählten Themen (nicht veraltet).
- Die Referenz zum Thema scheint in der Benutzeroberfläche fehlerhaft zu sein, wenn sie von der oberen Symbolleiste der DITA-Map eingefügt wird.
- Die native PDF-Generierung schlägt für eine DITA-Zuordnung fehl, wenn sie fehlende Verweise aufweist.
- Die Veröffentlichung von AEM Site mit Bedingungen für einzelne Themen schlägt in der Umgebung mit aktivierten Microservices fehl.
- Sobald der Dokumentstatus eines Themas auf **Fertig** aktualisiert wurde, ist das Symbol **Neue Version starten** nur im Modus **Vorschau** des Themas verfügbar.
