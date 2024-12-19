---
title: Konfigurieren eines Datenquellen-Connectors
description: Erfahren Sie, wie Sie einen Datenquellen-Connector konfigurieren
exl-id: bd1188e1-0e1d-4e70-928a-10251c3d529d
feature: Web Editor Configuration
role: Admin
level: Experienced
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '387'
ht-degree: 0%

---

# Konfigurieren eines Datenquellen-Connectors

AEM Guides bietet vordefinierte Connectoren für JIRA- und SQL-Datenbanken (MySQL, PostgreSQL, SQL Server, SQLite). Sie können auch andere Connectoren hinzufügen, indem Sie die Standardschnittstellen erweitern. Die folgende Konfiguration hilft Ihnen beim einfachen Hinzufügen der verschiedenen Datenquellen. Nach dem Hinzufügen können Sie die Datenquellen im Web-Editor anzeigen.

Führen Sie die folgenden Schritte aus, um einen Datenquellen-Connector zu konfigurieren und ihn dann über den Web-Editor zu verwenden:

## Konfigurieren eines Connectors

Sie können einen vorkonfigurierten Connector konfigurieren, indem Sie eine JSON-Datei hochladen. Sie können die folgenden Beispiel-Setup-Dateien verwenden, um Connectoren für Jira- und SQL-Datenbanken (MySQL, PostgreSQL, SQL Server, SQLite) einzurichten.

Beispiel-Setup-Datei für die Jira-Standardauthentifizierung mit Benutzername und Kennwort:

```
{
	"connectorClazz": "com.adobe.guides.konnect.definitions.ootb.connector.rest.JiraConnector",
	"configName": "Jira",
	"templateFolders": ["/content/dam/dita-templates/konnect/jira"],
	"connectionConfig": {
		"configClazz": "com.adobe.guides.konnect.definitions.ootb.config.rest.BasicAuthRestConfig",
		"configData": {
			"username": "jirausername",
			"password": "jirapassword",
			"url": "https://jira.corp.adobe.com/rest/api/latest/search"
		}
	}
}
```

Speichern Sie beispielsweise als `jira.json`.

Beispiel-Setup-Datei für die einfache Authentifizierung von Jira mit Token:

```
{
	"connectorClazz": "com.adobe.guides.konnect.definitions.ootb.connector.rest.JiraConnector",
	"configName": "Jira",
	"templateFolders": ["/content/dam/dita-templates/konnect/jira"],
	"connectionConfig": {
		"configClazz": "com.adobe.guides.konnect.definitions.ootb.config.rest.BasicAuthRestConfig",
		"configData": {
			"token": "jiraauthtoken",
			"url": "https://jira.corp.adobe.com/rest/api/latest/search"
		}
	}
}
```

Speichern Sie beispielsweise als `jira.json`.

Beispiel-Setup-Datei für die einfache Authentifizierung von Jira mit dem Token, in dem das Keyword „Basic“ vorhanden ist:

```
{
	"connectorClazz": "com.adobe.guides.konnect.definitions.ootb.connector.rest.JiraConnector",
	"configName": "Jira",
	"templateFolders": ["/content/dam/dita-templates/konnect/jira"],
	"connectionConfig": {
		"configClazz": "com.adobe.guides.konnect.definitions.ootb.config.rest.BasicAuthRestConfig",
		"configData": {
			"token": "Basic jiraauthtoken",
			"url": "https://jira.corp.adobe.com/rest/api/latest/search"
		}
	}
}
```

Speichern Sie beispielsweise als `jira.json`.

Beispiel-Setup-Datei für die Standardauthentifizierung von MySQL:

```
{
	"connectorClazz": "com.adobe.guides.konnect.definitions.ootb.connector.sql.MySqlConnector",
	"configName": "MySQL",
	"templateFolders": ["/content/dam/dita-templates/konnect/sql"],
	"connectionConfig": {
		"configClazz": "com.adobe.guides.konnect.definitions.ootb.config.sql.UserPassSqlConfig",
		"configData": {
			"username": "admin",
			"password": "admin",
			"driver": "com.mysql.jdbc.Driver",
			"connectionString": "jdbc:mysql://host.corp.adobe.com:3306/plm"
		}
	}
}
```

