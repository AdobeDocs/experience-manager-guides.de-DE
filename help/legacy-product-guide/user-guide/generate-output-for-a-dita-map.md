---
title: Generieren der Ausgabe für eine DITA-Zuordnung über die Zuordnungskonsole
description: Generieren Sie die Ausgabe für eine DITA-Zuordnung über die Zuordnungskonsole in AEM Guides. Erfahren Sie mehr über die inkrementelle Ausgabegenerierung und wie Sie den Status, den Abbruch und das Löschen einer Ausgabenaufgabe anzeigen können.
exl-id: d6cbd44c-e74c-4192-bcc4-fb7752c59508
feature: Publishing
role: User
source-git-commit: 7db3df07fd17eecae1c502554118ca12f95fb5ab
workflow-type: tm+mt
source-wordcount: '1418'
ht-degree: 0%

---

# Generieren der Ausgabe für eine DITA-Zuordnung über die Zuordnungskonsole {#id1825FG00UHT}

Führen Sie die folgenden Schritte aus, um die Ausgabe für eine DITA-Zuordnung zu generieren:

1. Navigieren Sie in der Assets-Benutzeroberfläche zu der DITA-Map-Datei, die Sie veröffentlichen möchten, und klicken Sie darauf.

   Die DITA-Zuordnungskonsole wird mit der Liste der zum Generieren der Ausgabe verfügbaren Ausgabevorgaben angezeigt.

1. Wählen Sie eine oder mehrere Ausgabevorgaben aus, die Sie zum Generieren der Ausgabe verwenden möchten.

   ![](images/generate-multiple-outputs-uuid.png){width="800" align="left"}

   >[!NOTE]
   >
   > Wenn Sie die AEM Site-Ausgabe generieren, verwendet der Veröffentlichungsprozess die in der Datei `.ditamap` definierte Struktur, um AEM Site-Struktur zu erstellen.

1. Klicken Sie auf das Symbol Generieren , um den Prozess zur Generierung der Ausgabe zu starten.


