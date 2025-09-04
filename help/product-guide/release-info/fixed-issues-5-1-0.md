---
title: Versionshinweise zu | Es wurden Probleme in Adobe Experience Manager Guides Version 5.1.0 behoben
description: Erfahren Sie mehr über die Fehlerbehebungen in Version 5.1.0 von Adobe Experience Manager Guides.
source-git-commit: 6c29d5540f48c850416db279b4392b6042c8ca2c
workflow-type: tm+mt
source-wordcount: '1789'
ht-degree: 1%

---

# Es wurden Probleme in Version 5.1.0 (September 2025) behoben

Dieser Artikel behandelt die in verschiedenen Bereichen von Version 5.1.0 von Adobe Experience Manager Guides behobenen Fehler.


Weitere Informationen zu den neuen Funktionen und Verbesserungen finden Sie unter [Neue Funktionen in Version 5.1.0](whats-new-5-1-0.md).

Erfahren Sie mehr [Upgrade-Anweisungen für Version 5.1.0](upgrade-instructions-5-1-0.md).


## Authoring

- **CSS**- und **Seitenlayout**-Dateien in nativen PDF-Vorlagen weisen ein inkonsistentes Dateisperrverhalten auf, sodass sie auch dann bearbeitet werden können, wenn die Dateien gesperrt sind. (GUIDES-26688)
- Wenn Sie die Seite aktualisieren, nachdem Sie dem linken Bedienfeld benutzerdefinierte Schaltflächen hinzugefügt haben, werden doppelte Registerkarten erstellt. (GUIDES-30899)
- Wenn XML-Inhalte mit eckigen Klammern (z. B. &lt;/ oder />) innerhalb eines `code block` Elements in einem Thema hinzugefügt werden, wird das Code-Blockelement in der endgültigen Ausgabe leer angezeigt. (GUIDES-31007)
- Die Werte der globalen Variablen `canCheckIn` und `canCheckOut` werden nicht korrekt festgelegt, wenn eine Datei über die Editor-Symbolleiste aus- und eingecheckt wird.(GUIDES-29890)
- Wenn eine DITA-Zuordnung in der Kartenansicht ausgewählt wird, wird die Auswahlanzahl zunächst falsch angezeigt, da die untergeordneten Knoten der Zuordnung nicht ausgewählt sind. Die korrekte Anzahl der Auswahlen und die Einbeziehung aller untergeordneten Knoten wird erst bei der nachfolgenden Auswahl angezeigt. (GUIDES-25663)
- Markdown-Dateien werden nicht abgerufen, wenn im Repository-Bereich mit dem Filter **DITA-Thema** gesucht wird. Außerdem funktionieren **Suchen und Ersetzen** nicht für Markdown-Dateien und zugehörige Inhalte. (GUIDES-27133)
- Das **Menü-Dropdown-Menü** der Editor-Symbolleiste kann nicht mit dem Erweiterungs-Framework angepasst werden. Daher können Sie im Dropdown-Menü „Menü“ keine vorhandenen Schaltflächen ausblenden oder anzeigen bzw. neue Schaltflächen hinzufügen. (GUIDES-28748)
- Wenn ein XML-Kommentar innerhalb eines Elements in der Source-Ansicht hinzugefügt wird, gehen die führenden und nachfolgenden Leerzeichen um den Kommentar verloren, wenn die Ansicht gewechselt wird. (GUIDES-29781)
- Multimediaoptionen funktionieren nicht, wenn sie auf dem Symbol mit den Auslassungspunkten (dem **Mehr**-Menü) in der Symbolleiste vorhanden sind. (GUIDES-29583)
- Beim Erstellen eines neuen Themas über die Assets-Benutzeroberfläche oder den Editor wird das Thema nicht automatisch im Editor geöffnet, wenn die `xmleditor.uniquefilenames` in `XMLEditorConfig` auf „true“ festgelegt ist. (GUIDES-28171)
- Leerzeichen, die innerhalb einer MathML-Gleichung in der Source-Ansicht hinzugefügt werden, bleiben beim Wechseln der Editor-Ansichten nicht erhalten. (GUIDES-26111)
- Wenn JCR-Sitzungsverbindungen beim Aktualisieren oder Erstellen von Themen nicht geschlossen werden, führt dies zu Speicherlecks und Service-Ausfallzeiten. (GUIDES-26282)
- Durch Ziehen der Spalten wird deren Breite von Prozentsatz zu Pixelwerten geändert, was zu verzerrten oder falsch ausgerichteten Tabellen führt.(GUIDES-23128)
- Wenn Inhalte in ein `code block` eingefügt werden oder Leerzeichen im `code block` hinzugefügt werden und die Ansicht gewechselt wird, gehen die Leerzeichen verloren. (GUIDES-27478)
- Beim Hinzufügen einer Zuordnung zum `bookmap` wird diese in `fmditatopicrefs` anstatt in `fmditamaprefs` gespeichert. (GUIDES-25480)
- Das **„Bild einfügen** kann auf einem hochauflösenden oder auszoomten Bildschirm nicht korrekt gerendert werden, wodurch der Bildtitel und die alternativen Textfelder verschwinden. (GUIDES-26459)
- Das Feld zum Einfügen von Sonderzeichen im Editor kann für das deutsche Gebietsschema nicht geladen werden. (GUIDES-24537)
- Kommentare und Beschriftungen, die beim Speichern einer neuen Version einer DITAVAL-Datei hinzugefügt werden, werden mit der neuen Version nicht im Versionsverlauf gespeichert. (GUIDES-24076)
- Die ausgehenden und eingehenden Verweise unter **Dateieigenschaften** im rechten Bereich werden beim Wechsel zwischen Zuordnungsdateien nicht ordnungsgemäß aktualisiert. Dieses Problem tritt insbesondere dann auf, wenn die Zuordnungsdateien eine große Anzahl von Verweisen enthalten. (GUIDES-23344)
- Der Repository-Filter behält die Reihenfolge der benutzerdefinierten Filter, die in der `ui_config.json` definiert sind, nicht bei. (GUIDES-21193)
- Durch das Löschen mehrerer Textzeilen in einem `codeblock` wird ein leerer Bereich erstellt, der nicht aus der Autorenansicht entfernt werden kann. (GUIDES-20672)
- Neue IDs können für Elemente nicht generiert werden, wenn solche Elemente über Ausschnitte hinzugefügt oder über Vorlagen erstellt werden, selbst wenn **Option „ID automatisch generieren** in `XMLEditorConfig` aktiviert ist. (GUIDES-21734)
- Beim Erstellen eines neuen DITA-Assets aus DITA-Vorlagen werden die Replikationseigenschaften aus den entsprechenden DITA-Vorlagen kopiert. (GUIDES-25145)
- Der Zugriff auf Dateieigenschaften über das Repository-Bedienfeld ist nicht möglich, wenn der Name des übergeordneten Ordners das Zeichen &quot;&amp;&quot; enthält. (GUIDES-25762)
- Durch Schließen einer Themendatei kann diese als neue Version gespeichert werden, auch wenn das Thema gesperrt ist. Dieses Problem tritt insbesondere auf, wenn die Option **Nach neuer Version beim Schließen** fragen“ in `XMLEditorConfig` aktiviert ist. (GUIDES-23875)
- Die aktuelle maximale Breite des Repository-Bereichs blendet Themen- und Zuordnungstitel aus, wenn die Inhaltshierarchie tief verschachtelt ist. (GUIDES-27751)

