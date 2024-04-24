---
title: Übersetzen von Dokumenten aus dem Web Editor
description: Übersetzen Sie Ihre Inhalte über den Web-Editor in mehrere Sprachen. Erfahren Sie, wie Sie ein Übersetzungsprojekt erstellen, Regeln hinzufügen, Versionen anzeigen und nicht synchronisierte Dateien in AEM Handbüchern schließen.
exl-id: 321c5442-92eb-4662-ab61-d4d4f05eeb39
feature: Authoring, Features of Web Editor, Translation
role: User
source-git-commit: ce7619538b229625277a552071bed8800e67f677
workflow-type: tm+mt
source-wordcount: '2246'
ht-degree: 1%

---

# Übersetzen von Dokumenten aus dem Web Editor {#id21BKF0Z0YZF}

>[!TIP]
>
> Es wird empfohlen, diese Übersetzungsfunktion im Web Editor zu verwenden, wenn Sie ein Upgrade auf AEM Guides as a Cloud Service Version Februar 2022 oder höher durchgeführt haben.

AEM Guides verfügen über eine leistungsstarke Funktion im Web Editor, mit der Sie Ihre Inhalte in mehrere Sprachen übersetzen können. Sie können ein neues Übersetzungsprojekt erstellen und die Übersetzungsaufträge später dem vorhandenen Übersetzungsprojekt hinzufügen. Sie können auch ein mehrsprachiges Übersetzungsprojekt erstellen, das Übersetzungsaufträge für alle ausgewählten Sprachen enthält.

>[!NOTE]
>
> Ihr Administrator kann die Registerkarte Verwalten \(für die Übersetzung verwendet\) im Web Editor konfigurieren. Weitere Informationen finden Sie unter *Konfigurieren der Übersetzungsfunktion im Web-Editor* im as a Cloud Service Installieren und Konfigurieren von Adobe Experience Manager-Handbüchern.

## Vorbereitung

Stellen Sie vor dem Ausführen der Schritte in diesem Verfahren sicher, dass Sie den erforderlichen Sprachstamm und die Zielordner erstellt haben.

1. Erstellen Sie einen Stammordner zum Speichern des Quellinhalts. Der Stammordner muss mit dem Sprachnamen \(z. B. Englisch\) oder dem Sprachcode \(en\) erstellt werden.
1. Erstellen Sie die Zielordner, in die Sie den Inhalt übersetzen möchten. Wenn Sie beispielsweise Ihren Inhalt in Deutsch oder Französisch übersetzen möchten, müssen Sie einen Ordner mit dem Namen &quot;-de \(für Deutsch\)&quot;oder &quot;-fr \(für Französisch\)&quot;erstellen.

>[!NOTE]
>
> Der Stammordner und die Zielordner müssen auf derselben Ebene erstellt werden.

## Ein Übersetzungsprojekt erstellen

1. Im **Repository** -Bedienfeld öffnen Sie die DITA-Map-Datei in der Kartenansicht.
1. Klicken Sie auf **Verwalten** Registerkarte. Die **Übersetzungsbereich** zeigt die verfügbaren Sprachgruppen an.

1. Als Benutzer können Sie die für Ihr Ordnerprofil konfigurierten Sprachgruppen anzeigen. Die Sprachgruppen zeigen die Sprachordner zusammen mit ihren Sprachcodes an. Beispielsweise enthält die Sprachgruppe G1 die Ordner Italienisch \(it\), Deutsch \(de\), Französisch \(fr\) und Englisch \(en\).

   ![Übersetzungsbereich](images/translation-languages.png){width="300" align="left"}

   *Wählen Sie die Sprachgruppen oder Sprachen aus, in denen Sie Ihre Dokumente übersetzen möchten.*


   >[!IMPORTANT]
   >
   > Sie können nur die Sprachen auswählen und übersetzen, für die Sie den Zielordner parallel zur Ausgangssprache erstellt haben. Ein auf einer anderen Ebene erstellter Sprachordner, z. B. eine Ebene weiter ab dem Ordner für die Ausgangssprache, wird ebenfalls nicht angezeigt. Stellen Sie sicher, dass Sie alle Zielsprachordner auf derselben Ebene wie Ihren Ausgangssprachordner erstellen.



