---
title: Dateien und Ordner verwalten
description: Erfahren Sie, wie Sie Dateien und Ordner in AEM Guides verwalten. Kopieren Sie Dateien und Ordner in großen Mengen, ziehen Sie sie per Drag-and-Drop, löschen Sie sie, verschieben Sie sie und suchen Sie DITA-Inhalte.
exl-id: e5b44286-7ac3-49e4-9e6f-7bc8ae2fc935
feature: Content Management
role: User
source-git-commit: 6006cabdc11b80179833a21b4d99d2f6c3f968ee
workflow-type: tm+mt
source-wordcount: '3109'
ht-degree: 0%

---

# Dateien und Ordner verwalten {#id2116G0L08XA}

In diesem Abschnitt wird erläutert, wie AEM Guides mit grundlegenden Dateivorgängen wie dem Kopieren, Einfügen, Drag &amp; Drop und Löschen von Dateien umgeht. Die folgenden Szenarien sind möglich:

## Dateien kopieren und einfügen

**Wenn die Datei einen lesbaren Dateinamen hat**

- *Wenn die Datei mit demselben Namen nicht im Zielordner vorhanden ist*: Es wird eine neue Kopie der Datei erstellt und ihr auch eine UUID zugewiesen. Hier ist der Dateiname mit dem ursprünglichen Dateinamen identisch.
- *Wenn die Datei mit demselben Namen bereits im Zielordner vorhanden ist*: Eine neue Kopie der Datei wird mit dem Suffix \(z. B. filename0.extension\) erstellt. Der neu erstellten Datei wird auch eine UUID zugewiesen.


**Wenn der Dateiname auf einem UUID-Muster basiert**

- *Wenn die Datei mit demselben Namen nicht im Zielordner vorhanden ist*: Eine neue Kopie der Datei wird erstellt und ihr am neuen Speicherort wird auch eine neue UUID zugewiesen. Hier ist der Dateiname mit der UUID identisch.
- *Wenn die Datei mit demselben Namen bereits im Zielordner vorhanden ist*: Eine neue Kopie der Datei wird erstellt und ihr wird auch eine neue UUID zugewiesen. Der Dateiname entspricht der UUID.


## Ordner kopieren und einfügen

**Kopieren und Einfügen des Ordners am selben Speicherort**

- *Der Ordner enthält Dateien mit für Menschen lesbaren Dateinamen*: Eine neue Kopie des Ordners wird mit dem Suffix \(wie Ordnername0\) erstellt. Den Dateien im Ordner wird auch eine neue UUID zugewiesen. Die Dateinamen werden jedoch nicht geändert.

- *Der Ordner enthält Dateien mit Dateinamen, die auf einem UUID-Muster basieren*: Eine neue Kopie des Ordners wird mit dem Suffix \(wie Ordnername0\) erstellt. Eine neue UUID wird auch allen Dateien im neuen Ordner zugewiesen. Die Dateinamen werden ebenfalls geändert. Die Dateinamen sind mit der neuen UUID identisch.


**Kopieren und Einfügen des Ordners an einem anderen Speicherort**

- *Der Ordner enthält Dateien mit für Menschen lesbaren Dateinamen*: Eine neue Kopie des Ordners wird erstellt und eine neue UUID wird auch allen Dateien im Ordner am neuen Speicherort zugewiesen. Hier gibt es keine Änderung an den Ordnern oder Dateinamen.

- *Der Ordner enthält Dateien mit Dateinamen, die auf einem UUID-Muster basieren*: Eine neue Kopie des Ordners wird mit demselben Namen wie der ursprüngliche Ordner erstellt. Eine neue UUID wird auch allen Dateien im neuen Ordner zugewiesen. Die Dateinamen werden ebenfalls geändert. Die Dateinamen sind mit der neuen UUID identisch.


## Drag &amp; Drop von Dateien

**Drag-and-Drop mit lesbaren Dateinamen**

