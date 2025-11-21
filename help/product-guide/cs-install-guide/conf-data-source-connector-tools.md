---
title: Konfigurieren eines Datenquellen-Connectors mithilfe von Tools
description: Erfahren Sie, wie Sie einen Datenquellen-Connector mithilfe der Tools konfigurieren.
exl-id: d7cd412b-89ea-43a5-97b3-09944863bbee
feature: Web Editor Configuration
role: Admin
level: Experienced
source-git-commit: 6e23f52fc9124d0f07f8108da1b5fe574f553469
workflow-type: tm+mt
source-wordcount: '883'
ht-degree: 0%

---

# Konfigurieren eines Datenquellen-Connectors über die Benutzeroberfläche

Experience Manager Guides enthält das Tool **Datenquellen** mit dem Sie vordefinierte Connectoren für Datenquellen konfigurieren können. Sie können die JIRA-, SQL- (MySQL, PostgreSQL, Microsoft SQL Server, SQLite, MariaDB, H2DB), AdobeCommerce-, Elasticsearch- und generischen REST-Client-Connectoren einrichten.


Neben diesen vordefinierten Connectoren stellt Experience Manager Guides die Connectoren für die Datenquellen Salsify, Akeneo und Microsoft Azure DevOps Boards (ADO) bereit. Sie können diese Open-Source-Connectoren aus dem [Maven Central Repository“ herunterladen und ](https://central.sonatype.com/search?q=com.adobe.aem.addon.guides). Die Benutzer können dann diese Connectoren konfigurieren.
Erfahren Sie, wie [einen Open-Source-Connector installieren](#install-open-source-connector).



Sie können auch eine Verbindung zu JSON-Datendateien über einen Datei-Connector herstellen. Laden Sie die JSON-Datei von Ihrem Computer hoch oder durchsuchen Sie sie über die Adobe Experience Manager-Assets. Erstellen Sie dann Inhaltsfragmente oder Themen mithilfe der Generatoren.

Um einen Connector zu konfigurieren, führen Sie die folgenden Schritte aus:

1. Wählen Sie oben den Link **Adobe Experience Manager** und dann „Tools“ aus.
1. Wählen Sie **Guides** aus der Liste der Tools aus.
1. Wählen Sie die **Datenquellen** aus. Die **Datenquellen** wird angezeigt. Sie können die verbundenen Datenquellen anzeigen.

   Sie können zwischen der **Listenansicht** oder **Kachelansicht** wechseln, um die verschiedenen verbundenen Datenquellen als Liste oder als Kacheln anzuzeigen.

   <img src="./assets/data-sources-create-window.png" alt= "Auf der Seite „Datenquellen“ aufgeführte Datenquellen" width="800">

   *Anzeigen oder Erstellen eines Datenquellen-Connectors.*

1. Klicken Sie auf **Erstellen**.
1. Wählen Sie die Datenbank aus, für die Sie den Connector erstellen möchten. Beispiel: der Elasticsearch-Connector.

   >[!NOTE]
   >
   >Alle verfügbaren vordefinierten Datenbanken werden aufgelistet.

1. Klicken Sie auf **Weiter**.
1. Geben Sie die Konfigurations- und Verbindungsdetails gemäß der Datenbank ein.

   >[!TIP]
   >
   >* Bewegen Sie den Mauszeiger über <img src="./assets/info-details.svg" alt= "Infosymbol" width="25"> in der Nähe des Felds, um weitere Details dazu anzuzeigen.
   >* Felder mit * sind Pflichtfelder. Sie können beispielsweise die folgenden Details für den Elasticsearch-Connector eingeben.

   * **Name**: Geben Sie den Namen der Datenquelle ein.
   * **Authentifizierungstyp**: Wählen Sie in der Dropdown-Liste den Authentifizierungstyp aus. Beispiel: Einfache Benutzername-Kennwort-Authentifizierung
   * **Benutzername**: Geben Sie Ihren Benutzernamen ein.
   * **Kennwort**: Geben Sie Ihren Benutzernamen und Ihr Kennwort ein.
   * **URL**: API-URL hinzufügen.


1. Wählen Sie die Option **Werksvorlagen ausschließen**, um die Werksvorlagen von der Verwendung für die Erstellung von Themen und Ausschnitten auszuschließen. Sie werden nicht in der Dropdown **Liste Datenzuordnungsvorlage** im Dialogfeld **Inhaltsfragmentgenerator hinzufügen** oder **Themengenerator hinzufügen** angezeigt.
1. Wählen Sie **Verbindung testen** aus. Sie können die Schaltfläche **Verbindung testen** erst anzeigen, nachdem Sie die erforderlichen Details hinzugefügt haben. Zeigt eine Erfolgsmeldung an, wenn die Verbindungsdetails korrekt sind. Andernfalls wird möglicherweise eine Fehlermeldung angezeigt.
1. Wählen **oben** Speichern“ aus, um den Connector zu speichern.     Die Schaltfläche **Speichern** wird aktiviert, nachdem Sie alle Details ausgefüllt haben und die Verbindung erfolgreich hergestellt wurde.


   Wenn der Connector erfolgreich gespeichert wurde, können Sie die verbundene Datenquelle auf der Seite anzeigen.

**Verbindung zu mehreren Ressourcen herstellen**

Sie können mehrere Ressourcen auf der Grundlage verschiedener URLs für einige Connectoren wie Generic REST Client, Salsify, Akeneo und Microsoft Azure DevOps Boards (ADO) hinzufügen oder verwenden. Verbinden Sie sich dann mit ihnen, um Inhaltsfragmente oder Themen mithilfe der Generatoren für sie zu erstellen.

Führen Sie die folgenden Schritte aus, um eine Ressource zu erstellen:

1. Wählen Sie ![Symbol hinzufügen](assets/Add_icon.svg) im Abschnitt **URL-Ressource** aus, um für jede URL eine Ressource hinzuzufügen.
1. Konfigurieren Sie alle Details im Dialogfeld **Ressource hinzufügen**.
1. Klicken Sie auf **Hinzufügen**.
1. Sie können ![Bearbeitungssymbol](assets/edit_pencil_icon.svg) bearbeiten oder ![ Ressource aus ](assets/Delete_icon.svg) URL-Ressourcenliste löschen.
1. Sie können auch die Standardressourcen verwenden, die für Datenquellen wie Salsify, Akeneo und Microsoft ADO verfügbar sind. Schalten Sie die Optionen für die Ressource aus, die Sie nicht für eine Datenquelle konfigurieren möchten.

Auf diese Weise können Sie schnell Daten aus einer der Ressourcen für eine bestimmte Datenquelle in einem einzelnen Inhaltsfragment oder Thema abrufen.



## Installieren eines Open-Source-Connectors{#install-open-source-connector}

Um eine Abhängigkeit im [Maven Central Repository](https://central.sonatype.com/search?q=com.adobe.aem.addon.guides) in den Cloud-Services zu veröffentlichen, müssen Sie die Abhängigkeit für einen Open-Source-Connector einschließen und einbetten.

1. Fügen Sie die Abhängigkeit in `all/pom.xml` in Ihrem Cloud Manager-Git-Projekt-Code hinzu. Sie können beispielsweise die folgende Abhängigkeit für den Microsoft Azure DevOps Boards-Datenquellen-Connector hinzufügen.


   ```
   <dependency>
       <groupId>com.adobe.aem.addon.guides</groupId>
       <artifactId>konnect-azure-devops</artifactId>
       <version>1.0.0</version>
       <type>jar</type>
   </dependency> 
   ```

1. Betten Sie die hinzugefügte Abhängigkeit ein.

   ```
   <embedded>
       <groupId>com.adobe.aem.addon.guides</groupId>
       <artifactId>konnect-azure-devops</artifactId>
       <type>jar</type>
       <target>/apps/aemdoxonaemcsstageprogram-vendor-packages/content/install</target>
   </embedded> 
   ```

1. Führen Sie die Pipeline aus, um die Änderungen in den Cloud-Services anzuwenden.
Der Connector wird in Ihrer Umgebung installiert.


## Für einen Connector verfügbare Funktionen

* Schalten Sie zwischen **Listenansicht** oder **Kachelansicht** um, um die verschiedenen verbundenen Datenquellen als Liste oder als Kacheln anzuzeigen.
* Aktivieren Sie das Kontrollkästchen für einen einzelnen Connector. Klicken Sie **Alle auswählen**, um alle Anschlüsse auszuwählen. Sie können auf **Auswahl aufheben** klicken, wenn alle Connectoren ausgewählt sind.

<img src="./assets/data-sources-features.png" alt= "Funktionen der Datenquellen auf der Seite „Datenquellen“" width="800">

*Bearbeiten, Erneutes Verbinden, Duplizieren oder Löschen eines Datenquellen-Connectors.*

Sie können die folgenden Funktionen für den Connector auf der Seite **Datenquellen** verwenden:

* **Bearbeiten**: Bearbeiten Sie die Konfigurationsdetails für den ausgewählten Connector.

* **Erneut verbinden**: Erneut mit einem getrennten Connector verbinden.

* **Duplizieren**: Erstellen Sie einen neuen doppelten Connector, indem Sie den aktuellen Connector als Basis verwenden. Der doppelte Connector wird standardmäßig mit einem Suffix (wie connectorName_1) erstellt. Beispiel: sample-elastische-search_1.
Wenn der Connector mit demselben Namen vorhanden ist, wird ein Fehler angezeigt.

* **Löschen**: Löscht den ausgewählten Connector.


Nachdem Sie die Datenquelle konfiguriert haben, wird der Connector unter dem **Datenquellenbedienfeld** im Web-Editor aufgeführt. Anschließend können Sie eine Verbindung zur Datenquelle herstellen und ein Inhaltsfragment in Ihre Themen einfügen. Weitere Informationen finden Sie unter [Einfügen eines Inhaltsausschnitts aus Ihrer Datenquelle](../user-guide/web-editor-content-snippet.md).