1. Sie können eine beliebige Sprachgruppe als Ziel für die Übersetzung auswählen. Wenn Sie **Alle auswählen**, werden die ausgewählten Dateien in alle verfügbaren Sprachen innerhalb der vorhandenen Sprachgruppen übersetzt.

   Die Option Sprachordner wird ausgegraut und zeigt ein Warnzeichen an:

   - Wenn der Zielordner für eine Sprache fehlt.
   - Wenn die Zielsprache mit der Quelle identisch ist.


   >[!NOTE]
   >
   > Wenn Sie den Zielordner für eine Sprache erstellen, nachdem Sie die Sprachgruppe erstellt haben, aktualisieren Sie den Browser, um die Sprache in den Sprachgruppen zu aktivieren.

1. Wenn Sie eine bestimmte Sprache auswählen, wird diese wie ausgewählt unter allen ausgewählten Sprachgruppen angezeigt. Wenn man also in eine Sprache übersetzt, wird es für alle Sprachgruppen auf einmal übersetzt. Wenn beispielsweise Deutsch sowohl in G1- als auch in G2-Sprachgruppen vorhanden ist, wird es für beide Sprachen ausgewählt.

1. Aus dem **weitere Sprachen** können Sie eine beliebige Sprache auswählen, für die Sie den Zielordner erstellt haben, die jedoch nicht zu einer Sprachgruppe gehört.

