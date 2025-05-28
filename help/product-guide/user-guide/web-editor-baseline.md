---
title: Erstellen und Verwalten von Baselines über die Zuordnungskonsole
description: Erstellen und verwalten Sie Baselines über die Zuordnungskonsole in Adobe Experience Manager Guides. Erfahren Sie, wie Sie Baselines auf der Grundlage von Kennzeichnungen erstellen und Filter auf die Baselines anwenden.
exl-id: 14f87bdd-3042-46f9-853e-e9ded81b10ed
feature: Authoring, Features of Web Editor, Publishing
role: User
source-git-commit: c7e76de14a3dd63eff794ecca16ebbccb3cb2d8a
workflow-type: tm+mt
source-wordcount: '1881'
ht-degree: 0%

---

# Erstellen und Verwalten von Baselines über die Map-Konsole {#id223MB0ZF043}

Mit der Funktion „Grundeinstellungen“ können Sie eine Version Ihrer Themen und Assets erstellen, die dann zur Veröffentlichung oder Übersetzung verwendet werden können. Wenn Ihre DITA-Zuordnung beispielsweise über `topicA` und `imageA` verfügt, können Sie eine Grundlinie erstellen, die die 3. Version von `topicA`, aber die 4. Version von `ImageA` verwendet. Sobald Sie eine Grundlinie eingerichtet haben, können Sie Themen aus verschiedenen Versionen in einem einzigen Schritt veröffentlichen oder übersetzen.

Die Auswahl einer Baseline ist für Ausgabevorgaben optional, und eine DITA-Zuordnung kann mehr als eine Baseline haben. Jede Ausgabevorgabe innerhalb einer DITA-Zuordnung kann jedoch nur mit einer einzigen Baseline verknüpft werden. Wenn zum Zeitpunkt der Veröffentlichung keine Baseline angegeben ist, wird die Ausgabe mit der neuesten Version des Inhalts veröffentlicht.

Ebenso ist die Auswahl einer Baseline zur Übersetzung von Inhalten optional. Wenn Sie sich jedoch dafür entscheiden, Inhalte mithilfe einer Baseline zu übersetzen, werden die Inhalte der Baseline zusammen mit den übersetzten Kopien ebenfalls gespeichert. Anschließend können Sie die übersetzte Baseline verwenden, um weitere Vorgänge auszuführen, z. B. um sie für externe Herausgeber freizugeben oder zu archivieren.


>[!TIP]
>
> Es wird empfohlen, diese Grundlinien-Funktion über die Zuordnungskonsole zu verwenden. Sie können jedoch auch &quot;[ Dashboard verwenden, um Baselines zu erstellen und zu verwalten](./generate-output-use-baseline-for-publishing.md).

Auf der Registerkarte **Baseline** können Sie die folgenden Aktionen ausführen:

