---
title: Bearbeiten von Themen im Web-Editor
description: Erfahren Sie, wie Sie Themen im Web-Editor bearbeiten können. Erfahren Sie mehr über verschiedene Bearbeitungsfunktionen, um Ihre Themendateien in AEM Handbüchern zu ändern.
exl-id: 8da37a81-e8c3-434f-b3f4-4723d87c2ade
feature: Authoring, Web Editor
role: User
source-git-commit: d30f05ff614693beca5d9cf7f206a36f3dadfc8b
workflow-type: tm+mt
source-wordcount: '889'
ht-degree: 0%

---

# Bearbeiten von Themen im Web-Editor {#id2056B040VUI}

Der Web Editor verfügt über eine Reihe von Bearbeitungsfunktionen, mit denen Sie Themendateien einfach erstellen oder ändern können. Im Großen und Ganzen führen Sie die folgenden Schritte aus, um ein Thema im Web Editor zu bearbeiten.

>[!IMPORTANT]
>
> Wenn bei der Arbeit mit dem Web Editor ein Anwendungsfehler auftritt, aktualisieren Sie die Seite, damit sie weiterhin funktioniert.

1. Um Änderungen an Ihrem Thema vorzunehmen, klicken Sie auf den Textbereich des erforderlichen Elements und nehmen Sie Änderungen vor.

1. Um ein bestimmtes Element einzufügen, klicken Sie auf das Ende des Elements, nach dem Sie das neue Element einfügen möchten, und klicken Sie in der Symbolleiste auf das Symbol für das gewünschte Element. Sie können auch den Tastaturbefehl `Alt+Enter` , um die **Element einfügen** Popup.

   Es wird eine Liste mit Elementen angezeigt, die im Thema verwendet werden können. AEM Guides führen eine intelligente Platzierung von Elementen gemäß ihrer gültigen Position im Thema durch.

   >[!NOTE]
   >
   > Sie können auch auswählen, welches Symbol in der Symbolleiste angezeigt werden soll, indem Sie die `ui_config.json` Datei unter - `/etc/designs/fmdita/clientlibs/xmleditor/`. Weitere Informationen zum Anpassen von Funktionen erhalten Sie von Ihrem Systemadministrator.

1. Nachdem Sie die Bearbeitung des Dokuments abgeschlossen haben, klicken Sie auf **Speichern**.

   >[!NOTE]
   >
   > Wenn Sie keine Änderungen in AEM Repository übertragen möchten, klicken Sie auf **Schließen** und klicken Sie anschließend auf **Ohne Speichern schließen** im Dialogfeld Nicht gespeicherte Änderungen .


## Teilauswahl von Inhalten über Elemente hinweg

Mit Experience Manager-Handbüchern können Sie auch Inhalte elementübergreifend auswählen. Nach Auswahl des Inhalts können Sie die folgenden Vorgänge ausführen:
- Formatierung und Löschen: Machen Sie den ausgewählten Inhalt fett, kursiv, unterstrichen oder löschen Sie ihn sogar. Der Inhalt der gültigen offenen Tags wird dann zusammengeführt und unter einem einzelnen Element angezeigt. Sie können beispielsweise den Inhalt eines Absatzes auswählen und die Auswahl auf einen anderen Absatz erweitern. Wenn Sie dann den ausgewählten Inhalt fett formatieren, werden alle fett gedruckten Inhalte der geöffneten Tags zusammengeführt und unter einem einzigen Absatzelement angezeigt.

Wenn Sie den ausgewählten Inhalt löschen, wird der verbleibende Inhalt nach dem Löschen in den geöffneten Tags zusammengeführt.

- Um den Inhalt mit einem gültigen Element zu umgeben: Führen Sie die folgenden Schritte aus, um den Inhalt mit einem gültigen Element zu umgeben:
   - Wählen Sie den Inhalt eines Elements aus.
   - Wählen Sie die ![add](images/Add_icon.svg) über das Symbol in der sekundären Symbolleiste am oberen Rand, um die **Umgeben mit Element** Dialogfeld. Im Dialogfeld werden die gültigen Elemente für den ausgewählten Inhalt aufgelistet.
     >[!NOTE]
     >
     > Sie können auch das Dialogfeld Umfrage mit Element anzeigen, indem Sie das Kontextmenü des ausgewählten Inhalts auswählen.

   - Wählen Sie im Dialogfeld ein Element aus. Der ausgewählte Inhalt wird unter diesem Element eingeschlossen. Wenn Sie beispielsweise den Inhalt in einem Absatz auswählen und dann die `<note>` -Element aus **Umgeben mit Element** angezeigt, wird der ausgewählte Inhalt unter einem Hinweis angezeigt.\
     ![Dialogfeld &quot;Umgehendes Element&quot;](./images/surround-element.png) {width="300" align="left"}

