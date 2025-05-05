---
title: Editor-Einstellungen in Experience Manager Guides
description: Erfahren Sie mehr über die verschiedenen Einstellungen, die in der Editor-Benutzeroberfläche von Experience Manager Guides verfügbar sind.
feature: Authoring, Features of Web Editor
role: User
exl-id: fad2874f-dab5-4538-8502-f7112c51d941
source-git-commit: ffc9a9e15f11e7059822b7cf6d4707b83d15a4f4
workflow-type: tm+mt
source-wordcount: '1975'
ht-degree: 0%

---

# Editor-Einstellungen

Die Option **Einstellungen** in der [Registerkartenleiste](./web-editor-tab-bar.md) des Editors ist nur für Administratoren und Ordnerprofiladministratoren verfügbar und ermöglicht die Konfiguration der folgenden Einstellungen:

- [Allgemein](#general)
- [Bedienfelder](#panels)
- [Liste der Elemente](#elements-list)
- [Attribute Liste](#attributes-list)
- [Farben](#colors)
- [Profile veröffentlichen](#publish-profiles)
- [Validierung](#validation)
- [Attribute anzeigen](#display-attributes)
- [Übersetzung](#translation)
- [Metadaten](#metadata)


>[!NOTE]
>
> Wenn Sie Standardeinstellungen aktualisieren, sollten Sie die Dokumente erneut öffnen, damit die Änderungen wirksam werden.

## Allgemein

Mit den allgemeinen Einstellungen können Sie das Wörterbuch konfigurieren, das mit dem Editor verwendet werden soll. Diese Registerkarte enthält vier Abschnitte: **Rechtschreibprüfung**, **Bedingung**, **Authoring** und **Zitate** .

![](images/editor-setting-general.png){width="650" align="left"}

- **Rechtschreibprüfung**: Es gibt zwei Optionen: **Rechtschreibprüfung von AEM** Browser-**&#x200B;**. Standardmäßig verwendet der Editor die Rechtschreibprüfung des Browsers, wobei die Rechtschreibprüfung mit dem integrierten Wörterbuch des Browsers durchgeführt wird. Sie können zur AEM-Rechtschreibprüfung wechseln, um das Adobe Experience Manager-Wörterbuch zu verwenden, das auch angepasst werden kann, um Ihre benutzerdefinierte Wortliste hinzuzufügen. Weitere Informationen zum Anpassen des AEM-Wörterbuchs finden Sie [ Abschnitt „Anpassen des Standardwörterbuchs von AEM](../cs-install-guide/customize-aem-custom-dictionary.md) im Abschnitt Installieren und Konfigurieren von Adobe Experience Manager Guides as a Cloud Service.

- **Bedingung**

   - **Bedingten Text in der Autorenansicht hervorheben**: Wählen Sie diese Option, um den bedingten Text in der Autorenansicht hervorzuheben. Der bedingte Inhalt wird mit der für die Bedingung definierten Farbe hervorgehoben.

   - **Mit Bedingungsattributen validieren**: Wählen Sie diese Option, um die Validierung der für die Attribute definierten Werte zu ermöglichen. Dadurch wird verhindert, dass Sie einen falschen Wert hinzufügen.

   - **Schlüssel mit Titel im Bedienfeld „Betreffschema“ anzeigen**: Wählen Sie diese Option, um die Schlüssel zusammen mit Titeln im Betreffschema anzuzeigen. Wenn Sie diese Option nicht auswählen, werden nur die Titel angezeigt. Hier werden beispielsweise die Schlüssel „os“, „audience“ und „other“ zusammen mit Titeln angezeigt.

     ![](images/subject-scheme-title.png){width="550" align="left"}

   - **Betreffschema im Bedienfeld Bedingungen anzeigen**: Wählen Sie diese Option, um ein Betreffschema im Bedienfeld Bedingungen anzuzeigen. Wenn Sie diese Option deaktivieren, werden die definierten Bedingungen im Bedienfeld Bedingungen angezeigt.

- **Authoring**

   - **Alle ersetzen aktivieren**: Wählen Sie diese Option aus, um das Symbol **Alle ersetzen** im Bedienfeld **Suchen und Ersetzen** anzuzeigen.

- **Zitate**

  ändern den Stil der Zitate. Wählen Sie den Zitierstil aus der Dropdown-Liste aus, den Sie in Ihrem Projekt verwenden möchten. Weitere Informationen finden Sie Ansicht [ändern Zitierstile](./web-editor-apply-citations.md#change-citation-style).

- **KI-Assistent**
Wählen Sie diese Option aus, um die Funktion [KI](./ai-assistant.md)Assistent“ in der Experience Manager Guides zu aktivieren. Deaktivieren Sie diese Option, um die Funktion zu deaktivieren.


## Bedienfelder

Mit dieser Einstellung werden die Bereiche gesteuert, die im linken und rechten Bereich der Editor- und Zuordnungskonsole angezeigt werden. Sie können die Schaltfläche umschalten, um das gewünschte Bedienfeld ein- oder auszublenden.

![](images/editor-setting-panel.png){width="650" align="left"}

Sie können auch die Reihenfolge festlegen, in der die in Bedienfeldern vorhandenen Funktionen angezeigt werden. Um die Standard bestellen der verfügbaren Features in den Bereichen zu ändern, wählen Sie die gepunkteten Balken aus, um die Feature-Registerkarten per Drag &amp; Drop an die gewünschte Position zu ziehen. Ein Feature kann je nach Anforderung auch vom **Mehr** Abschnitt in den Hauptabschnitt eines Bedienfelds verschoben werden und umgekehrt. Nach der Neuanordnung werden die Features im gleichen Sequenz im jeweiligen rechten und linken Bereich angezeigt.

![](images/panels-screen.png){width="650" align="left"}


Es können maximal acht Bereiche gleichzeitig angezeigt werden. Alle an den Bedienfeldeinstellungen vorgenommenen Änderungen werden sofort angewendet.


>[!NOTE]
>
> Wenn ein benutzerdefiniertes Bedienfeld konfiguriert wurde, wird es auch im Liste von Bedienfeldern angezeigt. Sie können den Schalter umschalten, um das benutzerdefinierte Bedienfeld anzuzeigen oder zu verstecken.

## Elemente Liste

Als Administrator können Sie die Liste von Elementen steuern, die ein Autor in eine Datei einfügen kann, und auch den Anzeigenamen für das Element definieren. Mit der Einstellung &quot;Elemente Liste&quot; können Sie den Namen des Elements gemäß den DITA-Spezifikationen und eine Beschriftung angeben, die Sie anstelle des von der DITA definierten Elementnamens verwenden möchten:

![](images/editor-setting-element-list.png){width="650" align="left"}

In der obigen Screenshot hat das `p` Element die Beschriftung &quot;Absatz&quot; erhalten und `codeblock` erhält zusammen mit einigen anderen Elementen die Beschriftung &quot;Symbol Block&quot;. Wenn Sie die **Option Nur über Elementen** verwenden auswählen, werden nur die gültigen Elemente \(am aktuellen Einfügepunkt\) aus diesem Liste im **Dialogfeld Einfügen Element** angezeigt.

Im folgenden Screenshot werden nur 3 von 4 konfigurierten Elementen aus dem vorherigen Screenshot im aktuellen Kontext angezeigt:

![](images/editor-setting-insert-element-list.PNG){width="300" align="left"}

## Attribute Liste

Ähnlich wie bei den Liste Elementen können Sie die Liste von Attributen und deren Anzeigenamen steuern, die in den Attributen Liste eines Elements angezeigt werden sollen. Im folgenden Screenshot wurden nur 3 Attribute für die Anzeige im Attribut eines Elements Liste konfiguriert:

![](images/editor-setting-attributes-list.png){width="650" align="left"}

Wenn Sie mit dieser Einstellung versuchen, einem Element ein Attribut hinzuzufügen, Ansicht Sie nur die Liste der im Liste konfigurierten Attribute.

![](images/editor-setting-add-attributes-list.png){width="300" align="left"}


## Farben

Zeigt eine Liste der vorkonfigurierten Hintergrundfarben für (**)**. Benutzer können beim Anwenden einer Bedingung auf ein Thema eine Hintergrundfarbe auswählen. Als Administrator können Sie auch benutzerdefinierte Hintergrundfarben erstellen und zur Liste hinzufügen. Um eine neue Farbe hinzuzufügen, geben Sie den gewünschten Namen in das Feld **Farbname** ein, wählen Sie eine benutzerdefinierte Farbe aus und klicken Sie auf das Symbol **+** . Die benutzerdefinierte Farbe wird am Ende der Farbliste angezeigt.

## Profile veröffentlichen

Enthält die Profile, mit denen die Ausgabe der **Wissensdatenbank** veröffentlicht werden kann. Sie können für eine Target-Komponente Knowledgebase eine neue Profil erstellen. Zum Beispiel Salesforce oder ServiceNow.

**Salesforce-Profil Erstellen**

**Voraussetzungen**

- Erstellen eine vernetzte Anwendung für Salesforce. Weitere Informationen finden Sie unter [Aktivieren der OAuth-Einstellungen für die API-Integration](https://help.salesforce.com/s/articleView?id=sf.connected_app_create_api_integration.htm&amp;type=5).

- Stellen Sie beim Konfigurieren der verbundenen Anwendung Folgendes sicher:

   - Geben Sie den Rückruf an.

     `URL: http://<server name>:<port>/bin/dxml/thirdparty/callback/salesforce`

   - Wählen Sie die folgenden OAuth-Bereiche aus:
      - Vollständiger Zugriff (vollständig)
      - Wählen Sie Benutzerdaten über APIs verwalten (API) aus

     Sobald die App konfiguriert ist, stellt Salesforce einen **Consumer Key** und **Consumer Secret** bereit. Diese können zum Erstellen des Salesforce-Profils verwendet werden.


   - Um eine Salesforce-Profil zu erstellen, wählen Sie die **Basis Salesforce-Wissen aus der** Dropdown-Liste &quot;Typ **Server**&quot; aus. Geben Sie einen Profilnamen ein. Geben Sie **Site-URL** die Verbraucherwebsite ein, mit der Sie die Ausgabe veröffentlichen möchten, und fügen Sie dann den **Consumer Key** und **Consumer Secret** hinzu, die von der Salesforce-Verbraucherwebsite bereitgestellt werden. Wählen Sie dann **Validieren** und **Speichern** das neu erstellte Profil aus.

     ![Salesforce-Veröffentlichungsprofil in Editor-Einstellungen](./images/salesforce-publish-profile.png){width="550" align="left"}

     >[!NOTE]
     >
     >Verwenden Sie zum Konfigurieren eines Proxys für Salesforce in Experience Manager Guides die Apache-HTTP-Komponenten-Proxy-Konfiguration in AEM. Erfahren Sie, wie [Proxy für den AEM Link Checker konfigurieren](https://helpx.adobe.com/experience-manager/kb/How-to-configure-proxy-for-the-AEM-Link-Checker-AEM.html).


**Erstellen eines ServiceNow-Profils**

**Voraussetzungen**

Konfigurieren Sie den ServiceNow-Server, um die Assets hochzuladen.

- Stellen Sie eine Verbindung mit dem **ServiceNow**-Server her.
- Navigieren Sie **Systemeigenschaften** > **Sicherheit**.
- Deaktivieren Sie die folgende Option:

  **Diese Eigenschaft muss so eingestellt sein, dass die MIME-Typprüfung für Uploads (alle Versionen von Eureka und höher) aktiviert wird. Aktiviert (true) oder deaktiviert (false) die Validierung des MIME-Typs für die Dateianhänge. Dateierweiterungen, die über glide.attachment.extensions konfiguriert werden, werden während des Uploads auf MIME-Typ überprüft.**

- Wählen Sie **Speichern** aus.

  Nachdem Sie die App konfiguriert haben, erstellen Sie das Profil **ServiceNow**.

- Um ein Profil zu erstellen, wählen Sie die ServiceNow-Wissensdatenbank aus der Dropdown-Liste **Servertyp** aus. Geben Sie ein Profil **Name** ein. Geben Sie unter **ServiceNow** URL die Verbraucherwebsite ein, die Sie für die Veröffentlichung der Ausgabe verwenden möchten, und fügen Sie dann den **Benutzernamen** und das **Kennwort** hinzu, die von der ServiceNow-Verbraucherwebsite bereitgestellt werden. Wählen Sie dann **Validieren** und **Speichern** das neu erstellte Profil aus.

  ![ServiceNow-Veröffentlichungsprofil](./images/service-now-publish-profile.png){width="550" align="left"}

  Nach der Validierung können Sie das Veröffentlichungsprofil in den Ausgabevorgaben einer DITA-Zuordnung auswählen und es zum Generieren der Ausgabe für den ausgewählten **Salesforce**- oder **ServiceNow**-Server verwenden.

  Erfahren Sie mehr über die [Wissensdatenbank](../user-guide/generate-output-knowledge-base.md)-Ausgabevorgabe.


## Validierung

Diese Registerkarte enthält Optionen zum Konfigurieren der Schematron-Validierungen im Editor. Sie können die folgenden Funktionen aktivieren:

- **Vor dem Speichern der Datei** Tauglichkeitsprüfung Prüfung ausführen: Wählen Sie diese Option aus, um Schematron-Validierungen mit den ausgewählten Schematron-Dateien vor dem Speichern auszuführen. Sie können eine Schematron-Datei hinzufügen, indem Sie auf das Plus-Zeichen (+) klicken. Die ausgewählte(n) Schematron-Datei(en) werden aufgeführt.

  >[!NOTE]
  >
  > Die ausgewählte(n) Schematron-Datei(en) bleiben für das ausgewählte Ordnerprofil erhalten.

  ![Validierung in Editor-Einstellungen](./images/editor-setting-validation.png){width="550" align="left"}

  Dies verhindert, dass Benutzer eine Datei speichern, die gegen eine in der/den ausgewählten Schematron-Datei(en) definierte Regel verstößt. Wenn diese Option nicht ausgewählt ist, wird die Datei vor dem Speichern der Änderungen nicht validiert.

- **Zulassen, dass alle Benutzer Schematron-Dateien im Validierungsbereich hinzufügen**: Wählen Sie diese Option aus, damit die Benutzer im Validierungsbereich des Editors beliebige Schematron-Dateien hinzufügen können. Auf diese Weise können Benutzer Schematron-Dateien hinzufügen und dann die Themen anhand der Schematron-Datei validieren. Wenn diese Option nicht ausgewählt ist, steht die Schaltfläche zum Hinzufügen **Schematrondatei** Schematrondatei hinzufügen“ den Benutzenden im **Validierungsbereich** des Editors nicht zur Verfügung.


## Attribute anzeigen

Wie bei der Attributliste können Sie die Liste der Attribute steuern, die in der Attributliste eines Elements angezeigt werden sollen. Standardmäßig wurden vier **Anzeigeattribute** - Zielgruppe, Plattform, Produkt und Eigenschaften so konfiguriert, dass sie in der Attributliste eines Elements angezeigt werden. Sie können ein Anzeigeattribut auch mit dem Symbol **Hinzufügen** oben hinzufügen. Sie können auch jedes der Anzeigeattribute über das Symbol **Löschen** löschen.

Die für ein Element definierten Attribute werden im Layout- und Gliederungsansicht angezeigt.

![](images/editor-settings-display-attributes.png){width="550" align="left"}

## Übersetzung

Diese Registerkarte enthält die Optionen zum Erstellen von Sprachgruppen, zum Übertragen der Quellkennzeichnungen in die Zielversion und zum Bereinigen des Übersetzungsprojekts.

![](images/editor-setting-translation.png){width="550" align="left"}

- **Sprachgruppen**: Als Administrator können Sie eine Gruppe von Sprachen erstellen und sie als Gruppe verwenden, um die Inhalte zu übersetzen.

  Führen Sie die folgenden Schritte aus, um eine neue Sprachgruppe zu erstellen:

   1. Wählen Sie **Hinzufügen** aus.
   1. Geben Sie die Sprache Gruppe den Namen ein. Jede Sprache sollte einen eindeutigen Namen haben. Wenn das Feld &quot;Name&quot; leer ist oder der Name nicht eindeutig ist, können Sie einen Fehler Ansicht.
   1. Wählen Sie die Sprachen aus der Dropdown-Liste aus. Sie können mehrere Sprachen auswählen.

      Geben Sie die ersten Zeichen der Sprache oder den Sprach-Code ein, um die gewünschten Sprachen zu filtern. Geben Sie beispielsweise &quot;en&quot; ein, um alle Sprachen zu filtern, die &quot;en&quot; am Anfang ihres Namens oder Codes enthalten.

   1. Wählen Sie das Symbol Fertig aus, um der Gruppe die ausgewählten Sprachen hinzuzufügen. Die Sprachen werden angezeigt. Wenn Sie drei oder mehr Sprachen hinzufügen, wird **Option „Mehr anzeigen** angezeigt. Sie können auf **Mehr anzeigen** klicken, um alle in der Gruppe vorhandenen Sprachen anzuzeigen.

      >[!TIP]
      >
      > Schalten Sie **Mehr anzeigen** auf **Weniger anzeigen** um und zeigen Sie nur einige Sprachen an.

   1. Bewegen Sie den Mauszeiger über die Sprachen in einer Gruppe, um ![ Sprachgruppen zu bearbeiten ](images/edit_pencil_icon.svg)Bearbeiten-Symbol![ oder zu löschen](images/Delete_icon.svg).
   1. Speichern die **Einstellungen**.

      >[!NOTE]
      >
      >Als User können Sie die für Ihren Ordner konfigurierten Sprachgruppen Profil Ansicht.

- **Quellversionsbezeichnungen an die Target-Komponente** Version weitergeben: Aktivieren Sie diese Option, um die Bezeichnung der Quelldateiversion an die übersetzte Datei zu übergeben. Standardmäßig ist diese Einstellung deaktiviert.
- **Bereinigung von Übersetzungsprojekten nach Abschluss**: Wählen Sie diese Option aus, um die Übersetzungsprojekte so zu konfigurieren, dass sie nach der Übersetzung automatisch deaktiviert oder gelöscht werden. Standardmäßig ist &quot;Keine **&quot;** ausgewählt, sodass das Projekt nach der Übersetzung vorhanden ist.

  Sie können die Übersetzungsprojekte deaktivieren, wenn Sie sie später verwenden möchten. Wenn Sie ein Projekt löschen, werden alle darin vorhandenen Dateien und Ordner dauerhaft gelöscht.


## Metadaten

Sie können die Versionsmetadaten des Themas und ihre Werte steuern, die im Dialogfeld **Versionsverlauf** angezeigt werden.  Geben Sie im Metadatenpfad den Speicherort der Knoten an, aus denen Sie die Metadaten auswählen möchten. Sie können auch einen benutzerdefinierten Namen für die Metadaten als Beschriftung definieren. Die Standardeigenschaften sind Titel, Dokumentstatus und Tags.

Die Metadaten können aus jeder Eigenschaft unter dem `/jcr:content` des Assets ausgewählt werden, sodass Sie den Pfad der Eigenschaft als Metadatenpfad hinzufügen können.


Ein Fehler wird angezeigt, wenn die Metadaten Pfad leer ist. Wenn Sie das Feld leer lassen, wird das letzte Element als Titel ausgewählt.


![Registerkarte „Metadaten“ in den Editor-Einstellungen](images/editor-setting-metadata.png){width="550" align="left"}

*Konfigurieren der Metadaten für das Dialogfeld **Versionsverlauf**.*



Sie können auch die Reihenfolge festlegen, in der diese Metadaten-Tags angezeigt werden. Um die Standardreihenfolge dieser Tags zu ändern, wählen Sie die gepunkteten Balken aus, um die Tags per Drag-and-Drop an die gewünschte Position zu ziehen.
Die Metadatenbeschriftungen werden im Dialogfeld **Versionsverlauf** des Editors in derselben Reihenfolge angezeigt.

**Übergeordnetes Thema:**&#x200B;[ Einführung in den Editor](web-editor.md)
