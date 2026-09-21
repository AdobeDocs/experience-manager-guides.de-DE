---
title: Verwenden von MCP mit Adobe Experience Manager Guides
description: Erfahren Sie, wie Sie das Model Context Protocol (MCP) mit AEM Guides verwenden, um über einen KI-Assistenten mit Themen, Karten, Baselines und Berichten zu arbeiten
feature: Authoring
role: User
source-git-commit: 864884f26389d256b0e054e3c0b7400b89f6d6ce
workflow-type: tm+mt
source-wordcount: '814'
ht-degree: 0%
---

# Verwenden des Adobe Experience Manager Guides MCP-Servers

Das Model Context Protocol (MCP) ist eine Standardmethode für KI-Assistenten, um eine Verbindung zu externen Tools und Daten herzustellen, anstatt den Kontext zu wechseln, um diese Tools selbst zu bedienen.

Der Adobe Experience Manager Guides MCP-Server bringt dies zu Experience Manager Guides. Dadurch kann ein MCP-aktivierter KI-Assistent wie Claude Anthropic unter eigenen AEM-Berechtigungen eine Verbindung zu Ihrer Experience Manager Guides-Umgebung herstellen und in Ihrem Namen handeln. Sobald die Verbindung hergestellt ist, können Sie mit Ihren Karten, Themen, Grundlinien und Berichten auf Experience Manager Guides as a Cloud Service arbeiten.

In diesem Artikel wird erläutert, warum MCP für Experience Manager Guides nützlich ist, was der MCP-Server abdeckt, mit welchen Anwendungen er arbeitet und wie er verwendet wird.

## Warum MCP für Experience Manager Guides sinnvoll ist

Dokumentations-Teams verbringen oft viel Zeit mit sich wiederholenden, navigationslastigen Aufgaben, wie z. B. dem Suchen von Themen in einer großen Karte, dem Überprüfen des Dokumentstatus, dem Nachverfolgen fehlerhafter Links, dem Erstellen von Grundlinien für eine Version oder dem Exportieren von Berichten. Mit dem Experience Manager Guides MCP-Server können Sie einen KI-Assistenten bitten, diese direkt zu bearbeiten, ohne zur Experience Manager Guides-Benutzeroberfläche zu wechseln.

Beispiel:

- Anstatt eine Karte zu öffnen und den Status jedes Themas einzeln zu überprüfen, bitten Sie den Assistenten, die Themen und ihre Status aufzulisten.
- Anstatt einen Bericht mit fehlerhaften Links manuell zu starten und auf der Experience Manager Guides-Benutzeroberfläche zu warten, bitten Sie den Assistenten, den Bericht auszuführen und Ihnen mitzuteilen, wann er abgeschlossen ist.
- Anstatt zum Bildschirm „Grundlinie“ zu navigieren, bitten Sie den Assistenten, eine Grundlinie für eine bestimmte Karte zu erstellen.

## MCP-Server von Experience Manager Guides bereitgestellt

Experience Manager Guides stellt MCP-Funktionen für die Arbeit mit Experience Manager Guides-Inhalten und zugehörigen Workflows bereit. Abhängig von Ihren AEM-Berechtigungen bietet der MCP-Server Zugriff auf die folgenden Funktionen:

* **Themen und Karten**: Arbeiten Sie mit Themen und Karten über den gesamten Inhaltslebenszyklus, von der Erstellung und Anzeige von Inhalten bis hin zur Aktualisierung, Versionierung, Sperrung und Löschung.
* **Baselines**: Arbeiten Sie mit Baselines, indem Sie sie erstellen, auflisten, exportieren, duplizieren, neu erstellen und beschriften.
  >[!NOTE]
  >
  > Sowohl für Cloud Service- als auch für On-Premise-Umgebungen sind Baseline-Funktionen nur verfügbar, wenn [neue Baseline](../user-guide/web-editor-baseline-v2.md) aktiviert ist.
* **Berichte**: Gewinnen Sie Einblicke in Ihre Inhalte, indem Sie auf Themenlisten und Metadaten zugreifen, fehlerhafte Links identifizieren und die Multimedia-Nutzung überprüfen.
* **System**: Verstehen Sie den Status Ihres Systems, indem Sie Paketversionen, den Paketzustand und die Umgebungsdiagnose überprüfen.

Wenn Sie nicht über die Berechtigung zum Ausführen einer Aktion in AEM verfügen, können Sie dieselbe Aktion nicht über MCP durchführen.

Die exakten verfügbaren Tools können sich im Laufe der Zeit ändern. Anstatt sich auf eine feste Liste zu verlassen, bitten Sie Ihren Assistenten, Ihnen zu zeigen, was verfügbar ist:

`List all Experience Manager Guides tools available and describe what they do.`


## Unterstützte Anwendungen

Der Experience Manager Guides MCP-Server ist ein MCP-Remoteserver, der eine Verbindung zu kompatiblen MCP-Clients herstellen kann. Verbinden Sie je nach Umgebung Ihren MCP-Client und authentifizieren Sie sich beim Experience Manager Guides MCP-Server. Weitere Informationen finden Sie unter [Einrichten des Experience Manager Guides MCP-Servers](./configure-aem-guides-mcp.md).

## Verwenden des Experience Manager Guides MCP-Servers

Beschreiben Sie nach der Verbindung in einfacher Sprache, was Sie möchten. Der Assistent wählt das entsprechende Tool aus und gibt die entsprechenden Parameter ein, z. B. den Zuordnungspfad oder den Namen der Baseline.

>[!IMPORTANT]
>
> Anfragen, die mehrere Schritte umfassen oder bis zur Fertigstellung Zeit benötigen, z. B. Exporte, Baseline-Builds und Massenaktualisierungen, funktionieren am besten mit einem denkenden Modell. Diese werden im Hintergrund ausgeführt: Der Assistent startet den Auftrag und überprüft dann dessen Status, bis das Ergebnis oder ein Download-Link bereit ist.

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


