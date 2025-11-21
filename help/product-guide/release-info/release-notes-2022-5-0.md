---
title: Versionshinweise zu | Adobe Experience Manager Guides as a Cloud Service, Version Mai 2022
description: Mai-Version von Adobe Experience Manager Guides as a Cloud Service
exl-id: 7928a300-5ec9-492c-b9be-02b6f87638c6
feature: Release Notes
role: Leader
source-git-commit: 6e23f52fc9124d0f07f8108da1b5fe574f553469
workflow-type: tm+mt
source-wordcount: '1887'
ht-degree: 0%

---

# Mai-Version von Adobe Experience Manager Guides as a Cloud Service

## Upgrade auf die Version vom Mai

Führen Sie ein Upgrade Ihres aktuellen Adobe Experience Manager Guides as a Cloud Service-Setups (später als *AEM Guides as a Cloud Service* bezeichnet) durch, indem Sie die folgenden Schritte ausführen:
1. Checken Sie den Git-Code der Cloud Services aus und wechseln Sie zu der Verzweigung, die in der Cloud Services-Pipeline konfiguriert ist und der Umgebung entspricht, die Sie aktualisieren möchten.
1. Aktualisieren Sie `<dox.version>` Eigenschaft in `/dox/dox.installer/pom.xml` Datei Ihres Cloud Services-Git-Codes auf 2022.5.144.
1. Übernehmen Sie die Änderungen und führen Sie die Cloud Services-Pipeline aus, um auf die Version vom Mai von AEM Guides as a Cloud Service zu aktualisieren.

## Kompatibilitätsmatrix

In diesem Abschnitt finden Sie die Kompatibilitätsmatrix für die Softwareanwendungen, die von AEM Guides as a Cloud Service Version Mai 2022 unterstützt werden.

### FrameMaker und FrameMaker Publishing Server

| FMPS | FrameMaker |
| --- | --- |
| Nicht kompatibel | Aktualisierung 2020 4 und höher |
| | |

*Die in AEM erstellten Grundlinien und Bedingungen werden ab 2020.2 in FMPS-Versionen unterstützt.

### Sauerstoffanschluss

| AEM Guides as a Cloud Service-Version | Fenster des Sauerstoffanschlusses | Oxygen Connector Mac |
| --- | --- | --- |
| 2022.5.0 | 2,6,9 | 2,6,9 |
|  |  |  |


## Neue Funktionen und Verbesserungen

AEM Guides as a Cloud Service bietet in der Mai-Version viele Verbesserungen und neue Funktionen:

### Erweiterter Web-Editor

* **Erstellen Sie Karten basierend auf benutzerdefinierten Vorlagen**

Jetzt erhalten Sie die leistungsstarke Funktion zum Erstellen benutzerdefinierter Zuordnungsvorlagen. Sie können sie verwenden, um DITA-Karten zusammen mit den Themenvorlagen und Zuordnungsvorlagen zu erstellen, auf die in der Zuordnungsvorlage verwiesen wird.

![DITA-Vorlagen](assets/dita-templates.png)

Sie können auch auf andere Zuordnungsvorlagen und Themenvorlagen aus der benutzerdefinierten Zuordnungsvorlage verweisen. Die referenzierten Zuordnungsvorlagen können auf verschiedene Zuordnungsvorlagen, Themenvorlagen, Themen, Karten, Bilder, Videos und andere Assets verweisen.

![Erstellen von DITA-Vorlagen](assets/create-dita-template.png)

Die benutzerdefinierte Zuordnungsvorlage kann Ihnen dabei helfen, die Zuordnungsvorlagen und die gesamte referenzierte Ordnerstruktur sehr einfach zu replizieren. Diese benutzerdefinierten Vorlagen sind besonders nützlich, um mehrere Karten zu erstellen und neu zu erstellen, die rekursive Strukturen und Verweise haben.

* Die Funktion **Keyword einfügen** wurde verbessert. Sie können jetzt ein einzufügendes Keyword leichter finden, da die Keywords in alphabetischer Reihenfolge aufgeführt werden. Sie können auch nach Keywords suchen, indem Sie eine Suchzeichenfolge in das Suchfeld eingeben.

![Keyword einfügen](assets/insert-keyword.png)

* Im Repository werden die Dateien jetzt in Stapeln geladen. Es werden 75 Dateien gleichzeitig geladen. Dieses Laden im Batch ist effizient, und Sie können schneller auf die Dateien zugreifen als alle Dateien, die in einem Ordner vorhanden sind.

![Weitere Dateien laden](assets/load-more-files.png)

* Sie können SVG-Bilder rendern, die eingebettete Daten oder Links in allen Bildschirmen des XML-Editors enthalten, einschließlich, aber nicht beschränkt auf die Vorschau- und Autorenansicht.

