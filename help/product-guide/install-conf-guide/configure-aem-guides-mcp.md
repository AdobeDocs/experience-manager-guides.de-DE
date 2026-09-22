---
title: Einrichten von MCP für Adobe Experience Manager Guides
description: Erfahren Sie, wie Sie einen KI-Assistenten mit dem Experience Manager Guides MCP-Server für Cloud Service- und lokale Bereitstellungen verbinden
meta-feature: Authoring
meta-product: Experience Manager, Experience Manager Guides
meta-role: User
meta-type: Documentation
source-git-commit: 6841c373b75770e8691a2cac4d56aeb368b09480
workflow-type: tm+mt
source-wordcount: '1557'
ht-degree: 1%
---

# Einrichten des Experience Manager Guides MCP-Servers

Dieser Artikel behandelt die umgebungsspezifischen Details für die Verbindung mit dem Experience Manager Guides MCP-Server. Das Setup unterscheidet sich, je nachdem, ob Ihre Experience Manager Guides-Instanz as a Cloud Service oder lokal ausführt. Wählen Sie die Ihrer Umgebung entsprechende Registerkarte aus.

>[!BEGINTABS]

>[!TAB Cloud Service]

## MCP-Server-Endpunkt

Experience Manager Guides stellt seine MCP-Funktionen über einen einzigen HTTP-Endpunkt bereit.

| MCP-Server | Endpunkt | Beschreibung |
|---|---|---|
| **Experience Manager Guides** | `https://mcp.adobeaemcloud.com/adobe/mcp/guides` | Arbeiten mit Themen und Karten, [neuen Baselines](../user-guide/web-editor-baseline-v2.md) und Berichten in Experience Manager Guides. |

Um die aktuelle Toolliste für Ihre Umgebung zu erhalten, fragen Sie Ihren Assistenten:

```
List all Experience Manager Guides tools available from the author https://author-pXXXX-eXXXX.adobeaemcloud.com and describe what they do.
```

## Anfordern des Zugriffs für Ihre Organisation

Der Zugriff auf den Experience Manager Guides MCP-Server erfolgt **Opt-in pro Organisation**. Bevor sich jemand in Ihrer Organisation verbinden kann:

- Experience Manager Guides muss in Ihrer AEM as a Cloud Service-Umgebung aktiviert sein.
- Die IMS-Organisations-ID (Organisations-ID) Ihres Unternehmens muss vom Team Adobe Guides auf die Zulassungsliste gesetzt werden.

Um Zugriff zu erhalten, wenden Sie sich an Ihr Adobe Customer Success-Team.

## Einrichtung

Sie installieren keine lokalen Komponenten. Sie verweisen Ihren Client auf die Server-URL und authentifizieren sich über den Adobe IMS-Anmeldefluss.

### Claude Anthropica