Speichern Sie beispielsweise als `mysql.json`.

Beispiel-Setup-Datei für die Standardauthentifizierung von PostgreSQL:

```
{
	"connectorClazz": "com.adobe.guides.konnect.definitions.ootb.connector.sql.PostgreSqlConnector",
	"configName": "PostgreSQL",
	"templateFolders": ["/content/dam/dita-templates/konnect/sql"],
	"connectionConfig": {
		"configClazz": "com.adobe.guides.konnect.definitions.ootb.config.sql.UserPassSqlConfig",
		"configData": {
			"username": "admin",
			"password": "admin",
			"driver": "org.postgresql.Driver",
			"connectionString": "jdbc:postgresql://host:port/database"
		}
	}
}
```

Speichern Sie beispielsweise als `postgres.json`.

Beispiel-Setup-Datei für die Standardauthentifizierung von MS SQL Server:

```
{
	"connectorClazz": "com.adobe.guides.konnect.definitions.ootb.connector.sql.MsSqlServerConnector",
	"configName": "MSSQLServer",
	"templateFolders": ["/content/dam/dita-templates/konnect/sql"],
	"connectionConfig": {
		"configClazz": "com.adobe.guides.konnect.definitions.ootb.config.sql.UserPassSqlConfig",
		"configData": {
			"username": "admin",
			"password": "admin",
			"driver": "com.microsoft.sqlserver.jdbc.SQLServerDriver",
			"connectionString": "jdbc:sqlserver://10.10.10.10\\SQLEXPRESS01:1433;database=TutorialDB;encrypt=false;trustServerCertificate=true"
		}
	}
}
```

Speichern Sie beispielsweise als `mssqlserver.json`.

Beispiel-Setup-Datei für die SQLite-Standardauthentifizierung:

```
{
	"connectorClazz": "com.adobe.guides.konnect.definitions.ootb.connector.sql.SqliteConnector",
	"configName": "SQLiteServer",
	"templateFolders": ["/content/dam/dita-templates/konnect/sql"],
	"connectionConfig": {
		"configClazz": "com.adobe.guides.konnect.definitions.ootb.config.sql.UserPassSqlConfig",
		"configData": {
			"username": "admin",
			"password": "admin",
			"driver": "org.sqlite.JDBC",
			"connectionString": "jdbc:sqlite:sample.db"
		}
	}
}
```

Speichern Sie beispielsweise als `sqqlite.json`.

### Anpassen einer Connector-Konfiguration

Mit AEM Guides können Sie einige Werte in der Konfigurationsdatei an die Anforderungen der Benutzenden anpassen.

| Eigenschaftsname | Beschreibung |
|---|---|
| configName | Der Benutzer kann einen Konfigurationsnamen angeben, um den Connector zu identifizieren |
| templateFolders | Liste der Ordner, aus denen Vorlagen abgerufen werden |

Andere Felder werden je nach ausgewählter Konfigurationsklasse angepasst, um den Connector auszuführen.

## Laden Sie die Datei an einen Speicherort in AEM hoch

Laden Sie die Datei an einen Speicherort in AEM Assets hoch.

Beispiel: `/content/dam/jira.json`

## Erstellen einer Konfiguration mit der REST-API

Sie können die Konfiguration mit der REST-API registrieren. Weitere Informationen finden Sie im Abschnitt *REST-API zum Registrieren eines Datenquellen-Connectors* in der API-Referenz für Adobe Experience Manager Guides.

Nachdem Sie die Datenquelle konfiguriert haben, wird der Connector im Web-Editor unter dem Bedienfeld „Datenquellen“ aufgelistet. Anschließend können Sie eine Verbindung zur Datenquelle herstellen und ein Inhaltsfragment in Ihre Themen einfügen. Weitere Informationen finden Sie unter [Einfügen eines Inhaltsausschnitts aus Ihrer Datenquelle](../user-guide/web-editor-content-snippet.md).