- *Verschieben Sie per Drag-and-Drop an die gleiche Stelle*: Sie erhalten die Optionen für **Vorhandene Datei(en\) überschreiben**, **Beibehalten Beide Dateien\(s\)** und eine Option zum Erstellen einer Version der vorhandenen Arbeitskopie.

  ![](images/uuid-human-readable-drag-drop-same-location.PNG){width="650" align="center"}

  Wenn Sie die Option &quot;**Vorhandene Datei überschreiben\(n\)**&quot;wählen, ersetzt die hochgeladene Datei die aktuelle Arbeitsversion der vorhandenen Datei am ursprünglichen Speicherort. Die UUID wird weder erstellt noch geändert.

  Wenn Sie die Option &quot;**Beides beibehalten\(s\)**&quot;wählen, wird eine neue Kopie der Datei mit dem Suffix &quot;\(z. B. filename0.extension\)&quot;erstellt. Eine neue UUID wird auch der neu kopierten Datei zugewiesen.

  Wenn Sie mit der Option Vorhandene Datei überschreiben\(s\) die Option zum Erstellen einer Version aus der vorhandenen Arbeitskopie auswählen, wird auch eine neue Version aus der Arbeitskopie des Dokuments erstellt.

  >[!NOTE]
  >
  > **Die Funktion &quot;Neue Version für hochgeladene Datei erstellen&quot;** muss von Ihrem Administrator aktiviert werden. Wenn diese Funktion aktiviert ist, wird eine neue Version für die hochgeladene Datei erstellt. Wenn die Option deaktiviert ist, wird keine Version der hochgeladenen Datei erstellt. Weitere Informationen finden Sie im Abschnitt *Neue Version für hochgeladene Datei erstellen* im Abschnitt Installieren und Konfigurieren von Adobe Experience Manager Guides as a Cloud Service .

  Wenn eine Datei bereits von einem anderen Benutzer zur Bearbeitung ausgecheckt wurde und Sie versuchen, die vorhandene Datei hochzuladen und zu überschreiben, schlägt sie fehl und zeigt einen Fehler an.

  >[!NOTE]
  >
  >Die Funktion **Ausgecheckte Datei beim Hochladen überschreiben** muss von Ihrem Administrator deaktiviert werden. Wenn diese Funktion aktiviert ist, können Sie ausgecheckte Dateien überschreiben. Wenn die Funktion nicht aktiviert ist, kann eine ausgecheckte Datei nicht überschrieben werden. Weitere Informationen finden Sie im Abschnitt *Ausgecheckte Datei beim Hochladen überschreiben* im Abschnitt Installieren und Konfigurieren von Adobe Experience Manager Guides as a Cloud Service.


- *Drag-and-Drop von Dateien an einem anderen Speicherort*: Eine neue Kopie der Datei wird erstellt und ihr wird auch eine neue UUID am neuen Speicherort zugewiesen. Hier ist der Dateiname mit dem ursprünglichen Dateinamen identisch.


**Ziehen und Ablegen von Dateinamen basierend auf einem UUID-Muster**

*Datei per Drag &amp; Drop am selben Speicherort ablegen*: Sie erhalten die Optionen zum **Überschreiben vorhandener Dateien\(n\)** zusammen mit der Option, eine Version der vorhandenen Arbeitskopie zu erstellen.

![](images/uuid-drag-drop-same-location.PNG){width="650" align="center"}

Wenn die Datei überschrieben wird, ändert sich weder der Dateiname noch die UUID.

Wenn Sie die Option &quot;**Version für vorhandene Arbeitskopie erstellen**&quot;auswählen, wird eine neue Version aus der Arbeitskopie des Dokuments erstellt. Die neue Datei wird hochgeladen, eine neue Version der Datei wird ebenfalls erstellt und als Arbeitskopie des Dokuments erstellt.

**Die Funktion &quot;Neue Version für hochgeladene Datei erstellen&quot;** muss von Ihrem Administrator aktiviert werden. Wenn diese Funktion aktiviert ist, wird eine neue Version für die hochgeladene Datei erstellt. Wenn die Option deaktiviert ist, wird keine Version der hochgeladenen Datei erstellt. Weitere Informationen finden Sie im Abschnitt *Neue Version für hochgeladene Datei erstellen* im Abschnitt Installieren und Konfigurieren von Adobe Experience Manager Guides as a Cloud Service .


