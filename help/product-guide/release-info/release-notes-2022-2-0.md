---
title: Versionshinweise für  [!DNL AEM Guides], Version Februar 2022
description: Februar-Version von [!DNL Adobe Experience Manager Guides] as a Cloud Service
exl-id: eb7ff475-bb5b-4d32-b291-024147fbfed1
feature: Release Notes
role: Leader
source-git-commit: 6d8c01f20f7b59fed92c404561b647d9ebecb050
workflow-type: tm+mt
source-wordcount: '974'
ht-degree: 0%

---

# Februar-Version von [!DNL Adobe Experience Manager Guides] as a Cloud Service

## Aktualisierung auf die Februarversion

Führen Sie die folgenden Schritte aus, um das aktuelle Setup für [!DNL Adobe Experience Manager Guides] as a Cloud Service (später als [!DNL AEM Guides] as a Cloud Service bezeichnet) zu aktualisieren:
1. Sehen Sie sich den Git-Code des Cloud Service an und wechseln Sie zu der Verzweigung, die in der Cloud Service-Pipeline entsprechend der Umgebung konfiguriert ist, die Sie aktualisieren möchten.
1. Aktualisieren Sie die Eigenschaft `<dox.version>` in der Datei `/dox/dox.installer/pom.xml` Ihres Cloud Service-Git-Codes auf 2022.2.114.
1. Übertragen Sie die Änderungen und führen Sie die Cloud Service-Pipeline aus, um auf die Februar-Version von [!DNL AEM Guides] as a Cloud Service zu aktualisieren.

## Kompatibilitätsmatrix

In diesem Abschnitt wird die Kompatibilitätsmatrix für die Softwareanwendungen aufgelistet, die von der Version vom [!DNL AEM Guides] as a Cloud Service vom Februar 2022 unterstützt werden.

### FrameMaker und FrameMaker Publishing Server

| FMPS | FrameMaker |
| --- | --- |
| Nicht kompatibel | Aktualisierung 4 und höher für 2020 |
| | |


### Sauerstoffanschluss

| [!DNL AEM Guides] Cloud-Version | Sauerstoff Connector Windows | Sauerstoff Connector Mac |
| --- | --- | --- |
| 2022.2.0 | 2.4.0 | 2.4.0 |
|  |  |  |


## Neue Funktionen und Verbesserungen

### Native PDF-Veröffentlichung

Auch die Erstellung einer nativen PDF wird in der Februar-Version von [!DNL AEM Guides] as a Cloud Service unterstützt. Eine neue Publishing-Engine wurde mit den folgenden Funktionen eingeführt:
* Erstellen einer CSS-Vorlage
* Erstellen verschiedener Seitenvorlagen
* Design-PDF-Vorlagen mit CSS- und Seitenvorlagen
* Publish-Mapping und Themeninhalt im PDF-Format

### Unterstützung für den Knowledgebase-Site-Pfad in der artikelbasierten Veröffentlichung

[!DNL AEM Guides] as a Cloud Service bietet die Funktion zum artikelbasierten Veröffentlichen, um schrittweise eine Ausgabe eines oder mehrerer Themen zu generieren oder Ihre Inhalte auf einer Knowledgebase-Plattform zu veröffentlichen. Mit der Februarversion haben Sie eine zusätzliche Option, den Knowledgebase-Site-Pfad auszuwählen, zu dem das Thema/die Map veröffentlicht werden muss. Nachdem Sie den Pfad ausgewählt haben, wird die Ausgabe am angegebenen Pfad generiert.

### Verbesserungen am Webeditor

Im Web-Editor wurden viele Verbesserungen und neue Funktionen hinzugefügt:

* **Verbessertes Dialogfeld beim Schließen einer Datei**

[!DNL AEM Guides] as a Cloud Service fordert Sie auf, Ihre Änderungen zu speichern und Ihre gesperrten Dateien zu entsperren, wenn Sie versuchen, eine im Web Editor geöffnete Datei zu schließen. Die Eingabeaufforderungen werden basierend auf den von Ihrem Administrator konfigurierten Einstellungen **Check-in beim Schließen verlangen** und **Fragen Sie nach einer neuen Version bei Schließen** .

Basierend auf der Konfiguration erhalten Sie die Option, die Änderungen zu speichern und eine neue Version Ihres Dokuments zu erstellen. Sie können auch die Datei einchecken und die Änderungen in der aktuellen Version speichern.

![ File close](assets/file-close-save-changes-unlock.png)

Weitere Informationen finden Sie unter *Szenarien zum Schließen und Speichern von Dateien* im Benutzerhandbuch.

* Der Zeichenpalette wurde ein geschütztes Leerzeichen hinzugefügt.  Ein **geschütztes** Leerzeichen verhindert einen automatischen Zeilenumbruch an einem bestimmten Punkt in einem HTML-Dokument. Der Web Editor unterstützt ein geschütztes Leerzeichen für die Ausgabe AEM Site und HTML5.

