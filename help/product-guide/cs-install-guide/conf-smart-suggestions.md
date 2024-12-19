---
title: Konfigurieren der Smart-Vorschläge für das Authoring
description: Erfahren Sie, wie Sie die intelligenten Vorschläge für das Authoring konfigurieren
exl-id: a595ca1f-0123-40d3-a79c-a066bc6517b4
source-git-commit: d3e0c475ebd50a2664ea45c293d34b3a10772633
workflow-type: tm+mt
source-wordcount: '745'
ht-degree: 1%

---

# Konfigurieren der KI-gestützten intelligenten Vorschläge für das Authoring

Als Administrator können Sie die Funktion für intelligente Vorschläge für Autoren konfigurieren. Der Smart Suggestion-Service wird durch die authentifizierungsbasierte Adobe IMS-Authentifizierung gesichert. Integrieren Sie Ihre Umgebung mit sicheren Token-basierten Authentifizierungs-Workflows von Adobe und verwenden Sie die neue Funktion für intelligente Vorschläge . Mit der folgenden Konfiguration können Sie die Registerkarte **KI-Konfiguration** zum Ordnerprofil hinzufügen. Nach dem Hinzufügen können Sie die Funktion für intelligente Vorschläge im Web-Editor verwenden.

## Erstellen von IMS-Konfigurationen in Adobe Developer Console

Führen Sie die folgenden Schritte aus, um IMS-Konfigurationen in Adobe Developer Console zu erstellen:

>[!NOTE]
>
>Wenn Sie bereits ein OAuth-Projekt erstellt haben, um die auf Microservices basierende Veröffentlichung zu konfigurieren, können Sie die folgenden Schritte überspringen, um das Projekt zu erstellen.

