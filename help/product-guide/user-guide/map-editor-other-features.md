---
title: Weitere Funktionen des Zuordnungs-Editors
description: Entdecken Sie einige allgemeine Funktionen im Karteneditor. Erfahren Sie, wie Sie wichtige Verweise im Zuordnungs-Editor auflösen.
exl-id: f0e7a402-ac12-4c63-9d7f-92567ee29a39
feature: Authoring, Map Editor
role: User
TQID: https://experienceleague.adobe.com/Af2mFR-OG-QTbQU7HBQb-kfvuCcw5fd89CA4-mSroNE
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2:
  - id: ab01a588-7dea-43f2-a699-0b3f128465d6
  - id: d90290ec-3e61-4ebd-8649-bcafe0836803
subfeature_v2:
  - id: ad602516-aca3-4247-9ae8-f393d958efa9
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
source-git-commit: fd5e1e85933eb2785b0a74b0fa49fec1da4ca0c2
workflow-type: tm+mt
source-wordcount: 1281
ht-degree: 0%

---

# Zusätzliche Funktionen im Karten-Editor {#id1942D0T0HUI}

Zu den gebräuchlichen Funktionen im Zuordnungs-Editor gehören:

## Auflösen von Schlüsselverweisen {#id176GD01H05Z}

Ein DITA-Inhaltsschlüssel-Verweis (oder `conkeyref`) ist ein Mechanismus zum Einfügen eines Teils des Inhalts von einem Thema in ein anderes. Dieser Mechanismus verwendet den Schlüssel zum Auffinden des wiederzuverwendenden Inhalts und nicht den direkten Inhaltsverweismechanismus. Weitere Informationen zu direkten und indirekten Verweisen in DITA finden Sie unter *DITA-Adressierung* in der DITA-Sprachspezifikation von OASIS.

Wenn mit dem DITA-Thema Schlüsselverweise verknüpft sind, müssen diese aufgelöst werden, bevor ein Thema in der Vorschau angezeigt, bearbeitet oder überprüft werden kann.

Die Schlüsselverweise werden auf der Grundlage der Stammzuordnung aufgelöst, die in der folgenden Prioritätsreihenfolge festgelegt ist:

1. Benutzereinstellungen
1. Kartenansichtsbereich
1. Ordnerprofil

Die in den Benutzereinstellungen ausgewählte Stammzuordnung hat die höchste Priorität, um wichtige Verweise aufzulösen, gefolgt vom Bereich für die Zuordnungsansicht und der Stammzuordnung des Ordnerprofils. Wenn in den Benutzereinstellungen also keine Zuordnung festgelegt ist, wird die im Bereich „Kartenansicht“ geöffnete Zuordnung verwendet. Wenn im Bereich der Zuordnungsansicht keine Zuordnung geöffnet ist, wird der Zuordnungssatz im Ordner Profile verwendet, um die Schlüsselverweise aufzulösen.

Die Schlüsselverweise können in einer DITA-Map-Datei oder einer separaten DITA-Datei gespeichert werden. In Experience Manager Guides können Sie wichtige Verweise entweder auf Projekt- oder Sitzungsebene angeben. Wenn für die Benutzersitzung bereits eine Stammzuordnung definiert ist, wird diese zur Auflösung der Schlüssel verwendet. Andernfalls wird die Standard-Stammzuordnung für diesen Ordner verwendet. Wenn keine standardmäßige Stammzuordnung konfiguriert ist, werden die fehlenden Schlüsselverweise für den Benutzer hervorgehoben.

Es gibt mehrere Möglichkeiten, wichtige Verweise in einem DITA-Thema aufzulösen, indem Sie die DITA-Zuordnung definieren, die an den folgenden Stellen verwendet werden soll:

**Projekteigenschaften** - Sie können im Abschnitt Projekteigenschaften eine Stammzuordnung definieren, in der die wichtigsten Verweise beim Erstellen eines Projekts aufgelöst werden.

Diese Stammzuordnung gilt für alle mit diesem Projekt verknüpften Assets \(Ordner und Unterordner\). Für Inhalte, auf die in mehreren Projekten verwiesen wird, wird eine alphabetische Liste der Projekte beibehalten und die standardmäßige Stammzuordnung, die mit dem ersten Projekt verknüpft ist, wird verwendet. Sie können auch die DITA-Map auswählen, die für die Auflösung von Schlüsselverweisen in der Liste verwendet werden soll.

**Themenvorschau** - Wählen Sie im Themenvorschaumodus in der Symbolleiste das Symbol für die Tastenauflösung und dann die DITA-Datei aus, die für die Schlüsselverweise verwendet werden soll.