*Datei an anderer Stelle per Drag &amp; Drop verschieben*: Sie erhalten die Optionen zum **Überschreiben vorhandener Dateien\(n\)**, zum **Verschieben von Dateien\(s\) an eine neue Position** und zur Option zum Erstellen einer Version der vorhandenen Arbeitskopie.

![](images/uuid-drag-drop-different-location.PNG){width="650" align="center"}

Wenn Sie die Option &quot;**Vorhandene Datei überschreiben\(n\)**&quot;wählen, ersetzt die hochgeladene Datei die vorhandene Datei am ursprünglichen Speicherort. Die UUID wird weder erstellt noch geändert.

Wenn Sie die Option **Datei verschieben\(en\) an neuen Speicherort** auswählen, wird die vorhandene Datei an den aktuellen Speicherort verschoben und dann mit der hochgeladenen Datei überschrieben. Wenn Sie eine Datei an den neuen Speicherort verschieben, werden vorhandene Verweise nicht von oder in die Datei beschädigt.

Wenn Sie die Option zum Erstellen einer Version aus der vorhandenen Kopie auswählen und die Dateien ersetzen oder verschieben, wird eine neue Version aus der Arbeitskopie des Dokuments erstellt. Die neue Datei wird entweder an der vorhandenen Stelle ersetzt oder an die neue Position verschoben.


## Stapelweises Verschieben von Dateien {#move-files-bulk}

AEM Guides verfügt über das Tool zum Verschieben von Stapeln, mit dem ein Administrator einen Ordner mit einer großen Anzahl von Dateien von einem Speicherort zum anderen verschieben kann. Mit diesem Tool können Sie Dateien in einem oder mehreren Ordnern einfach in einen anderen Ordner in Ihrem AEM-Repository verschieben. Eines der Hauptmerkmale dieses Tools ist, dass es nicht nur eine große Anzahl von Dateien verschiebt, sondern auch die Verweise auf und aus den verschobenen Dateien beibehält. Sie können die Anzahl der Dateien anpassen, die Sie in Stapeln verschieben können, ohne die Authoring- und Veröffentlichungsaufgaben zu beeinträchtigen.

>[!NOTE]
>
> Das Werkzeug zum Verschieben von Stapeln funktioniert nur auf Ordnerebene. Wenn Sie einzelne Themen- oder Zuordnungsdateien verschieben möchten, verwenden Sie das Werkzeug zum regulären Verschieben aus AEM Assets-Benutzeroberfläche.

Im Folgenden finden Sie einige Funktionen des Tools zum Verschieben von Stapeln:

- Sie können die Anzahl der in jedem Batch zu verarbeitenden Dateien anpassen. Dies erfordert möglicherweise, dass Sie einige Tests durchführen, bevor Sie zu einer optimalen Nummer gelangen, die Ihr System leicht handhaben kann.
- Autoren- und Veröffentlichungsdienste werden reibungslos und ohne Unterbrechung des Verschiebevorgangs ausgeführt.
- Sie haben die vollständige Kontrolle über das Zeitintervall zwischen den nachfolgenden \(ausgeführten\) Batch-Prozessen. Dieses Zeitintervall stellt sicher, dass die Nachbearbeitung abgeschlossen ist, bevor der nächste Dateistapel gestartet wird.

- Automatische Verarbeitung von Ordnern mit demselben Namen. Mit dieser Funktion wird sichergestellt, dass Ordner, die denselben Namen aufweisen, nicht überschrieben werden.

- Automatische Verarbeitung von Verweisen auf und aus den zu verschiebenden Dateien.


Beachten Sie die folgenden Punkte, bevor Sie den Batch-Prozess ausführen:

- Wenn Sie Themen verschieben möchten, die derzeit geprüft werden, müssen Sie den Überprüfungsprozess für alle diese Themen schließen, bevor Sie sie verschieben. Wenn Sie die Überprüfungsaufgabe nicht schließen, wird der Überprüfungsprozess unterbrochen.
- Sie dürfen jederzeit nur einen einzigen Massenverschiebungsvorgang auf dem System ausführen. Dadurch wird eine ordnungsgemäße Verarbeitung der Verweise auf und von den verschobenen Themen sichergestellt.


