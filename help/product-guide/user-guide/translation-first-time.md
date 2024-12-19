---
title: Best Practices für die Übersetzung von Inhalten
description: Kenntnis der Best Practices für die Übersetzung von Inhalten in AEM Guides Erfahren Sie, wie Sie den Übersetzungs-Service konfigurieren, ein neues Übersetzungsprojekt erstellen und den Übersetzungsauftrag starten.
exl-id: f2a4df86-bba7-434c-b7f9-3587b8a4f9bc
feature: Translation
role: User
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '1295'
ht-degree: 2%

---

# Best Practices für die Übersetzung von Inhalten {#id1678G0S702F}

Beachten Sie den folgenden Punkt für die Übersetzung von Inhalten:

- Ordner- und Dateinamen müssen den Dateibenennungsstandards entsprechen, z. B. - es sollten keine Leerzeichen, Apostrophe, geschweifte Klammern, Gleichheitszeichen, Sonderzeichen oder Nicht-ASCII-Zeichen vorhanden sein.

- Wenn Sie Inhalte in verschiedene Sprachen übersetzen, müssen Sie Ordner für jede Sprache erstellen. Jeder dieser Sprachordner enthält den Inhalt, der dieser Sprache entspricht. Sie können beispielsweise Ordner mit dem Sprach-Bezeichner erstellen, z. B. `de` für Deutsch, `fr` für Französisch usw. Alternativ können Sie Ordner mit den Sprach- und Regionskennzeichnungen erstellen, z. B. `fr-FR` für Französisch (wie in Frankreich verwendet) oder `fr-CA` für Französisch (wie in Kanada verwendet).
- Für die Zielsprache sollten auch die tatsächlichen Gebietsschemata gemäß den Zielsprachordnern in ihrer Instanz ausgewählt sein.
- Die Cloud-Konfiguration sollte mit der des Quellordners übereinstimmen und es sollte nur eine Cloud-Konfiguration in einem Ordner geben. Sie können unter /conf mehrere Ordner erstellen, wenn Sie mehrere Übersetzungs-Connectoren verwenden möchten.
- Ein Ordner darf nicht mehr als 1000 Dateien enthalten.
- Stellen Sie sicher, dass die Person, die mit dem Initiieren des Übersetzungsprozesses beauftragt ist, über Lese-, Änderungs-, Erstellungs- und Löschberechtigungen für die Ordner der Ausgangs- und Zielsprache verfügt.
- Da für die Übersetzung von Inhalten ein Übersetzungsprojekt erstellt werden muss, muss der Benutzer Zugriff darauf haben, ein Projekt in AEM zu erstellen.
- Wenn Sie bedingte Vorgaben mit Ihrer Zuordnung verwenden möchten, müssen Sie sie vor dem Initiieren des Übersetzungsprozesses erstellen. Da bedingte Vorgaben auch in der übersetzten Version der Zuordnung gebündelt sind, müssen Sie beim Erstellen der Vorgaben vor dem Initiieren des Übersetzungsprozesses sicherstellen, dass sie in der übersetzten Version verfügbar sind.
- Die Übersetzung von Inhalten muss über die DITA-Zuordnungskonsole und nicht über die AEM Assets-Benutzeroberfläche gestartet werden.
- Der komponentenbasierte DITA-Übersetzungs-Workflow darf nicht verwendet werden, wenn Sie Inhalte mit menschlicher Übersetzung übersetzen. Diese Option muss jedoch für maschinelle Übersetzung verwendet werden.
- Die global verwendeten Inhalte und Medien, die nicht lokalisiert werden müssen, sollten nicht in die Sprachkopien übernommen werden.
- Alle allgemeinen Inhalte, die lokalisiert werden müssen, sollten in einem gemeinsamen Ordner unter dem Sprachordner aufbewahrt werden.

Die folgende Abbildung zeigt ein Beispiel für eine Ordnerstruktur in AEM, wenn Sie global Inhalte und drei Sprachkopien verwendet haben.

![](images/aem-directory_structure.png){width="800" align="left"}

## Konfigurieren des Übersetzungsdienstes

Führen Sie die folgenden Schritte aus, um den Service für menschliche oder maschinelle Übersetzung zu konfigurieren:

1. Wählen Sie in der Benutzeroberfläche von Assets den Ordner für die Ausgangssprache aus.