Sie können den aktuellen Status der Ausgabegenerierungsanforderung anzeigen, indem Sie auf &quot;Ausgaben&quot;klicken. Weitere Informationen finden Sie unter [Status der Ausgabegenerierungsaufgabe anzeigen](#viewing_output_history)

>[!IMPORTANT]
>
> Wenn sich ein Ausgabeerstellungsprozess für eine Vorgabe entweder in der Warteschlange befindet oder in Bearbeitung ist, können Sie keine weitere Ausgabegenerierungsaufgabe für dieselbe Vorgabe starten.

Sie können die PDF-Ausgabe für eine oder mehrere Ausgabevorgaben generieren, die für eine DITA-Zuordnung erstellt wurden, vom Web Editor aus. Weitere Informationen finden Sie unter [Verwenden des Bereichs &quot;Schnellgenerierung&quot;, um die Ausgabe für die Vorgaben zu generieren und anzuzeigen](web-editor-quick-generate-panel.md#).

Sie können auch die AEM Site-Ausgabe für ein oder mehrere Themen oder die gesamte DITA-Zuordnung aus dem Web Editor generieren. Weitere Informationen finden Sie unter [Artikelbasierte Veröffentlichung im Web-Editor](web-editor-article-publishing.md#id218CK0U019I).

## Inkrementelle Generierung der Ausgabe {#generating_standalone_topic}

>[!NOTE]
>
> Die inkrementelle Generierung der Ausgabe ist nur für AEM Site-Ausgabe verfügbar. Außerdem können Sie DITA- \(.dita/.xml\) Themen nur aus einer DITA-Zuordnung oder Unterzuordnungen neu generieren. Wenn Sie eine DITA-Zuordnung, Unterzuordnung, Themengruppe oder ein Thema mit &quot;`@processing-role="resource-only"`&quot;auswählen, ist die Neuerstellungsoption nicht verfügbar.

Es kann eine Reihe von Fällen geben, in denen Sie nur einige Themen in Ihrer DITA-Map aktualisieren und nur diese aktualisierten Themen live übertragen. Um solche Szenarien zu handhaben, können Sie mit AEM Guides inkrementelle Ausgaben erstellen. Wenn Sie einige Themen aktualisiert haben, müssen Sie nicht die gesamte DITA-Map neu generieren. Sie können nur die aktualisierten Themen auswählen und neu generieren.

Wenn Ihre Zuordnung chunked ist und Sie ein einzelnes Thema in dieser Zuordnung aktualisiert haben, müssen Sie die gesamte Zuordnung für das aktualisierte Thema oder den aktualisierten Inhalt neu generieren, um es in der Ausgabe widerzuspiegeln. Sie erhalten die Option zur Neuerstellung der Ausgabe nicht auf Themenebene, sondern nur auf der Ebene der \(Chunked\) Zuordnung. Dies gilt für die übergeordnete Zuordnung und alle Unterkarten.

Führen Sie die folgenden Schritte aus, um die Ausgabe für ein bestimmtes Thema oder eine bestimmte Themengruppe neu zu generieren:

>[!IMPORTANT]
>
> Wenn Sie die Ausgabe der AEM Site neu generieren, wird die Ausgabe mit der aktuellen Version der Dateien erstellt und nicht mit der angehängten Grundlinie.

1. Navigieren Sie in der Assets-Benutzeroberfläche zur DITA-Zuordnungsdatei und klicken Sie darauf.

   Die DITA-Zuordnungskonsole wird mit der Liste der zum Generieren der Ausgabe verfügbaren Ausgabevorgaben angezeigt.

1. Wählen Sie die Registerkarte **Themen** aus.

   Eine Liste der in der DITA-Map verfügbaren Themen wird angezeigt.

1. Wählen Sie die Themen aus, die Sie neu erstellen möchten.

   >[!NOTE]
   >
   > Wenn Sie der DITA-Map neue Themen hinzugefügt haben, können Sie diese neuen Themen von hier aus nicht generieren. Sie müssen zuerst die neu hinzugefügten Themen veröffentlichen, indem Sie die DITA-Map-Veröffentlichungsfunktion verwenden.

   ![](images/regenerate-topics.png){width="800" align="left"}

1. Klicken Sie auf **Regenerate**.

   Die Seite Ausgewählte Themen regenerieren wird angezeigt.

1. Wählen Sie die Ausgabevorgabe aus, die Sie zum erneuten Generieren der ausgewählten Themen verwenden möchten.

1. Klicken Sie auf **Regenerate** , um den Generierungsprozess der Ausgabe zu starten.


>[!IMPORTANT]
>
> Wenn Sie einen Thementitel umbenennen und das Thema neu generieren, wird der aktualisierte Thementitel nicht im Inhaltsverzeichnis der DITA-Map angezeigt. Um den Thementitel im Inhaltsverzeichnis zu aktualisieren, müssen Sie die gesamte DITA-Zuordnung generieren.

Sie können den aktuellen Status der Ausgabegenerierungsanforderung anzeigen, indem Sie auf &quot;Ausgaben&quot;klicken. Weitere Informationen finden Sie unter [Status der Ausgabegenerierungsaufgabe anzeigen](#viewing_output_history).

## Status der Ausgabegenerierungsaufgabe anzeigen {#viewing_output_history}

Nachdem Sie die Ausgabegenerierungsaufgabe für eine Zuordnung initiiert oder ausgewählte Themen neu generiert haben, sendet AEM Guides diese Aufgabe an die Ausgabegenerierungswarteschlange. Diese Warteschlange wird in Echtzeit aktualisiert und zeigt den Status jeder Ausgabegenerierungsaufgabe in der Warteschlange an.

Führen Sie die folgenden Schritte aus, um die Ausgabegenerierungswarteschlange anzuzeigen:

1. Navigieren Sie in der Assets-Benutzeroberfläche zu der Zuordnungsdatei, für die Sie den Status der Ausgabegenerierung überprüfen möchten, und klicken Sie darauf.

1. Klicken Sie auf **Ausgaben**.

   ![](images/output-queued.png){width="800" align="left"}

   Die Seite &quot;Ausgaben&quot;ist in zwei Teile unterteilt:

   - **In die Warteschlange gestellte Ausgaben:**

     Listet die Ausgaben auf, die darauf warten, generiert zu werden oder sich im Generierungsprozess befinden. Die Aufgaben in der Warteschlange oder in Bearbeitung werden mit einem blauen Farbsymbol vor dem Vorgabennamen angezeigt. Sie finden außerdem die Einstellung zur Generierung der Ausgabe oder die Vorgabe, die für die in der Warteschlange befindliche Aufgabe verwendet wird, den Typ, den Benutzer, der die Aufgabe initiiert hat, die Zeit seit der Warteschlange der Aufgabe und den aktuellen Status.

     Klicken Sie auf den Link, um auf das **Publish Dashboard** zuzugreifen und den aktuellen Ausführungsstatus anzuzeigen. Eine Liste aller aktiven Veröffentlichungsaufgaben ist im Publish Dashboard verfügbar. Der Link **In die Warteschlange gestellte Ausgaben** und der Link **Publish Dashboard** werden nur angezeigt, wenn Ausgaben vorhanden sind, die darauf warten, generiert zu werden oder sich im Generierungsprozess befinden. Sie werden nicht angezeigt, wenn die Ausgabeaufgaben abgeschlossen sind. Weitere Informationen zum Publish-Dashboard finden Sie unter [Verwalten von Veröffentlichungsaufgaben mit dem Publish-Dashboard](generate-output-publish-dashboard.md#).

   - **Erzeugte Ausgaben**

     Listet die abgeschlossenen Ausgabenaufgaben auf. Auch hier werden einige Unterschiede im Abschnitt &quot;In die Warteschlange gestellte Ausgaben&quot;angezeigt. Sie verfügen über neue Informationen in Form des Ausgabedosten-Symbols und der Zeit der Ausgabenerstellung.

     In dieser Liste können Aufgaben aufgeführt sein, die erfolgreich ausgeführt wurden, Aufgaben, die mit der Nachricht ausgeführt wurden, oder fehlgeschlagene Aufgaben. Die erfolgreichen Aufgaben werden mit einem grünen Farbsymbol angezeigt, die Aufgaben mit einer Nachricht haben ein orangefarbenes Symbol und die fehlgeschlagenen Aufgaben werden mit einem roten Farbsymbol angezeigt.

     Für alle Aufgaben erstellt der Veröffentlichungsprozess eine Protokolldatei \(logs.txt\), auf die über den Link in der Spalte Generiert am zugegriffen werden kann. Für Aufgaben, die fehlgeschlagen sind oder Meldungen aufweisen, können Sie die Protokolldatei überprüfen, die im Abschnitt [Anzeigen und Überprüfen der Protokolldatei](generate-output-basic-troubleshooting.md#id1822G0P0CHS) erläutert wird.

     >[!NOTE]
     >
     > Wenn Sie auf einen Link der generierten PDF-Ausgabe klicken, werden Sie aufgefordert, die PDF herunterzuladen. Dies ist das Standardverhalten in AEM 6.5 und 6.4.


## Aufgabe zur Generierung einer Ausgabe abbrechen {#id2061H100T5Z}

AEM Guides bietet Publishern eine einfache und einfache Möglichkeit, laufende Veröffentlichungsaufgaben abzubrechen. Als Herausgeber können Sie eine laufende Veröffentlichungsaufgabe über die DITA-Zuordnungskonsole oder das [Publish-Dashboard](generate-output-publish-dashboard.md#) abbrechen.

Führen Sie die folgenden Schritte aus, um eine Ausgabegenerierungsaufgabe über die DITA-Zuordnungskonsole abzubrechen:

1. Navigieren Sie in der Assets-Benutzeroberfläche zu der Zuordnungsdatei, für die Sie eine laufende Ausgabegenerierungsaufgabe abbrechen möchten, und klicken Sie darauf.

1. Klicken Sie auf **Ausgaben**.

1. Bewegen Sie in der Liste &quot;In die Warteschlange gestellte Ausgaben&quot;den Mauszeiger über eine Aufgabe, die Sie abbrechen möchten.

1. Klicken Sie auf das Symbol *Vorgang abbrechen* .

   ![](images/cancel-publish-task-map-console.png){width="800" align="left"}

1. Klicken Sie in der Meldung Abbruch bestätigen auf **Ja** .

   ![](images/confirm-cancel-output-map-condole.png){width="800" align="left"}

   Wenn die Aufgabe noch nicht gestartet wurde, wird der Befehl &quot;Abbrechen&quot;für die Aufgabe ausgeführt. Für eine Aufgabe, die abgebrochen wird, ist der Status auf &quot;Abbrechen&quot;eingestellt.

   Nachdem die Aufgabe erfolgreich abgebrochen wurde, wird sie in die Liste **Erzeugte Ausgaben** mit dem Status **Abgebrochen** verschoben. Wenn Sie den Mauszeiger über die abgebrochene Aufgabe bewegen, wird der Name des Benutzers angezeigt, der die Aufgabe abgebrochen hat. Im folgenden Screenshot wird die Aufgabe *HTML5* abgebrochen.

   ![](images/cancelled-output-task.png){width="800" align="left"}


## Ausgabeaufgabe aus DITA-Map-Konsole löschen

Wenn Sie mehrere Ausgaben für eine DITA-Zuordnung generieren, wird die Liste der generierten Ausgaben für eine solche Zuordnung über einen bestimmten Zeitraum sehr lang. Als Herausgeber können Sie den Ausgabedarstellungsverlauf einer beliebigen Zuordnungsdatei bereinigen, indem Sie die veralteten Aufgaben aus der Liste *Erzeugte Ausgaben* entfernen. Beachten Sie, dass die Ausgabe nicht aus dem System entfernt wird, sondern nur der Eintrag der generierten Ausgabe aus der Liste *Erzeugte Ausgaben* entfernt wird.

Führen Sie die folgenden Schritte aus, um eine Ausgabeaufgabe aus der Liste &quot;Generierte Ausgabe&quot;zu entfernen:

1. Navigieren Sie in der Assets-Benutzeroberfläche zu der Zuordnungsdatei, aus der Sie die Aufgaben löschen möchten, und klicken Sie darauf.

1. Klicken Sie auf **Ausgaben**.

1. Bewegen Sie in der Liste Erzeugte Ausgaben den Mauszeiger über eine Aufgabe, die Sie löschen möchten.

1. Klicken Sie auf das Löschsymbol.

   ![](images/delete-output-task.png){width="800" align="left"}

1. Klicken Sie in der Eingabeaufforderung Löschungsmeldung bestätigen auf **Ja**.

   Die Aufgabe wird aus der Liste Erzeugte Ausgaben gelöscht.


**Übergeordnetes Thema:**[ Ausgabegenerierung](generate-output.md)