1. [Adobe Developer Console starten](https://developer.adobe.com/console).
1. Nach erfolgreicher Anmeldung bei Developer Console wird der Bildschirm &quot;**&quot;**. Auf dem **Startseite**-Bildschirm finden Sie mühelos Informationen und Schnelllinks, einschließlich der oberen Navigationslinks zu Projekten und Downloads.
1. Um ein neues leeres Projekt zu erstellen, wählen Sie **Neues Projekt erstellen** aus den **Schnellstart**Links aus.
   ![Schnellstart-Links](assets/conf-ss-quick-start.png) {width="550" align="left"}
   *Neues Projekt erstellen.*

1. Wählen **API hinzufügen** auf dem Bildschirm **Projekte** aus.  Der **„API hinzufügen** wird angezeigt. Auf diesem Bildschirm werden alle verfügbaren APIs, Ereignisse und Services für Adobe-Produkte und -Technologien angezeigt, mit denen Sie Anwendungen entwickeln können.

1. Wählen Sie die **I/O Management API** aus, um sie zu Ihrem Projekt hinzuzufügen.
   ![IO-Management-API](assets/confi-ss-io-management.png)
   *Fügen Sie Ihrem Projekt die I/O-Management-API hinzu.*

1. Erstellen Sie eine neue **OAuth-Berechtigung** und speichern Sie sie.

   ![OAuth-Berechtigungskachel in der API konfigurieren](assets/conf-ss-OAuth-credential.png)

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

1. Öffnen Sie den Experience Manager und wählen Sie dann Ihr Programm aus, das die Umgebung enthält, die Sie konfigurieren möchten.
1. Wechseln Sie zur Registerkarte **Umgebungen**.
1. Wählen Sie den Namen der Umgebung aus, die Sie konfigurieren möchten. Dadurch sollten Sie zur Seite **Umgebungsinformationen** gelangen.
1. Wechseln Sie zur Registerkarte **Konfiguration** .
1. Aktualisieren Sie das JSON-Feld SERVICE_ACCOUNT_DETAILS . Stellen Sie sicher, dass Sie denselben Namen und dieselbe Konfiguration wie im folgenden Screenshot verwenden.

![Konfiguration des IMS-Dienstkontos](assets/ims-service-account-config.png){width="800" align="left"}


*Fügen Sie die Konfigurationsdetails der Umgebung hinzu.*




Nachdem Sie die IMS-Konfiguration zur Umgebung hinzugefügt haben, führen Sie die folgenden Schritte aus, um diese Eigenschaften mithilfe von OSGi mit AEM Guides zu verknüpfen:

1. Fügen Sie in Ihrem Cloud Manager-Git-Projekt-Code die folgenden beiden Dateien hinzu (für den Dateiinhalt, Ansicht [Anhang](#appendix)).

   * `com.adobe.aem.guides.eventing.ImsConfiguratorService.cfg.json`
   * `com.adobe.fmdita.smartsuggest.service.SmartSuggestConfigurationConsumer.cfg.json`
1. Stellen Sie sicher, dass die neu hinzugefügten Dateien von Ihrem `filter.xml` abgedeckt werden.
1. Übertragen Sie Ihre Git-Änderungen und übertragen Sie sie.
1. Führen Sie die Pipeline aus, um die Änderungen auf die Umgebung anzuwenden.

Sobald dies geschehen ist, sollten Sie die Funktion für intelligente Vorschläge verwenden können.



## Anhang {#appendix}

**Datei**:
`com.adobe.aem.guides.eventing.ImsConfiguratorService.cfg.json`

**Inhalt**:

```
{
 "service.account.details": "$[secret:SERVICE_ACCOUNT_DETAILS]",
}
```

**Datei**: `com.adobe.fmdita.smartsuggest.service.SmartSuggestConfigurationConsumer.cfg.json`

**Inhalt**:

```
{
  "smart.suggestion.flag":true,
  "conref.inline.threshold":0.6,
  "conref.block.threshold":0.7,
  "emerald.url":"https://adobeioruntime.net/apis/543112-smartsuggest/emerald/v1",
  "instance.type":"prod"
}
```

## Konfigurationsdetails für Smart-Vorschläge

| Schlüssel | Beschreibung | Zulässige Werte | Standardwert |
|---|---|---|---|
| smart.suggestion.flag | Steuert, ob intelligente Vorschläge aktiviert sind oder nicht | true/false | false |
| conref.inline.threshold | Schwellenwert, der die Präzision/den Abruf von Vorschlägen steuert, die für das Tag abgerufen werden, das der Benutzer derzeit eingibt. | Beliebiger Wert von -1,0 bis 1,0. | 0,6 |
| conref.block.threshold | Schwellenwert, der die Präzision/den Abruf von Vorschlägen steuert, die für Tags in der gesamten Datei abgerufen werden. | Beliebiger Wert von -1,0 bis 1,0. | 0,7 |
| emerald.url | Endpunkt für die Emerald-Vektor-Datenbank | [https://adobeioruntime.net/apis/543112-smartsuggest/emerald/v1](https://adobeioruntime.net/apis/543112-smartsuggest/emerald/v1) | [https://adobeioruntime.net/apis/543112-smartsuggest/emerald/v1](https://adobeioruntime.net/apis/543112-smartsuggest/emerald/v1) |
| instance.type | Typ der AEM-Instanz. Stellen Sie sicher, dass dies für jede AEM-Instanz, für die die Smart-Vorschläge konfiguriert sind, eindeutig ist. Ein Anwendungsfall bestünde darin, die Funktion in der Staging-Umgebung mit „instance.type“ = „stage“ zu testen, während die Funktion gleichzeitig auch in „prod“ konfiguriert ist. | Jeder eindeutige Schlüssel, der die Umgebung identifiziert. Nur *alphanumerische* Werte sind zulässig. „dev“/„stage“/„prod“/„test1“/„stage2“ | „prod“ |

Nach der Konfiguration wird das Symbol für intelligente Vorschläge im rechten Bedienfeld des Web-Editors angezeigt. Sie können die Liste der intelligenten Vorschläge anzeigen, wenn Sie Ihre Themen bearbeiten. Weitere Informationen finden Sie [ Abschnitt „KI-basierte Smart-](../user-guide/authoring-ai-based-smart-suggestions.md) für das Authoring“ im Experience Manager-Benutzerhandbuch.
