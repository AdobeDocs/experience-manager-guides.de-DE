---
title: Versionshinweise | Adobe Experience Manager Guides as a Cloud Service, Version September 2022
description: September-Version von Adobe Experience Manager Guides as a Cloud Service
exl-id: f6247f91-43cc-43a4-a6f8-3b1f09d0533f
feature: Release Notes
role: Leader
TQID: https://experienceleague.adobe.com/vzzg-FlQ0IsMKzYDYcIJjh9hGRnuzV-tiuMa7tvO85o
product_v2: id: fae5e35a-80c9-4b94-9352-1a060a6aab1did: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2: id: a3bd6397-2eb2-4908-a61c-226e26855dcaid: afb45297-4313-4f67-818e-bc0b03abe086
subfeature_v2: id: d5ea0417-7932-4688-a3e2-4d3b2e7076a3
role_v2: id: f8a45b24-4be7-4f1b-909b-60d06b483a20
topic_v2: id: a004cc84-67b9-4a33-a3a7-8ec7273ef4dc
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 1300
ht-degree: 3%

---

# September-Version von Adobe Experience Manager Guides as a Cloud Service

## Upgrade auf die Version September

Führen Sie ein Upgrade Ihres aktuellen Adobe Experience Manager Guides as a Cloud Service-Setups (später als *AEM Guides as a Cloud Service* bezeichnet) durch, indem Sie die folgenden Schritte ausführen:
1. Checken Sie den Git-Code der Cloud Services aus und wechseln Sie zu der Verzweigung, die in der Cloud Services-Pipeline konfiguriert ist und der Umgebung entspricht, die Sie aktualisieren möchten.
1. Aktualisieren Sie `<dox.version>` Eigenschaft in `/dox/dox.installer/pom.xml` Datei Ihres Cloud Services-Git-Codes auf 2022.9.178.
1. Übernehmen Sie die Änderungen und führen Sie die Cloud Services-Pipeline aus, um auf die Version September von AEM Guides as a Cloud Service zu aktualisieren.

## Schritte zum Indizieren des vorhandenen Inhalts

Führen Sie die folgenden Schritte aus, um den vorhandenen Inhalt zu indizieren und den neuen Text „Suchen und Ersetzen“ auf Zuordnungsebene zu verwenden:
* Ausführen einer POST-Anfrage an den Server (mit korrekter Authentifizierung) - `http://<server:port>/bin/guides/map-find/indexin`.
(Optional: Sie können bestimmte Pfade der Zuordnungen übergeben, um sie zu indizieren. Standardmäßig werden alle Zuordnungen indiziert. | Beispiel: `https://<Server:port>/bin/guides/map-find/indexing?paths=<map_path_in_repository>`)
* Die API gibt eine jobId zurück. Um den Auftragsstatus zu überprüfen, können Sie eine GET-Anfrage mit Auftrags-ID an denselben Endpunkt senden - `http://<server:port>/bin/guides/map-find/indexing?jobId={jobId}`
(Beispiel: `http://<_localhost:8080_>/bin/guides/map-find/indexing?jobId=2022/9/15/7/27/7dfa1271-981e-4617-b5a4-c18379f11c42_678)`
* Sobald der Vorgang abgeschlossen ist, wird die obige GET-Anfrage erfolgreich beantwortet und es wird angegeben, ob Zuordnungen fehlgeschlagen sind. Die erfolgreich indizierten Zuordnungen können aus den Serverprotokollen bestätigt werden.


## Kompatibilitätsmatrix

In diesem Abschnitt finden Sie die Kompatibilitätsmatrix für die Softwareanwendungen, die von AEM Guides as a Cloud Service Version September 2022 unterstützt werden.

### FrameMaker und FrameMaker Publishing Server

| FMPS | FrameMaker |
| --- | --- |
| Nicht kompatibel | Aktualisierung 2020 4 und höher |
| | |

*Die in AEM erstellten Grundlinien und Bedingungen werden ab 2020.2 in FMPS-Versionen unterstützt.

### Sauerstoffanschluss

| AEM Guides as a Cloud Service-Version | Fenster des Sauerstoffanschlusses | Oxygen Connector Mac | In Oxygen Windows bearbeiten | In Oxygen Mac bearbeiten |
| --- | --- | --- | --- | --- |
| 2022.9.0 | 2.7.13 | 2.7.13 | 2,3 | 2,3 |
|  |  |  |  |  |


## Neue Funktionen und Verbesserungen

AEM Guides as a Cloud Service bietet in der September-Version viele Verbesserungen und neue Funktionen:


### Erstellen einer dynamischen Baseline basierend auf Kennzeichnungen

Jetzt bietet AEM Guides die Funktion, dynamische Baselines basierend auf Beschriftungen zu erstellen. Wenn Sie eine Baseline generieren, eine Baseline herunterladen oder ein Übersetzungsprojekt mithilfe einer Baseline erstellen, werden die Dateien basierend auf den aktualisierten Beschriftungen dynamisch ausgewählt. Diese Funktion ist praktisch, da Sie die Grundlinie beim Aktualisieren der Kennzeichnungen nicht ändern müssen.
Sie können auch den Snapshot der Baseline als CSV exportieren.

![Baselines erstellen](assets/dynamic-baseline.png)

### Suchen und Ersetzen des Textes auf Kartenebene

Sie können jetzt in einer Zuordnung nach Dateien suchen, die bestimmten Text enthalten. Der gesuchte Text wird in den Dateien hervorgehoben. Sie können das gesuchte Wort oder die gesuchte Wortgruppe in den Dateien auch durch ein anderes Wort oder eine andere Wortgruppe ersetzen.
Wählen Sie das Symbol **Ersetzen**, um das aktuelle Vorkommen zu ersetzen, und das Symbol **Alle in Datei ersetzen**, um alle Vorkommen in der ausgewählten Datei zu ersetzen.

![Ersetzen in Karte suchen](assets/map-find-replace.png)

Standardmäßig sind die Optionen **Datei vor dem Ersetzen auschecken** und **Neue Version nach dem Ersetzen erstellen** ausgewählt, sodass eine Datei ausgecheckt wird, bevor Sie den Text ersetzen, und eine neue Version erstellt wird, nachdem der Text ersetzt wurde.

### Anzeigen von Versionsunterschieden bei Dateien mit unzureichender Synchronisierung im Übersetzungs-Dashboard

Sie können jetzt die **Nicht synchron)-Dateien** den Änderungen übersetzen, die zwischen den beiden Versionen eines Themas vorgenommen wurden.\
![Übersetzungs-Dashboard](assets/translation-version-diff.png)
Im Übersetzungs-Dashboard können Sie die Unterschiede zwischen der zuletzt übersetzten Version und der aktuellen Version der ausgewählten Datei leicht erkennen.

