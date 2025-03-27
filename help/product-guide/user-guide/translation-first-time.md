---
title: Best Practices für die Übersetzung von Inhalten
description: Kenntnis der Best Practices für die Übersetzung von Inhalten in AEM Guides Erfahren Sie, wie Sie den Übersetzungs-Service konfigurieren, ein neues Übersetzungsprojekt erstellen und den Übersetzungsauftrag starten.
exl-id: f2a4df86-bba7-434c-b7f9-3587b8a4f9bc
feature: Translation
role: User
source-git-commit: ac83f613d87547fc7f6a18070545e40ad4963616
workflow-type: tm+mt
source-wordcount: '838'
ht-degree: 0%

---

# Best Practices für die Übersetzung von Inhalten {#id1678G0S702F}

Beachten Sie den folgenden Punkt für die Übersetzung von Inhalten:

- Ordner- und Dateinamen müssen den Dateibenennungsstandards entsprechen, z. B. - es sollten keine Leerzeichen, Apostrophe, geschweifte Klammern, Gleichheitszeichen, Sonderzeichen oder Nicht-ASCII-Zeichen vorhanden sein.

- Wenn Sie Inhalte in verschiedene Sprachen übersetzen, müssen Sie Ordner für jede Sprache erstellen. Jeder dieser Sprachordner enthält den Inhalt, der dieser Sprache entspricht. Sie können beispielsweise Ordner mit dem Sprach-Bezeichner erstellen, z. B. `de` für Deutsch, `fr` für Französisch usw. Alternativ können Sie Ordner mit den Sprach- und Regionskennzeichnungen erstellen, z. B. `fr-FR` für Französisch (wie in Frankreich verwendet) oder `fr-CA` für Französisch (wie in Kanada verwendet).
- Für die Zielsprache sollten auch die tatsächlichen Gebietsschemata gemäß den Zielsprachordnern in ihrer Instanz ausgewählt sein.
- Die Cloud-Konfiguration sollte mit der des Quellordners übereinstimmen und es sollte nur eine Cloud-Konfiguration in einem Ordner geben. Sie können unter /conf mehrere Ordner erstellen, wenn Sie mehrere Übersetzungs-Connectoren verwenden möchten.
- Ein Ordner darf nicht mehr als 1000 Dateien enthalten.
- Stellen Sie sicher, dass die Person, die mit dem Initiieren des Übersetzungsprozesses beauftragt ist, über Lese-, Änderungs-, Erstellungs- und Löschberechtigungen für die Ordner der Ausgangs- und Zielsprache verfügt.
- Da für die Übersetzung von Inhalten ein Übersetzungsprojekt erstellt werden muss, muss der Benutzer Zugriff darauf haben, ein Projekt in Adobe Experience Manager zu erstellen.
- Wenn Sie bedingte Vorgaben mit Ihrer Zuordnung verwenden möchten, müssen Sie sie vor dem Initiieren des Übersetzungsprozesses erstellen. Da bedingte Vorgaben auch in der übersetzten Version der Zuordnung gebündelt sind, müssen Sie beim Erstellen der Vorgaben vor dem Initiieren des Übersetzungsprozesses sicherstellen, dass sie in der übersetzten Version verfügbar sind.
- Die Übersetzung von Inhalten muss über die DITA-Zuordnungskonsole und nicht über die Adobe Experience Manager Assets-Benutzeroberfläche gestartet werden.
- Der komponentenbasierte DITA-Übersetzungs-Workflow darf nicht verwendet werden, wenn Sie Inhalte mit menschlicher Übersetzung übersetzen. Diese Option muss jedoch für maschinelle Übersetzung verwendet werden.
- Die global verwendeten Inhalte und Medien, die nicht lokalisiert werden müssen, sollten nicht in die Sprachkopien übernommen werden.
- Alle allgemeinen Inhalte, die lokalisiert werden müssen, sollten in einem gemeinsamen Ordner unter dem Sprachordner aufbewahrt werden.

Die folgende Abbildung zeigt ein Beispiel für eine Ordnerstruktur in Adobe Experience Manager, wenn Sie global Inhalte und drei Sprachkopien verwendet haben.

![](images/aem-directory_structure.png){align="left"}

## Konfigurieren des Übersetzungsdienstes

