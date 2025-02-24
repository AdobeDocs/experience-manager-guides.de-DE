---
title: Erstellen von Themen
description: Erfahren Sie, wie Sie mit benutzerdefinierten Vorlagen in Adobe Experience Manager Guides DITA-Thementypen erstellen.
exl-id: 84e9cfdf-e188-487f-9181-68708029c101
feature: Authoring
role: User
source-git-commit: 67d6b6f59e5d8c37389a181949ce4527760576e2
workflow-type: tm+mt
source-wordcount: '833'
ht-degree: 0%

---

# Erstellen von Themen {#id2056AL00O5Z}

Mit Adobe Experience Manager Guides können Sie DITA-Themen des Typs „Thema“, „Aufgabe“, „Konzept“, „Referenz“, „Glossar“, „DITAVAL“, „Markdown“ und mehr erstellen. Sie können nicht nur Themen auf der Grundlage von vordefinierten Vorlagen erstellen, sondern auch benutzerdefinierte Vorlagen definieren. Diese Vorlagen müssen dem Profilordner hinzugefügt werden, damit sie in der Blueprint zur Vorlagenauswahl und im Editor angezeigt werden.

>[!NOTE]
>
> Die Profilkonfiguration „Global“ und „Ordner“ ist nur für Benutzer mit Administratorrechten auf Ordnerebene verfügbar. Weitere Informationen zum Einrichten globaler Profile und Profile auf Ordnerebene finden Sie unter *Konfigurieren von Authoring* Vorlagen) unter Installieren und Konfigurieren von Adobe Experience Manager Guides für Ihr Setup.


Es gibt zwei Möglichkeiten, Themen in Experience Manager Guides zu erstellen:

