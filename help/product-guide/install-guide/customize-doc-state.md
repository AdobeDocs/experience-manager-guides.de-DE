---
title: Dokumentstatus konfigurieren
description: Erfahren Sie, wie Sie Dokumentstatus konfigurieren
exl-id: d7603b4e-aae4-48ca-be84-8edb51626405
feature: Document State
role: Admin
level: Experienced
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '1131'
ht-degree: 0%

---

# Dokumentstatus konfigurieren {#id181GB0400UI}

Mit AEM Guides können Sie die Dokumentstatus für Ihre DITA-Themen entsprechend den Anforderungen Ihres Unternehmens definieren. Sie können verschiedene Status Ihres Dokuments von Anfang bis Ende definieren. Der erste Status kann beispielsweise Entwurf sein und zu Überprüfen, Genehmigt, Übersetzt und schließlich zu Veröffentlicht wechseln.

Es gibt zwei Möglichkeiten, wie ein Thema von einem Status zum anderen übergehen kann: manuelle und automatische. Die in einem Profil definierten Dokumentstatus können zum manuellen Ändern des Dokumentstatus verwendet werden. Dies kann über die Seite Eigenschaften einer Themendatei erfolgen. Sie können auch definieren, wer das Dokument von einem Status in einen anderen verschieben kann. Ein Autor kann beispielsweise ein Dokument erstellen und der Standardstatus des Dokuments kann &quot;Entwurf&quot;lauten. Wenn der Autor das Dokument zur Überprüfung sendet, kann er den Dokumentstatus in &quot;In Überprüfung&quot;ändern. Der Überprüfer kann den Dokumentstatus basierend auf dem Überprüfungsprozess entweder zu Genehmigt oder zu Entwurf erneut ändern. Wenn das Dokument genehmigt ist, kann der Herausgeber den Dokumentstatus abhängig vom Workflow in Übersetzt oder Veröffentlicht ändern.

>[!NOTE]
>
> Wenn ein Benutzer zur Gruppe *Administratoren* gehört, kann der Benutzer den Status eines Dokuments von einem beliebigen Status ändern, unabhängig von den im System definierten Dokumentstatusübergängen.

## Erstellen eines Dokumentstatus

AEM Guides wird mit einer Reihe von Standarddokumentstatus ausgeliefert. Diese Status sind:

- Entwurf
- Bearbeiten
- In Review
- Genehmigt
- Überarbeitet
- Fertig

Diese Standardstatus sind für alle DITA-Themen verfügbar, die unter DAM erstellt wurden. Sie können Ihre eigenen Dokumentstatus erstellen und sie einem bestimmten Ordner zuweisen. Alle DITA-Dateien, die unter diesem Ordner erstellt wurden, haben dann Zugriff auf die neu erstellten Dokumentstatus.

Um Dokumentstatus mithilfe des Ordnerprofils zu erstellen, führen Sie die folgenden Schritte aus:

1. Klicken Sie oben auf den Adobe Experience Manager-Link und wählen Sie **Tools** aus.
1. Wählen Sie **Guides** aus der Liste der Tools aus.
1. Klicken Sie auf die Kachel Dokumentstatus .

   Die Seite Assets-Status wird angezeigt. Standardmäßig zeigt die Seite ein Standardprofil an.

1. Klicken Sie auf **Profil erstellen** und geben Sie die folgenden Details ein:
   - Geben Sie im Feld Profil den Namen für das Profil ein.
   - Geben Sie den Pfad an, auf den Sie das neue Profil anwenden möchten.
   - Geben Sie die Status des Dokuments in den &quot;**Zulässige Status**&quot;unter &quot;**Status**&quot;an. Die standardmäßigen Dokumentstatus sind &quot;Entwurf&quot;, &quot;Bearbeiten&quot;, &quot;In Review&quot;, &quot;Genehmigt&quot;und &quot;Fertig&quot;.

     Klicken Sie auf die Schaltfläche **Hinzufügen** , um einen Dokumentstatus hinzuzufügen.

      - Klicken Sie auf das Symbol Löschen , um einen Dokumentstatus zu löschen.

     >[!NOTE]
     >
     > Löschen Sie keinen Dokumentstatus, wenn sich Dokumente noch in diesem Status befinden. Wenn Sie einen Dokumentstatus löschen, können Sie den Dokumentstatus solcher Dokumente nur ändern, wenn Sie zur Benutzergruppe *administrator* gehören.

   - Geben Sie den Anfangsstatus des Dokuments im Ordner &quot;**Startstatus**&quot;an.
   - Geben Sie den Endstatus des Dokuments im **Endstatus** an.
   - Geben Sie den Statusübergang des Dokuments in **Von** und **bis** unter **Statusübergang** an.

      - Geben Sie die Benutzer und Benutzergruppen an, die den Dokumentstatus in **Gruppen** ändern können.

      - Klicken Sie auf die Schaltfläche **Hinzufügen** , um einen Statusübergang hinzuzufügen.

      - Klicken Sie auf das Symbol Löschen , um eine Statustransition zu löschen.

     >[!NOTE]
     >
     > Löschen Sie keine Statusübergänge, wenn die Dokumente noch den Status &quot;`From`&quot; aufweisen. Wenn Sie eine Statustransition löschen, können Sie den Dokumentstatus solcher Dokumente nur ändern, wenn Sie zur Benutzergruppe *administrator* gehören.

1. Klicken Sie auf **Fertig**.

## Erstellen einer Kopie eines Dokumentstatusprofils

Je nach Anforderung können Sie eine Kopie eines vorhandenen Dokumentstatusprofils erstellen. Sie können die Kopie als Grundlage für die Erstellung eines anderen Dokumentprofils verwenden.

