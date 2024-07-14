---
title: Best Practices für die Übersetzung von Inhalten
description: Machen Sie sich mit den Best Practices für die Übersetzung von Inhalten in AEM Guides vertraut. Erfahren Sie, wie Sie den Übersetzungsdienst konfigurieren, ein neues Übersetzungsprojekt erstellen und den Übersetzungsauftrag starten.
exl-id: f2a4df86-bba7-434c-b7f9-3587b8a4f9bc
feature: Translation
role: User
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '1295'
ht-degree: 2%

---

# Best Practices für die Übersetzung von Inhalten {#id1678G0S702F}

Beachten Sie beim Übersetzen von Inhalten den folgenden Punkt:

- Ordner- und Dateinamen müssen den Dateinamenstandards entsprechen, z. B.: Leerzeichen, Apostroph, Klammern, Gleichheitszeichen, Sonderzeichen oder Nicht-ASCII-Zeichen dürfen nicht verwendet werden.

- Wenn Sie Inhalte in verschiedene Sprachen übersetzen, müssen Sie für jede Sprache entsprechende Ordner erstellen. Jeder dieser Sprachordner enthält den Inhalt, der dieser Sprache entspricht. Sie können beispielsweise Ordner mit dem Sprachbezeichner wie `de` für Deutsch, `fr` für Französisch usw. erstellen. Alternativ können Sie Ordner mit den Sprachen- und Regionsbezeichnungen erstellen, z. B. &quot;`fr-FR`&quot;für Französisch, wie in Frankreich verwendet, &quot;`fr-CA`&quot;für Französisch, wie in Kanada verwendet.
- Für die Zielsprache sollten auch die tatsächlichen Gebietsschemata entsprechend den Zielsprachordnern in ihrer Instanz ausgewählt sein.
- Die Cloud-Konfiguration sollte mit der des Quellordners identisch sein und es sollte nur eine Cloud-Konfiguration in einem Ordner geben. Sie können unter /conf mehrere Ordner erstellen, wenn Sie mehrere Übersetzungs-Connectoren verwenden möchten.
- Ein Ordner sollte nicht mehr als 1000 Dateien enthalten.
- Stellen Sie sicher, dass der Benutzer, der mit dem Initiieren des Übersetzungsprozesses betraut ist, über Lese-, Änderungs-, Erstellen- und Löschberechtigungen für die Ordner mit den Quell- und Zielsprachen verfügt.
- Da die Übersetzung von Inhalten die Erstellung eines Übersetzungsprojekts erfordert, muss der Benutzer Zugriff auf die Erstellung eines Projekts in AEM haben.
- Wenn Sie bedingte Vorgaben mit Ihrer Zuordnung verwenden möchten, müssen Sie diese erstellen, bevor Sie den Übersetzungsprozess starten. Da bedingte Vorgaben auch in der übersetzten Version der Zuordnung gebündelt sind, stellen Sie beim Erstellen der Vorgaben vor dem Initiieren des Übersetzungsprozesses sicher, dass sie in der übersetzten Version verfügbar sind.
- Der Inhaltsübersetzungsprozess muss von der DITA-Zuordnungskonsole und nicht von der AEM Assets-Benutzeroberfläche aus gestartet werden.
- Der komponentenbasierte DITA-Übersetzungs-Workflow darf nicht verwendet werden, wenn Sie Inhalte über eine menschliche Übersetzung übersetzen. Diese Option muss jedoch für die maschinelle Übersetzung verwendet werden.
- Die global verwendeten Inhalte und Medien, die nicht lokalisiert werden müssen, sollten nicht in den Sprachkopien enthalten sein.
- Alle gemeinsamen Inhalte, die lokalisiert werden müssen, sollten in einem gemeinsamen Ordner unter dem Ordner Sprache gespeichert werden.

Die folgende Abbildung zeigt ein Beispiel für eine Ordnerstruktur in AEM, wenn Sie global verwendeten Inhalt und drei Sprachkopien haben.

![](images/aem-directory_structure.png){width="800" align="left"}

## Übersetzungsdienst konfigurieren

Führen Sie die folgenden Schritte aus, um den Dienst für menschliche oder maschinelle Übersetzung zu konfigurieren:

1. Wählen Sie in der Assets-Benutzeroberfläche den Ordner Quellsprache aus.

1. Öffnen Sie die Ordnereigenschaften und rufen Sie die Registerkarte **Cloud Service** auf.

