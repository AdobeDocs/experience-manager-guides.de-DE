---
title: Versionshinweise zu | Neue Funktionen in der Adobe Experience Manager Guides, Version vom November 2023
description: Erfahren Sie mehr über die neuen und erweiterten Funktionen der Version November 2023 von Adobe Experience Manager Guides as a Cloud Service.
exl-id: 83c04e01-92f1-41b0-8866-a202f4106b51
feature: What's New
role: Leader
source-git-commit: 6d8c01f20f7b59fed92c404561b647d9ebecb050
workflow-type: tm+mt
source-wordcount: '803'
ht-degree: 0%

---

# Neue Funktionen in der Adobe Experience Manager Guides as a Cloud Service-Version vom November 2023

Dieser Artikel behandelt die neuen und erweiterten Funktionen in der Version vom November 2023 von Adobe Experience Manager Guides (später als *Experience Manager Guides as a Cloud Service* bezeichnet).

Weitere Informationen zu den Upgrade-Anweisungen, der Kompatibilitätsmatrix und den in dieser Version behobenen Problemen finden Sie in [Versionshinweisen](release-notes-2023-11-0.md).

## Native PDF-Verbesserungen

Die folgenden nativen PDF-Verbesserungen wurden in der Version vom November 2023 vorgenommen:

### Verwenden und Duplizieren von vordefinierten PDF-Vorlagen

Experience Manager Guides bietet vordefinierte oder werkseitige PDF-Vorlagen. Duplizieren Sie die werkseitigen PDF-Vorlagen, um die benutzerdefinierten PDF-Vorlagen zu erstellen.

Jetzt können Sie beim Erstellen und Duplizieren einer Vorlage auch eine Vorschau des Miniaturbilds für eine Vorlage anzeigen. Sie können dieses Bild auch bearbeiten oder löschen. Diese Funktion ist nützlich, um Vorlagen mit ähnlichen Namen zu markieren oder zu unterscheiden.
Weitere Informationen zur [PDF-Vorlage](../native-pdf/pdf-template.md).

![Dialogfeld &quot;PDF-Vorlage duplizieren“](assets/duplicate-template.png){width="550" align="left"}

*Duplizieren Sie eine vorhandene PDF-Vorlage.*


### Ändern der Reihenfolge von Seiten und Veröffentlichen mehrerer Seiten pro Blatt

