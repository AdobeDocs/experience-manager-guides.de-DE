---
title: Versionshinweise | Neue Funktionen in Adobe Experience Manager Guides Version 4.4.0
description: Erfahren Sie mehr über die neuen und verbesserten Funktionen in der Adobe Experience Manager Guides-Version 4.4.0.
role: Leader
source-git-commit: 57c3b39f0ab0fde5b18e4d4ae0e1501738997e68
workflow-type: tm+mt
source-wordcount: '3050'
ht-degree: 15%

---

# Neue Funktionen in Version 4.6.0 (September 2024)

Dieser Artikel behandelt die neuen und verbesserten Funktionen, die mit Version 4.6.0 von Adobe Experience Manager Guides eingeführt wurden.

Eine Liste der in dieser Version behobenen Probleme finden Sie unter [Behobene Probleme in Version 4.6.0](../release-info/fixed-issues-4-6-0.md).

Erfahren Sie mehr über [Upgrade-Anweisungen für Version 4.6.0](../release-info/upgrade-instructions-4-6-0.md).


## Verbesserungen bei der Veröffentlichung

In Version 4.6.0 wurden folgende Verbesserungen an der Veröffentlichung von Inhalten vorgenommen:



### Publish eines Themas oder seiner Elemente für ein Experience Fragment

Ein Experience Fragment ist eine modulare Inhaltseinheit in Adobe Experience Manager, die Inhalte und Layouts integriert. Experience Fragments sind hilfreich bei der Erstellung konsistenter und ansprechender Erlebnisse, die über mehrere Kanäle hinweg wiederverwendet werden können. Sie können beispielsweise Erlebnisfragmente für Kopf- oder Fußzeilen mit Branding-Elementen, Werbebannern, Kundenaussagen und Ereignispromotionen erstellen.

