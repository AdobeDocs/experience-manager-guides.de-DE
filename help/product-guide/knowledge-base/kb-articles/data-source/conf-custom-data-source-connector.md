---
title: Benutzerdefinierten Connector für Datenquellen konfigurieren
description: Erfahren Sie, wie Sie einen benutzerdefinierten Connector für die Datenquellen konfigurieren.
feature: Web Editor Configuration
role: Admin
level: Experienced
source-git-commit: fdd19363c6768860ffa2f70c934b6f71c811c08b
workflow-type: tm+mt
source-wordcount: '1521'
ht-degree: 0%

---

# Benutzerdefinierte Data Source Connectors konfigurieren

Mit Experience Manager Guides können Sie die Connectoren Ihren Anforderungen entsprechend anpassen und sie dann mit den verschiedenen Datenquellen verwenden. Um einen Connector anzupassen, müssen Sie die Connector-Schnittstelle und die wichtigen Funktionen implementieren und dann die Schnittstelle konfigurieren. Sie können auch die Ressourcen zusammen mit den benutzerdefinierten Connectoren bereitstellen.


- [Connector für Experience Manager Guides anpassen](#customize-connector)
- [Connector-Oberfläche implementieren](#implement-interface)
- [Wichtige Funktionen](#important-functions)
- [Typen von standardmäßigen Connector-Implementierungen](#default-connectors)
   - [Konfigurationsoberfläche](#config-interface)
   - [Standardkonfigurationstypen für Implementierungen](#default-config-types)
   - [Konkrete Konfigurationsimplementierungen](#concrete-config-implementation)
   - [Zusätzliche Ressourcen](#resources)



## Connector für Experience Manager Guides anpassen {#customize-connector}

Sie können einen Connector für eine Datenquelle mithilfe der vordefinierten Schnittstellen und abstrakten Klassen anpassen oder konfigurieren. Der gesamte Quellcode ist unter [https://github.com/adobe/guides-data-source-connectors/tree/main/konnect-definitions](https://github.com/adobe/guides-data-source-connectors/tree/main/konnect-definitions) verfügbar.


Siehe [![javadoc](https://javadoc.io/badge2/com.adobe.aem.addon.guides/konnect-definitions/javadoc.svg)](https://javadoc.io/doc/com.adobe.aem.addon.guides/konnect-definitions) für konnect-definitions.

## Connector-Oberfläche implementieren {#implement-interface}

Führen Sie die folgenden Schritte aus, um die Oberfläche und ihre Funktionen entsprechend Ihren Anforderungen zu implementieren:

1. Definieren Sie eine standardisierte Methode für die Integration der Connectoren in ein System, die die Ausführung von Abfragen, die Validierung von Verbindungen und das Abrufen von Metadaten ermöglicht.
1. Erleichtern Sie die Integration der Benutzeroberfläche durch Bereitstellung der Standardmethoden zum Konfigurieren von Vorlagen, Logos, Abfragen und anderen Einstellungen.
1. Stellen Sie sicher, dass die Connectoren ordnungsgemäß validiert sind und Fehler (`KonnectException`) bei der Interaktion mit Datenquellen verarbeiten können.

Die Schnittstelle dient als Entwurf für die Implementierung verschiedener Typen von Data Connectors und stellt sicher, dass die Connectoren alle spezifischen Integrations- und Betriebsanforderungen innerhalb eines größeren Software-Ökosystems erfüllen.

## Wichtige Funktionen {#important-functions}

Implementieren Sie die folgenden wichtigen Funktionen:

| Methode | Mandatory | Beschreibung |
|---|---|---|
| getLogoUrl |  | <ul><li> Diese Methode gibt die URL zurück, die als Logo des Connectors verwendet wird. <li> Standardmäßig wird eine leere Zeichenfolge zurückgegeben, die angibt, dass keine Logo-URL bereitgestellt wird, es sei denn, diese wird überschrieben. <br><b> Zusätzliche Hinweise</b>: <br> <ul><li> Wenn Sie sowohl eine Logo-URL als auch einen Logo-Klassennamen angeben, wird die Logo-URL verwendet, um das Logo in der Benutzeroberfläche anzuzeigen. <li> Wenn Sie die Logo-URL über die Konfigurationseinstellungen angeben, wird die in der Methodimplementierung festgelegte URL überschrieben. |
| validateConnection | Ja | <ul><li> Verwenden Sie diese Methode, um zu überprüfen, ob der Connector eine Verbindung zu seiner Datenquelle herstellen kann. <li> Es nimmt ein `ConfigDto` -Objekt als Parameter an, das die Konfigurationseinstellungen wie Verbindungs-Anmeldedaten und Endpunkt-URLs enthält. <li> Die Methode gibt &quot;true&quot;zurück, wenn die Validierung (Verbindungstest) erfolgreich war. Dies gibt an, dass der Connector eine Verbindung zur Datenquelle herstellen kann. |
| execute | ja | <ul><li>Verwenden Sie diese Methode, um eine einzelne Abfrage für den Connector auszuführen und mit einer Datenquelle zu interagieren. <li> Die Connectoren, die diesen Vorgang unterstützen, verarbeiten die Ausführung der Abfrage, analysieren die Antwort und konvertieren sie bei Bedarf in eine JSON-Zeichenfolge. <li> Kapseln Sie die in dieser Methode auszuführende Abfrage in einem `QueryInfoDto` -Objekt, das Details wie die Abfragezeichenfolge und Parameter enthält. <li> Die Methode gibt eine JSON-Zeichenfolge zurück, die die Antwort aus der Ausführung der Abfrage darstellt. <br><b> Zusätzliche Hinweise</b>: <li>Die Implementierungen dieser Methode variieren je nach spezifischem Connector und dessen Interaktion mit der Datenquelle. <li> Verwenden Sie den `KonnectException` , um alle Ausnahmen oder Fehler zu handhaben, die während der Ausführung oder Verbindung mit der Datenquelle auftreten. |
| executeWithLimit | ja | <ul><li> Verwenden Sie diese Methode für denselben Zweck wie `execute()`, allerdings mit der zusätzlichen Funktion, eine begrenzende Abfrage anzuwenden, in der Regel zum Anzeigen der Vorschau in UI-Komponenten. <li> Connectoren, die diesen Vorgang unterstützen, verwalten die Ausführung der Abfrage, analysieren die Antwort und konvertieren sie bei Bedarf in eine JSON-Zeichenfolge. <li> Kapseln Sie die in dieser Methode auszuführende Abfrage in einem `QueryInfoDto` -Objekt, ähnlich wie bei der vorherigen Methode. <br><b> Zusätzliche Hinweise</b>: <ul><li> `QueryResultDto` ist eine benutzerdefinierte Klasse oder ein Datenübertragungsobjekt, das das Ergebnis der Abfrageausführung einschließlich Metadaten zur Abfrage und deren Ausführungsstatus einkapselt. |
| getSampleQuery | | <ul><li>Diese Methode gibt eine Beispielabfragezeichenfolge zurück, die beispielsweise in der Benutzeroberfläche im Dialogfeld angezeigt werden kann, in dem Benutzer Abfragen einfügen oder bearbeiten können. <li>Standardmäßig wird eine leere Zeichenfolge zurückgegeben, die angibt, dass keine Beispielabfrage bereitgestellt wird, sofern sie nicht überschrieben wird. <br><b> Zusätzliche Hinweise</b>: <ul> <li> Wenn Sie keine Beispielabfrage definieren und die Methode eine leere Zeichenfolge zurückgibt, wird keine Beispielabfrage im UI-Dialogfeld zum Einfügen von Abfragen angezeigt. |
| getTemplates | | <ul> <li> Diese Methode gibt eine Liste von Vorlagen zurück, die mit dem Connector verknüpft sind. <li> Standardmäßig wird eine leere Liste zurückgegeben, die angibt, dass keine Vorlagen bereitgestellt werden, sofern sie nicht überschrieben werden. |
| getLogoClassName | | <ul> <li> Diese Methode gibt den Klassennamen als Logo des Connectors zurück. Standardmäßig wird eine leere Zeichenfolge zurückgegeben, die angibt, dass kein Logo-Klassenname angegeben wird, es sei denn, es wird überschrieben. <br><b> Zusätzliche Hinweise</b>: <ul><li> Wenn Sie sowohl eine Logo-URL als auch einen Logo-Klassennamen angeben, wird die Logo-URL verwendet, um das Logo in der Benutzeroberfläche anzuzeigen. <li> Wenn Sie den Logo-Klassennamen über die Konfigurationseinstellungen angeben, überschreibt er den in der Methodimplementierung festgelegten Klassennamen. |
| enabled | ja | <ul><li> Diese Methode prüft, ob `connector` aktiviert ist. <li> Standardmäßig gibt die Methode &quot;false&quot;zurück. Das bedeutet, dass der Connector nur aktiviert ist, wenn er von einer Klasse überschrieben wird, die diese Methode implementiert. |
| getDescription | | <ul><li>Verwenden Sie diese Methode, um eine Beschreibungszeichenfolge zurückzugeben, die in der Benutzeroberfläche angezeigt werden kann. <li> Standardmäßig wird eine leere Zeichenfolge zurückgegeben, die angibt, dass keine Beschreibung bereitgestellt wird, es sei denn, diese wird überschrieben. |
| getAuthor | | <ul><li> Diese Methode bietet eine Möglichkeit, den Namen des Autors abzurufen, der den Connector erstellt hat oder für ihn verantwortlich ist. <li> Normalerweise hilft es dabei, den Ersteller oder Betreuer des Connectors innerhalb eines Systems oder Frameworks zu identifizieren und zu bestätigen. |
| getName | ja | <ul><li>Diese Methode bietet eine Möglichkeit, den eindeutigen Namen abzurufen, der einem Connector zugewiesen ist. <li>Der zurückgegebene Name ist für die Identifizierung des Connectors innerhalb eines Benutzeroberflächen-Kontexts (UI) von entscheidender Bedeutung, insbesondere wenn in den Konfigurationseinstellungen des Connectors kein expliziter Name angegeben wird. <li>Dieser Name wird in verschiedenen Komponenten der Benutzeroberfläche verwendet, um Connectoren benutzerfreundlich anzuzeigen oder zu verwalten. |
| getGroup | ja | <ul> <li>Diese Methode bietet eine Möglichkeit, den mit einem Connector verknüpften Gruppennamen abzurufen. <li>Gruppennamen werden normalerweise verwendet, um Connectoren basierend auf ihrer Funktionalität, ihrem Zweck oder ihrem Typ in logische Gruppen zu organisieren oder zu kategorisieren. <li> Dies ermöglicht eine einfachere Verwaltung und Präsentation von Connectoren über die Konfigurationsoberfläche. |
| getDefaultTemplatePath |  | <ul><li> Diese Methode gibt den Standardpfad für die mit diesem Connector verknüpften Vorlagen zurück. <li> Standardmäßig wird eine leere Zeichenfolge zurückgegeben, die angibt, dass kein Standardpfad festgelegt ist, es sei denn, er wird überschrieben. |
| getLogoSvg |  | <ul><li>Verwenden Sie diese Methode, um die SVG-Darstellung des Logos des Connectors zurückzugeben. <li> Standardmäßig wird eine leere Zeichenfolge zurückgegeben, die angibt, dass keine SVG-Daten bereitgestellt werden, es sei denn, sie werden überschrieben. |
| getMaxNoRowsForPreviewQuery | | <ul><li>Diese Methode gibt die maximale Anzahl von Zeilen zurück, die in der UI-Vorschau abgefragt oder angezeigt werden. <li> Standardmäßig wird der Wert von DEFAULT_LIMIT_PREVIEW zurückgegeben, einer Konstante, die die Standardgrenze für Vorschauzeilen darstellt. |
| getConfigClass | ja | <ul><li>Diese Methode enthält Informationen zu den Klassen, die die Config-Schnittstelle implementieren und von diesem Connector unterstützt werden. <li> Dadurch kann die Anwendung oder das Framework dynamisch Konfigurationen erkennen und verwenden, die mit dem Connector kompatibel sind. |

## Typen von standardmäßigen Connector-Implementierungen {#default-connectors}

Die Bibliothek *konnect-definitions* enthält abstrakte Connector-Implementierungen und vordefinierte Funktionen zum Ausführen von Abfragen. Diese Connector-Implementierungen dienen als Vorlagen, die direkt erweitert und wie besehen verwendet werden können. Wenn eine benutzerdefinierte Implementierung erforderlich ist, können deren Funktionen überschrieben werden.

Neben der Implementierung der Standard-Connectoren können Sie auch eine der folgenden abstrakten Standardklassen implementieren:

- REST-Anschluss
- File Connector
- GraphQL Connector
- SQL Connector
- NoSQL Connector


Wenn ein Connector zu einem dieser Typen passt, erweitern Sie den Connector auf die entsprechende Basisklasse. Erstellen Sie sie andernfalls von Grund auf neu, indem Sie die Connector-Oberfläche implementieren.

## Konfigurationsoberfläche {#config-interface}

Die Oberfläche von `Config` wurde entwickelt, um eine Datenquelle mit einer bestimmten Authentifizierungsmethode zu konfigurieren und Ihnen so eine präzise Steuerung der Verbindungserstellung zu ermöglichen.

Die `Config` -Benutzeroberfläche bietet Flexibilität bei der Handhabung und Implementierung von Authentifizierungsdetails. Verschiedene Implementierungen bieten verschiedene Möglichkeiten zur Authentifizierung von Datenquellen. Ein Connector verwendet eine Config-Instanz, um Abfragen für eine Datenquelle auszuführen und zu validieren und so einen vollständigen Workflow zu bilden.
Ein Connector verwendet eine `Config` -Instanz, um Abfragen für eine Datenquelle auszuführen und zu validieren, wobei ein vollständiger Workflow entsteht.

Eine Konfigurationsimplementierung definiert, wie die Authentifizierung für die Verbindung mit einer Datenquelle gehandhabt wird. Diese Konfiguration wird dann von einer Connector-Implementierung verwendet, um mit der Datenquelle zu interagieren und sicherzustellen, dass Abfragen korrekt ausgeführt und validiert werden.

Insgesamt ist die `Config` -Schnittstelle ein wichtiger Bestandteil des Workflows für die Verbindung mit Datenquellen, insbesondere zur Authentifizierungskonfiguration.

### Standardkonfigurationstypen für Implementierungen {#default-config-types}

Es gibt drei Typen von standardmäßigen abstrakten Konfigurationsimplementierungen für die Authentifizierung:

- RestConfig
- SqlConfig
- NoSqlConfig

Wenn eine Konfiguration mit einem dieser Typen übereinstimmt, kann sie die entsprechende Basisklasse erweitern. Andernfalls kann es von Grund auf neu erstellt werden, indem die Konfigurationsoberfläche implementiert wird.

### Konkrete Konfigurationsimplementierungen {#concrete-config-implementation}

Die Bibliothek *konnect-definitions* enthält vordefinierte Implementierungen der Config-Oberfläche für einige häufig verwendete Authentifizierungskonfigurationen. Sie können diese Konfigurationen direkt im Connector verwenden oder neue über die Benutzeroberfläche &quot;Konfiguration&quot;definieren. Zu diesen Implementierungen gehören:

- API-Schlüssel-Authentifizierungskonfiguration
- Grundlegende Token-basierte Konfiguration für Auth
- Grundlegende Authentifizierungskonfiguration
- Bearer-Token-Konfiguration
- Benutzername Kennwortkonfiguration für SQL
- Verbindungszeichenfolge auth config für NoSQL

### Zusätzliche Ressourcen{#resources}

Mit Experience Manager Guides können Sie auch benutzerdefinierte Ressourcen für Logos und Vorlagen zusammen mit der Implementierung bereitstellen. Sie können diese Ressourcen im Ordner &quot;`resources`&quot;belassen.
Damit sie vom Connector verwendet werden können, müssen die folgenden Connector-Funktionen implementiert werden:


- `getLogoSvg` - Gibt die Logo-SVG als Zeichenfolge zurück.

- `getTemplates` - Gibt die Liste der Vorlagen im angegebenen Format zurück.