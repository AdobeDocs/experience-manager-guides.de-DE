---
title: Konfigurieren und Anpassen von Workflows
description: Erfahren Sie, wie Sie Workflows konfigurieren und anpassen
exl-id: 3be387b9-6ac2-4b61-afdf-fbe9d8b6cc1e
feature: Workflow Configuration
role: Admin
level: Experienced
source-git-commit: 6e23f52fc9124d0f07f8108da1b5fe574f553469
workflow-type: tm+mt
source-wordcount: '2126'
ht-degree: 4%

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

Das Inhaltserstellungs-Team jedes Unternehmens arbeitet auf eine bestimmte Weise, um seine Geschäftsanforderungen zu erfüllen. In einigen Organisationen gibt es einen dedizierten Editor, während andere Organisationen ein automatisiertes redaktionelles Überprüfungssystem haben könnten. In einer Organisation kann ein typischer Authoring- und Publishing-Workflow beispielsweise Aufgaben wie enthalten: Wenn ein Autor mit der Inhaltserstellung fertig ist, geht er automatisch an die Validierungsverantwortlichen. Nach Abschluss der Überprüfung wird er an den Publisher weitergeleitet, um die endgültige Ausgabe zu generieren. In AEM können Aktivitäten, die Sie mit Ihren Inhalten und Assets durchführen, in Form eines Prozesses kombiniert und einem AEM-Workflow zugeordnet werden. Weitere Informationen zu Workflows in AEM finden Sie unter [Verwalten von Workflows](https://helpx.adobe.com/de/experience-manager/6-5/sites/administering/using/workflows.html) in der Dokumentation zu AEM.

Mit AEM Guides können Sie den standardmäßigen Überprüfungs-Workflow anpassen. Sie können die folgenden vier benutzerdefinierten Überprüfungsprozesse mit Ihren anderen Authoring- oder Publishing-Workflows verwenden.

- **Überprüfung erstellen**: Dieser Prozess bereitet die Metadaten vor, die zum Erstellen einer Prüfungsaufgabe erforderlich sind. Beispielsweise werden den Reviewern Überprüfungsberechtigungen zugewiesen, der Status der zu überprüfenden Themen wird auf überprüft, die Zeitpläne für Überprüfungen werden festgelegt und vieles mehr. Von den vier Prozessen ist dies der einzige obligatorische Prozess, der in Ihren benutzerdefinierten Workflow aufgenommen werden muss. In Ihrem Workflow können Sie die anderen drei Prozesse ein- oder ausschließen.

- **Prüfungsaufgabe zuweisen**: Dieser Prozess erstellt die Prüfungsaufgabe und sendet die Aufgabenbenachrichtigung an den Initiator und die Validierungsverantwortlichen.

- **Überprüfungs-E-Mail senden**: Dieser Prozess sendet die Überprüfungs-E-Mail an den Initiator und die Validierungsverantwortlichen.

- **Auftrag zum Schließen der Überprüfung planen**: Dieser Prozess stellt sicher, dass der Überprüfungsprozess beim Erreichen der Frist abgeschlossen wird.


Beim Erstellen eines benutzerdefinierten Überprüfungs-Workflows besteht die erste Aufgabe darin, die erforderlichen Metadaten festzulegen, die für den Prozess „Überprüfung erstellen“ benötigt werden. Dazu können Sie ein ECMA-Skript erstellen. Ein Beispiel für das ECMA-Skript, das die Metadaten zuweist, finden Sie unten sowohl für das Thema als auch für die Zuordnung.

**für Thema**

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
workflowdata.getMetaDataMap().put("reviewType", "AEM");
workflowdata.getMetaDataMap().put("versionJson", "[{\"path\":\"GUID-ca6ae229-889a-4d98-a1c6-60b08a820bb3.dita\",\"review\":true,\"version\":\"1.0\",\"reviewers\":[\"projects-samplereviewproject-owner\"]}]");
workflowdata.getMetaDataMap().put("isDitamap","false");
workflowdata.getMetaDataMap().put("reviewVersion","3.0");
```

**Für Karte**

```json
var workflowdata = workItem.getWorkflowData();
workflowdata.getMetaDataMap().put("initiator", "admin");
workflowdata.getMetaDataMap().put("operation", "AEM_REVIEW");
workflowdata.getMetaDataMap().put("orgTopics", "GUID-ae42f13c-7201-4453-9a3a-c87675a5868e.dita|GUID-28a6517b-1b62-4d3a-b7dc-0e823225b6a5.dita|GUID-dd699e10-118d-4f1b-bf19-7f1973092227.dita|");
var payloadJson = "{\"referrer\":\"\",\"rootMap\":\"GUID-17feb385-acf3-4113-b838-77b11fd6988d.ditamap\",\"asset\":[\"GUID-17feb385-acf3-4113-b838-77b11fd6988d.ditamap\"],\"base\":\"/content/dam\"}";
workflowdata.getMetaDataMap().put("payloadJson", payloadJson);
workflowdata.getMetaDataMap().put("deadline", "2047-06-27T13:19:00.000+05:30");
workflowdata.getMetaDataMap().put("title", "Review task via workflow with map");
workflowdata.getMetaDataMap().put("description", "Review task via workflow with map Description");
workflowdata.getMetaDataMap().put("assignee", "user-one");
workflowdata.getMetaDataMap().put("status", "1");
workflowdata.getMetaDataMap().put("projectPath", "/content/projects/review_project_via_workflow");
workflowdata.getMetaDataMap().put("startTime", new Date().getTime());
var versionJson = "[{\"path\":\"GUID-ae42f13c-7201-4453-9a3a-c87675a5868e.dita\",\"version\":\"1.0\",\"review\":true,\"reviewers\":[\"starling-regression-user\"]},{\"path\":\"GUID-28a6517b-1b62-4d3a-b7dc-0e823225b6a5.dita\",\"version\":\"1.0\",\"review\":true,\"reviewers\":[\"starling-regression-user\"]},{\"path\":\"GUID-dd699e10-118d-4f1b-bf19-7f1973092227.dita\",\"version\":\"1.0\",\"review\":true,\"reviewers\":[\"starling-regression-user\"]}]";
workflowdata.getMetaDataMap().put("versionJson", versionJson);
workflowdata.getMetaDataMap().put("notifyViaEmail", "true");
workflowdata.getMetaDataMap().put("allowAllReviewers", "false");
workflowdata.getMetaDataMap().put("isDitamap", "true");
workflowdata.getMetaDataMap().put("ditamap", "GUID-17feb385-acf3-4113-b838-77b11fd6988d.ditamap");
var ditamapHierarchy = "[{\"path\":\"GUID-17feb385-acf3-4113-b838-77b11fd6988d.ditamap\",\"items\":[{\"path\":\"GUID-db5787bb-5467-4dc3-b3e5-cfde562ee745.ditamap\",\"items\":[{\"path\":\"GUID-ae42f13c-7201-4453-9a3a-c87675a5868e.dita\",\"items\":[],\"title\":\"\"},{\"path\":\"GUID-28a6517b-1b62-4d3a-b7dc-0e823225b6a5.dita\",\"items\":[],\"title\":\"\"}],\"title\":\"\"},{\"path\":\"GUID-dd699e10-118d-4f1b-bf19-7f1973092227.dita\",\"items\":[],\"title\":\"\"}]}]";
workflowdata.getMetaDataMap().put("ditamapHierarchy", ditamapHierarchy);
workflowdata.getMetaDataMap().put("reviewVersion","3.0");
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
| `projectPath` | Zeichenfolge | Pfad des Überprüfungsprojekts, dem die Überprüfungsaufgabe zugewiesen wird, z. B.: /content/projects/samplereviewproject. |
| `reviewType` | Zeichenfolge | Statischer Wert &quot;AEM&quot;. |
| `versionJson` | JSON-Objekt | versionJson ist eine Liste von Themen, die in die Überprüfung aufgenommen werden und bei denen jedes Themenobjekt die folgende Struktur aufweist [ { „Pfad“: &quot;/content/dam/1-topic.dita&quot;, „Version“: „1.1“, „Überprüfung“: true, „Validierungsverantwortliche“: [„projects-we_retail-editor“] } ] |
| `isDitamap` | Boolescher Wert | false/true |
| `ditamapHierarchy` | JSON-Objekt | Falls die Karte zur Überprüfung gesendet wird, sollte der Wert hier wie folgt sein:[ { „path“: „GUID-f0df1513-fe07-473f-9960-477d4df29c87.ditamap“, „items“: [ { „path“: „GUID-9747e8ab-8cf1-45dd-9e20-d47d482f667d.dita“, „title“: &quot;&quot;, „items“: [] } ] } ]. |
| `ditamap` | Zeichenfolge | Geben Sie den Pfad der Imagemap der Prüfungsaufgabe an |
| `allowAllReviewers` | Boolescher Wert | false/true |
| `notifyViaEmail` | Boolescher Wert | false/true |
| `reviewVersion` | Zeichenfolge | Gibt die aktuelle Version des Überprüfungs-Workflows an. Der Standardwert ist auf `3.0` festgelegt.<br> Um die neuen Funktionen des Überprüfungs-Workflows für [Autoren](../user-guide/review-close-review-task.md) und [Prüfer](../user-guide/review-complete-review-tasks.md) zu aktivieren, stellen Sie sicher, dass die `reviewVersion` auf `3.0` eingestellt ist. |


Nachdem Sie das Skript erstellt haben, rufen Sie es auf, bevor Sie den Prozess zum Erstellen einer Überprüfung in Ihrem Workflow aufrufen. Anschließend können Sie je nach Ihren Anforderungen die anderen Überprüfungs-Workflow-Prozesse aufrufen.

### Entfernen des Überprüfungs-Workflows aus der Bereinigungskonfiguration

Um die Leistung der Workflow-Engine zu verbessern, können Sie regelmäßig abgeschlossene Workflow-Instanzen aus dem AEM-Repository löschen. Wenn Sie die standardmäßigen AEM-Konfigurationen verwenden, werden alle abgeschlossenen Workflow-Instanzen nach einem bestimmten Zeitraum bereinigt. Dies führt auch dazu, dass alle Überprüfungs-Workflows aus dem AEM-Repository gelöscht werden.

Sie können verhindern, dass Überprüfungs-Workflows automatisch bereinigen, indem Sie das Modell des Überprüfungs-Workflows \(information\) aus der Konfiguration der automatischen Bereinigung entfernen. Sie müssen die **Adobe Granite Workflow-Bereinigungskonfiguration** verwenden, um die Workflow-Modelle für die Überprüfung aus der Liste für die automatische Bereinigung zu entfernen.

Stellen Sie in der **Adobe Granite Workflow-Bereinigungskonfiguration** sicher, dass Sie mindestens einen Workflow auflisten, den Sie sicher bereinigen können. Sie können beispielsweise einen der folgenden von AEM Guides erstellten Workflows verwenden:

- /etc/workflow/models/publishditamap/jcr:content/model
- /etc/workflow/models/post-dita-project-creation-tasks/ jcr:content/model

Durch Hinzufügen eines Workflows in der **Adobe Granite Workflow-Bereinigungskonfiguration** wird sichergestellt, dass AEM nur die Workflows bereinigt, die in der Konfiguration aufgeführt sind. Dadurch wird verhindert, dass AEM die Informationen des Überprüfungs-Workflows bereinigt.

Weitere Informationen zum Konfigurieren der **Adobe Granite Workflow-Bereinigungskonfiguration** finden Sie unter *Verwalten von Workflow-Instanzen* in der Dokumentation zu AEM.

### E-Mail- und AEM-Benachrichtigung anpassen

In einer Reihe von AEM Guides-Workflows werden E-Mail-Benachrichtigungen verwendet. Wenn Sie beispielsweise eine Prüfungsaufgabe initiieren, wird eine E-Mail-Benachrichtigung an die Validierungsverantwortlichen gesendet. Um jedoch sicherzustellen, dass die E-Mail-Benachrichtigung gesendet wird, müssen Sie diese Funktion in AEM aktivieren. Informationen zum Aktivieren der E-Mail-Benachrichtigung in AEM finden Sie im Artikel [Konfigurieren von E-Mail](https://experienceleague.adobe.com/docs/experience-manager-release-information/aem-release-updates/previous-updates/aem-previous-versions.html?lang=de) in der Dokumentation zu AEM.

AEM Guides enthält eine Reihe von E-Mail- und AEM-Benachrichtigungen, die Sie anpassen können. Führen Sie die folgenden Schritte aus, um diese Benachrichtigungen anzupassen:

1. Verwenden Sie den Package Manager, um `/libs/fmdita/mail/review` Ordner herunterzuladen.

   >[!NOTE]
   >
   > Nehmen Sie keine Anpassungen in den Standardkonfigurationsdateien im Knoten ``libs`` vor. Sie müssen eine Überlagerung des Knotens ``libs`` im Knoten ``apps`` erstellen und die erforderlichen Dateien nur im Knoten ``apps`` aktualisieren.

1. Der Ordner `review` enthält die folgenden Unterordner:

   - `aem-notification`
   - `CSS`
   - `email-notification`

   Die detaillierte Beschreibung dieser Unterordner wird unten erläutert:

   | Überprüfen von Unterordnern | Beschreibung |
   |-----------------|-----------|
   | `aem-notification` | Enthält verschiedene AEM-Benachrichtigungstypen, die angepasst werden können. <br> `closed` <br> `content-updated` <br> `feedback-addressed` <br> `feedback-provided` <br> `requested` <br> `reviewer-removed` <br> `tag-mention` <br> In diesen Unterordnern befinden sich `primary.vm`- und `secondary.vm`, mit denen Sie den Titel bzw. die Beschreibung der AEM-Benachrichtigung anpassen können. |
   | `CSS` | Enthält die `email-notification.css` zum Anpassen des Stils von E-Mail-Benachrichtigungen. |
   | `email-notification` | Enthält verschiedene E-Mail-Benachrichtigungstypen, die angepasst werden können. <br> `closed` <br> `content-updated` <br> `feedback-addressed` <br> `feedback-provided` <br> `requested` <br> `reviewer-removed` <br> `tag-mention` <br> In diesen Unterordnern befinden sich `primary.vm`- und `secondary.vm`, mit denen Sie den Betreff bzw. Text der E-Mail-Benachrichtigung anpassen können. |

Die Definition der einzelnen Benachrichtigungstypen ist unten beschrieben:

- `closed`: Trigger beim Schließen einer Prüfungsaufgabe.
- `content-updated`: Trigger, wenn ein Autor oder Initiator den Inhalt aktualisiert.
- `feedback-addressed`: Trigger, wenn der Autor oder Initiator die Kommentare kommentiert und eine Überprüfung durch den Reviewer anfordert.
- `feedback-provided` Trigger, wenn ein Reviewer die Aufgabe als abgeschlossen markiert, indem er dem Autor oder Initiator der Prüfungsaufgabe Kommentare auf Aufgabenebene bereitstellt.
- `requested`: Trigger, wenn ein Autor oder Initiator eine Prüfungsaufgabe erstellt.
- `reviewer-removed`: Trigger, bei denen die Zuweisung eines Reviewers zu einer Prüfungsaufgabe aufgehoben wird.
- `tag-mention`: Trigger, wenn ein Benutzer in Überprüfungskommentaren erwähnt oder getaggt wird.

Stellen Sie beim Anpassen einer E-Mail oder AEM-Benachrichtigung sicher, dass Sie nur den folgenden vordefinierten Variablensatz verwenden, der in `primary.vm`- und `secondary.vm`-Dateien verwendet wird.


| **Variablenname** | **Beschreibung** | **Datentyp** |
|-------------------------|---------------------------------------------------------------|---------------|
| `projectPath` | Pfad zum Projekt mit der Prüfungsaufgabe | Zeichenfolge |
| `reviewTitle` | Titel der Prüfungsaufgabe | Zeichenfolge |
| `projectName` | Name des Projekts | Zeichenfolge |
| `commentator` | Name des Benutzers, der einen Kommentar hinzugefügt hat | Zeichenfolge |
| `commentExcerpt` | Fragment des hinzugefügten Kommentars | Zeichenfolge |
| `taskLink` | Direkter Link zur Prüfungsaufgabe | URL |
| `authorName` | Name des Autors, der die Prüfungsaufgabe erstellt oder aktualisiert hat | Zeichenfolge |
| `dueDate` | Fälligkeitsdatum der Prüfungsaufgabe | Datum |
| `reviewerName` | Name des der Aufgabe zugewiesenen Reviewers | Zeichenfolge |
| `user` | Benutzer, der an der Prüfungsaufgabe beteiligt ist, z. B. Autor, Prüfer oder sogar Administrator. | Zeichenfolge |
| `recipient` | Spezifischer Benutzer, der die Benachrichtigung erhält | Zeichenfolge |


## Anpassen des Workflows nach der Ausgabe {#id17A6GI004Y4}

AEM Guides bietet Ihnen die Flexibilität, einen Workflow nach der Ausgabe anzugeben. Sie können einige Nachbearbeitungsaufgaben für die Ausgabe ausführen, die mit AEM Guides generiert wird. Beispielsweise können Sie einige CQ-Tags auf die generierte Ausgabe der AEM-Site anwenden oder bestimmte Eigenschaften auf die PDF-Ausgabe festlegen oder eine E-Mail an eine Benutzergruppe senden, sobald die Ausgabe generiert wurde.

Sie können ein neues Workflow-Modell erstellen, das als Workflow nach der Generierung von Ausgaben verwendet werden kann. Wenn ein Workflow zur Erzeugung nach der Ausgabe ausgelöst wird, gibt der Workflow zur Erzeugung von Ausgaben kontextuelle Informationen über die Workflow-Metadatenzuordnung frei, mit denen Sie die Verarbeitung der generierten Ausgabe durchführen können. In der folgenden Tabelle werden die als Metadaten freigegebenen Kontextinformationen beschrieben:

| Eigenschaft | Typ | Beschreibung |
|--------|----|-----------|
| ``outputName`` | Zeichenfolge | Name der Ausgabevorgabe, die zum Generieren der Ausgabe verwendet wird. |
| `generatedPath` | Zeichenfolge | Pfad im DAM, in dem die generierte Ausgabe gespeichert wird. |
| `outputType` | com.adobe.fmdita.output.OutputType | Typ der Ausgabevorgabe. |
| `outputTitle` | Zeichenfolge | Titel der Ausgabevorgabe. |
| `outputHistoryPath` | Zeichenfolge | Repository-Pfad des Verlaufsknotens. |
| `isSuccess` | Boolescher Wert | Eine Markierung, die den endgültigen Status des Ausgabegenerierungsprozesses darstellt - Erfolg oder Fehler. |
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