Registerkarte ](./assets/file-properties-outputs-4-6.png) {width="300" align="left"} Optionen für Dateieigenschaften ![

*Publish und Anzeigen der Erlebnisfragmente eines Themas im Abschnitt **Ausgaben**in den **Dateieigenschaften***

Mit Experience Manager Guides können Sie jetzt ein Thema oder dessen Elemente in einem Experience Fragment veröffentlichen. Sie können eine JSON-basierte Zuordnung zwischen einem Thema oder seinen Elementen und einer Experience Fragment-Vorlage erstellen. Mithilfe der Bedingungsfilter können Sie auch Experience Fragment-Varianten erstellen.

Erfahren Sie mehr über das [Publish-Erlebnisfragmente](../user-guide/publish-experience-fragment.md).



### Verbesserungen bei der Veröffentlichung von Inhaltsfragmenten

Experience Manager Guides bietet außerdem einige hilfreiche Verbesserungen bei Inhaltsfragmenten:

- Mit Experience Manager Guides können Sie ein Thema oder dessen Elemente in einem Inhaltsfragment veröffentlichen.

- Sie können die Inhaltsfragmente eines Themas im Abschnitt **Ausgaben** in den **Dateieigenschaften** veröffentlichen und anzeigen.


- Sie können Inhaltsfragmentvarianten einfach erstellen, indem Sie Inhalte mit Bedingungen filtern, während Sie sie in einem Inhaltsfragment veröffentlichen.

- Verwenden Sie die neue Zuordnungsschnittstelle, um die Elemente einfach auszuwählen und in einem Inhaltsfragment zu veröffentlichen.

Jetzt ersetzt die Inhaltsfragmentveröffentlichung nur den zugeordneten Inhalt, anstatt das vollständige Inhaltsfragment zu überschreiben. Diese Funktion ermöglicht es einem Inhaltsfragment, Daten aus mehreren Quellen wie mehreren Themen oder dem Inhaltsfragment-Editor zu enthalten.

![Fügen Sie das Fragmentmodell und die Zuordnungsdetails im Dialogfeld &quot;Publish als Inhaltsfragment&quot;hinzu](assets/content-fragment-mapping.png)

Weitere Informationen finden Sie unter [Publish-Inhaltsfragmente](../user-guide/publish-content-fragment.md).

### AEM Sites-Vorgabe wurde neu organisiert, um die Verwendung zu erleichtern

Die Einstellungen wurden neu angeordnet, damit Sie die Ausgabevorgabe schnell konfigurieren und die AEM Sites-Ausgabe generieren können.
Sie können die vorhandenen AEM Sites-Vorgaben erstellen, indem Sie im Dialogfeld **Neue Ausgabevorgabe** die Option **Alte Komponentenzuordnung verwenden** auswählen.

Zeigen Sie die Registerkarten **Allgemein**, **Inhalt** und **Querverweis** in den AEM Sites-Vorgaben an:
- **Allgemein**: Enthält die allgemeinen Konfigurationen zum Generieren der Ausgabe. Sie können den Site- und Ausgabepfad angeben, vorhandene Ausgabeseiten löschen oder überschreiben, die zuvor generierten Seiten für entfernte Themen löschen, die Designvorlage auswählen, die temporären Dateien beibehalten und den Nachbearbeitungs-Workflow festlegen.
- **Inhalt**: Enthält die Einstellungen, die für den Inhalt zur Ausgabegenerierung gelten. Sie können die Filter, die Grundlinie der DITA-Zuordnung und die Metadateneigenschaften für die Veröffentlichung auswählen.
- **Querverweise**: Diese Liste enthält Themen, die Querverweise mit Umfang =&quot;Peer&quot;enthalten. Sie können den Veröffentlichungskontext für eine Liste von Querverweisen mit scope=&quot;peer&quot; zu Themen angeben, die in anderen DITA-Maps verfügbar sind. Diese Registerkarte wird angezeigt, wenn Sie die Experience Manager Guides-Version (UUID) verwenden.



### Querverweise von AEM Sites-Vorgaben im Web Editor

Die neueste Verbesserung von Experience Manager Guides führt Querverweise in den AEM Sites-Vorgaben des Web Editors ein.
Querverweise in Experience Manager Guides helfen bei der Verbesserung der Inhaltsnavigation, der verbesserten Wiederverwendung von Inhalten und der Verbesserung des Benutzererlebnisses.


Sie können den Veröffentlichungskontext für eine Liste von Querverweisen auf Themen festlegen, die in anderen DITA-Maps mit scope=&quot;peer&quot; verfügbar sind. Beispielsweise enthält Thema 1 in Karte A einen Verweis auf Thema 2. Thema 2 kann in einer oder mehreren Maps vorhanden sein.  Sie können für jeden Link die übergeordnete Zuordnung und eine bestimmte Vorgabe oder die zuletzt veröffentlichte Ausgabe auswählen.

Wenn dasselbe Thema mehr als einmal in einer Datei referenziert wird, können Sie für jede Instanz einen anderen Veröffentlichungskontext hinzufügen. Dies bietet mehr Flexibilität und Kontrolle über den Inhalt. Zum Beispiel ist Thema 3 sowohl in Karte B als auch in Karte C vorhanden. Thema 1 enthält zwei Verweise auf Thema 3. Sie können Map B als übergeordnete Zuordnung für den ersten Link und Map C als übergeordnete Zuordnung für den zweiten Link auswählen.

![Veraltete AEM Sites-Vorgabe](assets/aem-sites-legacy.png)

*Geben Sie den Veröffentlichungskontext für die verknüpften Themen auf der Registerkarte **Querverweise**der Vorgabe **AEM Sites**an.*






### Möglichkeit, Metadaten aus Themendateieigenschaften an die native PDF-Ausgabe zu übergeben

Jetzt können Sie mit Experience Manager Guides die Metadaten aus den Dateieigenschaften eines Themas zu den Seitenlayouts hinzufügen, während Sie die native PDF-Ausgabe generieren. Verwenden Sie diese Funktion, um den Seitenlayouts themenspezifische Metadaten wie Titel, Tags und Beschreibung hinzuzufügen. Sie können auch Ihre veröffentlichte PDF auf Grundlage der Metadaten des Themas anpassen, z. B. das Hinzufügen eines Wasserzeichens zum Hintergrund des Themas basierend auf dem Dokumentstatus des Themas.

![ Hinzufügen von nativen Metadaten-PDF](./assets/add-metadata-native-pdf.png) {width="300" align="left"}

*Fügen Sie den Feldern in Ihren Seitenlayouts Metadaten hinzu.*

Erfahren Sie, wie Sie in einem Seitenlayout [Felder und Metadaten hinzufügen](../native-pdf/design-page-layout.md#add-fields-metadata).





### Unterstützung für Markdown-Dokumente in nativer PDF-Veröffentlichung

Experience Manager Guides unterstützt auch Markdown-Dokumente im nativen PDF-Publishing. Diese Funktion ist praktisch und hilft Ihnen beim Generieren von PDF für die Markdown-Dateien in Ihrer DITA-Zuordnung.

Weitere Informationen finden Sie unter [Unterstützung für Markdown-Dokumente](../web-editor/native-pdf-web-editor.md#support-for-markdown-documents).


### Laden Sie die temporäre Datei herunter, während Sie die Ausgabe über DITA-OT generieren

Sie können auch die temporären Dateien herunterladen, die beim Veröffentlichen der AEM Sites-, HTML-, benutzerspezifischen, JSON- oder PDF-Ausgabe über DITA-OT generiert wurden. Mit dieser Funktion können Sie alle Probleme analysieren, die während des Generierungsprozesses der Ausgabe auftreten könnten, und effektiv eine Fehlerbehebung durchführen.  
Sie können die Datei &quot;metadata.xml&quot;auch herunterladen, wenn Sie Metadateneigenschaften ausgewählt haben, die an die mit DITA-OT generierte Ausgabe übergeben wurden. 

Weitere Informationen zu den Vorgaben finden Sie unter [Grundlegendes zu den Ausgabevorgaben](../user-guide/generate-output-understand-presets.md).


### Option zur Auswahl einer flachen oder verschachtelten Dateihierarchie für die HTML5-Ausgabe

Jetzt können Sie mit Experience Manager Guides die flache Ordnerhierarchie für die temporären Dateien beibehalten, wobei der gesamte Inhalt im HTML5-Ausgabeformat veröffentlicht und in einem einzigen Ordner gespeichert wird.
Wenn Sie die Dateihierarchie nicht reduzieren möchten, wird die HTML5-Ausgabe in einer verschachtelten Ordnerhierarchie generiert. Dies bedeutet, dass die ursprüngliche Ordnerstruktur des Inhalts mit in Unterordner unterteilten Dateien in der Ausgabe repliziert wird. Diese verschachtelte Ordnerhierarchie ermöglicht eine komplexere Organisation und Kategorisierung von Dateien, was die Verwaltung und Navigation großer Datenmengen erleichtert.


Erfahren Sie mehr darüber, wie Sie [HTML5-Ausgabe generieren](../user-guide/generate-output-html5.md)


## Editor-Verbesserungen

Die folgenden Editor-Verbesserungen wurden in Version 4.6.0 hinzugefügt:

### Schreibgeschützter Zugriff auf den Author- und Source-Modus für gesperrte Dateien

Wenn eine DITA- oder Markdown-Datei von einem anderen Benutzer gesperrt oder ausgecheckt wurde, können Sie den Inhalt nicht bearbeiten oder ändern. Neben der Vorschau können Sie sie auch als schreibgeschützte Datei im Author- oder Source-Modus anzeigen.
Im schreibgeschützten Modus können Sie den Inhalt zusammen mit den Tags und Attributen im Modus **Autor** oder **Source** anzeigen und die Dateieigenschaften bearbeiten.

Sie können auch auf die Ansicht **Layout** für schreibgeschützte DITA-Maps zugreifen.
>[!NOTE]
>
> Ihre Ordnerprofiladministratoren müssen *ui_config.json* aktualisieren, damit Sie harmonisch auf die schreibgeschützten Dateien im Author-, Source- und Layout-Modus zugreifen können.

![gesperrter Dateieditor](./assets/locked-file-editor.png)
*Zeigen Sie die gesperrten Dateien im Author- und Source-Modus an.*


Erfahren Sie, wie Sie &quot;[gesperrte Dateien im Author- und Source-Modus öffnen](../user-guide/web-editor-edit-topics.md#open-locked-files-in-author-and-source-modes)&quot;.



### Teilinhalt über Elemente hinweg für Vorgänge auswählen

Experience Manager Guides verbessert Ihre Erfahrung bei der Auswahl des Inhalts über alle Elemente im Web Editor. Sie können Inhalte mühelos über verschiedene Elemente hinweg auswählen und Vorgänge wie Fettdruck, Kursiv und Unterstrichen durchführen.

Mit dieser Funktion können Sie die Formatierung für teilweise ausgewählten Inhalt nahtlos anwenden oder entfernen. Sie können auch schnell den Inhalt löschen, den Sie über mehrere Elemente hinweg ausgewählt haben. Nach dem Löschen des Inhalts wird der verbleibende Inhalt bei Bedarf automatisch unter einem einzigen gültigen Element zusammengeführt. Sie können auch Teilinhalte über Elemente hinweg auswählen und den Inhalt dann unter einem gültigen DITA-Element umgeben.

Insgesamt bieten diese Verbesserungen ein besseres Erlebnis und helfen Ihnen, Ihre Effizienz bei der Bearbeitung Ihrer Dokumente zu verbessern.
Weitere Informationen finden Sie unter [Teilauswahl des Inhalts über Element hinweg](../user-guide/web-editor-edit-topics.md#partial-selection-of-content-across-elements).



### Segmentierte Liste zum Anzeigen und Einfügen gültiger Elemente entsprechend ihrer Position

Beim Bearbeiten eines Dokuments im Web Editor können Sie jetzt eine getrennte Liste von Elementen anzeigen, die am aktuellen Speicherort und außerhalb des aktuellen Speicherorts gültig sind. Je nach Ihren Anforderungen wählen Sie ein Element aus den folgenden Optionen aus:

- **Gültige Elemente an der aktuellen Position**, die Sie an der aktuellen Cursorposition selbst einfügen können.
- **Gültige Elemente außerhalb der aktuellen Position**, die Sie nach den übergeordneten Elementen für das aktuelle Element in der Elementhierarchie einfügen können.

![Dialogfeld &quot;Element einfügen&quot;](assets/insert-element-dialog.png){width="300" align="left"}

*Zeigen Sie die getrennten Listen mit gültigen Elementen an, um ein Element an der aktuellen Position einzufügen.*


Diese Aufspaltungsliste gültiger Elemente hilft Ihnen, die Inhaltsstruktur beizubehalten und die DITA-Standards zu befolgen.

Erfahren Sie mehr über die Funktion **Element einfügen** im Abschnitt [Sekundäre Symbolleiste](../user-guide/web-editor-features.md#2051ea0j0y4) .


### Überarbeitetes Erlebnis zum Suchen und Filtern von Dateien in der Repository-Ansicht

Das Filtern von Dateien wurde verbessert. Die überarbeitete Funktion zum Filtern von Dateien bietet eine verbesserte Möglichkeit, Dateien mühelos zu suchen und durch Dateien zu navigieren.


![Suchen von Dateien in der Repository-Ansicht](assets/repository-filter-search-2404.png){width="300" align="left"}

*Suchen nach Dateien, die den Text`general purpose.`* enthalten

Profitieren Sie von Vorteilen wie einem schnelleren Zugriff auf relevante Dateien und einer intuitiveren Benutzeroberfläche für ein reibungsloseres und effizienteres Sucherlebnis.

![Schnellsuchfilter ](assets/repository-filter-search-quick.png) {width="300" align="left"}

*Verwenden Sie die Filter für die schnelle Suche, um nach DITA- und Nicht-DITA-Dateien zu suchen.*


>[!NOTE]
>
> Ihre Ordnerprofiladministratoren müssen *ui_config.json* aktualisieren, damit Sie harmonisch auf diese Funktion zugreifen können.

Weitere Informationen zur Funktion **Suche filtern** im Abschnitt [Linkes Bedienfeld](../user-guide/web-editor-features.md#id2051EA0M0HS).

### Gruppierung von Bedingungen für eine erweiterte Inhaltsorganisation

Mit Experience Manager Guides können Sie jetzt Bedingungen gruppieren und in einer verschachtelten Hierarchie darstellen, sodass Sie einer Gruppe mehrere Bedingungen hinzufügen können. Durch die Gruppierung von Bedingungen können Sie diese besser organisieren und über Ihren Inhalt hinweg anwenden.

![Bedingungen, die in einer verschachtelten Hierarchie organisiert sind](assets/conditions-nested-hierarchy.png){width="300" align="left"}

Weitere Informationen zur Funktionsbeschreibung für **Bedingungen** finden Sie im Abschnitt [Linkes Bedienfeld](../user-guide/web-editor-features.md#id2051EA0M0HS) .

### Anpassen Ihres Web-Editor-Erlebnisses mit einer neuen Benutzeroberfläche von Benutzereinstellungen

Das Dialogfeld **Benutzereinstellungen** im Web Editor enthält jetzt die neue Registerkarte **Erscheinungsbild** . Mit dieser neuen Registerkarte können Sie die gängigsten Look-and-Feel-Voreinstellungen in der Web-Editor-Oberfläche bequem konfigurieren.

Sie können konfigurieren, dass die Dateien nach Titel oder Dateinamen angezeigt und das Design der Anwendung und die Quellansicht geändert werden. Außerdem können Sie die Einstellungen so konfigurieren, dass eine geöffnete Datei in der Repository-Ansicht gefunden und die geschützten Leerzeichen verarbeitet werden.

Registerkarte ![Erscheinungsbild der Benutzereinstellungen](assets/user_preference_editor_appearance.png){width="550" align="left"}

*Passen Sie das Erscheinungsbild an Ihre Voreinstellungen an.*

Weitere Informationen zur Funktionsbeschreibung für **Benutzereinstellungen** finden Sie im Abschnitt [Linkes Bedienfeld](../user-guide/web-editor-features.md#id2051EA0M0HS) .


### Suchen Sie eine geöffnete Datei in der Repository-Ansicht des Web-Editors

Wählen Sie in den **Benutzereinstellungen** die Option **Dateien im Repository immer suchen** aus, um schnell zu navigieren und Ihre Datei in der Repository-Ansicht zu finden. Sie müssen nicht manuell danach suchen.

Bei der Bearbeitung hilft Ihnen diese Funktion auch dabei, den Speicherort der Datei innerhalb der Repository-Hierarchie anzuzeigen.

Weitere Informationen finden Sie unter [Suchen einer geöffneten Datei in der Repository-Ansicht](../user-guide/web-editor-edit-topics.md#locate-an-open-file-in-the-repository-view).

### Verbesserte Handhabung von geschützten Leerzeichen im Web Editor

Mit Experience Manager Guides können Sie beim Bearbeiten von Dokumenten im Web Editor eine ununterbrochene Leerzeichen-Anzeige anzeigen. Außerdem wird die Handhabung von geschützten Leerzeichen verbessert.
Sie konvertiert mehrere aufeinander folgende Leerzeichen in einen einzigen Leerraum, um die WYSIWYG-Ansicht des Dokuments im Web Editor beizubehalten. Diese Funktion trägt auch dazu bei, das Erscheinungsbild und die Professionalität des Dokuments zu verbessern.


Weitere Informationen finden Sie in den [anderen Funktionen des Web-Editors](../user-guide/web-editor-other-features.md).


### Möglichkeit, Eigenschaften von Elementen aus der Elementhierarchie anzuzeigen

Jetzt wird die Inhaltseigenschaft **Typ** als Dropdown-Menü angezeigt. Sie können die Tags der vollständigen Hierarchie für das aktuelle Tag aus der Dropdown-Liste anzeigen und auswählen.

Dieses Dropdown-Menü hilft Ihnen beim schnellen Zugriff auf die Inhaltseigenschaften für das ausgewählte Tag.


![Typ-Dropdown-Menü in den Inhaltseigenschaften](assets/content-properties-type.png){width="300" align="left"}

*Wählen Sie ein Tag aus der Hierarchie für das aktuelle Tag aus.*

Weitere Informationen zur Funktion **Inhaltseigenschaften** finden Sie im Abschnitt [Rechtes Bedienfeld](../user-guide/web-editor-features.md#id2051eb003yk) .



### Verbesserte Leistung beim stapelweisen Einchecken der Dateien im Map Editor

Experience Manager Guides verbessert die Leistung und das Erlebnis der Funktion zum Einchecken von Massendateien über den Map Editor. Diese Verbesserung hilft Ihnen, die Dateien schneller stapelweise einzuchecken.
Sie können den Fortschritt des Eincheckvorgangs für die Dateien auch über das Dialogfeld **Als neue Version speichern und Entsperren** anzeigen. Schließlich wird die Erfolgsmeldung angezeigt, nachdem der Vorgang abgeschlossen und alle ausgewählten ausgecheckten Dateien eingecheckt wurden.

![Als neue Version speichern und Dialogfeld entsperren](./assets/save-version-lock.png){width="300" align="left"}

*Zeigen Sie die Liste und den Status der Dateien an, die vom Map-Editor in großen Mengen geprüft wurden.*

Erfahren Sie, wie Sie [mit dem erweiterten Map-Editor arbeiten](../user-guide/map-editor-advanced-map-editor.md)





## Verbesserungen bei der Verwaltung von Inhalten

Das Content-Lebenszyklusmanagement wurde wie folgt verbessert:

### Möglichkeit zur Übersetzung von Inhalten in mehrere Sprachen mithilfe vorkonfigurierter Sprachgruppen

In Experience Manager Guides können Sie jetzt Sprachgruppen erstellen und Ihre Inhalte einfach in mehrere Sprachen übersetzen. Mit dieser Funktion können Sie Übersetzungen entsprechend den Anforderungen Ihres Unternehmens organisieren und verwalten.

Wenn Sie beispielsweise Inhalte für einige Länder in Europa übersetzen müssen, können Sie eine Sprachgruppe für europäische Sprachen wie Englisch (EN), Französisch (FR), Deutsch (DE), Spanisch (ES) und Italienisch (IT) erstellen.



![Übersetzungsbedienfeld](assets/translation-languages-2404.png){width="300" align="left"}

*Wählen Sie die Sprachgruppen oder Sprachen aus, die Sie Ihre Dokumente übersetzen möchten.*

>[!NOTE]
>
>Wenn der Zielordner einer Sprache fehlt oder die Zielsprache mit der Quelle identisch ist, ist die Sprache ausgegraut und es wird ein Warnsymbol angezeigt.

Als Admin können Sie Sprachgruppen erstellen und diese für mehrere Ordnerprofile konfigurieren. Als Autorin bzw. Autor können Sie die Sprachgruppen anzeigen, die für Ihr Ordnerprofil konfiguriert sind.


Insgesamt verbessert die Erstellung von Sprachgruppen die Effizienz und Produktivität von Übersetzungsprojekten und verbessert damit den Lokalisierungsprozess über mehrere Sprachen hinweg.


Erfahren Sie, wie Sie [Dokumente aus dem Web-Editor übersetzen](../user-guide/translate-documents-web-editor.md).


### Verbesserte Leistung und Skalierbarkeit für große Übersetzungsprojekte

Die Übersetzungsfunktion ist schneller und skalierbarer als je zuvor. Es verfügt über eine neue Architektur, die eine verbesserte Leistung bietet. Die Projekterstellungszeit ist jetzt schneller als früher und die Konflikte während des Prozesses sind fast nicht vorhanden. Diese verbesserte Leistung hilft Ihnen bei schnelleren Übersetzungen und sorgt für einen reibungslosen Betrieb auch bei großen Übersetzungsprojekten.

Diese Verbesserung ist sehr vorteilhaft, da sie die Produktivität und die Gesamterfahrung verbessert.

Erfahren Sie mehr darüber, wie Sie [Dokumente aus dem Web-Editor übersetzen](../user-guide/translate-documents-web-editor.md).

### Löschen oder deaktivieren Sie das Übersetzungsprojekt automatisch nach der Übersetzung

Als Administrator können Sie jetzt die Übersetzungsprojekte so konfigurieren, dass sie nach Abschluss der Übersetzung automatisch deaktiviert oder gelöscht werden. Diese Funktion hilft Ihnen, Ressourcen effizient zu nutzen und Dateien nach Abschluss der Übersetzung zu verwalten.

Durch das Löschen eines Projekts werden alle im Projekt vorhandenen Dateien und Ordner dauerhaft entfernt. Durch die Löschung der Übersetzungsprojekte können Sie auch den belegten Speicherplatz freigeben.

Sie können die Übersetzungsprojekte deaktivieren, wenn Sie sie später verwenden möchten.

![](assets/editor-setting-translation.png){width="550" align="left"}


*Konfigurieren Sie Sprachgruppen und die Bereinigungsparameter für Übersetzungsprojekte.*


Erfahren Sie mehr darüber, wie Sie [das Übersetzungsprojekt automatisch löschen oder deaktivieren](../user-guide/translate-documents-web-editor.md#automatically-delete-or-disable-a-completed-translation-project).


### Deaktivierung der Nachbearbeitung für ausgewählte Ordner in Adobe Experience Manager Assets


Als Administrator können Sie jetzt die Nachbearbeitung und Generierung von UUIDs für bestimmte Ordner in Experience Manager Assets deaktivieren. Diese Konfiguration kann hilfreich sein, insbesondere wenn es um viele Assets oder komplexe Ordnerstrukturen geht. Außerdem können mehrere Benutzer die Assets gleichzeitig hochladen, ohne sich gegenseitig zu stören.  

Die Deaktivierung der Nachbearbeitung für einen Ordner wirkt sich auch auf alle untergeordneten Ordner aus. Experience Manager Guides bietet jetzt jedoch die Möglichkeit, die Nachbearbeitung für einzelne untergeordnete Ordner im ignorierten Ordner selektiv zu aktivieren.

Erfahren Sie, wie Sie [die Nachbearbeitung für einen Ordner deaktivieren](../cs-install-guide/conf-folder-post-processing.md).


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

Stellen Sie dann als Autorin bzw. Autor eine Verbindung mit den Datenquellen her, um mithilfe der Generatoren Inhaltsausschnitte oder Themen zu erstellen. Diese Funktion ist praktisch, da Sie nicht für jede URL eine Datenquelle erstellen müssen. Dies hilft Ihnen, Daten schnell aus einer der Ressourcen für eine bestimmte Datenquelle in einem einzelnen Inhaltsfragment oder Thema abzurufen.

Sehen Sie sich weitere Informationen zu den Data Source Connectors an und erfahren Sie, wie Sie [einen Data Source Connector über die Benutzeroberfläche konfigurieren](../cs-install-guide/conf-data-source-connector-tools.md).

Erfahren Sie, wie Sie [Daten aus Ihrer Datenquelle verwenden](../user-guide/web-editor-content-snippet.md).

