---
title: Versionshinweise | Neue Funktionen in der Adobe Experience Manager Guides-Version 2024.4.0
description: Erfahren Sie mehr über die neuen und verbesserten Funktionen in der Version 2024.4.0 von Adobe Experience Manager Guides as a Cloud Service.
exl-id: e9db535a-5ad5-4ff0-94af-b4425594316a
source-git-commit: 5d99274da8fdacbd255d426fa4913b5773ca45f8
workflow-type: tm+mt
source-wordcount: '1806'
ht-degree: 28%

---

# Neue Funktionen in Version 2024.4.0

Dieser Artikel behandelt die neuen und verbesserten Funktionen der Adobe Experience Manager Guides-Version 2024.4.0.

Eine Liste der in dieser Version behobenen Probleme finden Sie im Artikel [Behobene Probleme in Version 2024.4.0](fixed-issues-2024-04-0.md).

Erfahren Sie mehr über [Upgrade-Anweisungen für Version 2024.4.0](upgrade-instructions-2024-04-0.md).

## Möglichkeit zur Übersetzung von Inhalten in mehrere Sprachen mithilfe vorkonfigurierter Sprachgruppen

In Experience Manager Guides können Sie jetzt Sprachgruppen erstellen und Ihre Inhalte einfach in mehrere Sprachen übersetzen. Mit dieser Funktion können Sie Übersetzungen entsprechend den Anforderungen Ihres Unternehmens organisieren und verwalten.

Wenn Sie beispielsweise Inhalte für einige Länder in Europa übersetzen müssen, können Sie eine Sprachgruppe für europäische Sprachen wie Englisch (EN), Französisch (FR), Deutsch (DE), Spanisch (ES) und Italienisch (IT) erstellen.



![Übersetzungsbedienfeld](assets/translation-languages-2404.png){width="300" align="left"}

*Wählen Sie die Sprachgruppen oder Sprachen aus, die Sie für die Übersetzung Ihrer Dokumente verwenden möchten.*

>[!NOTE]
>
>Wenn der Zielordner einer Sprache fehlt oder die Zielsprache mit der Quelle identisch ist, ist die Sprache ausgegraut und es wird ein Warnsymbol angezeigt.

Als Admin können Sie Sprachgruppen erstellen und diese für mehrere Ordnerprofile konfigurieren. Als Autorin bzw. Autor können Sie die Sprachgruppen anzeigen, die für Ihr Ordnerprofil konfiguriert sind.


Insgesamt verbessert die Erstellung von Sprachgruppen die Effizienz und Produktivität von Übersetzungsprojekten und verbessert damit den Lokalisierungsprozess über mehrere Sprachen hinweg.


Erfahren Sie, wie Sie [Dokumente aus dem Web-Editor übersetzen](../user-guide/translate-documents-web-editor.md).



## Löschen oder deaktivieren Sie das Übersetzungsprojekt automatisch nach der Übersetzung

Als Administrator können Sie jetzt die Übersetzungsprojekte so konfigurieren, dass sie nach Abschluss der Übersetzung automatisch deaktiviert oder gelöscht werden. Diese Funktion hilft Ihnen, Ressourcen effizient zu nutzen und Dateien nach Abschluss der Übersetzung zu verwalten.

Durch das Löschen eines Projekts werden alle im Projekt vorhandenen Dateien und Ordner dauerhaft entfernt. Durch die Löschung der Übersetzungsprojekte können Sie auch den belegten Speicherplatz freigeben.

Sie können die Übersetzungsprojekte deaktivieren, wenn Sie sie später verwenden möchten.

![](assets/editor-setting-translation.png){width="550" align="left"}


*Konfigurieren Sie Sprachgruppen und die Bereinigungsparameter für Übersetzungsprojekte.*