* Wenn Sie ein Bild aus dem Web Editor hochladen, wird ein Bestätigungsdialogfeld angezeigt, wenn bereits ein Bild mit demselben Namen vorhanden ist. Sie können entweder beide Dateien - die vorhandene und die neue -Datei - beibehalten oder die vorhandene Datei überschreiben und nur die neue Datei speichern.

* Wenn ein Benutzer eine Datei für Änderungen gesperrt hat, kann ein Administrator die Sperre freigeben und die Datei einchecken. Diese Funktion ist hilfreich, wenn einige Dateien bearbeitet werden müssen, aber von Benutzern gesperrt wurden, die nicht zum Einchecken in der Datei verfügbar sind

### Landkarten-Dashboard

Wenn Sie die DITA-Map herunterladen, wird die Anfrage in die Warteschlange gestellt und Sie erhalten eine Benachrichtigung, sobald die Karte zum Herunterladen bereit ist. Sie können die Zuordnungsdatei sofort herunterladen oder später über den im Posteingang für AEM Benachrichtigungen angegebenen Link herunterladen.

![Map download](assets/download-map-prompt.png)

### Überprüfung

Sie können die Details im Beschreibungsfeld der Prüfungsaufgabe erwähnen und es wird in der an den Validierer gesendeten E-Mail angezeigt.

## Behobene Probleme

Die in verschiedenen Bereichen behobenen Fehler sind unten aufgeführt:

### Artikelbasierte Veröffentlichung

* Bei der artikelbasierten Veröffentlichung werden keine Artikel veröffentlicht, die auf der ausgewählten Grundlinie basieren. (8771)
* DITAVAL-Dateien werden bei der artikelbasierten Veröffentlichung nicht berücksichtigt. (8770)
* Artikelbasierte Veröffentlichung für Salesforce-Profil kann nicht durchgeführt werden, wenn der Datensatztyp FAQ ist und der Artikelfeldinhalt Frage lautet. (8448)
* Artikelbasierte Veröffentlichung für das Salesforce-Profil kann nicht durchgeführt werden, wenn der Datensatztyp manuell ist. 8447)

### Web-Editor

* Das Ziehen und Ablegen einer Bedingung funktioniert in DITA-Themen nicht. (8761)
* Beim Hinzufügen eines Kapitels zu einer Lesekarte über Drag &amp; Drop aus der Favoriten-Ansicht fehlen Attribute. (8746)
* Das Bearbeiten der Eigenschaften eines Bildes (Höhe, Breite) führt zu einem Anwendungsfehler. (8722)
* Beschädigte Links werden nicht im Bedienfeld &quot;Umrisse&quot;in der Quellansicht angezeigt. 8590)
* Der XML-Editor entfernt Zeilenumbruch-Tags in Codeblock. 8522)
* Die Glossnutzung wird bei der Erstellung eines Glossars als Hinweis angezeigt. (8384)
* xref kann nicht selbst an gültigen Stellen eingefügt werden. 8354)
* Die Elementliste (Alt+Eingabetaste) wird im dunklen/dunkelsten Design grau dargestellt. (7913)
* Die Liste der Zuordnungsvorlagen in der Option **Erstellen** (Ellipsenmenü) des Repository-Bedienfelds entspricht nicht dem **Ordnerprofil** in den Benutzereinstellungen. (5918)
* Element-IDs werden nicht automatisch für Elemente generiert, die über die Funktion Inhalt wiederverwenden in der Hauptsymbolleiste hinzugefügt werden. (5826)

### Assets-Benutzeroberfläche

* Die Bildbearbeitung funktioniert auf dem Cloud-Server nicht erwartungsgemäß. (8768)
* Im Bedienfeld Versionsverlauf zeigt der aktuelle Versionsabschnitt einen falschen Zeitstempel an und wurde durch Informationen geändert. (8765)
* Das Hochladen von DITAVAL-Dateien auf den Cloud-Server schlägt fehl, wenn AEM Desktop-Tool verwendet wird. (8707)
* Der zweite Administrator-Benutzer kann nicht als erster Administrator-Benutzer zu einem Ordner hinzugefügt werden. 8430)
* Nicht eindeutige Eigenschaften eines Assets werden beim Kopieren und Einfügen des Assets nicht kopiert. (8241)

### Nutzungsänderungen

* Wenn ein Benutzername lang ist, werden die Symbole, die angenommen/abgelehnt werden, im Überprüfungsfenster des Web Editors nicht klar angezeigt. (8793)
* Im Bedienfeld **Suchen und Ersetzen** wird ein unerwünschtes Symbol angezeigt, wenn Sie den Mauszeiger im Ergebnisabschnitt bewegen. (8775)
* Das benutzerdefinierte Symbol wird nicht aus der Eigenschaft ausgewählt und stattdessen wird das Standardsymbol für die Berichte angezeigt, die mit der Schaltfläche Bericht generieren generiert wurden. (8573)
