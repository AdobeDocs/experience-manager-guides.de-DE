---
title: Versionshinweise zu | Neue Funktionen in Adobe Experience Manager Guides Version 5.1.0
description: Erfahren Sie mehr über die neuen und erweiterten Funktionen der Version 5.1.0 von Adobe Experience Manager Guides
role: Leader
source-git-commit: f6617b727d385d31ba66d575ee48f29e77ac716f
workflow-type: tm+mt
source-wordcount: '1398'
ht-degree: 0%

---

# Neue Funktionen in Version 5.1.0 (September 2025)

Dieser Artikel behandelt die neuen und erweiterten Funktionen, die mit Version 5.1.0 von Adobe Experience Manager Guides eingeführt wurden.

Eine Liste der in dieser Version behobenen Probleme finden Sie unter [Behobene Probleme in Version 5.1.0](fixed-issues-5-1-0.md).

Erfahren Sie mehr [Upgrade-Anweisungen für Version 5.1.0](../release-info/upgrade-instructions-5-1-0.md).


## Verbesserter Überprüfungs-Workflow

Mit dieser Version wurde der Überprüfungs-Workflow erheblich verbessert, um die nahtlose Kommunikation zwischen Autoren und Prüfern zu verbessern. Zu den wichtigsten Aktualisierungen gehören:

- Aufgabenverwaltungs-Workflows mit verwertbaren Benachrichtigungen
- Möglichkeit, Benutzende zu taggen, um sofortige Aufmerksamkeit zu erhalten
- Einfacherer Zugriff auf Projekt- und Aufgabendetails über das Überprüfungsfeld

Mit diesen Verbesserungen können Benutzer jetzt Folgendes erwarten:

- Effiziente und zeitnahe Überprüfungszyklen
- Reduzierter manueller Aufwand beim Austausch von Feedback

Weitere Informationen finden Sie unter [Einführung in die Überprüfung](../user-guide/review.md)

## Verbessertes Erlebnis bei der Erstellung und Verwendung von DITAVAL-Dateien

Diese Aktualisierung führt mehrere Verbesserungen ein, die die Erstellung, Verwaltung und Anwendung von DITAVAL-Dateien vereinfachen und eine bessere Kontrolle über bedingte Inhalte und Stile in allen Ausgaben ermöglichen.

Die wichtigsten Highlights sind:

- **Verbesserte Unterstützung für das Markieren in der Bearbeitung von DITAVAL-Dateien:** Experience Manager Guides bietet neue Funktionen zum Anpassen der Inhaltsveröffentlichung durch verbesserte Unterstützung für das Markieren in DITAVAL-Dateien. Sie können jetzt Start- und End-Flags um bestimmte Inhalte, einschließlich Bildern, anwenden und markierte Abschnitte mit Formatierungsoptionen wie fett, kursiv und mehr anreichern. Um Bedingungsüberschneidungen zu handhaben, kann der **Stilkonflikt** konfiguriert werden. Dazu gehört das Festlegen einer standardmäßigen Hintergrund- und Textfarbe, um Klarheit und Konsistenz in der Ausgabe sicherzustellen. Diese Flags werden in der nativen PDF-Generierung vollständig unterstützt, und die resultierende Ausgabe spiegelt alle angewendeten Stilelemente genau und umfassend wider.
Weitere Informationen finden Sie unter [Verwenden des DITAVAL-Editors](../user-guide/ditaval-editor.md).

  ![](assets/ditaval-flag-style-new.png){width="350" align="left"}

