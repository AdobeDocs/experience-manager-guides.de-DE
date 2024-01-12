---
title: Erstellen und Verwalten von Grundlinien im Web-Editor
description: Erstellen und verwalten Sie Grundlinien über den Webeditor in AEM Handbüchern. Erfahren Sie, wie Sie Grundlinien basierend auf Bezeichnungen erstellen und Filter auf die Grundlinien anwenden.
exl-id: 14f87bdd-3042-46f9-853e-e9ded81b10ed
feature: Authoring, Features of Web Editor, Publishing
role: User
source-git-commit: be06612d832785a91a3b2a89b84e0c2438ba30f2
workflow-type: tm+mt
source-wordcount: '1617'
ht-degree: 0%

---

# Erstellen und Verwalten von Grundlinien im Web-Editor {#id223MB0ZF043}

>[!TIP]
>
> Es wird empfohlen, diese Grundlinie-Funktion aus dem Web Editor zu verwenden, wenn Sie ein Upgrade auf AEM Guides-Version vom as a Cloud Service März oder höher durchgeführt haben.

AEM Handbücher bietet die Funktion &quot;Grundlinie&quot;im Web Editor, mit der Benutzer Grundlinien erstellen und Themen aus verschiedenen Versionen veröffentlichen oder übersetzen können.

## Erstellen einer Grundlinie

Sie können eine Grundlinie im Web Editor erstellen, indem Sie die folgenden Schritte ausführen:

1. Öffnen Sie im Bereich &quot;Repository&quot;die DITA-Map-Datei in der Kartenansicht.
1. Klicken Sie auf **Verwalten** Registerkarte. Die **Grundlinie** zeigt die Grundlinien der DITA-Zuordnung an.

   ![Grundlegender Bereich](images/baseline-manage.png){width="800" align="left"}

1. Im **Grundlinie** klicken Sie oben rechts auf das Symbol + , um eine Grundlinie zu erstellen.
1. Geben Sie einen Namen für die Grundlinie in **Name**.
1. In **Konfiguration** können Sie entweder **Manuelle Aktualisierung** Option oder **Automatische Aktualisierung** Option:

   **Manuelle Aktualisierung**: Sie können manuell eine statische Grundlinie mit einer bestimmten Version der Themen und des referenzierten Inhalts erstellen, die an einem bestimmten Datum und zu einer bestimmten Uhrzeit verfügbar ist, oder mit einer für eine Version der Themen definierten Bezeichnung:

   - In **Wählen Sie die Version basierend auf** eine der folgenden Optionen auswählen:


      1. **Datum** &lt;time stamp=&quot;&quot;>: Wählt die Version des Themas als Datum und Uhrzeit aus.
      1. **Titel**: Wählen Sie diese Option aus, um die Themen entsprechend dem Titel auszuwählen, der auf sie angewendet wurde. Wenn für die Themen Beschriftungen angegeben sind, werden die Beschriftungen im Dropdown-Menü aufgeführt. Sie können einen Titel aus der Liste auswählen. Sie können auch eine Beschriftung in das Textfeld einfügen.

         Für die direkten Verweise in statischen Grundlinien werden die Beschriftungen von der zuletzt gespeicherten Version der Karte abgerufen. Wenn Sie beispielsweise Bezeichnungen erstellt haben `Label Release 1.0` und `Label Release 1.1` für die Versionen 1.0 und 1.1 von Thema A und fügen Sie dann Thema A zur Karte hinzu, die als Version 1.0 gespeichert wurde. In diesem Fall können Sie die Beschriftungen anzeigen `Label Release 1.0` und `Label Release 1.1` in der Dropdown-Liste für statische Grundlinien-Beschriftungen.


         Wenn Sie **Titel,** Sie können die direkten und indirekten Verweise auswählen.
         - Bei direkten Verweisen innerhalb der DITA-Zuordnung erhalten Sie die Möglichkeit, die neueste Version von Themen zu verwenden, auf die die angegebene Bezeichnung nicht angewendet wurde.

           >[!NOTE]
           >
           > Wenn Sie einen nicht vorhandenen Titel eingeben, wählen Sie die Option **Erstellen Sie keine Grundlinie** dann schlägt die Grundlinien-Erstellung fehl und zeigt eine Fehlermeldung in der Nähe des Grundlinien-Namens im Bedienfeld Grundlinie an.

         - Bei indirekten Verweisen innerhalb der DITA-Zuordnung erhalten Sie eine zusätzliche Option, die neueste Version von Themen zu verwenden, auf die die angegebene Bezeichnung nicht angewendet wurde. Sie können auch **Automatisch auswählen** für den referenzierten Inhalt, und das System wählt automatisch die Version des referenzierten Inhalts aus, die der Version des Inhalts entspricht, in dem er referenziert wird.

         Nachdem Sie eine Bezeichnung oder Version als Datum ausgewählt haben, werden alle referenzierten Themen und Mediendateien in der Zuordnung entsprechend ausgewählt. Diese Themenauswahl wird nicht auf der Benutzeroberfläche angezeigt, sondern im Backend gespeichert.

   **Automatische Aktualisierung**: Wählen Sie diese Option für die Grundlinien-Erstellung aus, um die Themen automatisch entsprechend der auf sie angewendeten Bezeichnung auszuwählen.

   Grundlinien, die mit der Konfiguration der automatischen Aktualisierung erstellt wurden, werden dynamisch aktualisiert. Wenn Sie eine Grundlinie erstellen, eine Grundlinie herunterladen oder ein Übersetzungsprojekt mit einer Grundlinie erstellen, werden die Dateien dynamisch anhand der aktualisierten Beschriftungen ausgewählt. Wenn Sie beispielsweise Version 1.2 eines Themas mit Label Release 1.0 für die Grundlinie und später aktualisierte Version 1.5 mit Label Release 1.0 verwendet haben, wird die Grundlinie dynamisch aktualisiert und Version 1.5 wird verwendet.

   ![Erstellen einer Grundlinie](images/dynamic-baseline.png){width="550" align="left"}

   - **Beschriftungen auswählen**: Wenn für die Themen Beschriftungen angegeben sind, werden diese im Abschnitt **Beschriftungen auswählen** Dropdown. Sie können die Titel\(s\) aus der Liste auswählen. Die zuerst ausgewählten Titel erhalten höhere Priorität als die späteren.

     Bei dynamischen Grundlinien werden die Beschriftungen von der zuletzt gespeicherten Version und der aktuellen Arbeitskopie der Karte abgerufen. Wenn Sie beispielsweise Bezeichnungen erstellt haben   `Label Release A.1.0 ` und `Label Release A.1.1` für die Versionen 1.0 und 1.1 von Thema A und Beschriftungen `Label Release B.1.0` und `Label Release B.1.1` für die Versionen 1.0 und 1.1 von Thema B . Anschließend können Sie Thema A zu Karte A in Version 1.0 und Thema B zu Karte A in 1.0* hinzufügen (Arbeitskopie). In diesem Fall können Sie  `Label Release A.1.0 `, `Label Release A.1.1`, `Label Release B.1.0`, und `Label Release B.1.1` in der Dropdown-Liste der dynamischen Grundlinien-Beschriftungen.