- [Erstellen von Themen im Editor](#create-topics-from-the-editor)
- [Erstellen von Themen über die Assets-Benutzeroberfläche](#create-topics-from-the-assets-ui)

## Erstellen von Themen im Editor

Führen Sie die folgenden Schritte aus, um ein Thema im Editor zu erstellen:

1. Wählen Sie im Repository-Bedienfeld das Symbol **Neue Datei** und wählen Sie dann **Thema** aus dem Dropdown-Menü aus.

   ![](create-topic-option.png){width="500" align="left"}

   Sie können auf diese Option auch über die Startseite von [Experience Manager Guides ](./intro-home-page.md) über das Optionsmenü eines Ordners in der Repository-Ansicht zugreifen.

2. Das **Neues Thema** wird angezeigt.

3. Geben **im Dialogfeld** Neues Thema“ die folgenden Details an:
   - Ein Titel für das Thema.
   - \(Optional\)* Der Dateiname für das Thema. Der Dateiname wird basierend auf dem Thementitel automatisch vorgeschlagen. Wenn Ihr Administrator automatische Dateinamen basierend auf der UUID-Einstellung aktiviert hat, wird das Feld Name nicht angezeigt.
   - Eine Vorlage, auf der das Thema basieren soll. Bei einem vorkonfigurierten Setup können Sie beispielsweise aus den Vorlagen „Leer“, „Konzept“, „DIGITAL“, „Referenz“, „Aufgabe“, „Thema“, „Markdown“, „Glossar“ und „Fehlerbehebung“ wählen. Wenn für Ihren Ordner ein Ordnerprofil konfiguriert ist, zeigen Sie nur die Themenvorlagen an, die für das Ordnerprofil konfiguriert sind.
   - Pfad zum Speichern der Themendatei. Standardmäßig wird der Pfad des aktuell ausgewählten Ordners im Repository im Feld Pfad angezeigt.

4. Wählen Sie **Erstellen** aus.

   ![](images/create-topic-dialog-new.png){width="300" align="left"}

Das Thema wird unter dem angegebenen Pfad erstellt. Außerdem wird das Thema im Editor zur Bearbeitung geöffnet.

![](images/new-topic-editor.png){width="800" align="left"}

## Erstellen von Themen über die Assets-Benutzeroberfläche

Führen Sie die folgenden Schritte aus, um ein Thema über die Assets-Benutzeroberfläche zu erstellen:

1. Navigieren Sie in der Assets-Benutzeroberfläche zu dem Speicherort, an dem Sie das Thema erstellen möchten.

1. Um ein neues Thema zu erstellen, wählen Sie **Erstellen** \> **DITA-Thema**.

1. Wählen Sie auf der Blueprint-Seite den Typ des zu erstellenden DITA-Dokuments aus und klicken Sie auf **Weiter**.

   ![](images/create_dita_topic.png){width="800" align="left"}

   Standardmäßig stellt Experience Manager Guides die am häufigsten verwendeten DITA-Themenvorlagen bereit. Sie können weitere Themenvorlagen entsprechend Ihren Unternehmensanforderungen konfigurieren. Sehen Sie sich *Authoring-Vorlagen konfigurieren* in Installieren und konfigurieren Sie Adobe Experience Manager Guides für Ihr Setup.

   >[!NOTE]
   >
   > In der Listenansicht der Assets-Benutzeroberfläche wird der DITA-Topic-Typ in der Spalte Typ als Thema, Aufgabe, Konzept, Referenz, Glossentry, Markdown oder DITAVAL angezeigt. Die DITA-Karte wird als Karte angezeigt.

1. Geben Sie auf der Seite Eigenschaften das Dokument **Titel** an.

1. \(Optional\) Geben Sie die Datei **Name** an.

   Wenn Ihr Admin einen automatischen Dateinamen basierend auf einer UUID-Einstellung konfiguriert hat, wird die Option zum Angeben des Dateinamens nicht angezeigt. Ein UUID-basierter Dateiname wird der Datei automatisch zugewiesen.

   Wenn die Option zur Dateibenennung verfügbar ist, wird auch der Name basierend auf dem **Titel** Ihres Dokuments automatisch vorgeschlagen. Wenn Sie den Dokumentnamen manuell angeben möchten, stellen Sie sicher, dass **Name** keine Leerzeichen, Apostrophe oder geschweifte Klammern enthält und mit .xml oder.dita endet. Standardmäßig ersetzt Experience Manager Guides alle Sonderzeichen durch Bindestriche. Im Abschnitt Dateinamen des Best Practices-Handbuchs finden Sie Best Practices für die Benennung von DITA-Dateien.

1. Wählen Sie **Erstellen**. Die Meldung Thema erstellt wird angezeigt.

   Sie können das Thema zur Bearbeitung im Editor öffnen oder die Themendatei im Adobe Experience Manager-Repository speichern.

**Zusätzliche Informationen**

1. Jedem neuen Thema, das Sie über die Assets-Benutzeroberfläche erstellen **Erstellen** \> **DITA-Thema** oder dem Editor wird eine eindeutige Themen-ID zugewiesen. Der Wert dieser ID ist der Dateiname selbst. Außerdem wird ein neues Dokument als neueste Arbeitskopie des Themas in DAM gespeichert. Bis zum Speichern einer Revision eines neu erstellten Themas wird im Versionsverlauf keine Versionsnummer angezeigt. Wenn Sie das Thema zur Bearbeitung öffnen, werden die Versionsinformationen in der rechten oberen Ecke der Symbolleiste angezeigt:

   ![](images/topic-version-none_cs.png){width="550" align="left"}

2. Die Versionsinformationen für ein neu erstelltes Thema werden als *none* angezeigt. Wenn Sie eine neue Version speichern, wird ihr eine Versionsnummer als 1.0 zugewiesen.

3. Wenn Ihr Administrator Ihren Editor so konfiguriert hat, dass Dateien vor der Bearbeitung gesperrt werden, können Sie eine Datei erst bearbeiten, nachdem Sie sie gesperrt haben. Ebenso werden Sie, falls konfiguriert, aufgefordert, gesperrte Dateien zu entsperren, bevor Sie sie schließen.

4. Nachdem Sie Ihr DITA-Thema erstellt haben, speichern Sie die Änderungen in Ihrer Arbeitskopie weiter und erstellen Sie eine neue Version, sobald Sie die Aktualisierungen für Ihr Thema abgeschlossen haben.

**Übergeordnetes Thema:**[ Erstellen und Vorschau von Themen](create-preview-topics.md)
