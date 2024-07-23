---
title: Geänderte Themen übersetzen
description: Erfahren Sie, wie Sie ein geändertes Thema in AEM Guides erneut übersetzen.
feature: Translation
role: User
source-git-commit: 76c731c6a0e496b5b1237b9b9fb84adda8fa8a92
workflow-type: tm+mt
source-wordcount: '607'
ht-degree: 0%

---

# Geänderte Themen übersetzen {#id16A5A0B6072}

Wenn Sie Änderungen an einigen Themen vornehmen, müssen diese Themen erneut übersetzt werden. Sie können geänderte Themen von der DITA-Zuordnung aus verfolgen. Klicken Sie im Ordner Quellsprachkopie auf die DITA-Zuordnungsdatei und dann auf die Registerkarte Übersetzung . Sie können den Status jedes Themas sehen, ob eine Neuübersetzung erforderlich ist oder nicht.

Führen Sie die folgenden Schritte aus, um ein geändertes Thema zur erneuten Übersetzung zu senden:

1. Klicken Sie auf die DITA-Map-Datei im Ordner &quot;Quellsprachkopie&quot;.

1. Klicken Sie auf die Registerkarte **Übersetzung** .

1. Wählen Sie im Bereich **Filter** auf der linken Seite die Option **Sprachen übersetzen** aus, für die Sie den Status überprüfen möchten, und klicken Sie auf **Fertig**.

   Sie können den Übersetzungsstatus für jedes Thema sehen. In den Themen, für die eine andere Revision des Themas als für die Übersetzung verfügbar ist, wird der Status **Veraltet vom Datum** angezeigt.

   >[!NOTE]
   >
   > Der Übersetzungs-Workflow vergleicht die letzte gespeicherte Revision der Themendatei im Ordner für die Ausgangssprache mit der übersetzten Version.

   Wenn Sie auf den Pfeil klicken, werden weitere Details angezeigt. Sie können die bestimmte Sprachkopie sehen, die veraltet ist.

   ![](images/out-of-sync-uuid.png){width="800" align="left"}

1. Aktivieren Sie das Kontrollkästchen, um die Themen auszuwählen, die Sie zur erneuten Übersetzung senden möchten.

   Wenn Sie ein nicht synchronisiertes Datum auswählen, wird die Option **Sprachkopien erstellen/aktualisieren** im Bereich &quot;Verweise&quot;und die Schaltfläche **Nicht synchronisierten Status verwerfen** oberhalb des Symbols **Filter** angezeigt.

   Sie können die Schaltfläche **Nicht synchronisieren beenden** verwenden, um den Status &quot;Out of Date&quot;für die Themen in der DITA-Map zu überschreiben. Wenn Sie beispielsweise Änderungen an der englischen Version des Themas vorgenommen haben, für das keine Übersetzung erforderlich ist, können Sie diese Schaltfläche verwenden und den Status &quot;Out of Date&quot;für das ausgewählte Thema ändern.

   >[!NOTE]
   >
   > Wenn Sie auf die Schaltfläche **Nicht synchronisierten Status verwerfen** klicken, wird der Themenstatus für die ausgewählten Themen &quot;Nicht aktualisiert&quot;auf &quot;Aktuell&quot;gesetzt.

1. Klicken Sie auf **Sprachkopien aktualisieren** und konfigurieren Sie den Übersetzungsauftrag.

1. Sie können ein neues Übersetzungsprojekt erstellen oder Themen zu einem vorhandenen Übersetzungsprojekt hinzufügen. Geben Sie die erforderlichen Details an, um das Übersetzungsprojekt zu konfigurieren.

1. Klicken Sie auf **Starten**.

   Es wird eine Bestätigungsmeldung angezeigt, die anzeigt, dass das Thema zur Übersetzung gesendet wurde.

1. Navigieren Sie in der Projektekonsole zum Übersetzungsprojekt. Eine neue Übersetzungsauftragskarte wird im Ordner erstellt. Klicken Sie auf die Auslassungszeichen, um die Assets des Ordners anzuzeigen.

   ![](images/incremental-job.PNG){width="300" align="left"}

1. Um die Übersetzung zu starten, klicken Sie auf den Pfeil auf der Karte für den Übersetzungsauftrag und wählen Sie **Start** aus der Liste aus. Eine Meldung informiert Sie darüber, dass der Auftrag gestartet wurde.

   Sie können auch den Status des zu übersetzenden Themas anzeigen, wenn Sie auf das Auslassungszeichen am unteren Rand der Karte für Übersetzungsaufträge klicken.

   >[!NOTE]
   >
   > Wenn Sie den Übersetzungsdienst von Human verwenden, müssen Sie den Inhalt für die Übersetzung exportieren. Sobald Sie den übersetzten Inhalt haben, müssen Sie ihn wieder in das Übersetzungsprojekt importieren.

1. Nach Abschluss der Übersetzung ändert sich der Status in **Bereit zur Überprüfung**. Klicken Sie auf die Auslassungspunkte, um Themendetails anzuzeigen, und führen Sie in der Symbolleiste einen der folgenden Schritte aus:

   - Klicken Sie auf **In Assets einblenden** , um die Übersetzung anzuzeigen und zu überprüfen.

   - Klicken Sie auf **Übersetzung akzeptieren** , wenn Sie glauben, dass die Änderungen korrekt übersetzt wurden. Eine Bestätigungsmeldung wird angezeigt.

   - Klicken Sie auf **Übersetzung ablehnen** , wenn Sie der Meinung sind, dass der Auftrag erneut ausgeführt werden muss. Eine Zurückweisungsmeldung wird angezeigt.

   >[!NOTE]
   >
   > Es ist wichtig, das übersetzte Asset zu akzeptieren oder abzulehnen. Andernfalls bleibt die Datei an einem temporären Speicherort und wird nicht nach DAM kopiert.

1. Navigieren Sie zurück zur DITA-Map-Datei im Ordner für die Ausgangssprache in der Assets-Benutzeroberfläche. Die neu übersetzten Themen sind jetzt synchronisiert.


**Übergeordnetes Thema:**[ Inhalt übersetzen](translation.md)
