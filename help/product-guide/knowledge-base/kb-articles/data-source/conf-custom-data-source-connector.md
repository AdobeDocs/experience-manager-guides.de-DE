---
title: Konfigurieren eines benutzerdefinierten Connectors für die Datenquellen
description: Erfahren Sie, wie Sie einen benutzerdefinierten Connector für die Datenquellen konfigurieren.
feature: Web Editor Configuration
role: Admin
level: Experienced
exl-id: ef7ab117-7541-4e89-9ba4-22254a17efc0
source-git-commit: 682eaf6f4a3a158f49a8f2ea91ce9cd2de3ff772
workflow-type: tm+mt
source-wordcount: '1521'
ht-degree: 0%

---

# Konfigurieren von benutzerdefinierten Datenquellen-Connectoren

Mit Experience Manager Guides können Sie die Connectoren Ihren Anforderungen entsprechend anpassen und dann mit den verschiedenen Datenquellen verwenden. Um einen Connector anzupassen, müssen Sie die Connector-Schnittstelle und ihre wichtigen Funktionen implementieren und dann die Schnittstelle konfigurieren. Sie können die Ressourcen auch zusammen mit den benutzerdefinierten Connectoren bereitstellen.


- [Anpassen eines Connectors für Experience Manager Guides](#customize-connector)
- [Implementieren der Connector-Schnittstelle](#implement-interface)
- [Wichtige Funktionen](#important-functions)
- [Typen von standardmäßigen Connector-Implementierungen](#default-connectors)
   - [Konfigurationsschnittstelle](#config-interface)
   - [Typen von Standardimplementierungen](#default-config-types)
   - [Konkrete Konfigurationsimplementierungen](#concrete-config-implementation)
   - [Zusätzliche Ressourcen](#resources)



## Anpassen eines Connectors für Experience Manager Guides {#customize-connector}

Sie können einen Connector für eine Datenquelle mithilfe der vordefinierten Schnittstellen und abstrakten Klassen anpassen oder konfigurieren. Der gesamte Quell-Code ist verfügbar unter [https://github.com/adobe/guides-data-source-connectors/tree/main/konnect-definitions](https://github.com/adobe/guides-data-source-connectors/tree/main/konnect-definitions).


Siehe [![javadoc](https://javadoc.io/badge2/com.adobe.aem.addon.guides/konnect-definitions/javadoc.svg)](https://javadoc.io/doc/com.adobe.aem.addon.guides/konnect-definitions) für konnect-definitionen.

## Implementieren der Connector-Schnittstelle {#implement-interface}

Führen Sie die folgenden Schritte aus, um die Schnittstelle und ihre Funktionen gemäß Ihren Anforderungen zu implementieren:

1. Definieren Sie eine standardisierte Methode für die Integration der Connectoren mit einem System, sodass Abfragen ausgeführt, Verbindungen validiert und Metadaten abgerufen werden können.
1. Erleichterung der UI-Integration durch Bereitstellung der Standardmethoden zum Konfigurieren von Vorlagen, Logos, Abfragen und anderen Einstellungen.
1. Stellen Sie sicher, dass die Connectoren ordnungsgemäß validiert sind und Fehler (`KonnectException`) bei der Interaktion mit Datenquellen verarbeiten können.

Die Schnittstelle dient als Blueprint für die Implementierung verschiedener Arten von Daten-Connectoren und stellt sicher, dass die Connectoren alle spezifischen Integrations- und Betriebsanforderungen in einem größeren Software-Ökosystem erfüllen.

## Wichtige Funktionen {#important-functions}

Implementieren Sie die folgenden wichtigen Funktionen:

| Methode | Mandatory | Beschreibung |
|---|---|---|
| getLogoUrl |  | <ul><li> Diese Methode gibt die URL zurück, die als Logo des Connectors verwendet wird. <li> Standardmäßig wird eine leere Zeichenfolge zurückgegeben, was darauf hinweist, dass keine Logo-URL bereitgestellt wird, es sei denn, sie wird überschrieben. <br><b> zusätzliche Hinweise</b>: <br> <ul><li> Wenn Sie sowohl eine Logo-URL als auch einen Logo-Klassennamen angeben, wird die Logo-URL verwendet, um das Logo in der Benutzeroberfläche anzuzeigen. <li> Wenn Sie die Logo-URL über die Konfigurationseinstellungen angeben, überschreibt sie die in der Methodenimplementierung festgelegte URL. |
| validateConnection | Ja | <ul><li> Verwenden Sie diese Methode, um zu überprüfen, ob der Connector eine Verbindung zu seiner Datenquelle herstellen kann. <li> Dazu wird ein `ConfigDto`-Objekt als Parameter benötigt, das die Konfigurationseinstellungen wie Verbindungsanmeldeinformationen und Endpunkt-URLs enthält. <li> Die Methode gibt „true“ zurück, wenn die Validierung (Verbindungstest) erfolgreich war. Dies bedeutet, dass der Connector eine Verbindung zu seiner Datenquelle herstellen kann. |
| vollziehen | ja | <ul><li>Verwenden Sie diese Methode, um eine einzelne Abfrage für den Connector auszuführen und mit einer Datenquelle zu interagieren. <li> Die Connectoren, die diesen Vorgang unterstützen, handhaben die Ausführung der Abfrage, parsen die Antwort und konvertieren sie bei Bedarf in eine JSON-Zeichenfolge. <li> Kapseln Sie die in dieser Methode auszuführende Abfrage in einem `QueryInfoDto`-Objekt, das Details wie die Abfragezeichenfolge und Parameter enthält. <li> Die Methode gibt eine JSON-Zeichenfolge zurück, die die Antwort aus der Ausführung der Abfrage darstellt. <br><b> zusätzliche Hinweise</b>: <li>Implementierungen dieser Methode variieren je nach dem spezifischen Connector und seiner Interaktion mit der Datenquelle. <li> Verwenden Sie die `KonnectException`, um alle Ausnahmen oder Fehler zu behandeln, die während der Ausführung oder Verbindung mit der Datenquelle auftreten. |
| executeWithLimit | ja | <ul><li> Verwenden Sie diese Methode für denselben Zweck wie `execute()`, jedoch mit der zusätzlichen Funktion, eine einschränkende Abfrage anzuwenden, normalerweise zum Anzeigen der Vorschauen in Benutzeroberflächenkomponenten. <li> Connectoren, die diesen Vorgang unterstützen, handhaben die Ausführung der Abfrage, parsen die Antwort und konvertieren sie bei Bedarf in eine JSON-Zeichenfolge. <li> Kapseln Sie die in dieser Methode auszuführende Abfrage in einem `QueryInfoDto` Objekt, ähnlich der vorherigen Methode. <br><b> zusätzliche Hinweise</b>: <ul><li> `QueryResultDto` ist eine benutzerdefinierte Klasse oder ein Datenübertragungsobjekt, das das Ergebnis der Abfrageausführung einschließlich Metadaten zur Abfrage und deren Ausführungsstatus enthält. |
| getSampleQuery | | <ul><li>Diese Methode gibt eine Beispiel-Abfragezeichenfolge zurück, die in der Benutzeroberfläche angezeigt werden kann, z. B. im Dialogfeld, in dem Benutzer Abfragen einfügen oder bearbeiten können. <li>Standardmäßig wird eine leere Zeichenfolge zurückgegeben, was darauf hinweist, dass keine Beispielabfrage bereitgestellt wird, es sei denn, sie wird überschrieben. <br><b> zusätzliche Hinweise</b>: <ul> <li> Wenn Sie keine Beispielabfrage definieren und die Methode eine leere Zeichenfolge zurückgibt, wird im Dialogfeld zum Einfügen der Abfrage in der Benutzeroberfläche keine Beispielabfrage angezeigt. |
| getTemplates | | <ul> <li> Diese Methode gibt eine Liste von Vorlagen zurück, die mit dem Connector verknüpft sind. <li> Standardmäßig wird eine leere Liste zurückgegeben, was bedeutet, dass keine Vorlagen bereitgestellt werden, es sei denn, sie werden überschrieben. |
| getLogoClassName | | <ul> <li> Diese Methode gibt den Klassennamen als Logo des Connectors zurück. Standardmäßig wird eine leere Zeichenfolge zurückgegeben, was darauf hinweist, dass kein Logo-Klassenname bereitgestellt wird, es sei denn, er wird überschrieben. <br><b> zusätzliche Hinweise</b>: <ul><li> Wenn Sie sowohl eine Logo-URL als auch einen Logo-Klassennamen angeben, wird die Logo-URL verwendet, um das Logo in der Benutzeroberfläche anzuzeigen. <li> Wenn Sie den Namen der Logoklasse über die Konfigurationseinstellungen angeben, überschreibt er den in der Methodenimplementierung festgelegten Klassennamen. |
| enabled | ja | <ul><li> Diese Methode prüft, ob ein `connector` aktiviert ist. <li> Standardmäßig gibt die Methode false zurück. Das bedeutet, dass der Connector nur aktiviert wird, wenn er von einer Klasse überschrieben wird, die diese Methode implementiert. |
| getDescription | | <ul><li>Verwenden Sie diese Methode, um eine Beschreibungszeichenfolge zurückzugeben, die in der Benutzeroberfläche angezeigt werden kann. <li> Standardmäßig wird eine leere Zeichenfolge zurückgegeben, was bedeutet, dass keine Beschreibung bereitgestellt wird, es sei denn, sie wird überschrieben. |
| getAuthor | | <ul><li> Diese Methode bietet eine Möglichkeit, den Namen des Autors abzurufen, der den Connector erstellt hat oder für ihn verantwortlich ist. <li> Dies hilft in der Regel dabei, den Ersteller oder Betreuer des Connectors innerhalb eines Systems oder Frameworks zu identifizieren und zu bestätigen. |
| getName | ja | <ul><li>Diese Methode bietet eine Möglichkeit, den eindeutigen Namen abzurufen, der einem Connector zugewiesen ist. <li>Der zurückgegebene Name ist wichtig, um den Connector in einem Benutzeroberflächen-Kontext zu identifizieren, insbesondere wenn in den Konfigurationseinstellungen des Connectors kein expliziter Name angegeben ist. <li>Dieser Name wird in verschiedenen UI-Komponenten verwendet, um Connectoren benutzerfreundlich anzuzeigen oder zu verwalten. |
| getGroup | ja | <ul> <li>Diese Methode bietet eine Möglichkeit, den mit einem Connector verknüpften Gruppennamen abzurufen. <li>Gruppennamen werden normalerweise verwendet, um Connectoren basierend auf ihrer Funktionalität, ihrem Zweck oder ihrem Typ in logische Gruppen zu organisieren oder zu kategorisieren. <li> Dies ermöglicht eine einfachere Verwaltung und Darstellung von Connectoren in der Konfigurationsoberfläche. |
| getDefaultTemplatePath |  | <ul><li> Diese Methode gibt den Standardpfad für die mit diesem Connector verknüpften Vorlagen zurück. <li> Standardmäßig wird eine leere Zeichenfolge zurückgegeben. Dies bedeutet, dass kein Standardpfad festgelegt wird, es sei denn, er wird überschrieben. |
| getLogoSvg |  | <ul><li>Mit dieser Methode geben Sie die SVG-Darstellung des Connector-Logos zurück. <li> Standardmäßig wird eine leere Zeichenfolge zurückgegeben, was darauf hinweist, dass keine SVG-Daten bereitgestellt werden, es sei denn, sie werden überschrieben. |
| getMaxNoRowsForPreviewQuery | | <ul><li>Diese Methode gibt die maximale Anzahl von Zeilen zurück, die in der Vorschau der Benutzeroberfläche abgefragt oder angezeigt werden. <li> Standardmäßig wird der Wert von DEFAULT_LIMIT_PREVIEW zurückgegeben, eine Konstante, die das standardmäßige Limit für Vorschauzeilen darstellt. |
| getConfigClass | ja | <ul><li>Diese Methode stellt Informationen über die Klassen bereit, die die Config-Schnittstelle implementieren und von diesem Connector unterstützt werden. <li> Dadurch kann das Programm oder Framework mit Konfigurationen, die mit dem Connector kompatibel sind, dynamisch suchen und arbeiten. |

## Typen von standardmäßigen Connector-Implementierungen {#default-connectors}

Die *konnect-definitions*-Bibliothek enthält abstrakte Connector-Implementierungen und mit vordefinierten Funktionen zum Ausführen von Abfragen. Diese Connector-Implementierungen fungieren als Vorlagen, die direkt erweitert und unverändert verwendet werden können. Wenn eine benutzerdefinierte Implementierung erforderlich ist, können die Funktionen überschrieben werden.

Neben der Implementierung der Standard-Connectoren können Sie auch eine der folgenden standardmäßigen abstrakten Klassen implementieren:

- REST-Connector
- Datei-Connector
- GraphQL-Connector
- SQL-Connector
- NoSQL-Connector


Wenn ein Connector in einen dieser Typen passt, erweitern Sie den Connector auf die entsprechende Basisklasse. Erstellen Sie sie andernfalls von Grund auf neu, indem Sie die Connector-Schnittstelle implementieren.

## Konfigurationsschnittstelle {#config-interface}

Die `Config`-Schnittstelle dient der Konfiguration einer Datenquelle mit einer bestimmten Authentifizierungsmethode, sodass Sie präzise Kontrolle darüber haben, wie Sie die Verbindung erstellen.

Die `Config` bietet Flexibilität bei der Verarbeitung und Implementierung von Authentifizierungsdetails. Verschiedene Implementierungen können verschiedene Möglichkeiten zur Authentifizierung von Datenquellen bieten. Ein Connector verwendet eine Config-Instanz, um Abfragen für eine Datenquelle auszuführen und zu validieren, wodurch ein vollständiger Workflow gebildet wird.
Ein Connector verwendet eine `Config`, um Abfragen für eine Datenquelle auszuführen und zu validieren, was einen vollständigen Workflow bildet.

Eine Konfigurationsimplementierung definiert, wie die Authentifizierung für die Verbindung mit einer Datenquelle verarbeitet wird. Diese Konfiguration wird dann von einer Connector-Implementierung verwendet, um mit der Datenquelle zu interagieren und sicherzustellen, dass Abfragen korrekt ausgeführt und validiert werden.

Insgesamt ist die `Config`-Schnittstelle ein wichtiger Teil des Workflows für die Verbindung mit Datenquellen, der sich speziell auf die Authentifizierungskonfiguration konzentriert.

### Typen von Standardimplementierungen {#default-config-types}

Es gibt drei Arten von standardmäßigen abstrakten Konfigurationsimplementierungen für die Authentifizierung:

- RestConfig
- SqlKonfiguration
- NoSqlConfig

Wenn eine Konfiguration einem dieser Typen entspricht, kann sie die entsprechende Basisklasse erweitern. Andernfalls kann sie von Grund auf neu erstellt werden, indem die Config-Schnittstelle implementiert wird.

### Konkrete Konfigurationsimplementierungen {#concrete-config-implementation}

Die *konnect-definitions*-Bibliothek enthält vordefinierte Implementierungen der Config-Schnittstelle für einige weit verbreitete Authentifizierungskonfigurationen. Sie können diese Konfigurationen direkt im Connector verwenden oder neue mithilfe der Konfigurationsoberfläche definieren. Zu diesen Implementierungen gehören:

- API-Schlüssel-Authentifizierungskonfiguration
- Einfache Konfiguration für Authentifizierungs-Token
- Einfache Authentifizierungskonfiguration
- Bearer-Token-Konfiguration
- Benutzername/Kennwort-Konfiguration für SQL
- Authentifizierungskonfiguration der Verbindungszeichenfolge für NoSQL

### Zusätzliche Ressourcen{#resources}

Mit Experience Manager Guides können Sie auch benutzerdefinierte Ressourcen für Logos und Vorlagen zusammen mit der -Implementierung bereitstellen. Sie können diese Ressourcen im `resources` Ordner belassen.
Damit sie vom Connector verwendet werden können, müssen die folgenden Connector-Funktionen implementiert werden:


- `getLogoSvg` - Gibt die Logo-SVG als Zeichenfolge zurück.

- `getTemplates` - Gibt die Liste der Vorlagen im angegebenen Format zurück.
