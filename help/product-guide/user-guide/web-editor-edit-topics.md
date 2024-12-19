---
title: Bearbeiten von Themen im Web-Editor
description: Erfahren Sie, wie Sie Themen im Web-Editor bearbeiten. Erfahren Sie mehr über verschiedene Bearbeitungsfunktionen zum Ändern Ihrer Themendateien in AEM Guides.
exl-id: 8da37a81-e8c3-434f-b3f4-4723d87c2ade
feature: Authoring, Web Editor
role: User
source-git-commit: 2a22aa0746602f7ecd6b3d6cf616a68d45309bdf
workflow-type: tm+mt
source-wordcount: '1055'
ht-degree: 0%

---

# Bearbeiten von Themen im Web-Editor {#id2056B040VUI}

Der Web-Editor verfügt über eine Reihe von Bearbeitungsfunktionen, mit denen Sie mühelos Themendateien erstellen oder ändern können. Allgemein würden Sie die folgenden Schritte ausführen, um ein Thema im Web-Editor zu bearbeiten.

>[!IMPORTANT]
>
> Wenn während der Arbeit im Web-Editor ein Anwendungsfehler auftritt, aktualisieren Sie die Seite, um weiter zu arbeiten.

1. Um Änderungen an Ihrem Thema vorzunehmen, klicken Sie in den Textbereich des erforderlichen Elements und nehmen Sie Änderungen vor.

1. Um ein bestimmtes Element einzufügen, klicken Sie auf das Ende des Elements, nach dem Sie das neue Element einfügen möchten, und klicken Sie auf das Symbol Erforderliches Element in der Symbolleiste. Sie können auch den Tastaturbefehl `Alt+Enter` verwenden, um das Popup **Element einfügen** aufzurufen.

   Es wird eine Liste der Elemente angezeigt, die im Thema verwendet werden können. AEM Guides platziert Elemente intelligent entsprechend ihrer gültigen Position im Thema.

   >[!NOTE]
   >
   > Sie können auch auswählen, welches Symbol in der Symbolleiste angezeigt werden soll, indem Sie die `ui_config.json` unter - `/etc/designs/fmdita/clientlibs/xmleditor/` konfigurieren. Weitere Informationen zum Anpassen von Funktionen erhalten Sie von Ihrem Systemadministrator.

1. Nachdem Sie das Dokument bearbeitet haben, klicken Sie auf **Speichern**.

   >[!NOTE]
   >
   > Wenn Sie die Änderungen nicht in das AEM-Repository übernehmen möchten, klicken Sie auf **Schließen** und anschließend auf **Ohne Speichern schließen** im Dialogfeld Nicht gespeicherte Änderungen.


## Teilweise Auswahl von Inhalten über Elemente hinweg

Mit Experience Manager Guides können Sie auch Inhalte über Elemente hinweg auswählen. Nach Auswahl des Inhalts können Sie die folgenden Schritte ausführen:

- Formatierung und Löschung: Formatieren und Kursiv formatieren, unterstreichen oder sogar löschen Sie ausgewählte Inhalte. Der Inhalt der gültigen offenen Tags wird dann zusammengeführt und unter einem einzigen Element angezeigt. Sie können beispielsweise den Inhalt innerhalb eines Absatzes auswählen und die Auswahl auf einen anderen Absatz erweitern. Wenn Sie dann den ausgewählten Inhalt fett formatieren, wird der gesamte fettgedruckte Inhalt aus den geöffneten Tags zusammengeführt und unter einem einzigen Absatzelement angezeigt.

Wenn Sie den ausgewählten Inhalt löschen, wird der verbleibende Inhalt nach dem Löschen in den geöffneten Tags zusammengeführt.

- Den Inhalt mit einem gültigen Element umgeben: Führen Sie die folgenden Schritte aus, um den Inhalt mit einem gültigen Element einzuschließen:

   - Wählen Sie den Inhalt in einem Element aus.
   - Wählen Sie ![ Symbol ](images/Add_icon.svg)Hinzufügen“ in der sekundären Symbolleiste oben aus, um das Dialogfeld **Umschließen mit Element** anzuzeigen. Das Dialogfeld listet die gültigen Elemente für den ausgewählten Inhalt auf.
     >[!NOTE]
     >
     > Sie können das Dialogfeld Umschließen mit Element auch anzeigen, indem Sie auf das Kontextmenü des ausgewählten Inhalts klicken.

   - Wählen Sie ein Element im Dialogfeld aus. Der ausgewählte Inhalt wird unter diesem Element umschlossen. Wenn Sie beispielsweise den Inhalt in einem Absatz auswählen und dann das `<note>` Element im Dialogfeld **Mit Element umgeben** auswählen, wird der ausgewählte Inhalt unter einer Anmerkung angezeigt.\
     ![Dialogfeld „Element umschließen](./images/surround-element.png) {width="300" align="left"}

## Browser beim Bearbeiten der Dateien aktualisieren

