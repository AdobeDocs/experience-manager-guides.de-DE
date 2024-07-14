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

Experience Manager Guides enthält das Tool **Data Sources** , mit dem Sie native Connectoren für Datenquellen konfigurieren können. Sie können die Connectoren JIRA, SQL (MySQL, PostgreSQL, Microsoft SQL Server, SQLite, MariaDB, H2DB), AdobeCommerce, Elasticsearch und Generic REST Client einrichten.


Neben diesen vordefinierten Connectoren stellt Experience Manager Guides die Connectoren für die Datenquellen Salsify, Akeneo und Microsoft Azure DevOps Boards (ADO) bereit. Sie können diese Open-Source-Connectoren aus dem [Maven Central Repository](https://central.sonatype.com/search?q=com.adobe.aem.addon.guides) herunterladen und installieren. Die Benutzer können diese Connectoren dann konfigurieren.
Erfahren Sie, wie Sie [einen Open-Source-Connector installieren](#install-open-source-connector).



Sie können auch über einen Datei-Connector eine Verbindung zu JSON-Datendateien herstellen. Laden Sie die JSON-Datei von Ihrem Computer hoch oder durchsuchen Sie sie über die Adobe Experience Manager-Assets. Erstellen Sie dann mithilfe der Generatoren Inhaltsfragmente oder Themen.

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
   >
   >* Bewegen <img src="./assets/info-details.svg" alt= "Infosymbol" width="25"> in der Nähe des Felds, um weitere Details dazu anzuzeigen.
   > * Felder mit * sind obligatorisch. Sie können beispielsweise die folgenden Details für den Elasticsearch-Connector eingeben.

   * **Name**: Geben Sie den Namen der Datenquelle ein.
   * **Authentifizierungstyp**: Wählen Sie den Authentifizierungstyp aus der Dropdown-Liste aus. Beispiel: Grundlegende Authentifizierung mit Benutzername und Kennwort
   * **Benutzername**: Geben Sie Ihren Benutzernamen ein.
   * **Kennwort**: Geben Sie Ihren Benutzernamen und Ihr Kennwort ein.
   * **URL**: Fügen Sie die API-URL hinzu.


1. Wählen Sie die Option **Factory-Vorlagen ausschließen** aus, um die Factory-Vorlagen von der Verwendung für die Themen- und Snippet-Generierung auszuschließen. Sie werden nicht im Dropdown-Menü **Datenzuordnungsvorlage** im Dialogfeld **Inhaltsfragmentgenerator hinzufügen** oder im Dialogfeld **Themengenerator hinzufügen** angezeigt.


1. Wählen Sie **Verbindung testen** aus. Sie können die Schaltfläche **Verbindung testen** erst anzeigen, nachdem Sie die erforderlichen Details hinzugefügt haben. Zeigen Sie eine Erfolgsmeldung an, wenn die Verbindungsdetails korrekt sind. Andernfalls wird möglicherweise eine Fehlermeldung angezeigt.



1. Wählen Sie oben **Speichern** aus, um den Connector zu speichern.     Zeigen Sie die Schaltfläche **Speichern** an, die aktiviert ist, nachdem Sie alle Details ausgefüllt haben und die Verbindung erfolgreich hergestellt wurde.


   Wenn der Connector erfolgreich gespeichert wurde, können Sie die verbundene Datenquelle auf der Seite anzeigen.

**Verbindung zu mehreren Ressourcen herstellen**

Sie können für einige Connectoren wie generischer REST Client, Salsify, Akeneo und Microsoft Azure DevOps-Pinnwände (ADO) mehrere Ressourcen hinzufügen oder verwenden, die auf unterschiedlichen URLs basieren. Stellen Sie dann eine Verbindung mit ihnen her, um mithilfe der Generatoren Inhaltsfragmente oder Themen zu erstellen.

Führen Sie die folgenden Schritte aus, um eine Ressource zu erstellen:

1. Wählen Sie ![Symbol hinzufügen](assets/Add_icon.svg) im Abschnitt **URL-Ressource** aus, um eine Ressource für jede URL hinzuzufügen.
1. Konfigurieren Sie alle Details im Dialogfeld **Ressource hinzufügen** .
1. Klicken Sie auf **Hinzufügen**.
1. Sie können das Symbol ![Bearbeiten](assets/edit_pencil_icon.svg) bearbeiten oder die Ressource ![löschen](assets/Delete_icon.svg) aus der Liste der URL-Ressourcen löschen.

1. Sie können auch die Standardressourcen verwenden, die für Datenquellen wie Salsify, Akeneo und Microsoft ADO verfügbar sind. Schalten Sie die Optionen für die Ressource aus, die Sie nicht für eine Datenquelle konfigurieren möchten.

Auf diese Weise können Sie schnell Daten aus einer der Ressourcen für eine bestimmte Datenquelle in einem einzelnen Inhaltsfragment oder Thema abrufen.



## Installieren eines Open-Source-Connectors{#install-open-source-connector}

Um eine Abhängigkeit im [Maven Central Repository](https://central.sonatype.com/search?q=com.adobe.aem.addon.guides) auf den Cloud Services zu veröffentlichen, müssen Sie die Abhängigkeit für einen Open-Source-Connector einschließen und einbetten.

1. Fügen Sie die Abhängigkeit in `all/pom.xml` in Ihrem Cloud Manager-Git-Projektcode hinzu. Sie können beispielsweise die folgende Abhängigkeit für den Datenquellen-Connector für Microsoft Azure DevOps-Pinnwände hinzufügen.


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
       &lt;groupId>com.adobe.aem.addon.guides&lt;/groupId>
       &lt;artifactId>konnect-azure-devops&lt;/artifactId>
       &lt;type>jar&lt;/type>
       &lt;target>/apps/aemdoxonaemcsstageprogram-vendor-packages/content/install&lt;/target>
       &lt;/embedded>
       &quot;
   
1. Führen Sie die Pipeline aus, um die Änderungen auf die Cloud Service anzuwenden.
Der Connector ist in Ihrer Umgebung installiert.


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


Nachdem Sie die Datenquelle konfiguriert haben, wird der Connector im Web Editor im Bereich **Datenquellen** aufgelistet. Anschließend können Sie eine Verbindung zur Datenquelle herstellen und ein Inhaltsfragment in Ihre Themen einfügen. Weitere Informationen finden Sie unter [Einfügen eines Inhaltsfragments aus Ihrer Datenquelle](../user-guide/web-editor-content-snippet.md).
