---
title: Geänderte Themen übersetzen
description: Erfahren Sie, wie Sie ein geändertes Thema in AEM Guides erneut übersetzen.
feature: Translation
role: User
hide: true
exl-id: b623b109-8695-40e5-9e28-78f78cf57ad6
source-git-commit: ea597cd14469f21e197c700542b9be7c373aef14
workflow-type: tm+mt
source-wordcount: '607'
ht-degree: 0%

---

# Geänderte Themen übersetzen {#id16A5A0B6072}

Wenn Sie Änderungen an einigen Themen vornehmen, müssen diese Themen erneut übersetzt werden. Sie können geänderte Themen aus der DITA-Karte verfolgen. Klicken Sie im Ordner für die Sprachkopie auf die DITA-Zuordnungsdatei und dann auf die Registerkarte Übersetzung. Sie können den Status der einzelnen Themen sehen, unabhängig davon, ob sie neu übersetzt werden müssen oder nicht.

Führen Sie die folgenden Schritte aus, um ein geändertes Thema zur erneuten Übersetzung zu senden:

1. Klicken Sie auf die DITA-Zuordnungsdatei im Ordner der Quellsprache.

1. Klicken Sie auf die **Übersetzung**.

1. Wählen Sie im Bedienfeld **Filter** auf der linken Seite die **Übersetzungssprachen** aus, deren Status Sie überprüfen möchten, und klicken Sie auf **Fertig**.

   Sie können den Übersetzungsstatus für jedes Thema anzeigen. Themen, für die eine andere Themenrevision verfügbar ist als die, die zur Übersetzung gesendet wurde, haben den Status **veraltet**.

   >[!NOTE]
   >
   > Der Übersetzungs-Workflow vergleicht die zuletzt gespeicherte Revision der Themendatei im Ordner der Ausgangssprache mit der übersetzten Version.

   Wenn Sie auf den Pfeil klicken, um weitere Details anzuzeigen. Sie können die jeweilige Sprachkopie sehen, die veraltet ist.

   ![](images/out-of-sync-uuid.png){width="800" align="left"}

1. Aktivieren Sie das Kontrollkästchen, um die Themen auszuwählen, die zur erneuten Übersetzung gesendet werden sollen.

   Wenn Sie ein Nicht synchronisierungsdatum auswählen, wird die Option **Sprachkopien erstellen/aktualisieren** im Bedienfeld „Verweise“ und die Schaltfläche **Nicht synchronisierungsstatus** über dem Symbol **Filtern** angezeigt.

   Sie können die Schaltfläche **Nicht synchronisiert verwerfen** verwenden, um den Status Nicht mehr aktuell für die Themen in der DITA-Zuordnung zu überschreiben. Wenn Sie beispielsweise an der englischen Version des Themas Änderungen vorgenommen haben, die nicht übersetzt werden müssen, können Sie diese Schaltfläche verwenden und den Status Veraltet für das ausgewählte Thema ändern.

   >[!NOTE]
   >
   > Wenn Sie auf die Schaltfläche **Nicht synchronisierungsstatus verwerfen** klicken, wird der Themenstatus für die ausgewählten veralteten Themen auf „Aktuell“ festgelegt.

1. Klicken Sie **Sprachkopien aktualisieren** und konfigurieren Sie den Übersetzungsauftrag.

1. Sie können wählen, ob Sie ein neues Übersetzungsprojekt erstellen oder Themen zu einem vorhandenen Übersetzungsprojekt hinzufügen möchten. Geben Sie die erforderlichen Details an, um das Übersetzungsprojekt zu konfigurieren.

1. Klicken Sie auf **Starten**.

   Eine Bestätigungsmeldung wird angezeigt, dass das Thema zur Übersetzung versendet wurde.

1. Navigieren Sie in der Projektkonsole zum Übersetzungsprojekt. Im Ordner wird eine neue Karte für Übersetzungsaufträge erstellt. Klicken Sie auf die Auslassungszeichen, um die Assets des Ordners anzuzeigen.

   ![](images/incremental-job.PNG){width="300" align="left"}

1. Um die Übersetzung zu starten, klicken Sie auf der Karte Übersetzungsauftrag auf den Pfeil und wählen Sie **Starten** aus der Liste aus. Eine Meldung informiert Sie darüber, dass der Vorgang gestartet wurde.

   Sie können den Status des zu übersetzenden Themas auch anzeigen, indem Sie unten auf der Karte „Übersetzungsauftrag“ auf die Auslassungszeichen klicken.

   >[!NOTE]
   >
   > Wenn Sie den menschlichen Übersetzungs-Service verwenden, müssen Sie die Inhalte für die Übersetzung exportieren. Sobald Sie die übersetzten Inhalte haben, müssen Sie sie wieder in das Übersetzungsprojekt importieren.

1. Nach Abschluss der Übersetzung ändert sich der Status in **Bereit für Überprüfung**. Klicken Sie auf die Auslassungszeichen, um Themendetails anzuzeigen, und führen Sie einen der folgenden Schritte auf der Symbolleiste aus:

   - Klicken Sie **In Assets einblenden**, um die Übersetzung anzuzeigen und zu überprüfen.

   - Klicken Sie **Übersetzung akzeptieren**, wenn Sie der Meinung sind, dass die Änderungen korrekt übersetzt wurden. Eine Bestätigungsmeldung wird angezeigt.

   - Klicken Sie **Übersetzung ablehnen** wenn Sie der Meinung sind, dass der Vorgang wiederholt werden muss. Eine Ablehnungsmeldung wird angezeigt.

   >[!NOTE]
   >
   > Es ist wichtig, das übersetzte Asset zu akzeptieren oder abzulehnen, da sonst die Datei am temporären Speicherort bleibt und nicht in DAM kopiert wird.

1. Navigieren Sie zurück zur DITA-Zuordnungsdatei im Ordner für die Ausgangssprache in der Assets-Benutzeroberfläche. Die neu übersetzten Themen sind jetzt synchronisiert.


**Übergeordnetes Thema:**&#x200B;[&#x200B; Inhalte übersetzen](translation.md)