Führen Sie die folgenden Schritte aus, um den Service für menschliche oder maschinelle Übersetzung zu konfigurieren:

1. Wählen Sie in der Benutzeroberfläche von Assets den Ordner für die Ausgangssprache aus.

1. Öffnen Sie die Ordnereigenschaften und navigieren Sie zur Registerkarte **Cloud-Services** .

1. Konfigurieren **auf der Registerkarte** Cloud-Services“ den Übersetzungs-Service, den Sie verwenden möchten.

   Sie können maschinelle oder menschliche Übersetzung konfigurieren.

   Stellen Sie sicher, dass sich in einem Ordner nur eine Konfiguration für den Übersetzungs-Connector befindet. Unter /conf können mehrere Ordner erstellt werden, wenn mehrere Übersetzungs-Connectoren vorhanden sind. Für den Ordner der Ausgangssprache muss eine Cloud-Konfiguration ausgewählt sein, bevor der Übersetzungsprozess gestartet wird.

   >[!NOTE]
   >
   > Weitere [ zur Integration mit Übersetzungs-Services von Drittanbietern finden Sie ](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/administering/reusing-content/translation/integration-framework.html?lang=en) der Dokumentation zu Adobe Experience Manager unter „Konfigurieren des Frameworks für die Übersetzungsintegration“.

1. Wählen Sie **Speichern und schließen** um die aktualisierten Ordnereigenschaften zu speichern.


## Übersetzungsauftrag starten {#id225IK030OE8}

Führen Sie die folgenden Schritte aus, um den Übersetzungsauftrag zu starten:

1. Navigieren Sie in **Projekte**-Konsole zu dem Projektordner, den Sie für die Lokalisierung erstellt haben.

1. Wählen Sie das Lokalisierungsprojekt aus, um die Detailseite zu öffnen.

1. Klicken Sie auf der Kachel **Übersetzungsauftrag** auf den Pfeil und wählen Sie in der Liste **Starten** aus, um den Übersetzungs-Workflow zu starten.

   >[!NOTE]
   >
   > Wenn Sie den menschlichen Übersetzungs-Service verwenden, müssen Sie die Inhalte für die Übersetzung exportieren. Sobald Sie die übersetzten Inhalte haben, müssen Sie sie wieder in das Übersetzungsprojekt importieren.

1. Um den Status des Übersetzungsauftrags anzuzeigen, klicken Sie unten auf der Kachel **Übersetzungsauftrag** auf das Auslassungszeichen.


Nach Abschluss der Übersetzung ändert sich der Status des Übersetzungsauftrags in *Bereit für Überprüfung*. Um den Übersetzungsprozess abzuschließen, müssen Sie die übersetzte Kopie und die Asset-Metadaten aus der Kachel Übersetzungsauftrag in der Projektkonsole akzeptieren. Wenn Sie ein neues Übersetzungsprojekt starten möchten, rufen Sie [Übersetzungsprojekt erstellen](translate-documents-web-editor.md#create-a-translation-project) auf.

>[!NOTE]
>
>- Wenn Sie die Übersetzung für ein oder mehrere Themen in einem Übersetzungsauftrag ablehnen, wird der **In Bearbeitung** Übersetzungsstatus aller abgelehnten Themen auf ihren ursprünglichen Status zurückgesetzt. Der Status der referenzierten Themen wird entsprechend dem aktuellen Übersetzungsstatus überprüft und zurückgesetzt. Außerdem werden die im Zielsprachordner erstellten Übersetzungsdateien nicht gelöscht, selbst wenn die Übersetzung dafür abgelehnt wird.
>- Wenn Sie den Übersetzungsauftrag für ein Thema in mehreren Projekten (für eines der Projekte) ablehnen, löschen oder abbrechen, wird der **In Bearbeitung** Übersetzungsstatus des Themas nicht zurückgesetzt, dieses Projekt wird jedoch aus der Projektliste **In Bearbeitung** für dieses bestimmte Asset entfernt.
>- Wenn Sie außerdem den Übersetzungsauftrag abbrechen oder löschen oder das gesamte Projekt löschen, wird der **In Bearbeitung** Übersetzungsstatus auf den ursprünglichen Status zurückgesetzt.

**Übergeordnetes Thema:**[&#x200B;Übersicht über die Inhaltsübersetzung](translation.md)