Neben der Veröffentlichung der Seiten gemäß dem Quelldokument können Sie beim Veröffentlichen eines mehrseitigen Dokuments auch die Seitenreihenfolge beim PDF ändern.  Dadurch haben Sie die Möglichkeit, die Seiten in verschiedenen Reihenfolgen zu veröffentlichen, z. B. alle ungeraden oder alle geraden Seiten zuerst. Sie können auch als Broschüre veröffentlichen und die Seiten wie ein Buch lesen. Sie können auch die Anzahl der Seiten festlegen, die Sie auf einem einzelnen Blatt Papier veröffentlichen möchten. Weitere Informationen finden Sie im Abschnitt [Seitenorganisation](../native-pdf/components-pdf-template.md#page-organization) .

### Sortieren von Glossarbegriffen basierend auf Sortierschlüsseln

Jetzt können Sie die Glossarbegriffe auch anhand von Sortierschlüsseln sortieren. Sie können das Tag „sort-as“ verwenden, um einen Sortierschlüssel für die Glossarbegriffe zu definieren. Anschließend können Sie sie anhand von Sortierschlüsseln anstelle der Begriffe sortieren. Auf diese Weise können Sie die Glossarbegriffe nach den in verschiedenen Sprachen verwendeten Begriffen sortieren. Sie können auch einen einzelnen Sortierschlüssel für einen Glossarbegriff mit einer Phrase oder einer Gruppe von Wörtern definieren.
Weitere Informationen finden Sie unter [Erweiterte PDF-Einstellungen](../native-pdf/components-pdf-template.md#advanced-pdf-settings).


### Verbessertes Ressourcenmanagement für native PDF-Vorlagen

Experience Manager Guides hat jetzt die Ressourcenverwaltung für native PDF-Vorlagen verbessert. Sie können jetzt Ressourcen wie Bilder, CSS-Dateien und Schriftarten-Dateien über mehrere native PDF-Vorlagen hinweg freigeben und wiederverwenden. Mit dieser Verbesserung ist die Verwaltung der Ressourcen für einen großen Satz von Vorlagen viel einfacher. Sie müssen nicht für jede Vorlage doppelte Ressourcen erstellen. Sie können diese in einem freigegebenen Ordner speichern und in allen nativen PDF-Vorlagen verwenden.
Weitere Informationen finden Sie unter [PDF-Vorlage](../native-pdf/pdf-template.md).

## Verbesserungen am Web-Editor

In der Version vom November 2023 wurden die folgenden Verbesserungen am Web-Editor vorgenommen:


### Dateien nach Titel oder Dateinamen anzeigen

Sie können jetzt die Standardmethode zum Anzeigen der Dateien im Web-Editor auswählen. Sie können die Liste der Dateien anhand der Titel oder der Dateinamen aus den verschiedenen Bedienfeldern in der Autorenansicht anzeigen.

![Dialogfeld „Benutzereinstellungen“](assets/user-preferences-2311.png){width="550" align="left"}

*Ändern Sie die Standardeinstellung zum Anzeigen der Dateien im Dialogfeld **Benutzereinstellungen**.*


### Verwalten von Bedingungsvorgaben

Sie können Bedingungsattribute in Ihren DITA-Themen definieren. Verwenden Sie dann die Bedingungsattribute in der Bedingungsvorgabe, um den Inhalt in einer DITA-Zuordnung zu veröffentlichen. Mit Experience Manager Guides können Sie jetzt auch Bedingungsvorgaben über den Web-Editor erstellen und verwalten. Sie können sie auch einfach bearbeiten, duplizieren oder löschen.

![Bedingungsvorgaben auf der Registerkarte Verwalten des Web-Editors &#x200B;](assets/web-editor-manage-condition-presets.png){width="550" align="left"}

Weitere Informationen finden Sie unter [Verwenden von Bedingungsvorgaben](../user-guide/generate-output-use-condition-presets.md).

### Wiederherstellen von Dateiregisterkarten beim Aktualisieren des Browsers

Experience Manager Guides stellt den Status der geöffneten Dateiregisterkarten im Web-Editor wieder her, wenn Sie den Browser aktualisieren. Weitere Informationen finden Sie im Abschnitt **Browser beim Bearbeiten der Dateien aktualisieren** unter [Themen im Web-Editor bearbeiten](../user-guide/web-editor-edit-topics.md).

### Einfaches Entpacken eines Elements

Jetzt können Sie ein Element mithilfe der Option aus dem Kontextmenü eines Elements im Web-Editor einfach entpacken. Auf diese Weise können Sie den Text des Elements einfach mit dem übergeordneten Element zusammenführen.
Weitere Informationen finden Sie im Abschnitt **Element entpacken** unter &quot;[&#x200B; Funktionen im Web-Editor](../user-guide/web-editor-other-features.md).

### Tastaturbefehle zum Verschieben des Cursors

Experience Manager Guides ermöglicht jetzt auch die Verwendung von Tastaturbefehlen zum Verschieben des Cursors im Web-Editor. Sie können die Tastaturbefehle verwenden, um ein Wort schnell nach links oder rechts zu verschieben. Sie können auch mithilfe der Tastaturbefehle zum Anfang oder Ende der Zeile wechseln.
Jetzt können Sie auch Tastaturbefehle verwenden, um den Cursor an den Anfang des nächsten Elements oder an das Ende des vorherigen Elements zu verschieben.
Erfahren Sie mehr über [Tastaturbefehle im Web-Editor](../user-guide/web-editor-keyboard-shortcuts.md).