## Asset-Management

- Das Kopieren eines Ordners mit einer großen Anzahl von Assets aus der Assets-Benutzeroberfläche führt zu einer API-Zeitüberschreitung. Der Vorgang wird weiterhin im Backend ausgeführt und nach einiger Zeit abgeschlossen, aber in der Benutzeroberfläche wird keine Erfolgs- oder Fehlermeldung oder Benachrichtigung angezeigt. (GUIDES-30900)
- Ein Kopieren/Einfügen-Vorgang, der für einen Ordner in der Assets-Benutzeroberfläche ausgeführt wird, schlägt aufgrund von Nachbearbeitungsfehlern fehl. (GUIDES-30840)
- Das Kopieren und Einfügen schlägt für Ordner mit ebenenübergreifenden Assets (Assets mit Unter-Assets) in der Assets-Benutzeroberfläche fehl. (GUIDES-28107)
- Ordner mit einer großen Anzahl von Assets werden nicht ordnungsgemäß in das Repository geladen. (GUIDES-32500)
- Ordner-Knotennamen werden im Editor fälschlicherweise anstelle von Ordnertiteln angezeigt. (GUIDES-32402)
- Beim Hochladen von Assets mit nicht unterstützten oder unzulässigen Zeichen in den Dateinamen tritt ein Fehler auf. (GUIDES-28845)
- Beim Öffnen eines Themas in der Autorenansicht nach einer Browser-Aktualisierung werden zuvor angewendete Tags im Bedienfeld Dateieigenschaften nicht beibehalten und das Hinzufügen neuer Tags überschreibt die vorhandenen, insbesondere wenn eine große Anzahl von Tags zur Auswahl verfügbar ist. (GUIDES-29078)
- Beim Generieren eines Metadatenberichts für eine DITA-Zuordnung, die eine große Anzahl von Assets enthält, reagiert die Schaltfläche **Verwalten** nicht mehr oder zeigt eine verzögerte Antwort an. (GUIDES-28443)
- Der Dokumentstatus aus der Arbeitskopie eines Themas wird für alle Versionen dieses Themas in der Benutzeroberfläche „Übersetzung und Grundlinie“ angezeigt. (GUIDES-20674)

