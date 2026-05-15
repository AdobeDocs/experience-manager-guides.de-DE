---
title: Versionshinweise für [!DNL AEM Guides], Februar 2022
description: Februarversion von  [!DNL Adobe Experience Manager Guides] as a Cloud Service
exl-id: eb7ff475-bb5b-4d32-b291-024147fbfed1
feature: Release Notes
role: Leader
TQID: https://experienceleague.adobe.com/QdLQIO8X1Lkj3iwoJAUQ-ENujxT-n7y5gGlI-gQz-IE
product_v2: id: fae5e35a-80c9-4b94-9352-1a060a6aab1did: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2: id: a3bd6397-2eb2-4908-a61c-226e26855dcaid: afb45297-4313-4f67-818e-bc0b03abe086id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0eid: d90290ec-3e61-4ebd-8649-bcafe0836803
subfeature_v2: id: d5ea0417-7932-4688-a3e2-4d3b2e7076a3id: d6596f3f-92a7-43ec-b444-237db6adad05
role_v2: id: f8a45b24-4be7-4f1b-909b-60d06b483a20
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 982
ht-degree: 2%

---

# Februarversion von [!DNL Adobe Experience Manager Guides] as a Cloud Service

## Upgrade auf die Februarversion

Führen Sie ein Upgrade Ihres aktuellen [!DNL Adobe Experience Manager Guides] as a Cloud Service-Setups (später [!DNL AEM Guides] as a Cloud Service bezeichnet) durch, indem Sie die folgenden Schritte ausführen:
1. Checken Sie den Git-Code der Cloud Services aus und wechseln Sie zu der Verzweigung, die in der Cloud Services-Pipeline konfiguriert ist und der Umgebung entspricht, die Sie aktualisieren möchten.
1. Aktualisieren Sie `<dox.version>` Eigenschaft in `/dox/dox.installer/pom.xml` Datei Ihres Cloud Services-Git-Codes auf Version 2022.2.114.
1. Übertragen Sie die Änderungen und führen Sie die Cloud Services-Pipeline aus, um auf die Februarversion von [!DNL AEM Guides] as a Cloud Service zu aktualisieren.

## Kompatibilitätsmatrix

In diesem Abschnitt finden Sie die Kompatibilitätsmatrix für die Softwareanwendungen, die von [!DNL AEM Guides] as a Cloud Service-Version Februar 2022 unterstützt werden.

### FrameMaker und FrameMaker Publishing Server

| FMPS | FrameMaker |
| --- | --- |
| Nicht kompatibel | Aktualisierung 2020 4 und höher |
| | |


### Sauerstoffanschluss

| [!DNL AEM Guides] Cloud-Version | Fenster des Sauerstoffanschlusses | Oxygen Connector Mac |
| --- | --- | --- |
| 2022.2.0 | 2.4.0 | 2.4.0 |
|  |  |  |


## Neue Funktionen und Verbesserungen

### Native PDF-Veröffentlichung

Die Erstellung eines nativen PDF wird seit der Februarversion von [!DNL AEM Guides] as a Cloud Service ebenfalls unterstützt. Eine neue Publishing-Engine wurde mit den folgenden Funktionen eingeführt:
* Erstellen einer CSS-Vorlage
* Erstellen verschiedener Seitenvorlagen
* Entwerfen von PDF-Vorlagen, die CSS- und Seitenvorlagen enthalten
* Veröffentlichen von Zuordnungs- und Themeninhalten im PDF-Format

### Unterstützung für den Knowledgebase-Site-Pfad in der artikelbasierten Veröffentlichung

[!DNL AEM Guides] as a Cloud Service bietet die Funktion zur artikelbasierten Veröffentlichung, um schrittweise eine Ausgabe eines oder mehrerer Themen zu generieren oder Ihre Inhalte auf einer Wissensdatenbankplattform zu veröffentlichen. Mit der Februarversion haben Sie eine zusätzliche Option, den Pfad der Wissensdatenbank-Website auszuwählen, auf den das Thema/die Karte veröffentlicht werden soll. Nachdem Sie den Pfad ausgewählt haben, wird die Ausgabe unter dem angegebenen Pfad generiert.

### Verbesserungen am Web-Editor

Im Web-Editor wurden viele Verbesserungen und neue Funktionen hinzugefügt:

* **Verbessertes Dialogfeld beim Schließen der Datei**

[!DNL AEM Guides] as a Cloud Service fordert Sie auf, Ihre Änderungen zu speichern und Ihre gesperrten Dateien zu entsperren, wenn Sie versuchen, eine im Web-Editor geöffnete Datei zu schließen. Die Eingabeaufforderungen werden basierend auf den vom Administrator konfigurierten Einstellungen **Einchecken beim Schließen anfragen** und **Beim Schließen nach neuer Version** fragen“ angezeigt.

Je nach Konfiguration haben Sie die Möglichkeit, die Änderungen zu speichern und eine neue Version Ihres Dokuments zu erstellen. Sie können auch die Datei einchecken und die Änderungen an der aktuellen Version speichern.

![Datei schließen](assets/file-close-save-changes-unlock.png)

Weitere Informationen finden Sie unter *Schließen und Speichern von Dateien* im Benutzerhandbuch.

