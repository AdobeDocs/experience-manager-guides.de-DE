---
title: Konfigurieren des Guides-Assistenten zum Durchsuchen von Inhalten
description: Erfahren Sie, wie Sie den Guides-Assistenten für die Inhaltssuche konfigurieren
source-git-commit: 8ac0ed6b867a3efdef750cb19ed4955a67def9ee
workflow-type: tm+mt
source-wordcount: '603'
ht-degree: 0%

---


# Konfigurieren des KI-gestützten Guides-Assistenten für die Inhaltssuche

Als Administrator können Sie die Hilfsfunktion &quot;Guides Assistant&quot;für die Autoren konfigurieren. Der Guides Assistant-Dienst wird durch die auth-basierte Authentifizierung von Adobe IMS gesichert. Integrieren Sie Ihre Umgebung in die sicheren Token-basierten Authentifizierungs-Workflows von Adobe und beginnen Sie mit der Verwendung der neuen Funktion Guides Assistant . Die folgenden Konfigurationen helfen Ihnen beim Hinzufügen der **AI-Konfiguration** in ein Ordnerprofil ein. Nach dem Hinzufügen können Sie die Funktion Guides Assistant im Web Editor verwenden.

## Erstellen von IMS-Konfigurationen in der Adobe Developer-Konsole

Führen Sie die folgenden Schritte aus, um IMS-Konfigurationen in der Adobe Developer Console zu erstellen:

>[!NOTE]
>
>Wenn Sie bereits ein OAuth-Projekt erstellt haben, um die Funktion für intelligente Vorschläge oder die mikrodienstbasierte Veröffentlichung zu konfigurieren, können Sie die folgenden Schritte überspringen, um das Projekt zu erstellen.

1. Launch [Adobe Developer-Konsole](https://developer.adobe.com/console).
1. Nach erfolgreicher Anmeldung bei der Developer Console sehen Sie die **Startseite** angezeigt. Die **Startseite** auf dem Sie einfach Informationen und schnelle Links finden können, einschließlich der Links zur oberen Navigation zu Projekten und Downloads.
1. Um ein neues leeres Projekt zu erstellen, wählen Sie **Neues Projekt erstellen** aus dem **Schnellstart** Links.
   ![Schnellstartlinks](assets/conf-ss-quick-start.png) {width="550" align="left"}
   *Erstellen Sie ein neues Projekt.*

1. Auswählen **API hinzufügen** aus dem **Projekte** angezeigt.  Die **API hinzufügen** angezeigt. Auf diesem Bildschirm werden alle verfügbaren APIs, Ereignisse und Dienste für Adobe-Produkte und -Technologien angezeigt, mit denen Sie Anwendungen entwickeln können.

1. Wählen Sie die **I/O-Management-API** , um es zu Ihrem Projekt hinzuzufügen.
   ![IO-Management-API](assets/confi-ss-io-management.png)
   *Fügen Sie Ihrem Projekt die I/O-Management-API hinzu.*

1. Erstellen Sie eine neue **OAuth-Berechtigung** und speichern Sie es.
   ![OAuth-Berechtigungskachel in &quot;API konfigurieren&quot;](assets/conf-ss-OAuth-credential.png) {width="3000" align="left"}
   *Konfigurieren Sie OAuth-Anmeldedaten für Ihre API.*

1. Im  **Projekte** Registerkarte, wählen Sie die **OAuth Server to Server** und wählen Sie dann die neu erstellten Anmeldedaten aus.

1. Wählen Sie die **OAuth Server-zu-Server** -Link, um die Anmeldeinformationen Ihres Projekts anzuzeigen.

   ![Anmeldedaten](assets/conf-ss-connected-credentials.png) {width="800" align="left"}

   *Stellen Sie eine Verbindung zum Projekt her, um die Anmeldedaten anzuzeigen.*

1. Kehren Sie zu **Projekte** Registerkarte und wählen Sie **Projektübersicht** auf der linken Seite.

   <img src="assets/project-overview.png" alt="Projektübersicht" width="500">

   *Beginnen Sie mit dem neuen Projekt.*

1. Klicken Sie auf **Herunterladen** oben auf die Schaltfläche zum Herunterladen der Dienst-JSON.

   <img src="assets/download-json.png" alt="JSON herunterladen" width="500">

   *Laden Sie die Details zum JSON-Dienst herunter.*

Sie haben die OAuth-Authentifizierungsdetails konfiguriert und die Details zum JSON-Dienst heruntergeladen. Halten Sie diese Datei so bereit, wie es im nächsten Abschnitt erforderlich ist.

### Hinzufügen der IMS-Konfiguration zur Umgebung

Führen Sie die folgenden Schritte aus, um der Umgebung die IMS-Konfiguration hinzuzufügen:

1. Öffnen Sie Experience Manager und wählen Sie das Programm aus, das die Umgebung enthält, die Sie konfigurieren möchten.
1. Wechseln Sie zu **Umgebungen** Registerkarte.
1. Wählen Sie den Umgebungsnamen aus, den Sie konfigurieren möchten. Diese sollte Sie zum **Umgebungsinformationen** Seite.
1. Wechseln Sie zu **Konfiguration** Registerkarte.
1. Aktualisieren Sie das JSON-Feld SERVICE_ACCOUNT_DETAILS . Stellen Sie sicher, dass Sie denselben Namen und dieselbe Konfiguration wie im folgenden Screenshot verwenden.

![IMS-Dienstkontokonfiguration](assets/ims-service-account-config.png){width="800" align="left"}


*Fügen Sie die Details zur Umgebungskonfiguration hinzu.*




Nachdem Sie die IMS-Konfiguration zur Umgebung hinzugefügt haben, führen Sie die folgenden Schritte aus, um diese Eigenschaften mit OSGi mit AEM Guides zu verknüpfen:

1. Fügen Sie in Ihrem Git-Projektcode für Cloud Manager die folgenden beiden Dateien hinzu (für Dateiinhalte, zeigen Sie [Anhang](#appendix)).

   * `com.adobe.aem.guides.eventing.ImsConfiguratorService.cfg.json`

1. Stellen Sie sicher, dass die neu hinzugefügten Dateien von Ihrem `filter.xml`.
1. Übernehmen Sie Ihre Git-Änderungen und übertragen Sie sie.
1. Führen Sie die Pipeline aus, um die Änderungen auf die Umgebung anzuwenden.

Danach sollten Sie die **Assistent** Funktion.



## Anhang {#appendix}

**Datei**:
`com.adobe.aem.guides.eventing.ImsConfiguratorService.cfg.json`

**Inhalt**:

```
{
 "service.account.details": "$[secret:SERVICE_ACCOUNT_DETAILS]",
}
```


Nach der Konfiguration wird die **Assistent** ![Assistent](assets/guides-assistant-icon.svg) wird im rechten Bereich des Web-Editors angezeigt. Wählen Sie das Symbol aus, um die **Assistent** Bedienfeld.
Weitere Informationen finden Sie unter [KI-gestützter Guides-Assistent zum Durchsuchen von Inhalten](../user-guide/ai-based-guides-assistant.md) im Experience Manager-Benutzerhandbuch.