* Die standardmäßige XSD/DTD kann auf die neueste Version aktualisiert werden

### Verbesserter Übersetzungsprozess

* **Möglichkeit zum Erstellen eines Übersetzungsprojekts mit Zielgruppenbestimmung**
Wenn Sie nur den Umfang für ein zu übersetzendes Projekt erstellen müssen, können Sie **Erstellen eines neuen Übersetzungsprojekts für die Berechnung des Umfangs** auswählen. Dadurch werden die Kopien nicht zur Übersetzung gesendet und der ursprüngliche Übersetzungsstatus der Dateien wird beibehalten.

![Scoping-Übersetzungsprojekt](assets/scoping-translation-project.png)

* Wenn Sie die Übersetzung für ein oder mehrere Themen in einem Übersetzungsauftrag ablehnen, wird der Status der laufenden Übersetzung aller abgelehnten Themen auf ihren ursprünglichen Status zurückgesetzt.

* Die **Languages** zeigt die Sprachordner zusammen mit ihren Sprachcodes an. Zum Beispiel Französisch (fr) und Deutsch (de).

* Die Übersetzungsfunktion unterstützt jetzt auch den Sprach-Code, der sowohl das Land als auch die Sprache umfasst. Zum Beispiel, `fr-fr`, `en-us`.

![Übersetzungssprache](assets/translation-languages.png)

* Beim Laden einer DITA-Zuordnung, die sich außerhalb des Sprachordners befindet, wird keine Ausnahme am Backend protokolliert.

Weitere Informationen zur Übersetzung finden Sie im Abschnitt *Übersetzen von Dokumenten aus dem Web-Editor* in Verwenden von Adobe Experience Manager Guides as a Cloud Service.


### Erweiterte Veröffentlichung

* Sie können auch über die Registerkarte Ausgaben auf **Dashboard veröffentlichen** zugreifen, während Sie über das Zuordnungs-Dashboard eine Ausgabe generieren. Eine Liste aller aktiven Veröffentlichungsaufgaben ist im Veröffentlichungs-Dashboard verfügbar.

![Ausgaben in der Warteschlange](assets/queued-output.png)

* Im Zuordnungs-Dashboard können Sie mehrere DITAVAL-Dateien auswählen, um bedingte Inhalte zu generieren. Sie können die Dateireihenfolge durch Hinzufügen oder Löschen von Dateien beibehalten. Sie können auch den Mauszeiger über den Dateinamen bewegen, um den Pfad im AEM-Repository anzuzeigen, in dem die Datei gespeichert ist.

* **Veraltete Funktion**
AEM as a Cloud Service unterstützt die Generierung des DITA-Ausgabeformats für FrameMaker-Dokumente nicht mehr. Diese DITA-Option wurde auch aus den Ausgabevorgaben des Zuordnungs -Dashboards entfernt.

### Verbesserte artikelbasierte Veröffentlichung

Der XML-Editor bietet die Möglichkeit, während der Veröffentlichung in einem Salesforce-Profil mehr als eine Produktkategorie einem Artikel zuzuordnen.

### Weitere Funktionsverbesserungen

* Der Vorschaumodus unterstützt auch `deliveryTarget` bedingtes Verarbeitungsattribut in DITA. Sie ist als Option im Dropdown-Filter zusammen mit **Zielgruppe**, **Plattform**, **Produkt**, Props **andere Props** verfügbar.
* Die Option wurde bereitgestellt, um die Synchronisierung zwischen dem AEM-Server in Oxygen und dem lokalen System zu erzwingen.

## Behobene Probleme

Die in verschiedenen Bereichen behobenen Fehler sind unten aufgeführt:

* Im Überprüfungsfeld des Web-Editors kann der Benutzer nicht auf die Überprüfungskommentare antworten. (9667)
* Die Anwendung wird leer, wenn Sie auf einen leeren Ordner klicken, nachdem Sie ihn über das Menü „Optionen“ aktualisiert haben. (9 639)
* Eine neue Version wird erstellt, wenn wir **eingecheckte Datei speichern** schließen. (9 638)
* Die Schaltfläche „Schließen“ wird nicht angezeigt, wenn **Kontrollkästchen „Als neue Version**&quot; aktiviert ist. (9 637)
* Der richtige PDF wird nicht veröffentlicht, wenn er zuerst über einen separaten PDF für jedes Kapitel und dann über eine einzelne PDF-Datei veröffentlicht wird (separate PDF-Dateien erstellen ist nicht aktiviert). (9632)
* Das Zuordnungs-Dashboard verursacht ein Problem mit Metadaten für Benutzende ohne Administratorrechte. (9620)
* Sobald eine Baseline erstellt wurde, wird der Status in der Benutzeroberfläche auf Fehlgeschlagen gesetzt (der Abrufen-Statusaufruf schlägt fehl), wenn der Server mehr als 10000 Dateien hat. (9608)
* Das Speichern großer Datenmengen in -Eigenschaften führt zu einem Veröffentlichungsfehler, da der aufgeteilte Veröffentlichungs-Workflow fehlschlägt. (9586)
* Der Status der bedingten Attribute wird beim Wechsel zwischen Vorschau und Source und dem erneuten Vorschaumodus nicht beibehalten. (9553)
* Der Name der Lesezuordnung ist in der Repository-Ansicht leer, falls über das `mainbooktitle`-Tag kein Name angegeben wird. (9538)
* HTTP 400-Fehler beim Öffnen einer mit Oxygen hochgeladenen Datei. (9535)
* Die Vorgaben einer zuvor geöffneten Zuordnung bleiben beim Öffnen einer Zuordnung ohne definierte Vorgaben auf der Registerkarte Ausgabe sichtbar. (9523)
* Die Suchfunktion für Tags und Attribute funktioniert im Gliederungsfenster nicht. (9506)
* Neu erstellte Sammlung ist erst sichtbar, wenn der Browser aktualisiert wurde. (9505)
* Beschriftungen für bedingte Attribute (nicht die Werte) werden im Quellmodus beim Hinzufügen aller Bedingungen über die Option „Alle Eigenschaften hinzufügen“ angezeigt. (9501)
* Dateien werden bei der Wiederherstellung auf eine beliebige Version automatisch ausgecheckt. (9482)
* In der Assets-Benutzeroberfläche werden beim Zurücksetzen einer Dateiversion falsche Zeitstempelunterschiede angezeigt. (9480)
* Beim Einfügen von Elementen in das topicref-Element der DITA-Zuordnung werden mehrere Elemente aus den Suchergebnissen hinzugefügt. (9474)
* Wenn die Einstellung **Neue Version für hochgeladene Datei erstellen** aktiviert ist, wird beim Zurücksetzen und Speichern auf einem eingefrorenen Knoten eine neue Version erstellt. (9473)
* Der Anzeigetext der Schlüsselreferenz und der Inhaltsschlüsselreferenz wird beim Ändern der Link-URL nicht beibehalten, wenn der Anzeigetext beim Definieren der Schlüsselreferenz nicht hinzugefügt wird. (9458)
* Im Versionsverlauf werden Versionsnummer und Titel für die aktuelle Version nicht angezeigt. (9446)
* Editor friert ein, wenn bestimmte Inhaltsdateien im Editor geöffnet werden. (9443)
* Die Suche im Repository-Bedienfeld und im Dialogfeld zum Durchsuchen von TopicRef friert den Bildschirm ein, wenn der Inhalt groß ist. (9432)
* An die Ausgabe der AEM-Site übergebene Metadaten berücksichtigen nicht die Grundlinie des Inhalts. (9416)
* Oxygen überprüft eine falsche Version eines Themas, nachdem eine Version in AEM zurückgesetzt wurde. (9411)
* Fehlgeschlagene Baseline deaktiviert die Bearbeitung auf der Registerkarte „Voreinstellung“ im Karten-Dashboard. (9403)
* Bei der Erstellung neuer Inhalte wird immer ein Fehler protokolliert. (9388)
* Neu erstellte DITA-Assets werden immer von einem anderen Benutzer ausgecheckt. (9 387)
* Das Umbenennen des Elements funktioniert beim Konvertieren von „topicRef“ in „glossref“ nicht ordnungsgemäß. (9380)
* Versionsbezeichnung wird im Dialogfeld „Als neue Version **&quot; nicht** Dropdown angezeigt. (9379)
* Bedingungen werden beim Wechseln zwischen verschiedenen Versionen aus dem Dropdown-Menü **Differenz anzeigen** nicht angewendet. (9366)
* Bei der Verwendung von Vorschaufiltern treten mehrere Probleme auf. (9365)
* Nicht-DITA- und DITAVAL-Assets können nicht in topicref eingefügt werden. (9363)
* Die genehmigte Übersetzung integriert sich nicht in die Zielsprache, wenn der Code der Zielsprache fünf Zeichen wie `fr_ca` enthält. (9357)
* Es können keine Dateien mit &quot;**in Ordner suchen** im Menü **Weitere Optionen** durchsucht werden, und die App reagiert nicht mehr. (9337)
* Das Dialogfeld „Durchsuchen“ bleibt hängen, wenn eine große Anzahl von Schlüsseln vorhanden ist. (9332)
* DITAVAL-Dateien funktionieren nicht beim Veröffentlichen auf Artikelbasis. (9330)
* Die Reihenfolge der Fußnoten ist in der Ausgabe der AEM-Site falsch. (9327)
* Die Suche wird nicht automatisch durchgeführt, wenn die Option „Pfad auswählen“ geändert wird. (9323)
* Wenn die Übersetzung abgeschlossen ist, wird eine zusätzliche Version für das übersetzte Asset erstellt. (9310)
* Die Administratorbenutzer im Ordnerprofil können nicht gelöscht werden. (9306)
* Die Stammzuordnung, die über die Inhaltsschlüsselreferenz aktualisiert wurde, wird erst festgelegt, nachdem die Seite aktualisiert wurde. (9302)
* Web-Authentifizierung funktioniert nicht in Oxygen. (9296)
* Weblinks mit kodierten Zeichen funktionieren nicht ordnungsgemäß. (9227)
* Die Datei wird beim Öffnen mit Sauerstoff nicht ausgecheckt. (9217)
* Ausgecheckte Dateien aktualisieren funktioniert nicht bei der Protokollierung mit Webauthentifizierung in Oxygen. (9179)
* Die Registerkarten „Übersetzung“ und „Baseline“ sind einige Zeit lang im Zuordnungs-Dashboard sichtbar. (9 146)
* Beim erneuten Laden des Ordnerprofils treten Erlebnis- oder Funktionsprobleme auf. (9103)
* Beim Löschen des Seitenlayouteditors wird dieser nicht über den mittleren Bereich in der Autorenansicht geschlossen. (9087)
* Im Web-Editor tritt ein Validierungsfehler auf, wenn ein Bild entfernt und dann die neue Version des Dokuments gespeichert wird. (8985)
* Es können nicht alle `glossrefs` im Glossar-Bedienfeld angezeigt werden (inhaltsspezifisch). (8 886)
* `xref` ohne Text wird in der auf Artikeln basierenden Veröffentlichungsausgabe nicht angezeigt. (8 764)
* Verweise werden bei Bewegtbildern oder Multimediadateien beschädigt, die in den Dateinamen ein Leerzeichen enthalten. (8 624)
* Verweise werden beschädigt, wenn Sie `Select All` auswählen und die Multimediadateien oder DITA-Inhalte in einen anderen Ordner verschieben. (8622)
* Ausgabeaufträge mit dem Status „Warten“ oder „Wird ausgeführt“ werden im Veröffentlichungs-Dashboard nicht bereinigt.  (8 569)
* Die Ausgabe-Bereinigungsfunktion schlägt fehl, wenn eine große Anzahl von übrig gebliebenen Ausgabe-Verlaufsknoten vorhanden ist. (8568)
* Das DITA Add-on-Paket verhindert die Erkennung von DAM-Duplikat-Assets. (8417)
* Schaltfläche „Prüfungsaufgabe erstellen“ für Nicht-DITA-Dateien aktiviert. (8401)
* Das Dialogfeld „Verweise einfügen“ wird beim Hinzufügen eines Betreffs zu einer Zuordnung über die Benutzeroberfläche geöffnet. (8212)
* In jedem leeren `entry`-Element wurde unerwarteter Leerraum gefunden, wenn dem `tgroup`-Element das Attribut „outputClass“ hinzugefügt wird. (7532)
* Das Repository-Bedienfeld zeigt keine Symbole für ein- oder ausgecheckte Dateisperren an, sobald die Aktion abgeschlossen ist. (5 817)
* Das Sperrsymbol wird in der Repository-Ansicht angezeigt, auch wenn die Datei aus dem Editor eingecheckt wird.  (5 756)
* Sites fehlen in den AEM-Vorgaben auf der Registerkarte „Ausgabe“. (9567)
* Der XML-Editor reagiert nicht mehr auf den Versuch, einige DITA-Dateien zu bearbeiten. (9537)
* Wenn Sie eine Suche im XML-Editor durchführen, friert die Seite ein. (9452)
* Karte herunterladen mit Grundlinie funktioniert nicht, wenn der Inhalt in einen anderen Ordner verschoben wird. (9331)
* Das erneute Hochladen schlägt in Oxygen fehl, wenn die Datei(en) bereits in AEM am selben Speicherort vorhanden sind. (9328)
* Die Position der Hervorhebung ist in der Seitenansicht falsch. (9305)
* Nach dem Einchecken eines Dokuments von Oxygen nach AEM wird der japanische Inhalt im Dokument durch Fragezeichen (???) ersetzt. (9276)
* Das Hochladen von Dateien von Oxygen auf AEM schlägt fehl. (9157)
* Die E-Mail-Benachrichtigung wird nicht gesendet, wenn eine Prüfungsaufgabe im Posteingang erneut zugewiesen wird. (8 376)

## Bekannte Probleme

Beim Öffnen des Editors wird gelegentlich eine leere Seite angezeigt.