* Der Zeichenpalette wurde ein Leerzeichen ohne Unterbrechung hinzugefügt.  Ein **Leerzeichen verhindert** automatischen Zeilenumbruch an einer bestimmten Stelle in einem HTML-Dokument. Der Web-Editor unterstützt eine unterbrechungsfreie Platzierung für die Ausgabe von AEM Site und HTML5.

* Beim Hochladen eines Bildes aus dem Web-Editor wird ein Bestätigungsdialogfeld angezeigt, wenn bereits ein Bild mit demselben Namen vorhanden ist. Sie können entweder beide Dateien beibehalten - die vorhandene und die neue Datei - oder die vorhandene Datei überschreiben und nur die neue Datei speichern.

* Wenn ein Benutzer eine Datei für die Bearbeitung gesperrt hat, kann ein Administrator die Sperre aufheben und die Datei einchecken. Diese Funktion ist hilfreich, wenn einige Dateien bearbeitet werden müssen, aber von Benutzenden gesperrt wurden, die nicht zum Einchecken der Datei verfügbar sind

### Zuordnungs-Dashboard

Wenn Sie sich dafür entscheiden, die DITA-Karte herunterzuladen, wird die Anfrage in die Warteschlange gestellt und Sie erhalten eine Benachrichtigung, sobald die Karte zum Herunterladen bereit ist. Sie können die Zuordnungsdatei direkt herunterladen oder später über den Link im AEM-Benachrichtigungs-Posteingang herunterladen.

![Map-Download](assets/download-map-prompt.png)

### Überprüfung

Sie können die Details im Beschreibungsfeld der Prüfungsaufgabe angeben, und sie wird in der E-Mail angezeigt, die an den Validierungsverantwortlichen gesendet wird.

## Behobene Probleme

Die in verschiedenen Bereichen behobenen Fehler sind unten aufgeführt:

### Artikelbasierte Veröffentlichung

* Bei der artikelbasierten Veröffentlichung werden Artikel nicht basierend auf der ausgewählten Baseline veröffentlicht. (8771)
* DITAVAL-Dateien werden in der artikelbasierten Veröffentlichung nicht berücksichtigt. (8770)
* Die artikelbasierte Veröffentlichung für das Salesforce-Profil kann nicht durchgeführt werden, wenn der Datensatztyp „Häufig gestellte Fragen“ und der Inhalt des Artikelfelds „Frage“ ist. (8448)
* Die artikelbasierte Veröffentlichung für das Salesforce-Profil kann nicht durchgeführt werden, wenn der Datensatztyp „Manuell“ ist. (8447)

### Web-Editor

* In DITA-Themen funktioniert das Ziehen und Ablegen einer Bedingung nicht. (8761)
* Attribute fehlen beim Hinzufügen eines Kapitels zu einer Bookmap mithilfe von Drag-and-Drop aus der Favoritenansicht. (8746)
* Das Bearbeiten der Eigenschaften eines Bildes (Höhe, Breite) führt zu einem Anwendungsfehler. (8722)
* Beschädigte Links werden nicht im Gliederungsbereich in der Quellansicht angezeigt. (8590)
* Der XML-Editor entfernt das Zeilenumbruch-Tag im Codeblock. (8522)
* Die Verwendung des Glossars wird bei der Erstellung eines Glosseneintrags als Hinweis angezeigt. (8384)
* xref kann auch an gültigen Speicherorten nicht eingefügt werden. (8354)
* Die Elementliste (Alt+Eingabetaste) wird im dunkelsten/dunkelsten Design ausgegraut angezeigt. (7913)
* Die Liste der Zuordnungsvorlagen in **Erstellen** Option (Menü mit Auslassungspunkten) im Repository-Bereich entspricht nicht dem **Ordnerprofil** in den Benutzereinstellungen. (5918)
* Element-IDs werden nicht automatisch für Elemente generiert, die über die Funktion Inhalt wiederverwenden in der Hauptsymbolleiste hinzugefügt wurden. (5826)

### Assets-Benutzeroberfläche

* Die Bildbearbeitung funktioniert auf dem Cloud-Server nicht wie erwartet. (8768)
* Im Bereich Versionsverlauf wird im Abschnitt Aktuelle Version ein falscher Zeitstempel angezeigt und durch Informationen geändert. (8765)
* Der DITAVAL-Datei-Upload auf dem Cloud-Server schlägt fehl, wenn das AEM-Desktop-Tool verwendet wird. (8707)
* Der zweite Administratorbenutzer kann nicht als der erste Administratorbenutzer einem Ordner hinzugefügt werden. (8430)
* Nicht eindeutige Eigenschaften eines Assets werden nicht kopiert, wenn das Asset kopiert und eingefügt wird. (8241)

### Änderungen der Benutzerfreundlichkeit

* Wenn ein Benutzername lang ist, werden im Überprüfungsfenster des Web-Editors die Symbole zum Akzeptieren/Ablehnen nicht deutlich angezeigt. (8793)
* Im Bedienfeld **Suchen und Ersetzen** wird ein unerwünschtes Symbol auf dem Mauszeiger im Ergebnisabschnitt angezeigt. (8775)
* Benutzerdefiniertes Symbol wird nicht aus der Eigenschaft ausgewählt, sondern stattdessen wird das Standardsymbol für die mit der Schaltfläche Bericht generieren generierten Berichte angezeigt. (8573)