- [Erstellen einer Baseline](#create-a-baseline)
- [Baselines verwalten](#manage-baselines)


## Erstellen einer Baseline

Sie können eine Baseline über die Zuordnungskonsole erstellen, indem Sie die folgenden Schritte ausführen:

1. [Öffnen Sie die DITA-Zuordnungsdatei in der Zuordnungskonsole](./open-files-map-console.md).
1. Navigieren Sie zur Registerkarte **Baseline** und wählen Sie oben rechts das Symbol + aus, um mit der Erstellung einer Baseline zu beginnen.
1. Geben **im Dialogfeld &quot;** Baseline“ die folgenden Details an:

   ![Baseline-Bedienfeld](images/baseline-manage.png){width="500" align="left"}

   - Geben Sie einen Namen für die Baseline in das Feld **Name** ein.
   - Wählen Sie **Konfiguration** die Option [Manuelles Update](#configuring-baseline-for-manual-update) oder [Automatisches Update](#configuring-baseline-for-automatic-update).
   - Wählen Sie **Anwenden** aus.

Die Baseline wird erstellt. Die Basiserstellung erfolgt asynchron, sodass Sie weiterhin an anderen Dateien arbeiten können. Nachdem die Baseline erstellt wurde, wird eine Popup-Meldung angezeigt, die bestätigt, dass die Baseline erstellt wurde, und Sie erhalten auch eine Benachrichtigung im Posteingang für dieselbe Baseline.

### Konfigurieren von Baseline für die manuelle Aktualisierung

Sie können manuell eine statische Grundlinie mit einer bestimmten Version der Themen und referenzierten Inhalten erstellen, die an einem bestimmten Datum und zu einer bestimmten Uhrzeit verfügbar sind, oder mit einer Beschriftung, die für eine Version der Themen definiert ist:

Wählen **in „Version basierend auf auswählen** eine der folgenden Optionen aus:

- **Datum** : Wählt die Version der Themen zum angegebenen Zeitpunkt aus.
- **Beschriftung**: Wählen Sie diese Option aus, um die Themen entsprechend der ihnen zugewiesenen Beschriftung auszuwählen. Wenn für die Themen Beschriftungen angegeben sind, werden die Beschriftungen in der Dropdown-Liste aufgelistet. Sie können einen Titel aus der Liste auswählen. Sie können dem Textfeld auch einen Titel hinzufügen.

  >[!NOTE]
  >
  > Bei der Auswahl von Kennzeichnungen bleibt das Kennzeichnungsladeprogramm sichtbar, bis alle Kennzeichnungen erfolgreich abgerufen und vollständig geladen wurden. Nach dem Laden werden die Kennzeichnungen in alphabetischer Reihenfolge ohne Unterscheidung der Groß-/Kleinschreibung angezeigt. Sie werden in Stapeln von 20 abgerufen, wobei unendlicher Bildlauf in der Dropdown-Liste aktiviert ist, um beim Scrollen zusätzliche Stapel zu laden.

  Für die direkten Verweise in statischen Basislinien werden die Beschriftungen aus der zuletzt gespeicherten Version der Zuordnung abgerufen. Beispiel: Sie haben die Bezeichnungen `Label Release 1.0` und `Label Release 1.1` für die Versionen 1.0 und 1.1 von Thema A erstellt und anschließend Thema A zu der als Version 1.0 gespeicherten Zuordnung hinzugefügt. In diesem Fall können Sie die Beschriftungen `Label Release 1.0` und `Label Release 1.1` in der Dropdown-Liste für statische Baseline-Beschriftungen anzeigen.

  Wenn Sie auf **Beschriftung“ klicken** können Sie die direkten und indirekten Verweise auswählen.
   - Bei direkten Verweisen innerhalb der DITA-Zuordnung haben Sie die Möglichkeit, die neueste Version von Themen zu verwenden, auf die nicht die angegebene Kennzeichnung angewendet wurde.

     >[!NOTE]
     >
     > Wenn Sie eine nicht vorhandene Beschriftung eingeben und die Option **Keine Baseline erstellen** wählen, schlägt die Baseline-Erstellung fehl und gibt im Baseline-Bedienfeld eine Fehlermeldung in der Nähe des Baseline-Namens aus.

   - Für indirekte Verweise innerhalb der DITA-Zuordnung haben Sie eine zusätzliche Möglichkeit, die neueste Version von Themen zu verwenden, auf die nicht die angegebene Kennzeichnung angewendet wurde. Sie können für **referenzierten Inhalt auch** Automatische Auswahl“ auswählen. Das System wählt dann automatisch die Version des referenzierten Inhalts aus, die der Version des Inhalts entspricht, auf den verwiesen wird.

Nachdem Sie eine Bezeichnung oder Version als Datum ausgewählt haben, werden alle referenzierten Themen und Mediendateien in der Zuordnung entsprechend ausgewählt. Diese Themenauswahl wird nicht auf der Benutzeroberfläche angezeigt, sondern im Backend gespeichert.

### Konfigurieren von Baseline für die automatische Aktualisierung

Wählen Sie diese Option für die Basiserstellung aus, um die Themen automatisch entsprechend dem Titel auszuwählen, der auf sie angewendet wurde.

Baselines, die mithilfe der automatischen Aktualisierungskonfiguration erstellt wurden, werden dynamisch aktualisiert. Wenn Sie eine Baseline generieren, eine Baseline herunterladen oder ein Übersetzungsprojekt mithilfe einer Baseline erstellen, werden die Dateien basierend auf den aktualisierten Beschriftungen dynamisch ausgewählt. Wenn Sie beispielsweise Version 1.2 eines Themas mit der Bezeichnung Release 1.0 für die Grundlinie und Version 1.5 mit der Bezeichnung Release 1.0 aktualisiert haben, wird die Grundlinie dynamisch aktualisiert und Version 1.5 wird verwendet.

![Erstellen einer Baseline](images/dynamic-baseline.png){width="300" align="left"}

- **Kennzeichnungen**: Wenn für die Themen Kennzeichnungen angegeben sind, verwenden Sie das **Kennzeichnungen** zur Auswahl aus den [aufgelisteten Kennzeichnungen](#labels-list).

  Die zuerst ausgewählten Bezeichnungen erhalten gegenüber den späteren eine höhere Priorität.

  >[!NOTE]
  >
  >Während die Beschriftungen abgerufen werden, wird ein Lader angezeigt und die Dropdown-Liste ist deaktiviert.

  Bei dynamischen Baselines werden die Beschriftungen aus der zuletzt gespeicherten Version und der aktuellen Arbeitskopie der Zuordnung abgerufen. Wenn Sie beispielsweise Kennzeichnungen erstellt haben   `Label Release A.1.0 ` und `Label Release A.1.1` für die Versionen 1.0 und 1.1 von Thema A und Beschriftungen `Label Release B.1.0` und `Label Release B.1.1` für die Versionen 1.0 und 1.1 von Thema B . Anschließend können Sie Thema A zu Map A in Version 1.0 und Thema B zu Map A in 1.0* (Arbeitskopie) hinzufügen. In diesem Fall können Sie `Label Release A.1.0 `, `Label Release A.1.1`, `Label Release B.1.0` und `Label Release B.1.1` in der Dropdown-Liste der dynamischen Baseline-Beschriftungen anzeigen.
- **Indirekte Verweise**: Für indirekte Verweise innerhalb der DITA-Karte werden Ihnen die folgenden Optionen bereitgestellt:

   - **Automatisch auswählen**: Sie können für den referenzierten Inhalt **Automatisch auswählen** und das System wählt automatisch die Version des referenzierten Inhalts aus, die der Version des Inhalts entspricht, auf den verwiesen wird.
   - **Ausgewählte Beschriftung verwenden**: Sie können eine Grundlinie erstellen, bei der die ausgewählte Beschriftung für eine Version von Themen definiert ist.
   - **Aktuelle Version oder Arbeitskopie verwenden**: Verwenden Sie die neueste Version von Themen, auf die nicht die angegebene Beschriftung angewendet wurde, oder wenn keine Version erstellt wurde, verwenden Sie die Arbeitskopie der Themen, um die Grundlinie zu erstellen.

## Baselines verwalten

Sie können Ihre vorhandenen Grundlinien mithilfe der verschiedenen Funktionen im Grundlinien-Dashboard verwalten.

- Sie können mit dem Textfeld im Bedienfeld „Baseline“ nach einer vorhandenen Baseline suchen. Verwenden Sie das Symbol **Filter anwenden**, um alle Baselines anzuzeigen oder die Baselines mit dem Erstellungsstatus „Erfolgreich“, „In Bearbeitung“ oder „Fehlgeschlagen“ aufzulisten.
- Verwenden Sie das Symbol **Aktualisieren** im Bedienfeld „Baseline“, um erneut alle Baselines zu überprüfen und eine neue Liste von Baselines für die DITA-Map anzuzeigen, die in der Kartenansicht geöffnet wird.
- Wählen Sie die Baseline aus, um den Inhalt einer vorhandenen statischen Baseline im Bedienfeld **Baseline** anzuzeigen oder zu bearbeiten. Das Baseline-Bearbeitungsfenster zeigt die DITA-Zuordnungsdatei, den Inhalt oder die Themen der Zuordnung und den referenzierten Inhalt an.

  >[!NOTE]
  >
  >Der Bearbeitungsvorgang für statische Grundlinien wird nur für eine geringe Anzahl von Referenzänderungen empfohlen. Der Bearbeitungsvorgang wird nicht empfohlen, die Version der DITA-Hauptzuordnung zu ändern, da alle Verweise neu berechnet werden müssen. Dies kann bei großen DITA-Zuordnungen zu einem Fehler bei der grundlegenden Aktualisierung führen. Für die größeren DITA-Zuordnungen können Sie eine neue Grundlinie erstellen oder die Eigenschaften der Grundlinie bearbeiten.
  >
  >Der Bearbeitungsvorgang im Fall einer dynamischen Baseline ermöglicht es Ihnen, die Eigenschaften der Baseline zu bearbeiten, da die Referenzen für dynamische Baselines zur Laufzeit mithilfe der Kennzeichnungen generiert werden.

  ![Optionen einer Baseline](images/baseline-options.png){width="500" align="left"}

### Für eine vorhandene Baseline verfügbare Aktionen

Sie können auch die folgenden Vorgänge für die Grundlinie über das Menü Optionen ausführen:

**Duplizieren einer Baseline**

Sie können eine Baseline duplizieren und entsprechend Ihren Anforderungen ändern.

![Duplizieren einer Baseline](images/baseline-duplicate.png){width="300" align="left"}
*Duplizieren Sie eine Baseline basierend auf einer Beschriftung oder erstellen Sie eine exakte Kopie.*

1. Wählen **Duplizieren** aus dem Menü Optionen einer Baseline. Das **Basislinie duplizieren** wird geöffnet.
>[!NOTE]
>
>Der Standardname der Baseline lautet `<selected baseline name>`_suffix (wie sample-baseline_1). Sie können den Namen Ihren Anforderungen entsprechend ändern.

   In **Version basierend auswählen** können Sie entweder die Option **Exakte Kopie** oder die Option **Beschriftung** auswählen:

   - **Exakte Kopie**: Experience Manager Guides wählt dieselbe Version aller Themen aus und erstellt eine exakte Kopie der duplizierten Baseline.
   - **Beschriftung**: In der Dropdown-Liste können Sie eine der [ Beschriftungen ](#labels-list). Experience Manager Guides wählt die Versionen der Themen aus, für die die ausgewählte Beschriftung definiert ist, während für die übrigen Themen die Version aus der duplizierten Baseline ausgewählt wird. Sie wählen beispielsweise den Titel `Release 1.0` aus der Dropdown-Liste aus und wählen dann die Versionen der Themen aus, für die Sie diesen Titel definiert haben. Bei allen anderen Themen wird die Version aus der duplizierten Baseline ausgewählt.
1. Wählen Sie **Duplizieren** aus.

- **Umbenennen** oder **Löschen** einer vorhandenen Baseline**.
- **Verwalten von Beschriftungen** mit denen Sie vorhandene Beschriftungen für statische Baselines hinzufügen, entfernen oder ändern können. Wenn Ihr Administrator vordefinierte Kennzeichnungen konfiguriert hat, werden Sie diese Kennzeichnungen in der Dropdown-Liste Kennzeichnung hinzufügen angezeigt. Weitere Informationen zum Hinzufügen von Beschriftungen finden Sie unter [Beschriftungen verwenden](web-editor-use-label.md#).

  >[!NOTE]
  >
  > Der Prozess zum Hinzufügen oder Entfernen von Kennzeichnungen erfolgt asynchron, sodass Sie weiterhin an anderen Dateien arbeiten können. Nachdem die Kennzeichnung hinzugefügt oder entfernt wurde, wird eine Popup-Meldung angezeigt, die bestätigt, dass die Kennzeichnung hinzugefügt oder entfernt wurde, und Sie erhalten auch eine Benachrichtigung im Posteingang für dieselbe Kennzeichnung.

- **Eigenschaften bearbeiten** einer vorhandenen statischen Baseline, die Sie beim Erstellen der Baseline festgelegt haben.
- **Baseline exportieren** exportiert einen Schnappschuss der Baseline in die Excel-Datei von Microsoft, einschließlich aller wichtigen Details wie Titel, Dateiname, Dateityp, Versionsnummer, Dokumentstatus und anderer relevanter Informationen.


### Beschriftungsliste {#labels-list}

Die im Dropdown-Menü aufgelisteten Bezeichnungen basieren auf den folgenden Kriterien:
- Die Beschriftungen sollten einer der Versionen der Themen in der DITA-Map hinzugefügt werden (auf der die Baseline erstellt wird).
- Und nur die Verweise der ersten Ebene (Themen oder Unterkarten) der DITA-Karte werden für die Auswahl der Beschriftungen berücksichtigt.

## Baseline-Filter

Mithilfe des Symbols Filter im Bedienfeld **Baseline-Filter** können Sie Filter auf die Baseline anwenden, die im Baseline-Bearbeitungsfenster geöffnet ist:

![Baseline-Filter](images/baseline-filter.png){width="300" align="left"}

- Filtern Sie die Dateien nach Dateinamen oder Dateispeicherort.
- Filtern Sie die Dateien anhand der Werte für verschiedene Spalten wie Dateityp, Referenztyp usw.
- Auswahl der Spalten, die im Baseline-Bearbeitungsfenster angezeigt werden sollen.

>[!NOTE]
>
> Sie können eine Spaltenüberschrift auswählen und die Dateien basierend auf den Spalten im Baseline-Bearbeitungsfenster sortieren.

**Speichern oder Zurücksetzen einer Baseline**

Nachdem Sie die Baseline bearbeitet haben, klicken Sie auf **Speichern**, um die Änderungen an der Baseline zu speichern. Sie können auf **Zurücksetzen** klicken, wenn Sie die Änderung nicht speichern und die Grundlinie zurücksetzen möchten. Bei Auswahl von **Zurücksetzen** wird eine Warnung angezeigt, dass Ihre nicht gespeicherten Änderungen verloren gehen.

**Übergeordnetes Thema:**[ Ausgabegenerierung](generate-output.md)

