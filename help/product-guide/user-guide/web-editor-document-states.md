---
title: Dokumentstatus
description: Erfahren Sie mehr über die Typen von Dokumentstatus in AEM Guides. Erfahren Sie, wie Sie den Dokumentstatus ändern oder anzeigen und den Dokumentstatus in DDLC verwenden.
exl-id: 3a68b2ed-b917-4f05-8b2b-d2722a740502
feature: Authoring, Features of Web Editor, Document State
role: User
source-git-commit: be06612d832785a91a3b2a89b84e0c2438ba30f2
workflow-type: tm+mt
source-wordcount: '936'
ht-degree: 0%

---

# Dokumentstatus {#id1821HC00URO}

Um die Dokumentbereitschaft zu verwalten, stellt AEM Guides die Eigenschaft document state bereit, um den aktuellen Status des Dokuments anzugeben. Mit den Dokumentstatus können Sie schnell ermitteln, ob ein Dokument neu ist, geprüft wird oder abgeschlossen ist.

## Typen von Dokumentstatus

Ein Dokument kann einen beliebigen Dokumentstatus enthalten, der im Profil &quot;Dokumentstatus&quot;definiert ist. Ein Dokument kann beispielsweise einen der folgenden Dokumentenstatus haben:

- Entwurf - Gibt an, dass das Dokument mit neuen Änderungen erstellt und gespeichert wird.
- In Überprüfung - Gibt an, dass ein Überprüfungs-Workflow für das Dokument initiiert wurde.
- Überprüft - Gibt an, dass das Dokument von den vorgesehenen Benutzern geprüft wurde.

Diese Status werden manuell oder automatisch entsprechend den Profileinstellungen für den Dokumentstatus festgelegt. Wenn beispielsweise das Profil &quot;Dokumentstatus&quot;mit dem Startstatus &quot;Entwurf&quot;konfiguriert ist und der Status &quot;In Überprüfung&quot;für Dokumente, die geprüft werden, definiert ist. Wenn Sie dann ein Dokument erstellen, wird der Dokumentstatus auf *Entwurf* festgelegt. Wenn Sie eine Prüfungsaufgabe starten, wird der Status des Dokuments in &quot;In Review&quot;geändert.

Sie können den Dokumentstatus für ein einzelnes oder mehrere Dokumente auch manuell ändern. Wenn Sie jedoch den Dokumentstatus für mehrere Dokumente ändern möchten, wird der zulässige Status durch die für die ausgewählten Dokumente zulässigen allgemeinen Status bestimmt. Angenommen, Sie haben die Dokumentstatus in derselben Reihenfolge als Entwurf, In-Review, Überprüfen und Bereit für Publish definiert. In Dokument 1.dita wird der Status auf *Entwurf* und in Dokument 2.dita auf &quot;Überprüfen&quot;gesetzt. Wenn Sie sowohl &quot;one.dita&quot;als auch &quot;two.dita&quot;auswählen, lautet der zulässige Dokumentstatus &quot;*Bereit für Publish*&quot;. Da sich two.dita im Status *Überprüfen* befindet, ist der nächste mögliche Status für two.dita nur *Bereit für Publish*, der angezeigt wird, wenn beide Dokumente ausgewählt sind.

>[!NOTE]
>
> Ein Dokument kann jeweils nur in einem Status vorhanden sein.

## Dokumentstatus ändern

Um den Status eines Dokuments zu ändern, führen Sie die folgenden Schritte aus:

1. Wählen Sie in der Assets-Benutzeroberfläche ein oder mehrere Dokumente aus, für die Sie den Dokumentstatus ändern möchten.
1. Klicken Sie in der Hauptsymbolleiste auf **Eigenschaften**.
1. Wählen Sie den neuen Status aus der Dropdownliste **Dokumentstatus** aus. Sie können nur die Dokumentstatus auswählen, die im Abschnitt Statusübergang des Dokumentstatusprofils zulässig sind.

   >[!NOTE]
   >
   >Administratoren können alle Dokumentstatus anzeigen und das Dokument in einen beliebigen Status ändern.

1. Klicken Sie auf **Speichern und schließen**.

## Dokumentstatus anzeigen

Die Kartenansicht der Assets-Benutzeroberfläche zeigt den aktuellen Status sowie das Erstellungsdatum und die Größe des entsprechenden DITA-Themas oder der DITA-Zuordnung an.

![](images/document_state.png){width="800" align="left"}

## Dokumentstatus in DDLC verwenden

