---
title: Verwenden von MCP mit Adobe Experience Manager Guides
description: Erfahren Sie, wie Sie das Model Context Protocol (MCP) mit AEM Guides verwenden, um über einen KI-Assistenten mit Themen, Karten, Baselines und Berichten zu arbeiten
feature: Authoring, Publishing
role: User
source-git-commit: c724946a3426e28a1270ba01cdf2646bbf5f2a0d
workflow-type: tm+mt
source-wordcount: '974'
ht-degree: 0%

---


# Verwenden des Adobe Experience Manager Guides MCP-Servers

Das Model Context Protocol (MCP) ist eine Standardmethode für KI-Assistenten, um eine Verbindung zu externen Tools und Daten herzustellen, anstatt den Kontext zu wechseln, um diese Tools selbst zu bedienen.

Der Adobe Experience Manager Guides MCP-Server bringt dies zu Experience Manager Guides. Dadurch kann ein MCP-aktivierter KI-Assistent wie Claude Anthropic unter eigenen AEM-Berechtigungen eine Verbindung zu Ihrer Experience Manager Guides-Umgebung herstellen und in Ihrem Namen handeln. Sobald die Verbindung hergestellt ist, können Sie mit Ihren Karten, Themen, Grundlinien und Berichten auf Experience Manager Guides as a Cloud Service arbeiten.

In diesem Artikel wird erläutert, warum MCP für Experience Manager Guides nützlich ist, was der MCP-Server abdeckt, mit welchen Anwendungen er arbeitet, wie er eingerichtet wird und wie er verwendet wird.

## Warum MCP für Experience Manager Guides sinnvoll ist

Dokumentations-Teams verbringen oft viel Zeit mit sich wiederholenden, navigationslastigen Aufgaben, wie z. B. dem Suchen von Themen in einer großen Karte, dem Überprüfen des Dokumentstatus, dem Nachverfolgen fehlerhafter Links, dem Erstellen von Grundlinien für eine Version oder dem Exportieren von Berichten. Mit dem Experience Manager Guides MCP-Server können Sie einen KI-Assistenten bitten, diese direkt zu bearbeiten, ohne zur Experience Manager Guides-Benutzeroberfläche zu wechseln.

Beispiel:

- Anstatt eine Karte zu öffnen und den Status jedes Themas einzeln zu überprüfen, bitten Sie den Assistenten, die Themen und ihre Status aufzulisten.
- Anstatt einen Bericht mit fehlerhaften Links manuell zu starten und auf der Experience Manager Guides-Benutzeroberfläche zu warten, bitten Sie den Assistenten, den Bericht auszuführen und Ihnen mitzuteilen, wann er abgeschlossen ist.
- Anstatt zum Bildschirm „Grundlinie“ zu navigieren, bitten Sie den Assistenten, eine Grundlinie für eine bestimmte Karte zu erstellen.

## MCP-Server von Experience Manager Guides bereitgestellt

Experience Manager Guides stellt seine MCP-Funktionen über einen einzigen HTTP-Endpunkt bereit.

| MCP-Server | Endpunkt | Beschreibung |
| --- | --- | --- |
| **Experience Manager Guides** | `https://mcp.adobeaemcloud.com/adobe/mcp/guides` | Arbeiten mit Themen und Karten, Grundlinien und Berichten in Experience Manager Guides. |

Dieser eine Endpunkt deckt vier Bereiche ab:

- **Themen und Karten** - Erstellen, Lesen, Aktualisieren, Löschen, Versionieren und Sperren von Themen und Karten.
- **Baselines** - Erstellen, Auflisten, Exportieren, Duplizieren, Neuerstellen und Kennzeichnen von Baselines.
- **Berichte** - Themenlisten, Metadaten, fehlerhafte Links und Multimediennutzung.
- **System** - Paketversion, Paketzustand und Umgebungsdiagnose.

Die exakten verfügbaren Tools können sich im Laufe der Zeit ändern. Anstatt sich auf eine feste Liste zu verlassen, bitten Sie Ihren Assistenten, Ihnen zu zeigen, was verfügbar ist:

```
List all Experience Manager Guides tools available from the author https://author-pXXXX-eXXXX.adobeaemcloud.com and describe what they do.
```

## Anfordern des Zugriffs für Ihre Organisation

Der Zugriff auf den Experience Manager Guides MCP-Server erfolgt **Opt-in pro Organisation**. Bevor sich jemand in Ihrer Organisation verbinden kann:

- Experience Manager Guides muss in Ihrer AEM as a Cloud Service-Umgebung aktiviert sein.
- Die IMS-Organisations-ID (Organisations-ID) Ihres Unternehmens muss vom Team Adobe Guides auf die Zulassungsliste gesetzt werden.

Um Zugriff zu erhalten, wenden Sie sich an Ihr Adobe Customer Success-Team.

## Unterstützte Anwendungen

Der Experience Manager Guides MCP-Server ist ein **Remote**-Server. Es funktioniert mit jedem MCP-Client, der Remote-Server unterstützt, einschließlich:

### Chat-Anwendungen

- Anthropic Claude (Web und Desktop)

### Entwickler-Tools

- Mauszeiger
- Visual Studio Code
- Andere MCP-fähige IDEs

## Setup

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

## Authentifizierung

Der Experience Manager Guides MCP-Server verwendet **Adobe IMS** für die Authentifizierung.

- Bei der ersten Verbindung öffnet Ihr Client ein Browser-Anmeldefenster. Melden Sie sich mit Ihrer Adobe ID an, um die Verbindung abzuschließen.
- Nach der Anmeldung wird jede Aktion mit Ihren bestehenden AEM-Berechtigungen ausgeführt. Wenn Sie keine Berechtigung für eine Aktion in AEM haben, schlägt dieselbe Aktion über MCP fehl.

## Verwenden des Experience Manager Guides MCP-Servers

Beschreiben Sie nach der Verbindung in einfacher Sprache, was Sie möchten. Der Assistent wählt das entsprechende Tool aus und gibt die entsprechenden Parameter ein, z. B. den Zuordnungspfad oder den Namen der Baseline.

>[!IMPORTANT]
>
>Anfragen, die mehrere Schritte umfassen oder bis zur Fertigstellung Zeit benötigen, z. B. Exporte, Baseline-Builds und Massenaktualisierungen, funktionieren am besten mit einem denkenden Modell. Diese werden im Hintergrund ausgeführt: Der Assistent startet den Auftrag und überprüft dann dessen Status, bis das Ergebnis oder ein Download-Link bereit ist.

### Beispiel-Eingabeaufforderungen

Die folgenden Eingabeaufforderungen veranschaulichen typische Anfragen, von denen jede ein anderes Tool auslöst:

1. **Themenstatus in einer Zuordnung überprüfen**

   > Listen Sie alle Themen auf der Karte unter `/content/dam/docs/user-guide.ditamap` auf und zeigen Sie ihre Titel und Dokumentstatus an.

1. **Erstellen einer Baseline**

   > Erstellen Sie eine statische Grundlinie mit dem `/content/dam/docs/user-guide.ditamap` „Version 3.2“.

1. **Bericht ausführen**

   > Führen Sie den Bericht zu fehlerhaften Links für das Benutzerhandbuch aus und geben Sie mir den Download-Link, wenn er bereit ist.

## Verwaltung der Erwartungen

- **Ergebnis validieren** - Der Assistent kann Fehler machen, z. B. die falsche Karte oder das falsche Thema auswählen. Überprüfen Sie einen Bericht oder eine neue Baseline, bevor Sie ihn verwenden.
- **Mit der Zeit verbessert sich** - Wenn der Assistent besser wird, können Aufgaben, die heute einige Aufforderungen erfordern, eine Aufforderung später annehmen.
- **Sie führen den Aufruf weiterhin aus** - Der Assistent kann Ihnen den Status eines Themas mitteilen oder fehlerhafte Links auflisten. Die Entscheidung, ob Inhalte zur Veröffentlichung bereit sind, liegt jedoch weiterhin beim Prüfer oder Herausgeber.
- **Seien Sie vorsichtig bei der automatischen Genehmigung** - Einige MCP-Clients, einschließlich Claude, ermöglichen es Ihnen, Aktionen automatisch zu genehmigen, anstatt jede zu bestätigen. Dies ist für schreibgeschützte Aktionen akzeptabel, z. B. das Ausführen eines Berichts. Für Aktionen, die Inhalte erstellen, ändern oder sperren, bestätigen Sie jede Aktion, damit Sie sie überprüfen können, bevor sie wirksam wird.

Wenden Sie sich bei Fragen zu Experience Manager Guides MCP an Ihr Adobe Customer Success-Team.


