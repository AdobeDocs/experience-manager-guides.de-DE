---
title: Konfigurieren und Anpassen von Workflows
description: Erfahren Sie, wie Sie Workflows konfigurieren und anpassen
exl-id: 3be387b9-6ac2-4b61-afdf-fbe9d8b6cc1e
feature: Workflow Configuration
role: Admin
level: Experienced
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '1744'
ht-degree: 3%

---

# Konfigurieren und Anpassen von Workflows {#id181AI0OJ0RO}

Workflows ermöglichen die Automatisierung von Aktivitäten des Typs Adobe Experience Manager \(AEM\). Ein Workflow besteht aus einer Reihe von Schritten, die in einer bestimmten Reihenfolge ausgeführt werden. Sie können für jeden Schritt eine eigene Aktivität definieren. Sie können beispielsweise eine E-Mail-Benachrichtigung an alle Reviewer in einer Gruppe senden, wenn eine Themenüberprüfung erstellt wird. Sie können auch eine Benachrichtigung an den Herausgeber senden, wenn eine Aufgabe zur Ausgabegenerierung abgeschlossen ist.

Weitere Informationen zu Workflows in AEM finden Sie unter:

- [Verwalten von Workflows](https://helpx.adobe.com/de/experience-manager/6-5/sites/administering/using/workflows.html)

- Anwenden von und Teilnehmen an Workflows: [Arbeiten mit Workflows](https://helpx.adobe.com/de/experience-manager/6-5/sites/authoring/using/workflows.html).

- Das Erstellen von Workflow-Modellen und die Erweiterung der Workflow-Funktionalität: [Entwickeln und Erweitern von Workflows](https://helpx.adobe.com/de/experience-manager/6-5/sites/developing/using/workflows.html).

- Verbesserung der Leistung von Workflows, die bedeutende Server-Ressourcen nutzen: [Gleichzeitige Verarbeitung von Workflows](https://helpx.adobe.com/de/experience-manager/6-5/sites/deploying/using/configuring-performance.html#ConfiguringforPerformance).


Die Abschnitte in diesem Thema führen Sie durch verschiedene Anpassungen, die Sie in den in AEM Guides bereitgestellten Standard-Workflows vornehmen können.

## Anpassen des Workflow für Überprüfungen {#id176NE0C00HS}

Das Inhaltserstellungs-Team jedes Unternehmens arbeitet auf eine bestimmte Weise, um seine Geschäftsanforderungen zu erfüllen. In einigen Organisationen gibt es einen dedizierten Editor, während andere Organisationen ein automatisiertes redaktionelles Überprüfungssystem haben könnten. In einer Organisation kann ein typischer Authoring- und Publishing-Workflow beispielsweise Aufgaben wie enthalten: Wenn ein Autor mit der Inhaltserstellung fertig ist, geht er automatisch an die Validierungsverantwortlichen. Nach Abschluss der Überprüfung wird er an den Publisher weitergeleitet, um die endgültige Ausgabe zu generieren. In AEM können Aktivitäten, die Sie für Ihre Inhalte und Assets ausführen, in Form eines Prozesses kombiniert und einem AEM-Workflow zugeordnet werden. Weitere Informationen zu Workflows in AEM finden Sie unter [Verwalten von Workflows](https://helpx.adobe.com/de/experience-manager/6-5/sites/administering/using/workflows.html) in der AEM-Dokumentation.

Mit AEM Guides können Sie den standardmäßigen Überprüfungs-Workflow anpassen. Sie können die folgenden vier benutzerdefinierten Überprüfungsprozesse mit Ihren anderen Authoring- oder Publishing-Workflows verwenden.

- **Überprüfung erstellen**: Dieser Prozess bereitet die Metadaten vor, die zum Erstellen einer Prüfungsaufgabe erforderlich sind. Beispielsweise werden den Reviewern Überprüfungsberechtigungen zugewiesen, der Status der zu überprüfenden Themen wird auf überprüft, die Zeitpläne für Überprüfungen werden festgelegt und vieles mehr. Von den vier Prozessen ist dies der einzige obligatorische Prozess, der in Ihren benutzerdefinierten Workflow aufgenommen werden muss. In Ihrem Workflow können Sie die anderen drei Prozesse ein- oder ausschließen.

- **Prüfungsaufgabe zuweisen**: Dieser Prozess erstellt die Prüfungsaufgabe und sendet die Aufgabenbenachrichtigung an den Initiator und die Validierungsverantwortlichen.

- **Überprüfungs-E-Mail senden**: Dieser Prozess sendet die Überprüfungs-E-Mail an den Initiator und die Validierungsverantwortlichen.

- **Auftrag zum Schließen der Überprüfung planen**: Dieser Prozess stellt sicher, dass der Überprüfungsprozess beim Erreichen der Frist abgeschlossen wird.


Beim Erstellen eines benutzerdefinierten Überprüfungs-Workflows besteht die erste Aufgabe darin, die erforderlichen Metadaten festzulegen, die für den Prozess „Überprüfung erstellen“ benötigt werden. Dazu können Sie ein ECMA-Skript erstellen. Ein Beispiel für das ECMA-Skript, das die Metadaten zuweist, finden Sie unten:

```json
var workflowdata=workItem.getWorkflowData();
workflowdata.getMetaDataMap().put("initiator","admin");
workflowdata.getMetaDataMap().put("operation","AEM_REVIEW");
workflowdata.getMetaDataMap().put("orgTopics","/content/dam/xml-solution/review.xml");
workflowdata.getMetaDataMap().put("payloadJson","{\"base\":\"/content/dam/xml-solution\",\"asset\":[\"/content/dam/xml-solution/review.xml\"],\"referrer\":\""}");
workflowdata.getMetaDataMap().put("deadline","2017-06-27T13:19:00.000+05:30");
workflowdata.getMetaDataMap().put("title","Review through custom workflow");
workflowdata.getMetaDataMap().put("description","Initiate this review process using the AEM workflow");
workflowdata.getMetaDataMap().put("assignee","user-one", "user-two");
workflowdata.getMetaDataMap().put("status","1");
workflowdata.getMetaDataMap().put("projectPath","/content/projects/review");
workflowdata.getMetaDataMap().put("startTime", System.currentTimeMillis());
```

Sie können dieses Skript im Knoten `/etc/workflows/scripts` erstellen. In der folgenden Tabelle werden die Eigenschaften beschrieben, die von diesem ECMA-Skript zugewiesen werden:

| Eigenschaft | Typ | Beschreibung |
|--------|----|-----------|
| `initiator` | Zeichenfolge | Benutzer-ID des Benutzers, der die Prüfungsaufgabe initiiert. |
| `operation` | Zeichenfolge | Ein statischer Wert, der als `AEM_REVIEW` festgelegt ist. |
| `orgTopics` | Zeichenfolge | Pfad der Themen, die zur Überprüfung freigegeben werden. Geben Sie mehrere Themen durch Kommata getrennt an. |
| `payloadJson` | JSON-Objekt | Geben Sie die folgenden Werte an:<br> - `base`: Pfad des übergeordneten Ordners, der das zur Überprüfung gesendete Thema enthält.<br>- `asset`: Pfad des zur Überprüfung gesendeten Themas. <br>- `referrer`: Lassen Sie es leer. |
| `deadline` | Zeichenfolge | Geben Sie die Zeit im `yyyy-MM-dd'T'HH:mm:ss.SSSXXX` an. |
| `title` | Zeichenfolge | Geben Sie einen Titel für die Prüfungsaufgabe ein. |
| `description` | Zeichenfolge | Geben Sie eine Beschreibung für die Prüfungsaufgabe ein. |
| `assignee` | Zeichenfolge | Benutzer-ID der Benutzer, an die Sie die Themen zur Überprüfung senden möchten. |
| `status` | Ganzzahl | Ein statischer Wert, der auf 1 gesetzt ist. |
| `startTime` | Long | Verwenden Sie die `System.currentTimeMillis()`, um die aktuelle Systemzeit abzurufen. |

Nachdem Sie das Skript erstellt haben, rufen Sie es auf, bevor Sie den Prozess zum Erstellen einer Überprüfung in Ihrem Workflow aufrufen. Anschließend können Sie je nach Ihren Anforderungen die anderen Überprüfungs-Workflow-Prozesse aufrufen.

### Entfernen des Überprüfungs-Workflows aus der Bereinigungskonfiguration

Um die Leistung der Workflow-Engine zu verbessern, können Sie regelmäßig abgeschlossene Workflow-Instanzen aus dem AEM-Repository löschen. Wenn Sie die standardmäßigen AEM-Konfigurationen verwenden, werden alle abgeschlossenen Workflow-Instanzen nach einem bestimmten Zeitraum bereinigt. Dies führt auch dazu, dass alle Überprüfungs-Workflows aus dem AEM-Repository gelöscht werden.

Sie können verhindern, dass Überprüfungs-Workflows automatisch bereinigen, indem Sie das Modell des Überprüfungs-Workflows \(information\) aus der Konfiguration der automatischen Bereinigung entfernen. Sie müssen die **Adobe Granite Workflow-Bereinigungskonfiguration** verwenden, um die Workflow-Modelle für die Überprüfung aus der Liste für die automatische Bereinigung zu entfernen.

Stellen Sie in der **Adobe Granite Workflow-** sicher, dass Sie mindestens einen Workflow auflisten, den Sie sicher bereinigen können. Sie können beispielsweise einen der folgenden von AEM Guides erstellten Workflows verwenden:

- /etc/workflow/models/publishditamap/jcr:content/model
- /etc/workflow/models/post-dita-project-creation-tasks/ jcr:content/model

Durch Hinzufügen eines Workflows in der **Adobe Granite Workflow-Bereinigungskonfiguration** sichergestellt, dass AEM nur die Workflows bereinigt, die in der Konfiguration aufgeführt sind. Dadurch wird verhindert, dass AEM die Informationen des Überprüfungs-Workflows bereinigt.

Weitere Informationen zum Konfigurieren der **Adobe Granite Workflow-Bereinigungskonfiguration** finden Sie unter *Verwalten von Workflow-Instanzen* in der AEM-Dokumentation.

### E-Mail-Vorlagen anpassen

In einer Reihe von AEM Guides-Workflows werden E-Mail-Benachrichtigungen verwendet. Wenn Sie beispielsweise eine Prüfungsaufgabe initiieren, wird eine E-Mail-Benachrichtigung an die Validierungsverantwortlichen gesendet. Um jedoch sicherzustellen, dass die E-Mail-Benachrichtigung gesendet wird, müssen Sie diese Funktion in AEM aktivieren. Informationen zum Aktivieren der E-Mail-Benachrichtigung in AEM finden Sie im Artikel [Konfigurieren von E-Mail](https://experienceleague.adobe.com/docs/experience-manager-release-information/aem-release-updates/previous-updates/aem-previous-versions.html?lang=de) in der AEM-Dokumentation.

AEM Guides enthält eine Reihe von E-Mail-Vorlagen, die Sie anpassen können. Führen Sie die folgenden Schritte aus, um diese Vorlagen anzupassen:

1. Melden Sie sich bei AEM an und öffnen Sie den CRXDE Lite-Modus.

1. Navigieren Sie auf der Registerkarte Navigator zum folgenden Speicherort:

   `/libs/fmdita/mail`

   >[!NOTE]
   >
   > Nehmen Sie keine Anpassungen in den Standardkonfigurationsdateien im Knoten ``libs`` vor. Sie müssen eine Überlagerung des Knotens ``libs`` im Knoten ``apps`` erstellen und die erforderlichen Dateien nur im Knoten ``apps`` aktualisieren.

1. Der E-Mail-Ordner enthält die folgenden anpassbaren Vorlagen:

   | Name der Vorlagendatei | Beschreibung |
   |-----------------|-----------|
   | closereview.html | Diese E-Mail-Vorlage wird verwendet, wenn eine Prüfungsaufgabe geschlossen wird. |
   | createreview.html | Diese E-Mail-Vorlage wird verwendet, wenn eine neue Prüfungsaufgabe erstellt wird. |
   | reviewapproval.css | Diese CSS-Datei enthält den Stil der E-Mail-Vorlagen. |


## Anpassen des Workflows nach der Ausgabe {#id17A6GI004Y4}

AEM Guides bietet Ihnen die Flexibilität, einen Workflow nach der Ausgabe anzugeben. Sie können einige Nachbearbeitungsaufgaben für die Ausgabe ausführen, die mit AEM Guides generiert wird. Beispielsweise können Sie einige CQ-Tags auf die generierte AEM-Site-Ausgabe anwenden oder bestimmte Eigenschaften auf die PDF-Ausgabe festlegen oder eine E-Mail an eine Benutzergruppe senden, sobald die Ausgabe generiert wurde.

Sie können ein neues Workflow-Modell erstellen, das als Workflow nach der Generierung von Ausgaben verwendet werden kann. Wenn ein Workflow zur Erzeugung nach der Ausgabe ausgelöst wird, gibt der Workflow zur Erzeugung von Ausgaben kontextuelle Informationen über die Workflow-Metadatenzuordnung frei, mit denen Sie die Verarbeitung der generierten Ausgabe durchführen können. In der folgenden Tabelle werden die als Metadaten freigegebenen Kontextinformationen beschrieben:

| Eigenschaft | Typ | Beschreibung |
|--------|----|-----------|
| ``outputName`` | Zeichenfolge | Name der Ausgabevorgabe, die zum Generieren der Ausgabe verwendet wird. |
| `generatedPath` | Zeichenfolge | Pfad im DAM, in dem die generierte Ausgabe gespeichert wird. |
| `outputType` | com.adobe.fmdita.output.OutputType | Typ der Ausgabevorgabe. |
| `outputTitle` | Zeichenfolge | Titel der Ausgabevorgabe. |
| `outputHistoryPath` | Zeichenfolge | Repository-Pfad des Verlaufsknotens. |
| `isSuccess` | Boolesch | Eine Markierung, die den endgültigen Status des Ausgabegenerierungsprozesses darstellt - Erfolg oder Fehler. |
| `logPath` | Zeichenfolge | Pfad in DAM, unter dem die Ausgabegenerierungsprotokolle gespeichert werden. |
| `generatedTime` | Long | Zeitpunkt, zu dem der Ausgabenerstellungsprozess ausgelöst wurde. |
| `initiator` | Zeichenfolge | Die Benutzer-ID des Benutzers, der den Workflow zur Ausgabegenerierung ausgelöst hat. |

Um die Metadaten der Ausgabegenerierung zu verwenden, können Sie ein ECMA-Skript oder ein OSGi-Bundle erstellen. Ein Beispiel für das ECMA-Skript, das die Metadaten verwendet, finden Sie unten:

>[!NOTE]
>
> Sie können dieses Skript im Knoten ``/etc/workflows/scripts`` erstellen.

```json
var session = workflowSession.getSession(); // Obtain session object to read/write the repository.
var payload = workItem.getWorkflowData().getPayload().toString(); // Get the workflow payload (the ditamap file on which the generation was triggered)
var metadata = workItem.getWorkflowData().getMetaDataMap(); // Get the workflow metadata object
var generatedPath = metadata.get("generatedPath"); // supplied by AEM Guides
var username = metadata.get("initiator"); // supplied by AEM Guides
var successful = metadata.get("isSuccess"); // supplied by AEM Guides
var title = metadata.get("outputTitle"); // supplied by AEM Guides
var subject = "Output Generation Finished";
var message = "Generation of output " + title + " just finished " + 
(successful ? "successfully. " : "unsuccessfully. ");
    message += "It was triggered by " + username;    
if (successful) {
    message += "<br/><br/>The path to the generated output is " + 
generatedPath;
}
/*
    MailerAPI.sendMail("dl-docs-authors", subject, message);
*/
```

Rufen Sie nach Erstellung des Skripts das benutzerdefinierte Skript in Ihrem Workflow auf. Anschließend können Sie je nach Ihren Anforderungen die anderen Workflow-Prozesse aufrufen. Nachdem Sie Ihren benutzerdefinierten Workflow entworfen haben, rufen Sie die *Nachgenerierung abschließen* als letzten Schritt in Ihrem Workflow-Prozess auf. Der Schritt *Nachgenerierung abschließen* stellt sicher, dass der Status der Ausgabegenerierungsaufgabe nach Abschluss des Ausgabegenerierungsprozesses auf *Abgeschlossen* aktualisiert wird. Nachdem Sie einen benutzerdefinierten Workflow für die Generierung nach der Ausgabe erstellt haben, können Sie ihn mit jeder Ihrer Vorgaben für die Ausgabegenerierung konfigurieren. Wählen Sie den gewünschten Workflow in der Eigenschaft *Workflow nach der Generierung ausführen* der gewünschten Voreinstellung aus. Wenn Sie eine Ausgabegenerierungsaufgabe mit der konfigurierten Ausgabevorgabe ausführen, ändert sich der Aufgabenstatus \(auf der Registerkarte „Ausgabe“\) in *Nachbearbeitung*.

## Anpassen und Aktualisieren des Asset-Workflows {#id18C3D0I0B5Z}

Standardmäßig werden die Workflow-Trigger *DAM Update Asset* immer dann angezeigt, wenn Sie ein AEM-Asset erstellen oder aktualisieren \(XML oder non-XML\). Wenn Sie beispielsweise ein Thema erstellen oder aktualisieren, wird der *DAM-Update-Asset*-Workflow ausgeführt. Der *DAM Update Asset*-Workflow versucht, relevante Metadaten aus der Assets zu extrahieren. Der vorkonfigurierte Workflow *Asset-Aktualisierung* verfügt über keine Schritte zum Extrahieren relevanter Metadaten aus einer DITA-Datei, und der Workflow *DAM-Update-Asset* generiert zum Zeitpunkt der Ausführung viele Protokolle. Wenn Sie die zusätzlichen Protokolle vermeiden möchten, können Sie den Workflow so konfigurieren, dass alle XML-Dateien aus der Verarbeitung übersprungen werden.

Führen Sie die folgenden Schritte aus, um den Workflow *DAM-Update-Asset* anzupassen:

1. Öffnen Sie die **Workflow-Starter** Seite.

   Die Standard-URL für den Zugriff auf die Seite „Workflow-Starter“ lautet:

   ```http
   http://<server name>:<port>/libs/cq/workflow/admin/console/content/launchers.html
   ```

1. Öffnen Sie in der Liste der Workflow-Starter die Eigenschaften des Workflows **DAM-Update-Asset** .

1. Fügen Sie eine Bedingung mit dem folgenden Ausdruck hinzu:

   ```json
   jcr:content/metadata/dc:format!=application/xml
   ```

1. Klicken Sie auf **Speichern und schließen**.


## Konfigurieren des XML-Workflows für die Nachbearbeitung {#id18CJB03J0Y4}

AEM Guides erstellt eine Reihe von Workflows, mit denen Sie DITA-Inhalte in AEM bearbeiten können. Es gibt beispielsweise Workflows, die ausgeführt werden, wenn Sie DITA-Inhalte hochladen oder vorhandene Inhalte aktualisieren. Diese Workflows analysieren DITA-Dokumente und führen verschiedene Aufgaben durch, z. B. das Festlegen der Metadaten, das Hinzufügen von Standardausgabesets zu neuen DITA-Zuordnungen und andere zugehörige Aufgaben.

>[!NOTE]
>
> Um die standardmäßigen Nachbearbeitungs-Workflows anzupassen oder zu erweitern, können Sie den Nachbearbeitungs-Ereignis-Handler verwenden, der in der *API-Referenz für Adobe Experience Manager Guides* beschrieben wird.

Die folgenden Eigenschaften steuern, wie AEM Guides die Nachbearbeitungs-Workflows ausführt:

>[!NOTE]
>
> Auf die folgenden Eigenschaften kann über die Web-Konsole zugegriffen werden: http://&lt;Server-Name>:&lt;Port>/system/console/configMgr.

| Eigenschaft | Bundle-Name | Beschreibung |
|--------|-----------|-----------|
| Dynamische Ausblicke | `com.adobe.fmdita.postprocess.PostProcessObservation` | Für alle Dateien, für die die Nachbearbeitung nicht durchgeführt wurde, ruft sie die ausgehenden Referenzen ab, indem sie die Themendateien analysiert. Es wird empfohlen, diese Option deaktiviert zu lassen, da sie die Möglichkeit bietet, das System zu überlasten, wenn die Anzahl der zu verarbeitenden Dateien groß ist. |
| Nachbearbeitungs-Threads | `com.adobe.fmdita.config.ConfigManager` | Legt die Anzahl der Nachbearbeitungs-Threads fest, die für den Nachbearbeitungs-Workflow verwendet werden sollen. <br>Der Standardwert ist 1. |