Um eine Kopie eines Dokumentstatusprofils zu erstellen, führen Sie die folgenden Schritte aus:

1. Klicken Sie oben auf den Adobe Experience Manager-Link und wählen Sie **Tools** aus.
1. Wählen Sie **Guides** aus der Liste der Tools aus.
1. Klicken Sie auf die Kachel Dokumentstatus .

   Die Seite Assets-Status wird angezeigt.

1. Wählen Sie das zu duplizierende Dokumentstatusprofil aus und klicken Sie auf **Profil duplizieren**.
1. Nehmen Sie die erforderlichen Änderungen vor und klicken Sie auf **Fertig**.

## Löschen von Dokumentstatus- oder Statusübergängen

>[!NOTE]
>
> Löschen Sie keine Dokumentstatus- oder Statusübergänge, wenn sich Dokumente noch im Status- oder Statusübergang befinden. Wenn Sie einen Status- oder Statusübergang löschen, können Sie den Dokumentstatus solcher Dokumente nur ändern, wenn Sie zur Benutzergruppe *administrator* gehören.

Führen Sie die folgenden Schritte aus, um einen Dokumentstatus- oder Statusübergang aus einem Dokumentstatusprofil zu löschen:

1. Klicken Sie oben auf den Adobe Experience Manager-Link und wählen Sie **Tools** aus.
1. Wählen Sie **Guides** aus der Liste der Tools aus.
1. Klicken Sie auf die Kachel Dokumentstatus .

   Die Seite Assets-Status wird angezeigt.

1. Wählen Sie das Dokumentstatusprofil aus, aus dem Sie den Dokumentstatus löschen möchten, und klicken Sie auf **Profil bearbeiten**.
1. Löschen Sie den Dokumentstatus- oder Statusübergang und klicken Sie auf **Fertig**.

## Löschen von Dokumentstatusprofilen

Um ein Dokumentenstatusprofil zu löschen, führen Sie die folgenden Schritte aus:

1. Klicken Sie oben auf den Adobe Experience Manager-Link und wählen Sie **Tools** aus.
1. Wählen Sie **Guides** aus der Liste der Tools aus.
1. Klicken Sie auf die Kachel Dokumentstatus .

   Die Seite Assets-Status wird angezeigt.

1. Wählen Sie das zu löschende Dokumentstatusprofil aus und klicken Sie auf **Profil löschen**.

## Dokumentstatusänderung automatisieren

Wenn Sie den Dokumentstatus nicht manuell ändern möchten, können Sie einen Workflow erstellen und die Änderung des Dokumentstatus automatisieren.

>[!NOTE]
>
> Automatisierte Workflows sollten den in der Konfiguration definierten Dokumentstatus und Transitionen entsprechen. Das System führt keine Prüfungen auf Statusänderungen durch, die über automatisierte Workflows durchgeführt werden.

Führen Sie die folgenden Schritte aus, um die Änderung des Dokumentstatus zu automatisieren:

1. Öffnen Sie die Workflow-Seite über die AEM-Server-URL.

   `<AEM_Server_URL>:<port>/workflow`

1. Öffnen Sie einen Workflow auf der Workflow-Seite. Beispiel: Thema überprüfen.
1. Wählen Sie **Prozessschritt** aus dem Abschnitt **Workflow** des AEM-Dialogfelds und ziehen Sie den Workflow per Drag-and-Drop.

   ![](assets/process-step-workflow.png)

1. Doppelklicken Sie auf den Prozess und öffnen Sie das Dialogfeld **Schritt-Eigenschaften** .
1. Geben Sie die folgenden Details auf der Registerkarte **Prozess** des Dialogfelds ein und klicken Sie auf &quot;OK&quot;:
   - Wählen Sie **Dokumentstatus für ein DAM-Asset festlegen** aus der Dropdown-Liste &quot;Prozess&quot;.
   - Aktivieren Sie das Kontrollkästchen Handler-Modus .
   - Geben Sie den Namen des Dokumentstatus in das Textfeld **Argumente** ein.

     >[!NOTE]
     >
     > Vergewissern Sie sich, dass Sie den richtigen Dokumentstatus in das Textfeld Argument eingeben. Wenn Sie einen falschen Namen eingeben, wird für das Dokument der falsche Dokumentstatus festgelegt.

1. Klicken Sie auf **Speichern** , um den Workflow zu speichern.

## Genehmigungs-Workflow aktivieren

AEM Guides bietet einen Arbeitsablauf für die Dokumentgenehmigung, mit dem Sie den Lebenszyklus Ihres Dokumententwicklungsprozesses steuern können. Führen Sie die folgenden Schritte aus, um den Genehmigungs-Workflow zu aktivieren:

1. Melden Sie sich bei AEM an und öffnen Sie den CRXDE Lite-Modus.

1. Navigieren Sie zur Standardkonfigurationsdatei, die unter folgendem Speicherort verfügbar ist:

   `/libs/fmdita/clientlibs/clientlibs/xmleditor/ui_config.json`

1. Erstellen Sie eine Kopie der Standardkonfigurationsdatei an folgendem Speicherort:

   `/apps/fmdita/xmleditor/ui_config.json`

1. Navigieren Sie zur Datei &quot;`ui_config.json`&quot; und öffnen Sie sie im Knoten &quot;`apps`&quot;, um sie zu bearbeiten.

1. Aktivieren Sie in der Datei `ui_config.json` die Funktion des Genehmigungsarbeitsablaufs, indem Sie den Abschnitt *features* wie unten gezeigt ändern:

   ```json
   "features":  
   { 
      "approvalWorkflow":  true 
   }
   ```