Um Dateien stapelweise zu verschieben, führen Sie die folgenden Schritte aus:

1. Klicken Sie oben auf den Adobe Experience Manager-Link und wählen Sie **Tools** aus.
1. Wählen Sie **Guides** aus der Liste der Tools aus.
1. Klicken Sie auf die Kachel **Bulk Move Tool** .
1. Die Seite mit dem Werkzeug zum Verschieben von Stapeln wird je nach Einrichtung angezeigt. Geben Sie die folgenden Details auf der Seite **Bulk Move Tool** an:

   <details>

   <summary> Cloud Service und On-Premise-UUID-basiertes Dateisystem </summary>

   ![](images/bulk-move-tool-uuid.png){width="650" align="center"}

   >[!TIP]
   >
   > Auswahl <img src="images/info-icon.svg" width="25">   in der Nähe eines Felds, um weitere Details dazu anzuzeigen.


   - **Suffix zu duplizierten Ordnern hinzufügen**: Wenn Sie Ordner mit demselben Namen verschieben, müssen Sie diese Option auswählen. Im vorherigen Screenshot enthält der Pfad **Source** beispielsweise den Namen der zu verschiebenden Ordner. Der Ordner &quot;topic&quot;befindet sich an zwei verschiedenen Speicherorten - Test-A und Test-B. Wenn Sie diese Option auswählen, werden die Ordner erfolgreich verschoben. Der erste verschobene Ordner heißt &quot;topic&quot;, während der zweite Ordner &quot;topic0&quot;heißt. Beim Verschieben wird den Ordnern mit demselben Namen ein Suffix aus der sequenziellen Reihe \(0, 1, 2 usw.) hinzugefügt.

     Wenn Sie Ordner mit demselben Namen verschieben, ohne diese Option auszuwählen, wird der Vorgang mit einer Meldung abgebrochen.

   - **Source-Pfad\(s\)**: Geben Sie den Speicherort der Ordner an, die Sie verschieben möchten.

      - Wählen Sie **Ordner durchsuchen** aus  <img src="images/browse-folder-icon.svg" width="25">    , um das Dialogfeld Datei durchsuchen zu öffnen. Wählen Sie die Ordner aus, die Sie verschieben möchten, und klicken Sie auf **Auswählen** , um den Vorgang abzuschließen.

      - Sie können auch den Quellspeicherort eingeben oder kopieren und einfügen. Drücken Sie die Eingabetaste , um den Ordner zur Liste hinzuzufügen.

        Die ausgewählten Ordner werden zusammen mit ihrem Pfad aufgelistet. Bewegen Sie den Mauszeiger über das Ordner-Tag, um den vollständigen Pfad anzuzeigen.
      - Sie können auch einen beliebigen Ordner entfernen, indem Sie auf **Entfernen** klicken <img src="images/remove-folder.svg" width="25"> in der Nähe des Ordners


   - **Zielpfad**: Geben Sie den Speicherort an, an den Sie die Quellordner verschieben möchten.

      - Wählen Sie **Ordner durchsuchen** aus <img src="images/browse-folder-icon.svg" width="25"> , um das Dialogfeld &quot;Datei durchsuchen&quot;zu öffnen. Wählen Sie den Speicherort aus, an den Sie die Quellordner verschieben möchten. und klicken Sie auf Auswählen , um den Vorgang abzuschließen.
      - Sie können auch den Zielpfad eingeben oder kopieren und einfügen.

     Der ausgewählte Ordner wird zusammen mit seinem Pfad im Textfeld angezeigt.


   - Klicken Sie auf **Massenverschiebung**.

     Das System startet das Verschieben von Dateien von der Quelle an den Zielspeicherort. Nach Abschluss des Prozesses wird rechts auf der Seite eine Zusammenfassung des Verschiebevorgangs angezeigt.

     ![](images/bulk-move-summary-uuid.png){width="650" align="center"}

   </details>

   <details>

   <summary> On-Premise-Nicht-UUID-basiertes Dateisystem </summary>

   ![](images/bulk-move-tool-non-uuid.png){width="650" align="center"}

   >[!TIP]
   >
   > Auswahl <img src="images/info-icon.svg" width="25">   in der Nähe eines Felds, um weitere Details dazu anzuzeigen.

   - **Stapelgröße**: Geben Sie die Anzahl der Dateien an, die in einem Batch verschoben werden sollen. Die Standardwerte bei 50 Dateien.
   - **Schlafintervall (Sekunden)**: Geben Sie die Zeit in Sekunden an, die der Prozess warten soll, bevor der nächste Batch gestartet wird. Während dieses Ruhezeitintervalls behebt das System die Verweise auf und aus den verschobenen Dateien. Das standardmäßige Schlafintervall beträgt 60 Sekunden.


   - **Suffix zu duplizierten Ordnern hinzufügen**: Wenn Sie Ordner mit demselben Namen verschieben, müssen Sie diese Option auswählen. Im vorherigen Screenshot enthält der **Source-Pfad** beispielsweise den Namen der zu verschiebenden Ordner. Der Ordner &quot;topic&quot;befindet sich an zwei verschiedenen Speicherorten - Test-A und Test-B. Wenn Sie diese Option auswählen, werden die Ordner erfolgreich verschoben. Der erste verschobene Ordner heißt &quot;topic&quot;, während der zweite Ordner &quot;topic0&quot;heißt. Beim Verschieben wird den Ordnern mit demselben Namen ein Suffix aus der sequenziellen Reihe \(0, 1, 2 usw.) hinzugefügt.

     Wenn Sie Ordner mit demselben Namen verschieben, ohne diese Option auszuwählen, wird der Vorgang mit einer Meldung abgebrochen.

   - **Verweise auf ausgecheckte Dateien aktualisieren**: Wenn Sie Ordner verschieben, die ausgecheckte Dateien enthalten, wird empfohlen, diese Option auszuwählen. Wenn Sie diese Option auswählen, werden alle ausgecheckten Dateien gespeichert und mit einer neuen Revision eingecheckt. Diese neue Revision wird dann an den Zielort verschoben.

     Wenn Sie diese Option nicht auswählen, werden die ausgecheckten Dateien in den Zielordner im gleichen ausgecheckten Status verschoben. In diesem sich bewegenden Prozess kann es jedoch zu Datenverlust kommen.


   - **Source-Pfad\(s\)**: Geben Sie den Speicherort der Ordner an, die Sie verschieben möchten.

      - Wählen Sie **Ordner durchsuchen** aus  <img src="images/browse-folder-icon.svg" width="25">    , um das Dialogfeld Datei durchsuchen zu öffnen. Wählen Sie die Ordner aus, die Sie verschieben möchten, und klicken Sie auf **Auswählen** , um den Vorgang abzuschließen.

      - Sie können auch den Quellspeicherort eingeben oder kopieren und einfügen. Drücken Sie die Eingabetaste , um den Ordner zur Liste hinzuzufügen.

        Die ausgewählten Ordner werden zusammen mit ihrem Pfad aufgelistet. Bewegen Sie den Mauszeiger über das Ordner-Tag, um den vollständigen Pfad anzuzeigen.
      - Sie können auch einen beliebigen Ordner entfernen, indem Sie auf **Entfernen** klicken <img src="images/remove-folder.svg" width="25"> in der Nähe des Ordners


   - **Zielpfad**: Geben Sie den Speicherort an, an den Sie die Quellordner verschieben möchten.

      - Wählen Sie **Ordner durchsuchen** aus <img src="images/browse-folder-icon.svg" width="25"> , um das Dialogfeld &quot;Datei durchsuchen&quot;zu öffnen. Wählen Sie den Speicherort aus, an den Sie die Quellordner verschieben möchten. und klicken Sie auf Auswählen , um den Vorgang abzuschließen.
      - Sie können auch den Zielpfad eingeben oder kopieren und einfügen.

        Der ausgewählte Ordner wird zusammen mit seinem Pfad im Textfeld angezeigt.

   - Klicken Sie auf **Massenverschiebung**.

     Das System startet das Verschieben von Dateien von der Quelle an den Zielspeicherort. Nach Abschluss des Prozesses wird rechts auf der Seite eine Zusammenfassung des Verschiebevorgangs angezeigt.
     ![](images/bulk-move-summary-non-uuid.png){width="650" align="center"}