1. **Indirekte Verweise**: Für indirekte Verweise in der DITA-Zuordnung erhalten Sie die folgenden Optionen:

   - **Automatisch auswählen**: Sie können auswählen, **Automatisch auswählen** für den referenzierten Inhalt, und das System wählt automatisch die Version des referenzierten Inhalts aus, die der Version des Inhalts entspricht, in dem er referenziert wird.

   - **Ausgewählte Bezeichnung verwenden**: Sie können eine Grundlinie mit der ausgewählten Bezeichnung erstellen, die für eine Version von Themen definiert ist.
   - **Verwenden der neuesten Version oder der Arbeitskopie**: Verwenden Sie die neueste Version der Themen, auf die die angegebene Beschriftung nicht angewendet wurde, oder verwenden Sie die Arbeitskopie der Themen, um die Grundlinie zu erstellen, falls keine Version erstellt wurde.
1. Klicken Sie auf **Übernehmen**.

Die Grundlinie wird erstellt. Die Grundlinien-Erstellung erfolgt asynchron, sodass Sie im Web Editor weiterhin an anderen Dateien arbeiten können. Nachdem die Grundlinie erstellt wurde, wird eine Popup-Meldung angezeigt, die bestätigt, dass die Grundlinie erstellt wurde, und Sie erhalten auch eine Inbox-Benachrichtigung für dieselbe Grundlinie.

## Grundlinien verwalten

Sie können Ihre vorhandenen Grundlinien mithilfe der verschiedenen Funktionen im Dashboard Grundlinie verwalten.

- Sie können über das Textfeld im Bedienfeld &quot;Grundlinie&quot;nach einer vorhandenen Grundlinie suchen. Verwenden Sie die **Filter anwenden** -Symbol, um alle Grundlinien anzuzeigen oder die Grundlinien mit dem Erstellungsstatus als &quot;Erfolgreich&quot;, &quot;In Bearbeitung&quot;oder &quot;Fehlgeschlagen&quot;aufzulisten.
- Verwenden Sie die **Aktualisieren** im Bedienfeld &quot;Grundlinie&quot;ein, um alle Grundlinien erneut zu überprüfen und eine neue Liste der Grundlinien für die DITA-Karte anzuzeigen, die in der Kartenansicht geöffnet ist.
- Sie können den Inhalt einer vorhandenen statischen Grundlinie anzeigen oder bearbeiten, indem Sie auf die Grundlinie in der Liste im **Grundlinie** Bedienfeld. Das Grundlinien-Bearbeitungsfenster in der Mitte zeigt die DITA-Map-Datei, den Inhalt oder die Themen der Zuordnung und den referenzierten Inhalt an.

  >[!NOTE]
  >
  >Der Bearbeitungsvorgang für statische Grundlinien wird nur für wenige Referenzänderungen empfohlen. Der Bearbeitungsvorgang wird nicht empfohlen, um die Version der DITA-Hauptkarte zu ändern, da alle Verweise neu berechnet werden müssen. Dies kann bei großen DITA-Maps zu einem Fehler bei der Grundlinien-Aktualisierung führen. Für die größeren DITA-Maps können Sie eine neue Grundlinie erstellen oder die Eigenschaften der Grundlinie bearbeiten.
  >
  >Der Bearbeitungsvorgang bei dynamischen Grundlinien ermöglicht es Ihnen, die Eigenschaften der Grundlinie zu bearbeiten, da die Verweise für dynamische Grundlinien zur Laufzeit mithilfe der Beschriftungen generiert werden.

  ![Optionen einer Grundlinie](images/baseline-options.png){width="800" align="left"}



  Sie können auch die folgenden Vorgänge auf der Grundlinie im Menü Optionen ausführen:
- **Grundlinie duplizieren**: Sie können eine Grundlinie duplizieren und entsprechend Ihren Anforderungen ändern.
  ![Grundlinie duplizieren](images/baseline-duplicate.png){width="300" align="left"}
  *Duplizieren Sie eine Grundlinie basierend auf einem Titel oder erstellen Sie eine exakte Kopie.*

   1. Auswählen **Duplizieren** im Menü Optionen einer Grundlinie. Die **Grundlinie duplizieren** wird geöffnet.
      >[!NOTE]
      > 
      >Der Standardname der Grundlinie lautet `<selected baseline name>`_suffix (wie sample-baseline_1). Sie können den Namen entsprechend Ihren Anforderungen ändern.
   1. In **Wählen Sie die Version basierend auf** können Sie entweder die **Exakte Kopie** oder **Titel** Option:
      - **Exakte Kopie**: Experience Manager Guides wählen dieselbe Version aller Themen aus und erstellen eine exakte Kopie der duplizierten Grundlinie.
      - **Titel**: Sie können eine Bezeichnung aus der Dropdown-Liste auswählen. In den Experience Manager-Handbüchern werden die Themenversionen ausgewählt, für die der ausgewählte Titel definiert ist, während für die übrigen Themen die Version aus der duplizierten Grundlinie ausgewählt wird. Beispielsweise können Sie die Bezeichnung `Release 1.0` aus der Dropdown-Liste aus, werden die Versionen der Themen ausgewählt, für die Sie diese Bezeichnung definiert haben. Bei allen anderen Themen wird die Version aus der duplizierten Grundlinie ausgewählt.
   1. Klicks **Duplizieren**.
- **Umbenennen** oder **Löschen** eine bestehende Grundlinie.
- Hinzufügen, Entfernen oder Ändern vorhandener Bezeichnungen aus dem **Verwalten von Bezeichnungen** für statische Grundlinien. Wenn Ihr Administrator vordefinierte Beschriftungen konfiguriert hat, werden diese Beschriftungen in der Dropdown-Liste Titel hinzufügen angezeigt. Weitere Informationen zum Hinzufügen von Bezeichnungen finden Sie unter [Verwenden von Bezeichnungen](web-editor-use-label.md#).

  >[!NOTE]
  >
  > Der Prozess zum Hinzufügen oder Entfernen von Beschriftungen erfolgt asynchron, sodass Sie im Web Editor weiterhin an anderen Dateien arbeiten können. Nachdem der Titel hinzugefügt oder entfernt wurde, wird eine Popup-Meldung angezeigt, in der bestätigt wird, dass der Titel hinzugefügt oder entfernt wurde, und Sie erhalten auch eine Inbox-Benachrichtigung.

- **Eigenschaften bearbeiten** einer vorhandenen statischen Grundlinie, die Sie beim Erstellen der Grundlinie festgelegt haben.
- Exportieren Sie die Momentaufnahme einer Grundlinie in eine Microsoft Excel-Datei mit der **Exportgrundlinie** -Option.

**Standardfilter**

Verwenden des Symbols Filter im **Standardfilter** -Bedienfeld können Sie Filter auf die Grundlinie anwenden, die im Fenster der Grundlinienbearbeitung geöffnet wurde:

![Grundlinienfilter](images/baseline-filter.png){width="300" align="left"}

- Filtern Sie die Dateien nach Dateinamen oder Dateispeicherort.
- Filtern Sie die Dateien anhand der Werte für verschiedene Spalten wie Dateityp, Referenztyp usw.
- Wählen Sie die Spalten aus, die im Bearbeitungsfenster für die Grundlinie angezeigt werden sollen.

>[!NOTE]
>
> Sie können auf eine Spaltenüberschrift klicken und die Dateien nach den Spalten im Bearbeitungsfenster für die Grundlinie sortieren.

**Speichern oder Zurücksetzen einer Grundlinie**

Nachdem Sie die Grundlinie bearbeitet haben, können Sie auf **Speichern** -Schaltfläche oben, um die Änderungen an der Grundlinie zu speichern. Sie können auf die **Zurücksetzen** , wenn Sie die Änderung nicht speichern und die Grundlinie zurücksetzen möchten. Wenn Sie auf die **Zurücksetzen** -Schaltfläche ein Warnhinweis angezeigt, dass nicht gespeicherte Änderungen verloren gehen.

**Übergeordnetes Thema:**[ Arbeiten mit dem Web-Editor](web-editor.md)