- **Unterstützung mehrerer DITAVAL-Dateien für native PDF:** Für native PDF können jetzt mehrere DITAVAL-Dateien hinzugefügt werden, die jeweils als getaggter Eintrag angezeigt werden, um sie leicht zu identifizieren und zu entfernen. Dies bietet mehr Flexibilität und Kontrolle über bedingte Inhalte in PDF-Ausgaben

  Darüber hinaus verbessert diese Aktualisierung die Erstellung von Ausgabevorgaben, indem bearbeitbare DITAVAL-Felder in allen Formaten aktiviert werden, sodass Benutzende DITAVAL-Pfade manuell angeben können.

  Weitere Informationen finden Sie unter [&#x200B; von Ausgabevorgaben &#x200B;](../user-guide/generate-output-understand-presets.md) Experience Manager Guides.

## Verbesserungen beim Veröffentlichen

Im Rahmen der neuen Version wurden die folgenden Veröffentlichungsverbesserungen vorgenommen:

### Verbesserte Protokollfilterung der Ausgabenerstellung

Diese Version bietet Verbesserungen an der Benutzeroberfläche für die Filterfunktion für Ausgabegenerierungsprotokolle. Sie können jetzt die Ausgabenerstellungsprotokolle besser nach allen vier verschiedenen Ebenen filtern: **Info**, **Warn**, **Error** (einschließlich Fehler und Ausnahmen) und **Fatal** mit verbesserten und intuitiven farbcodierten Indikatoren, die die Analyse vereinfachen und die Sichtbarkeit im gesamten Protokollstrom verbessern. Diese Verbesserung ermöglicht eine effizientere Navigation in Protokollen und eine präzise Lokalisierung kritischer Probleme.

Weitere Informationen finden Sie unter [Allgemeine Fehlerbehebung](../user-guide/generate-output-basic-troubleshooting.md).

![](./assets/log-file-new.png){align="left"}


### Temporäre Dateien für die veröffentlichte Ausgabe enthalten jetzt Autoren- und Veröffentlichungs-URLs in einer neuen Konfigurationsdatei

Die neuesten Veröffentlichungsverbesserungen für Experience Manager Guides fügen jetzt eine neue `system_config.xml`-Datei zu den temporären Dateien hinzu, die beim Veröffentlichen von HTML-, PDF- und JSON-Ausgaben mit DITA-OT generiert wurden, sowie die native PDF-Ausgabe. Diese Datei wird automatisch in den Veröffentlichungsauftrag aufgenommen und kann auch über temporäre Dateien aufgerufen werden, wenn Sie die Option **Temporäre Dateien beibehalten** für die Voreinstellungen aktivieren und die Ausgabe generieren.

Die `system_config.xml`-Datei enthält Details zur AEM-Instanz, einschließlich der Autoren-URL, der lokalen URL und der Veröffentlichungs-URL, wodurch der Kontext klarer wird und die Rückverfolgbarkeit der heruntergeladenen URLs verbessert wird.

Weitere Informationen finden Sie unter [Grundlegendes zu Ausgabevorgaben](../user-guide/generate-output-understand-presets.md).

### Neue Unterstützung von Ausgabepfadvariablen für die Ausgabegenerierung

Dieses Update führt die dynamische `output path` für Ausgabevorgaben wie native PDF, DITA-OT-PDF, JSON, HTML5 und benutzerdefinierte Einstellungen ein. Statt einen festen Pfad zu verwenden, können Benutzer jetzt den Ausgabespeicherort während der Installation mit der Variablen `${base_output_path}` definieren, was eine größere Flexibilität bietet. Der vorherige Standardpfad `/content/dam/fmdita-outputs` ist nicht mehr erforderlich.

Alle Ausgabepfade, die mit den globalen Ordnerprofilvorgaben verknüpft sind, werden automatisch migriert, um die neue Basisausgabepfadvariable zu nutzen. Bei benutzerdefinierten Ordnerprofilen erfolgt die Migration jedoch nicht automatisch. Es wird empfohlen, sich an das Customer Success-Team zu wenden, um Unterstützung zu erhalten.

Weitere Informationen finden Sie unter [Grundlegendes zu Ausgabevorgaben](../user-guide/generate-output-understand-presets.md).

### Exportierte Baseline enthält jetzt den Dokumentstatus

Die Funktion „Baseline exportieren“ enthält jetzt **Dokumentstatus** sowie wichtige Details wie Titel, Dateiname, Dateityp und Versionsnummer in der Baseline-Momentaufnahme. Diese Verbesserung verbessert das Baseline-Management, indem sie einen umfassenderen Überblick über die Baseline bietet.

Weitere Informationen finden Sie unter [Baselines in der Map-Konsole erstellen und verwalten](../user-guide/web-editor-baseline.md#manage-baselines).

### Unterstützung für die grundlagengesteuerte inkrementelle Veröffentlichung über das Zuordnungs-Dashboard für die AEM Sites-Ausgabe unter Verwendung der Legacy-Komponentenzuordnung

Der Prozess der inkrementellen Ausgabegenerierung wurde verbessert, um die Veröffentlichung spezifischer Themenversionen zu unterstützen, die in der ausgewählten Baseline für AEM Sites mithilfe der Legacy-Komponentenzuordnung definiert wurden, und um eine genaue Verbreitung des Inhalts in der Ausgabe sicherzustellen.

Weitere Informationen finden Sie unter [Inkrementelle Ausgabegenerierung](../user-guide/generate-output-aem-site.md).

## Verbesserungen am Editor

Im Rahmen der neuen Version wurden die folgenden Editor-Verbesserungen vorgenommen:

### Verbessertes Sucherlebnis für das Bedienfeld „Wiederverwendbarer Inhalt“

Experience Manager Guides bietet ein verbessertes Sucherlebnis im Bedienfeld „Wiederverwendbarer Inhalt“. Mit diesem Update werden bei der Suche nach einem Keyword jetzt alle Dateien gescannt, die als wiederverwendbarer Inhalt hinzugefügt wurden, und nicht nur die offenen, um sicherzustellen, dass Sie die genaue Position des Keywords auf allen Vorkommen finden, unabhängig davon, ob die Container geöffnet oder reduziert sind. Wenn Sie die Suchleiste löschen, wird außerdem der Originalzustand aller Container beibehalten, was eine effizientere und benutzerfreundlichere Suchfunktion bietet.

Weitere Informationen finden Sie unter [Wiederverwendbare Inhalte](../user-guide/web-editor-features.md#reusable-content).

### Attribut &#39;Format&#39; für Referenz-Links hinzugefügt

Adobe Experience Manager Guides fügt jetzt ein **format**-Attribut für Referenz-Links im Editor hinzu. Dieses Attribut wird in der Ansicht **Source angezeigt** gibt den Dateityp deutlich an, z. B.:

- Für Dateien mit der Erweiterung **.pdf** wird das Format auf **pdf** festgelegt
- Für Dateien mit der Erweiterung **.** wird das Format auf &quot;**&quot;**
- Für Dateien mit den Dateien **.** oder **.** wird das Format auf **dita**

Darüber hinaus ist das Format von Dateien mit der **&#x200B;**.xml **ebenfalls auf dita** festgelegt. Bei Dateien ohne Erweiterung bleibt das Format leer. Darüber hinaus wird für alle Referenz-Links mit dem Bereich **extern** das Format auf **html** festgelegt, unabhängig von der Dateierweiterung in den Referenz-Links.

### Verbesserte Download-Optionen für Karten im Editor

Experience Manager Guides führt eine neue Option **Verwenden tatsächlicher Dateinamen** im Dialogfeld **Karte herunterladen** ein. Wenn Sie jetzt Zuordnungsdateien herunterladen, können Sie die ursprünglichen Dateinamen anstelle der standardmäßigen UUIDs beibehalten, was die Erkennung und Verwaltung Ihrer Dateien erheblich erleichtert. Diese Option ist nur verfügbar, wenn Sie **Dateihierarchie beibehalten** auswählen. Sie ist deaktiviert, wenn Sie **Dateihierarchie reduzieren** auswählen, was Ihnen mehr Flexibilität bei der Organisation Ihrer heruntergeladenen Karten gibt.

Weitere Informationen finden Sie unter [Dateien &#x200B;](../user-guide/authoring-download-assets.md#download-a-dita-map-file-from-the-editor).

![](assets/download-map-dialog-new.png){width="300" align="left"}

### Eingabeaufforderung für Sitzungs-Timeout, um versehentlichen Inhaltsverlust zu verhindern

Eine Popup-Meldung informiert Sie jetzt darüber, wenn Ihre Adobe Experience Manager-Sitzung abläuft und Sie aufgrund von Inaktivität abgemeldet werden. Diese Nachricht wird ausgelöst, wenn Sie versuchen, Inhalte in Experience Manager Guides zu bearbeiten, nachdem die Sitzung beendet wurde. Die Funktion trägt dazu bei, das Risiko des Verlusts nicht gespeicherter Arbeit zu reduzieren, und verbessert die Zuverlässigkeit und Fließfähigkeit des Erlebnisses insgesamt, auch in Zeiträumen der Inaktivität.

![](assets/sign-out-prompt.png)

Weitere Informationen zur [Sitzungs-Zeitüberschreitungsaufforderung](../user-guide/session-timeout-prompt.md) in Experience Manager Guides.

### Verbesserte `navref` im Editor

Die neuesten Verbesserungen am Editor verbessern die Handhabung von `navref` in einer DITA-Zuordnung. Wenn Sie nun ein `navref` Element zu einer Karte hinzufügen, wird das Dialogfeld **Pfad auswählen** geöffnet, in dem Sie einfach die Kartenverweise auswählen können, die als Navigations-Links in Ihre Karte aufgenommen werden sollen. Nach dem Hinzufügen wird der Titel der hinzugefügten Zuordnung sowohl in der Autoren- als auch in der Layout-Ansicht angezeigt, wodurch die enthaltene Navigation beim Authoring besser sichtbar wird.  Darüber hinaus wird das hinzugefügte `navref` automatisch aufgelöst, um die referenzierte Zuordnung im Editor anzuzeigen.

Weitere Informationen finden Sie unter [Navigationsverweise hinzufügen](../user-guide/map-editor-other-features.md#add-navigation-references).


### Verbesserungen der Benutzeroberfläche in der Editor-Symbolleiste und Benutzereinstellungen

Mit dieser Version wurden die Einstellungen in **Benutzereinstellungen** auf der Startseite für die Registerkarten „Allgemein“ und „Erscheinungsbild“ neu strukturiert. Dazu gehört das Umbenennen der Beschriftung **Öffnen der Voreinstellungen für**) und das Verschieben des Umschalters Leerzeichen ohne Unterbrechung in die Editor-Symbolleiste.

Darüber hinaus sind in der Editor-Symbolleiste einige Umschalter für den Schnellzugriff zum Aktivieren oder Deaktivieren von Änderungen, Tags und nicht umbrechenden Leerzeichen jetzt unter der Option **Anzeigen** im Dropdown-Menü gruppiert, um die Benutzerfreundlichkeit zu verbessern.

Weitere Informationen finden Sie unter [Symbolleiste im Editor](../user-guide/web-editor-toolbar.md#menu-dropdown).