</details>

## DITA-Inhalt durchsuchen

Standardmäßig erkennt AEM DITA-Inhalte nicht, bietet daher keinen Mechanismus zum Durchsuchen von DITA-Inhalten in seinem Repository. AEM Guides fügt eine Ebene über AEM hinzu, die es AEM ermöglicht, DITA-Inhalte zu verstehen und zu verarbeiten. Mit der Funktion &quot;DITA-Inhalt durchsuchen&quot;in AEM Guides können Sie in AEM Repository nach DITA-Inhalten suchen.

>[!NOTE]
>
>Ihr Systemadministrator kann die Suchkomponente **DITA Element** konfigurieren und dann die Funktion über die AEM Assets-Benutzeroberfläche verwenden. Weitere Informationen finden Sie im Abschnitt *DITA-Element-Suchkomponente in der Assets-Benutzeroberfläche hinzufügen* unter Installieren und Konfigurieren von Adobe Experience Manager Guides as a Cloud Service .

Mithilfe der Suchfunktion haben Sie folgende Möglichkeiten:

- Suche nach DITA-Inhalt basierend auf einem Elementwert, z. B. `author`= xml
- Suche nach DITA-Inhalt basierend auf einem Attributwert, z. B. `@platform`= windows
- Verwenden Sie eine Kombination aus DITA-Element und Attributwert, z. B. `author`= xml `AND` `@platform`= windows