Erfahren Sie mehr darüber, wie Sie [das Übersetzungsprojekt automatisch löschen oder deaktivieren](../user-guide/translate-documents-web-editor.md#automatically-delete-or-disable-a-completed-translation-project).


## Aktivieren Sie die Ausgabe für Ihre Maps in der Massenaktivierungssammlung in der Vorschauinstanz.

Zusätzlich zur Aktivierung der Ausgabe für Ihre Massen-Aktivierungskollektion in der Veröffentlichungsinstanz bieten die Experience Manager-Richtlinien die Funktion , um sie in der Instanz **Vorschau** zu aktivieren.


Mit dieser Funktion können Sie Ihren Inhalt in einer Vorschauinstanz aktivieren, um zu überprüfen, wie er aussieht und wie er funktioniert, bevor er in der **Publish** -Instanz aktiviert wird.


![ erstellte Registerkarte für den Verlauf der Massenaktivierung-Erfassung ](assets/bulk-collection-audit-history.png){width="800" align="left"}

*Zeigen Sie die Informationen zu den aktivierten Zuordnungsausgaben auf der Registerkarte **Audit History**an.*


Erfahren Sie mehr über die [Massenaktivierung](../user-guide/conf-bulk-activation-publish-map-collection.md).

## Verbesserungen in den Data Source Connectors

Die folgenden Verbesserungen wurden an den Datenquellen-Connectoren für Version 2024.4.0 vorgenommen:

### Stellen Sie eine Verbindung zu den Datenquellen Salsify, Akeneo und Microsoft Azure DevOps Boards (ADO) her.

Zusätzlich zu den vorhandenen vordefinierten Connectoren bieten Experience Manager Guides auch Connectoren für Datenquellen von Salsify, Akeneo und Microsoft Azure DevOps Boards (ADO) an. Als Admin können Sie diese Connectoren herunterladen und installieren. Konfigurieren Sie anschließend die installierten Connectoren.

### Kopieren Sie die Beispielabfrage und fügen Sie sie ein, um einen Inhaltsausschnitt oder ein Thema zu erstellen

Sie können einfach eine Beispieldatenabfrage kopieren und in den Generator einfügen, um einen Inhaltsausschnitt oder ein Thema zu erstellen. Mit dieser Funktion müssen Sie sich nicht an die Syntax erinnern oder eine Abfrage manuell erstellen. Anstatt die Abfrage manuell einzugeben, können Sie eine Beispielabfrage kopieren und einfügen, sie bearbeiten und sie zum Abrufen der Daten nach Ihren Anforderungen verwenden.

![Dialogfeld zum Einfügen eines Inhaltsausschnitts“](assets/insert-content-snippet.png){width="800" align="left"}

*Kopieren und bearbeiten Sie eine Beispielabfrage, um den Inhaltsausschnitt zu erstellen.*

### Herstellen einer Verbindung zu JSON-Datendateien über einen Dateianschluss


Als Admin können Sie jetzt einen JSON-Datei-Connector konfigurieren, um JSON-Datendateien als Datenquelle zu verwenden. Verwenden Sie den Connector, um die JSON-Dateien von Ihrem Computer oder aus den Adobe Experience Manager-Assets zu importieren. Als Autorin bzw. Autor können Sie dann mithilfe der Generatoren Inhaltsausschnitte oder Themen erstellen.

Mit dieser Funktion können Sie die in Ihren JSON-Dateien gespeicherten Daten verwenden und sie über verschiedene Ausschnitte hinweg wiederverwenden. Der Inhalt wird auch dynamisch aktualisiert, sobald Sie die JSON-Dateien aktualisieren.

### Konfigurieren mehrerer Ressourcen-URLs für einen Connector zum Erstellen von Inhaltsfragmenten oder Themen

Als Administrator können Sie mehrere Ressourcen-URLs für einige Connectoren wie den generischen REST Client, Salsify, Akeneo und die Microsoft Azure DevOps-Pinnwände (ADO) konfigurieren.

Stellen Sie dann als Autorin bzw. Autor eine Verbindung mit den Datenquellen her, um mithilfe der Generatoren Inhaltsausschnitte oder Themen zu erstellen. Diese Funktion ist praktisch, da Sie nicht für jede URL eine Datenquelle erstellen müssen. Dies hilft Ihnen, Daten aus einer der Ressourcen für eine bestimmte Datenquelle in einem einzelnen Inhaltsfragment oder Thema schnell abzurufen.

Sehen Sie sich weitere Informationen zu den Data Source Connectors an und erfahren Sie, wie Sie [einen Data Source Connector über die Benutzeroberfläche konfigurieren](../cs-install-guide/conf-data-source-connector-tools.md).

Erfahren Sie, wie Sie [Daten aus Ihrer Datenquelle verwenden](../user-guide/web-editor-content-snippet.md).

## Anpassen Ihres Web-Editor-Erlebnisses mit der neuen Benutzeroberfläche der Benutzereinstellungen

Das Dialogfeld **Benutzereinstellungen** im Web Editor enthält jetzt die neue Registerkarte **Erscheinungsbild** . Mit dieser neuen Registerkarte können Sie die gängigsten Look-and-Feel-Voreinstellungen in der Web-Editor-Oberfläche bequem konfigurieren.

Sie können konfigurieren, dass die Dateien nach Titel oder Dateinamen angezeigt und das Design der Anwendung und die Quellansicht geändert werden. Außerdem können Sie die Einstellungen so konfigurieren, dass eine geöffnete Datei in der Repository-Ansicht gefunden und die geschützten Leerzeichen verarbeitet werden.

Registerkarte ![Erscheinungsbild der Benutzereinstellungen](assets/user_preference_editor_appearance.png){width="550" align="left"}

*Passen Sie das Erscheinungsbild an Ihre Voreinstellungen an.*

Weitere Informationen zur Funktionsbeschreibung für **Benutzereinstellungen** finden Sie im Abschnitt [Linkes Bedienfeld](../user-guide/web-editor-features.md#id2051EA0M0HS) .

## Suchen Sie eine geöffnete Datei in der Repository-Ansicht des Web-Editors

Wählen Sie in den **Benutzereinstellungen** die Option **Dateien im Repository immer suchen** aus, um schnell zu Ihrer Datei zu navigieren und sie in der Repository-Ansicht zu finden. Sie müssen nicht manuell danach suchen.

Bei der Bearbeitung hilft Ihnen diese Funktion auch dabei, den Speicherort der Datei innerhalb der Repository-Hierarchie anzuzeigen.

Weitere Informationen finden Sie unter [Suchen einer geöffneten Datei in der Repository-Ansicht](../user-guide/web-editor-edit-topics.md#locate-an-open-file-in-the-repository-view).


## Verbesserte Handhabung von geschützten Leerzeichen im Web Editor

Mit Experience Manager Guides können Sie beim Bearbeiten von Dokumenten im Web Editor eine ununterbrochene Leerzeichen-Anzeige anzeigen. Außerdem wird die Handhabung von geschützten Leerzeichen verbessert.
Sie konvertiert mehrere aufeinander folgende Leerzeichen in einen einzigen Leerraum, um die WYSIWYG-Ansicht des Dokuments im Web Editor beizubehalten. Diese Funktion trägt auch dazu bei, das Erscheinungsbild und die Professionalität des Dokuments zu verbessern.


Weitere Informationen finden Sie in den [anderen Funktionen des Web-Editors](../user-guide/web-editor-other-features.md).




## Deaktivierung der Nachbearbeitung für ausgewählte Ordner in Adobe Experience Manager Assets


Als Administrator können Sie jetzt die Nachbearbeitung und Generierung von UUIDs für bestimmte Ordner in Experience Manager Assets deaktivieren. Diese Konfiguration kann hilfreich sein, insbesondere wenn es um viele Assets oder komplexe Ordnerstrukturen geht. Außerdem können mehrere Benutzer die Assets gleichzeitig hochladen, ohne sich gegenseitig zu stören.  

Die Deaktivierung der Nachbearbeitung für einen Ordner wirkt sich auch auf alle untergeordneten Ordner aus. Experience Manager Guides bietet jetzt jedoch die Möglichkeit, die Nachbearbeitung für einzelne untergeordnete Ordner im ignorierten Ordner selektiv zu aktivieren.

Erfahren Sie, wie Sie [die Nachbearbeitung für einen Ordner deaktivieren](../cs-install-guide/conf-folder-post-processing.md).

## Überarbeitetes Erlebnis zum Suchen und Filtern von Dateien in der Repository-Ansicht

Das Filtern von Dateien wurde verbessert. Die überarbeitete Funktion zum Filtern von Dateien bietet eine verbesserte Möglichkeit, Dateien mühelos zu suchen und durch Dateien zu navigieren.


![Suchen von Dateien in der Repository-Ansicht](assets/repository-filter-search-2404.png){width="300" align="left"}

*Suchen nach Dateien, die den Text`general purpose.`* enthalten

Profitieren Sie von Vorteilen wie einem schnelleren Zugriff auf relevante Dateien und einer intuitiveren Benutzeroberfläche für ein reibungsloseres und effizienteres Sucherlebnis.

![Schnellsuchfilter ](assets/repository-filter-search-quick.png) {width="300" align="left"}

*Verwenden Sie die Filter für die schnelle Suche, um nach DITA- und Nicht-DITA-Dateien zu suchen.*

Weitere Informationen zur Funktion **Suche filtern** im Abschnitt [Linkes Bedienfeld](../user-guide/web-editor-features.md#id2051EA0M0HS).

## Segmentierte Liste zum Anzeigen und Einfügen gültiger Elemente entsprechend ihrer Position

Beim Bearbeiten eines Dokuments im Web Editor können Sie jetzt eine getrennte Liste von Elementen anzeigen, die am aktuellen Speicherort und außerhalb des aktuellen Speicherorts gültig sind. Je nach Ihren Anforderungen wählen Sie ein Element aus den folgenden Optionen aus:

* **Gültige Elemente an der aktuellen Position**, die Sie an der aktuellen Cursorposition selbst einfügen können.
* **Gültige Elemente außerhalb der aktuellen Position**, die Sie nach den übergeordneten Elementen für das aktuelle Element in der Elementhierarchie einfügen können.

![Dialogfeld &quot;Element einfügen&quot;](assets/insert-element-dialog.png){width="300" align="left"}

*Zeigen Sie die getrennten Listen mit gültigen Elementen an, um ein Element an der aktuellen Position einzufügen.*


Diese Aufspaltungsliste gültiger Elemente hilft Ihnen, die Inhaltsstruktur beizubehalten und die DITA-Standards zu befolgen.

Erfahren Sie mehr über die Funktion **Element einfügen** im Abschnitt [Sekundäre Symbolleiste](../user-guide/web-editor-features.md#2051ea0j0y4) .


## Content Properties Typ wird als Dropdown-Menü angezeigt

Jetzt wird die Inhaltseigenschaft **Typ** als Dropdown-Menü angezeigt. Sie können die Tags der vollständigen Hierarchie für das aktuelle Tag aus der Dropdown-Liste anzeigen und auswählen.

Über dieses Dropdown-Menü können Sie schnell auf die relevanten Tags innerhalb der hierarchischen Struktur zugreifen.


![Typ-Dropdown-Menü in den Inhaltseigenschaften](assets/content-properties-type.png){width="300" align="left"}

*Wählen Sie ein Tag aus der Hierarchie für das aktuelle Tag aus.*

Weitere Informationen zur Funktion **Inhaltseigenschaften** finden Sie im Abschnitt [Rechtes Bedienfeld](../user-guide/web-editor-features.md#id2051eb003yk) .



## Verbesserte Leistung beim stapelweisen Prüfen von Dateien im Map Editor

Experience Manager Guides verbessert die Leistung und das Erlebnis der Funktion zum Einchecken von Massendateien über den Map Editor. Diese Verbesserung hilft Ihnen, die Dateien schneller stapelweise einzuchecken.
Sie können den Fortschritt des Eincheckvorgangs für die Dateien auch über das Dialogfeld **Als neue Version speichern und Entsperren** anzeigen. Schließlich wird die Erfolgsmeldung angezeigt, nachdem der Vorgang abgeschlossen und alle ausgewählten ausgecheckten Dateien eingecheckt wurden.

![Als neue Version speichern und Dialogfeld entsperren](./assets/save-version-lock.png){width="300" align="left"}

*Zeigen Sie die Liste und den Status der Dateien an, die vom Map-Editor in großen Mengen geprüft wurden.*

Erfahren Sie, wie Sie [mit dem erweiterten Map-Editor arbeiten](../user-guide/map-editor-advanced-map-editor.md)

## Laden Sie die temporäre Datei herunter, während Sie die Ausgabe über DITA-OT generieren

Sie können auch die temporären Dateien herunterladen, die beim Veröffentlichen der AEM Site, HTML, Benutzerdefiniert, JSON oder PDF-Ausgabe über DITA-OT generiert wurden. Mit dieser Funktion können Sie alle Probleme analysieren, die während des Generierungsprozesses der Ausgabe auftreten könnten, und effektiv eine Fehlerbehebung durchführen.  
Sie können die Datei &quot;metadata.xml&quot;auch herunterladen, wenn Sie Metadateneigenschaften ausgewählt haben, die an die mit DITA-OT generierte Ausgabe übergeben wurden. 

Weitere Informationen zu den Vorgaben finden Sie unter [Grundlegendes zu den Ausgabevorgaben](../user-guide/generate-output-understand-presets.md).


## Ersetzen Sie IMS JWT-Anmeldeinformationen durch IMS OAuth-Anmeldeinformationen für die mikrodienstbasierte Veröffentlichung.


Die Anmeldedaten für das Dienstkonto (JWT) werden nicht mehr zugunsten der Anmeldedaten für **OAuth Server-to-Server** unterstützt. Ihre Anwendungen, die die Anmeldedaten für das Service-Konto (JWT) verwenden, funktionieren nach dem 1. Januar 2025 nicht mehr. Sie müssen bis zum 1. Januar 2025 zu den neuen Anmeldedaten migrieren, um sicherzustellen, dass Ihre Anwendung weiterhin funktioniert.


Der Cloud Publishing-Dienst für Experience Manager Guides wird jetzt durch die OAuth-basierte Authentifizierung von Adobe IMS gesichert. Erfahren Sie, wie Sie mit der OAuth-Authentifizierung ](../knowledge-base/publishing/configure-microservices-imt-config.md) die Veröffentlichung auf Microservice-Basis konfigurieren.[