## Aktualisieren des Browsers beim Bearbeiten der Dateien

Experience Manager-Handbücher bieten die Möglichkeit, den Browser zu aktualisieren, während Sie den Inhalt im Web Editor bearbeiten. Mit dieser Funktion können Sie die Bearbeitung von Inhalten fortsetzen, falls bei der Arbeit ein Anwendungsfehler auftritt. Wenn Sie auf die Browseraktualisierung klicken, während eine oder mehrere Dateien mit nicht gespeicherten Änderungen zur Bearbeitung geöffnet sind, werden Sie gewarnt, dass die nicht gespeicherten Änderungen möglicherweise verloren gehen. Sie erhalten die Möglichkeit, den Aktualisierungsvorgang abzubrechen und Ihre Dateien zu speichern, um Ihre Änderungen beizubehalten.

Selbst beim Aktualisieren des Browsers werden die Ansichten des linken und des rechten Bereichs im Web Editor beibehalten. Experience Manager-Handbücher stellen den zuletzt gespeicherten Status der Dateien wieder her, die im Web Editor geöffnet wurden, wenn Sie den Browser aktualisieren. Beispielsweise werden die im Repository-Bedienfeld geöffneten Dateien erneut geöffnet. Das Zuordnungsbedienfeld wird zusammen mit der zuvor geöffneten Karte beibehalten.

Das aktive Thema oder die DITA-Zuordnung wird im Inhaltsbearbeitungsbereich erneut geöffnet.

Das rechte Bedienfeld wird ebenfalls neu geöffnet und zeigt dieselbe Ansicht an wie vor der Aktualisierung.

## Arbeitskopierer

AEM Handbücher bieten einen Arbeitskopie-Indikator, der anzeigt, ob die aktuelle \(Arbeitskopie\) der Datei mit der gespeicherten Version synchronisiert ist oder nicht. Wenn Sie Änderungen an Ihrer aktuellen Kopie vorgenommen und Ihre Datei nicht gespeichert haben, wird auf der Registerkarte &quot;Datei&quot;des Themas ein \*-Zeichen mit dem Titel angezeigt. Dieser Indikator dient als Erinnerung, um Ihre Änderungen zu speichern, und verschwindet, wenn Sie Ihre Datei speichern.

![Arbeitskopierer](images/working-copy-text-update-indicator.png){width="550" align="left"}

AEM Guides zeigen auch an, ob die letzte gespeicherte \(Work\) Kopie der Datei mit der gespeicherten Version synchronisiert ist oder nicht. Wenn Sie einige nicht gespeicherte Änderungen zwischen der Arbeitskopie und der zuletzt gespeicherten Version haben, wird ein \*-Zeichen zusammen mit den Versionsinformationen angezeigt, die in der rechten oberen Ecke der Registerkarte &quot;Datei&quot;des Themas angezeigt werden. Dieser Indikator dient als Erinnerung zum Speichern und Erstellen einer Version aus Ihrer aktuellen \(funktionierenden\) Kopie der Datei.

![Versionsaktualisierungsindikator](images/version-update-indicator.png){width="550" align="left"}




## Suchen einer geöffneten Datei in der Repository-Ansicht

Während Sie eine Datei im Web Editor öffnen, bietet das Experience Manager-Handbuch die Möglichkeit, die Datei in der Repository-Ansicht zu finden. Beispielsweise wird das aktuelle Thema beim Bearbeiten gesucht.

Sie können die Funktion deaktivieren, um die Datei mit der **Immer Dateien im Repository suchen** Option aus der **Erscheinungsbild** des **Benutzereinstellungen**.


**Übergeordnetes Thema:**[ Arbeiten mit dem Web-Editor](web-editor.md)
