---
title: Konfigurieren der MCP-Verbindungseinstellungen für AEM Guides On-Premise
description: Erfahren Sie, wie Sie MCP-Verbindungseinstellungen für AEM Guides On-Premise konfigurieren.
meta-feature: Authoring
meta-product: Experience Manager, Experience Manager Guides
meta-role: Admin
meta-type: Documentation
source-git-commit: e234425f1e277990de25057971f3e2453c93360f
workflow-type: tm+mt
source-wordcount: '361'
ht-degree: 4%
---

# Konfigurieren der MCP-Verbindungseinstellungen für Experience Manager Guides (On-Premise)

KI-Tools wie Claude, Cursor und Codex können mithilfe des Model Context Protocol (MCP) eine Verbindung zu Experience Manager Guides herstellen. Sie können die MCP-Verbindungs- und Authentifizierungseinstellungen über die Seite Konfiguration der Adobe Experience Manager-Web-Konsole konfigurieren.

Die verfügbaren Konfigurationen steuern die Token-Verarbeitung, Anfragen ohne Referrer-Informationen und die externe URL für die AEM-Autoreninstanz.

## Konfigurieren der Verarbeitung von Anmelde-Token

Um die Verarbeitung von Anmelde-Token zu konfigurieren, führen Sie die folgenden Schritte aus:

1. Öffnen Sie die Seite Konfiguration der Adobe Experience Manager-Web-Konsole .

   Die Standard-URL für den Zugriff auf die Konfigurationsseite lautet:

   ```
   http://<server name>:<port>/system/console/configMgr
   ```

2. Suchen Sie nach **AEM Guides OAuth PKCE Token Wrapper und wählen Sie** aus.

3. Konfigurieren Sie die folgenden Eigenschaften:

   | Eigenschaft | Standard | Beschreibung |
   |---|---|---|
   | Granite-Basis-URL | `http://localhost:4502` | Gibt die URL an, die AEM für die Kommunikation mit der Autoreninstanz während der Authentifizierung verwendet. Ändern Sie den Standard-Port 4502 nur, wenn Ihre Autoreninstanz einen anderen Port verwendet. |
   | Granite-Zeitüberschreitung (ms) | `5000` | Gibt die maximale Zeit in Millisekunden an, die auf den Abschluss der Authentifizierungsanfrage gewartet werden soll. |

4. Klicken Sie auf **Speichern**.

## Konfigurieren von Anfragen ohne Referrer-Informationen

>[!NOTE]
>
> Diese Einstellung muss nur konfiguriert werden, wenn Sie den Cursor verwenden.

Einige MCP-Clients, einschließlich Cursor, senden möglicherweise Anfragen ohne Referrer-Informationen. Um diese Anfragen zuzulassen, konfigurieren Sie den Apache Sling Referrer-Filter wie folgt:

1. Öffnen Sie die Seite Konfiguration der Adobe Experience Manager-Web-Konsole .

   Die Standard-URL für den Zugriff auf die Konfigurationsseite lautet:

   ```
   http://<server name>:<port>/system/console/configMgr
   ```

2. Suchen Sie nach **Apache Sling Referrer Filter** und wählen Sie.

3. Legen Sie in der **Leer zulassen**-Eigenschaft den Wert auf `true` fest.

   Diese Einstellung ermöglicht Anfragen, die während der Authentifizierung keine Referrer-Informationen enthalten.

4. Klicken Sie auf **Speichern**.

## Konfigurieren der externen URL für die Autoreninstanz

Mit dem **Day CQ Link Externalizer**-Service können Sie zentral die externen URLs definieren, die zum Präfix von Ressourcenpfaden verwendet werden, einschließlich der URL der AEM-Autoreninstanz.

Um die externe URL zu konfigurieren, führen Sie die folgenden Schritte aus:

1. Öffnen Sie die Seite Konfiguration der Adobe Experience Manager-Web-Konsole .

   Die Standard-URL für den Zugriff auf die Konfigurationsseite lautet:

   ```
   http://<server name>:<port>/system/console/configMgr
   ```

2. Suchen Sie nach „Day **Link Externalizer“ und wählen Sie** aus.

3. Fügen **unter** Domains“ die `author` Zuordnung im folgenden Format hinzu oder aktualisieren Sie sie:

   ```
   author [scheme://]server[:port][/contextpath]
   ```

   Beispiel:

   ```
   author https://author.mycompany.com
   ```

4. Klicken Sie auf **Speichern**.