Führen Sie die folgenden Schritte aus, um in AEM Repository nach DITA-Inhalten zu suchen:

1. Öffnen Sie die Assets-Benutzeroberfläche.

1. Wählen Sie in der linken Leiste **Filter** aus.

   ![](images/left-rail-filter.png){width="450" align="center"}

   Die Inhaltsfilteroptionen werden in der linken Leiste angezeigt. Außerdem finden Sie die Filteroption - DITA-Element, das zum Filtern von DITA-Inhalten verwendet wird.

   ![](images/dita-element-search.png){width="450" align="center"}

1. *\(Optional\)* Suchen Sie im Feld **Suchverzeichnis auswählen** nach dem Ort, nach dem Sie suchen möchten.

1. Geben Sie im Filter **DITA-Element** den **Elementnamen**, das **Attribut** und einen Wert an, nach dem Sie suchen möchten. Um beispielsweise nach Dokumenten zu suchen, deren Element `author` vom Ersteller `@type` ist, müssen Sie die Informationen wie im folgenden Screenshot gezeigt angeben:

   ![](images/search-params.png){width="650" align="center"}

   Die im Filter **DITA Element** eingegebenen Suchkriterien werden oben in der Suchleiste angezeigt. Die Dateien, die den Suchkriterien entsprechen, werden im Bereich **Suchergebnisse** angezeigt.

   Beachten Sie beim Festlegen der Suchkriterien die folgenden Punkte:

   - Um nach einer genauen Wortgruppe zu suchen, geben Sie die Wortgruppe in das Feld Wert in Anführungszeichen `"`Phrase suchen`"` ein.
   - Sie können bis zu 3 DITA-Element-Suchkriterien hinzufügen.
   - Wenn Sie mehrere Suchkriterien angeben, werden alle mit der UND-Logik kombiniert.
   - Sie können in Ihren Suchkriterien keine Platzhalterzeichen verwenden. Um beispielsweise nach Plattform \(Attribut\) mit dem Wert Windows zu suchen, können Sie nicht \*Formular oder Windows?s angeben.

**Checkout-Statusfilter in der Suche**