Folgen Sie der offiziellen Anleitung: [Einrichten von Claude für AEM MCP](https://experienceleague.adobe.com/de/docs/experience-manager-cloud-service/content/ai-in-aem/mcp-support/chat-applications/setup-claude). Verwenden Sie beim Hinzufügen des benutzerdefinierten Connectors den Experience Manager Guides-Endpunkt:

```
https://mcp.adobeaemcloud.com/adobe/mcp/guides
```

### Cursor/Visual Studio Code

Fügen Sie den Server zu Ihrer MCP-Konfiguration hinzu. Fügen Sie für den Cursor Folgendes zu `.cursor/mcp.json` hinzu:

```json
{
  "mcpServers": {
    "aem-guides": {
      "url": "https://mcp.adobeaemcloud.com/adobe/mcp/guides"
    }
  }
}
```

Für Clients, die nur lokale (stdio) Server unterstützen, verbinden Sie den Remote-Endpunkt mit [`mcp-remote`](https://www.npmjs.com/package/mcp-remote):

```json
{
  "mcpServers": {
    "aem-guides": {
      "command": "npx",
      "args": ["-y", "mcp-remote", "https://mcp.adobeaemcloud.com/adobe/mcp/guides"]
    }
  }
}
```

>[!TAB On-Premise]

Sie können unterstützte KI-Clients mithilfe des Model Context Protocol (MCP) mit einer lokalen Experience Manager Guides-Instanz verbinden. Nachdem Sie die Verbindung hergestellt haben, kann der Client auf die Experience Manager Guides-Vorgänge zugreifen, die für Ihr AEM-Benutzerkonto verfügbar sind.

Alle Vorgänge werden mit &quot;**AEM-Identität und -Berechtigungen** ausgeführt. Der verbundene Client kann nur die Inhalte und Ressourcen anzeigen oder ändern, auf die Ihr AEM-Konto zugreifen darf.

Bei der Authentifizierung wird der OAuth 2.0-Autorisierungs-Code-Fluss mit dem Proof Key for Code Exchange (PKCE) verwendet. Sie authentifizieren sich bei AEM, wenn Sie zum ersten Mal eine Verbindung zu einem Client herstellen. Nach erfolgreicher Authentifizierung aktualisiert die Verbindung automatisch Zugriffstoken.

Sie können die folgenden Clients verbinden:

| Client | Verbindungsmethode | AEM-Instanzanforderungen |
| ------------------ | ----------------------------------------- | --------------------------------------------------------------------------------------------------- |
| **Claude Desktop** | Desktop-Erweiterung (`.mcpb`) | Unterstützt HTTP- und HTTPS-Endpunkte, einschließlich interner Hosts, auf die über das Unternehmensnetzwerk zugegriffen werden kann. |
| **ChatGPT (Web und Desktop)** | Benutzerdefinierter Connector | Erfordert einen öffentlich zugänglichen HTTPS-Endpunkt mit einem gültigen, öffentlich vertrauenswürdigen TLS-Zertifikat. |
| **Cursor** | MCP-Konfiguration in `~/.cursor/mcp.json` | Unterstützt HTTP- und HTTPS-Endpunkte, einschließlich interner Hosts, auf die über das Unternehmensnetzwerk zugegriffen werden kann. |

## Voraussetzungen

Wenden Sie sich an Ihren AEM-Administrator, um die folgende Konfiguration zu überprüfen, bevor Sie einen Client verbinden:

1. **Stellen Sie sicher, dass die MCP-Funktion bereitgestellt ist.**: Stellen Sie sicher, dass die MCP-Funktion auf Ihrer Experience Manager Guides-Instanz bereitgestellt und ausgeführt wird.

2. **Konfigurieren der Granite-Basis-URL.**: Suchen Sie im Konfigurations-Manager der AEM-Web-Konsole (`/system/console/configMgr`) die Konfiguration **Experience Manager Guides OAuth PKCE Token Wrapper** und überprüfen Sie, ob die Granite-Basis-URL konfiguriert ist. Wenn die Granite-Basis-URL nicht korrekt konfiguriert ist, kann der Client die Verbindung nicht herstellen.

3. **Konfigurieren Sie den Day CQ Link Externalizer.**: Suchen Sie im Konfigurations-Manager der AEM-Web-Konsole die Konfiguration **Day CQ Link Externalizer** und stellen Sie sicher, dass die externe Autoren-URL auf die richtige AEM-Autoreninstanz verweist. Die externe Autoren-URL wird während der OAuth-Erkennung verwendet. Eine falsche URL kann verhindern, dass der Client die Verbindung herstellt.

   Weitere Informationen finden Sie unter [Konfigurieren der MCP-Verbindungseinstellungen für AEM Guides On-Premise](./configure-aem-guides-mcp-on-prem.md)

4. **Abrufen der MCP-Server-URL.**: Die MCP-Server-URL verwendet das folgende Format:

   ```
   http(s)://<AEM-HOST>/bin/guides/v1/mcp/sse
   ```

   >[!NOTE]
   >
   > Verwenden Sie den vollständigen SSE-Endpunkt beim Konfigurieren eines Clients. Fügen Sie der URL keinen Schrägstrich hinzu.

   Beispiel:

   **Interne AEM-Autoreninstanz:**

   ```
   http://10.42.42.20:4502/bin/guides/v1/mcp/sse
   ```

   **Öffentliche AEM-Autoreninstanz:**

   ```
   https://author.example.com/bin/guides/v1/mcp/sse
   ```



5. **Überprüfen Sie Ihre AEM-Anmeldeinformationen und -Berechtigungen.**: Sie müssen über ein gültiges Konto für die AEM-Instanz verfügen. Verwenden Sie dieselben Anmeldeinformationen wie für die Anmeldung bei der Benutzeroberfläche von AEM. Die über MCP verfügbaren Vorgänge werden durch die diesem Konto zugewiesenen Berechtigungen bestimmt.

## Claude Desktop verbinden

Claude Desktop unterstützt Desktop-Erweiterungen (`.mcpb`). Die Experience Manager Guides MCP-Erweiterung packt die Verbindungskonfiguration, sodass Sie eine MCP-JSON-Konfiguration nicht manuell bearbeiten müssen.

1. Rufen Sie die [`aem-guides-mcp.mcpb`](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html?package=/content/software-distribution/en/details.html/content/dam/aem/public/aemdox/other-packages/guides-mcp/aem-guides-mcp.zip) Erweiterungsdatei ab.

2. Öffnen Sie **Claude Desktop** und navigieren Sie zu **Einstellungen > Erweiterungen**.

3. Installieren Sie `aem-guides-mcp.mcpb`, indem Sie auf die Datei doppelklicken oder sie in das Fenster „Erweiterungen“ ziehen.

   **Adobe Experience Manager Guides MCP** wird im Installationsdialogfeld angezeigt.

4. Wählen Sie **Installieren** aus.

5. Geben Sie im Feld **Experience Manager Guides MCP Server URL** den vollständigen SSE-Endpunkt für Ihre AEM-Instanz ein.

   Beispiel:

   ```
   http://<AEM-HOST>:4502/bin/guides/v1/mcp/sse
   ```

6. Wählen **Speichern** und stellen Sie sicher, dass die Erweiterung aktiviert ist.

## ChatGPT verbinden

Sie können den Experience Manager Guides MCP-Server als benutzerdefinierten Connector in ChatGPT konfigurieren.

>[!IMPORTANT]
>
> ChatGPT erfordert, dass der MCP-Server über einen **öffentlich zugänglichen HTTPS-Endpunkt mit einem gültigen, öffentlich vertrauenswürdigen TLS-Zertifikat) verfügbar**.
>
> HTTP-Endpunkte, `localhost`, private IP-Adressen und selbstsignierte Zertifikate werden nicht unterstützt. Die AEM-Instanz muss über einen HTTPS-Host verfügbar gemacht werden, z. B. einen Lastenausgleich, einen Reverse-Proxy oder eine mit TLS konfigurierte Dispatcher.
>
> Die in **Day CQ Link Externalizer** konfigurierte externe Autoren-URL muss ebenfalls auf die öffentliche HTTPS-Adresse verweisen. Andernfalls können die OAuth Discovery-Metadaten falsche Authentifizierungsendpunkte anzeigen und die Anmeldung verhindern.

1. Stellen Sie sicher, dass Ihr MCP-Server unter einer öffentlichen HTTPS-URL im folgenden Format verfügbar ist:

   ```
   https://<PUBLIC-AEM-HOST>/bin/guides/v1/mcp/sse
   ```

   Öffnen Sie den Endpunkt in einem Browser und stellen Sie sicher, dass Sie den Host ohne Zertifikatwarnung oder Verbindungsfehler erreichen können.

2. Öffnen Sie in ChatGPT **Einstellungen > Plug-ins**.

   >[!NOTE]
   >
   > Die Verfügbarkeit des Connectors hängt von Ihrem ChatGPT-Plan und der Arbeitsbereichskonfiguration ab. Möglicherweise muss die bzw. der Workspace-Admin benutzerdefinierte oder Entwickler-Connectoren aktivieren.

3. Wählen Sie die Option zum Hinzufügen oder Erstellen eines Plug-ins aus.

4. Angeben der Connector-Details:

   * **Name:** Geben Sie `Experience Manager Guides` oder einen anderen beschreibenden Namen ein.
   * **MCP-Server-URL:** Geben Sie den öffentlichen HTTPS-SSE-Endpunkt ein.
   * **Authentifizierung:** Wählen Sie **OAuth** aus.

   Sie müssen keine OAuth-Client-ID oder keinen geheimen Client-Schlüssel angeben. Der MCP-Server unterstützt die automatische Clientregistrierung.

5. Erstellen Sie den Connector.

## Cursor verbinden

Konfigurieren Sie den Experience Manager Guides-MCP-Server in Cursor, indem Sie die Serverdetails zur MCP-Konfiguration hinzufügen.

1. Navigieren Sie in Cursor zu **Anpassen > MCPs > Neu**.

   Der Cursor öffnet die `~/.cursor/mcp.json` Konfigurationsdatei.

2. Fügen Sie die Experience Manager Guides MCP-Server-Konfiguration hinzu.

   Beispiel:

   ```json
   {
     "mcpServers": {
       "aem-guides": {
         "url": "http://10.42.34.176:4502/bin/guides/v1/mcp/sse",
         "type": "http"
       }
     }
   }
   ```

3. Ersetzen Sie die Beispiel-URL durch den MCP SSE-Endpunkt für Ihre AEM-Instanz.

4. Speichern Sie die Konfiguration.

5. Aktivieren Sie den konfigurierten MCP-Server.

>[!ENDTABS]

## Experience Manager Guides authentifizieren und verwenden

Nachdem Sie die MCP-Verbindung in Ihrem Client konfiguriert haben, authentifizieren Sie sich mit Ihrem AEM-Konto.

1. Starten Sie den Authentifizierungsprozess von Ihrem Client aus.

   * **Claude Desktop:** Der Authentifizierungsfluss beginnt, wenn Claude zum ersten Mal versucht, die Experience Manager Guides-Verbindung zu verwenden.
   * **ChatGPT:** Die Authentifizierung beginnt, nachdem Sie den Experience Manager Guides-Connector erstellt und verbunden haben.
   * **Cursor:** Aktivieren Sie den konfigurierten MCP-Server und wählen Sie **Authentifizieren** aus.

2. Wenn die AEM-Anmeldeseite in Ihrem Browser geöffnet wird, melden Sie sich mit Ihren AEM-Anmeldeinformationen an.

3. Genehmigen Sie die Zugriffsanfrage, wenn Sie dazu aufgefordert werden.

4. Kehren Sie nach Abschluss der Authentifizierung zu Ihrem Client zurück.

Sie können jetzt die für Ihr Konto verfügbaren Experience Manager Guides-Vorgänge verwenden. Probieren Sie zum Beispiel Eingabeaufforderungen wie:

```
List the available Experience Manager Guides operations.
```

```
Get the topic list for my map in Experience Manager Guides.
```

```
Show me the broken-link report for my map.
```

>[!NOTE]
>
> Die über MCP verfügbaren Vorgänge und Inhalte werden durch die Berechtigungen des AEM-Kontos bestimmt, das zur Authentifizierung verwendet wird. Die MCP-Verbindung bietet keine zusätzlichen AEM-Berechtigungen.

Nach erfolgreicher Authentifizierung aktualisiert der Client die Authentifizierungs-Token automatisch. Normalerweise müssen Sie sich nicht erneut anmelden, es sei denn, die Sitzung läuft ab oder der Zugriff wird widerrufen.

## Fehlerbehebung bei Verbindungsproblemen

Verwenden Sie die folgenden Informationen, um häufige Verbindungs- und Authentifizierungsprobleme zu beheben.

| Client | Problem | Mögliche Ursache und Lösung |
| -------------- | -------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Claude Desktop | Die Erweiterung kann nicht installiert oder deaktiviert werden. | Ihre Version von Claude Desktop unterstützt die Erweiterung möglicherweise nicht. Claude Desktop aktualisieren und erneut versuchen. |
| Claude Desktop | Der Browser wird nicht zur Authentifizierung geöffnet oder die Verbindung wird nicht abgeschlossen. | Überprüfen Sie die MCP-Server-URL. Sie muss mit `/bin/guides/v1/mcp/sse` enden und sollte keinen abschließenden Schrägstrich enthalten. Stellen Sie außerdem sicher, dass der Zugriff auf die AEM-Instanz über Ihren Computer möglich ist. |
| ChatGPT | ChatGPT kann den MCP-Server nicht erreichen oder erlaubt Ihnen nicht, den Connector hinzuzufügen. | Stellen Sie sicher, dass der Endpunkt über HTTPS öffentlich zugänglich ist. HTTP-Endpunkte, `localhost`, private IP-Adressen und private Netzwerkendpunkte werden nicht unterstützt. |
| ChatGPT | Ein Zertifikat- oder Sicherheitsfehler wird angezeigt. | Vergewissern Sie sich, dass der Server ein gültiges, nicht abgelaufenes Zertifikat verwendet, das von einer öffentlich vertrauenswürdigen Zertifizierungsstelle ausgestellt wurde. Selbstsignierte Zertifikate werden nicht unterstützt. |
| ChatGPT | Die Authentifizierung leitet zu einem falschen Host um oder schlägt während der Erkennung fehl. | Stellen Sie sicher, dass die externe Autoren-URL in **Day CQ Link Externalizer** auf die öffentliche HTTPS AEM-Autorenadresse verweist. |
| Alle Clients | Die Registrierung schlägt während der Authentifizierung fehl. | Überprüfen Sie die Server-seitige OAuth-Registrierungskonfiguration mit Ihrem AEM-Administrator. |
| Alle Clients | Die Authentifizierung schlägt fehl oder wird nicht abgeschlossen. | Überprüfen Sie die Granite-Basis-URL, die Konfiguration von Day CQ Link Externalizer, die MCP-Server-URL und die Verbindung zur AEM-Instanz. |
| Alle Clients | Die Verbindung ist erfolgreich, aber Experience Manager Guides-Vorgänge oder -Ergebnisse sind nicht verfügbar. | Überprüfen Sie, ob das authentifizierte AEM-Konto über die erforderlichen Experience Manager Guides-Berechtigungen verfügt und ob der angeforderte Vorgang für das Konto verfügbar ist. |
| Alle Clients | Der Client fordert die Authentifizierung an, nachdem die Verbindung zuvor funktioniert hat. | Die Authentifizierungssitzung ist möglicherweise abgelaufen oder der Zugriff wurde widerrufen. Erneute Authentifizierung bei AEM. |



