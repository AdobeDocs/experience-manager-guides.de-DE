---
title: Konfigurieren der Smart-Hilfe für die Inhaltssuche
description: Erfahren Sie, wie Sie die Smart-Hilfe für die Inhaltssuche konfigurieren
exl-id: b5836c02-027e-459a-a7f0-f7d631f999dc
source-git-commit: 682eaf6f4a3a158f49a8f2ea91ce9cd2de3ff772
workflow-type: tm+mt
source-wordcount: '609'
ht-degree: 0%

---

# Konfigurieren der KI-gestützten Smart-Hilfe für die Suche nach Inhalten

Als Administrator können Sie die Funktion der intelligenten Hilfe für die Autoren konfigurieren. Der Smart Help-Service wird durch die authentifizierungsbasierte Adobe IMS-Authentifizierung gesichert. Integrieren Sie Ihre Umgebung mit den sicheren Token-basierten Authentifizierungs-Workflows von Adobe und verwenden Sie die neue Funktion „Smart Help“. Mit den folgenden Konfigurationen können Sie die Registerkarte **KI-Konfiguration** zu einem Ordnerprofil hinzufügen. Nach dem Hinzufügen können Sie die Funktion „Smart-Hilfe“ im Web-Editor verwenden.

## Erstellen von IMS-Konfigurationen in Adobe Developer Console

Führen Sie die folgenden Schritte aus, um IMS-Konfigurationen in Adobe Developer Console zu erstellen:

>[!NOTE]
>
>Wenn Sie bereits ein OAuth-Projekt erstellt haben, um die Smart Suggestions-Funktion für die auf Microservices basierende Veröffentlichung zu konfigurieren, können Sie die folgenden Schritte überspringen, um das Projekt zu erstellen. Sie können mit Schritt 8 beginnen.

1. [Adobe Developer Console starten](https://developer.adobe.com/console).
1. Nach erfolgreicher Anmeldung bei Developer Console wird der Bildschirm &quot;**&quot;**. Auf dem **Startseite**-Bildschirm finden Sie mühelos Informationen und Schnelllinks, einschließlich der oberen Navigationslinks zu Projekten und Downloads.
1. Um ein neues leeres Projekt zu erstellen, wählen Sie **Neues Projekt erstellen** aus den **Schnellstart**&#x200B;Links aus.
   ![Schnellstart-Links](assets/conf-ss-quick-start.png) {width="550" align="left"}
   *Neues Projekt erstellen.*

1. Wählen **API hinzufügen** auf dem Bildschirm **Projekte** aus.  Der **„API hinzufügen** wird angezeigt. Auf diesem Bildschirm werden alle verfügbaren APIs, Ereignisse und Services für Adobe-Produkte und -Technologien angezeigt, mit denen Sie Anwendungen entwickeln können.

1. Wählen Sie die **I/O Management API** aus, um sie zu Ihrem Projekt hinzuzufügen.
   ![IO-Management-API](assets/confi-ss-io-management.png)
   *Fügen Sie Ihrem Projekt die I/O-Management-API hinzu.*

1. Erstellen Sie eine neue **OAuth-Berechtigung** und speichern Sie sie.
   ![OAuth-Berechtigungskachel in API konfigurieren](assets/conf-ss-OAuth-credential.png) {width="3000" align="left"}
   *Konfigurieren von OAuth-Anmeldeinformationen für Ihre API.*

1. Wählen Sie auf **Registerkarte** die Option **OAuth-Server zu Server** und wählen Sie dann die neu erstellten Anmeldeinformationen aus.

1. Wählen Sie den **OAuth Server-zu-Server**-Link aus, um die Details der Anmeldeinformationen Ihres Projekts anzuzeigen.

   ![Verbundene Anmeldedaten](assets/conf-ss-connected-credentials.png) {width="800" align="left"}

   *Stellen Sie eine Verbindung zum Projekt her, um die Details der Berechtigung anzuzeigen.*

1. Kehren Sie zur Registerkarte **Projekte** zurück und wählen Sie **Projektübersicht** auf der linken Seite aus.

   <img src="assets/project-overview.png" alt="Projektübersicht" width="500">

   *Erste Schritte mit dem neuen Projekt.*

1. Klicken Sie oben auf **Schaltfläche** Herunterladen“, um die JSON-Datei des Services herunterzuladen.

   <img src="assets/download-json.png" alt="JSON herunterladen" width="500">

   *JSON-Service-Details herunterladen.*

Sie haben die OAuth-Authentifizierungsdetails konfiguriert und die JSON-Service-Details heruntergeladen. Halten Sie diese Datei bereit, da sie im nächsten Abschnitt benötigt wird.

### Hinzufügen der IMS-Konfiguration zur Umgebung

Führen Sie die folgenden Schritte aus, um die IMS-Konfiguration zur Umgebung hinzuzufügen:

1. Öffnen Sie den Experience Manager und wählen Sie Ihr Programm aus, das die zu konfigurierende Umgebung enthält.
1. Wechseln Sie zur Registerkarte **Umgebungen**.
1. Wählen Sie den Umgebungsnamen aus, den Sie konfigurieren möchten. Dadurch sollten Sie zur Seite **Umgebungsinformationen** gelangen.
1. Wechseln Sie zur Registerkarte **Konfiguration** .
1. Aktualisieren Sie das JSON-Feld SERVICE_ACCOUNT_DETAILS . Stellen Sie sicher, dass Sie denselben Namen und dieselbe Konfiguration wie im folgenden Screenshot verwenden.

![Konfiguration des IMS-Dienstkontos](assets/ims-service-account-config.png){width="800" align="left"}


*Fügen Sie die Konfigurationsdetails der Umgebung hinzu.*




Nachdem Sie die IMS-Konfiguration zur Umgebung hinzugefügt haben, führen Sie die folgenden Schritte aus, um diese Eigenschaften mithilfe von OSGi mit AEM Guides zu verknüpfen:

1. Fügen Sie in Ihrem Cloud Manager-Git-Projekt-Code die folgenden beiden Dateien hinzu (für den Dateiinhalt, Ansicht [Anhang](#appendix)).

   * `com.adobe.aem.guides.eventing.ImsConfiguratorService.cfg.json`

1. Stellen Sie sicher, dass die neu hinzugefügten Dateien von Ihrem `filter.xml` abgedeckt werden.
1. Übertragen Sie Ihre Git-Änderungen und übertragen Sie sie.
1. Führen Sie die Pipeline aus, um die Änderungen auf die Umgebung anzuwenden.

Sobald dies geschehen ist, sollten Sie in der Lage sein, die Funktion **Intelligente Hilfe** zu verwenden.



## Anhang {#appendix}

**Datei**:
`com.adobe.aem.guides.eventing.ImsConfiguratorService.cfg.json`

**Inhalt**:

```
{
 "service.account.details": "$[secret:SERVICE_ACCOUNT_DETAILS]",
}
```


Nach der Konfiguration wird das Symbol **Smart** Hilfe![Smart](assets/smart-help-icon.svg) im rechten Bereich des Web-Editors angezeigt. Wählen Sie das Symbol aus, um das Bedienfeld **Smart-Hilfe** anzuzeigen.
Weitere Informationen finden Sie im Abschnitt [KI-gestützte Smart-Hilfe für die Suche ](../user-guide/ai-based-smart-help.md) Inhalten“ im Experience Manager-Benutzerhandbuch.