Zusätzlich zum DITA-Elementfilter können Sie mit AEM Guides auch nach Inhalten suchen, die auf ihrem Checkout-Status basieren. Dies ist hilfreich, wenn Sie Dateien schnell herausfiltern möchten, die derzeit von Ihnen ausgecheckt wurden und wieder einchecken möchten.

Führen Sie die folgenden Schritte aus, um nach Dateien basierend auf ihrem Checkout-Status zu suchen:

1. Öffnen Sie die Assets-Benutzeroberfläche.

1. Klicken Sie in der linken Leiste auf **Filter** .
1. Geben Sie Ihren Suchbegriff in die Suchleiste ein.
1. Wenden Sie die erforderlichen Filter aus der linken Leiste an.

   Sie können beispielsweise den Filter **Checkout-Status** anwenden, um die ausgecheckten oder eingecheckten Themen anzuzeigen. Sie können diese Liste weiter verfeinern, indem Sie den Benutzer oder die Gruppe aus der Liste Ausgecheckt von auswählen.

   Ihr Suchergebnis wird angezeigt.


## Dateien löschen

Das Löschen von Dateien aus AEM Repository ist eine eingeschränkte Funktion, die von Ihrem Systemadministrator gesteuert wird. Je nach Konfiguration kann das Löschen von Dateien eingeschränkt werden, wenn sie:

- Ausgecheckt
- Eingehende oder ausgehende Verweise haben

Sie können Dateien auch nur löschen, wenn Sie einer bestimmten Benutzergruppe angehören, die zum Löschen von Dateien berechtigt ist.

>[!NOTE]
>
> Weitere Informationen zu den Konfigurationen für die Dateiverwaltung finden Sie in den Abschnitten *Löschen ausgecheckter Dateien verhindern* und *Löschen referenzierter Dateien verhindern* in der as a Cloud Services Installieren und Konfigurieren von Adobe Experience Manager Guides .

Wenn Ihr Administrator allen Benutzern die Berechtigung zum Löschen der Datei erteilt hat, wird beim Löschen von Dateien mit Verweisen die folgende Meldung angezeigt:

![](images/allow_unsafe_delete-force-delete.PNG){width="650" align="center"}

In diesem Szenario können Sie Dateien erzwungen löschen, ohne die eingehenden oder ausgehenden Verweise aus den Dateien zu entfernen.

Wenn die Löschberechtigungen einer bestimmten Benutzergruppe zugewiesen werden, wird auch die oben genannte Meldung für Benutzer dieser Gruppe angezeigt. Für andere Benutzer wird jedoch die folgende Meldung angezeigt:

![](images/allow_unsafe_delete_for_delete_assets_group.PNG){width="650" align="center"}

In diesem Szenario dürfen Benutzer Dateien erst löschen, nachdem alle eingehenden und ausgehenden Verweise entfernt wurden.

## Arbeiten mit Mediendateien

Mediendateien wie Bilder und Videos sind ein integraler Bestandteil Ihres Inhalts. Beim Hochladen und Verwalten Ihres Inhalts können Sie auch mit Mediendateien arbeiten.

Wenn sich Ihre Mediendatei geändert hat, können Sie die Dateien im **Versionsverlauf** finden und in der Vorschau anzeigen. So erhalten Sie Informationen zu den Änderungen in den verschiedenen Versionen einer Mediendatei:

1. Rufen Sie die Datei in der **Assets-Benutzeroberfläche** auf.
1. Wählen Sie die Datei aus, für die Sie den Versionsverlauf anzeigen möchten.
1. Klicken Sie in der linken Leiste auf **Versionsverlauf** und wählen Sie eine Version aus.
1. Sie können auch die Miniaturansichten der verschiedenen Versionen unter Versionsverlauf anzeigen.

   ![](images/media-version-history-icon.png){width="800" align="center"}

1. Wählen Sie in den aufgelisteten Versionen die Version aus, die Sie als Basisversion verwenden möchten, und klicken Sie auf **Vorschau der Version anzeigen**. Die Vorschau der ausgewählten Version wird im Fenster Versionsvorschau angezeigt.

   ![](images/media-version-preview.png){width="650" align="center"}


**Übergeordnetes Thema:**[ Inhalt verwalten](authoring.md)
