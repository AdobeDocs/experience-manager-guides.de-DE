---
title: Versionshinweise zu | Adobe Experience Manager Guides as a Cloud Service, Version November 2022
description: November-Version von Adobe Experience Manager Guides as a Cloud Service
exl-id: 9f329ec1-dd74-47cc-8567-3fadd962584a
feature: Release Notes
role: Leader
source-git-commit: 6d8c01f20f7b59fed92c404561b647d9ebecb050
workflow-type: tm+mt
source-wordcount: '1384'
ht-degree: 0%

---

# November-Version von Adobe Experience Manager Guides as a Cloud Service

## Upgrade auf die November-Version

Führen Sie ein Upgrade Ihres aktuellen Adobe Experience Manager Guides as a Cloud Service-Setups (später als *AEM Guides as a Cloud Service* bezeichnet) durch, indem Sie die folgenden Schritte ausführen:
1. Checken Sie den Git-Code der Cloud Service aus und wechseln Sie zu der Verzweigung, die in der Cloud Service-Pipeline konfiguriert ist und der Umgebung entspricht, die Sie aktualisieren möchten.
1. Aktualisieren Sie `<dox.version>` Eigenschaft in `/dox/dox.installer/pom.xml` Datei Ihres Cloud Service-Git-Codes auf 2022.11.198.
1. Übertragen Sie die Änderungen und führen Sie die Cloud Service-Pipeline aus, um auf die November-Version von AEM Guides as a Cloud Service zu aktualisieren.

## Schritte zum Indizieren des vorhandenen Inhalts (nur bei Versionen vor der AEM Guides as a Cloud Service-Version September)

Führen Sie die folgenden Schritte aus, um den vorhandenen Inhalt zu indizieren und den neuen Text „Suchen und Ersetzen“ auf Zuordnungsebene zu verwenden:

* Ausführen einer POST-Anfrage an den Server (mit korrekter Authentifizierung) - `http://<server:port>/bin/guides/map-find/indexing`.
(Optional) Sie können bestimmte Pfade der Karten übergeben, um sie zu indizieren. Standardmäßig werden alle Karten indiziert || Beispiel : `https://<Server:port>/bin/guides/map-find/indexing?paths=<map_path_in_repository>`)