1. Öffnen Sie die Ordnereigenschaften und wechseln Sie zur Registerkarte **Cloud Service** .

1. Konfigurieren Sie auf der Registerkarte **0}Cloud Service&quot; den Übersetzungs-Service, den Sie verwenden möchten.**

   Sie können maschinelle oder menschliche Übersetzung konfigurieren.

   Stellen Sie sicher, dass sich in einem Ordner nur eine Konfiguration für den Übersetzungs-Connector befindet. Unter /conf können mehrere Ordner erstellt werden, wenn mehrere Übersetzungs-Connectoren vorhanden sind. Für den Ordner der Ausgangssprache muss eine Cloud-Konfiguration ausgewählt sein, bevor der Übersetzungsprozess gestartet wird.

   >[!NOTE]
   >
   > Siehe [Konfigurieren des Translation Integration Framework](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/administering/reusing-content/translation/integration-framework.html?lang=en) in der AEM-Dokumentation für Details zur Integration mit Übersetzungsdiensten von Drittanbietern.

1. Klicken Sie auf **Speichern und schließen** um die aktualisierten Ordnereigenschaften zu speichern.


>[!TIP]
>
> Im Abschnitt *Übersetzung* des Best Practices-Handbuchs finden Sie die Best Practices für die Übersetzung von Inhalten.

## Erstellen eines neuen Übersetzungsprojekts

Führen Sie die folgenden Schritte aus, um ein Übersetzungsprojekt zu erstellen:

>[!NOTE]
>
> Bevor Sie die Schritte in diesem Verfahren ausführen, stellen Sie sicher, dass Sie die erforderlichen Sprachstamm- und Zielordner erstellt haben, wie in [Best Practices für die Inhaltsübersetzung](#id1678G0S702F) beschrieben.

1. Klicken Sie in der Assets-Benutzeroberfläche auf die DITA-Zuordnungsdatei.

1. Klicken Sie auf die **Übersetzung**.

1. Wählen Sie in der **Target Languages** das Gebietsschema aus, in das Sie Ihr Projekt übersetzen möchten, und klicken Sie auf **Done**.

   Eine Zusammenfassung und Details zu Themen und zugehörigen Assets werden angezeigt.

   >[!IMPORTANT]
   >
   > Die **Zielsprachen** zeigen nur die Sprachen an, für die parallel zur Quellsprache ein Sprachordner erstellt wird. Ein auf einer anderen Ebene erstellter Sprachordner, z. B. eine Ebene unterhalb des Ordners der Ausgangssprache, wird ebenfalls nicht angezeigt. Stellen Sie sicher, dass Sie alle Zielsprachordner auf derselben Ebene wie den Ordner für die Ausgangssprache erstellen.

1. Wählen Sie die Themen aus, die Sie zur Übersetzung senden möchten.

   Sie können auch die folgenden Themenfilteroptionen verwenden:

   >[!NOTE]
   >
   > Nachdem Sie den erforderlichen Filter angewendet haben, klicken Sie im Bedienfeld **Filter** auf „Fertig“, um Themen basierend auf Ihrer Auswahl zu filtern.

   - **Übersetzungsstatus**: Themen nach ihrem Übersetzungsstatus filtern. Die verfügbaren Optionen sind: Nicht synchronisiert, Fehlende Kopie, In Bearbeitung und Synchronisiert.
   - **Suche**: Geben Sie einen oder mehrere Begriffe ein, um nach den Thementiteln zu suchen.
   - **Source-Typ**: Wählen Sie diese Option, um Themen nach ihren Dateitypen zu filtern. Die verfügbaren Optionen sind: Alle, DITA, DITA Map, Ressource.
   - **Source-Version geändert nach**: Wählen Sie diese Option, um das Thema nach Änderungsdatum und -uhrzeit zu filtern. Alle Themen, die nach dem angegebenen Datum und der angegebenen Uhrzeit geändert wurden, werden in der Liste angezeigt.
   - **Baseline**: Klicken Sie auf „Baseline verwenden“ und wählen Sie eine auf der Karte erstellte Baseline aus. Alle Dateien, die Teil der ausgewählten Baseline sind, werden auf der Seite Übersetzung angezeigt. Sie können die gewünschten Dateien aus der Grundlinie auswählen und mit dem Übersetzungsprozess fortfahren. Nach der Übersetzung Ihrer Inhalte können Sie die übersetzten Baselines exportieren. Weitere Informationen zum Exportieren der übersetzten Baseline finden Sie unter [Exportieren der übersetzten Baseline](generate-output-use-baseline-for-publishing.md#id196SE600GHS).
1. Klicken **unten** Filterbedienfeld auf „Sprachkopien erstellen/aktualisieren“.

1. Wählen Sie in **Liste** Projekt **die Option „Neues Übersetzungsprojekt erstellen** aus.

   >[!NOTE]
   >
   > Wenn Sie bereits über ein Übersetzungsprojekt verfügen, können Sie diesem Projekt Themen hinzufügen. Wählen Sie **Option „Zu vorhandenem Übersetzungsprojekt hinzufügen** aus der Liste **Projekt** und wählen Sie ein Projekt aus der Liste **Vorhandenes Übersetzungsprojekt** aus.

1. Geben Sie im Feld **Projekttitel** einen Namen für das Projekt ein.

1. Wählen Sie die Option **DITA-Map einschließen**, um die Map zur Übersetzung zu senden.
1. Klicken Sie **Starten**, um ein neues Übersetzungsprojekt zu erstellen.

   Ein neues Übersetzungsprojekt wird mit der ausgewählten Version der Themen erstellt. Zu diesem Zeitpunkt wird eine Popup-Meldung angezeigt, die bestätigt, dass das Übersetzungsprojekt erstellt wurde. Sobald alle Kopien der Zielsprache im Übersetzungsprojekt verfügbar sind, erhalten Sie eine Benachrichtigung im Posteingang. Sobald der Bereich für die Zielsprachenkopien im Übersetzungsprojekt verfügbar ist, können Sie mit dem Übersetzungsauftrag beginnen.

   ![](images/status-translation-uuid.png){width="800" align="left"}


Die Registerkarte Übersetzung enthält die folgenden Abschnitte:

- **Zusammenfassung**: Zeigt die Anzahl der referenzierten Themen und die Ausgangssprache zusammen mit dem Code an.
- **Details**: Zeigt den Thementitel, den Thementyp, den Sprach-Code des Themas, die Quellsprache, die Version des Quellthemas, die dem Thema hinzugefügte Beschriftung und den Übersetzungsstatus an.




## Übersetzungsauftrag starten {#id225IK030OE8}

Führen Sie die folgenden Schritte aus, um den Übersetzungsauftrag zu starten:

1. Navigieren Sie in **Projekte**-Konsole zu dem Projektordner, den Sie für die Lokalisierung erstellt haben.

1. Klicken Sie auf das Lokalisierungsprojekt, um die Detailseite zu öffnen.

1. Klicken Sie auf der Kachel **Übersetzungsauftrag** auf den Pfeil und wählen Sie **Starten** aus der Liste aus, um den Übersetzungs-Workflow zu starten.

   >[!NOTE]
   >
   > Wenn Sie den menschlichen Übersetzungs-Service verwenden, müssen Sie die Inhalte für die Übersetzung exportieren. Sobald Sie die übersetzten Inhalte haben, müssen Sie sie wieder in das Übersetzungsprojekt importieren.

1. Um den Status des Übersetzungsauftrags anzuzeigen, klicken Sie unten auf der Kachel **Übersetzungsauftrag** auf das Auslassungszeichen.


Nach Abschluss der Übersetzung ändert sich der Status des Übersetzungsauftrags in *Bereit für Überprüfung*. Um den Übersetzungsprozess abzuschließen, müssen Sie die übersetzte Kopie und die Asset-Metadaten aus der Kachel Übersetzungsauftrag in der Projektkonsole akzeptieren.

>[!NOTE]
>
> Wenn Sie die Übersetzung für ein oder mehrere Themen in einem Übersetzungsauftrag ablehnen, wird der **In Bearbeitung** Übersetzungsstatus aller abgelehnten Themen auf ihren ursprünglichen Status zurückgesetzt. Der Status der referenzierten Themen wird entsprechend dem aktuellen Übersetzungsstatus überprüft und zurückgesetzt. Außerdem werden die im Zielprojekt erstellten Übersetzungsdateien nicht gelöscht, selbst wenn die Übersetzung dafür abgelehnt wird.

**Übergeordnetes Thema:**[ Inhalte übersetzen](translation.md)