## Überprüfung

- Versuche, Überprüfungsaufgaben über den AEM-Workflow zu erstellen, schlagen konsequent fehl, da der Überprüfungsknoten nicht erstellt wird. (GUIDES-28214)
- Die Dokumentansicht in der Überprüfungs-Benutzeroberfläche umschließt den Inhalt für einige Bildschirmgrößen nicht, sodass Benutzende horizontal scrollen müssen, um den gesamten Inhalt anzuzeigen. (GUIDES-25292)
- Beim Aktualisieren der Details einer Prüfungsaufgabe im Überprüfungs-Dashboard wird nicht bestätigt, ob die Aktualisierung erfolgreich war oder nicht. (GUIDES-8051)

## Übersetzung

- Übersetzungen, die über Experience Manager Guides übermittelt werden, enthalten keine angehängten Assets, was dazu führt **dass die Schaltfläche** Starten“ für den Übersetzungsauftrag für Benutzende nicht mehr verfügbar ist. (GUIDES-28237)

## Publishing

- In der nativen PDF-Ausgabe wird die Indexliste (LOI) in nicht alphabetischer Reihenfolge angezeigt und verschachtelte Indexbegriffe werden nicht richtig gruppiert, was die Navigation innerhalb des Index erschwert. (GUIDES-29090)
- Die **Seitenvorlage zuordnen** und **Themenseitenvorlage** Dropdown-Liste auf der Seite „Ausgabevorgabe für die AEM Sites-Komponentenzuordnung“ wird leer angezeigt, wenn der Zielpfad eine Variable mit einem Doppelpunkt enthält. (GUIDES-28119)
- Wenn eine DITA-Zuordnung verschiedene Arten von Themenverweisen wie Konzept, Referenz oder Aufgabe enthält und mithilfe des `chunk=to-content`-Attributs zusammengeführt wird, um eine Einzelseitenausgabe in AEM Sites mit der Komponentenzuordnung zu generieren, wird der Inhalt aufgrund von Veröffentlichungsfehlern nicht ordnungsgemäß veröffentlicht. (GUIDES-28118)
- Beim Veröffentlichen einer DITA-Zuordnung mit `chunk=to-content` Attribut werden doppelte JCR-Knoten in der neuen AEM Sites-Ausgabe erstellt, was zu einer redundanten Inhaltsstruktur in AEM Sites führt. (GUIDES-28104)
- Wenn beim Veröffentlichen einer DITA-Zuordnung mit der neuen AEM Sites-Ausgabe ein Thema das `chunk =to-content` hat und die Ausgabe so eingestellt ist, dass Thementitel als Seitennamen verwendet werden, wird im generierten Seitennamen fälschlicherweise das Wort **Chunk** angezeigt, anstatt den ursprünglichen Themennamen beizubehalten. (GUIDES-28102)
- Die `cq:template` -Eigenschaft, die in der AEM Guides-Themenvorlage für neue AEM Sites-Veröffentlichungen festgelegt ist, zeigt einen falschen Wert an, was sich auf die Vorlagenstruktur und das Rendern von Inhalten auswirkt. (GUIDES-27789)
- Die native PDF-Veröffentlichung wird auf unbestimmte Zeit fortgesetzt, wenn der DITA-Inhalt über einen Weblink verfügt, ohne dass der Umfang wie `external` vorhanden ist. (GUIDES-26434)
- Die Veröffentlichung nativer PDFs und AEM-Sites verzögert sich und wird in die Warteschlange gestellt, wenn Fehler im Inhalt auftreten. (GUIDES-26516)
- Beim Generieren von AEM Site-Seiten mit Titeln, die mehrere Wörter enthalten, die durch Leerzeichen getrennt sind, zeigt der Zuordnungstitel Bindestriche anstelle von Leerzeichen an. (GUIDES-27903)
- Bei der nativen PDF wird ein ungültiger Metadaten-Eigenschaftsname nicht aufgelöst und wie `unresolved property name` in **Dokumenteigenschaften** angezeigt. (GUIDES-25680)
- Mehrzeiliger Text in `codeblock` verursacht Probleme mit Textüberläufen während der PDF-Generierung. (GUIDES-15541)
- Beim Hinzufügen von Zuordnungen zur Zuordnungssammlung werden andere Assets als Zuordnungen (z. B. Themen usw.) angezeigt und die übersetzten Zuordnungssprachen werden ebenfalls nicht ordnungsgemäß sortiert.(GUIDES-25085)
- Im alten AEM Sites-Output werden Abschnittslinks innerhalb verschachtelter Themen einer Zuordnung nicht korrekt aufgelöst, wenn sie manuell im Source-Modus festgelegt werden oder der Inhalt aus einer externen Quelle importiert wird. Anstatt zum vorgesehenen Abschnitt zu navigieren, leiten sie zum Hauptthema um, das das verschachtelte Thema enthält. (GUIDES-26103)
- Wenn das `scope=external` Attribut in externen Links in einem DITA-Thema fehlt, schlägt die Veröffentlichung von HTML5 fehl, ohne dass die Dateien angegeben werden, in denen dieses Attribut in den Fehlerprotokollen fehlt. (GUIDES-25969)
- Video-Links können nicht in natives PDF eingebettet werden, selbst wenn die Option **Multimediadateien einbetten** in der PDF-Vorgabe aktiviert ist. (GUIDES-9989)
- Die Metadateneigenschaften können nicht an Zuordnungs-Landingpages übergeben werden, die mit der neuen AEM Sites-Veröffentlichung generiert wurden. (GUIDES-27288)