**Themenbearbeitungsansicht** - Wählen Sie beim Bearbeiten eines DITA-Themas das Symbol für die Tastenauflösung und dann die DITA-Datei aus, die für die Auflösung der Schlüsselverweise verwendet werden soll.

## Hinzufügen von Navigationsverweisen

Das `navref`-Element wird in einer DITA-Zuordnung verwendet, um Navigationsverweise aus einer anderen DITA-Zuordnung einzuschließen. Dadurch können Autoren Navigationsstrukturen wie freigegebene Menüs oder Links wiederverwenden, ohne den tatsächlichen Inhalt der referenzierten Zuordnung mit der Ausgabe zusammenzuführen.

>[!NOTE]
>
> Das `navref`-Element ist ausschließlich für Navigationszwecke innerhalb der Kartenstruktur vorgesehen. Es trägt nicht zur generierten DITA-Zuordnungsausgabe bei und wird von der Verarbeitung ausgeschlossen und in der Zuordnungsansicht, in Berichten, in der Grundlinie, in der Übersetzung und in der Vorschau angezeigt.

Führen Sie die folgenden Schritte aus, um einer Zuordnung Navigationsverweise hinzuzufügen:

1. Öffnen Sie die DITA-Zuordnungsdatei, der Sie einen Navigationsverweis hinzufügen möchten.

   Die Zuordnungsdatei wird im Zuordnungs-Editor geöffnet.
1. Wechseln Sie zur Autorenansicht und platzieren Sie den Cursor an einer gültigen Position für eine Navigationsreferenz.
1. Wählen Sie die Option **Element** in der Symbolleiste aus.
1. Wählen Sie im **Element einfügen** die Option **navref**.

   ![](./images/select-navref-element.png)
1. Das **Pfad auswählen** wird angezeigt. Wählen Sie eine Zuordnungsdatei aus, die Sie als Navigationsreferenz in Ihre Zuordnung aufnehmen möchten, und wählen Sie **Auswählen**.

Ein Navigationsverweis der ausgewählten Zuordnungsdatei wird am angegebenen Speicherort hinzugefügt. Außerdem wird der Titel der referenzierten Zuordnung sowohl in der Autoren- als auch in der Layout-Ansicht angezeigt.

![](./images/navref-added-author-view.png)

*Autorenansicht*

![](./images/navref-added-layout-view.png)

*Layout-Ansicht*

## Ausführen einer Konsistenzprüfung für eine Zuordnung

Mit der Option Konsistenzprüfung ausführen im Kontextmenü können Sie eine Konsistenzprüfung für die ausgewählte Zuordnung ausführen, um Probleme wie fehlerhafte Links, doppelte IDs und Schematron-Validierungsfehler vor der Veröffentlichung zu erfassen.

>[!NOTE]
>
> Diese Funktion ist standardmäßig aktiviert. Wenn Sie diese Funktion lieber nicht in Ihrer Umgebung verwenden möchten, wenden Sie sich an Ihr Customer Success-Team.

Welche Prüfungen ausgeführt werden können, wird durch eine Konsistenzprüfungsvorgabe definiert, die von einem Administrator auf Ordnerprofilebene erstellt und verwaltet wird. Weitere Informationen finden Sie unter [Erstellen und Verwalten von Vorgaben für Konsistenzprüfungen](../install-conf-guide/conf-health-check-preset.md).

Führen Sie die folgenden Schritte aus, um eine Konsistenzprüfung einer Zuordnung durchzuführen:

1. Öffnen Sie eine Karte im Editor.
1. Wählen Sie im Menü Optionen die Option **Konsistenzprüfung ausführen** aus.
   ![](./images/run-health-check-option.png)
1. Das Dialogfeld Konsistenzprüfung ausführen wird angezeigt. Wählen Sie eine Konsistenzprüfungs-Vorgabe aus, die Sie ausführen möchten. Nur die für Ihr Ordnerprofil konfigurierten Vorgaben sind zur Auswahl verfügbar.

   Wenn Sie eine Vorgabe auswählen, werden die definierten Prüfungen in das Dialogfeld geladen.

   ![](./images/health-check-selected-checks.png)
1. *Optional* Baseline auswählen. Wenn Sie keine Grundlinie verwenden möchten, wählen Sie **Keine** aus.
1. Wählen Sie **Ausführen** aus.

