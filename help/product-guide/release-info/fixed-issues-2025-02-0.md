---
title: Versionshinweise zu | Es wurden Probleme in Adobe Experience Manager Guides Version 2025.02.0 behoben
description: Erfahren Sie mehr über die Fehlerbehebungen in der Version 2025.02.0 von Adobe Experience Manager Guides as a Cloud Service.
source-git-commit: c45f76f1186ed12bb26a59dfcd9b9056e043d1d9
workflow-type: tm+mt
source-wordcount: '1286'
ht-degree: 1%

---

# Es wurden Probleme in der Version 2025.02.0 behoben

Dieser Artikel behandelt die in verschiedenen Bereichen der Version 2025.02.0 von Adobe Experience Manager Guides as a Cloud Service behobenen Fehler.

Weitere Informationen zu den neuen Funktionen und Verbesserungen finden Sie unter [Neue Funktionen in Version 2025.02.0](whats-new-2025-02-0.md).

Erfahren Sie mehr [Upgrade-Anweisungen für die Version 2025.02.0](upgrade-instructions-2025-02-0.md).


## Authoring

- Beim Aktualisieren von Bedingungen über das Ordnerprofil gehen alle Bedingungsgruppen verloren und die Bedingungen werden reduziert. 23526)
- Beim Ändern des Werts der Kopfzeilen für eine Tabelle im Bedienfeld **Inhaltseigenschaften** wird der aktualisierte Wert nicht angewendet. 23213)
- Für nachfolgende Handbücher zu Dokumentstatusübergängen ist eine Seitenaktualisierung erforderlich. 19421)
- Beim Hinzufügen von Themen in DITA Map mit dem **Themenverweis** Elementdialogfeld in der **Autoren** Ansicht werden die ausgewählten Themen in umgekehrter Reihenfolge der Auswahl eingefügt. (8031)
- Beim Wechseln zwischen **Autoren** und **Source**-Ansicht werden die führenden Leerzeichen in `<pre>`- oder `<codeblock>` gelöscht und die Datei wird mit dieser Löschung gespeichert. 19987)
- Der als &quot;**&quot; markierte Dokumentstatus** vor dem Speichern einer neuen Version auf **Entwurf** zurück, was dazu führt, dass der **Fertig**-Status in keiner Dokumentversion bestehen bleibt. 20006)
- Wenn Listenelemente aus dem para-Tag verschoben werden, gehen die Listenelementinhalte verloren. 22764)
- Beim Hinzufügen von Themen in DITA Map mit dem **Themenverweis** Elementdialogfeld in der **Autoren** Ansicht werden die ausgewählten Themen in umgekehrter Reihenfolge der Auswahl eingefügt. 22858)
- Beim Hinzufügen neuer Themenverweise in DITA Map mit dem **Themenverweis** Elementdialog in der **Layout** Ansicht werden die hinzugefügten Verweise als fehlerhafte Links angezeigt. 22859)
- Wenn Sie in einem Thema mit der rechten Maustaste auf das `<simpletable>`-Tag klicken **wird die Option** Umbenennen“ nicht angezeigt. 22860)
- Wenn Sie eine `xref` einfügen, die einen schlüsselbasierten Verweis mit Link-Text verwendet, wird der Link-Text in Experience Manager Guides nicht angezeigt. 18775)
- Durch Ziehen und Ablegen eines Bildes in einem Thema in **Autoren** Ansicht wird der Bildverweis beschädigt, was zu Datenverlust führt. 25769)
- Bei der Suche nach Dateien im Repository mit **Search &amp; Filter**-Funktion können nicht mehrere Dateien ausgewählt werden. 25104)
- Wenn Sie ein Bild aus einem externen Produkt (z. B. MS PowerPoint) kopieren und in Handbücher einfügen, wird die Funktion zum schnellen Hochladen des Assets für die Verwendung in der Datei unterbrochen. 24983)
- Wenn Sie eine `topicref` über eine andere ziehen (in **Autoren** oder **Layout** Ansicht), wird eine Bestätigung für den Ersatz anstelle der Verschachtelung angezeigt. Wenn Sie im Bestätigungsdialogfeld **Nein** auswählen, wird weiterhin Inhalt ersetzt, was zu Datenverlust führt. 18602)
- Sie können nicht mehrere Tastaturbefehle zu einem einzelnen Ereignis hinzufügen, noch können Sie ein Argument zu einem Ereignis hinzufügen, wenn Sie es über eine Verknüpfung auslösen. 19066)
- Beim erneuten Laden des Browsers wird die zuvor geschlossene Registerkarte Bild erneut geöffnet. 19267)
- Das teilweise Auswählen von Text in einem Absatz- oder Listenelement und das Ziehen des Textes aus dem Element verursacht Inhaltsverlust beim Wechsel zwischen **Author** und **Source** Ansichten. 25790)

