---
title: Architektur der Integration externer Datenquellen in AEM Guides
description: Erfahren Sie mehr über die Architektur der Integration externer Datenquellen in AEM Guides.
exl-id: ce99033a-0ce1-4696-9d4c-89187273b0bd
source-git-commit: 682eaf6f4a3a158f49a8f2ea91ce9cd2de3ff772
workflow-type: tm+mt
source-wordcount: '646'
ht-degree: 0%

---

# Integration externer Datenquellen

Daten aus externen Systemen können einfach in Ihre Experience Manager Guides-Instanz integriert werden. Durch die Verbindung mit externen Datenquellen können die Funktionalität und Benutzerfreundlichkeit Ihres Content-Management-Systems erheblich verbessert werden.


Sie können mithilfe der Datenintegration effizient Daten aus externen Quellen verbinden und abrufen. Bei dieser Funktion müssen Sie sich nicht darauf verlassen, dass das IT-Team die Daten abruft und sie dann manuell kopiert und einfügt oder die Änderungen im externen System ständig aktualisiert.

Diese Funktion stellt die Synchronisierung mit der ursprünglichen Quelle sicher und ermöglicht harmonische Aktualisierungen der Dokumentation, ohne auf manuelle Kopieren/Einfügen-Vorgänge angewiesen zu sein. Außerdem wird so die Datenkonsistenz zwischen Experience Manager Guides und der externen Datenquelle gewahrt.

Darüber hinaus können Sie den Inhalt nach dem Abrufen aus externen Datenquellen im DITA-Format erstellen und den integrierten Inhalt auch wiederverwenden.


## Framework zur Datenquellenintegration

Das Integrations-Framework einer Datenquelle umfasst hauptsächlich zwei Hauptkomponenten: die externen Datenquellen und ihre Integration in die Experience Manager Guides-Instanz.

### Externe Datenquellen

Zu den Datenquellen, mit denen Sie über Experience Manager Guides eine Verbindung herstellen können, gehören die folgenden:

- Relationale Datenbanken (RDBMS)
   - PostgreSQL, MySQL, Microsoft SQL Server, MariaDB und SQLite
- Nicht-relationale Datenbanken
   - MongoDB, Apache Cassandra, Apache CouchDB und Redis
- Product Information Management (PIM) / Product Lifecycle Management (PLM)
   - Pimcore, Salsify, Akeneo und Informatica
- Produktmanagementsysteme
   - JIRA- und Microsoft Azure DevOps-Boards (ADO)
- OLAP- (Online Analytical Processing) und Analytics-Systeme

### Integration in Experience Manager Guides



Durch die Verwendung eines authentifizierten Connectors werden Daten von einem externen System übertragen und generieren Daten in Experience Manager Guides.
![Architektur](assets/konnect-architecture.png)


### Integration in Experience Manager Guides

Führen Sie die folgenden Schritte aus, um den Inhalt in Experience Manager Guides zu integrieren:

1. **Einrichten des Datenquellen-Connectors**
   - Der Datenquellen-Connector dient als Schnittstelle zum Herstellen der Verbindung mit den externen Datenquellen. Sie müssen den Connector konfigurieren, um die Verbindung herzustellen, und die Authentifizierungsmethoden wie `Basic Auth` oder `API key Auth` einschließen. Alle Konfigurationsdetails, einschließlich verschlüsselter Informationen, werden sicher in Adobe Experience Manager gespeichert.
   - Die Connector-Ebene ist erweiterbar, sodass Sie Ihre Implementierungen für die Verbindung mit verschiedenen Systemen erstellen können, die von Experience Manager Guides nicht vorkonfiguriert bereitgestellt werden.
     ![Connector-Ebene](assets/data-source-connector-layer.jpg)
   >[!NOTE]
   >
   > Greifen Sie auf das Modul Konconnect-Definition zu und implementieren Sie die Connector-Schnittstelle , um einen benutzerdefinierten Connector zu erstellen. Erfahren Sie mehr über [Konfigurieren von benutzerdefinierten Datenquellen-Connectoren](./conf-custom-data-source-connector.md).

1. **Anpassen der Velocity-Vorlagen**

   - Experience Manager Guides unterstützt Velocity (https://velocity.apache.org/), eine hochgradig robuste Vorlagen-Engine zur Umwandlung von Daten aus JSON-Dateien in DITA-Inhalte. Velocity bietet die Flexibilität, durch JSON-Strukturen mit beliebigen Verschachtelungsebenen zu navigieren.
   - Das folgende Beispiel zeigt, wie Sie Velocity-Vorlagen und Daten aus Jira integrieren können, um mühelos Tabellen oder geordnete Listen zu generieren.
      - Jira-Antwort

        ```
        {
            "expand": "schema,names",
            "total": 5,
            "hostname": "https://jira.corp.adobe.com",
            "maxResults": "200",
            "issues": [
                {
                    "key": "DXML-12756",
                    "fields": {
                        "description": "Implement the snippet generator in External Data Source integration",
                        "summary": "Implement the snippet generator in External Data Source integration"
                    }
                },
                {
                    "key": "DXML-12755",
                    "fields": {
                        "description": "Implement the topic generator in External Data Source integration",
                        "summary": "Implement the topic generator in External Data Source integration"
                    }
                },
                {
                    "key": "DXML-12745",
                    "fields": {
                        "description": "Implement the ability to register a new connector",
                        "summary": "Implement the ability to register a new connector"
                    }
                }
            ],
            "startAt": 0
        }
        ```

      - Vorlagen
        ![Vorlagenmodul](assets/data-source-TemplatingEngine.png){width="800" align="left"}
      - Daten aus derselben Datenquelle, aber unterschiedlichen Vorlagen
        ![Daten generiert](assets/data-source-templates-topics.png){width="800" align="left"}

1. **Generieren von Inhalten mithilfe von Vorlagen**
   - Sie können den Inhalt aus den von Ihnen erstellten Vorlagen generieren.
   - Sie können verschiedene Inhaltstypen generieren:
      - Snippet: Dies ist ein einmalig verwendbarer Inhalt. Sie können die Daten aus dem Connector in der definierten Vorlage generieren und dann in das gewünschte Tag einbetten.
      - DITA-Thema: Generieren Sie verschiedene Themen, die unverändert im Inhalt verwendet werden können oder als *wiederverwendbare Komponente“ wiederverwendet* können.
      - DITA Topic + Map: Sie können auch eine vollständige Zuordnung mit dem Thema generieren und dann die Daten direkt zur Veröffentlichung verwenden oder als *wiederverwendbare Komponente* in anderen Daten verwenden.


1. **Publish der integrierte Inhalt**
   - Publishing ist die vorkonfigurierte Funktion von Experience Manager Guides und Sie können alle vom externen System generierten Daten direkt als PDF- oder AEM Site-Ausgabe veröffentlichen.

>[!MORELIKETHIS]
>
> In den folgenden Dokumenten finden Sie weitere Informationen zur Konfiguration der Connectoren und deren Verwendung in Ihrer -Instanz.
> - [Konfigurieren eines Datenquellen-Connectors](../../../install-guide/conf-data-source-connector-tools.md)
> - [Generieren von Inhalten mithilfe von Snippets oder Themen](../../../user-guide/web-editor-content-snippet.md)
