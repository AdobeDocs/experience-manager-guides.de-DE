---
title: Konfigurieren eines Datenquellen-Connectors mit Tools
description: Erfahren Sie, wie Sie mithilfe der Tools einen Datenquellen-Connector konfigurieren.
exl-id: d7cd412b-89ea-43a5-97b3-09944863bbee
feature: Web Editor Configuration
role: Admin
level: Experienced
source-git-commit: 873542cb2e8e1b7e80e0ecc113cae4f603b18592
workflow-type: tm+mt
source-wordcount: '902'
ht-degree: 0%

---

# Konfigurieren eines Datenquellen-Connectors über die Benutzeroberfläche

Experience Manager-Handbücher enthalten die **Data Sources** -Tool, mit dem Sie native Connectoren für Datenquellen konfigurieren können. Sie können die Connectoren JIRA, SQL (MySQL, PostgreSQL, Microsoft SQL Server, SQLite, MariaDB, H2DB), AdobeCommerce, Elasticsearch und Generic REST Client einrichten.


Neben diesen vordefinierten Connectoren bieten die Experience Manager Guides die Connectoren für die Datenquellen Salsify, Akeneo und Microsoft Azure DevOps Boards (ADO). Sie können diese Open-Source-Connectoren über die [Maven Central Repository](https://central.sonatype.com/search?q=com.adobe.aem.addon.guides). Die Benutzer können diese Connectoren dann konfigurieren.
Erfahren Sie, wie [einen Open-Source-Connector installieren](#install-open-source-connector).



Sie können auch über einen Datei-Connector eine Verbindung zu JSON-Datendateien herstellen. Laden Sie die JSON-Datei von Ihrem Computer hoch oder durchsuchen Sie sie über die Adobe Experience Manager-Assets. Erstellen Sie dann mithilfe der Generatoren Inhaltsfragmente oder Themen.

Um einen Connector zu konfigurieren, führen Sie die folgenden Schritte aus:

1. Wählen Sie die **Adobe Experience Manager** oben klicken und &quot;Tools&quot;auswählen.
1. Auswählen **Handbücher** aus der Liste der Tools.
1. Wählen Sie die **Data Sources** Kachel. Die **Data Sources** angezeigt. Sie können die verbundenen Datenquellen anzeigen.

   Sie können zwischen **Listenansicht** oder **Kachelansicht** um die verschiedenen verbundenen Datenquellen als Liste oder Kacheln anzuzeigen.

   <img src="./assets/data-sources-create-window.png" alt= "Datenquellen, die auf der Seite &quot;Datenquellen&quot;aufgelistet sind" width="800">

   *Anzeigen oder Erstellen eines Datenquellen-Connectors*
1. Klicken Sie auf **Erstellen**.
1. Wählen Sie die Datenbank aus, für die Sie den Connector erstellen möchten. Beispielsweise der Elasticsearch-Connector.
   >[!NOTE]
   >
   >Alle verfügbaren nativen Datenbanken werden aufgelistet.

1. Klicken Sie auf **Weiter**.
1. Geben Sie die Konfigurations- und Verbindungsdetails gemäß der Datenbank ein.

   >[!TIP]
   >
   >* Bewegen <img src="./assets/info-details.svg" alt= "Infosymbol" width="25"> neben dem Feld, um weitere Details dazu anzuzeigen.
   > * Felder mit * sind obligatorisch. Sie können beispielsweise die folgenden Details für den Elasticsearch-Connector eingeben.

   * **Name**: Geben Sie den Namen der Datenquelle ein.
   * **Authentifizierungstyp**: Wählen Sie den Authentifizierungstyp aus der Dropdown-Liste aus. Beispiel: Grundlegende Authentifizierung mit Benutzername und Kennwort
   * **Benutzername**: Geben Sie Ihren Benutzernamen ein.
   * **Passwort**: Geben Sie Ihren Benutzernamen und Ihr Kennwort ein.
   * **URL**: Hinzufügen der API-URL.


1. Wählen Sie die **Werksvorlagen ausschließen** -Option, um die Factory-Vorlagen von der Verwendung für die Themen- und Snippet-Generierung auszuschließen. Sie werden nicht unter dem **Datenzuordnungsvorlage** Dropdown im  **Inhaltsfragment-Generator hinzufügen** oder **Themengenerator hinzufügen** Dialogfeld.


1. Auswählen **Verbindung testen**. Sie können die **Verbindung testen** -Schaltfläche nur aktiviert ist, nachdem Sie die erforderlichen Details hinzugefügt haben. Zeigen Sie eine Erfolgsmeldung an, wenn die Verbindungsdetails korrekt sind. Andernfalls wird möglicherweise eine Fehlermeldung angezeigt.



1. Auswählen **Speichern** oben, um den Connector zu speichern.     Anzeigen der **Speichern** -Schaltfläche aktiviert, nachdem Sie alle Details ausgefüllt haben und die Verbindung erfolgreich hergestellt wurde.


   Wenn der Connector erfolgreich gespeichert wurde, können Sie die verbundene Datenquelle auf der Seite anzeigen.

**Verbindung zu mehreren Ressourcen herstellen**

Sie können für einige Connectoren wie generischer REST Client, Salsify, Akeneo und Microsoft Azure DevOps-Pinnwände (ADO) mehrere Ressourcen hinzufügen oder verwenden, die auf unterschiedlichen URLs basieren. Stellen Sie dann eine Verbindung mit ihnen her, um mithilfe der Generatoren Inhaltsfragmente oder Themen zu erstellen.

Führen Sie die folgenden Schritte aus, um eine Ressource zu erstellen:

1. Auswählen ![Symbol hinzufügen](assets/Add_icon.svg) im **URL-Ressourcenabschnitt** , um für jede URL eine Ressource hinzuzufügen.
1. Konfigurieren Sie alle Details im **Ressource hinzufügen** Dialogfeld.
1. Klicken Sie auf **Hinzufügen**.
1. Sie können ![Bearbeitungssymbol](assets/edit_pencil_icon.svg) oder löschen ![delete](assets/Delete_icon.svg) die Ressource aus der URL-Ressourcenliste.

1. Sie können auch die Standardressourcen verwenden, die für Datenquellen wie Salsify, Akeneo und Microsoft ADO verfügbar sind. Schalten Sie die Optionen für die Ressource aus, die Sie nicht für eine Datenquelle konfigurieren möchten.

Auf diese Weise können Sie schnell Daten aus einer der Ressourcen für eine bestimmte Datenquelle in einem einzelnen Inhaltsfragment oder Thema abrufen.



## Installieren eines Open-Source-Connectors{#install-open-source-connector}

So veröffentlichen Sie eine Abhängigkeit auf der [Maven Central Repository](https://central.sonatype.com/search?q=com.adobe.aem.addon.guides) den Cloud Services hinzufügen, müssen Sie die Abhängigkeit für einen Open-Source-Connector einbeziehen und einbetten.

1. Fügen Sie die Abhängigkeit in `all/pom.xml`  in Ihrem Cloud Manager-Git-Projektcode. Sie können beispielsweise die folgende Abhängigkeit für den Datenquellen-Connector für Microsoft Azure DevOps-Pinnwände hinzufügen.


   ```
   <dependency>
       <groupId>com.adobe.aem.addon.guides</groupId>
       <artifactId>konnect-azure-devops</artifactId>
       <version>1.0.0</version>
       <type>jar</type>
   </dependency> 
   ```

1. Betten Sie die hinzugefügte Abhängigkeit ein.

       &quot;
       &lt;embedded>
       &lt;groupid>com.adobe.aem.addon.guides&lt;/groupid>
       &lt;artifactid>konnect-azure-devops&lt;/artifactid>
       &lt;type>jar&lt;/type>
       &lt;target>/apps/aemdoxonaemcsstageprogram-vendor-packages/content/install&lt;/target>
       &lt;/embedded>
       &quot;
   
1. Führen Sie die Pipeline aus, um die Änderungen auf die Cloud Service anzuwenden.
Der Connector ist in Ihrer Umgebung installiert.


## Für einen Connector verfügbare Funktionen

* Zwischen den **Listenansicht** oder **Kachelansicht**  um die verschiedenen verbundenen Datenquellen als Liste oder Kacheln anzuzeigen.
* Aktivieren Sie das Kontrollkästchen für einen einzelnen Connector. Klicks **Alle auswählen** , um alle Connectoren auszuwählen. Sie können auf **Auswahl für alle aufheben** wenn alle Connectoren ausgewählt sind.

<img src="./assets/data-sources-features.png" alt= "Funktionen der Datenquellen auf der Seite &quot;Datenquellen&quot;" width="800">

*Bearbeiten, erneutes Verbinden, Duplizieren oder Löschen eines Datenquellen-Connectors.*

Sie können die folgenden Funktionen für den Connector auf der **Data Sources** Seite:

* **Bearbeiten**: Bearbeiten Sie die Konfigurationsdetails für den ausgewählten Connector.

* **Wiederholen**: Schließen Sie eine Verbindung zu einem getrennten Connector wieder her.

* **Duplizieren**: Erstellen Sie einen neuen doppelten Connector mit dem aktuellen Connector als Basis. Der doppelte Connector wird standardmäßig mit einem Suffix (wie connectorname_1) erstellt. Beispiel: sample-elastisches-search_1.
Wenn der Connector mit demselben Namen vorhanden ist, wird ein Fehler angezeigt.

* **Löschen**: Löschen Sie den ausgewählten Connector.


Nachdem Sie die Datenquelle konfiguriert haben, wird der Connector unter der **Data Sources-Bedienfeld** im Web-Editor. Anschließend können Sie eine Verbindung zur Datenquelle herstellen und ein Inhaltsfragment in Ihre Themen einfügen. Weitere Informationen finden Sie unter [Inhaltsfragment aus Ihrer Datenquelle einfügen](../user-guide/web-editor-content-snippet.md).