## Veröffentlichung

- Das Veröffentlichen in Salesforce schlägt fehl, wenn Inhalte Leerzeichen ohne Unterbrechung enthalten. 23664)
- Bei Karten mit fehlerhaften Links schlägt die Salesforce-Veröffentlichung fehl und die Fortschrittsleiste wird unbegrenzt angezeigt. 24963)
- Bei Themen mit Fehlern wie fehlerhaften Links schlägt die Salesforce-Veröffentlichung fehl und die Fortschrittsleiste wird unbegrenzt angezeigt. 22985)
- Die native PDF-Veröffentlichung schlägt für die Konformitätsoption **PDF/X-4** fehl und gibt mit dem Fehler an, dass **PDF/X-4-Dokumente einen nicht leeren Titel erfordern**. 16904)
- Wenn Platzhaltertext verwendet wird, können Querverweise, die `<keyref>` in nativem PDF verwenden, nicht aufgelöst werden. 19365)
- Die native PDF-Generierung schlägt für Inhalte fehl **wobei das** chunk“ auf &quot;**-content“**. 21772)
- Beim Generieren einer nativen PDF-Ausgabe wird das `ditavalref` nicht unterstützt. 16320)
- Beim Bearbeiten einer großen CSS-Datei im nativen PDF-CSS-Editor tritt eine erhebliche Verzögerung auf. 16915)
- Für HTML5-basierte Veröffentlichungen wird das DITA-OT-Flag generate.copy.outer automatisch angewendet. 24299)
- Der Querverweis wird auch dann in einen relativen Link konvertiert, wenn **Umfang** des Links auf &quot;**&quot;**. 23059)
- Wenn eine ICC-Datei unter einem internen Pfad verfügbar ist, kann sie nicht in den **Drucken** für die native PDF-Voreinstellung ausgewählt werden. 14741)
- Wenn mehrere Veröffentlichungsanfragen für verschiedene Zuordnungen mit derselben Ordnerprofilvorgabe initiiert werden, schlägt die Veröffentlichung fehl. 18800)
- Bei Themen mit mehrwertigen Metadaten/Eigenschaften schlägt die Veröffentlichung fehl, wenn sie an DITA OT übergeben werden. 19001)
- Das **Eigenschaften bearbeiten** für eine Baseline zeigt nicht die zuvor gespeicherten Kriterien für eine dynamische Baseline an.  23964)
- Die Baseline enthält keine indirekten Verweise, wenn sich der Inhalt im endgültigen Dokumentstatus befindet. 19148)
- Die Einstellung **Bereinigen von Seitennamen und Dateinamen für AEM Sites und andere**) gilt für alle Ausgabeformate. (7651)
- Wenn ein externer Link eine UUID enthält, geht er in die Nachbearbeitung und konvertiert den externen Link in einen UUID-Link, wodurch der Link im Web-Editor und auch auf den Veröffentlichungsseiten unterbrochen wird. 22574)


## Verwaltung