![Dialogfeld Versionsunterschied](assets/version-diff.png)

Basierend auf den Unterschieden können Sie entscheiden, ob Sie ein Thema übersetzen möchten oder nicht.

### Für PDF-Vorgaben verfügbare Metadaten-Benutzeroberfläche

Sie können die Metadaten aus der Ausgabevorgabe einer DITA-Zuordnung festlegen. Sie können die Metadaten für Titel, Autor, Betreff und Keywords festlegen. Diese Metadaten werden den Metadaten in den Dateieigenschaften Ihrer Ausgabe-PDF zugeordnet.
Diese Metadaten setzen die auf Buchebene definierten Metadaten außer Kraft. Sie können die Metadaten in jeder Ausgabevorgabe spezifisch definieren und an die Ausgabe-PDF übergeben.

![Metadaten in Voreinstellung](assets/preset-metadata.png)


## Behobene Probleme

Die in verschiedenen Bereichen behobenen Fehler sind unten aufgeführt:

* Web-Editor | Beim Verschieben von Elementen innerhalb eines Themas werden die zugewiesenen IDs für Elemente durch automatisch zugewiesene IDs überschrieben. (7895)
* Änderungen verfolgen | Inhalt geht verloren, wenn ein neues Element mit der Eingabetaste eingegeben wird. (10246)
* Die Unterzuordnung, die auf die Hauptzuordnung in „dita-templates“ verweist, wird nicht erstellt. (10231)
* Der XML-Editor | Kopieren/Einfügen funktioniert nicht im Autorenmodus. (10309)
* Wenn mehrere Versionsbezeichnungen ausgewählt sind, wird die Auswahl nicht aufgehoben. (9561)
* Die automatische Navigation zum Pfad im Dialogfeld zum Durchsuchen der Site funktioniert nicht wie das Durchsuchen der Datei. (9920)
* Das Gliederungsbedienfeld zeigt beim Wechsel vom **Author**- in den **Source** Modus keine Inhalte an. (10319)
* Inhalte in einem neuen Thema, die mit einem Inhalt in der Themenvorlage erstellt wurden, funktionieren nicht. Die kopierte Hash-ID wird in der Inhaltskopie nicht aktualisiert. (9890)
* Web-Editor | Beim Erstellen einer Zuordnung aus der Zuordnungsvorlage ist kein Ladeprogramm vorhanden. (9891)
* Neuer Zuordnungs-Editor | Fett- oder Kursiv im Zuordnungstitel hinzugefügter Text wird nicht beibehalten, wenn wir von **Autor** zur **Layout** Ansicht wechseln. (10218)
* Neuer Zuordnungs-Editor | Bedingungen, die auf Verweise angewendet werden, können nicht aus der Layout-Ansicht entfernt werden. (10213)
* Der neue Zuordnungs-Editor | Anwenden von Bedingungsreferenzen funktioniert in der Layout-Ansicht nicht wie in der Authoring-Ansicht. (10198)
* Neuer Zuordnungs-Editor | Nach links aus dem Kontextmenü verschieben : Entfernt den Verweis, wenn er nicht nach links verschoben werden kann. (10219)
* Neuer Zuordnungs-Editor |Das Symbol wird für die Verweise in einer mithilfe der Layout-Ansicht erstellten Zuordnung falsch angezeigt. (10197)
* Repository-Bedienfeld | Mit einem Rechtsklick im Repository-Bedienfeld wird ein Anwendungsfehler angezeigt. (10123)
* Suchen und Ersetzen | Der Dunkle Modus ist für Suchergebnisse im Web-Editor nicht lesbar. (9978)
* Übersetzung | Metadaten und Tags werden nicht an die übersetzten Kopien weitergegeben. (4696)
* Beim Kopieren und Einfügen (Strg+C/Strg+V) des Inhalts wird im Autorenmodus ein Fehler ausgegeben. (10304)
* PDF-Vorlage | Beim Hinzufügen von Hintergrundbildern zu einem Seitenlayout wird der absolute Bildpfad angezeigt, und die Bilder werden nicht in der Ausgabe-PDF angezeigt. (10297)
* Native PDF | Kapiteltitel und Kapitelüberschrift funktionieren in der PDF-Veröffentlichung nicht. (9947)
* Das native PDF | `xref` für ein Konzept wurde für ein bestimmtes DITA-Thema nicht korrekt aufgelöst. (10229)
* Nativer PDF | Beschriftungstext für eine Tabelle kann in der generierten PDF-Ausgabe nicht angezeigt werden. (9827)
* Native PDF | Verweise in Anhängen werden in der PDF-Ausgabe nicht als Anhänge angezeigt. (10182)
* Das native PDF | Frame-Attribut für eine Tabelle wird nicht an die temporäre HTML weitergegeben (als Klasse). (10353)
* Native PDF | temporäre HTML-Dateien fügen die Klassen „closep“ und „rowsep“ zu td und th hinzu, selbst wenn ihr Wert in der Quell-DITA 0 ist. (10352)
* Native PDF | Metadaten für im Seiten-Layout hinzugefügtes Zertifikat werden nicht berücksichtigt. (10377)
* Native PDF | Generierung von PDF schlägt für bestimmte Inhalte fehl. (9927)
* Native PDF | Inhalte über conkeyref werden in der PDF-Ausgabe nicht angezeigt. (9836)
* Native PDF | Die wichtigsten Referenzen für Keydefs mit Bildern oder externen Links werden nicht aufgelöst. (10063)
* In der Autorenansicht für eine Zuordnung wird kein Platzhaltertext für die Tabellen- und Abbildliste angezeigt. (10330)
* Beim Erstellen einer neuen Baseline wird der bereits ausgewählte Baseline-Filter nicht angewendet. (9954)
* Videodatei fehlt in der Grundlinie, wenn der Name des übergeordneten Ordners ein Leerzeichen enthält. 10031)
* Bei der Basiserstellung wird nicht die neueste Version ausgewählt, wenn sich die Zeitzone des Benutzers von der Zeitzone des Servers unterscheidet. (10190)
* Die Tastenkombination Strg + F öffnet das Browser-Suchmodal in der Assets-Konsole nach der Installation von AEM Guides 4.1 in AEM 6.5.12 nicht. (10189)


## Bekannte Probleme

Adobe hat die folgenden bekannten Probleme in AEM Guides as a Cloud Service Version September 2022 identifiziert.


* Dynamische Baseline ist nicht in die Veröffentlichung der Wissensdatenbank integriert.

* Das Symbol Übersetzung | Versionsdifferenz wird für den Quellinhalt aufgrund einer Änderung am Zielinhalt angezeigt.
