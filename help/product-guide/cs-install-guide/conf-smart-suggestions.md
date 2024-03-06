---
title: Konfigurieren der intelligenten Vorschläge für das Authoring
description: Erfahren Sie, wie Sie die intelligenten Vorschläge für das Authoring konfigurieren
source-git-commit: 1cdad275651b78d794ebc3f4ad9ead266ebeb0bd
workflow-type: tm+mt
source-wordcount: '689'
ht-degree: 1%

---

# KI-gestützte intelligente Vorschläge für das Authoring konfigurieren

Als Administrator können Sie die Funktion Smart Suggestions für Autoren konfigurieren. Der intelligente Empfehlungsdienst wird durch die auth-basierte Authentifizierung von Adobe IMS gesichert. Integrieren Sie Ihre Umgebung in die sicheren Token-basierten Authentifizierungs-Workflows von Adobe und beginnen Sie mit der Verwendung der neuen Funktion für intelligente Vorschläge. Die folgende Konfiguration hilft Ihnen beim Hinzufügen der **AI-Konfiguration** zum Ordnerprofil. Nach dem Hinzufügen können Sie die Funktion für intelligente Vorschläge im Web-Editor verwenden.

## Erstellen von IMS-Konfigurationen in der Adobe Developer-Konsole

Führen Sie die folgenden Schritte aus, um IMS-Konfigurationen in der Adobe Developer Console zu erstellen:
1. Launch [Adobe Developer-Konsole](https://developer.adobe.com/console).
1. Nach erfolgreicher Anmeldung bei der Developer Console sehen Sie die **Startseite** angezeigt. Die **Startseite** auf dem Sie einfach Informationen und schnelle Links finden können, einschließlich der Links zur oberen Navigation zu Projekten und Downloads.
1. Um ein neues leeres Projekt zu erstellen, wählen Sie  **Neues Projekt erstellen** aus dem  **Schnellstart** Links.
   ![Schnellstartlinks](assets/conf-ss-quick-start.png) {width="550" align="left"}
   *Erstellen Sie ein neues Projekt.*

1. Auswählen  **API hinzufügen**  aus dem  **Projekte** angezeigt.  Die **API hinzufügen** angezeigt. Auf diesem Bildschirm werden alle verfügbaren APIs, Ereignisse und Dienste für Adobe-Produkte und -Technologien angezeigt, mit denen Sie Anwendungen entwickeln können.

1. Wählen Sie die **I/O-Management-API** , um es zu Ihrem Projekt hinzuzufügen.
   ![IO-Management-API](assets/confi-ss-io-management.png)
   *Fügen Sie Ihrem Projekt die I/O-Management-API hinzu.*

1. Erstellen Sie eine neue **OAuth-Berechtigung** und speichern Sie es.
   ![OAuth-Berechtigungskachel in &quot;API konfigurieren&quot;](assets/conf-ss-OAuth-credential.png) {width="3000" align="left"}
   *Konfigurieren Sie OAuth-Anmeldedaten für Ihre API.*

1. Im  **Projekte** auswählen **OAuth Server to Server** und wählen Sie dann die neu erstellten Anmeldedaten aus.

1. Wählen Sie die **OAuth Server-zu-Server** -Link, um die Anmeldeinformationen Ihres Projekts anzuzeigen.

   ![Anmeldedaten](assets/conf-ss-connected-credentials.png) {width="800" align="left"}

   *Stellen Sie eine Verbindung zum Projekt her, um die Anmeldedaten anzuzeigen.*
1. Kopieren Sie die Schlüssel CLIENT_ID und CLIENT_SECRET .

Sie haben jetzt die OAuth-Authentifizierungsdetails konfiguriert. Halten Sie diese beiden Schlüssel bereit, da sie im nächsten Abschnitt benötigt werden.

### Hinzufügen der IMS-Konfiguration zur Umgebung

Führen Sie die folgenden Schritte aus, um der Umgebung die IMS-Konfiguration hinzuzufügen:

1. Öffnen Sie Experience Manager und wählen Sie dann das Programm aus, das die Umgebung enthält, die Sie konfigurieren möchten.
1. Wechseln Sie zu **Umgebungen** Registerkarte.
1. Wählen Sie den Umgebungsnamen aus, den Sie konfigurieren möchten. Dies sollte Sie zur Seite &quot;Umgebungsinformationen&quot;führen.
1. Wechseln Sie zu **Konfiguration** Registerkarte.
1. Fügen Sie die Schlüssel CLIENT_ID und CLIENT_SECRET hinzu, wie im folgenden Screenshot gezeigt. Stellen Sie sicher, dass Sie dieselben Namen und Konfigurationen wie unten hervorgehoben verwenden.
   ![Umgebungskonfiguration](assets/conf-ss-environment.png) {width="800" align="left"}
   *Fügen Sie die Details zur Umgebungskonfiguration hinzu.*




Nachdem Sie die IMS-Konfiguration zur Umgebung hinzugefügt haben, führen Sie die folgenden Schritte aus, um diese Eigenschaften mit OSGi mit AEM Guides zu verknüpfen:

1. Fügen Sie im Git-Projektcode des Cloud Manager-Cloud-Managers die folgenden beiden Dateien hinzu (für Dateiinhalte, zeigen Sie [Anhang](#appendix)).

   * `com.adobe.fmdita.ims.service.ImsOauthUserAccountHeadersImpl.cfg.json`
   * `com.adobe.fmdita.smartsuggest.service.SmartSuggestConfigurationConsumer.cfg.json`
1. Stellen Sie sicher, dass die neu hinzugefügten Dateien von Ihrem `filter.xml`.
1. Übernehmen Sie Ihre Git-Änderungen und übertragen Sie sie.
1. Führen Sie die Pipeline aus, um die Änderungen auf die Umgebung anzuwenden.

Danach sollten Sie die Funktion für intelligente Vorschläge verwenden können.



## Anhang {#appendix}

**Datei**:
`com.adobe.fmdita.ims.service.ImsOauthUserAccountHeadersImpl.cfg.json`

**Inhalt**:

```
{
  "client.id": "$[secret:CLIENT_ID]",
  "client.secret": "$[secret:CLIENT_SECRET]",
  "ims.url": "https://ims-na1.adobelogin.com"
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

## Konfigurationsdetails für intelligente Vorschläge

| Schlüssel | Beschreibung | Zulässige Werte | Standardwert |
|---|---|---|---|
| smart.suggestion.flag | Steuert, ob intelligente Vorschläge aktiviert sind oder nicht | true/false | Falsch |
| conref.inline.threshold | Schwellenwert, der die Genauigkeit/den Rückruf von Vorschlägen steuert, die für das Tag abgerufen werden, in das der Benutzer derzeit eingibt. | Jeder Wert zwischen -1,0 und 1,0. | 0,6 |
| conref.block.threshold | Schwellenwert, der die Genauigkeit/den Rückruf von Vorschlägen steuert, die für Tags in der gesamten Datei abgerufen werden. | Jeder Wert zwischen -1,0 und 1,0. | 0,7 |
| emerald.url | Endpunkt für die Emerald Vektor-Datenbank | [https://adobeioruntime.net/apis/543112-smartsuggest/emerald/v1](https://adobeioruntime.net/apis/543112-smartsuggest/emerald/v1) | [https://adobeioruntime.net/apis/543112-smartsuggest/emerald/v1](https://adobeioruntime.net/apis/543112-smartsuggest/emerald/v1) |
| instance.type | Typ der AEM Instanz. Stellen Sie sicher, dass dies für jede AEM Instanz eindeutig ist, für die die intelligenten Vorschläge konfiguriert sind. Ein Anwendungsfall bestünde darin, die Funktion in der Staging-Umgebung mit &quot;instance.type&quot; = &quot;stage&quot;zu testen, während die Funktion gleichzeitig auch für &quot;prod&quot;konfiguriert ist. | Jeder eindeutige Schlüssel, der die Umgebung identifiziert. Nur *alphanumerisch* -Werte zulässig sind. &quot;dev&quot;/&quot;stage&quot;/&quot;prod&quot;/&quot;test1&quot;/&quot;stage2&quot; | &quot;prod&quot; |

Nach der Konfiguration wird das Symbol für intelligente Vorschläge im rechten Bereich des Web-Editors angezeigt. Sie können die Liste der intelligenten Vorschläge anzeigen, wenn Sie Ihre Themen bearbeiten. Weitere Informationen finden Sie unter [KI-basierte intelligente Vorschläge für das Authoring](../user-guide/authoring-ai-based-smart-suggestions.md) im Experience Manager-Benutzerhandbuch.