- Ressourcenlecks treten aufgrund nicht geschlossener Fehler **ResourceResolver** in Protokollen auf. 18488)
- Titel und Symbol des Dialogfelds **Löschen erzwingen** sind in der Assets-Benutzeroberfläche falsch ausgerichtet. 21933)
- Wenn JSON-Dateien im Profilordner für die XML-Editor-Konfiguration aktualisiert werden, wird die XML-Editor-Konfiguration durch den Speichervorgang unterbrochen. 22414)
- Beim Duplizieren eines Ordnerprofils wird dessen Admin-Benutzerliste auch aus dem ursprünglichen Ordnerprofil kopiert. 19067)
- Beim Verschieben großer Ordner (mit einer großen Menge an DITA-Inhalten bis zu 200.000 Elementen) aus der Assets-Benutzeroberfläche tritt ein Fehler auf. 20107)
- Bei Verwendung des dynamischen Titels mit `<conkeyref>` wird er in der Berichtsthemenliste **Guides“ nicht ordnungsgemäß**. 20144)
- Das Bearbeiten des **Ordner**-Profils mit aktivierter Unified Shell führt zu einer leeren Benutzeroberfläche. 22212)
- Beim Löschen von Ordnern, die eine große Anzahl von Dateien enthalten, schlägt der Vorgang fehl. 17107)
- Wenn Sie den Übersetzungsauftrag abbrechen/löschen oder das Projekt löschen, zeigt das Übersetzungs-Dashboard **Status „In Bearbeitung** an. 18417)
- Wenn Sie Unified Shell für eine Cloud-Instanz aktivieren, wird die Themenvorschau nicht im Zuordnungs-Dashboard geöffnet. 18826)
- Wenn Sie zwei Versionen eines nicht übersetzten Themas gleichzeitig mit einer nicht vorhandenen Übersetzung senden und die zweite Version vor der ersten genehmigen, wird das Übersetzungsprojekt mit der ersten Version unterbrochen. 22200)


## Überprüfung

- Bei der Auswahl mehrerer Themen für eine Überprüfung in einer Karte gibt die E-Mail-Benachrichtigung, die der Reviewer erhält, an, dass alle Themen in der Karte zur Überprüfung verfügbar sind und nicht nur die ausgewählten. 23214)
- Der Thementitel und das Symbol sind in der Benutzeroberfläche zur Revisionserstellung nicht korrekt ausgerichtet. 11670)


## APIs

- Beim Erstellen eines **Baseline** mithilfe der Guides-API durch Auslösen **BaslinUtlis**-Service tritt ein Fehler auf. 19385)

## Bekannte Probleme

Adobe hat die folgenden bekannten Probleme in Version 2025.02.0 identifiziert:

- Bei Verwendung von Bildern als Variablen in der PDF-Vorlage wird es in der Ausgabe nicht aufgelöst.
- Die Funktion **Im Repository suchen** funktioniert beim erstmaligen Öffnen des Handbücher-Editors nicht, funktioniert aber nach der Aktualisierung des Browsers wie erwartet.
- In **Themenliste** schlägt die Sortierung nach Titel bei Assets mit `<conref>` oder `<conkeyref>` im Titel fehl, sodass diese Einträge immer oben angezeigt werden.
- Das Wechseln des Ordnerprofils spiegelt Änderungen nicht sofort in der Benutzeroberfläche wider, ohne dass der Browser aktualisiert wird.
- Die Anpassungen des Erweiterungs-Frameworks, die vor Guides 2025.02.x.x vorgenommen wurden, funktionieren möglicherweise nicht wie beabsichtigt.
- Das vollständige Inhaltsverzeichnis der Karte wird nicht aktualisiert, wenn Themen aus der Karte selektiv veröffentlicht werden.
- Das Veröffentlichen einer Zuordnung, die eine Markdown-Datei mit internen Bildverweisen enthält, schlägt auf Windows-Servern fehl.
- Die Aufzählungsliste kann in Markdown nicht in eine nummerierte Liste konvertiert werden.
- Das Veröffentlichen auf einer nativen AEM-Site schlägt fehl, wenn Markdown-Dateien in einer Zuordnung referenziert werden.
- Die Position der Hintergrundfarbe ist in der Benutzeroberfläche des Bedienfelds **Bedingung“ falsch**.
- Wenn Sie ein Bild als `<keyref>` verwenden, wird **„Referenztyp** des Bildes nicht im **Multimedia-Bericht“**.
- In einigen Fällen funktioniert die Sperrfunktion für CSS-Dateien nicht wie erwartet, sodass andere Benutzer die Dateien bearbeiten und speichern können, selbst wenn sie von einem anderen Benutzer gesperrt werden.