Dokumentenstatus spielen eine wichtige Rolle bei der Verwaltung des Lebenszyklus von Dokumenten in DDLC. Wenn Ihr Unternehmen die DDLC-Regeln strikt befolgt, wird ein Mechanismus zur Kontrolle von Bearbeitungsdokumenten basierend auf ihrem Status zu einer wesentlichen Funktion. Sie können beispielsweise das Bearbeiten von Dokumenten zulassen, wenn sie sich im Status *Entwurf* oder *In Überprüfung* befinden. Sobald ein Dokument jedoch geprüft wurde und zur Veröffentlichung bereit ist, sollte es eine Möglichkeit geben, eine weitere Änderung von Dokumenten zu verhindern.

AEM Guides bietet einen Arbeitsablauf für die Dokumentgenehmigung, mit dem Sie den Lebenszyklus Ihres Dokumententwicklungsprozesses steuern können. Sobald ein Dokument zur Veröffentlichung bereit ist oder den vorletzten Status erreicht hat, können Sie es als genehmigt markieren. Nachdem ein Dokument genehmigt wurde, erstellt AEM Guides eine neue Version des Dokuments und macht es schreibgeschützt. Anschließend können Sie das Dokument zur Veröffentlichung verschieben oder eine Grundlinie für die weitere Verarbeitung erstellen.

Um eine neue Version der Dokumente zu starten, die als genehmigt gekennzeichnet sind, muss ein Autor eine neue Version starten. Beim Starten einer neuen Version ändert sich der Dokumentstatus erneut in *Entwurf*. Wenn Sie den Dokumentstatus in &quot;*Entwurf*&quot; ändern, wird das Dokument erneut bearbeitbar gemacht und Sie können mit der nächsten Version weiterarbeiten.

Führen Sie die folgenden Schritte aus, um die Dokumentvalidierungsfunktion zu verwenden:

>[!NOTE]
>
> Die Validierungs-Workflow-Funktion muss von Ihrem Administrator aktiviert werden. Weitere Informationen finden Sie im Abschnitt *Genehmigungs-Workflow aktivieren* im Abschnitt Installieren und Konfigurieren von Adobe Experience Manager Guides as a Cloud Service.

1. Öffnen Sie im Web Editor das Dokument, das Sie zur Genehmigung markieren möchten.

1. Klicken Sie auf das Symbol **Genehmigt markieren**![](images/mark_approve_icon.svg) .

1. Wenn Ihr Dokument sich im Status befindet, der als genehmigt markiert werden soll, wird das folgende Dialogfeld angezeigt:

   ![](images/mark-approved-correct-state.png){width="300" align="left"}

   Wenn Ihr Dokument nicht als genehmigt markiert werden kann, wird die folgende Meldung angezeigt:

   ![](images/mark-approved-incorrect-state.png){width="300" align="left"}

1. Wenn Ihr Dokument bereit ist, als genehmigt markiert zu werden, wählen Sie eine Beschriftung aus der Dropdownliste aus und klicken Sie auf **Genehmigen**.

   >[!NOTE]
   >
   > Wenn Ihr Administrator keine vordefinierte Liste von Bezeichnungen konfiguriert hat, wird Ihnen ein Freiformtextfeld zur Eingabe eines Titels angezeigt.

1. Nachdem das Dokument erfolgreich als genehmigt markiert wurde, wird eine **Vorschau** des Dokuments im schreibgeschützten Modus angezeigt.

   ![](images/approved-doc-read-only.png){width="650" align="left"}

   >[!NOTE]
   >
   > Im Vorschaumodus werden alle Bearbeitungsoptionen aus der Symbolleiste entfernt. Darüber hinaus wurde die Ansicht &quot;Author&quot;und &quot;Source&quot;des Dokuments auch aus der oberen Navigation entfernt.


Nachdem ein Dokument als genehmigt markiert wurde, steht es nicht mehr zur Bearbeitung zur Verfügung. Wenn Sie das Dokument für die nächste Version verwenden möchten, müssen Sie es wieder in den Status *Entwurf* bringen. So ändern Sie den Dokumentstatus eines genehmigten Dokuments wieder in den Modus *Entwurf* :

1. Klicken Sie in einem genehmigten Dokument auf das Symbol **Neue Version starten** ![](images/approved-restart-draft-mode-icon.svg) .

   Die Meldung Neue Version starten wird angezeigt.

1. Klicken Sie auf **Bestätigen**.

   Der Status des Dokuments wird in Entwurf geändert und das Dokument wird im Web-Editor im Bearbeitungsmodus geöffnet.


**Übergeordnetes Thema:**[ Arbeiten mit dem Web-Editor](web-editor.md)
