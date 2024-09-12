---
title: Architektur der externen Datenquellenintegration in AEM Guides
description: Erfahren Sie mehr über die Architektur der externen Data Sources-Integration in AEM Guides.
source-git-commit: b0cf652023770eda24ea27ff105ed6dc2cdd1f08
workflow-type: tm+mt
source-wordcount: '646'
ht-degree: 0%

---

# Integration externer Datenquellen

Daten aus externen Systemen können einfach in Ihre Experience Manager Guides-Instanz integriert werden. Die Verbindung mit externen Datenquellen kann die Funktionalität und Benutzerfreundlichkeit Ihres Content-Management-Systems erheblich verbessern.


Mithilfe der Datenintegration können Sie effizient Daten aus externen Quellen verbinden und abrufen. Mit dieser Funktion müssen Sie nicht vom IT-Team abhängig sein, um die Daten abzurufen und sie dann manuell zu kopieren und einzufügen oder die Änderungen im externen System ständig zu aktualisieren.

Diese Funktion sorgt für die Synchronisation mit der ursprünglichen Quelle und ermöglicht harmonische Aktualisierungen der Dokumentation, ohne manuelles Kopieren und Einfügen zu erfordern. Darüber hinaus wird die Datenkonsistenz zwischen Experience Manager Guides und der externen Datenquelle sichergestellt.

Darüber hinaus können Sie den Inhalt nach dem Abrufen aus externen Datenquellen im DITA-Format erstellen und auch den integrierten Inhalt wiederverwenden.


## Framework zur Datenquellenintegration

Das Integrations-Framework einer Datenquelle umfasst in erster Linie zwei Hauptkomponenten: die externen Datenquellen und deren Integration in die Experience Manager Guides-Instanz.

### Externe Datenquellen

Einige der Datenquellen, mit denen Sie eine Verbindung über Experience Manager Guides herstellen können, sind:

- Relationale Datenbanken (RDBMS)
   - PostgreSQL, MySQL, Microsoft SQL Server, MariaDB und SQLite
- Nicht relationale Datenbanken
   - MongoDB, Apache Cassandra, Apache CouchDB und Redis
- Produktinformationsmanagement (PIM)/Product Lifecycle Management (PLM)
   - Pimcore, Salsify, Akeneo und Informatica
- Produktmanagement-Systeme
   - JIRA- und Microsoft Azure DevOps-Pinnwände (ADO)
- Online-Analytics-Verarbeitung (OLAP) und Analytics-Systeme

### Integration in Experience Manager Guides



Durch die Verwendung eines authentifizierten Connectors werden Daten von einem externen System übertragen und in Experience Manager Guides generiert Daten.
![Architektur](assets/konnect-architecture.png)


### Integration in Experience Manager Guides

Führen Sie die folgenden Schritte aus, um den Inhalt in Experience Manager Guides zu integrieren:

1. **Einrichten des Datenquellen-Connectors**
   - Der Data Source Connector dient als Schnittstelle zur Herstellung der Verbindung mit den externen Datenquellen. Sie müssen den Connector konfigurieren, um die Verbindung herzustellen und die Authentifizierungsmethoden einzuschließen, z. B. `Basic Auth` oder `API key Auth`. Alle Konfigurationsdetails, einschließlich verschlüsselter Informationen, werden in Adobe Experience Manager sicher gespeichert.
   - Die Connector-Ebene ist erweiterbar und ermöglicht Ihnen die Erstellung von Implementierungen für die Verbindung mit verschiedenen Systemen, die nicht standardmäßig von Experience Manager Guides bereitgestellt werden.
     ![Connector-Ebene](assets/data-source-connector-layer.jpg)
   >[!NOTE]
   >
   > Greifen Sie auf das Definitionsmodul Connector zu und implementieren Sie die Schnittstelle Connector , um einen benutzerdefinierten Connector zu erstellen. Erfahren Sie mehr über das [Konfigurieren von benutzerdefinierten Data Source Connectors](./conf-custom-data-source-connector.md).

1. **Anpassen der Velocity-Vorlagen**

   - Experience Manager Guides unterstützt Velocity (https://velocity.apache.org/), eine hochgradig robuste Vorlagenmodul zur Umwandlung der Daten aus JSON-Dateien in DITA-Inhalte. Velocity bietet die Flexibilität, durch JSON-Strukturen mit beliebigen Verschachtelungsebenen zu navigieren.
   - Im folgenden Beispiel wird gezeigt, wie Sie Velocity-Vorlagen und -Daten aus Jira integrieren können, um mühelos Tabellen oder geordnete Listen zu generieren.
      - Jira Response

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
      - Daten aus derselben Datenquelle, aber aus unterschiedlichen Vorlagen
        ![Generierte Daten](assets/data-source-templates-topics.png){width="800" align="left"}

1. **Erstellen von Inhalten mit den Vorlagen**
   - Sie können den Inhalt aus den von Ihnen erstellten Vorlagen erstellen.
   - Sie können verschiedene Inhaltstypen generieren:
      - Snippet: Dies ist ein einmalig verwendbarer Inhalt. Sie können die Daten aus dem Connector in der definierten Vorlage generieren und dann in das gewünschte Tag einbetten.
      - DITA-Thema: Generieren Sie verschiedene Themen, die unverändert im Inhalt verwendet werden sollen oder die als *wiederverwendbare Komponente* wiederverwendet werden können.
      - DITA-Thema und -Karte: Sie können auch eine vollständige Zuordnung mit dem Thema erstellen und dann die Daten direkt für die Veröffentlichung verwenden oder sie als *wiederverwendbare Komponente* in anderen Daten verwenden.


1. **Publish des integrierten Inhalts**
   - Die Veröffentlichung ist die OOTB-Funktion von Experience Manager Guides und Sie können alle vom externen System generierten Daten direkt als PDF- oder AEM Site-Ausgabe veröffentlichen.

>[!MORELIKETHIS]
>
> Die folgenden Dokumente enthalten weitere Details zum Konfigurieren der Connectoren und deren Verwendung in Ihrer Instanz.
> - [Konfigurieren eines Datenquellen-Connectors](../../../install-guide/conf-data-source-connector-tools.md)
> - [Generieren von Inhalten mit Snippets oder Themen](../../../user-guide/web-editor-content-snippet.md)