Sie können auch eine Konsistenzprüfung für eine Zuordnung über das Bedienfeld **Konsistenzprüfungsbericht** ausführen. Öffnen Sie dazu eine Karte in der Kartenansicht und wählen Sie das Symbol **Konsistenzprüfungsbericht** aus.

![](./images/health-check-report-icon.png)

>[!NOTE]
>
>Diese Option wird nur für eine Karte angezeigt, auf der noch keine Konsistenzprüfung ausgeführt wurde. Wenn auf der Karte bereits eine Konsistenzprüfung ausgeführt wurde, wird durch Klicken auf das Symbol **Konsistenzprüfungsbericht** stattdessen der vorhandene Bericht geöffnet.

Wählen Sie im Bedienfeld **Konsistenzprüfung ausführen** aus.

![](./images/run-health-check-report-panel.png)

Dadurch wird dasselbe Dialogfeld **Konsistenzprüfung ausführen** in dem Sie eine Konsistenzprüfungsvorgabe und eine Grundlinie auswählen können, um eine Konsistenzprüfung für die Zuordnung auszuführen, wie in den obigen Schritten beschrieben.

## Verwenden des Konsistenzprüfungsberichts im Editor

Wenn Sie eine Konsistenzprüfung für eine Zuordnung ausführen, wird der Bericht im Bedienfeld **Konsistenzprüfungsbericht** geöffnet, wie unten dargestellt:

![](./images/health-check-report-panel-editor.png)

### Berichts-Symbolleiste

In der Symbolleiste am oberen Rand des Bedienfelds werden die folgenden Elemente angezeigt:

- **Map name**: Der Name der Zuordnung, für die der Bericht generiert wurde.
- **Infosymbol**: Wählen Sie diese Option aus, um den Vorgabennamen, die Zuordnungsversion und Baseline (falls vorhanden) anzuzeigen, die zum Generieren des Berichts verwendet werden.
- **Filter**: Engt den Bericht auf eine bestimmte Regel ein, z. B. um nur die Ergebnisse der fehlerhaften Links anzuzeigen. Der Filter listet nur die Regeltypen auf, die im aktuellen Bericht zu Ergebnissen geführt haben.
- **Bericht herunterladen**: Lädt den Bericht herunter.
- **Regenerieren**: Führt die Konsistenzprüfung erneut aus.

### Ergebnisse der Konsistenzprüfung

Jedes Ergebnis der ausgewählten Prüfungen wird mit den folgenden Details aufgelistet:
- **Severity**: Der Schweregrad des Ergebnisses, z. B. Fehler, Warnung, Info oder Schweregrad „Schwerwiegend“.
- **Name der Konsistenzprüfungsvorgabe**: Name der Konsistenzprüfungsvorgabe, die zum Generieren des Berichts verwendet wird
- **Regelname**: Die Regel, die das Ergebnis generiert hat, z. B. fehlerhafte Links oder doppelte ID.
- **Zeilennummer**: Die Zeile in der Datei, in der das Problem auftritt.
- **Asset**: Die Datei, in der das Problem gefunden wurde.

Wählen Sie ein Ergebnis aus, um die entsprechende Datei genau in der Zeile zu öffnen, in der das Problem weiterhin besteht.

![](./images/health-check-preset-report-selected.png)

>[!NOTE]
>
>Die Ergebnisse der fehlerhaften Verknüpfung öffnen die Datei im Autorenmodus. Doppelte ID- und Schematron-Validierungsergebnisse öffnen die Datei im Source-Modus.

### Bericht neu generieren

Nachdem Sie ein Problem behoben haben, wählen **in** Symbolleiste die Option „Erneut generieren“ aus, um die Konsistenzprüfung erneut auszuführen und zu bestätigen, dass das Problem behoben ist. Wählen **im angezeigten** Erneut generieren“ die Prüfungen aus, die Sie in den neu generierten Bericht aufnehmen möchten.

![](./images/health-check-preset-report-regenerate.png)

>[!NOTE]
>
> Konsistenzprüfungsberichte sind spezifisch für den Benutzer, der sie erstellt hat. Wenn mehrere Benutzer einen Bericht für dieselbe Zuordnung generieren, zeigt jeder Benutzer seine eigenen Ergebnisse an. Administratoren haben jedoch immer Zugriff auf den neuesten für die Zuordnung generierten Bericht.

### Bericht herunterladen

Wählen Sie **Bericht herunterladen** aus, um den Bericht im XLS-Format mit detaillierten Informationen für jedes Ergebnis herunterzuladen.


**Übergeordnetes Thema:**&#x200B;[&#x200B; Einführung in den Zuordnungs-Editor](map-editor.md)