1. Sie können auch eine der folgenden Optionen auswählen, um Ihr Projekt zu übersetzen:

   **Keines** Wählen Sie diese Option, um die Standardversionen der Dateien zu übersetzen. Standardmäßig ist diese Option aktiviert.

   **Grundlinie verwenden:** Sie können eine Grundlinie auswählen, um Ihr Projekt zu übersetzen. Klicken Sie auf Grundlinie verwenden und wählen Sie eine auf der Karte erstellte Grundlinie aus. Alle Dateien, die Teil der ausgewählten Grundlinie sind, werden auf der Seite Übersetzung angezeigt. Sobald Ihr Inhalt übersetzt wurde, können Sie die übersetzte Grundlinie exportieren. Weitere Informationen zum Exportieren der übersetzten Grundlinie finden Sie unter [Exportieren der übersetzten Grundlinie](generate-output-use-baseline-for-publishing.md#id196SE600GHS).

   **Verwenden Sie die neueste Version wie unter**: Wählen Sie diese Option, um die Version der Themen nach Erstellungsdatum und -zeit zu filtern. Wenn Sie ein Datum und eine Uhrzeit auswählen, wird nur die neueste Version der Dateien angezeigt, die am oder vor dem ausgewählten Datum und der ausgewählten Uhrzeit erstellt wurden.

1. Klicks **Anwenden**. Eine Liste mit Details zu Themen und zugehörigen Assets wird angezeigt.
1. Wählen Sie die Themen aus, die Sie zur Übersetzung senden möchten. Sie können auch die Themenfilteroptionen für die folgenden Spalten verwenden:

   - **Titel**: Titel der Quelldatei.  Bewegen Sie den Mauszeiger über den Titel der Quelldatei, um den Titel der Zieldatei oder der übersetzten Datei anzuzeigen.
   - **Dateiname**: Name der Quelldatei
   - **Dateityp**: Typ der Quelldatei. Die verfügbaren Optionen sind &quot;Zuordnung&quot;, &quot;Thema&quot;und &quot;Bild&quot;.
   - **Referenztyp**: Direkte oder indirekte Verweise
   - **Version**: Versionsnummer der Quelldatei
   - **Versionsbezeichnung**: Titel der ausgewählten Version der Quelldatei
   - **Zielversion**: Versionsnummer der Zieldatei
   - **Dokumentstatus**: Status der Quelldatei. Die verfügbaren Optionen sind &quot;Entwurf&quot;, &quot;In-Review&quot;und &quot;Überprüfen&quot;.
   - **Zielsprache**: Die Sprache, in die Sie die Quelldatei übersetzen möchten
   - **Übersetzungsstatus**: Die verfügbaren Optionen sind: &quot;Nicht synchronisiert&quot;, &quot;Kopie fehlt&quot;, &quot;Wird ausgeführt&quot;und &quot;Synchronisiert&quot;.
   - **Zielbezeichnung**: Beschriftung für die ausgewählte Version der Zieldatei
1. Klicks **Zu übersetzen** oben rechts.

   ![](images/translation-send.png){width="800" align="left"}

1. Wählen Sie aus der Dropdown-Liste **Neues Übersetzungsprojekt erstellen**.

   ![](images/translation-project-types.png){width="350" align="left"}

   Neben einem neuen Übersetzungsprojekt können Sie auch aus den folgenden Optionen auswählen:

   - Sie können zwischen **Erstellen einer Struktur** nur für das Übersetzungsprojekt.
   - Sie können zwischen **Erstellen eines neuen XLIFF-Übersetzungsprojekts** , um den XML-Inhalt in das XML Localization Interchange File Format (XLIFF) zu konvertieren. XLIFF ist ein offenes XML-basiertes Format, das verwendet wird, um die Datenübertragung zwischen verschiedenen Tools zu standardisieren, die im Prozess der Inhaltsübersetzung verwendet werden. AEM Guides unterstützen XLIFF-Version 1.2. In einem XLIFF-Projekt wird der Inhalt in das XLIFF-Format des Branchenstandards exportiert, das Übersetzungsagenturen zur Verfügung gestellt werden kann. Das XLIFF-Format ermöglicht die potenzielle Wiederverwendung von Segmenten, die Sie bereits während der Übersetzungsphase übersetzt haben.\
     Nachdem der XLIFF-Inhalt übersetzt wurde, kann er in AEM Guides importiert werden, um eine übersetzte Version des ursprünglichen DITA-Projekts zu erstellen.

     >[!NOTE]
     >
     > Der XLIFF-Export funktioniert nur mit der Konfiguration menschlicher Übersetzungen.

   - Sie können **Neues mehrsprachiges Übersetzungsprojekt erstellen** enthält Übersetzungsaufträge für alle Sprachen, die Sie für die Übersetzung ausgewählt haben. Wenn Sie beispielsweise Französisch, Deutsch und Spanisch ausgewählt haben, wird ein Projekt erstellt, das Übersetzungsaufträge für alle drei Sprachen enthält.
   - Wenn Sie bereits über ein Übersetzungsprojekt verfügen, können Sie diesem Projekt Themen hinzufügen. Wählen Sie Hinzufügen zu aus **Vorhandenes Übersetzungsprojekt** in der Liste &quot;Projekt&quot;aus und wählen Sie ein Projekt aus der Liste Vorhandenes Übersetzungsprojekt aus. Sie können diese Projekte nach der neuesten, aufsteigenden oder absteigenden Reihenfolge sortieren.

     >[!NOTE]
     >
     > Wenn es sich bei Ihrem vorhandenen Projekt um ein Scoping-Projekt handelt, ist in seinem Namen &quot;\(Scoping\)&quot;angehängt.

   - Wenn Sie den Bereich für die Übersetzung eines Projekts erstellen müssen, können Sie **Neues Scoping-Übersetzungsprojekt erstellen**. Dadurch werden die Kopien nicht zur Übersetzung gesendet und der ursprüngliche Übersetzungsstatus der Dateien wird beibehalten. Die Zielsprachkopie der referenzierten Themen, die zum Scoping gesendet werden, hat keine Auswirkungen.
1. Geben Sie im Feld **Projekttitel** einen Namen für das Projekt ein.
1. Klicks **Erstellen** , um ein neues Übersetzungsprojekt zu erstellen.

   Ein neues Übersetzungsprojekt wird mit der ausgewählten Version der Themen erstellt. Zu diesem Zeitpunkt wird eine Popup-Meldung angezeigt, die bestätigt, dass das Übersetzungsprojekt erstellt wurde. Sobald alle Zielsprachkopien im Übersetzungsprojekt verfügbar sind, erhalten Sie eine Benachrichtigung im Posteingang. Sobald die Zielsprachkopien im Übersetzungsprojekt verfügbar sind, können Sie den Übersetzungsauftrag starten. Weitere Informationen finden Sie unter [Übersetzungsauftrag starten](translation-first-time.md#id225IK030OE8).

   >[!NOTE]
   >
   > Wenn Sie die Übersetzung für ein oder mehrere Themen in einem Übersetzungsauftrag ablehnen, wird die **In Bearbeitung** Der Übersetzungsstatus aller abgelehnten Themen wird auf ihren ursprünglichen Status zurückgesetzt. Der Status der referenzierten Themen wird überprüft und entsprechend dem aktuellen Übersetzungsstatus zurückgesetzt. Außerdem werden die im Zielprojekt erstellten Übersetzungsdateien nicht gelöscht, selbst wenn die Übersetzung für sie abgelehnt wurde.

## Übersetzungsregeln hinzufügen

Mit AEM Guides können Ihre Administratoren die Übersetzungsregeln konfigurieren. Das SRX-Format (Segmentation Rules eXchange) ist ein Standard für den Austausch von Segmentierungsregeln zwischen verschiedenen Benutzern und verschiedenen Übersetzungsumgebungen. Sie können einen Ordner erstellen und Ihre benutzerdefinierten SRX-Dateien hinzufügen.

SRX-Dateien sollten als `<language-code>.srx`. Beispiel: en-US oder ar-AE.

>[!NOTE]
>Bei diesem Titel wird nicht zwischen Groß- und Kleinschreibung unterschieden, sodass Sie &quot;en-US&quot;, &quot;en-us&quot;oder &quot;EN-us&quot;haben können. Außerdem können AEM Hilfslinien &#39;-&#39; (Bindestrich) oder &#39;_&#39; (Unterstrich) auflösen. Sie können also &quot;en-US&quot;oder &quot;en_US&quot;haben.

Sie können diese Dateien auch in einen beliebigen Ordner unter AEM Asset-Stamm einfügen, der `./content/dam`.



Nachdem Sie den Ordner erstellt haben, der die SRX-Dateien enthält, können Sie den Ordnerpfad in der Konfiguration des SRX-Speicherorts für Übersetzungen in Ihrem Ordnerprofil hinzufügen.

Es wird empfohlen, für eine bessere Leistung nur SRX-Dateien im Ordner zu belassen, der im Ordnerprofil konfiguriert ist.


AEM Guides wählt die SRX-Regeln entsprechend der Ausgangssprache des Übersetzungsprojekts aus. Es sucht nach einer benutzerdefinierten SRX-Datei für eine Sprache. Wenn Sie keine benutzerdefinierte SRX-Datei definieren, werden die Regeln gemäß den vordefinierten Übersetzungsregeln ausgewählt.


Weitere Informationen zum Einrichten von globalen Profilen und Profilen auf Ordnerebene finden Sie unter *Authoring-Vorlagen konfigurieren* unter Adobe Experience Manager-Handbücher installieren und konfigurieren as a Cloud Service.

## Übergeben der Versionsbezeichnung an die Zielversion

Mit AEM Guides können Sie den Titel der Quelldatei an die Zieldatei übergeben. Auf diese Weise können Sie die Quellversion der übersetzten Datei leicht identifizieren.

Um die Bezeichnung der Quellversion zur Zielkopie hinzuzufügen, muss Ihr Systemadministrator die Option **Quellversionsbeschriftungen an die Zielversion weiterleiten** unter **Übersetzung** Registerkarte in **Editor-Einstellungen**.

Wenn Sie beispielsweise Quelldateien mit der Versionsbezeichnung haben `Release 1.0` auf sie angewendet werden, können Sie dann auch die Quellbezeichnung \(`Release 1.0`\) in die übersetzte Datei.

![](images/translation-pass-source-label.png){width="650" align="left"}

>[!NOTE]
>
> Der Quelltitel wird nur an eine Zielversion angehängt. Wenn Sie die Quellbeschriftung in eine andere Version verschieben, wird sie automatisch in der neuesten Zielbeschriftung angezeigt.

## Versionsunterschied für nicht synchronisierte Dateien anzeigen 

AEM Handbücher bieten die Möglichkeit, die Unterschiede zwischen der ausgewählten Version und der zuletzt übersetzten Quellversion der Themen zu überprüfen. Sie können die **Nicht synchronisiert** -Dateien basierend auf den vorgenommenen Änderungen.

![](images/translation-version-diff.png){width="650" align="left"}

Wählen Sie die **Unterschied anzeigen** icon \(![](images/show-difference-icon.svg)\) für ein Thema, um die Unterschiede zwischen der zuletzt übersetzten Version und der aktuellen Version der ausgewählten Datei anzuzeigen.

>[!NOTE]
>
> **Unterschied anzeigen** icon \(![](images/show-difference-icon.svg)\) wird nur für DITA-Dateien angezeigt, die den Übersetzungsstatus als **Nicht synchronisiert**.

Die **Versionsunterschiede** angezeigt. Sie zeigt die **Zuletzt übersetzte Version** und **Ausgewählte Version** auf der linken Seite. Im Vorschaufenster werden die Unterschiede zwischen der zuletzt übersetzten Version und der ausgewählten Version des Themas angezeigt.

![](images/version-diff.png){width="650" align="left"}

## Nicht synchronisierte Assets schließen

Wenn Sie Änderungen an einigen Assets vornehmen, werden diese Assets nicht mehr synchronisiert. Sie können die geänderten Assets entweder erneut übersetzen oder den Status Nicht synchronisiert verwerfen auswählen. Wenn Sie beispielsweise einige sehr geringfügige Änderungen vorgenommen haben, die eigentlich keine Übersetzung benötigen, können Sie ihren Status auf In Sync markieren.

So schließen Sie den Status Nicht synchronisiert :

1. Wählen Sie die nicht synchronisierten Assets aus, für die Sie den Status ändern möchten.
1. Wählen Sie die **Synchronisieren markieren** button \(![](images/translation-mark-in-sync-icon.svg)\) oben. Die **Synchronisieren markieren** angezeigt.

   ![](images/translation-mark-in-sync.png){width="550" align="left"}

1. Klicks **Force Sync**. Für die ausgewählten nicht synchronisierten Assets wird der Status auf Synchronisiert gesetzt.

>[!NOTE]
>
> **Synchronisieren markieren** button \(![](images/translation-mark-in-sync-icon.svg)\) wird nur für Assets angezeigt, deren Übersetzungsstatus &quot;Nicht synchronisiert&quot;lautet.

## In Bearbeitung befindliche Übersetzungsprojekte für eine Zuordnung oder ein Thema anzeigen

Einige Verweise auf Ihr Übersetzungs-Dashboard befinden sich möglicherweise in Bearbeitung. Diese Verweise haben **In Bearbeitung** Link unter **Übersetzungsstatus** Spalte. Wenn Sie auf den Link klicken, wird die **Laufende Projekte** wird geöffnet. Im Dialogfeld sehen Sie die Liste aller laufenden Übersetzungsprojekte \(zusammen mit der Zielsprache\), die die ausgewählte Referenz enthalten.

>[!NOTE]
>
> Sie können den Link In Bearbeitung für die übersetzten Projekte sehen, die in AEM Guides as a Cloud Service Version Februar 2023 oder höher erstellt wurden.

Klicken Sie im Dialogfeld auf den Namen der Referenz, um sie im Vorschaumodus zu öffnen. Sie können auch auf das Übersetzungsprojekt klicken, um die Übersetzung zu starten.

![](images/translation-in-progress.png){width="550" align="left"}


## Automatisches Löschen oder Deaktivieren eines abgeschlossenen Übersetzungsprojekts

>[!NOTE]
> 
>Diese Funktion steht für die neuen Übersetzungsprojekte zur Verfügung, die Sie mit Experience Manager Guides 2404 oder höher erstellen.  Es hat keine Auswirkungen auf bestehende Projekte.

Ihr Administrator kann die **Bereinigung des Übersetzungsprojekts nach Abschluss** Option unter **Übersetzung** Registerkarte in **Editor-Einstellungen** , um die Übersetzungsprojekte automatisch zu deaktivieren oder zu löschen.

Für eine effiziente Dokumentenverwaltung bieten Experience Manager-Handbücher die Möglichkeit, die Übersetzungsprojekte zu löschen, nachdem Sie die Übersetzung abgeschlossen haben.

Sie können die Übersetzungsprojekte auch deaktivieren, wenn Sie sie später verwenden möchten. Beim Löschen eines Projekts werden alle im Projekt vorhandenen Dateien und Ordner gelöscht. Durch das Deaktivieren eines Projekts wird es nicht gelöscht, sondern im Repository beibehalten. Sie können ein deaktiviertes Projekt jedoch nicht aktualisieren oder bearbeiten.  Das Löschen oder Deaktivieren eines Projekts hat keine Auswirkungen auf den Übersetzungsstatus von Verweisen.


**Übergeordnetes Thema:**[ Arbeiten mit dem Web-Editor](web-editor.md)