## Grundlinie

- Beim Kopieren einer DITA-Zuordnung über die Assets-Benutzeroberfläche wird auch die angehängte Baseline in die neue Zuordnung kopiert. (GUIDES-11227)
- Beim Erstellen einer neuen Baseline mit einer großen Anzahl von Kennzeichnungen wird verhindert, dass alle Kennzeichnungen abgerufen werden. (GUIDES-16232)

## Startseite

- Die Startseite wird leer, wenn eine der im Widget **Letzte Dateien** aufgelisteten Dateien auf einer Vorlage basiert, deren Quellvorlage keine Miniaturansicht enthält. (GUIDES-31506)

## Platform

- Bei der Arbeit mit großen Sammlungen treten Leistungsprobleme wie längere Ladezeiten und zeitweise auftretende Zeitüberschreitungen auf. (GUIDES-29065, GUIDES-28793)
- Schwachstellen im Zusammenhang mit der veralteten Guava-Bibliothek, die in auf Experience Manager Guides hochgeladenen AEM Guides-Komponenten verwendet wird.(GUIDES-27402)

## Bekannte Probleme

Adobe hat die folgenden bekannten Probleme in Version 5.1.0 identifiziert:


- Der letzte Kommentar auf Aufgabenebene wird in der E-Mail-Benachrichtigung an den Aufgabeninitiator angezeigt, wenn der Reviewer die Aufgabe abschließt, ohne einen Kommentar hinzuzufügen. (GUIDES-33590)
- Im Dialogfeld „Zusammenführen“ wird in der Dropdown-Liste fälschlicherweise der Hauptinhalt angezeigt, anstatt die verfügbaren Versionen des ausgewählten Themas anzuzeigen. (GUIDES-30820)
- Beim Wechseln zwischen Voreinstellungen, die dieselbe Baseline verwenden, wird die Schaltfläche Speichern für die aktuelle Voreinstellung deaktiviert. (GUIDES-28025)
- Eine leere Zeile wird automatisch eingefügt, wenn neue Inhalte in eine neue Zeile innerhalb eines Codeblock-Elements eingefügt werden.(GUIDES-27842)
- Ein Thema innerhalb einer DITA-Zuordnung kann nicht in der AEM Sites-Ausgabe veröffentlicht werden, wenn es sowohl als keydef als auch als topicref in seinen Unterzuordnungen verwendet wird. (GUIDES-22269)
- Im Bedienfeld Inhaltseigenschaften wird das Feld Attribute automatisch geschlossen, wenn Sie versuchen, einen Verweis im Dialogfeld Link aktualisieren zu aktualisieren, sodass der Link nicht aktualisiert wird. (GUIDES-17767)