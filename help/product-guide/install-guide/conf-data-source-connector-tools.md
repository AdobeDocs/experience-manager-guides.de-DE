---
title: Konfigurieren eines Datenquellen-Connectors mit Tools
description: Erfahren Sie, wie Sie mithilfe der Tools einen Datenquellen-Connector konfigurieren.
exl-id: 2a0ac0a0-b2a9-453e-851b-fb04c8903526
feature: Web Editor Configuration
role: Admin
level: Experienced
source-git-commit: 1eb4fcb33d6f905df3f543232e7040d1da42560b
workflow-type: tm+mt
source-wordcount: '539'
ht-degree: 0%

---

# Konfigurieren eines Datenquellen-Connectors über die Benutzeroberfläche

Experience Manager Guides enthält das Tool **Data Sources** , mit dem Sie native Connectoren für Datenquellen konfigurieren können. Sie können Connectoren für die Datenbanken JIRA, SQL (MySQL, PostgreSQL, Microsoft SQL Server, SQLite, MariaDB, H2DB), AdobeCommerce und Elasticsearch einrichten.

Um einen Connector zu konfigurieren, führen Sie die folgenden Schritte aus:

1. Wählen Sie oben den Link **Adobe Experience Manager** aus und wählen Sie &quot;Tools&quot;.
1. Wählen Sie **Guides** aus der Liste der Tools aus.
1. Wählen Sie die Kachel **Datenquellen** aus. Die Seite **Data Sources** wird angezeigt. Sie können die verbundenen Datenquellen anzeigen.

   Sie können zwischen der **Listenansicht** oder der **Kachelansicht** umschalten, um die verschiedenen verbundenen Datenquellen als Liste oder Kacheln anzuzeigen.

   <img src="./assets/data-sources-create-window.png" alt= "Datenquellen, die auf der Seite &quot;Datenquellen&quot;aufgelistet sind" width="800">

   *Anzeigen oder Erstellen eines Datenquellen-Connectors.*
1. Klicken Sie auf **Erstellen**.
1. Wählen Sie die Datenbank aus, für die Sie den Connector erstellen möchten. Beispielsweise der Elasticsearch-Connector.
   >[!NOTE]
   >
   >Alle verfügbaren nativen Datenbanken werden aufgelistet.

1. Klicken Sie auf **Weiter**.
1. Geben Sie die Konfigurations- und Verbindungsdetails gemäß der Datenbank ein.

   >[!TIP]
   >* Bewegen <img src="./assets/info-details.svg" alt= "Infosymbol" width="25"> in der Nähe des Felds, um weitere Details dazu anzuzeigen.
   > * Felder mit * sind obligatorisch. Sie können beispielsweise die folgenden Details für den Elasticsearch-Connector eingeben.

   * **Name**: Geben Sie den Namen der Datenquelle ein.
   * Authentifizierungstyp: Wählen Sie in der Dropdown-Liste den Authentifizierungstyp aus. Beispiel: Grundlegende Authentifizierung mit Benutzername und Kennwort
   * **Benutzername**: Geben Sie Ihren Benutzernamen ein.
   * **Kennwort**: Geben Sie Ihren Benutzernamen und Ihr Kennwort ein.
   * **URL**: Fügen Sie die API-URL hinzu.

1. Wählen Sie **Verbindung testen** aus. Sie können die Schaltfläche **Verbindung testen** erst anzeigen, nachdem Sie die erforderlichen Details hinzugefügt haben. Zeigen Sie eine Erfolgsmeldung an, wenn die Verbindungsdetails korrekt sind. Andernfalls wird möglicherweise eine Fehlermeldung angezeigt.



1. Wählen Sie oben **Speichern** aus, um den Connector zu speichern.     Zeigen Sie die Schaltfläche **Speichern** an, die aktiviert ist, nachdem Sie alle Details ausgefüllt haben und die Verbindung erfolgreich hergestellt wurde.


   Wenn der Connector erfolgreich gespeichert wurde, können Sie die verbundene Datenquelle auf der Seite anzeigen.

## Für einen Connector verfügbare Funktionen

* Zwischen der **Listenansicht** oder der **Kachelansicht** wechseln, um die verschiedenen verbundenen Datenquellen als Liste oder Kacheln anzuzeigen.
* Aktivieren Sie das Kontrollkästchen für einen einzelnen Connector. Klicken Sie auf **Alle auswählen** , um alle Connectoren auszuwählen. Sie können auf &quot;**Auswahl aufheben**&quot;klicken, wenn alle Connectoren ausgewählt sind.

<img src="./assets/data-sources-features.png" alt= "Funktionen der Datenquellen auf der Seite &quot;Datenquellen&quot;" width="800">

*Bearbeiten, erneutes Verbinden, Duplizieren oder Löschen eines Datenquellen-Connectors.*

Sie können die folgenden Funktionen für den Connector auf der Seite **Data Sources** verwenden:

* **Bearbeiten**: Bearbeiten Sie die Konfigurationsdetails für den ausgewählten Connector.

* **Erneute Verbindung herstellen**: Verbinden Sie sich erneut mit einem getrennten Connector.

* **Duplizieren**: Erstellen Sie einen neuen doppelten Connector mit dem aktuellen Connector als Basis. Der doppelte Connector wird standardmäßig mit einem Suffix (wie connectorname_1) erstellt. Beispiel: sample-elastisches-search_1.
Wenn der Connector mit demselben Namen vorhanden ist, wird ein Fehler angezeigt.

* **Löschen**: Löschen Sie den ausgewählten Connector.


Nachdem Sie die Datenquelle konfiguriert haben, wird der Connector im Web Editor im Bereich **Datenquellen** aufgelistet. Anschließend können Sie eine Verbindung zur Datenquelle herstellen und ein Inhaltsfragment in Ihre Themen einfügen. Weitere Informationen finden Sie unter [Daten aus Ihrer Datenquelle verwenden](../user-guide/web-editor-content-snippet.md).

>[!NOTE]
>
>Sie können auch benutzerdefinierte Connectoren erstellen und diese mit den verschiedenen Datenquellen verwenden. Erfahren Sie, wie Sie [benutzerdefinierte Connectoren konfigurieren](../knowledge-base/kb-articles/data-source/conf-custom-data-source-connector.md).