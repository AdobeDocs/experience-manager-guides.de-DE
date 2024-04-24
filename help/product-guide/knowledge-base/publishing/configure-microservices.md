---
title: Neue mikrodienstbasierte Veröffentlichung für AEM Guides as a Cloud Service konfigurieren
description: Erfahren Sie, wie Sie neue mikrodienstbasierte Veröffentlichungen für AEM-Handbücher konfigurieren.
exl-id: 92e3091d-6337-4dc6-9609-12b1503684cd
feature: Microservice in AEM Guides
role: User, Admin
source-git-commit: f929d4fd74e98e2025d80c14dbef6aeb464c0dd5
workflow-type: tm+mt
source-wordcount: '711'
ht-degree: 2%

---

# Konfigurieren der Veröffentlichung auf Microservice-Basis mit JWT-Authentifizierung

[!BADGE Cloud Service]{type=Informative}

>[!NOTE]
>
> Die Anmeldedaten für Dienstkonten (JWT) wurden zugunsten der OAuth-Server-zu-Server-Anmeldeinformationen eingestellt. Ihre Anwendungen, die die Anmeldedaten für das Service-Konto (JWT) verwenden, funktionieren nach dem 1. Januar 2025 nicht mehr. Sie müssen bis zum 1. Januar 2025 zu den neuen Anmeldedaten migrieren, um sicherzustellen, dass Ihre Anwendung weiterhin funktioniert. Weitere Informationen [Migration von JWT-Anmeldedaten (Service Account) zu OAuth-Server-zu-Server-Anmeldedaten](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/migration/).



Die mikrodienstbasierte Veröffentlichung in für Adobe Experience Manager Guides as a Cloud Service unterstützt die Typen von Ausgabevorgaben (nativ und DITA-OT-basiert), HTML5, JSON und CUSTOM.

Da die Anmeldedaten für das Dienstkonto (JWT) veraltet sind, wird empfohlen, die OAuth-basierte Authentifizierung von Adobe IMS zu verwenden. Erfahren Sie, wie [Konfigurieren der Veröffentlichung auf Microservice-Basis mit OAuth-Authentifizierung](configure-microservices-imt-config.md).

Für den durch die JWT-basierte Authentifizierung von Adobe IMS gesicherten Publishing-Dienst sollten Kunden die folgenden Schritte ausführen, um ihre Umgebungen mit sicheren Token-basierten Authentifizierungsworkflows zu integrieren und mit der Verwendung der neuen Cloud-basierten skalierbaren Publishing-Lösung zu beginnen.


## Erstellen von IMS-Konfigurationen in der Adobe Developer-Konsole

**Rolle, die zur Erstellung der Verwirrungen erforderlich ist**: Systemadministrator

Führen Sie die folgenden Schritte aus, um IMS-Konfigurationen in der Adobe Developer Console zu erstellen:

1. Öffnen Sie die Entwicklerkonsole: `https://developer.adobe.com/console`.

1. Wechseln zu **Projekte** von oben aus.

   <img src="assets/projects-tab.png" alt="Projekt-Tab" width="500">

1. Um ein neues leeres Projekt zu erstellen, wählen Sie **Leeres Projekt** aus dem **Neues Projekt erstellen** Dropdown.

   <img src="assets/create-new-project.png" alt="Neues Projekt erstellen" width="500">

1. Auswählen **API** aus dem **Zum Projekt hinzufügen** Dropdown-Liste, um Ihrem Projekt die IO Management-API hinzuzufügen.

   <img src="assets/add-project.png" alt="Projekt hinzufügen" width="300">

   <img src="assets/io-management-api.png" alt="IO-Management" width="500">

1. Erstellen Sie beim Hinzufügen der API ein neues Paar aus privatem/öffentlichem Schlüssel. Dadurch wird automatisch der private Schlüssel auf Ihr System heruntergeladen.

   <img src="assets/generate-key-pair.png" alt="Schlüsselpaar generieren" width="500">

1. Speichern Sie die konfigurierte API.

   <img src="assets/save-api.png" alt="API speichern" width="600">

1. Gehen Sie zurück zu **Projekte** Registerkarte und klicken Sie auf **Projektübersicht** auf der linken Seite.

   <img src="assets/project-overview.png" alt="Projektübersicht" width="500">

1. Klicks **Herunterladen** oben auf die Schaltfläche zum Herunterladen der Dienst-JSON.

   <img src="assets/download-json.png" alt="JSON herunterladen" width="500">