1. Konfigurieren Sie auf der Registerkarte **Cloud Service** den zu verwendenden Übersetzungsdienst.

   Sie können maschinelle oder menschliche Übersetzung konfigurieren.

   Stellen Sie sicher, dass nur eine Konfiguration für den Übersetzungs-Connector in einem Ordner vorhanden ist. Unter /conf können mehrere Ordner erstellt werden, wenn mehrere Übersetzungs-Connectoren vorhanden sind. Für den Quellsprachordner muss eine Cloud-Konfiguration ausgewählt sein, bevor der Übersetzungsprozess gestartet wird.

   >[!NOTE]
   >
   > Weitere Informationen zur Integration mit Übersetzungsdiensten von Drittanbietern finden Sie unter [Konfigurieren des Übersetzungsintegrations-Frameworks](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/administering/reusing-content/translation/integration-framework.html?lang=en) in AEM Dokumentation.

1. Klicken Sie auf **Speichern und schließen** , um die aktualisierten Ordnereigenschaften zu speichern.


>[!TIP]
>
> Best Practices zur Übersetzung von Inhalten finden Sie im Abschnitt *Übersetzung* des Best Practices-Handbuchs.

## Erstellen eines neuen Übersetzungsprojekts

Führen Sie die folgenden Schritte aus, um ein Übersetzungsprojekt zu erstellen:

>[!NOTE]
>
> Bevor Sie die Schritte in diesem Verfahren durchführen, stellen Sie sicher, dass Sie den erforderlichen Sprachstamm und die Zielordner erstellt haben, wie in [Best Practices für die Übersetzung von Inhalten](#id1678G0S702F) beschrieben.

1. Klicken Sie in der Assets-Benutzeroberfläche auf die DITA-Zuordnungsdatei.

1. Klicken Sie auf die Registerkarte **Übersetzung** .

1. Wählen Sie in der Liste **Zielsprachen** das Gebietsschema aus, in das Sie Ihr Projekt übersetzen möchten, und klicken Sie auf **Fertig**.

   Eine Zusammenfassung und Details zu Themen und zugehörigen Assets werden angezeigt.

   >[!IMPORTANT]
   >
   > Die **Zielsprachen** zeigen nur die Sprachen an, für die parallel zur Ausgangssprache ein Sprachordner erstellt wird. Ein auf einer anderen Ebene erstellter Sprachordner, z. B. eine Ebene weiter ab dem Ordner für die Ausgangssprache, wird ebenfalls nicht angezeigt. Stellen Sie sicher, dass Sie alle Zielsprachordner auf derselben Ebene wie Ihren Ausgangssprachordner erstellen.

1. Wählen Sie die Themen aus, die Sie zur Übersetzung senden möchten.

   Sie können auch die folgenden Themenfilteroptionen verwenden:

   >[!NOTE]
   >
   > Klicken Sie nach dem Anwenden des erforderlichen Filters im Filterbereich auf **Fertig** , um die Themen nach Ihrer Auswahl zu filtern.

   - **Übersetzungsstatus**: Wählen Sie diese Option, um Themen nach ihrem Übersetzungsstatus zu filtern. Die verfügbaren Optionen sind: &quot;Nicht synchronisiert&quot;, &quot;Fehlende Kopie&quot;, &quot;In Bearbeitung&quot;und &quot;In Sync&quot;.
   - **Suche**: Geben Sie einen oder mehrere Begriffe ein, die in den Thementiteln durchsucht werden sollen.
   - **Source-Typ**: Wählen Sie diese Option, um Themen nach Dateitypen zu filtern. Die verfügbaren Optionen sind: Alle, DITA, DITA-Zuordnung, Ressource.
   - **Source-Version geändert nach**: Wählen Sie diese Option aus, um das Thema nach Datum und Uhrzeit der Änderung zu filtern. Alle Themen, die nach dem angegebenen Datum und der angegebenen Uhrzeit geändert wurden, werden in der Liste angezeigt.
   - **Grundlinie**: Klicken Sie auf Grundlinie verwenden und wählen Sie eine auf der Zuordnung erstellte Grundlinie aus. Alle Dateien, die Teil der ausgewählten Grundlinie sind, werden auf der Seite Übersetzung angezeigt. Sie können die gewünschten Dateien aus der Grundlinie auswählen und mit dem Übersetzungsprozess fortfahren. Sobald Ihr Inhalt übersetzt wurde, können Sie die übersetzte Grundlinie exportieren. Weitere Informationen zum Exportieren der übersetzten Grundlinie finden Sie unter [Exportieren der übersetzten Grundlinie](generate-output-use-baseline-for-publishing.md#id196SE600GHS).
1. Klicken Sie unten im Filterbereich auf **Sprachkopien erstellen/aktualisieren** .

1. Wählen Sie in der Liste **Projekt** die Option **Neues Übersetzungsprojekt erstellen** aus.

   >[!NOTE]
   >
   > Wenn Sie bereits über ein Übersetzungsprojekt verfügen, können Sie diesem Projekt Themen hinzufügen. Wählen Sie die Option **Zu vorhandenem Übersetzungsprojekt hinzufügen** aus der Liste **Projekt** und wählen Sie ein Projekt aus der Liste **Vorhandenes Übersetzungsprojekt** aus.

1. Geben Sie im Feld **Projekttitel** einen Namen für das Projekt ein.

1. Wählen Sie die Option **DITA-Map einschließen** aus, um die Zuordnung zur Übersetzung zu senden.
1. Klicken Sie auf **Starten** , um ein neues Übersetzungsprojekt zu erstellen.

   Ein neues Übersetzungsprojekt wird mit der ausgewählten Version der Themen erstellt. Zu diesem Zeitpunkt wird eine Popup-Meldung angezeigt, die bestätigt, dass das Übersetzungsprojekt erstellt wurde. Sobald alle Zielsprachkopien im Übersetzungsprojekt verfügbar sind, erhalten Sie eine Benachrichtigung im Posteingang. Sobald der Bereich der Zielsprachkopien im Übersetzungsprojekt verfügbar ist, können Sie den Übersetzungsauftrag starten.

   ![](images/status-translation-uuid.png){width="800" align="left"}


Die Registerkarte Übersetzung enthält die folgenden Abschnitte:

- **Zusammenfassung**: Zeigt die Anzahl der referenzierten Themen und der Quellsprache zusammen mit ihrem Code an.
- **Details**: Zeigt den Thementitel, den Thementyp, den Sprachcode des Themas, die Quellsprache, die Version des Quellthemas, die zum Thema hinzugefügte Bezeichnung und den Übersetzungsstatus an.




## Übersetzungsauftrag starten {#id225IK030OE8}

Führen Sie die folgenden Schritte aus, um den Übersetzungsauftrag zu starten:

1. Navigieren Sie in der Konsole **Projekte** zum Projektordner, den Sie für die Lokalisierung erstellt haben.

1. Klicken Sie auf das Lokalisierungsprojekt, um die Detailseite zu öffnen.

1. Klicken Sie auf den Pfeil auf der Kachel **Übersetzungsauftrag** und wählen Sie **Start** aus der Liste aus, um den Übersetzungs-Workflow zu starten.

   >[!NOTE]
   >
   > Wenn Sie den Übersetzungsdienst von Human verwenden, müssen Sie den Inhalt für die Übersetzung exportieren. Sobald Sie den übersetzten Inhalt haben, müssen Sie ihn wieder in das Übersetzungsprojekt importieren.

1. Um den Status des Übersetzungsauftrags anzuzeigen, klicken Sie unten auf der Kachel **Übersetzungsauftrag** auf das Auslassungszeichen.


Nach Abschluss der Übersetzung ändert sich der Status des Übersetzungsauftrags in *Bereit zur Überprüfung*. Um den Übersetzungsprozess abzuschließen, müssen Sie die übersetzte Kopie und die Asset-Metadaten aus der Kachel Übersetzungsauftrag in der Projektkonsole akzeptieren.

>[!NOTE]
>
> Wenn Sie die Übersetzung für ein oder mehrere Themen in einem Übersetzungsauftrag ablehnen, wird der Übersetzungsstatus **In Bearbeitung** aller abgelehnten Themen wieder auf den ursprünglichen Status zurückgesetzt. Der Status der referenzierten Themen wird überprüft und entsprechend dem aktuellen Übersetzungsstatus zurückgesetzt. Außerdem werden die im Zielprojekt erstellten Übersetzungsdateien nicht gelöscht, selbst wenn die Übersetzung für sie abgelehnt wurde.

**Übergeordnetes Thema:**[ Inhalt übersetzen](translation.md)