Experience Manager Guides bietet Unterstützung zum Aktualisieren des Browsers, während Sie Ihre Inhalte im Web-Editor bearbeiten. Mit dieser Funktion können Sie Inhalte weiter bearbeiten, falls während der Arbeit ein Anwendungsfehler auftritt. Wenn Sie auf die Browser-Aktualisierung klicken, während eine oder mehrere Dateien mit nicht gespeicherten Änderungen zur Bearbeitung geöffnet werden, werden Sie gewarnt, dass die nicht gespeicherten Änderungen verloren gehen können. Sie haben die Möglichkeit, den Aktualisierungsvorgang abzubrechen und Ihre Dateien zu speichern, um Ihre Änderungen beizubehalten.

Selbst beim Aktualisieren des Browsers werden die Ansichten des linken und rechten Bedienfelds im Web-Editor beibehalten. Experience Manager Guides stellt den letzten gespeicherten Status der im Web-Editor geöffneten Dateien wieder her, wenn Sie den Browser aktualisieren. Beispielsweise werden die im Repository-Bereich geöffneten Dateien erneut geöffnet. Das Kartenbedienfeld wird zusammen mit der zuvor geöffneten Karte beibehalten.

Das aktive Thema oder die DITA-Karte wird im Inhaltsbearbeitungsbereich erneut geöffnet.

Das rechte Bedienfeld wird ebenfalls wieder geöffnet und zeigt dieselbe Ansicht wie vor der Aktualisierung an.

## Arbeitskopie-Anzeige

AEM Guides stellt die Arbeitskopie-Anzeige bereit, die anzeigt, ob die aktuelle \(Arbeitskopie\) der Datei mit der gespeicherten Version synchronisiert ist oder nicht. Wenn Sie Änderungen an Ihrer aktuellen Kopie vorgenommen und Ihre Datei nicht gespeichert haben, wird auf der Registerkarte Datei des Themas ein \*-Zeichen zusammen mit dem Titel angezeigt. Diese Anzeige dient als Erinnerung zum Speichern Ihrer Änderungen und verschwindet, wenn Sie Ihre Datei speichern.

![Arbeitskopie-Anzeige](images/working-copy-text-update-indicator.png){width="550" align="left"}

AEM Guides gibt auch an, ob die zuletzt gespeicherte \(Working\)-Kopie der Datei mit der gespeicherten Version synchronisiert ist. Wenn Sie einige nicht gespeicherte Änderungen zwischen der Arbeitskopie und der zuletzt gespeicherten Version haben, wird ein \*-Zeichen zusammen mit den Versionsinformationen angezeigt, die in der rechten oberen Ecke der Registerkarte Datei des Themas angezeigt werden. Dieser Indikator dient als Erinnerung daran, eine Version aus Ihrer aktuellen \(Working\) Kopie der Datei zu speichern und zu erstellen.

![Versionsaktualisierungsanzeige](images/version-update-indicator.png){width="550" align="left"}


## Öffnen gesperrter Dateien im Authoring- und Source-Modus

Wenn eine DITA- oder Markdown-Datei von einem anderen Benutzer gesperrt oder ausgecheckt wird, ist das Bearbeiten oder Ändern des Inhalts nicht möglich. Sie können die Datei jedoch zusätzlich zum Vorschaumodus weiterhin im schreibgeschützten Format sowohl im **Author**- als auch **2** Source **-Modus anzeigen.**

Im schreibgeschützten Modus können Sie den Inhalt, die Tags und die Attribute innerhalb des **author** oder **Source** Modus anzeigen. Sie können auch die Dateieigenschaften ändern.

In der Symbolleiste werden die folgenden Symbole für schreibgeschützten Zugriff angezeigt:

- Tag-Ansicht umschalten
- Versionsverlauf
- Versions-Label

Experience Manager Guides zeigt auch eine **Schreibgeschützter Zugriff** in der Nähe der Versionsnummer an.

![Schreibgeschützte Datei im Autorenmodus anzeigen](images/locked-file-editor.png)

Sie können auf die **Layout**-Ansicht für schreibgeschützte DITA-Zuordnungen zugreifen. In dieser Ansicht werden die DITA-Karte und ihre Eigenschaften angezeigt, Änderungen werden jedoch verhindert.

>[!NOTE]
>
> Administrierende Benutzer bzw. Benutzerinnen auf Ordnerebene müssen *ui_config.json* aktualisieren, damit sie im Autoren-, Source- und Layout-Modus harmonisch auf die schreibgeschützten Dateien zugreifen können.

## Suchen einer geöffneten Datei in der Repository-Ansicht

Beim Öffnen einer Datei im Web-Editor bietet Experience Manager Guides die Funktion zum Suchen der Datei in der Repository-Ansicht. Sie findet beispielsweise das aktuelle Thema, während Sie es bearbeiten.

Sie können die Funktion zum Suchen der Datei mit der Option **Dateien immer im Repository suchen** auf der Registerkarte **Erscheinungsbild** der **Benutzereinstellungen** deaktivieren.


**Übergeordnetes Thema:**[ Arbeiten mit dem Web-Editor](web-editor.md)