Sie haben jetzt die Details zur JWT-Authentifizierung konfiguriert und auch den privaten Schlüssel und die JSON-Datei mit den Dienstdetails heruntergeladen. Halten Sie diese beiden Dateien bereit, da diese Dateien im nächsten Abschnitt benötigt werden.

### Hinzufügen der IMS-Konfiguration zur Umgebung

Führen Sie die folgenden Schritte aus, um der Umgebung die IMS-Konfiguration hinzuzufügen:

1. Öffnen Sie Experience Manager und wählen Sie dann Ihr Programm aus, das die Umgebung enthält, die Sie konfigurieren möchten.
1. Wechseln zu **Umgebungen** Registerkarte.
1. Klicken Sie auf den Umgebungsnamen, den Sie konfigurieren möchten. Dies sollte Sie zur Seite &quot;Umgebungsinformationen&quot;führen.
1. Wechseln zu **Konfiguration** Registerkarte.
1. Laden Sie den privaten Schlüssel und die Projekt-JSON hoch, wie im Screenshot unten dargestellt. Stellen Sie sicher, dass Sie dieselben Namen und Konfigurationen wie unten hervorgehoben verwenden.

   <img src="assets/ims-config-environment.png" alt="ims-Konfigurationen" width="500">

>[!NOTE]
>
> Sie müssen den Inhalt der JSON-Datei mit Details zum privaten Schlüssel und Dienst in die Wertspalte des Konfigurationsbereichs öffnen, kopieren und einfügen, wie im obigen Screenshot gezeigt.

Nachdem Sie die IMS-Konfiguration zur Umgebung hinzugefügt haben, führen Sie die folgenden Schritte aus, um diese Eigenschaften mit OSGi-Experience Manager-Handbüchern zu verknüpfen:

1. Fügen Sie in Ihrem Git-Projektcode des Cloud Manager die folgenden beiden Dateien hinzu (Dateiinhalte finden Sie unter [Anhang](#appendix)).

   * `com.adobe.aem.guides.eventing.ImsConfiguratorService.cfg.json`
   * `com.adobe.fmdita.publishworkflow.PublishWorkflowConfigurationService.xml`
1. Stellen Sie sicher, dass die neu hinzugefügten Dateien von Ihrem `filter.xml`.
1. Übernehmen Sie Ihre Git-Änderungen und übertragen Sie sie.
1. Führen Sie die Pipeline aus, um die Änderungen auf die Umgebung anzuwenden.

Danach sollten Sie in der Lage sein, das neue Microservice-basierte Cloud Publishing zu verwenden.

## Häufig gestellte Fragen

1. Kann ein einzelner Schlüssel in mehreren Cloud-Umgebungen verwendet werden?
   * Ja, Sie können einen privaten Schlüssel generieren und ihn für alle Umgebungen verwenden. Sie müssen jedoch Umgebungsvariablen für alle Umgebungen konfigurieren und denselben Schlüssel verwenden.
1. Wenn OSGi-Konfigurationen zur Verwendung von Microservice aktiviert sind, funktioniert der Veröffentlichungsprozess auf einem lokalen AEM-Server mit derselben Codebasis?
   * Nein, wenn die Markierung `dxml.use.publish.microservice` auf `true` dann sucht es immer nach Microservice-Konfigurationen. Satz `dxml.use.publish.microservice` nach `false` , damit die Veröffentlichung auf Ihrer lokalen Seite funktioniert.
1. Wie viel Speicher wird dem DITA-Prozess bei der Verwendung von mikrodienstbasierter Veröffentlichung zugewiesen? Wird dies über DITA-Profil-Ameisenparameter gesteuert?
   * Bei mikrodienstbasierter Veröffentlichung wird die Speicherzuordnung nicht durch DITA-Profil-ant-Parameter gesteuert. Der im Dienstcontainer verfügbare Gesamtspeicher beträgt 8 GB, von denen 6 GB dem DITA-OT-Prozess zugeordnet sind.


## Anhang {#appendix}

**Datei**:
`com.adobe.aem.guides.eventing.ImsConfiguratorService.cfg.json`

**Inhalt**:

```
{
  "service.account.details": "$[secret:SERVICE_ACCOUNT_DETAILS]",
  "private.key": "$[secret:PRIVATE_KEY]"
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