* Die API gibt eine jobId zurück. Um den Status des Auftrags zu überprüfen, können Sie eine GET-Anfrage mit Auftrags-ID an denselben Endpunkt senden - `http://<server:port>/bin/guides/map-find/indexing?jobId={jobId}`
(Beispiel: http://&lt;_localhost:8080_>/bin/guides/map-find/indexing?jobId=2022/9/15/7/27/7dfa1271-981e-4617-b5a4-c18379f11c42_678)

* Sobald der Vorgang abgeschlossen ist, antwortet die obige GET-Anfrage mit Erfolg und gibt an, ob Zuordnungen fehlgeschlagen sind. Die erfolgreich indizierten Zuordnungen können aus den Serverprotokollen bestätigt werden.

## Kompatibilitätsmatrix

In diesem Abschnitt finden Sie die Kompatibilitätsmatrix für die Softwareanwendungen, die von AEM Guides as a Cloud Service Version November 2022 unterstützt werden.

### FrameMaker und FrameMaker Publishing Server

| FMPS | FrameMaker |
| --- | --- |
| Nicht kompatibel | Aktualisierung 2020 4 und höher |
| | |

*Die in AEM erstellten Grundlinien und Bedingungen werden ab 2020.2 in FMPS-Versionen unterstützt.

### Sauerstoffanschluss

| AEM Guides as a Cloud Service-Version | Fenster des Sauerstoffanschlusses | Oxygen Connector Mac | In Oxygen Windows bearbeiten | In Oxygen Mac bearbeiten |
| --- | --- | --- | --- | --- |
| 2022.11.0 | 2.7.13 | 2.7.13 | 2,3 | 2,3 |
|  |  |  |  |


## Neue Funktionen und Verbesserungen

AEM Guides as a Cloud Service bietet in der November-Version Verbesserungen und neue Funktionen:


### Löschen von Dateien aus dem Repository-Bedienfeld

Jetzt können Sie Dateien (jeweils nur eine Datei) einfach über das Menü **Optionen** der ausgewählten Datei im Repository-Bereich löschen.
<img src="assets/repository-delete-file.png" alt="Aus Repository löschen" width="500">

Vor dem Löschen der Datei wird eine Bestätigungsaufforderung angezeigt. Wenn keine andere Datei auf die Datei verweist, wird sie gelöscht und eine Erfolgsmeldung wird angezeigt.

Wenn die ausgewählte Datei ausgecheckt ist, kann sie nicht gelöscht werden, und es wird eine Fehlermeldung angezeigt. Wenn die ausgewählte Datei zu einer Favoritensammlung hinzugefügt oder von einer anderen Datei referenziert wird, sucht AEM Guides nach Ihrer Bestätigung und gibt Ihnen die Möglichkeit, sie zwangsweise zu löschen. Wenn Sie ein referenziertes Thema löschen und die Datei mit Verweisen zur Bearbeitung geöffnet haben, wird der fehlerhafte Link für die referenzierte Datei angezeigt.

**Hinweis**: Sie können die ausgewählte Datei auch mithilfe der Löschen -Taste der Tastatur löschen.


### Bereinigen ausgewählter Versionen von Dateien

Wenn Sie Ihre Inhalte erstellen und verwalten, werden möglicherweise viele Versionen für Ihre DITA-Dateien in Ihrem Repository erstellt. Mit AEM Guides können Sie ältere Versionen Ihrer DITA-Dateien aus dem Repository bereinigen und Speicherplatz freigeben.

<img src="assets/preview-purge-report.png" alt="Vorschau des Bereinigungsberichts" width="500">


AEM Guides löscht nicht die erste Version der Datei oder eine Version, die in einer Baseline enthalten ist, oder auf die eine Kennzeichnung angewendet wurde. Der Bereinigungsvorgang löscht nicht einmal Dateien, die in einer Übersetzung oder einem Überprüfungs-Workflow enthalten sind. Sie können die Anzahl der beizubehaltenden Versionen auswählen und auch die Dateien löschen, die älter als die definierte Anzahl von Tagen sind.

Vor Beginn des Bereinigungsvorgangs können Sie eine Vorschau des Berichts anzeigen, um die Versionen anzuzeigen, die bereinigt werden sollen. Sie können dann den Bereinigungsvorgang starten oder abbrechen.

<img src="assets/download-purge-report.png" alt="PDownload-Bereinigungsbericht" width="500">

Sobald der Bereinigungsvorgang abgeschlossen ist, können Sie den Bereinigungsbericht überprüfen, um die bereinigten Dateien anzuzeigen.

### Verwalten von globalen und Ordnerprofil-Ausgabevorgaben

AEM Guides bietet die Funktion zum Erstellen und Verwalten von Ausgabevoreinstellungen für die globalen Profile und Ordnerprofile. Anschließend können Sie diese Ausgabevorgaben einfach verwenden, um eine Ausgabe für alle Zuordnungen zu generieren, die mit diesem globalen Profil oder Ordnerprofil verknüpft sind.

<img src="assets/add-global-output-preset.png" alt="Globales Profil hinzufügen" width="400">

**Hinweis** Nur Benutzer mit Administratorrechten auf Ordnerebene können globale Vorgaben und Ordnerprofilvorgaben erstellen.

Diese globalen Vorgaben werden auf der Registerkarte **Ausgabe** aller zugehörigen Zuordnungen angezeigt. Sie können sie verwenden, um die Ausgabe für alle zugehörigen Zuordnungen zu generieren. Sie können die Vorgabe als Standard-PDF-Vorgabe auswählen, um die PDF-Ausgabe zu generieren. Sie können auch **Bearbeiten**, **Umbenennen**, **Duplizieren** oder **Löschen** eine vorhandene Ausgabevorgabe aus dem Menü **Optionen**.

### Dem Übersetzungs-Dashboard hinzugefügte Spalte „Versionsbezeichnung“

Im Übersetzungs-Dashboard wird auch die Spalte Versionsbezeichnung angezeigt. Dadurch wird der Titel für die ausgewählte Version der Quelldatei angezeigt. Auf diese Weise können Sie alle Dateien mit einem bestimmten Titel auswählen und in einem Schritt übersetzen.

<img src="assets/send-translation.png" alt="Zur Übersetzung senden" width="600">


### Native PDF | PDF mit Änderungsleiste, die den Unterschied zwischen Dokumentversionen anzeigt

Jetzt können Sie mit der Änderungsleiste eine PDF erstellen, die die Inhaltsunterschiede zwischen zwei Versionen anzeigt. Sie können die aktuelle Version mit einer Baseline der vorherigen Version vergleichen oder zwischen den beiden ausgewählten Baseline-Versionen vergleichen.

<img src="assets/pdf-change-version.png" alt="spdf-change-version" width="600">

Auf der PDF wird eine Änderungsleiste angezeigt, die den geänderten, eingefügten oder gelöschten Inhalt angibt. Sie haben außerdem die Möglichkeit, Folgendes durchzuführen:
* Den eingefügten Inhalt grün und unterstrichen anzeigen
* Gelöschte Inhalte in roter Farbe anzeigen und mit einem Durchgestrichen markieren

### Native PDF | Variablenunterstützung für Ausgabepfad und PDF-Dateiname

Jetzt können Sie auch die folgenden vordefinierten Variablen verwenden, um den Ausgabepfad und die PDF-Datei zu definieren. Sie können eine einzelne oder eine Kombination von Variablen verwenden, um diese Optionen zu definieren:
* `${map_filename}`
* `${map_title}`
* `${preset_name}`
* `${language_code}`
* `${map_parentpath}` (nur für Ausgabepfad)
* `${path_after_langfolder}` (nur für Ausgabepfad)


### Native PDF | Inhaltsverzeichnis für DITA-Zuordnungen generieren und Seiten-Layouts neu anordnen

Jetzt können Sie das Inhaltsverzeichnis auch in DITA-Zuordnungen generieren, indem Sie eine erweiterte PDF-Einstellung der Vorlage verwenden. Sie können die Anzeige der verschiedenen Seiten-Layouts aktivieren oder deaktivieren und auch ihre Position neu anordnen.

## Behobene Probleme

Die in verschiedenen Bereichen behobenen Fehler sind unten aufgeführt:

* Native PDF | `conkeyref` wird in der erzeugten PDF-Ausgabe nicht aufgelöst. 10564)
* Native PDF | Probleme treten beim Zugriff auf Metadaten einer Zuordnung in der PDF-Ausgabe auf. 10556)
* Native PDF | Inline-Stile werden zum Generieren von Tags anstelle des Klassennamens verwendet.  10498)
* Der Web-Editor lädt gelegentlich leere Seiten. 10678)
* Das PDF-Veröffentlichen schlägt fehl, wenn eine Vorgabe durch Duplizieren einer vorhandenen Vorgabe erstellt wird. 10584)
* **Protokoll anzeigen**-Taste funktioniert nicht, wenn die PDF-Generierung für eine Voreinstellung fehlschlägt. 10576)
* Beachten Sie, dass in einem para-Tag, das ein conf ist, nicht in der Vorschau angezeigt wird. 10559)
* Durch Drücken der Rücktaste am Ende eines Listenelements wird die gesamte Liste entfernt. 10540)
* Bei der Verwendung eines nativen PDF-Exports werden die verschachtelten `<indexterm>` nicht im Index verschachtelt. 10521)
* **Schaltfläche &quot;** Einrücken“ in der Symbolleiste fehlt in der Source-Ansicht. 10448)
* Das erste Zeichen eines Listenelements geht verloren, während die Liste im Editor erstellt wird. 10447)
* Wenn eine DITA-Asset-Version geändert und im Baseline-Bearbeitungsfenster gespeichert wird, werden mehrere Popup-Fenster angezeigt. 10399)
* Der Anwendungsfehler tritt beim Klicken auf **Bearbeiten**-Schaltfläche auf, nachdem alle Ausgabevorgaben im Bedienfeld „Schnellgenerierung“ ausgewählt wurden. 10388)
* Benutzerdefinierte Metadaten für DITA-Themen werden nicht beibehalten, wenn über die Assets-Benutzeroberfläche eine Einfügeaktion zum Kopieren ausgeführt wird. 10367)
* Die Nachbearbeitung ist für den gesamten Sprachordner blockiert, dessen Assets in einem aktiven Übersetzungsprojekt vorhanden sind. 10332)
* Die Registerkarte „Vorlage“ im XML-Editor ist für Ordnerprofiladministratoren nicht sichtbar. 10266)
* Navigationsprobleme treten im Web-Editor nach dem Upgrade auf 4.0 auf. 10159)
* SVG-Dateien werden im Vorschaumodus nicht angezeigt. 10010)
* Wenn die Registerkarte „Ausgabe“ des Editors mehr Vorgaben enthält, kann der Abschnitt „Vorgaben“ nicht gescrollt werden und alle Vorgaben werden nicht angezeigt. (9 787)
* **Bearbeiten** und **Anmerken**-Optionen für ein Bild funktionieren in der Spaltenansicht nicht ordnungsgemäß. (8 758)
* Der Peer-Link wird nicht aufgelöst und in der generierten Ausgabe als normaler Text angezeigt. (7774)
