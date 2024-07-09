---
title: Konfigurieren der mikrodienstbasierten Veröffentlichung mit der OAuth-Authentifizierung für AEM Guides as a Cloud Service
description: Erfahren Sie, wie Sie die Veröffentlichung auf Microservice-Basis mit OAuth-Authentifizierung für AEM Guides konfigurieren.
feature: Microservice in AEM Guides
role: Admin
exl-id: db0c83c7-1ece-4010-b214-f8d806d26bc9
source-git-commit: c51a372dc44921a489219f5ac99e3ad180ccc91d
workflow-type: tm+mt
source-wordcount: '827'
ht-degree: 0%

---

# Konfigurieren der mikrodienstbasierten Veröffentlichung mit OAuth-Authentifizierung

Mit dem Publishing-Microservice können Sie große Veröffentlichungsarbeitslasten gleichzeitig auf Experience Manager Guides as a Cloud Service ausführen und die branchenführende Server-lose Adobe I/O Runtime-Plattform nutzen.

Für jede Veröffentlichungsanforderung führt Experience Manager Guides as a Cloud Service einen separaten Container aus, der entsprechend den Benutzeranforderungen horizontal skaliert wird. Dies bietet die Möglichkeit, mehrere Veröffentlichungsanfragen auszuführen und eine bessere Leistung zu erzielen als die großen On-Premise-Adobe Experience Manager-Server.

>[!NOTE]
>
> Microservice-basierte Veröffentlichung in Experience Manager Guides unterstützt die Typen von PDF (nativ und DITA-OT-basiert), HTML5, JSON und benutzerdefinierten Ausgabevorgaben.

Da der Cloud Publishing-Dienst durch die Adobe IMS OAuth-basierte Authentifizierung geschützt ist, führen Sie die folgenden Schritte aus, um ihre Umgebungen mit sicheren Token-basierten Authentifizierungsarbeitsabläufen zu integrieren und mit der Cloud-basierten skalierbaren Publishing-Lösung zu beginnen.


## Erstellen von IMS-Konfigurationen in Adobe Developer Console

**Rolle, die zum Erstellen der Konfigurationen erforderlich ist**: Systemadministrator

Führen Sie die folgenden Schritte aus, um IMS-Konfigurationen in zu erstellen **Adobe Developer Console**:

>[!NOTE]
>
>Wenn Sie bereits ein OAuth-Projekt erstellt haben, um die KI-gestützten intelligenten Vorschläge für das Authoring zu konfigurieren, können Sie die folgenden Schritte überspringen, um das Projekt zu erstellen.

1. Öffnen **Developer Console**: `https://developer.adobe.com/console`.

1. Wechseln Sie zu **Projekte** oben.

   <img src="assets/projects-tab.png" alt="Projekt-Tab" width="500">

   *Wählen Sie die **Projekte**auf der Registerkarte **Adobe Developer Console***

1. Um ein neues leeres Projekt zu erstellen, wählen Sie **Leeres Projekt** aus dem **Neues Projekt erstellen** Dropdown.

   <img src="assets/create-new-project.png" alt="Neues Projekt erstellen" width="500">

   *Erstellen Sie ein neues leeres Projekt.*

1. Auswählen **API** aus dem **Zum Projekt hinzufügen** Dropdown-Liste, um Ihrem Projekt die IO Management-API hinzuzufügen.

   <img src="assets/add-project.png" alt="Projekt hinzufügen" width="300">

   *Wählen Sie ein API-Projekt aus der Dropdown-Liste aus.*

   <img src="assets/io-management-api.png" alt="IO-Management" width="500">

   *Fügen Sie Ihrem Projekt die I/O-Management-API hinzu.*

1. Erstellen Sie eine neue OAuth-Berechtigung und speichern Sie sie.

   <img src="assets/microservice-api-oauth.png" alt="Schlüsselpaar generieren" width="500">

   *Konfigurieren Sie OAuth-Anmeldedaten für Ihre API.*


1. Kehren Sie zu **Projekte** Registerkarte und wählen Sie **Projektübersicht** auf der linken Seite.

   <img src="assets/project-overview.png" alt="Projektübersicht" width="500">

   *Beginnen Sie mit dem neuen Projekt.*

1. Klicken Sie auf **Herunterladen** oben auf die Schaltfläche zum Herunterladen der Dienst-JSON.

   <img src="assets/download-json.png" alt="JSON herunterladen" width="500">

   *Laden Sie die Details zum JSON-Dienst herunter.*

Sie haben die OAuth-Authentifizierungsdetails konfiguriert und die Details zum JSON-Dienst heruntergeladen. Halten Sie diese Datei so bereit, wie es im nächsten Abschnitt erforderlich ist.


## Hinzufügen der IMS-Konfiguration zur Umgebung

>[!NOTE]
>
>Wenn Sie bereits ein OAuth-Projekt für intelligente Vorschläge erstellt haben, können Sie dasselbe Projekt für Microservices wiederverwenden und die folgenden Schritte überspringen, um die IMS-Konfiguration zur Umgebung hinzuzufügen.

### Vorhandene Konfiguration aktualisieren (JWT auf OAuth shift )

Wenn Sie bereits einen Microservice für die Veröffentlichung mit JWT (nicht mehr unterstützt) verwenden, führen Sie die folgenden Schritte aus, um die Konfigurationen zu aktualisieren:



1. Öffnen **Experience Manager** und wählen Sie das Programm aus, das die Umgebung enthält, die Sie konfigurieren möchten.
1. Wechseln Sie zu **Umgebungen** Registerkarte.
1. Wählen Sie den Namen der Umgebung aus, die Sie konfigurieren möchten. Diese sollte Sie zum **Umgebungsinformationen** Seite.
1. Wechseln Sie zu **Konfiguration** Registerkarte.

1. Aktualisieren Sie das JSON-Feld SERVICE_ACCOUNT_DETAILS mit der neuen JSON-Datei OAuth , die Sie heruntergeladen haben.
1. Löschen Sie das Feld PRIVATE_KEY .



   <img src="assets/ims-service-account-config.png" alt="IMS-Dienstkontokonfiguration" width="500">

   *Aktualisieren Sie die vorhandenen JWT-Umgebungskonfigurationen.*

### Erstmalige Konfiguration

Um einen Publishing-Microservice zum ersten Mal zu verwenden, aktualisieren Sie die Konfigurationen wie folgt:
1. Öffnen **Experience Manager** und wählen Sie das Programm aus, das die Umgebung enthält, die Sie konfigurieren möchten.
1. Wechseln Sie zu **Umgebungen** Registerkarte.
1. Wählen Sie den Namen der Umgebung aus, die Sie konfigurieren möchten. Diese sollte Sie zum **Umgebungsinformationen** Seite.
1. Wechseln Sie zu **Konfiguration** Registerkarte.

1. Erstellen Sie eine neue Konfiguration mit dem Namen SERVICE_ACCOUNT_DETAILS. Fügen Sie als Wert den Inhalt der OAuth-JSON-Datei hinzu, den Sie von der Entwicklerkonsole heruntergeladen haben.


<img src="assets/jws-service-account-config.png" alt="IMS-Dienstkontokonfiguration" width="500">

*Konfigurieren Sie die Umgebung zum ersten Mal.*


### Erstmalige Codeänderungen für die Aktivierung der mikrodienstbasierten Veröffentlichung

>[!NOTE]
>
> Überspringen Sie die folgenden Schritte, wenn Sie bereits eine mikrodienstbasierte Veröffentlichung verwenden:

Nachdem Sie die IMS-Konfiguration zur Umgebung hinzugefügt haben, führen Sie die folgenden Schritte aus, um diese Eigenschaften mithilfe von OSGi mit Experience Manager Guides zu verknüpfen:

1. Fügen Sie in Ihrem Git-Projektcode für Cloud Manager die folgenden beiden Dateien hinzu `/apps/fmditaCustom/config` (für Dateiinhalte, Ansicht [Anhang](#appendix)).

   * `com.adobe.aem.guides.eventing.ImsConfiguratorService.cfg.json`
   * `com.adobe.fmdita.publishworkflow.PublishWorkflowConfigurationService.xml`
1. Stellen Sie sicher, dass die neu hinzugefügten Dateien von Ihrem `filter.xml`.
1. Übernehmen Sie Ihre Git-Änderungen und übertragen Sie sie.
1. Führen Sie die Pipeline aus, um die Änderungen auf die Umgebung anzuwenden.

Danach können Sie die Microservice-basierte Cloud-Veröffentlichung verwenden.

## Häufig gestellte Fragen


1. Wenn OSGi-Konfigurationen für die Verwendung von Microservice aktiviert sind, funktioniert der Veröffentlichungsprozess auf dem lokalen Experience Manager-Server mit derselben Codebasis?
   * Nein, wenn die Markierung `dxml.use.publish.microservice` auf `true`, sucht es immer nach Microservice-Konfigurationen. Satz `dxml.use.publish.microservice` nach `false` , damit die Veröffentlichung auf Ihrem lokalen Server funktioniert.
1. Wie viel Speicher wird dem DITA-Prozess bei der Verwendung von mikrodienstbasierter Veröffentlichung zugewiesen? Wird dies über das DITA-Profil und die -Parameter gesteuert?
   * Bei mikrodienstbasierter Veröffentlichung wird die Speicherzuordnung nicht durch das DITA-Profil und die -Parameter gesteuert. Der im Dienstcontainer verfügbare Gesamtspeicher beträgt 8 GB, von denen 6 GB dem DITA-OT-Prozess zugeordnet sind.


## Anhang {#appendix}

**Datei**:
`com.adobe.aem.guides.eventing.ImsConfiguratorService.cfg.json`

**Inhalt**:

```
{
"service.account.details": "$[secret:SERVICE_ACCOUNT_DETAILS]",
}
```

**Datei**: `com.adobe.fmdita.publishworkflow.PublishWorkflowConfigurationService.xml`

**Inhalt**:
* `dxml.use.publish.microservice`: Wechsel zur Aktivierung der Veröffentlichung auf Microservice-Basis mithilfe von DITA-OT
* `dxml.use.publish.microservice.native.pdf`: Wechsel zur Aktivierung der mikrodienstbasierten nativen PDF-Veröffentlichung

```
<?xml version="1.0" encoding="UTF-8"?>
<jcr:root xmlns:jcr="http://www.jcp.org/jcr/1.0" xmlns:sling="http://sling.apache.org/jcr/sling/1.0"
          jcr:primaryType="sling:OsgiConfig"
          dxml.publish.microservice.url="https://adobeioruntime.net/api/v1/web/543112-guidespublisher/default/publishercaller.json"
          dxml.use.publish.microservice="{Boolean}true"
          dxml.use.publish.microservice.native.pdf="{Boolean}true"
/>
```
