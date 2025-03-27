---
title: Output-Erzeugung
description: Verwalten Sie den Prozess der Ausgabenerstellung in AEM Sites, PDF, HTML5, EPUB, Custom und JSON über DITA-OT-Plug-ins, native PDF-Veröffentlichung und FMPS in AEM Guides.
feature: Publishing
role: User
exl-id: 11bb3604-f45c-4df7-be74-588dbf8594af
source-git-commit: ac83f613d87547fc7f6a18070545e40ad4963616
workflow-type: tm+mt
source-wordcount: '781'
ht-degree: 0%

---

# Output-Erzeugungsprozess verwalten

Mit Adobe Experience Manager Guides können Sie die folgenden Aktionen für die generierte Ausgabe ausführen:

- [Anzeigen des Status der Ausgabegenerierungsaufgabe](#view-the-status-of-the-output-generation-task)
- [Aufgabe zum Erzeugen einer Ausgabe abbrechen](#cancel-an-output-generation-task)
- [Ausgabeaufgabe löschen](#delete-an-output-task)

## Anzeigen des Status der Ausgabegenerierungsaufgabe

Nachdem Sie die Ausgabegenerierungsaufgabe für eine Zuordnung initiiert oder ausgewählte Themen neu generiert haben, sendet Experience Manager Guides diese Aufgabe an die Ausgabegenerierungswarteschlange. Diese Warteschlange wird in Echtzeit aktualisiert und zeigt den Status jeder Ausgabegenerierungsaufgabe in der Warteschlange an.

1. Navigieren Sie in der Assets-Benutzeroberfläche zu der Zuordnungsdatei, für die Sie den Status der Ausgabegenerierung überprüfen möchten, und öffnen Sie sie.

1. Wählen Sie **OUTPUTS** aus.

   ![](images/output-queued.png){align="left"}

   Die Seite „Ausgaben“ ist in zwei Teile unterteilt:

   - **Ausgänge in der Warteschlange:**

     Listet die Ausgaben auf, die entweder auf die Generierung warten oder sich im Generierungsprozess befinden. Die Aufgaben in der Warteschlange oder in Bearbeitung werden mit einem blauen Farbsymbol vor dem Voreinstellungsnamen angezeigt. Sie finden auch die Einstellung für die Ausgabegenerierung oder die Voreinstellung für die Aufgabe in der Warteschlange, den Typ, den Benutzer, der die Aufgabe initiiert hat, den Zeitpunkt, seit dem die Aufgabe in die Warteschlange gestellt wird, und den aktuellen Status.

     Wählen Sie den Link aus, um auf das **Dashboard veröffentlichen** zuzugreifen und den aktuellen Status der Ausführung anzuzeigen. Eine Liste aller aktiven Veröffentlichungsaufgaben ist im Veröffentlichungs-Dashboard verfügbar. Die **Eingereihte Ausgaben** und der **Veröffentlichungs-Dashboard** Link werden nur angezeigt, wenn es Ausgaben gibt, die entweder darauf warten, generiert zu werden, oder sich im Generierungsprozess befinden. Sie werden nicht angezeigt, wenn die Ausgabeaufgaben abgeschlossen wurden. Weitere Informationen über das Dashboard „Veröffentlichen“ finden Sie unter [Verwalten von Veröffentlichungsaufgaben mithilfe des Dashboards „Veröffentlichen“](generate-output-publish-dashboard.md#).

   - **Erzeugte Ausgaben**

     Listet die abgeschlossenen Ausgabeaufgaben auf. Auch hier sind die Informationen, die angezeigt werden, mit einigen Unterschieden ähnlich wie der Abschnitt „Gereihte Ausgaben“. Sie haben neue Informationen in Form des Ausgabeergebnissymbols und der Ausgabegenerierungszeit.

     In dieser Liste können Sie Aufgaben, die erfolgreich ausgeführt wurden, Aufgaben, die mit einer Nachricht ausgeführt wurden, oder fehlgeschlagene Aufgaben anzeigen. Die erfolgreichen Aufgaben werden mit einem grünen Farbsymbol angezeigt, die Aufgaben mit einer Nachricht haben ein orangefarbenes Farbsymbol und die fehlgeschlagenen Aufgaben werden mit einem roten Farbsymbol angezeigt.

     Für alle Aufgaben erstellt der Veröffentlichungsprozess eine Protokolldatei \(logs.txt\), auf die Sie zugreifen können, indem Sie den Link in der Spalte Generiert unter auswählen. Bei fehlgeschlagenen Aufgaben oder bei Meldungen können Sie die Protokolldatei überprüfen. Weitere Informationen hierzu finden Sie im Abschnitt [Anzeigen und Überprüfen der Protokolldatei](generate-output-basic-troubleshooting.md#id1822G0P0CHS).

     >[!NOTE]
     >
     > Wenn Sie den Link der generierten PDF-Ausgabe auswählen, werden Sie aufgefordert, die PDF herunterzuladen.


## Aufgabe zum Erzeugen einer Ausgabe abbrechen

Experience Manager Guides bietet Publishern eine einfache Möglichkeit, laufende Veröffentlichungsaufgaben abzubrechen. Als Herausgeber können Sie eine laufende Veröffentlichungsaufgabe über die DITA Map-Konsole oder das [Dashboard veröffentlichen“ ](generate-output-publish-dashboard.md#).

Führen Sie die folgenden Schritte aus, um eine Aufgabe zur Ausgabegenerierung über die DITA-Zuordnungskonsole abzubrechen:

1. Navigieren Sie in der Assets-Benutzeroberfläche zu der Zuordnungsdatei, für die Sie eine laufende Ausgabegenerierungsaufgabe abbrechen möchten, und öffnen Sie sie.

1. Wählen Sie **OUTPUTS** aus.

1. Bewegen Sie in **Liste &quot;** Ausgaben“ den Mauszeiger über eine Aufgabe, die Sie abbrechen möchten.

1. Wählen Sie das Symbol **Diesen Auftrag abbrechen** aus.

   ![](images/cancel-publish-task-map-console.png){align="left"}

1. Wählen **auf** Eingabeaufforderung **Abbruch bestätigen** die Option „Ja“.

   ![](images/confirm-cancel-output-map-console.png){align="left"}

   Wenn die Aufgabe noch nicht gestartet wurde, wird der Abbruchbefehl für die Aufgabe ausgeführt. Für eine Aufgabe, die abgebrochen wird, wird der Status auf Abbruch gesetzt.

   Nachdem die Aufgabe erfolgreich abgebrochen wurde, wird sie in die Liste **Erzeugte Ausgaben** mit dem Status **Abgebrochen** verschoben. Wenn Sie den Mauszeiger über die abgebrochene Aufgabe bewegen, wird der Name des Benutzers angezeigt, der die Aufgabe abgebrochen hat. Im folgenden Screenshot wird die Aufgabe *HTML* abgebrochen.

   ![](images/cancelled-output-task.png){align="left"}


## Ausgabeaufgabe löschen

Wenn Sie mehrere Ausgaben für eine DITA-Zuordnung generieren, wird die Liste Erzeugte Ausgaben für eine solche Zuordnung über einen bestimmten Zeitraum sehr lang. Als Herausgeber können Sie den Ausgabehistorie jeder Zuordnungsdatei bereinigen, indem Sie die veralteten Aufgaben aus der Liste *Erzeugte Ausgaben* entfernen. Beachten Sie, dass die Ausgabe nicht aus dem System entfernt wird, sondern nur der Eintrag der generierten Ausgabe aus der Liste *Generierte Ausgaben* entfernt wird.

Führen Sie die folgenden Schritte aus, um eine Ausgabeaufgabe aus der Liste Erzeugte Ausgabe zu entfernen:

1. Navigieren Sie in der Assets-Benutzeroberfläche zu der Zuordnungsdatei, aus der Sie die Aufgaben löschen möchten, und öffnen Sie sie.

1. Wählen Sie **OUTPUTS** aus.

1. Bewegen Sie in **Liste „Erzeugte**&quot; den Mauszeiger über eine Aufgabe, die Sie löschen möchten.

1. Wählen Sie das Löschsymbol aus.

   ![](images/delete-output-task.png){align="left"}

1. Wählen Sie **Ja** in der **Löschen bestätigen** aus.

   Die Aufgabe wird aus der Liste Erzeugte Ausgaben gelöscht.
