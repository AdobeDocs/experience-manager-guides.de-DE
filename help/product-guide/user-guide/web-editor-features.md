---
title: Die Editor-Funktionen kennen
description: Entdecken Sie die Funktionen des Editors in Adobe Experience Manager Guides. Kenntnis der Benutzeroberfläche des Editors, einschließlich Kopfzeilenleiste, Registerkartenleiste, Symbolleiste, linker Bereich, Inhaltsbearbeitungsbereich und rechter Bereich.
exl-id: 340cf72e-e44d-4df2-8312-50d00ac651b7
feature: Authoring, Features of Web Editor
role: User
source-git-commit: ac83f613d87547fc7f6a18070545e40ad4963616
workflow-type: tm+mt
source-wordcount: '18659'
ht-degree: 0%

---

# Die Editor-Funktionen kennen {#id176NC500V5Z}

Dieser Abschnitt führt Sie durch die verschiedenen Funktionen, die im Editor verfügbar sind. Wir können den Editor in die folgenden Abschnitte oder Bereiche unterteilen:

- [Kopfzeilenleiste](#header-bar)
- [Tabulatorleiste](#tab-bar)
- [Symbolleiste](#toolbar)
- [Linkes Bedienfeld](#left-panel)
- [Inhaltsbearbeitungsbereich](#content-editing-area)
- [Rechtes Bedienfeld](#right-panel)

Im folgenden Unterabschnitt werden die verschiedenen Abschnitte des Editors detailliert beschrieben.

## Kopfzeilenleiste

Die Kopfzeilenleiste ist die obere Leiste des Editors, in der das Adobe Experience Manager-Logo angezeigt wird (oder eine Unified Shell, wenn Sie Unified Shell als Experience Manager Guides-Benutzeroberfläche verwenden). Wenn Sie das Logo auswählen, werden Sie zur Experience Manager-Navigationsseite weitergeleitet.

![](./images/aem-home-header.png)

Verwenden Sie das Symbol **Erweitern** in der Symbolleiste, um die Kopfzeilenleiste auszublenden und den Inhaltsbereich zu maximieren. Um die Standardansicht wiederherzustellen, wählen Sie **Erweiterte Ansicht beenden** aus.


## Tabulatorleiste

Die Registerkartenleiste befindet sich oben in der Benutzeroberfläche des Editors und bietet Zugriff auf die folgenden Funktionen:

![](./images/tab-bar.png)

**Registerkarten**

Zeigt die aktuell geöffneten Themen im Editor als Datei-Registerkarten an. Sie können mehrere Themen gleichzeitig öffnen, die auf den jeweiligen Registerkarten in der Registerkartenleiste angezeigt werden. Standardmäßig können Sie die Dateititel auf den Registerkarten einsehen. Wenn Sie mit dem Mauszeiger auf eine Datei zeigen, können Sie den Dateititel und den Dateipfad als QuickInfo anzeigen.

>[!NOTE]
>
> Als Administrator können Sie auch festlegen, dass die Liste der Dateien nach Dateinamen auf den Registerkarten angezeigt wird. Wählen Sie die **Dateiname** im Abschnitt **Konfiguration der Editor-Dateien** Benutzereinstellungen[ aus](./intro-home-page.md#user-preferences).

Wenn Sie die Registerkarte Datei auswählen, wird ein Kontextmenü mit den Optionen Als neue Version speichern, Kopieren, Suchen in, Zu hinzufügen, Eigenschaften, Aufspaltung, Als PDF herunterladen und Schließen geöffnet.

**Alle speichern**

Speichert die von Ihnen vorgenommenen Änderungen in allen geöffneten Themen. Wenn mehrere Themen im Editor geöffnet sind, werden bei Auswahl von **Alle speichern** oder mithilfe der Tastenkombinationen **Strg**+**S** alle Dokumente mit einem Klick gespeichert. Sie müssen nicht jedes Dokument einzeln speichern.

>[!NOTE]
>
> Mit **Vorgang** Alle speichern“ wird keine neue Version der Themen erstellt. Um eine neue Version zu erstellen, verwenden Sie die Option **Als neue Version speichern**.

**KI-Assistent**

Ein leistungsstarkes, KI-gesteuertes Tool, das Ihre Produktivität durch intelligente Hilfe- und Authoring-Funktionen steigert. Es vereint zwei robuste KI-Funktionen - **Authoring** und **Help** - in der Experience Manager Guides-Oberfläche, sodass Sie Inhalte und Informationen aus der Experience Manager Guides-Dokumentation schneller und effizienter erstellen und aufrufen können.

>[!NOTE]
>
>Die Funktion KI-Assistent ist derzeit für Adobe Experience Manager Guides as a Cloud Service verfügbar.

**Ansicht erweitern**: Ermöglicht das Erweitern der Seitenansicht mithilfe des Symbols **Erweitern**. In dieser Ansicht ist die Kopfzeilenleiste mit dem Adobe Experience Manager-Logo ausgeblendet. Dadurch wird der Inhaltsbereich für die Bearbeitung maximiert. Um zur Standardansicht zurückzukehren, verwenden Sie das Symbol **Erweiterte Ansicht beenden**.

**Weitere Aktionen**: Ermöglicht das Navigieren zur **Assets** und **Settings**.

Die Option **Assets** führt Sie je nach Einrichtung zu einem Ziel:

- **Cloud Services**: Wenn Sie Cloud Services verwenden, gelangen Sie durch Auswahl der Option **Assets** zur Seite &quot;AEM-Navigation“.

- **On-Premise-Software**: Wenn Sie Adobe Experience Manager Guides (4.2.1 und höher) verwenden, gelangen Sie durch Auswahl der Option **Assets** zu Ihrem aktuellen Dateipfad in der Assets-Benutzeroberfläche.


Die Option **Einstellungen** ist nur für Administratoren und Ordnerprofiladministratoren verfügbar und ermöglicht die Konfiguration der folgenden Einstellungen:

>[!NOTE]
>
> Wenn Sie Standardeinstellungen aktualisieren, sollten Sie die Dokumente erneut öffnen, damit die Änderungen wirksam werden.

- **Allgemein**: Mit den allgemeinen Einstellungen können Sie das Wörterbuch konfigurieren, das mit dem Editor verwendet werden soll. Diese Registerkarte enthält vier Abschnitte: **Rechtschreibprüfung**, **Bedingung**, **Authoring** und **Zitate** .

  ![](images/editor-setting-general.png){width="650" align="left"}

   - **Rechtschreibprüfung**: Es gibt zwei Optionen: **Rechtschreibprüfung von AEM** Browser-****. Standardmäßig verwendet der Editor die Rechtschreibprüfung des Browsers, wobei die Rechtschreibprüfung mit dem integrierten Wörterbuch des Browsers durchgeführt wird. Sie können zur AEM-Rechtschreibprüfung wechseln, um das Adobe Experience Manager-Wörterbuch zu verwenden, das auch angepasst werden kann, um Ihre benutzerdefinierte Wortliste hinzuzufügen. Weitere Informationen zum Anpassen des AEM-Wörterbuchs finden Sie [ Abschnitt „Anpassen des Standardwörterbuchs von AEM](../cs-install-guide/customize-aem-custom-dictionary.md) im Abschnitt Installieren und Konfigurieren von Adobe Experience Manager Guides as a Cloud Service.

   - **Bedingung**

      - **Bedingten Text in der Autorenansicht hervorheben**: Wählen Sie diese Option, um den bedingten Text in der Autorenansicht hervorzuheben. Der bedingte Inhalt wird mit der für die Bedingung definierten Farbe hervorgehoben.

      - **Mit Bedingungsattributen validieren**: Wählen Sie diese Option, um die Validierung der für die Attribute definierten Werte zu ermöglichen. Dadurch wird verhindert, dass Sie einen falschen Wert hinzufügen.

      - **Schlüssel mit Titel im Bedienfeld „Betreffschema“ anzeigen**: Wählen Sie diese Option, um die Schlüssel zusammen mit Titeln im Betreffschema anzuzeigen. Wenn Sie diese Option nicht auswählen, werden nur die Titel angezeigt. Hier werden beispielsweise die Schlüssel „os“, „audience“ und „other“ zusammen mit Titeln angezeigt.

        ![](images/subject-scheme-title.png){width="550" align="left"}

      - **Betreffschema im Bedienfeld Bedingungen anzeigen**: Wählen Sie diese Option, um ein Betreffschema im Bedienfeld Bedingungen anzuzeigen. Wenn Sie diese Option deaktivieren, werden die definierten Bedingungen im Bedienfeld Bedingungen angezeigt.

   - **Authoring**

      - **Alle ersetzen aktivieren**: Wählen Sie diese Option aus, um das Symbol **Alle ersetzen** im Bedienfeld **Suchen und Ersetzen** anzuzeigen.

   - **Zitate**
Ändern des Stils von Zitaten. Wählen Sie in der Dropdown-Liste den Zitatstil aus, den Sie in Ihrem Projekt verwenden möchten. Weitere Informationen finden Sie unter [Ändern von ](./web-editor-apply-citations.md#change-citation-style).

   - **KI-Assistent**
Wählen Sie diese Option aus, um die Funktion [KI](./ai-assistant.md)Assistent“ in der Experience Manager Guides zu aktivieren. Deaktivieren Sie diese Option, um die Funktion zu deaktivieren.

**Bedienfelder**: Mit dieser Einstellung werden die Bedienfelder gesteuert, die im linken und rechten Bedienfeld des Editors und der Zuordnungskonsole angezeigt werden. Sie können die Schaltfläche umschalten, um das gewünschte Bedienfeld ein- oder auszublenden.

![](images/editor-setting-panel.png){width="650" align="left"}

Sie können auch die Reihenfolge festlegen, in der die in Bedienfeldern vorhandenen Funktionen angezeigt werden. Um die Standardreihenfolge der verfügbaren Funktionen in den Bedienfeldern zu ändern, wählen Sie die gepunkteten Balken aus, um die Elementregisterkarten per Drag-and-Drop an die gewünschte Position zu ziehen. Ein Feature kann je nach Anforderung auch vom **Mehr**-Abschnitt in den Hauptabschnitt eines Bedienfelds und umgekehrt verschoben werden. Nach der Neuanordnung erscheinen die Funktionen im entsprechenden rechten und linken Bedienfeld in der gleichen Reihenfolge.

![](images/panels-screen.png){width="650" align="left"}


Es können maximal acht Bedienfelder gleichzeitig angezeigt werden. Alle Änderungen an den Bedienfeldeinstellungen werden sofort übernommen.


>[!NOTE]
>
> Wenn ein benutzerdefiniertes Bedienfeld konfiguriert wurde, wird es auch in der Liste der Bedienfelder angezeigt. Sie können den Schalter umschalten, um das benutzerdefinierte Bedienfeld ein- oder auszublenden.

- **Elementliste**: Als Admin können Sie die Liste der Elemente steuern, die ein Autor in eine Datei einfügen kann, und auch den Anzeigenamen für das Element definieren. Mit der Einstellung Elementliste können Sie den Elementnamen gemäß DITA-Spezifikationen und eine Beschriftung angeben, die Sie anstelle des von DITA definierten Elementnamens verwenden möchten:

  ![](images/editor-setting-element-list.png){width="650" align="left"}

Im obigen Screenshot wurde dem `p`-Element eine Beschriftung mit Absatz und `codeblock` neben einigen anderen Elementen eine Beschriftung mit Codeblock zugewiesen. Wenn Sie die Option **Nur Elemente oben verwenden** auswählen, werden nur die gültigen Elemente \(bei der aktuellen Einfügemarke\) aus dieser Liste im Dialogfeld **Element einfügen** angezeigt.

Im folgenden Screenshot werden nur 3 von 4 konfigurierten Elementen aus dem vorherigen Screenshot im aktuellen Kontext angezeigt:

![](images/editor-setting-insert-element-list.PNG){width="300" align="left"}

- **Attributliste**: Ähnlich wie bei der Elementliste können Sie die Liste der Attribute und deren Anzeigenamen steuern, die in der Attributliste eines Elements angezeigt werden sollen. Im folgenden Screenshot wurden nur drei Attribute so konfiguriert, dass sie in der Attributliste eines Elements angezeigt werden:

  ![](images/editor-setting-attributes-list.png){width="650" align="left"}

  Bei dieser Einstellung wird beim Versuch, einem Element ein Attribut hinzuzufügen, nur die Liste der in der Liste konfigurierten Attribute angezeigt.

  ![](images/editor-setting-add-attributes-list.png){width="300" align="left"}

- **Farben**: Zeigt eine Liste der vorkonfigurierten Hintergrundfarben für &quot;**&quot;**. Benutzer können beim Anwenden einer Bedingung auf ein Thema eine Hintergrundfarbe auswählen. Als Administrator können Sie auch benutzerdefinierte Hintergrundfarben erstellen und zur Liste hinzufügen. Um eine neue Farbe hinzuzufügen, geben Sie den gewünschten Namen in das Feld **Farbname** ein, wählen Sie eine benutzerdefinierte Farbe aus und klicken Sie auf das Symbol **+** . Die benutzerdefinierte Farbe wird am Ende der Farbliste angezeigt.

- **Profile veröffentlichen**: Enthält die Profile, die zum Veröffentlichen der Ausgabe der **Wissensdatenbank** verwendet werden können. Sie können ein neues Profil für eine Ziel-Wissensdatenbank erstellen. Beispiel: Salesforce oder ServiceNow.

   - **Erstellen eines Salesforce-Profils**

     **Voraussetzungen**

      - Erstellen Sie eine verbundene App für Salesforce. Weitere Informationen finden Sie unter [OAuth-Einstellungen für API-Integration aktivieren](https://help.salesforce.com/s/articleView?id=sf.connected_app_create_api_integration.htm&amp;type=5).

      - Stellen Sie beim Konfigurieren der verbundenen App Folgendes sicher:

         - Geben Sie den Callback an.

           `URL: http://<server name>:<port>/bin/dxml/thirdparty/callback/salesforce`

         - Wählen Sie die folgenden OAuth-Bereiche aus:
            - Vollständiger Zugriff (vollständig)
            - Wählen Sie Benutzerdaten über APIs verwalten (API) aus

     Sobald die App konfiguriert ist, stellt Salesforce einen **Consumer Key** und **Consumer Secret** bereit. Diese können zum Erstellen des Salesforce-Profils verwendet werden.


   - Um ein Salesforce-Profil zu erstellen, wählen Sie die **Salesforce** Knowledge Base aus der Dropdown-Liste **Servertyp** aus. Geben Sie einen Profilnamen ein. Geben Sie **Site-URL** die Verbraucherwebsite ein, mit der Sie die Ausgabe veröffentlichen möchten, und fügen Sie dann den **Consumer Key** und **Consumer Secret** hinzu, die von der Salesforce-Verbraucherwebsite bereitgestellt werden. Wählen Sie dann **Validieren** und **Speichern** das neu erstellte Profil aus.

     ![Salesforce-Veröffentlichungsprofil in Editor-Einstellungen](./images/salesforce-publish-profile.png){width="550" align="left"}

     >[!NOTE]
     >
     >Verwenden Sie zum Konfigurieren eines Proxys für Salesforce in Experience Manager Guides die Apache-HTTP-Komponenten-Proxy-Konfiguration in AEM. Erfahren Sie, wie [Proxy für den AEM Link Checker konfigurieren](https://helpx.adobe.com/experience-manager/kb/How-to-configure-proxy-for-the-AEM-Link-Checker-AEM.html).


   - **Erstellen eines ServiceNow-Profils**

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


- **Validierung**: Diese Registerkarte enthält Optionen zum Konfigurieren der Schematron-Validierungen im Editor. Sie können die folgenden Funktionen aktivieren:

   - **Validierungsprüfung vor dem Speichern der Datei ausführen**: Wählen Sie diese Option, um vor einem Speichervorgang Schematron-Validierungen unter Verwendung der ausgewählten Schematron-Datei(en) auszuführen. Sie können eine Schematron-Datei hinzufügen, indem Sie auf das Symbol + klicken. Die ausgewählten Schematron-Dateien werden aufgelistet.

     >[!NOTE]
     >
     >Die ausgewählte(n) Schematron-Datei(en) bleiben für das ausgewählte Ordnerprofil erhalten.

     ![Validierung in Editor-Einstellungen](./images/editor-setting-validation.png){width="550" align="left"}

     Dies verhindert, dass Benutzer eine Datei speichern, die gegen eine in der/den ausgewählten Schematron-Datei(en) definierte Regel verstößt. Wenn diese Option nicht ausgewählt ist, wird die Datei vor dem Speichern der Änderungen nicht validiert.

   - **Zulassen, dass alle Benutzer Schematron-Dateien im Validierungsbereich hinzufügen**: Wählen Sie diese Option aus, damit die Benutzer im Validierungsbereich des Editors beliebige Schematron-Dateien hinzufügen können. Auf diese Weise können Benutzer Schematron-Dateien hinzufügen und dann die Themen anhand der Schematron-Datei validieren. Wenn diese Option nicht ausgewählt ist, steht die Schaltfläche zum Hinzufügen **Schematrondatei** Schematrondatei hinzufügen“ den Benutzenden im **Validierungsbereich** des Editors nicht zur Verfügung.


- **Attribute anzeigen**: Wie die Attributliste können Sie die Liste der Attribute steuern, die in der Attributliste eines Elements angezeigt werden sollen. Standardmäßig wurden vier **Anzeigeattribute** - Zielgruppe, Plattform, Produkt und Eigenschaften so konfiguriert, dass sie in der Attributliste eines Elements angezeigt werden. Sie können ein Anzeigeattribut auch mit dem Symbol **Hinzufügen** oben hinzufügen. Sie können auch jedes der Anzeigeattribute über das Symbol **Löschen** löschen.

  Die für ein Element definierten Attribute werden im Layout- und Gliederungsansicht angezeigt.

  ![](images/editor-settings-display-attributes.png){width="550" align="left"}

- **Übersetzung**: Diese Registerkarte enthält die Optionen zum Erstellen von Sprachgruppen, zum Übertragen der Quellkennzeichnungen in die Zielversion und zum Bereinigen des Übersetzungsprojekts.

  ![](images/editor-setting-translation.png){width="550" align="left"}

   - **Sprachgruppen**: Als Administrator können Sie eine Gruppe von Sprachen erstellen und sie als Gruppe verwenden, um die Inhalte zu übersetzen.

     Führen Sie die folgenden Schritte aus, um eine neue Sprachgruppe zu erstellen:

      1. Wählen Sie **Hinzufügen** aus.
      1. Geben Sie den Namen der Sprachgruppe ein. Jede Sprache sollte einen eindeutigen Namen haben. Sie können einen Fehler anzeigen, wenn das Namensfeld leer oder der Name nicht eindeutig ist.
      1. Wählen Sie die Sprachen aus dem Dropdown-Menü aus. Sie können mehrere Sprachen auswählen.

         Geben Sie die ersten Zeichen der Sprache oder den Sprach-Code ein, um die gewünschten Sprachen zu filtern. Geben Sie beispielsweise „en“ ein, um alle Sprachen zu filtern, die „en“ am Anfang ihres Namens oder Codes enthalten.

      1. Wählen Sie das Symbol Fertig aus, um der Gruppe die ausgewählten Sprachen hinzuzufügen. Die Sprachen werden angezeigt. Wenn Sie drei oder mehr Sprachen hinzufügen, wird **Option „Mehr anzeigen** angezeigt. Sie können auf **Mehr anzeigen** klicken, um alle in der Gruppe vorhandenen Sprachen anzuzeigen.

         >[!TIP]
         >
         >Schalten Sie **Mehr anzeigen** auf **Weniger anzeigen** um und zeigen Sie nur einige Sprachen an.

      1. Bewegen Sie den Mauszeiger über die Sprachen in einer Gruppe, um ![ Sprachgruppen zu bearbeiten ](images/edit_pencil_icon.svg)Bearbeiten-Symbol![ oder zu löschen](images/Delete_icon.svg).
      1. Speichern Sie die **Einstellungen**.

         >[!NOTE]
         >
         >Als Benutzer können Sie die für Ihr Ordnerprofil konfigurierten Sprachgruppen anzeigen.

   - **Beschriftungen der Quellversion an die Zielversion weitergeben**: Wählen Sie diese Option, um den Titel der Quelldateiversion an die übersetzte Datei weiterzugeben. Standardmäßig ist dies deaktiviert.
   - **Bereinigung des Übersetzungsprojekts nach Abschluss**: Wählen Sie diese Option, um die Übersetzungsprojekte so zu konfigurieren, dass sie nach der Übersetzung automatisch deaktiviert oder gelöscht werden. Standardmäßig ist **Keine** ausgewählt, sodass das Projekt nach der Übersetzung existiert.

     Sie können die Übersetzungsprojekte deaktivieren, wenn Sie sie später verwenden möchten. Durch das Löschen eines Projekts werden alle im Projekt vorhandenen Dateien und Ordner endgültig gelöscht.


- **Metadaten**: Sie können die Versionsmetadaten des Themas und deren Werte steuern, die im Dialogfeld **Versionsverlauf** angezeigt werden.  Geben Sie im Metadatenpfad den Speicherort der Knoten an, aus denen Sie die Metadaten auswählen möchten. Sie können auch einen benutzerdefinierten Namen für die Metadaten als Beschriftung definieren. Die Standardeigenschaften sind Titel, Dokumentstatus und Tags.

  Die Metadaten können aus jeder Eigenschaft unter dem `/jcr:content` des Assets ausgewählt werden, sodass Sie den Pfad der Eigenschaft als Metadatenpfad hinzufügen können.


  Wenn der Metadatenpfad leer ist, wird ein Fehler angezeigt. Wenn Sie das Feld leer lassen, wird das letzte Element als Titel ausgewählt.


  ![Registerkarte „Metadaten“ in den Editor-Einstellungen](images/editor-setting-metadata.png){width="550" align="left"}

  *Konfigurieren der Metadaten für das Dialogfeld **Versionsverlauf**.*



  Sie können auch die Reihenfolge festlegen, in der diese Metadaten-Tags angezeigt werden. Um die Standardreihenfolge dieser Tags zu ändern, wählen Sie die gepunkteten Balken aus, um die Tags per Drag-and-Drop an die gewünschte Position zu ziehen.
Die Metadatenbeschriftungen werden im Dialogfeld **Versionsverlauf** des Editors in derselben Reihenfolge angezeigt.

## Symbolleiste

Die Symbolleiste wird angezeigt, wenn Sie ein Thema oder eine Karte zur Bearbeitung im Editor öffnen. In der Symbolleiste stehen folgende Funktionen zur Verfügung:

- [Menü-Dropdown](#menu-dropdown)
- [Optionen zum Einfügen von Inhalten](#content-insertion-options)
- [Versionsinformationen und Schaltfläche Als neue Version speichern](#save-as-new-version)
- [Sperren/Entsperren](#lockunlock)

>[!NOTE]
>
> Die oben aufgeführten Funktionen gelten nur für Themendateien. Beim Arbeiten mit einer Zuordnungsdatei werden basierend auf der aktuellen Ansicht des Zuordnungs-Editors verschiedene Optionen in der Symbolleiste angezeigt. Weitere Informationen zu den Symbolleistenoptionen des Zuordnungs-Editors [ Sie im Dokument ](./map-editor-advanced-map-editor.md)Funktionen des Zuordnungs-Editors“.

### Menü-Dropdown

Die Dropdown-Liste Menü bietet Zugriff auf die Funktionen zum Bearbeiten, Suchen und Ersetzen, Versionsverlauf, Versionsbezeichnung, Zusammenführen, Prüfungsaufgabe erstellen, Änderungen verfolgen und Tags .

Diese Funktionen werden im Einzelnen wie folgt erläutert:

**Aktionen bearbeiten**

Greifen Sie beim Bearbeiten eines Themas im Editor auf die verschiedenen Bearbeitungsaktionen zu, z. B. **Ausschneiden** oder ***Strg***+***X*** , **Kopieren** oder ***Strg***+***C*** , **Rückgängig** oder ***Strg***+Z ***,**Wiederholen**oder*** CtrlCtrlY ****** ****** **** Löschenim Dropdown-Menü.


**Suchen und Ersetzen**

Die Funktion **Suchen und Ersetzen** ist im Autoren- und Source-Ansichtsmodus verfügbar. Wenn diese Option aktiviert ist, wird die Textleiste Suchen und Ersetzen unten im Themenbearbeitungsbereich angezeigt. Sie können die Tastaturbefehle (**+**+**F) verwenden** um die Leiste zum Suchen und Ersetzen aufzurufen.

![](images/find-replace-bar.png){align="left"}

Über das Einstellungssymbol \(![](images/settings-find-replace-icon.svg)\) können Sie die Suchoptionen **Groß-/Kleinschreibung ignorieren** und **Nur ganzes Wort** umschalten. Um die Suche ohne Berücksichtigung der Groß-/Kleinschreibung durchzuführen, aktivieren (oder wählen) Sie die Option **Groß-/Kleinschreibung ignorieren**. Andernfalls müssen Sie, wenn Sie die Suche unter Berücksichtigung der Groß-/Kleinschreibung durchführen möchten, die Option **Groß-/Kleinschreibung ignorieren** deaktivieren (oder deren Auswahl aufheben). Sie können auch ein ganzes Wort suchen.

Die Suche erfolgt sofort, d. h. wenn Sie den Suchbegriff oder das Wort in das Feld **Suchen** eingeben, wird der Begriff sofort durchsucht und im Thema ausgewählt. Um einen Text in Ihrem Thema zu ersetzen, geben Sie den Suchbegriff und seine Ersetzung in die entsprechenden Felder ein und wählen Sie die Schaltfläche **Ersetzen** oder **Alle ersetzen** aus.

In der Source-Ansicht **die Funktion „Suchen und Ersetzen** äußerst nützlich für die Suche nach einem bestimmten Element oder Attribut. Wenn Sie beispielsweise den Wert des `@product`-Attributs ersetzen möchten, kann dies einfach über die Source-Ansicht erfolgen. In der Autorenansicht können Sie nicht anhand eines Attributs oder Elements suchen. Bei Verwendung der Funktion „Alle ersetzen **müssen Sie jedoch mit Vorsicht vorgehen** da dadurch der XML-Code überschrieben werden könnte.

**Versionsverlauf**

Mit **Funktion „Versionsverlauf** im Editor können Sie die verfügbaren Versionen Ihrer DITA-Dateien überprüfen, vergleichen und auf eine beliebige Version aus dem Editor selbst zurücksetzen. Sie können den Inhalt und die Metadaten der aktuellen Version (die auch eine Arbeitskopie sein kann) mit einer beliebigen früheren Version derselben Datei vergleichen. Sie können auch die Beschriftungen und Kommentare für die verglichenen Versionen anzeigen.

>[!NOTE]
>
> Die Optionen für den Versionsverlauf werden nur angezeigt, wenn Änderungen an der ersten Version des Themas oder der Zuordnung vorgenommen wurden.

Um auf den Versionsverlauf zuzugreifen und auf eine bestimmte Version Ihres Themas zurückzukehren, führen Sie die folgenden Schritte aus:

1. Öffnen Sie ein Thema im Editor.
1. Wählen Sie **Versionsverlauf** aus der Dropdown-Liste **Menü** aus.

   Das **Versionsverlauf** wird angezeigt.

   ![Dialogfeld „Versionsverlauf“](images/version-history-dialog-web-editor.png){width="550" align="left"}

   *Vorschau der Änderungen in den verschiedenen Versionen eines Themas.*

1. Wählen Sie in der Dropdown-Liste „Vergleichen mit“ eine Version des Themas aus **mit dem Sie vergleichen oder** möchten.

   >[!NOTE]
   >
   > Wenn einer Version Beschriftungen zugewiesen sind, werden diese ebenfalls \(in Klammern\) zusammen mit der Versionsnummer angezeigt.

1. Aktivieren Sie die **Beschriftungen und Kommentare anzeigen**, um die Beschriftungen und Kommentare anzuzeigen, die auf die aktuelle und die verglichene Version angewendet wurden.
1. Sie können die folgenden Informationen auch im Dialogfeld **Versionsverlauf** anzeigen:

   **Vorschau**-Registerkarte: Der neu hinzugefügte Inhalt ist in grüner Schriftart, und der gelöschte Inhalt ist in roter Schriftart.

   Registerkarte **Metadaten**: Die neu hinzugefügten Metadaten sind in grüner Schrift, die gelöschten Metadaten in roter Schrift.

   ![Metadatenunterschied für Versionen ](images/metadata-version-diff.png){width="550" align="left"}

   *Vergleichen der Metadaten verschiedener Versionen im Versionsverlauf.*

   >[!NOTE]
   >
   > Ihr Systemadministrator kann die Metadaten, die angezeigt werden sollen, über die Registerkarte Metadaten unter &quot;**&quot;**. Weitere Informationen finden Sie im Abschnitt **Weitere Aktionen** der [Registerkartenleiste](#tab-bar).

   Sie können auch die Benutzer- und Zeitdetails der aktuellen und der verglichenen Version anzeigen.

   Nachdem Sie eine Version aus der Dropdown-Liste ausgewählt haben, wird **Option „Auf ausgewählte Version**&quot; verfügbar gemacht. Im Vorschaufenster werden die Unterschiede zwischen der aktuellen Version und der ausgewählten Version des Themas angezeigt.

1. Wählen Sie **Auf ausgewählte Version zurücksetzen** aus, um Ihre Arbeitskopie mit der ausgewählten Version des Themas wiederherzustellen.

   Das Dialogfeld Version zurücksetzen wird angezeigt.

   ![](images/version-history-revert-dialog-save-working-copy.png){width="550" align="left"}

1. \(*Optional*\) Geben Sie einen Grund für die Rückkehr zu einer früheren Version an. Sie können auch eine neue Version der derzeit aktiven Arbeitskopie Ihres Themas erstellen.

1. Wählen Sie **Bestätigen.**

   Ihre Arbeitskopie der Datei wird auf die ausgewählte Version zurückgesetzt. Wenn Sie eine neue Version der derzeit aktiven Arbeitskopie erstellen, wird auch eine neue Version der Datei mit allen Arbeitsänderungen erstellt.

   Wenn Sie zu einer früheren Version zurückkehren, wird ein visueller Hinweis angezeigt, der angibt, dass die Version, an der Sie gerade arbeiten, nicht die neueste Version ist.

   ![](images/older-version-visual-cue.png){align="left"}

**Versionsbezeichnungen**

Mit Beschriftungen können Sie den Schritt identifizieren, in dem sich ein bestimmtes Thema im DDLC (Document Development Life Cycle) befindet. Wenn Sie beispielsweise an einem Thema arbeiten, können Sie die Bezeichnung als „Genehmigt“ festlegen. Sobald ein Thema veröffentlicht und Kunden zur Verfügung gestellt wurde, können Sie diesem Thema die Bezeichnung „Freigegeben“ zuweisen.

Mit Experience Manager Guides können Sie Beschriftungen in einem Freiformtextformat angeben oder einen Satz vordefinierter Beschriftungen verwenden. Mit der benutzerdefinierten Beschriftung können alle Autorinnen und Autoren im System eine Beschriftung gemäß ihrer Auswahl angeben. Dies bietet Flexibilität, führt jedoch zu inkonsistenten Beschriftungen im System. Um dieses Problem zu beheben, können Admins einen Satz vordefinierter Kennzeichnungen konfigurieren. Weitere Informationen zum Konfigurieren vordefinierter Kennzeichnungen finden Sie unter *Konfigurieren und Anpassen des XML-Web* Editors in der Adobe Experience Manager Guides as a Cloud Service installieren und konfigurieren.

Diese Beschriftungen werden Autoren in Form einer Dropdown-Liste angezeigt, wenn sie eine Beschriftung angeben müssen. Dadurch wird sichergestellt, dass im System nur vordefinierte, konsistente Kennzeichnungen verwendet werden.

Es gibt verschiedene Methoden, mit denen Sie Beschriftungen auf Ihre Themen anwenden können - [Versionsverlauf](web-editor-use-label.md) Bedienfeld in der Assets-Benutzeroberfläche, [Baselines](/help/product-guide/user-guide/generate-output-use-baseline-for-publishing.md)-Benutzeroberfläche und im Editor. Mit der Funktion „Versionsbezeichnung“ im Editor können Autoren ihren Themen schnell und einfach Beschriftungen zuweisen.

Um Ihrem Thema Beschriftungen aus dem Editor hinzuzufügen, führen Sie die folgenden Schritte aus:

1. Öffnen Sie ein Thema im Editor.

1. Wählen Sie **Versionsbezeichnungen** aus dem Dropdown-Menü aus.

   Das Dialogfeld Versionsbeschriftungs-Verwaltung wird angezeigt.

   ![](images/version-label-management-dialog.png){width="650" align="left"}

   Das Dialogfeld Versionsbeschriftungsverwaltung ist in zwei Teile unterteilt: Das linke Bedienfeld enthält eine Liste der für das Thema verfügbaren Versionen zusammen mit der Dropdown-Liste Beschriftung \(oder einem Textfeld zur Eingabe einer Beschriftung\) und das rechte Bedienfeld mit einer Vorschau des Themas.

1. Wählen Sie eine Version aus, auf die Sie Kennzeichnungen anwenden möchten.

   Wenn Sie in der Versionsliste eine andere Version des Themas auswählen, werden im Vorschaubereich die Änderungen zwischen der aktuellen Version und der ausgewählten Version des Themas angezeigt

   >[!NOTE]
   >
   > Wenn eine Beschriftung bereits auf eine Version angewendet wird, wird sie neben der Versionsnummer in der Dropdown-Liste und unter der Liste Version auswählen angezeigt. Sie können eine vorhandene Beschriftung entfernen, indem Sie das Symbol \(**x**\) neben der Beschriftung auswählen.

1. Wenn Ihr Administrator eine Liste von Kennzeichnungen definiert hat, wird eine Dropdown-Liste der Kennzeichnungen angezeigt, aus der Sie die Kennzeichnungen auswählen können, die Sie anwenden möchten. Sie können mehrere Bezeichnungen aus der Dropdown-Liste auswählen.

   Andernfalls wird ein Textfeld angezeigt, in das Sie die Beschriftungen eingeben können, die Sie zu Ihrem Thema hinzufügen möchten.

   >[!NOTE]
   >
   > Eine Bezeichnung kann nicht auf mehrere Versionen eines Themas angewendet werden. Wenn Sie versuchen, eine vorhandene Beschriftung zu verknüpfen, erhalten Sie die Möglichkeit, sie aus der vorhandenen Version zu entfernen und auf die ausgewählte Version des Themas anzuwenden.

1. Wählen Sie **Bezeichnung hinzufügen** aus.

1. Wählen Sie in der Bestätigungsmeldung Kennzeichnung anwenden die Option **Kennzeichnung verschieben (falls in einer anderen Version verwendet)**, um Kennzeichnungen von einer vorhandenen Version in die ausgewählte Version zu verschieben. Wenn Sie diese Option nicht auswählen und es Beschriftungen gibt, die einer anderen Version des Themas zugewiesen sind, werden diese nicht in die Version des ausgewählten Themas verschoben. Solche Kennzeichnungen werden beim Bezeichnungsantrag ignoriert.

**Zusammenführen**

Wenn Sie in einer Umgebung mit mehreren Autoren arbeiten, wird es schwierig zu verfolgen, welche Änderungen die anderen Autoren in einem Thema oder einer Zuordnung vorgenommen haben. Mit der Zusammenführungsfunktion haben Sie nicht nur mehr Kontrolle über die Anzeige der Änderungen, sondern auch darüber, welche Änderungen in der neuesten Version des Dokuments beibehalten werden.

- **Zusammenführen von Themendateien**

  Um Änderungen in einem Thema zusammenzuführen, führen Sie die folgenden Schritte aus:

   1. Öffnen Sie ein Thema im Editor.

   1. Wählen Sie **Zusammenführen** aus.

      Das Dialogfeld „Zusammenführen“ wird angezeigt.

      ![](images/merge-changes-in-topic.png){width="550" align="left"}

   1. *\(Optional\)* Sie können auch eine neue Datei an einem anderen Speicherort im Repository suchen und auswählen.

   1. Wählen Sie eine Version der Datei aus, mit der Sie die aktuelle Version der Datei vergleichen möchten.

   1. Wählen Sie unter Optionen Folgendes aus:

      - **Änderungen aus ausgewählter Version verfolgen**: Diese Option zeigt alle Inhaltsaktualisierungen in Form von verfolgten Änderungen an. Sie können dann Änderungen im Dokument einzeln oder in einem Schritt akzeptieren oder ablehnen.

      - **Auf ausgewählte Version zurücksetzen**: Mit dieser Option wird die aktuelle Version des Dokuments auf die ausgewählte Version zurückgesetzt. Mit dieser Option haben Sie keine Kontrolle darüber, welche Inhalte akzeptiert oder abgelehnt werden.

   1. Wählen Sie **Fertig**.

   1. Wenn Sie die Option **Änderungen aus ausgewählter Version nachverfolgen** ausgewählt haben, werden alle Änderungen aus der ausgewählten Version in der Funktion „Nachverfolgte Änderungen“ im rechten Bedienfeld angezeigt.

      Sie können alle Kommentare im Bedienfeld „Getrackte Änderungen“ akzeptieren oder ablehnen oder einzelne Kommentare akzeptieren oder ablehnen.


- **Zusammenführen von Zuordnungsdateien**

  Um Änderungen in einer Zuordnungsdatei zusammenzuführen, führen Sie die folgenden Schritte aus:

   1. Öffnen Sie eine Karte im Editor.

   1. Wählen Sie **Zusammenführen** aus.

      Das Dialogfeld „Zusammenführen“ wird angezeigt.

      ![](images/merge-changes-in-map.png){width="550" align="left"}

   1. *\(Optional\)* Sie können auch eine neue Datei an einem anderen Speicherort im Repository suchen und auswählen.

   1. Wählen Sie eine Version der Datei aus, mit der Sie die aktuelle Version der Datei vergleichen möchten.

   1. Wählen Sie unter Optionen Folgendes aus:

      - **Änderungen aus ausgewählter Version verfolgen**: Mit dieser Option werden alle Inhaltsaktualisierungen in Form von Änderungen nachverfolgt. Sie können dann Änderungen im Dokument einzeln oder in einem Schritt akzeptieren oder ablehnen.

      - **Auf ausgewählte Version zurücksetzen**: Mit dieser Option wird die aktuelle Version des Dokuments auf die ausgewählte Version zurückgesetzt. Mit dieser Option haben Sie keine Kontrolle darüber, welche Inhalte akzeptiert oder abgelehnt werden.

   1. Wählen Sie **Fertig**.

   1. Wenn Sie die Option **Änderungen aus ausgewählter Version nachverfolgen** ausgewählt haben, werden alle Änderungen aus der ausgewählten Version im Bedienfeld „Nachverfolgte Änderungen“ angezeigt (rechts).

      Sie können alle Änderungen im Bedienfeld „Nachverfolgte Änderungen“ annehmen oder ablehnen oder einzelne Änderungen in der Zuordnungsdatei akzeptieren oder ablehnen.


**Prüfungsaufgabe erstellen**

Sie können [eine Prüfungsaufgabe erstellen](./review-send-topics-for-review.md) des aktuellen Themas oder der Zuordnungsdatei direkt im Editor erstellen. Öffnen Sie die Datei, für die Sie die Prüfungsaufgabe erstellen möchten, und wählen Sie **Prüfungsaufgabe erstellen** aus dem Dropdown-Menü aus, um den Prozess zur Erstellung der Überprüfung zu starten.

**Änderungen verfolgen**

Sie können alle an einem Dokument vorgenommenen Aktualisierungen nachverfolgen, indem Sie den Modus Änderungen nachverfolgen aktivieren. Nach der Aktivierung der Tracking-Änderungen werden alle Einfügungen und Löschungen im Dokument erfasst. Der gesamte gelöschte Inhalt wird mithilfe von Durchgestrichen hervorgehoben, und alle Einfügungen werden in grünem Text hervorgehoben. Darüber hinaus werden die Änderungsleisten am Rand der Themenseite angezeigt. Auch hier wird ein roter Balken für gelöschte Inhalte und ein grüner Balken für hinzugefügte Inhalte angezeigt. Wenn sich eine Ergänzung und ein Löschvorgang in derselben Zeile befinden, werden sowohl grüne als auch rote Balken angezeigt.

Der folgende Screenshot zeigt den gelöschten und eingefügten Inhalt zusammen mit den Änderungsleisten:

![](images/track-changes-content.png){width="650" align="left"}

Ein typischer Anwendungsfall für das Tracking von Änderungen in einem Dokument kann die Durchführung einer Peer Review sein. Sie können Änderungen nachverfolgen und Ihr Dokument zur Überprüfung freigeben. Die Überprüfenden nehmen dann Änderungen vor, wenn die Nachverfolgung aktiviert ist. Wenn Sie das Dokument erhalten, sollten Sie über einen Mechanismus verfügen, mit dem Sie die vorgeschlagenen Aktualisierungen anzeigen können und bequem Änderungen akzeptieren oder ablehnen können.

Experience Manager Guides stellt die Funktion „Getrackte Änderungen“ bereit, die Informationen zu den im Dokument vorgenommenen Aktualisierungen enthält. Die Funktion „Nachverfolgte Änderungen“ enthält Informationen dazu, welche Aktualisierungen vorgenommen wurden, wer sie vorgenommen hat und zu welchem Zeitpunkt. Mit der Funktion „Nachverfolgte Änderungen“ können Sie die vorgeschlagenen Aktualisierungen im Dokument auch einfach akzeptieren oder ablehnen.

Um auf die Funktion zuzugreifen, wählen **im rechten Bedienfeld das Symbol**&#x200B;Änderungen verfolgen“ aus.

![](images/changes-panel_cs.png){width="300" align="left"}

Durch Auswählen einer verfolgten Änderung wird der geänderte Inhalt im Dokument ausgewählt. Sie können eine Änderung annehmen, indem Sie auf das Symbol Änderung akzeptieren klicken, oder sie ablehnen, indem Sie die Änderung ablehnen auswählen.

Wenn Sie alle Änderungen mit einem Klick akzeptieren oder ablehnen möchten, wählen Sie **Alle Änderungen akzeptieren** oder **Alle Änderungen ablehnen**.

>[!NOTE]
>
> Im Vorschaumodus können Sie das Dokument mit oder ohne Markierungen des geänderten Inhalts anzeigen. Weitere Informationen finden Sie im [Vorschau](web-editor-views.md#preview-mode-id19AAGL00163)-Modus.

**Tags**

Die **Tags**-Funktion im Editor ist eine Umschalter-Schaltfläche, die die Sichtbarkeit von DITA-Elementen steuert. Wenn diese Option aktiviert ist, werden strukturelle Tags im Inhalt angezeigt, sodass Sie die zugrunde liegenden DITA-Elemente effektiver anzeigen und verwalten können. Wenn diese Option deaktiviert ist, blendet der Editor diese Tags aus und bietet so eine sauberere und fokussiertere Authoring-Umgebung.

Der folgende Screenshot zeigt ein Dokument mit aktivierter Tag-Ansicht:

![](images/tags-view.png){width="650" align="left"}

Die folgenden Vorgänge können in einem Dokument mit Tags ausgeführt werden:

- **Element auswählen**: Wählen Sie das öffnende oder schließende Tag eines Elements aus, um seinen Inhalt auszuwählen.

- **Tags erweitern oder reduzieren**: Wählen Sie das + oder - Anmelden eines Tags aus, um es zu erweitern oder zu reduzieren.

- **Kontextmenü verwenden**: Das Kontextmenü bietet Optionen zum Ausschneiden, Kopieren oder Einfügen des ausgewählten Elements. Sie können ein Element auch vor oder nach dem ausgewählten Element einfügen. Die anderen Optionen ermöglichen es Ihnen, für das ausgewählte Element eine ID zu generieren oder den Bereich „Eigenschaften“ zu öffnen.

- **Elemente per Drag-and-Drop verschieben**: Wählen Sie das Tag eines Elements aus und ziehen Sie es einfach per Drag-and-Drop in Ihr Dokument. Wenn der Ablageort ein gültiger Ort ist, an dem das Element zulässig ist, wird das Element an dem abgelegten Ort platziert.


>[!NOTE]
>
> Wenn ein(e) Benutzende(r) die Tag-Ansicht im Editor aktiviert, bleibt sie auch sitzungsübergreifend aktiviert. Das bedeutet, dass Sie die Tag-Ansicht nicht erneut aktivieren müssen, um später darauf zuzugreifen. Der Standardwert für die Tags-Ansicht für die Sitzung eines neuen Benutzers wird durch die `tagsView`-Eigenschaft in der `ui\_config.json` bestimmt. Weitere Informationen finden Sie im Abschnitt [Standardwert für die Tag-Ansicht konfigurieren](../cs-install-guide/configure-default-value-tags-view.md) unter Installieren und Konfigurieren von Adobe Experience Manager Guides as a Cloud Service.

### Optionen zum Einfügen von Inhalten

**Element** - ![](images/Add_icon.svg)

Fügt ein gültiges Element an der aktuellen oder nächsten gültigen Position ein. Sie können auch den Tastaturbefehl ***Alt***+***Eingabetaste*** verwenden, um das Dialogfeld Element zu öffnen. Wenn Sie beispielsweise einen Absatz bearbeiten, wird im Dialogfeld **Element** eine Liste von Elementen angezeigt, die in den Absatz eingefügt werden können. Wählen Sie das Element aus, das Sie einfügen möchten. Sie können die Tastatur verwenden, um durch die Liste der Elemente zu scrollen und die Eingabetaste ***,*** das gewünschte Element einzufügen.

Sie können zwei Arten gültiger Elemente anzeigen:

- **Gültige Elemente am aktuellen Speicherort**: Die Liste zeigt die Elemente an, die Sie am aktuellen Cursor-Speicherort selbst einfügen können.

- **Gültige Elemente außerhalb des aktuellen Speicherorts**: Die Liste zeigt die Elemente an, die Sie für das aktuelle Element innerhalb der Elementhierarchie nach einem der übergeordneten Elemente einfügen können.

Wenn Sie sich beispielsweise im Inline-`<b>` befinden, können Sie Elemente wie `<u>`, `<xref>` `<i>` an der aktuellen Position einfügen. Im Gegensatz dazu können Sie Elemente wie `<table>` und `<topic>` außerhalb des aktuellen Speicherorts einfügen.

Sie können auch ein Zeichen oder eine Zeichenfolge in das Suchfeld eingeben und nach den Elementen suchen, die damit beginnen.

![Element einfügen](images/insert-element.png){width="300" align="left"}

*Geben Sie &#39;t&#39; ein, um nach allen gültigen Elementen zu suchen, die mit &#39;t&#39; beginnen.*

Wenn Sie wie ein `note` in einem Blockelement arbeiten, verwenden Sie das Symbol Element einfügen , um ein neues Element nach dem `note` Element einzufügen. Im folgenden Screenshot wurde ein Element NOTE in das Element p \(Absatz\) eingefügt:

![Element in ein Blockelement einfügen](images/note-in-para-insert-element_cs.png){align="left"}

Wenn Sie im Notizelement die Eingabetaste drücken, wird ein neuer Absatz innerhalb des Notizelements selbst erstellt. Um ein neues Element außerhalb der Anmerkung einzufügen, wählen Sie das p-Element \(im Screenshot hervorgehoben\) im Breadcrumb für Elemente aus und wählen Sie dann das Symbol Element aus oder drücken Sie ***Alt***+***Eingabetaste***, um das Dialogfeld Element einfügen zu öffnen. Wählen Sie anschließend das gewünschte Element aus und drücken Sie die Eingabetaste, um das ausgewählte Element nach dem Element Notiz einzufügen.

Sie können auch ein -Element zwischen zwei -Elementen hinzufügen, wenn ein blinkender Blockcursor angezeigt wird.


![](images/Block-cursor.png){width="300" align="left"}

Wenn Sie beispielsweise an einem DITA-Thema arbeiten und der Blockcursor zwischen der Kurzbeschreibung und dem Textkörper blinkt, können Sie `prolog` Element hinzufügen und dann Copyright, Autor und andere Details hinzufügen.

Eine andere Möglichkeit, ein neues Element einzugeben, ist die Verwendung des Kontextmenüs. Klicken Sie mit der rechten Maustaste auf eine beliebige Stelle in Ihrem Dokument, um das Kontextmenü aufzurufen. Wählen Sie in diesem Menü **Element einfügen**, um das Dialogfeld **Element einfügen** anzuzeigen, und wählen Sie das Element aus, das Sie einfügen möchten.

![](images/insert-element-before-after.png){width="300" align="left"}

**Absatz** - ![](images/Paragraph_icon.svg)

Fügen Sie das Absatzelement an der aktuellen oder nächsten gültigen Position ein.

**Aufzählungsliste** - ![](images/BulletList_icon.svg)

Erstellt eine Liste mit Aufzählungszeichen am aktuellen oder nächsten gültigen Speicherort. Wenn Sie sich auf einer Aufzählungsliste befinden und dieses Symbol auswählen, wird das Element in einen normalen Absatz konvertiert.

**Nummerierte Liste** - ![](images/TextNumbered_icon.svg)

Erstellt eine nummerierte Liste am aktuellen oder nächsten gültigen Speicherort. Wenn Sie sich auf einer nummerierten Liste befinden und dieses Symbol auswählen, wird das Element in einen normalen Absatz konvertiert.

>[!NOTE]
>
>Sie können auch die Option **Liste teilen** aus dem Kontextmenü eines Listenelements auswählen, um die aktuelle Liste zu teilen und eine neue Liste auf derselben Ebene zu beginnen.

**Tabelle** - ![](images/Table_icon.svg)

Fügt eine Tabelle am aktuellen oder nächsten gültigen Speicherort ein. Wählen Sie das Symbol Tabelle aus, um das Dialogfeld Einfache Tabelle einfügen zu öffnen.

![](images/table-properties.png){width="550" align="left"}

>[!NOTE]
>
> Sie können auch eine Tabelle aus MS Word oder Excel kopieren und in die Experience Manager Guides-Themendatei einfügen. Die kopierte Tabelle wird je nach den in der XML-Editor-Konfiguration konfigurierten Einstellungen entweder als `<simpletable>` oder `<tgroup>` eingefügt. Weitere Informationen finden Sie unter [Konfigurieren der Anzeige eingefügter Tabellen](../cs-install-guide/conf-pasted-tables.md).

Sie können die Anzahl der Zeilen und Spalten angeben, die in der Tabelle erforderlich sind. Wenn Sie die erste Zeile als Tabellenüberschrift beibehalten möchten, wählen Sie die Option **Erste Zeile als Überschrift festlegen** aus. Um der Tabelle einen Titel hinzuzufügen, geben Sie ihn im Feld Titel ein.

Nachdem eine Tabelle eingefügt wurde, können Sie die Tabelle mit dem Kontextmenü ändern.

![](images/table-context-menu_cs.png){width="550" align="left"}



Über das Kontextmenü der Tabelle haben Sie folgende Möglichkeiten:

- Zellen, Zeilen oder Spalten einfügen

- Zusammenführen von Zellen in Rechts- und Abwärtsrichtung

- Zellen horizontal oder vertikal teilen

- Zellen, Zeilen oder Spalten löschen

- IDs generieren


Sie können auch Attribute für mehrere Zellen, die gesamte Zeile oder Spalte einer Tabelle definieren. Um beispielsweise eine Tabellenzelle auszurichten, ziehen Sie die gewünschte Zelle und wählen Sie sie aus. Im Bedienfeld Inhaltseigenschaften (rechts) ändert sich die Eigenschaft **Typ** in **Eintrag**.

1. Wählen **Abschnitt „Attribute** die Option **+Hinzufügen**.
1. Wählen Sie das `@valign` Attribut aus der Dropdown **Liste „Attribut** aus.
1. Wählen Sie aus der Dropdown-Liste Wert die gewünschte Textausrichtung aus, die Sie auf die ausgewählten Tabellenzellen anwenden möchten.
1. Wählen Sie **Hinzufügen.**

![](images/align-table-cell_cs.png){align="left"}

**Bild** - ![](images/Image_icon.svg)

Fügt ein Bild am aktuellen oder nächsten gültigen Speicherort ein. Klicken Sie auf das Bildsymbol, um das Dialogfeld Bild einfügen zu öffnen. Suchen Sie dann das Bild, das Sie einfügen möchten, und wählen Sie es aus.

>[!NOTE]
>
> Sie können auch ein Bild hinzufügen, indem Sie es aus Ihrem lokalen System auf Ihren Artikel ziehen und ablegen. In diesem Fall wird die Bilddatei mithilfe des Workflows **Assets hochladen** hinzugefügt.  Weitere Informationen finden Sie im Abschnitt **Workflow &quot;Assets hochladen** im [ Bereich](#left-panel).


![](images/insert-image.png){width="650" align="left"}

Sie können einen Bild-/Figurtitel und alternativen Text für das Bild im Dialogfeld Bild einfügen hinzufügen.

>
>
> Wenn Sie ein Bild einfügen und einen alternativen Text für dasselbe angeben, wird es innerhalb des `<alt>` gemäß den neuesten DITA-Standards hinzugefügt. Die Verwendung des Attributs `@alt` für alternativen Text ist veraltet, wird aber in früheren DITA-Versionen weiterhin unterstützt.

Mit der Option **Datei auswählen** können Sie nach der gewünschten Bilddatei anhand des Dateinamens suchen. Sie können die Suchergebnisse auch nach Pfad \(zum Suchen in\), Sammlungen, Dateityp und Tags filtern. Nachdem Sie die gewünschte Bilddatei gefunden haben, wählen Sie die Datei aus und klicken Sie auf **Auswählen**, um das Bild in Ihr Dokument einzufügen. Sie können verschiedene Formate von Bilddateien einfügen, z. B. `.png`, `.svg`, `.gif`, `.jpg`, `.eps`, `.ai`, `.psd` und mehr.

Nachdem Sie ein Bild eingefügt haben, können Sie die Attribute für Höhe, Breite, Platzierung und Inhalt im Bedienfeld Inhaltseigenschaften ändern. Wählen Sie die Bilddatei aus und nehmen Sie dann Änderungen im Bedienfeld Inhaltseigenschaften im rechten Bedienfeld vor.

![](images/image-properties.png){align="left"}

Das Feld Source zeigt die UUID der eingefügten Bilddatei an. Sie können den vollständigen Pfad der eingefügten Bilddatei finden, indem Sie den Mauszeiger über das Source-Feld bewegen. Der Pfad wird in der QuickInfo angezeigt.

Sie können die Größe eines Bildes ändern, indem Sie entweder den Wert für Höhe oder Breite für die Bilddatei angeben. Das Seitenverhältnis des Bildes wird automatisch beibehalten. Sie können auch das Seitenverhältnis der Bilddatei nicht beibehalten, indem Sie das Schlosssymbol \(von Seitenverhältnis beibehalten\) auswählen und die Werte für Höhe und Breite angeben.

Sie können die Platzierungseinstellung für das Bild auch als Inline- oder Break-Einstellung festlegen. Wenn Sie die Option Platzierung aufheben verwenden, können Sie anschließend auswählen, wo das Bild ausgerichtet werden soll (links, zentriert oder rechts).

Sie können auch andere Eigenschaften für eine Bilddatei hinzufügen, indem Sie die erforderlichen Eigenschaften im Feld **Attribute** auswählen.

>[!NOTE]
>
>Sie können auch anklickbare Bereiche \(Imagemap\) in Ihrem Bild definieren. Weitere Informationen finden Sie in der Beschreibung **Bildzuordnung einfügen/bearbeiten** im Abschnitt [Linkes Bedienfeld](web-editor-features.md#left-panel).

**Kontextmenü für Bild- oder Mediendateien**

Sie können auch einige allgemeine Vorgänge für Bilder und Mediendateien über das Kontextmenü durchführen. Klicken Sie mit der rechten Maustaste auf eine beliebige Stelle auf Ihrem Bild, um das Kontextmenü aufzurufen.

Das Kontextmenü bietet Optionen zum Ausschneiden, Kopieren oder Einfügen des Bildes oder Mediums. Sie können ein Element vor oder nach dem ausgewählten Element einfügen. Sie haben auch die Möglichkeit, ein Element umzubenennen oder seinen Wrapper zu entfernen. Sie können das ausgewählte Bild oder die ausgewählten Medien im Repository finden oder die Vorschau der Datei in der Assets-Benutzeroberfläche anzeigen.

Die anderen Optionen im Kontextmenü ermöglichen es Ihnen, einen Pfad zu kopieren, eine Imagemap zu bearbeiten, ein Element umzubenennen, einen Ausschnitt zu erstellen oder IDs für das ausgewählte Element zu generieren.

**Imagemap einfügen/bearbeiten**

Fügt eine Imagemap in das ausgewählte Bild ein. Ein Bild mit klickbaren Bereichen, die auf Themen oder Web-Seiten verlinken, wird als Imagemap bezeichnet.

Wählen Sie ein Bild im aktuellen Thema aus und klicken Sie auf das Symbol Imagemap einfügen/bearbeiten , um das Dialogfeld Imagemap einfügen zu öffnen.

![](images/insert-image-map.png){width="650" align="left"}

Wählen Sie die bevorzugte Form aus ![](images/imagemap-rectangle-toolbar.png), ![](images/imagemap-circle-toolbar.png) oder Polygon-![](images/imagemap-polygon-toolbr.png), um einen Bereich über einem Bild zu definieren, den Sie als Link verwenden möchten. Nach der Definition eines Bereichs wird das Dialogfeld Referenz angezeigt, in dem Sie den Link zu internen oder externen Inhalten angeben müssen:

![](images/reference-dialog.png){width="650" align="left"}

Wenn sich Bereiche überschneiden, können Sie die Form nach vorne bringen oder durch Klicken auf das entsprechende Symbol in der Symbolleiste nach hinten senden. Sie können einen Bereich auch entfernen, indem Sie ihn auswählen und auf das Symbol Löschen klicken. Durch Doppelklicken auf einen Bereich wird das Dialogfeld Referenz geöffnet, in dem Sie den Ziel-Link ändern können. Nachdem Sie die erforderlichen Bereiche auf dem Bild markiert haben, speichern Sie die Änderungen, indem Sie **Fertig** auswählen.


**Multimedia**

Fügt verschiedene Arten von Multimediadateien ein. Wählen Sie das Symbol Multimedia-Dropdown und dann den Dateityp aus, den Sie einfügen möchten. Folgende Multimediaformate werden unterstützt:

- Audiodatei
- Videodatei
- YouTube
- Vimeo

Bei Auswahl der Option Audio- oder Videodatei wird die Repository-Ansicht angezeigt, in der Sie die gewünschte Datei suchen und auswählen können. Wenn Sie YouTube oder Vimeo wählen, erhalten Sie den Dialog Multimedia einfügen. Fügen Sie den Link der Videodatei in das Feld Weblink ein und wählen Sie Einfügen aus, um das Video an der aktuellen oder nächsten gültigen Position in Ihrem Dokument hinzuzufügen.

>[!NOTE]
>
> Beim Hinzufügen eines YouTube-Video-Links müssen Sie die Zeichenfolge `watch?v=` durch `embed` in der URL ersetzen. Um beispielsweise einen YouTube-Video-Link hinzuzufügen: `https://www.youtube.com/**watch?v**=WlIKQOrmZcs`, müssen Sie ihn wie folgt hinzufügen: `https://www.youtube.com/**embed/**WlIKQOrmZcs`. Durch diese Änderung wird sichergestellt, dass das Video in die AEM-Site und die PDF-Ausgabe eingebettet wird.

Sie können die Audio- oder Videodatei auch über das Dialogfeld „Multimedia einfügen“ hinzufügen. Wählen Sie die Option Audio-/Videodatei und dann das Symbol „Durchsuchen“ aus, um die Repository-Ansicht zu starten. Wählen Sie die Audio- oder Videodatei aus dem Repository aus und klicken Sie auf **Auswählen**, um den Link der Datei in das Feld Audio-/Videodatei einzufügen. Wenn Sie eine Videodatei auswählen, wird auch eine Vorschau der Datei im Bereich Vorschau angezeigt. Sie können die Videodatei abspielen, um ihre Vorschau anzuzeigen.

![](images/insert-multimedia.png){width="650" align="left"}

**Querverweis**

Fügen Sie Verweise vom Typ ein - Inhaltsreferenz, Inhaltsschlüsselreferenz, Schlüsselreferenz, Dateireferenz, Weblink oder E-Mail-Link.

Wählen Sie das Symbol **Datei auswählen** \(für Inhaltsreferenz und Dateireferenz\) oder **Stammzuordnungssymbol auswählen** \(für Inhaltsschlüsselreferenz und Schlüsselreferenz\) aus und wählen Sie die gewünschte Datei oder den gewünschten Inhalt aus, zu der bzw. dem eine Verknüpfung hergestellt werden soll.

![](images/insert-references.png){width="650" align="left"}

Dem Dokument wird ein Link der ausgewählten Referenz hinzugefügt. Das Kontextmenü für den Link bietet die folgenden Optionen:

- **Element einfügen**: Zeigt eine Liste gültiger Elemente an, die Sie im jeweiligen Kontext einfügen können.
- **UUID kopieren**: Kopiert die UUID der eingefügten Referenz.
- **Pfad kopieren**: Kopiert den vollständigen Pfad der eingefügten Referenz.
- **IDs generieren**: Generiert eine eindeutige ID für den eingefügten Verweis.

Sie können auch anhand der UUID der Datei suchen, auf die Sie verweisen möchten. Geben Sie für Links zu Inhalten und Schlüsselreferenzen die UUID der Datei ein, mit der Sie eine Verknüpfung herstellen möchten. Die Datei wird dann automatisch im Abschnitt Vorschau durchsucht und angezeigt. Wenn Sie die UUID der Datei angeben, müssen Sie die Dateierweiterung für XML-Dateien nicht explizit angeben. Die Erweiterung .xml wird automatisch an die UUID angehängt.

![](images/insert-content-using-uuid-search.png){width="650" align="left"}

Wenn Ihr Admin die Option UUIDs in *XMLEditorConfig* aktiviert hat, wird die UUID des referenzierten Inhalts in der Eigenschaft **Link** angezeigt.

![](images/ref-link-uuid_cs.png){align="left"}

>[!NOTE]
>
> Wenn die Option **UUIDs aktivieren** nicht aktiviert ist, wird der relative Pfad des referenzierten Inhalts angezeigt.

>[!IMPORTANT]
>
> Obwohl der relative Pfad des referenzierten Inhalts in der Eigenschaft **Link** angezeigt wird, wird der Link intern mithilfe der UUID des referenzierten Inhalts erstellt.

>[!TIP]
>
> Im Abschnitt „Verweise“ des Best Practices-Handbuchs finden Sie Best Practices für das Verweisen auf Inhalte.

**Filtersuche**

Sie können in den Dateien im ausgewählten Pfad des AEM-Repositorys nach Text suchen. Im folgenden Screenshot wird beispielsweise „Allgemein“ durchsucht. Sie können Ihre Suche auch mithilfe erweiterter Filter eingrenzen. Sie können nach allen DITA-Dateien wie DITA-Themen und DITA-Karten suchen, die im ausgewählten Pfad vorhanden sind.

Sie können im ausgewählten Pfad nach Nicht-DITA-Dateien wie Bilddateien, Multimedia und Dokumenten suchen. Sie können auch in den Attributen von DITA-Elementen nach bestimmten Werten suchen. Sie können auch nach Dateien suchen, die vom angegebenen Benutzer ausgecheckt wurden.

![](images/reference-search-filters.png){width="650" align="left"}

>[!NOTE]
>
> Ihre bzw. Ihr Systemadmin kann auch die Textfilter konfigurieren und andere Filter ein- oder ausblenden. Weitere Informationen finden Sie *Abschnitt „Konfigurieren von Textfiltern* im Abschnitt Installieren und Konfigurieren von Adobe Experience Manager Guides as a Cloud Service.

Die Liste der gefilterten Dateien, die den gesuchten Text enthalten, wird angezeigt. Im obigen Screenshot werden beispielsweise die Dateien aufgelistet, die den Text „Allgemein“ enthalten. Sie können auch eine Vorschau des Inhalts der Datei anzeigen.


**Wiederverwendbarer Inhalt** - ![](images/reusable-content.svg)

Inhalte wiederverwenden, die in einem anderen Dokument in Ihrem Projekt vorhanden sind. Sie können Inhalte einfügen, indem Sie eine direkte Verknüpfung mit dem Inhalt in einer Datei herstellen oder einen Schlüsselverweis verwenden, Ansicht [Schlüsselverweise auflösen](map-editor-other-features.md#id176GD01H05Z). Wenn Sie auf das Symbol Wiederverwendbarer Inhalt klicken, wird das Dialogfeld Inhalt wiederverwenden angezeigt:

![](images/reuse-content-dialog.png){width="650" align="left"}

Wählen Sie im Dialogfeld Inhalt wiederverwenden die DITA-Datei für Dateiverweise oder die DITA-Zuordnungsdatei mit den Schlüsselverweisen aus. Nach der Auswahl werden die Themen- oder Schlüsselverweise im Dialogfeld angezeigt. Sie können die ID/den Schlüssel des Themas auswählen, das Sie einfügen möchten, und auf **Fertig** klicken, um den Inhalt in Ihr Thema einzufügen.

Zum Einfügen der Inhaltsreferenz können Sie auch die UUID der Datei eingeben. Der wiederverwendbare Inhalt dieser Datei wird dann im Abschnitt Vorschau aufgeführt.

Je nach Einstellung zum Einfügen von Links können Sie entweder die UUID des eingefügten Inhalts oder den relativen Pfad im Bedienfeld Eigenschaften oder in der Source-Code-Ansicht anzeigen. Der Link wird immer mit der UUID des referenzierten Inhalts erstellt. Sehen Sie *UUID-basierte Links konfigurieren* in der Adobe Experience Manager Guides as a Cloud Service installieren und konfigurieren.

>[!NOTE]
>
> Um Inhalte vor oder nach dem referenzierten Inhalt hinzuzufügen, verwenden Sie *Alt*+*Nach-*-Taste oder Alt+*Nach-*-Taste, um den Cursor an die gewünschte Position zu verschieben.

Sie können den referenzierten Inhalt auch innerhalb des Themas einbetten, indem Sie mit der rechten Maustaste auf den referenzierten Inhalt klicken und **Verweis durch Inhalt ersetzen** aus dem Kontextmenü auswählen.

**Symbol** - ![](images/symbol-icon.svg)

Fügt Sonderzeichen in das Thema ein. Wählen Sie das Symbol Symbol aus, um das Dialogfeld Sonderzeichen einfügen zu öffnen.

>[!NOTE]
>
> Experience Manager Guides bietet verschiebbare und in der Größe veränderbare Dialogfelder. Die Größe von Dialogfeldern mit zwei Querlinien in der rechten unteren Ecke kann geändert werden. Die Querlinien im Dialogfeld Sonderzeichen werden unten angezeigt.

![](images/insert-special-char.png){width="550" align="left"}

Im Dialogfeld Sonderzeichen einfügen können Sie anhand des Namens nach einem Sonderzeichen suchen. Alle Sonderzeichen werden in verschiedenen Kategorien gespeichert. Wählen Sie in der Dropdown-Liste Kategorie auswählen eine Kategorie aus. Die in der ausgewählten Kategorie verfügbaren Sonderzeichen werden angezeigt. Sie können mit den Pfeiltasten durch die Liste der Sonderzeichen navigieren oder das gewünschte Zeichen auswählen, das Sie einfügen möchten. Der Name und der Hexadezimalcode des ausgewählten Sonderzeichens werden unter der Liste angezeigt. Wählen Sie **Einfügen** aus, um das ausgewählte Zeichen in Ihr Dokument einzufügen.

**Keyword** - ![](images/Keyword_icon.svg)

Fügen Sie das in Ihrer DITA-Karte definierte Keyword ein. Wählen Sie die Option Keyword , um das Dialogfeld Schlüsselreferenz zu öffnen.

![](images/insert-keyword.png){width="550" align="left"}

Die Suchbegriffe werden in alphabetischer Reihenfolge aufgelistet. Sie können auch nach einem oder mehreren Suchbegriffen suchen, indem Sie eine Suchzeichenfolge in das Suchfeld eingeben. Das Suchergebnis gibt die Keywords zurück, die die Zeichenfolge in der ID oder im Wert enthalten. Die in Ihrer DITA-Zuordnung definierten Keywords werden in diesem Dialogfeld aufgeführt. Wählen Sie das Keyword aus, das Sie einfügen möchten, und wählen Sie **Einfügen**.

Sie können auch die Attribute des eingefügten Keywords ändern, indem Sie mit der rechten Maustaste auf das Keyword klicken und die Option Attribute auswählen. Das Dialogfeld **Attribute für Keyword“ wird geöffnet:

![](images/attributes-for-keyword.png){width="550" align="left"}

Sie können die Attribute des Keywords ändern oder dem Keyword ein neues Attribut hinzufügen.

**Snippets** - ![](images/insert-snippet-icon.svg)

Fügen Sie ein Snippet an der aktuellen oder der nächsten gültigen Position ein. Damit diese Funktion funktioniert, müssen Snippets in Ihrem System definiert sein. Weitere Informationen zum Hinzufügen eines Snippets finden Sie in der **Snippet**-Funktionsbeschreibung im Abschnitt [Linkes Bedienfeld](web-editor-features.md#left-panel).

Wenn Sie die Option Snippets auswählen, wird der Katalog Snippet einfügen angezeigt. Der Katalog ist kontextsensitiv, was bedeutet, dass die Snippets nur angezeigt werden, wenn sie am aktuellen Speicherort zulässig sind.

Das folgende Beispiel zeigt zwei vorkonfigurierte Snippets - „Warnung“ und „Fehler“, die an der aktuellen Position im Dokument eingefügt werden können.

![](images/insert-snippet.png){width="300" align="left"}

Wenn Sie einen Ausschnitt aus der Liste auswählen, wird er an der aktuellen oder nächsten gültigen Position im Dokument eingefügt. Der folgende Screenshot zeigt das in das Dokument eingefügte Fehler-Snippet:

![](images/error-snippet.png){width="400" align="left"}

**Zitate** - ![](images/Citations_icon.svg)

Erstellen Sie Zitate und fügen Sie sie zu Ihrem Inhalt hinzu. Erfahren Sie, wie Sie [Zitate in Ihren Inhalten hinzufügen und verwalten](./web-editor-apply-citations.md).

**Abfragedaten** - ![](images/data-sources-new-icon.svg)

Stellen Sie eine Verbindung mit Ihrer Datenquelle her und verwenden Sie die Daten zum Erstellen von Inhalten. Erfahren Sie, wie Sie [Daten aus Ihrer Datenquelle verwenden](./web-editor-content-snippet.md).

### Versionsinformationen und Als neue Version speichern

Die Funktion **Versionsinformationen und Als neue Version speichern** kombiniert Versionsverfolgung und Inhaltsspeicherung in einer einzigen Funktion.

- Versionsinformationen zeigen die aktuelle Version des Themas oder der Zuordnung an. Ein Sternchen (*) wird neben der Versionsnummer angezeigt, um nicht gespeicherte Änderungen anzuzeigen.

  Die Versionsnummer ändert sich mit jeder neuen Version, die für das Thema oder die Zuordnungsdatei erstellt wird. Wenn Sie an einem neu erstellten Dokument arbeiten, werden die Versionsinformationen als &quot;**&quot;**.

  ![](images/version-information.png){align="left"}


- **Als neue Version speichern** ist eine Schaltfläche, mit der Sie die im Thema vorgenommenen Änderungen speichern und außerdem eine neue Version des Themas erstellen können.

  ![](images/save-as-new-version.png){align="left"}


Wenn Sie ein Thema oder eine Zuordnung mit „Als **Version speichern“**, wird das folgende Dialogfeld angezeigt:

![](images/save-as-new-version-dialog.PNG){width="300" align="left"}

Geben Sie Kommentare und Versionsbezeichnungen ein, um die Änderungen zu identifizieren, und **Sie** Speichern“, um eine neue Version Ihrer Datei zu erstellen.

Wenn Sie die Option **Als neue Version speichern** auswählen, wird die erste Version des Themas in DAM erstellt, was auch zur derzeit aktiven Version Ihres Themas wird. Wenn Sie später zu einer älteren Version des Themas zurückkehren, wird diese zu Ihrer aktuellen aktiven Version des Themas.

Wenn Ihr Administrator über vorkonfigurierte Versionsbezeichnungen verfügt, werden Sie diese Bezeichnungen in einer Dropdown-Liste anzeigen. Sie können einen Titel aus der Liste der verfügbaren Bezeichnungen auswählen und Ihr Dokument speichern.

![](images/web-editor-pre-defined-labels.PNG){width="300" align="left"}

Beim Speichern eines Themas können Sie einen Kommentar hinzufügen, der die im Thema vorgenommenen Änderungen angibt. Dieser Kommentar wird im Versionsverlauf des Themas angezeigt.

Wenn Ihr Thema überprüft wird, erhalten Ihre Reviewer eine Benachrichtigung, dass eine neuere Version des Themas verfügbar ist. Er kann einfach auf die neueste Version Ihres Dokuments zugreifen und mit der Überprüfung der neuesten Version Ihres Themas fortfahren.

Wenn Sie den Mauszeiger über den Titel eines Themas bewegen, werden der Dateititel, der Dateipfad und die Versionsnummer angezeigt.

![](images/mouse-hover-on-title_cs.png){align="left"}

>[!NOTE]
>
> Sobald eine Version Ihres Themas verfügbar ist, können Sie Ihrem Thema auch Beschriftungen hinzufügen. Diese Beschriftungen können dann verwendet werden, um eine Grundlinie für die Veröffentlichung einer bestimmten Version Ihres Dokuments zu erstellen. Weitere Informationen zur Verwendung von Beschriftungen in Ihren Themen finden Sie unter [Beschriftungen verwenden](web-editor-use-label.md#).

### Sperren/Entsperren

Sperrt oder entsperrt die aktuelle Datei. Durch das Sperren einer Datei erhalten Sie exklusiven Schreibzugriff auf die Datei. Dadurch wird das Bearbeiten der Datei durch andere Benutzer eingeschränkt. Entsperren Sie die Datei , wenn andere Benutzer Bearbeitungszugriff haben sollen. Wenn die Datei entsperrt wird, werden die Änderungen in der aktuellen Version der Datei gespeichert.

![](images/web-editor-lock-button.png){align="left"}

Wenn Sie sich in der Kartenansicht befinden und die übergeordnete Karte erweitern, können Sie mit einem Klick alle Dateien in der Karte sperren. Erweitern Sie einfach die übergeordnete Zuordnungsdatei und wählen Sie die übergeordnete Datei aus. Dadurch werden alle Dateien in der Zuordnung ausgewählt. Dann können Sie auf **Sperren** ![](images/LockClosed_icon.svg) klicken, um alle Dateien innerhalb der Zuordnung zu sperren.

Im Repository-Bedienfeld werden die gesperrten Dateien mit einem Sperrsymbol angezeigt. Wenn Sie den Mauszeiger über dieses Sperrsymbol bewegen, wird die Option Gesperrt von Ihnen/Benutzername als QuickInfo angezeigt.

![](images/web-editor-locked-by-icon-new.png){width="350" align="left"}

Wenn eine Datei von einem anderen Benutzer gesperrt wird, wird beim Bewegen des Mauszeigers über das Sperrsymbol im Repository der Name des Benutzers angezeigt, der sie gesperrt hat. In diesem Fall wird die Datei im schreibgeschützten Modus geöffnet, wobei **Schreibgeschützter Zugriff** neben den Versionsinformationen angezeigt wird.

Als Administrator erhalten Sie auch Zugriff auf die Funktion **Entsperren erzwingen** mit der Sie die von anderen Benutzern gesperrte Datei entsperren können. Verwenden Sie diese Funktion, um auf die Bearbeitungsrechte für eine Datei zuzugreifen, die von anderen Benutzern gesperrt wurde.

![](images/web-editor-force-unlock-new.png){width="350" align="left"}

## Linkes Bedienfeld

Das linke Bedienfeld bietet schnellen Zugriff auf Sammlungen, Repository-Ansichten, Zuordnungsansichten und mehr Funktionen. Sie können das Bedienfeld erweitern, indem Sie **Symbol &quot;**&quot; in der linken unteren Ecke der Benutzeroberfläche auswählen. Verwenden Sie nach dem Erweitern das Symbol **Reduzieren**, um das Bedienfeld zu reduzieren. In der erweiterten Ansicht werden die Namen der Symbole angezeigt, die in der reduzierten Ansicht als QuickInfos angezeigt werden.

>[!NOTE]
>
> Die Größe des linken Bedienfelds kann geändert werden. Um die Größe des Bereichs zu ändern, bringen Sie den Cursor auf die Bereichsbegrenzung, der Cursor ändert sich in einen Doppelpfeil, wählen Sie und ziehen Sie, um die Größe des Bereichs zu ändern.

Das linke Bedienfeld bietet Zugriff auf die folgenden Funktionen:

- [Sammlungen](#collections)
- [Repository](#repository)
- [Map](#map)
- [Wiederverwendbarer Inhalt](#reusable-content)
- [umreißen](#outline)

Einige Funktionen im linken Bereich sind unter dem Abschnitt **Mehr** verfügbar. Wählen Sie das Symbol Mehr ![](images/Smock_MoreSmallList_18_N.svg), um auf die folgenden Funktionen zuzugreifen:

- [Glossar](#glossary)
- [Bedingungen](#conditions)
- [Subjektschema](#subject-scheme)
- [Snippets](#snippets)
- [Vorlagen](#templates)
- [Zitate](#citations)
- [Sprachvariablen](#language-variables)
- [Variablen](#variables)
- [Suchen und Ersetzen](#find-and-replace)
- [PDF-Vorlagen](#pdf-templates)
- [Überprüfung](#review)


Eine zusätzliche Option mit der Bezeichnung **Workfront** wird auch im linken Bereich angezeigt, wenn Adobe Workfront konfiguriert ist.

Weitere Informationen finden Sie unter [Workfront-Integration](./workfront-integration.md).

>[!NOTE]
>
> Die im linken Bedienfeld verfügbaren Funktionen werden von Ihrem Administrator verwaltet, sodass er die einzelnen im linken Bedienfeld vorhandenen Funktionen aktivieren oder deaktivieren kann. Im linken Bereich werden nur aktivierte Funktionen angezeigt. Weitere Informationen finden Sie im Abschnitt **Bedienfelder** der [Registerkartenleiste](#tab-bar).

Die Funktionen des linken Bedienfelds werden im Detail wie folgt erläutert:

### Sammlungen

Wenn Sie an einem Satz von Dateien oder Ordnern arbeiten, können Sie diese Ihrer Favoritenliste hinzufügen, um schnell darauf zuzugreifen. **Sammlungen** zeigen die Liste der von Ihnen hinzugefügten Dokumente und andere öffentlich zugängliche Listen von Dokumenten der anderen Benutzer an.

Standardmäßig können Sie die Dateien nach Titeln anzeigen. Wenn Sie mit dem Mauszeiger auf eine Datei zeigen, können Sie den Dateititel und den Dateipfad als QuickInfo anzeigen.

>[!NOTE]
>
> Als Administrator können Sie die Liste der Dateien nach Dateinamen im Editor anzeigen. Wählen Sie die **Dateiname** im Abschnitt **Konfiguration von Editor-Dateien** Benutzereinstellungen **aus**.

Um eine neue Sammlung zu erstellen, klicken Sie auf das Symbol &quot;+&quot; neben dem Bedienfeld „Sammlungen“, um das Dialogfeld **Neue Sammlung** aufzurufen:

![](images/favorite-new-collection.PNG){width="300" align="left"}

Geben Sie einen Titel und eine Beschreibung für die Sammlung ein, die Sie erstellen möchten. Wenn Sie **Öffentlich** auswählen, wird dieser Favorit auch anderen Benutzern angezeigt.

>[!NOTE]
>
> Sie können eine Sammlung auch über die Experience Manager Guides-Startseite erstellen. Öffnen Sie die Startseite, navigieren Sie zum Widget **Sammlungen** im Abschnitt [Übersicht](./intro-home-page.md#overview) und wählen Sie **Neue Sammlung** aus.

Um eine Datei zu Sammlungen hinzuzufügen, verwenden Sie eine der folgenden Methoden:

- Navigieren Sie zur gewünschten Datei oder zum gewünschten Ordner in der Repository-Ansicht, wählen Sie das Symbol *Optionen* aus, um das Kontextmenü zu öffnen, und wählen Sie **Hinzufügen zu** > **Sammlungen**. Im Dialogfeld **Zu Sammlungen hinzufügen** können Sie die Datei/den Ordner zu einem vorhandenen Favoriten hinzufügen oder einen neuen erstellen.

  ![](images/favorite-add-file-folder.png){width="300" align="left"}

- Klicken Sie im Editor mit der rechten Maustaste auf die Registerkarte einer Datei, um das Kontextmenü zu öffnen. Wählen Sie **Hinzufügen zu** > **Sammlungen**, um die Datei Ihrer Favoritenliste hinzuzufügen.

  ![](images/favorite-add-from-file-context-menu_cs.png){align="left"}


>[!NOTE]
>
> - Um ein Element aus der Favoritenliste zu entfernen, klicken Sie auf das Optionssymbol neben dem Element in einer Favoritensammlung und wählen Sie **Aus Sammlungen entfernen**.
> - Um die Datei in der Vorschau anzuzeigen, ohne sie zu öffnen, wählen Sie eine Datei aus und wählen **dann** Vorschau“ aus dem Menü „Optionen“.

**Optionsmenü für eine Sammlung**

Sie können auch viele Aktionen über das Menü Optionen ausführen, das für eine Sammlung verfügbar ist:

![](images/favorites-options.png){width="650" align="left"}

- **Umbenennen**: Umbenennen der ausgewählten Sammlung.
- **Löschen**: Löscht die ausgewählte Sammlung.
- **Aktualisieren**: Erstellt eine neue Liste mit Dateien und Ordnern aus dem Repository.
- **In Assets-Benutzeroberfläche anzeigen**: Den Datei- oder Ordnerinhalt in der Assets-Benutzeroberfläche anzeigen.

>[!NOTE]
>
> Sie können die Liste auch mithilfe des Aktualisierungssymbols oben aktualisieren.


### Repository

Wenn Sie das Repository-Symbol auswählen, erhalten Sie eine Liste der in DAM verfügbaren Dateien und Ordner. Standardmäßig können Sie die Dateien nach Titeln anzeigen. Wenn Sie mit dem Mauszeiger auf eine Datei zeigen, können Sie den Dateititel und den Dateinamen als QuickInfo anzeigen.

>[!NOTE]
>
> Als Administrator können Sie die Liste der Dateien nach Dateinamen im Editor anzeigen. Wählen Sie die **Dateiname** im Abschnitt **Konfiguration von Editor-Dateien** Benutzereinstellungen **aus**.

Es werden 75 Dateien gleichzeitig geladen. Jedes Mal, wenn Sie **Mehr laden**… auswählen, werden 75 Dateien geladen und die Schaltfläche wird nicht mehr angezeigt, wenn alle Dateien aufgelistet wurden. Dieses Laden im Batch ist effizient, und Sie können schneller auf die Dateien zugreifen als alle Dateien, die in einem Ordner vorhanden sind.

Sie können einfach zur gewünschten Datei in DAM navigieren und sie im Editor öffnen. Wenn Sie über die erforderlichen Zugriffsrechte zum Bearbeiten der Datei verfügen, können Sie dies tun.

Sie können auch eine Audio- oder Videodatei im Editor auswählen und wiedergeben. Sie können die Lautstärke oder
Die Ansicht des Videos. Im Kontextmenü haben Sie auch die Optionen zum Herunterladen, Ändern der Wiedergabe
Geschwindigkeit oder Bild im Bild anzeigen.

Wählen Sie eine Karte aus und drücken Sie die Eingabetaste oder doppelklicken Sie, um sie in der **Kartenansicht“** öffnen. Weitere Informationen finden Sie in der Beschreibung der Funktion **Kartenansicht** im Abschnitt [Linkes Bedienfeld](#left-panel). Wählen Sie ein Thema aus und drücken Sie die Eingabetaste oder doppelklicken Sie, um es im [Inhaltsbearbeitungsbereich“ ](#content-editing-area) öffnen. Die Möglichkeit, direkt im Editor in einer Datei zu navigieren und sie zu öffnen, spart Zeit und erhöht die Produktivität.

**Filtern der Suche im Repository**

Der Editor bietet erweiterte Filter für die Textsuche. Sie können in den Dateien im ausgewählten Pfad des Adobe Experience Manager-Repositorys nach einem Text suchen und filtern. Dabei werden Titel, Dateiname und Inhalt in den Dateien durchsucht.


![Suchen von Dateien in der Repository-Ansicht](images/repository-filter-search.png){width="300" align="left"}

*Filter anwenden, um nach den Dateien zu suchen, die den`personal spaceship.`* enthalten

Wählen Sie das Symbol **Filtersuche** \(![Suchfiltersymbol](images/filter-search-icon.svg)\) aus, um das Popup-Fenster „Filter“ zu öffnen.

>[!NOTE]
>
> Wenn Sie nach Text suchen oder Dateien filtern, wird auf dem Symbol **Suche filtern** \(![Suchfiltersymbol](images/filter-search-icon.svg)\) ein blauer Punkt angezeigt, um anzugeben, dass wir uns im Suchbereich befinden und dass einige Filter angewendet wurden.


Sie haben die folgenden Optionen, um die Dateien zu filtern und Ihre Suche im Adobe Experience Manager-Repository einzugrenzen:

- **DITA-Dateien**: Sie können nach allen **DITA-** und **DITA-Karten** suchen, die im ausgewählten Pfad vorhanden sind. Diese sind standardmäßig ausgewählt.
- **Nicht-DITA-Dateien**: Sie können im ausgewählten Pfad nach **DITAVAL-**, **Image-**, **Multimedia**, **Documents** und **JSON** suchen.

  ![Schnellsuchfilter ](images/repository-filter-search-quick.png) {width="300" align="left"}

  *Verwenden Sie die Filter für die schnelle Suche, um nach DITA- und Nicht-DITA-Dateien zu suchen.*

**Erweiterte Filterung**

Wählen Sie das Symbol **Erweiterte**![Erweitertes Filtersymbol](images/advanced-filter-gear-icon.svg), um das Dialogfeld **Erweiterter Filter** anzuzeigen.

Sie können die folgenden Optionen auf den Registerkarten **Allgemein** und **Erweitert** anzeigen.

![Dialogfeld „Erweiterter Filter“](images/repository-filter-search-advanced.png) {width="650" align="left"}


**Allgemein**

- **Suchergebnisse mit**: Suchen Sie nach Text in den Dateien, die im ausgewählten Pfad des Adobe Experience Manager-Repositorys vorhanden sind. Der Text wird im Titel, im Dateinamen und im Inhalt der Dateien durchsucht.

Dies ist mit dem Suchfeld im Repository-Fenster synchronisiert. Wenn Sie beispielsweise `general purpose` in das Suchfeld im Repository-Bereich eingeben, wird es auch im Dialogfeld **Erweiterter Filter** angezeigt und umgekehrt.

- **Suchen in**: Wählen Sie den Pfad aus, unter dem Sie die Dateien im Adobe Experience Manager-Repository suchen möchten.

**Erweitert**

- **DITA-Elemente**: Sie können auch in den Attributen der angegebenen DITA-Elemente nach bestimmten Werten suchen.
   - Wählen Sie **Element hinzufügen** aus, um die Elemente, Attribute und Werte hinzuzufügen.
   - Wenden Sie die ausgewählten Filter an.

- Wählen Sie **Alle löschen**, um alle angewendeten Filter zu löschen.


- Wählen Sie das Symbol **Filter schließen** ![Symbol schließen](images/close-icon.svg) aus, um den Filter zu schließen und zur Strukturansicht des Repositorys zurückzukehren.

  >[!NOTE]
  >
  >Ihre bzw. Ihr Systemadmin kann auch die Textfilter konfigurieren und andere Filter ein- oder ausblenden. Weitere Informationen finden Sie *Abschnitt „Konfigurieren von Textfiltern* im Abschnitt Installieren und Konfigurieren von Adobe Experience Manager Guides as a Cloud Service.
  >
  >Die Liste der gefilterten Dateien, die den gesuchten Text enthalten, wird angezeigt. Beispielsweise werden die Dateien, die die `personal spaceship` enthalten, im vorherigen Screenshot aufgelistet. Sie können mehrere Dateien aus der gefilterten Liste auswählen, um sie per Drag-and-Drop auf eine Karte zu ziehen, die zur Bearbeitung geöffnet ist.

**Menü „Optionen**

Neben dem Öffnen von Dateien über den linken Bereich können Sie auch viele Aktionen über das Menü Optionen in der Repository-Ansicht ausführen. Je nachdem, ob Sie einen Ordner, eine Themendatei oder eine Mediendatei auswählen, werden unterschiedliche Optionen angezeigt.

**Optionen für einen Ordner**

Sie können die folgenden Aktionen mithilfe des Menüs Optionen ausführen, das für einen *Ordner* in der Repository-Ansicht verfügbar ist:

![](images/options-menu-folder_cs.PNG){width="550" align="left"}


- **Neu**: Erstellen Sie ein neues DITA-Thema, eine neue DITA-Karte oder einen neuen Ordner.

  Schritte zum Erstellen eines neuen Themas:
   1. Wählen Sie **Neu** > **Thema** aus.
   2. Das **Neues Thema** wird angezeigt.

      ![](images/create-topic-dialog.png){width="300" align="left"}

   3. Geben **im Dialogfeld** Neues Thema“ die folgenden Details an:
      - Ein Titel für das Thema.
      - \(Optional\)* Der Dateiname für das Thema. Der Dateiname wird basierend auf dem Thementitel automatisch vorgeschlagen. Wenn Ihr Administrator automatische Dateinamen basierend auf der UUID-Einstellung aktiviert hat, wird das Feld Name nicht angezeigt.
      - Eine Vorlage, auf der das Thema basieren soll. Bei einem vorkonfigurierten Setup können Sie beispielsweise aus den Vorlagen „Leer“, „Konzept“, „DIGITAL“, „Referenz“, „Aufgabe“, „Thema“, „Markdown“, „Glossar“ und „Fehlerbehebung“ wählen. Wenn für Ihren Ordner ein Ordnerprofil konfiguriert ist, zeigen Sie nur die Themenvorlagen an, die für das Ordnerprofil konfiguriert sind.

      - Pfad zum Speichern der Themendatei. Standardmäßig wird der Pfad des aktuell ausgewählten Ordners im Repository im Feld Pfad angezeigt.

   4. Wählen Sie **Erstellen**. Das Thema wird unter dem angegebenen Pfad erstellt. Außerdem wird das Thema im Editor zur Bearbeitung geöffnet.

  Schritte zum Erstellen einer neuen DITA-Zuordnung:

   1. Wählen Sie **Neu** > **DITA-Karte**.
   2. Das **Neue Zuordnung** wird angezeigt.

      ![](images/create-map-dialog.png){width="300" align="left"}

   3. Geben **im Dialogfeld** Neue Zuordnung“ die folgenden Details an:
      - Ein Titel für die Karte.
      - *\(Optional\)* Der Dateiname für die Zuordnung. Der Dateiname wird basierend auf dem Zuordnungstitel automatisch vorgeschlagen. Wenn Ihr Administrator automatische Dateinamen basierend auf der UUID-Einstellung aktiviert hat, wird das Feld Name nicht angezeigt.
      - Eine Vorlage, auf der die Zuordnung basieren soll. Für ein vorkonfiguriertes Setup können Sie beispielsweise aus den Vorlagen „Bookmap“ oder „DITA Map“ auswählen.
      - Pfad, in dem die Zuordnungsdatei gespeichert werden soll. Standardmäßig wird der Pfad des aktuell ausgewählten Ordners im Repository im Feld Pfad angezeigt.
   4. Wählen Sie **Erstellen**. Die Zuordnung wird innerhalb des im Feld Pfad angegebenen Ordners erstellt und hinzugefügt. Außerdem wird die Karte in der Kartenansicht geöffnet. Sie können die Zuordnungsdatei im Zuordnungs-Editor öffnen und ihr ein Thema hinzufügen. Weitere Informationen zum Hinzufügen von Themen zu einer Zuordnungsdatei finden Sie unter [Erstellen einer Zuordnung](map-editor-create-map.md#). Wählen Sie alternativ **In Map-Konsole öffnen** aus, um die Zuordnung in der Map-Konsole zu öffnen.

  Schritte zum Erstellen eines neuen Ordners:

   1. Wählen Sie **Neu** > **Ordner** aus.
   2. Das **Neuer Ordner**-Dialogfeld wird angezeigt.

      ![](images/new-folder-dialog_cs.png){width="300" align="left"}

   3. Geben **im Dialogfeld** Neuer Ordner“ die folgenden Details an:
      - Ein Titel für den Ordner, der automatisch in den Ordnernamen konvertiert wird.
      - Pfad, in dem der Ordner gespeichert werden soll. Standardmäßig wird der Pfad des aktuell ausgewählten Ordners im Repository im Feld Pfad angezeigt.
   4. Wählen Sie **Erstellen**. Der Ordner wird in dem Ordner erstellt und hinzugefügt, von dem aus die Option Ordner erstellen ausgeführt wurde.

- **Assets hochladen**: Laden Sie eine Datei aus Ihrem lokalen System in den ausgewählten Ordner im Adobe Experience Manager-Repository hoch. Sie können auch Dateien aus Ihrem lokalen System per Drag-and-Drop auf das aktuelle Arbeitsthema ziehen. Dies ist sehr nützlich, wenn Sie Bilder aus Ihrem lokalen System in Ihr Thema einfügen möchten.

  ![](images/upload-assets.png){width="300" align="left"}

  Sie können einen Ordner auswählen, in den Sie die Datei hochladen möchten, und es wird auch eine Vorschau des Bildes angezeigt. Wenn Sie die Datei umbenennen möchten, können Sie dies im Textfeld Dateiname tun. Wählen Sie **Hochladen** aus, um den Datei-Upload abzuschließen. Wenn Sie eine Bilddatei per Drag-and-Drop auf ein Thema gezogen haben, wird die Bilddatei zum Artikel hinzugefügt und auch hochgeladen.

  Wenn Ihr Admin die Option UUIDs in *XMLEditorConfig* aktiviert hat, wird die UUID des hochgeladenen Bildes in der Eigenschaft **Source** angezeigt.

  ![](images/uuid-in-source-upload-image_cs.png){align="left"}

- **Dateien in Ordner suchen**: Versetzt den Fokus auf die Repository-Suche, in der Sie den Suchbegriff eingeben können. Die Suche wird unter dem ausgewählten Ordner im Repository durchgeführt. Sie können auch einen Filter anwenden, um DITA-Dateien, Bilddateien oder beides zurückzugeben.

  ![](images/find-files-in-folders-repo-view_cs.png){width="300" align="left"}

  Sie können auch mit der UUID einer Datei suchen. In diesem Fall zeigen die Suchergebnisse den Titel der DITA/XML-Datei an. Wenn es sich bei der Datei um eine Bilddatei handelt, wird die UUID der Datei angezeigt. Im folgenden Suchbeispiel wird die UUID einer Bilddatei durchsucht und in den Suchergebnissen die UUID der Originalbilddatei sowie der Thementitel der Datei angezeigt, in der auf dieses Bild verwiesen wird.

  ![](images/uuid-repo-search-image-topic-file_cs.png){width="300" align="left"}

- **Reduzieren**: Reduziert den ausgewählten Ordner im Repository.

  >[!NOTE]
  >
  > Erweitern Sie den Ordner mit dem Symbol **\>** neben einem Ordner.

- **Zu Sammlungen hinzufügen**: Fügt den ausgewählten Ordner zu den Favoriten hinzu. Sie können sie zu einer vorhandenen oder neuen Sammlung hinzufügen.

- **Aktualisieren**: Erstellt eine neue Liste mit Dateien und Ordnern aus dem Repository.
- **In Assets-Benutzeroberfläche anzeigen**: Zeigt den Ordnerinhalt in der Assets-Benutzeroberfläche an.

**Optionen für eine Datei**

Sie erhalten Zugriff auf verschiedene Optionen im Menü Optionen , je nachdem, ob Sie eine Mediendatei oder eine DITA-Datei auswählen. Einige gängige Optionen für Medien- und DITA-Dateien sind:

- Bearbeiten
- In FrameMaker öffnen
- Duplizieren
- Sperren/Entsperren
- Vorschau
- Verschieben nach
- Umbenennen
- Löschen
- Generieren
- Als PDF herunterladen
- Hinzufügen zu
- Kopieren
- In der Assets-Benutzeroberfläche anzeigen
- Eigenschaften


![Optionsmenü einer Datei in der Repository-Ansicht](images/options-menu-repo-view-file-level.png){width="550" align="left"}

Die verschiedenen Optionen im Menü „Optionen“ werden nachfolgend erläutert:

- **Bearbeiten**: Öffnen Sie die Datei zur Bearbeitung. Im Falle einer .ditamap/.bookmap-Datei wird diese zur Bearbeitung im [Map Editor](map-editor-advanced-map-editor.md#) geöffnet.

- **Duplizieren**: Mit dieser Option erstellen Sie ein Duplikat oder eine Kopie der ausgewählten Datei. Sie haben außerdem die Möglichkeit, die doppelte Datei in der Aufforderung Asset duplizieren umzubenennen. Standardmäßig wird die Datei mit dem Suffix \ (wie Dateiname\_1.extension\) erstellt. Der Titel der Datei bleibt gleich wie der der Quelldatei, und die neue Datei beginnt mit Version 1.0. Alle Verweise, Tags und Metadaten werden kopiert, während die Baselines nicht in die doppelte Datei kopiert werden.
- **Sperren**: Sperrt die ausgewählte Datei, damit sie bearbeitet werden kann. Wenn die Datei gesperrt ist, wird durch Bewegen des Mauszeigers über dem Sperrsymbol **Gesperrt von Ihnen** angezeigt, wenn Sie sie gesperrt haben, oder **Gesperrt von [Benutzername]**, wenn ein anderer Benutzer sie gesperrt hat.

- **Vorschau**: Erhalten Sie eine schnelle Vorschau der Datei (.dita, .xml, Audio, Video oder Bild), ohne sie zu öffnen. Sie können die Größe des Vorschaubereichs ändern. Wenn der Inhalt `<xref>` oder `<conref>` enthält, können Sie diese auswählen, um sie in einer neuen Registerkarte zu öffnen. Der Titel der Datei wird im Fenster angezeigt. Wenn kein Titel vorhanden ist, wird der Dateiname angezeigt. Um das Bedienfeld **Vorschau** zu schließen, können Sie entweder das Symbol zum Schließen auswählen oder eine beliebige Stelle außerhalb des Bereichs auswählen.

  ![](images/quick-preview_cs.png){align="left"}

- **Umbenennen**: Verwenden Sie diese Option, um die ausgewählte Datei umzubenennen. Geben Sie den Namen der neuen Datei im Dialogfeld **Asset umbenennen** ein.
   - Sie können eine Datei beliebigen Typs umbenennen.
   - Die Dateierweiterung kann nicht geändert werden.
   - Zwei Dateien dürfen nicht denselben Namen haben. Sie können also eine Datei nicht in einen bereits vorhandenen Namen umbenennen. Ein Fehler wird angezeigt.

- **Verschieben nach**: Verwenden Sie diese Option, um die ausgewählte Datei in einen anderen Ordner zu verschieben.
   - Sie können entweder den Namen des Zielordners eingeben oder **Pfad auswählen** um den Zielordner auszuwählen.
   - Sie können eine Datei beliebigen Typs an ein beliebiges Ziel im Inhaltsordner verschieben.
   - Zwei Dateien dürfen nicht denselben Namen haben. Daher können Sie eine Datei nicht in einen Ordner verschieben, in dem bereits eine Datei mit demselben Namen vorhanden ist.

  Wenn Sie versuchen, eine Datei in einen Ordner zu verschieben, in dem eine Datei mit demselben Namen, aber einem anderen Titel vorhanden ist, wird das Dialogfeld Umbenennen und Datei verschieben angezeigt, und Sie müssen die Datei vor dem Verschieben umbenennen. Die verschobene Datei im Zielordner hat den neuen Dateinamen.

  ![](images/rename-move-asset.png){width="550" align="left"}

  >[!NOTE]
  >
  > Sie können eine Datei auch per Drag-and-Drop in einen anderen Zielordner ziehen.

  **Ausschlussszenarien**

  In Experience Manager Guides ist es in den folgenden Szenarien nicht zulässig, eine Datei umzubenennen oder zu verschieben:

   - Sie können eine Datei nicht verschieben oder umbenennen, wenn sie Teil eines Überprüfungs- oder Übersetzungs-Workflows ist.

   - Wenn die Datei von einem anderen Benutzer gesperrt wird, ist ein Umbenennen oder Verschieben der Datei nicht möglich. Die Optionen Umbenennen oder Verschieben nach für die Datei werden nicht angezeigt.

  >[!NOTE]
  >
  > Wenn Ihnen der Administrator Berechtigungen für einen Ordner erteilt hat, werden nur die Optionen **Umbenennen** oder **Verschieben nach** angezeigt.

  <details>
    <summary> Cloud Services </summary>

  Beim Umbenennen oder Verschieben einer Datei werden vorhandene Verweise von oder auf die Datei nicht beschädigt, da jede Datei eine eindeutige UUID hat.
  </details>

- **Löschen**: Mit dieser Option können Sie die ausgewählte Datei löschen. Vor dem Löschen der Datei wird eine Bestätigungsaufforderung angezeigt.

   - Vor dem Löschen der Datei wird eine Bestätigungsaufforderung angezeigt.
   - Wenn keine andere Datei auf die Datei verweist, wird sie gelöscht und eine Erfolgsmeldung wird angezeigt.
   - Wenn die Datei gesperrt ist, können Sie sie nicht löschen, und es wird eine Fehlermeldung angezeigt.

     >[!NOTE]
     >
     > Wenn Ihr Administrator das Löschen gesperrter Dateien verhindert hat, wird nur die Fehlermeldung angezeigt. Weitere Informationen finden Sie *Abschnitt „Löschen von ausgecheckten Dateien verhindern* im Abschnitt Installieren und Konfigurieren von Adobe Experience Manager Guides as a Cloud Service.

   - Wenn die Datei einer Sammlung hinzugefügt wird, wird das **Löschen erzwingen** angezeigt, und Sie können das Löschen erzwingen.
   - Wenn die Datei von einer anderen Datei referenziert wird, wird **Löschen erzwingen** Dialogfeld mit der Bestätigungsmeldung angezeigt, und Sie können die Datei erzwingen:

     ![](images/options-menu-force-delete.png){width="300" align="left"}

     >[!NOTE]
     >
     > Wenn der Administrator die Berechtigung zum Löschen von Dateien erteilt hat, ist **Löschen erzwingen** aktiviert. Andernfalls ist **Löschen erzwingen** deaktiviert und es wird eine Meldung angezeigt, dass Sie nicht berechtigt sind, referenzierte Dateien zu löschen. Weitere Informationen finden Sie im Abschnitt *Verhindern des Löschens referenzierter Dateien* im Abschnitt Installieren und Konfigurieren von Adobe Experience Manager Guides as a Cloud Service.

   - Wenn Sie ein referenziertes Thema löschen und die Datei mit Verweisen zur Bearbeitung geöffnet haben, wird der fehlerhafte Link für die referenzierte Datei angezeigt.

  >[!NOTE]
  >
  > Sie können die ausgewählte Datei auch auf ähnliche Weise mit der Löschen -Taste der Tastatur löschen.

- **Kopieren**: Sie können aus den folgenden Optionen auswählen:

   - **UUID kopieren**: Kopieren Sie die UUID der ausgewählten Datei in die Zwischenablage.

   - **Pfad kopieren**: Kopieren Sie den vollständigen Pfad der ausgewählten Datei in die Zwischenablage.

- **Hinzufügen zu**: Sie können aus den folgenden Optionen auswählen:
   - **Sammlungen**: Fügt die ausgewählte Datei zu Sammlungen hinzu. Sie können sie zu einer vorhandenen oder neuen Sammlung hinzufügen.

   - **Wiederverwendbarer Inhalt**: Fügt die ausgewählte Datei der Liste Wiederverwendbarer Inhalt im linken Bereich hinzu.

- **Eigenschaften**: Hiermit können Sie die Eigenschaftsseite der ausgewählten Datei öffnen. Sie können auf diese Eigenschaftenseite auch über die Assets-Benutzeroberfläche zugreifen, indem Sie eine Datei auswählen und dann in der Symbolleiste das Symbol Eigenschaften auswählen.

- **Im Zuordnungs-Dashboard öffnen**: Wenn die ausgewählte Datei eine DITA-Zuordnung ist, wird durch diese Option das Zuordnungs-Dashboard geöffnet.

- **In Map-Konsole öffnen**: Falls die ausgewählte Datei eine DITA-Map ist, wird mit dieser Option die Map-Konsole geöffnet.

- **In Sauerstoff bearbeiten**: Wählen Sie diese Option, um die ausgewählte Datei im Oxygen Connector-Plug-in zu bearbeiten. Die Datei wird zur Bearbeitung geöffnet.

  >[!NOTE]
  >
  >Wenden Sie sich an Ihr Customer Success-Team , um diese Funktion in der Umgebung aktivieren zu lassen. Dies ist nicht als Teil der vordefinierten Unterstützung aktiviert. Weitere Informationen finden Sie im Abschnitt [Konfigurieren der Option zur Bearbeitung in Oxygen](../cs-install-guide/conf-edit-in-oxygen.md) im Installations- und Konfigurationshandbuch.


- **In Assets-Benutzeroberfläche anzeigen**: Verwenden Sie diese Option, um eine Vorschau einer .dita/.xml-Datei in der Assets-Benutzeroberfläche anzuzeigen. Bei einer .ditamap/.bookmap-Datei werden alle Themendateien innerhalb der Karte in einer einzigen einheitlichen Seitenansicht angezeigt.

- **Als PDF herunterladen**: Verwenden Sie die Option, um die PDF-Ausgabe zu generieren und herunterzuladen.

- **Generieren**: Verwenden Sie die Option, um eine Karte oder Themen innerhalb einer Karte auf einer Sites-Seite, in einem Inhaltsfragment oder in einem Experience Fragment zu veröffentlichen.

### Map

Wenn Sie das Symbol Kartenansicht auswählen, wird die Kartenansicht angezeigt, in der eine Liste von Themen in der Kartendatei angezeigt wird. Wenn Sie keine Zuordnungsdatei geöffnet haben, erscheint die Zuordnungsansicht leer. Ein Doppelklick auf eine Kartendatei öffnet die Kartendatei in dieser Ansicht. Sie können auf eine Datei innerhalb der Karte doppelklicken, um sie im Editor zu öffnen.

Standardmäßig können Sie die Dateien nach Titeln anzeigen. Wenn Sie mit dem Mauszeiger auf eine Datei zeigen, können Sie den Dateititel und den Dateipfad als QuickInfo anzeigen.

>[!NOTE]
>
>Als Administrator können Sie auch den Dateinamen der übergeordneten Zuordnung anzeigen, die derzeit in der Zuordnungsansicht geöffnet ist. Wählen Sie die **Dateiname** im Abschnitt **Konfiguration von Editor-Dateien** Benutzereinstellungen **aus**.


Wenn Sie eine Karte in der Kartenansicht öffnen, wird der Titel der aktuellen Karte in der Mitte der Registerkartenleiste angezeigt. Wenn der Titel zu lang ist, werden Auslassungspunkte angezeigt. Sie können auch den Mauszeiger über den Titel bewegen, um den vollständigen Titel in der QuickInfo anzuzeigen.

Wenn Sie Schlüsselattribute für die Themen- oder Zuordnungsreferenzen definieren, können Sie den Titel, das entsprechende Symbol und den Schlüssel im linken Bereich anzeigen. Die Taste wird als `keys=<key-name>` angezeigt.

![Schlüssel in der Kartenansicht](images/view-key-title-map-view.png){width="300" align="left"}

Wenn Sie Bearbeitungsrechte für die Zuordnungsdateien haben, können Sie auch die Dateien bearbeiten. Weitere Informationen zum Öffnen und Bearbeiten eines Themas über DITA Map finden Sie unter [Themen über DITA Map bearbeiten](map-editor-advanced-map-editor.md#id17ACJ0F0FHS).

Die folgenden Optionen sind für eine Zuordnungsdatei in der Zuordnungsansicht verfügbar:

- **In Map-Konsole öffnen**: Öffnet die Map-Datei in der Map-Konsole.
- **Bearbeiten**: Öffnet die Zuordnungsdatei zur Bearbeitung.
- **Optionen**: Öffnet das Kontextmenü für die ausgewählte Zuordnungsdatei.

Mit dem Menü Optionen der Zuordnungsdatei können Sie die folgenden Aktionen ausführen:

![Optionsmenü in der Kartenansicht](images/options-menu-map-view_cs.png){align="left"}

- **Bearbeiten**: Öffnen Sie die Zuordnungsdatei zur Bearbeitung im Zuordnungs-Editor.

- **Alle auswählen** Wählen Sie alle Dateien in der Zuordnung aus.

- **Auswahl aufheben**: Heben Sie die Auswahl der ausgewählten Dateien in der Zuordnung auf.

- **lock**: Ermöglicht es Ihnen, die ausgewählten Dateien in der Zuordnung zu sperren.

- **Entsperren**: Entsperrt die Zuordnungsdatei und stellt sie zur Bearbeitung bereit. Die Änderungen werden nicht auf eine frühere Version zurückgesetzt.

- **Als neue Version speichern und entsperren**: Erstellen Sie eine neuere Version und lösen Sie die Sperre für die ausgewählten Dateien in der Zuordnung.

- **Vorschau**: Öffnet eine Vorschau der Zuordnungsdatei. In dieser Ansicht werden alle Themendateien innerhalb der Zuordnung in einer einzigen, einheitlichen Seitenansicht angezeigt.

- **Kopieren**: Sie können aus den folgenden Optionen auswählen:
   - **UUID kopieren**: Kopieren Sie die UUID der Zuordnungsdatei in die Zwischenablage.
   - **Pfad kopieren**: Kopieren Sie den vollständigen Pfad der Zuordnungsdatei in die Zwischenablage.

- **Im Repository suchen**: Zeigt den Speicherort der Zuordnungsdatei im Repository \(oder DAM\) an.

- **Hinzufügen zu**: Sie können aus den folgenden Optionen auswählen:
   - **Sammlungen**: Fügt die Zuordnungsdatei zu Sammlungen hinzu. Sie können sie zu einer vorhandenen oder neuen Sammlung hinzufügen.

   - **Wiederverwendbarer Inhalt**: Fügt die Zuordnungsdatei zur Liste der wiederverwendbaren Inhalte im linken Bereich hinzu.

- **Eigenschaften**: Verwenden Sie diese Option, um die Eigenschaftenseite der Zuordnungsdatei zu öffnen. Sie können auf diese Eigenschaftsseite auch über die Assets-Benutzeroberfläche zugreifen, indem Sie eine Datei auswählen und in der Symbolleiste auf das Symbol Eigenschaften klicken.

- **Karten-Dashboard öffnen**: Öffnet das Karten-Dashboard.

- **In Assets-Benutzeroberfläche anzeigen**: Verwenden Sie diese Option, um eine Vorschau der Zuordnungsdatei in der Assets-Benutzeroberfläche anzuzeigen. In dieser Ansicht werden alle Themendateien innerhalb der Zuordnung in einer einzigen, einheitlichen Seitenansicht angezeigt.
- **Karte herunterladen**: Wählen Sie diese Option, um das Dialogfeld **Karte herunterladen** zu öffnen.

  Im **Karte herunterladen** können Sie die folgenden Optionen auswählen:

  **Baseline verwenden**: Wählen Sie diese Option, um eine Liste der Baselines zu erhalten, die für die DITA-Zuordnung erstellt wurden. Wenn Sie die Zuordnungsdatei und deren Inhalte basierend auf einer bestimmten Baseline herunterladen möchten, wählen Sie die Baseline aus der Dropdown-Liste aus. Weitere Informationen zum Arbeiten mit Grundlinien finden Sie unter [Arbeiten mit Grundlinien](./generate-output-use-baseline-for-publishing.md).

  **Dateihierarchie reduzieren**: Wählen Sie diese Option, um alle referenzierten Themen und Mediendateien in einem Ordner zu speichern.

  Sie können die Zuordnungsdatei auch herunterladen, ohne eine Option auszuwählen. In diesem Fall werden die letzten persistierten Versionen der referenzierten Themen und Mediendateien heruntergeladen.

  Nachdem Sie auf die Schaltfläche **Herunterladen** geklickt haben, wird die Anfrage für das Zuordnungspaket in die Warteschlange gestellt. Das **Erfolg**-Dialogfeld wird angezeigt, wenn das Paket erfolgreich erstellt wurde.  Sie können die Schaltfläche **Herunterladen** im Dialogfeld **Erfolg** auswählen.

  Sie erhalten die Benachrichtigung „Map-Download bereit“, wenn die Karte zum Herunterladen bereit ist. Falls der Download fehlschlägt, erhalten Sie die Benachrichtigung, dass der Map-Download fehlgeschlagen ist.

  Sie können auf den Download-Link über den Adobe Experience Manager-Benachrichtigungs-Posteingang zugreifen. Wählen Sie die generierte Zuordnungsbenachrichtigung im Posteingang aus, um die Zuordnung im ZIP-Format herunterzuladen.

  >[!NOTE]
  >
  >  Standardmäßig bleiben die heruntergeladenen Zuordnungen fünf Tage lang im Adobe Experience Manager-Benachrichtigungs-Posteingang.

- **Zuordnungskontext schließen**: Schließt die Zuordnungsdatei.

Der folgende Screenshot zeigt das Optionsmenü für eine Datei in der Kartenansicht:

![](images/options-menu-file_cs.PNG){align="left"}

Mit dem Menü Optionen können Sie die folgenden Aktionen ausführen:

- **Bearbeiten**: Öffnen Sie die Datei zur Bearbeitung. Im Falle einer .ditamap/.bookmap-Datei wird diese zur Bearbeitung im [Map Editor](map-editor-advanced-map-editor.md#) geöffnet.

- **lock**: Sperrt die ausgewählte Datei. Bei gesperrten Dateien ändert sich diese Option in **Entsperren**.



  >[!NOTE]
  >
  > - Wenn eine Datei von einem Benutzer gesperrt ist, wird durch Bewegen des Mauszeigers über dem Sperrsymbol der Benutzer \(name\) angezeigt, der die Datei gesperrt hat.
  > - Wenn Sie eine Datei einchecken, werden Sie aufgefordert, die Änderungen zu speichern. Wenn Sie Ihre Änderungen nicht speichern, wird nur die Datei eingecheckt.

- **Vorschau**: Erhalten Sie eine schnelle Vorschau der Datei (.dita, .xml, Audio, Video oder Bild), ohne sie zu öffnen. Sie können die Größe des Vorschaubereichs ändern. Wenn der Inhalt `<xref>` oder `<conref>` enthält, können Sie diese auswählen, um sie in einer neuen Registerkarte zu öffnen.  Der Titel der Datei wird im Fenster angezeigt. Wenn kein Titel vorhanden ist, wird der Dateiname angezeigt. Um den Bereich **Vorschau** zu schließen, können Sie entweder das Symbol zum Schließen auswählen oder eine beliebige Stelle außerhalb des Bereichs auswählen.
- **Kopieren**: Sie können aus den folgenden Optionen auswählen:
   - **UUID kopieren**: Kopieren Sie die UUID der ausgewählten Datei in die Zwischenablage.
   - **Pfad kopieren**: Kopieren Sie den vollständigen Pfad der ausgewählten Datei in die Zwischenablage.


- **Im Repository suchen**: Zeigt den Speicherort der ausgewählten Datei im Repository \(oder DAM\) an.
- **Alle erweitern**: Alle Themen in den Zuordnungsdateien erweitern.

- **Alle reduzieren**: Alle Themen ausblenden, die Teil der aktuellen Zuordnungsdatei sind.

- **Hinzufügen zu**: Sie können aus den folgenden Optionen auswählen:
   - **Sammlungen**: Fügt die ausgewählte Datei zu Sammlungen hinzu. Sie können sie zu einer vorhandenen oder neuen Sammlung hinzufügen.

   - **Wiederverwendbarer Inhalt**: Fügt die ausgewählte Datei der Liste Wiederverwendbarer Inhalt im linken Bereich hinzu.

- **Eigenschaften**: Hiermit können Sie die Eigenschaftsseite der ausgewählten Datei öffnen. Sie können auf diese Eigenschaftsseite auch über die Assets-Benutzeroberfläche zugreifen, indem Sie eine Datei auswählen und in der Symbolleiste auf das Symbol Eigenschaften klicken.

- **In Assets-Benutzeroberfläche anzeigen**: Verwenden Sie diese Option, um eine Vorschau einer .dita/.xml-Datei in der Assets-Benutzeroberfläche anzuzeigen. Bei einer .ditamap/.bookmap-Datei werden alle Themendateien innerhalb der Karte in einer einzigen einheitlichen Seitenansicht angezeigt.

- **Generieren**: Generieren Sie die Ausgabe für die ausgewählte Datei auf der Sites-Seite, im Inhaltsfragment oder im Experience Fragment.

>[!NOTE]
>
> Sie können auch die Eigenschaften ausgewählter Themen in einer DITA-Map über das Menü **Weitere Optionen** unter Verweise öffnen und bearbeiten.

### Wiederverwendbarer Inhalt

Eines der Hauptmerkmale von DITA ist die Möglichkeit, Inhalte wiederzuverwenden. Das Bedienfeld **Wiederverwendbarer Inhalt** kann Ihre DITA-Dateien speichern, aus denen Sie in der Regel wiederverwendbare Inhalte einfügen. Nach dem Hinzufügen bleiben die DITA-Dateien sitzungsübergreifend im Bedienfeld „Wiederverwendbarer Inhalt“. Das bedeutet, dass Sie Ihre DITA-Dateien nicht erneut hinzufügen müssen, um später darauf zuzugreifen.

Sie können wiederverwendbare Inhalte einfach per Drag-and-Drop aus dem Bedienfeld auf Ihr aktuelles Thema ziehen und es wird einfach und schnell eingefügt. Sie können auch eine Vorschau des Inhalts erhalten, bevor Sie ihn in Ihr Dokument einfügen.

Standardmäßig können Sie die Dateien nach Titeln anzeigen. Wenn Sie mit dem Mauszeiger auf eine Datei zeigen, können Sie den Dateititel und den Dateipfad als QuickInfo anzeigen.

>[!NOTE]
>
> Als Administrator können Sie die Liste der Dateien nach Dateinamen im Editor anzeigen. Wählen Sie die **Dateiname** im Abschnitt **Konfiguration von Editor-Dateien** Benutzereinstellungen **aus**.

Um eine DITA-Datei zu Ihrem Bedienfeld „Wiederverwendbarer Inhalt“ hinzuzufügen, verwenden Sie eine der folgenden Methoden:

- Wählen Sie das Symbol **+** neben Wiederverwendbarer Inhalt aus, um das Dialogfeld Datei durchsuchen zu öffnen. Wählen Sie die Datei aus, die Sie hinzufügen möchten, und wählen Sie dann **Hinzufügen** aus, um den Vorgang abzuschließen.

- Wählen Sie in der Repository-Ansicht das **Optionen**-Symbol der gewünschten Datei aus und wählen Sie **Hinzufügen zu** > **Wiederverwendbarer Inhalt** aus dem Kontextmenü.

- Klicken Sie im Editor mit der rechten Maustaste auf die Registerkarte einer Datei, um das Kontextmenü zu öffnen, und wählen Sie **Hinzufügen zu** > **Wiederverwendbarer Inhalt**.


Nachdem die Datei hinzugefügt wurde, können Sie alle wiederverwendbaren Inhaltselemente aus der Datei im Bedienfeld Wiederverwendbarer Inhalt anzeigen. Wiederverwendbare Inhalte werden mit ihren IDs und Elementnamen angezeigt.

Wenn Sie eine Datei zur Liste wiederverwendbarer Inhalte hinzufügen, wird der Titel der Datei anstelle der UUID der Datei angezeigt. Um die UUID der Datei zu überprüfen, bewegen Sie den Mauszeiger über den Titel der Datei, und die UUID der Datei wird in der QuickInfo angezeigt.

![](images/uuid-reusable-content-file-title_cs.png){width="400" align="left"}

>[!NOTE]
>
> Sie können der Liste wiederverwendbarer Inhalte mehrere Dateien hinzufügen. Anschließend können Sie den gewünschten Inhalt aus dem Bedienfeld Wiederverwendbarer Inhalt in Ihr Dokument einfügen.

**Aktualisieren**: Überprüft erneut alle wiederverwendbaren Inhalte und zeigt eine neue Liste der wiederverwendbaren Inhalte an.

Verwenden Sie eine der folgenden Methoden, um Inhalte aus dem Bedienfeld „Wiederverwendbarer Inhalt“ einzufügen:

- Bewegen Sie den Mauszeiger über ein Element, das Sie einfügen möchten, wählen Sie das Symbol **Optionen** und wählen Sie **Wiederverwendbaren Inhalt einfügen** aus der Dropdown-Liste aus.

  ![](images/insert-reusable-content_cs.png){width="400" align="left"}

  >[!NOTE]
  >
  > Wählen Sie eine Datei aus und wählen Sie **Vorschau** aus dem Menü **Optionen**, um eine Vorschau der Datei anzuzeigen, ohne sie zu öffnen. Sie können auch eine Vorschau der in einem Thema vorhandenen Verweise anzeigen. Die Referenz-ID wird im Fenster angezeigt.
  >
  > Die **Vorschau**-Option ist auch im Menü **Optionen** eines Elements verfügbar, das Ihnen vor dem Einfügen eine kurze Vorschau des Elements liefert.

- Ziehen Sie das wiederverwendbare Inhaltselement per Drag-and-Drop aus dem Bedienfeld an die gewünschte Position in Ihrem Dokument.

### umreißen

Wenn Sie das Symbol **Gliederung** auswählen, erhalten Sie eine hierarchische Ansicht der im Dokument verwendeten Elemente.

![](images/outline-view_cs.png){width="300" align="left"}

Die Gliederungsansicht bietet die folgenden Funktionen:

- Eine Baumansicht aller im Dokument verwendeten Elemente.

- Wenn ein Element eine ID, ein Attribut und einen Text hat, können Sie diese zusammen mit dem Element anzeigen.

- Greifen Sie in der Autoren- und Source-Ansicht auf die Gliederungsansicht zu.

- Verwenden Sie die Dropdown-Liste Filter , um alle Elemente oder nur die beschädigten Verweise anzuzeigen:

- Wenn Sie ein Element in der Gliederungsansicht auswählen, wird der Inhalt des Elements in der Authoring- oder Source-Ansicht ausgewählt. Die Gliederungsansicht bleibt mit der Autoren- und der Source-Ansicht synchronisiert. Wenn Sie Änderungen in einer Ansicht vornehmen, können Sie diese in der Gliederungsansicht anzeigen. Wenn Sie beispielsweise einen Absatz hinzufügen oder ein Element in der Autorenansicht aktualisieren, wird dies in der Gliederungsansicht angezeigt.

  ![](images/select-element-content-outline-view_cs.png){width="650" align="left"}

- Elemente per Drag-and-Drop verschieben. Sie können ein Element einfach ersetzen, indem Sie ein anderes Element darauf ablegen. Wenn Sie ein Element per Drag-and-Drop auf ein anderes Element ziehen und ein gestricheltes Rechteckfeld um das Element herum anzeigen, bedeutet dies, dass das Element ersetzt wird. Es ersetzt das Element, auf dem das Element abgelegt wird.

  ![](images/replace-element-outline-view_cs.png){align="left"}

  Wenn Sie ein Element per Drag-and-Drop ziehen, zeigt ein gestricheltes Rechteck an, dass das Element an der aktuellen Position platziert werden kann. Wenn Drag-and-Drop ungültig ist, wird eine Fehlermeldung angezeigt, die darauf hinweist, dass der Vorgang nicht zulässig ist.

  ![](images/drop-element-outline-view_cs.png){align="left"}

- Das Menü **Optionen** in der Ansicht *Gliederung* ermöglicht die Durchführung allgemeiner Vorgänge wie Ausschneiden, Kopieren, Löschen, ID generieren, Element vor oder nach dem aktuellen Element einfügen, ein Element umbenennen oder ersetzen, Element einschließen, Element entpacken und ein Ausschnitt aus dem ausgewählten Element erstellen.

>[!NOTE]
>
>Weitere Informationen zum Generieren einer ID, zum Einfügen eines Elements vor oder nach dem aktuellen Element und zum Entpacken eines Elements finden Sie unter [Weitere Funktionen im Editor](web-editor-other-features.md#).

**Konfigurieren von Anzeigen**

Mit der Option **Konfigurieren anzeigen** können Sie Folgendes anzeigen:

- **ID anzeigen**: Zeigt die ID des Elements an.
- **Attribut anzeigen**: Zeigt das Attribut zusammen mit seinem Wert an.
- **Text anzeigen**: Zeigt den Text an. Wenn der Text länger als 20 Zeichen ist, wird ein Auslassungszeichen angezeigt.

Wenn ein Blockelement über einen eigenen Text verfügt, wird er zusammen mit diesem Blockelement angezeigt. Wenn er keinen eigenen Text hat, wird der Text des ersten untergeordneten Elements zusammen mit diesem Blockelement angezeigt.

![](images/outline-view-block-element.png){width="550" align="left"}

Wenn Ihr Administrator ein Profil für Attribute erstellt hat, erhalten Sie diese Attribute zusammen mit den konfigurierten Werten. Sie können auch von Ihrem Administrator konfigurierte Anzeigeattribute auf der Registerkarte **Anzeigeattribute** im Abschnitt **Einstellungen** zuweisen. Die für ein Element definierten Attribute werden im Layout- und Gliederungsansicht angezeigt.


Weitere Informationen finden Sie unter *Attribute anzeigen* im Abschnitt *Einstellungen* im Bereich [Linkes ](#left-panel)).

**Suchfunktion**

Mithilfe der Suchfunktion können Sie nach einem Element anhand seines Namens, seiner ID, seines Textes oder seines Attributwerts suchen.

Bei der Suche wird nicht zwischen Groß- und Kleinschreibung unterschieden und die Zeichenfolge wird genau zurückgegeben. Die Suchergebnisse werden anhand der Position des Elements im Dokument sortiert.

Sie können im Element nach einer Zeichenfolge suchen, wenn diese in der Ansicht **Gliederung** angezeigt wird. Wenn beispielsweise die Zeichenfolge &quot;Adobe&quot; im Elementtext vorhanden und im Bedienfeld Gliederungsansicht angezeigt wird (wie Sie **Text anzeigen** aus dem Dropdown-Menü „Anzeigeoptionen“ ausgewählt haben), wird das enthaltende Element gefiltert. Wenn der Text jedoch nicht im Gliederungsansichtsbereich angezeigt wird (da Sie **Text anzeigen** in der Dropdown-Liste „Ansichtsoptionen“ nicht ausgewählt haben), wird das enthaltende Element nicht gefiltert. Ebenso finden Sie die Zeichenfolge in der ID oder den Attributen, sofern Sie sie ausgewählt haben.

### Glossar

Experience Manager Guides ermöglicht die einfache Erstellung und Verwendung von Glossardokumenten. Sie können Glossarthemendateien erstellen und sie dann in eine gemeinsame Glossarzuordnung einbinden. Sobald diese Zuordnung als Stammzuordnung hinzugefügt wurde, werden die Glossareinträge im Glossar-Bedienfeld angezeigt.

![](images/glossary-panel.png){width="650" align="left"}

Um einen Begriff aus dem Glossar einzufügen, ziehen Sie den Eintrag einfach per Drag-and-Drop aus dem Bedienfeld an die gewünschte Position in Ihrem Thema. Das Menü Optionen eines Glossarbegriffs bietet einen schnellen Überblick **Vorschau** des Eintragsbegriffs, **Pfad kopieren** der Eintragsbegriffdatei oder Auffinden der Eintragsbegriffdatei im Repository.

Führen Sie die folgenden Schritte aus, um nach Textausdrücken zu suchen und sie durch Glossarabkürzungen zu ersetzen:

1. Öffnen Sie das DITA-Thema oder die DITA-Karte, in dem bzw. der Sie den Text oder die Begriffe suchen und konvertieren möchten.
1. Wählen Sie das Glossar-Bedienfeld aus, um die in der Stammzuordnung vorhandenen Glossarbegriffe anzuzeigen. Sie können diese Begriffe per Drag-and-Drop in das geöffnete Thema einfügen.
1. Wählen Sie das **Hotspot**-Tool \( ![](images/hotspot-icon.svg)\) im Glossar-Bedienfeld, um bestimmte Textbegriffe zu suchen und in verknüpfte Glossar-Abkürzungen zu konvertieren. Umgekehrt können Sie damit auch nach Glossarkürzeln suchen und diese in Textbegriffe konvertieren.



Sie können die folgenden Einstellungen des Hotspot-Tools konfigurieren:

![](images/glossary-hotspot-tool.png){width="300" align="left"}


- **Glossarschlüssel**: Wählen Sie die Glossarschlüssel aus der DITA-Karte aus, die Sie für die Suche im ausgewählten Thema verwenden möchten. Die ausgewählten Tasten werden unten angezeigt. Sie können eine ausgewählte Taste entfernen, indem Sie auf das Symbol **Entfernen** klicken.

- **Themen**: Wählen Sie entweder das **Aktuelles Thema**, das im Editor geöffnet ist, alle **Geöffneten Themen** in der aktuellen Karte oder die **Aktuelle Karte**, die im Karten-Editor bearbeitet wird, um die Begriffe zu suchen.
- **Themen nach Status filtern**: Sie können die Suche auf Themen mit dem ausgewählten Dokumentstatus beschränken. Die Themen können den Status Entwurf, Bearbeiten, In-Überprüfung, Genehmigt, Überprüft, Fertig oder einen der von der Organisation konfigurierten Status aufweisen.
- **Aktion**: Sie können entweder die Glossarschlüssel (**für jedes Thema manuell)** &quot;**für alle Themen“**. Wenn Sie **Manuell für jedes Thema** auswählen, werden Sie aufgefordert, dies zu bestätigen, bevor Sie jeden Begriff in jedem Thema konvertieren. Wenn Sie **Automatisch für alle Themen** auswählen, werden alle Begriffe in allen Themen automatisch konvertiert.
- **Konvertieren**: Sie können entweder einen gesuchten **Text in Glossarbegriff** oder **Glossarbegriff in Text konvertieren.**
- **Optionen**: Sie können aus den folgenden Optionen auswählen:
   - **Übereinstimmung unter Berücksichtigung von Groß**- und Kleinschreibung: Sucht nach einem Begriff, um die Übereinstimmung mit derselben Groß-/Kleinschreibung zu finden. „USB“ entspricht beispielsweise nicht „USB“.
   - **Nur die erste Instanz konvertieren**: Wenn mehrere Instanzen des gesuchten Begriffs in einem Thema vorhanden sind, wird nur die erste Instanz konvertiert.
   - **Datei vor Konvertierung sperren**: Die gesuchte Datei wird gesperrt, bevor die Begriffe konvertiert werden.
   - **Neue Version nach Konvertierung erstellen**: Nach Abschluss der Konvertierung von Begriffen wird eine neue Version des Themas erstellt.
- **Weiter** wird angezeigt, wenn Sie die Option **Manuell für jedes Thema** auswählen. Wählen Sie **Weiter**, um die Begriffe für jedes Thema basierend auf den ausgewählten Einstellungen zu konvertieren. Es fordert bei jedem Thema zur Konvertierung der Begriffe auf und wechselt zur nächsten Datei. Sie können einen Begriff konvertieren oder überspringen und zum nächsten Begriff wechseln.

  ![](images/manual-convert-skip.png){width="300" align="left"}

- **Konvertieren** wird angezeigt, wenn Sie die Option **Automatisch für alle Themen** auswählen. Wählen Sie **Konvertieren** aus, um alle im Dokument enthaltenen Begriffe in verknüpfte Glossarabkürzungen zu konvertieren.

Eine Liste der **Themen aktualisiert** mit den konvertierten Begriffen und **Themen mit Fehler** wird angezeigt. Bewegen Sie den Mauszeiger über das Infosymbol neben Themen mit Fehler , um die Details des Fehlers anzuzeigen.

>[!NOTE]
>
> Aktualisieren Sie das Thema, um die konvertierten Begriffe anzuzeigen.

### Bedingungen

Im Bedienfeld Bedingungen werden die von Ihrem Administrator definierten bedingten Attribute im globalen Profil oder im Profil auf Ordnerebene angezeigt. Sie können Bedingungen zu Ihrem Inhalt hinzufügen, indem Sie die gewünschte Bedingung einfach per Drag-and-Drop auf Ihren Inhalt ziehen. Der bedingte Inhalt wird mit der für die Bedingung definierten Farbe hervorgehoben, damit er leicht identifiziert werden kann.

Sie können auch mehrere Bedingungen auf ein Element anwenden, indem Sie mehrere Bedingungen auf ein Element ziehen und dort ablegen. Wenn Sie mehrere Bedingungen auf ein Element anwenden, zeigt das Bedienfeld Eigenschaften die angewendeten Bedingungen getrennt durch ein Komma an.

![](images/multiple-conditions-applied_cs.png){align="left"}

In der Code-Ansicht werden die Bedingungen jedoch durch ein Leerzeichen getrennt. Wenn Sie eine Bedingung in der Code-Ansicht hinzufügen oder bearbeiten, stellen Sie sicher, dass mehrere Bedingungen durch ein Leerzeichen getrennt werden.

>[!IMPORTANT]
>
> Der folgende Screenshot zeigt einen Benutzer mit Administratorrechten. Als Benutzer mit Administratorrechten können Sie Bedingungen hinzufügen, bearbeiten und löschen. Andernfalls haben Sie als normaler Autor nur die Möglichkeit, Bedingungen anzuwenden.

![](images/conditional-content-through-panel_cs.png){align="left"}

Um eine Bedingung hinzuzufügen oder zu definieren, klicken Sie auf das Symbol + neben dem Bedienfeld Bedingungen , um das Dialogfeld Bedingung definieren anzuzeigen:

![](images/conditional-panel-create-cond.png){width="400" align="left"}

Wählen Sie aus der Liste Attribut das bedingte Attribut aus, das Sie definieren möchten, geben Sie einen Wert für die Bedingung ein und geben Sie dann die Bezeichnung an, die im Bedienfeld Bedingungen angezeigt wird. Definieren Sie eine Gruppe für die Bedingung. Sie können einer Gruppe mehrere Bedingungen hinzufügen. Sie können auch eine Farbe für die Bedingung definieren. Diese Farbe wird als Hintergrundfarbe des Inhalts festgelegt, auf den die Bedingung angewendet wird.

Sie können die Bedingungen gruppieren und in verschachtelten Ordnern strukturieren. Mit Gruppen können Sie Bedingungen auf mehreren Ebenen erstellen und sie besser für die Verwendung im Inhalt organisieren.

Beispielsweise können Sie Bedingungsgruppen von Produkten wie *Acrobat* und *AEM Guides* erstellen. Sie können die bedingten Attribute für beide Gruppen auswählen. Unter jeder Gruppe können Sie bestimmte Werte wie *Benutzer*, *Admin*, *Prüfer* und *Autor* haben.

>[!NOTE]
>
> Geben Sie entweder ein, um eine neue Gruppe zu erstellen, oder wählen Sie eine vorhandene Gruppe für ein bestimmtes Attribut aus.

Sie können `/` verwenden und Untergruppen wie `AEM Guides/Cloud Service` definieren.



![Bedingungen in einer verschachtelten Hierarchie organisiert](images/conditions-nested-hierarchy.png){width="300" align="left"}


Um eine Bedingung zu bearbeiten, wählen Sie **Bearbeiten** aus dem Menü „Optionen“. Das Dialogfeld Bedingung bearbeiten wird angezeigt:

![](images/conditional-panel-edit-cond.png){width="400" align="left"}

Geben Sie die Details auf die gleiche Weise an wie bei der Konfiguration bei der Definition einer neuen Bedingung.

### Subjektschema

Subject Scheme maps sind eine spezielle Form von DITA-Karten, mit denen taxonomische Themen und kontrollierte Werte definiert werden können. Je nach Ihren Anforderungen können Sie eine Zuordnung für das Betreffschema erstellen und in Ihrer Stammzuordnungsdatei darauf verweisen. Mit Experience Manager Guides können Sie die Hierarchie der Betreffdefinitionen in Ihrem Betreffschema auf verschachtelter Ebene definieren.

Sie können das Betreffschema einfach in einer Zuordnung des Betreffschemas erstellen und dann verwenden. Nachdem diese Zuordnung als Stammzuordnung hinzugefügt wurde, wird das Betreffschema im Bedienfeld „Betreffschema“ angezeigt. Das Bedienfeld „Betreffschema“ zeigt das verfügbare Betreffschema verschachtelt oder hierarchisch an.

Experience Manager Guides unterstützt auch verschachtelte Zuordnungen von Betreffschemata. Außerdem können unter der Stamm-Zuordnung des Betreffschemas mehrere Betreffschemata definiert sein.

Das folgende Beispiel zeigt die Verwendung des Betreffschemas in Experience Manager Guides.

1. Erstellen Sie eine Datei mit einem Schema in einem Tool Ihrer Wahl. Der folgende XML-Code erstellt ein Betreffschema, das Werte für das `platform`-Attribut bindet.

```XML
<?xml version="1.0" encoding="UTF-8"?>
    <!DOCTYPE subjectScheme PUBLIC "-//OASIS//DTD DITA Subject Scheme Map//EN" "subjectScheme.dtd">
    <subjectScheme id="GUID-4f942f63-9a20-4355-999f-eab7c6273270">
        <title>rw</title>
        <!-- Define new OS values that are merged with those in the unixOS scheme -->
        <subjectdef keys="os">
            <subjectdef keys="linux">    </subjectdef>
            <subjectdef keys="mswin">    </subjectdef>
            <subjectdef keys="zos">    </subjectdef>
        </subjectdef>
        <!-- Define application values -->
        <subjectdef keys="app" navtitle="Applications">
            <subjectdef keys="apacheserv">    </subjectdef>
            <subjectdef keys="mysql">    </subjectdef>
        </subjectdef>
        <!-- Define an enumeration of the platform attribute, equal to       each value in the OS subject. This makes the following values       valid for the platform attribute: linux, mswin, zos -->
        <enumerationdef>
            <attributedef name="platform">    </attributedef>
            <subjectdef keyref="os">    </subjectdef>
        </enumerationdef>
        <!-- Define an enumeration of the otherprops attribute, equal to       each value in the application subjects.       This makes the following values valid for the otherprops attribute:       apacheserv, mysql -->
        <enumerationdef>
            <attributedef name="otherprops">    </attributedef>
            <subjectdef keyref="app">    </subjectdef>
        </enumerationdef>
    </subjectScheme>
```

![](images/subject-scheme-panel-new.png){width="300" align="left"}

1. Speichern Sie die Datei mit der Erweiterung a.ditamap und laden Sie sie in einen beliebigen Ordner in DAM hoch.

   >[!NOTE]
   >
   > Sie können der Schemadatei einen Verweis in der übergeordneten DITA-Zuordnung hinzufügen.

   ![](images/subject-scheme-root-map-new.png){width="550" align="left"}

1. Legen Sie die übergeordnete Zuordnung als Stammzuordnung in „Benutzereinstellungen **fest**. Nachdem diese Zuordnung als Stammzuordnung hinzugefügt wurde, wird das Betreffschema im Bedienfeld „Betreffschema“ angezeigt.

   ![](images/subject-scheme-user-preferences-new.png){width="650" align="left"}


1. Öffnen Sie im Editor die Datei, in der Sie die Definitionen des Betreffschemas verwenden möchten.
1. Wenden Sie das Betreffschema auf Ihre Inhalte an, indem Sie einfach das gewünschte Betreffschema per Drag-and-Drop auf Ihren Inhalt ziehen. Der Inhalt wird dann in der definierten Farbe hervorgehoben.




**Umgang mit hierarchischen Definitionen von Betreffdefinitionen und Auflistungen**

Experience Manager Guides verarbeitet nicht nur die Auflistungen und die Objektdefinitionen in derselben Zuordnung, sondern bietet auch die Funktion zum Definieren von Auflistungen und Objektdefinitionen in zwei separaten Zuordnungen. Sie können eine oder mehrere Betreffdefinitionen in einer Zuordnung und die Auflistungsdefinitionen in einer anderen Zuordnung definieren und dann die Zuordnungsreferenz hinzufügen. Beispielsweise erstellt der folgende XML-Code Betreffdefinitionen und Auflistungsdefinitionen in zwei separaten Zuordnungen.

Die Definitionen des Betreffs sind in `subject_scheme_map_1.ditamap` definiert.


```XML
<?xml version="1.0" encoding="UTF-8"?> 
    <!DOCTYPE subjectScheme PUBLIC "-//OASIS//DTD DITA Subject Scheme Map//EN" "../dtd/libs/fmdita/dita_resources/DITA-1.3/dtd/subjectScheme/dtd/subjectScheme.dtd"> 
    <subjectScheme id="subject-scheme.ditamap_f0bfda58-377b-446f-bf49-e31bc87792b3"> 

    <title>subject_scheme_map_1</title> 
    
    <subjectdef keys="os" navtitle="Operating system">
        <subjectdef keys="linux" navtitle="Linux">
        <subjectdef keys="redhat" navtitle="RedHat Linux">
        </subjectdef>
        <subjectdef keys="suse" navtitle="SuSE Linux">
        </subjectdef>
        </subjectdef>
        <subjectdef keys="windows" navtitle="Windows">
        </subjectdef>
        <subjectdef keys="zos" navtitle="z/OS">
        </subjectdef>
        </subjectdef>
        <subjectdef keys="deliveryTargetValues">
        <subjectdef keys="print">
        </subjectdef>
        <subjectdef keys="online">
        </subjectdef>
    </subjectdef>
    <subjectdef keys="mobile" navtitle="Mobile">
        <subjectdef keys="android" navtitle="Android">
        </subjectdef>
        <subjectdef keys="ios" navtitle="iOS">
    </subjectdef>
    </subjectdef>
    <subjectdef keys="cloud" navtitle="Cloud">
        <subjectdef keys="aws" navtitle="Amazon Web Services">
        </subjectdef>
        <subjectdef keys="azure" navtitle="Microsoft Azure">
        </subjectdef>
        <subjectdef keys="gcp" navtitle="Google Cloud Platform">
        </subjectdef>
    </subjectdef>
    </subjectScheme>
```

Die Definition der Auflistung ist vorhanden in    subject_scheme_map_2.ditamap.

```XML
<?xml version="1.0" encoding="UTF-8"?> 
        <!DOCTYPE subjectScheme PUBLIC "-//OASIS//DTD DITA Subject Scheme Map//EN" "../dtd/libs/fmdita/dita_resources/DITA-1.3/dtd/subjectScheme/dtd/subjectScheme.dtd"> 
        <subjectScheme id="subject-scheme.ditamap_17c433d9-0558-44d4-826e-3a3373a4c5ae"> 
        <title>subject_scheme_map_2</title> 
        <mapref format="ditamap" href="subject_scheme_map_1.ditamap" type="subjectScheme"> 
        </mapref> 
        <enumerationdef>
        <attributedef name="platform">
        </attributedef>
        <subjectdef keyref="mobile">
        </subjectdef>
        <subjectdef keyref="cloud">
        </subjectdef>
        </enumerationdef>
        </subjectScheme>
```

Hier werden die Betreffdefinitionen in `subject_scheme_map_1.ditamap` definiert, während die Auflistung def in `subject_scheme_map_2.ditamap` vorhanden ist. Der Verweis auf `subject_scheme_map_1.ditamap` wird auch in `subject_scheme_map_2.ditamap` hinzugefügt.

>[!NOTE]
>
> Da die `subject_scheme_map_1.ditamap` und `subject_scheme_map_2.ditamap` miteinander referenziert werden, werden die Themenschemata aufgelöst.

Die Verweise auf die Auflistung des Antragstellers werden in der folgenden Prioritätsreihenfolge aufgelöst:

1. Gleiche Zuordnung
1. Referenzierte Zuordnung


Die Verweise werden nicht aufgelöst, wenn die Auflistung nicht in derselben Zuordnung und in der referenzierten Zuordnung gefunden wird.

**Werte auf ein bestimmtes Element beschränken**

Sie können die Bedingungen auch auf einige Elemente innerhalb eines Themas beschränken. Verwenden Sie das Tag `<elementdef>` , um das Element zu definieren, und das Tag `<attributedef>` , um die Bedingung zu definieren, die auf das Element angewendet werden kann.  Wenn Sie das Tag `<elementdef>` nicht hinzufügen, können Sie die Bedingungen auf alle Elemente anwenden.
Verwenden Sie beispielsweise die folgende Auflistung, um das Attribut `@platform` auf das Element `<shortdesc>` zu beschränken.  Die anderen Bedingungen sind für alle Elemente sichtbar.

```XML
<enumerationdef>
    <elementdef name="shortdesc">
    </elementdef>
    <attributedef name="platform">
    </attributedef>
    <subjectdef keyref="deliveryTargetValues">
    </subjectdef>
    <subjectdef keyref="os">
    </subjectdef>
  </enumerationdef>
```


**Attribute** Dropdown

Sie können den Wert des Betreffschemas auch über die Dropdown-Liste **Attribute** im Bedienfeld **Inhaltseigenschaften** in der Ansicht **Autor** ändern.

Führen Sie die folgenden Schritte aus, um den Wert zu ändern:

1. Wählen Sie ein Attribut aus der Dropdown **Liste „Attribut** aus.
1. Wählen Sie **Bearbeiten** aus.
1. Wählen Sie den erforderlichen Wert aus der Dropdown-Liste **Wert** aus.
1. Wählen Sie **Aktualisieren** aus.

Sie können auch Werte für ein Attribut anwenden, indem Sie mehrere Werte aus dem Dropdown-Menü auswählen.

**Source-Ansicht**

Sie können die Werte auch aus der Dropdown-Liste des Attributs in der Source-Ansicht ändern. Die Source-Ansicht verhindert auch, dass Sie einen falschen Wert hinzufügen.

![](images/subject-scheme-code-error.png){width="550" align="left"}

**Anzeigen und Anwenden des Betreffschemas im Bedienfeld „Bedingungen“**

Sie können das Betreffschema auch im Bedienfeld Bedingungen anzeigen und anwenden.

Um das Betreffschema im Bedienfeld Bedingungen anzuzeigen, muss Ihr Systemadministrator die Option **Betreffschema im Bedienfeld Bedingungen anzeigen** auf der Registerkarte Allgemein in den Einstellungen auswählen. Weitere Informationen finden Sie im Abschnitt **Einstellungen** in der [Registerkartenleiste](#tab-bar).

Im Bedienfeld Bedingungen wird die flache vertikale Struktur der Objektdefinitionen innerhalb des Themenschemas angezeigt.

Sie können Bedingungen zu Ihrem Inhalt hinzufügen, indem Sie die gewünschte Bedingung auf Ihren Inhalt ziehen und dort ablegen. Der bedingte Inhalt wird mit der für die Bedingung definierten Farbe hervorgehoben.

### Snippets

Snippets sind kleine Inhaltsfragmente, die in verschiedenen Themen in Ihrem Dokumentationsprojekt wiederverwendet werden können. Das Bedienfeld „Ausschnitte“ zeigt eine Sammlung von Inhaltsausschnitten an, die Sie erstellt haben. Um einen Ausschnitt einzufügen, ziehen Sie den Ausschnitt aus dem Bedienfeld an die gewünschte Position im Thema. Im Snippets-Bedienfeld können Sie Snippets hinzufügen, bearbeiten, löschen, in der Vorschau anzeigen und einfügen.

>[!IMPORTANT]
>
> Der folgende Screenshot zeigt einen Benutzer mit Administratorrechten. Als Benutzer mit Administratorrechten können Sie Snippets hinzufügen, bearbeiten und löschen. Andernfalls haben Sie als normaler Autor nur die Möglichkeit, ein Snippet in der Vorschau anzuzeigen und einzufügen.

![](images/snippets-panel_cs.png){align="left"}

Um einen Ausschnitt hinzuzufügen, verwenden Sie eine der folgenden Methoden:

- Wählen Sie das Symbol **+** neben Ausschnitte aus, um das Dialogfeld **Neues**&quot; zu öffnen.

  ![](images/snippet-new-dialog.png){width="300" align="left"}

  Geben Sie im Dialogfeld Neues Snippet einen Titel, der im Snippets-Bereich angezeigt wird, eine Beschreibung und einen XML-Code für den Snippet-Inhalt an, den Sie erstellen möchten. Wählen Sie **Erstellen** aus, um das Snippet zu speichern und zu erstellen.

- Klicken Sie im Inhaltsbearbeitungsbereich mit der rechten Maustaste auf den Breadcrumb des Elements, das Sie als Snippet verwenden möchten, und wählen Sie **Snippet erstellen** aus dem Kontextmenü. Das Dialogfeld Neues Snippet wird angezeigt, wobei der XML-Code des ausgewählten Elements im Feld **Inhalt** ausgefüllt wird. Geben Sie **Titel** und **Beschreibung** für den Ausschnitt ein und wählen Sie **Erstellen** aus, um den Ausschnitt zu speichern.

- Klicken Sie im Inhaltsbearbeitungsbereich mit der rechten Maustaste an eine beliebige Stelle auf den Inhalt, den Sie als Snippet verwenden möchten, und wählen Sie **Snippet erstellen** aus dem Kontextmenü. Das Dialogfeld Neues Snippet wird angezeigt, wobei der XML-Code des ausgewählten Elements im Feld **Inhalt** ausgefüllt wird. Geben Sie **Titel** und **Beschreibung** für den Ausschnitt ein und wählen Sie **Erstellen** aus, um den Ausschnitt zu speichern.

  Im folgenden Screenshot werden der Breadcrumb und der Inhaltsbereich hervorgehoben, von dem aus Sie das Kontextmenü aufrufen können.

  ![](images/snippet-create-from-breadcrumb-content.png){width="350" align="left"}


Verwenden Sie eine der folgenden Methoden, um einen Ausschnitt einzufügen:

- Wählen Sie einen Ausschnitt aus dem Snippets -Bedienfeld aus und ziehen Sie ihn per Drag-and-Drop an die gewünschte Position im Thema.

- Platzieren Sie die Einfügemarke an der Stelle, an der Sie den Ausschnitt einfügen möchten, und wählen Sie im Menü Optionen des gewünschten Ausschnitts die Option Ausschnitt einfügen aus.


>[!NOTE]
>
> Im Kontextmenü eines Snippet-Eintrags können Sie auch „Bearbeiten“, „Löschen“, „Vorschau“ oder „Snippet einfügen“ auswählen.

### Vorlagen

Das Bedienfeld Vorlagen ist nur für Administratoren verfügbar. Mithilfe dieses Bedienfelds können Admins mühelos Vorlagen erstellen und verwalten, die dann von den Autoren verwendet werden können. Standardmäßig werden die Vorlagen unter den Vorlagen vom Typ *Zuordnung* und *Thema* kategorisiert.

![](images/templates-panel_cs.png){width="300" align="left"}

Standardmäßig können Sie die Dateien nach Titeln anzeigen. Wenn Sie mit dem Mauszeiger auf eine Vorlage zeigen, können Sie den Dateititel und den Dateinamen als QuickInfo anzeigen.

>[!NOTE]
>
> Als Administrator können Sie auch die Liste der Dateien im Editor anzeigen. Wählen Sie die **Dateiname** im Abschnitt **Konfiguration von Editor-Dateien** Benutzereinstellungen **aus**.

Informationen zum Erstellen benutzerdefinierter Vorlagen finden Sie unter [Erstellen von Karten basierend auf benutzerdefinierten Vorlagen](./create-maps-customized-templates.md).

### Zitate

In Experience Manager Guides können Sie Zitate hinzufügen, importieren und sie auf Ihre Inhalte anwenden. Sie können diese Zitate aus jeder Quelle von Büchern, Websites und Zeitschriften hinzufügen.

Weitere Informationen finden Sie unter [Hinzufügen und Verwalten von Zitaten in Ihren Inhalten](./web-editor-apply-citations.md).

### Sprachvariablen

Experience Manager Guides bietet die Funktion zur Verwendung von Sprachvariablen in der nativen PDF-Ausgabe. Sie können Sprachvariablen verwenden, um lokalisierte Zeichenfolgen in der PDF-Ausgabe zu definieren oder statischen Text in den Ausgabevorlagen zu lokalisieren. Sie können CSS-Stile verwenden, um die Zeichenfolgen aus einer CSS-Datei zu lokalisieren.

Weitere Informationen finden Sie unter [Unterstützung für Sprachvariablen](../native-pdf/native-pdf-language-variables.md).

### Variablen

Mit Experience Manager Guides können Sie Variablen für die native Veröffentlichung von PDF erstellen und verwalten. Weitere Informationen finden Sie unter [Variablen in der PDF-](../native-pdf/native-pdf-variables.md).


### Suchen und Ersetzen

Das Symbol „Suchen und Ersetzen“ befindet sich unten im linken Bereich. Im Bedienfeld „Suchen und Ersetzen“ können Sie über Dateien in einer Zuordnung oder einem Ordner innerhalb Ihres Repositorys hinweg nach Text suchen und diesen ersetzen. Sie finden und ersetzen in allen Themen einer Karte sowie Themen, die in den Unter-Karten innerhalb der Karte vorhanden sind.

![](images/map-find-replace.png){align="left"}

Standardmäßig können Sie die Dateien nach Titeln anzeigen. Wenn Sie mit dem Mauszeiger auf eine Datei zeigen, können Sie den Dateititel und den Dateipfad als QuickInfo anzeigen.

>[!NOTE]
>
> Als Administrator können Sie auch die Liste der Dateinamen im Editor anzeigen. Wählen Sie die **Dateiname** im Abschnitt **Konfiguration von Editor-Dateien** Benutzereinstellungen **aus**.

Um die globale Suche und Ersetzung durchzuführen, führen Sie die folgenden Schritte aus:

1. Öffnen Sie das globale Bedienfeld **Suchen und Ersetzen**.
1. Wählen Sie das **Suchen in** und wählen Sie eine der folgenden Optionen aus, um die Suche durchzuführen.

   - **Aktuelle Karte**: Zum Suchen in der aktuell geöffneten Karte

     >[!NOTE]
     >
     > Diese Option wird angezeigt, wenn Sie bereits eine Karte zur Bearbeitung geöffnet haben.

   - **Path**: Zum Suchen nach dem ausgewählten Pfad
   - **Karte auswählen**: Zum Suchen in der ausgewählten Karte

1. Sie können das Dropdown-**„Optionen** verwenden und aus den folgenden Optionen auswählen:

   - **Datei vor Ersetzen sperren**: Wählen Sie diese Option, wenn Sie eine Datei vor dem Ersetzen des Suchbegriffs automatisch sperren möchten. Diese Einstellung ist relevanter, falls Ihr Administrator die Konfiguration so aktiviert hat, dass sie eine Datei vor der Bearbeitung sperrt. Wenn die Backend-Einstellung aktiviert ist, sollten Sie diese Option auswählen. Dadurch wird verhindert, dass das Dialogfeld Dateisperre Sie auffordert, jede Datei zu sperren, bevor Sie Änderungen vornehmen. Wenn Sie diese Option nicht auswählen, wird eine Eingabeaufforderung angezeigt, bevor eine Datei zur Bearbeitung geöffnet wird.
   - **Nur ganze Wörter**: Wählen Sie diese Option aus, wenn Sie nach der gesamten Suchzeichenfolge suchen möchten. Wenn Sie beispielsweise über in der Suchzeichenfolge eingeben, gibt das Suchergebnis alle Dateien zurück, die Wörter wie über und Überblick enthalten. Wählen Sie diese Option aus, wenn Sie die Suche auf den eingegebenen Begriff beschränken möchten.
   - **Neue Version nach Ersetzen erstellen**: Wählen Sie diese Option aus, wenn Sie eine neue Version des Themas erstellen möchten, in dem Sie den Text ersetzen möchten. Sie können auch Versionskommentare angeben, die mit jeder aktualisierten Datei hinzugefügt werden.

     Wenn Sie diese Option nicht auswählen, werden die Änderungen in der aktuellen Version des Themas gespeichert und es wird keine neue Version erstellt.

   - **Indirekte Verweise einschließen**: Wählen Sie diese Option aus, wenn Sie die Zeichenfolge in den indirekten Verweisen auch innerhalb der DITA-Zuordnung suchen möchten. Standardmäßig ist dies deaktiviert, sodass die Suche nur für die direkten Verweise durchgeführt wird.

1. Geben Sie den Suchbegriff oder Text ein, den Sie suchen möchten.
1. Geben Sie den Text ein, durch den Sie den Suchbegriff ersetzen möchten.
1. Drücken Sie die Eingabetaste oder wählen Sie **Suchen** Symbol \( ![](images/search-icon.svg)\) aus, um die Suche durchzuführen.
1. Wählen Sie eine Datei aus der Suchergebnisliste aus. Die Datei wird im Inhaltsbearbeitungsbereich geöffnet, wobei der gesuchte Begriff im Inhalt hervorgehoben wird.

1. Wählen Sie **Einzelnes Vorkommen ersetzen** \( ![](images/replace-icon.svg)\) aus, um den aktuell hervorgehobenen Suchbegriff im Thema zu ersetzen, oder wählen Sie Nächste Übereinstimmung ![](images/next-match-in-search.png) oder ![](images/previous-match-in-search.png) vorherige Übereinstimmung aus, um zum nächsten oder vorherigen Vorkommen des Textes zu wechseln.
1. Wählen Sie **Alle ersetzen** \( ![](images/replace-all-in-file-icon.svg)\), um alle Vorkommen des gesuchten Begriffs in einer Datei mit einem einzigen Klick durch den Ersetzungsbegriff zu ersetzen. Nachdem Sie alle Vorkommen in der ausgewählten Datei ersetzt haben, wird eine Benachrichtigung angezeigt.

Um das Symbol **Alle ersetzen** zu aktivieren, muss Ihr Systemadministrator die Option **Alle ersetzen aktivieren** auf der Registerkarte **Allgemein** in **Einstellungen** auswählen.

>[!NOTE]
>
> Bewegen Sie den Mauszeiger über eine Datei in der Suchergebnisliste, um das Symbol Alle ersetzen in der Datei auf der rechten Seite anzuzeigen. Sie erhalten auch das Symbol Datei ignorieren , um die Datei aus dem Suchergebnis zu entfernen. Die Dateien, die Sie ignorieren, werden aus der Liste entfernt und der gesuchte Begriff wird in ihnen nicht ersetzt.

Im gesamten System kann jeweils nur ein Vorgang zum Ersetzen aller Vorgänge ausgeführt werden. Bis zum Ausführen des Vorgangs wird der Status „Alle laufenden Vorgänge ersetzen“ angezeigt. Sie können auch den Vorgang „Alle ersetzen“ dazwischen abbrechen oder den Protokollbericht anzeigen. Wenn Sie den Vorgang abbrechen, erhalten Sie eine Benachrichtigung darüber in Ihrem Posteingang. Nachdem Sie alle Vorkommen in der ausgewählten Datei ersetzt haben, wird eine Erfolgsbenachrichtigung angezeigt.

![](images/replace-all-in-progress.png){width="300" align="left"}

Sie können auch die Option **In Karte suchen** im Menü **Optionen** einer Karte verwenden, um Text in einer Karte zu suchen und zu ersetzen. Diese Option wird für eine Zuordnung angezeigt, die im Repository-Bereich oder in der Zuordnungsansicht geöffnet ist.

![](images/map-options-menu.png){width="550" align="left"}

### PDF-Vorlagen

Ermöglicht die Arbeit mit verschiedenen PDF-Vorlagen. Weitere Informationen finden Sie unter [PDF-Vorlagen](../native-pdf/pdf-template.md).

### Überprüfung

Experience Manager Guides bietet die Funktion zum Anzeigen aller Prüfungsaufgaben in Ihren Projekten. Sie können alle Überprüfungsprojekte und die aktiven Überprüfungsaufgaben innerhalb der Überprüfungsprojekte, zu denen Sie gehören, im Bedienfeld **Überprüfen** anzeigen.  Anschließend können Sie die Prüfungsaufgaben öffnen, um die Kommentare der verschiedenen Validierungsverantwortlichen anzuzeigen.

Im Überprüfungsfenster werden die Überprüfungsaufgaben angezeigt. Standardmäßig können Sie die Dateien nach Titeln anzeigen. Wenn Sie mit dem Mauszeiger auf eine Datei zeigen, können Sie den Dateititel und den Dateipfad als QuickInfo anzeigen.

>[!NOTE]
>
> Als Administrator können Sie die Liste der Dateien nach Dateinamen im Editor anzeigen. Wählen Sie die **Dateiname** im Abschnitt **Konfiguration von Editor-Dateien** Benutzereinstellungen **aus**.

Als Autor können Sie die Kommentare in einem Thema mit dem Editor bearbeiten.

Führen Sie die folgenden Schritte aus, um die Prüfungskommentare in den aktiven Prüfungsaufgaben anzuzeigen, die in Ihren Projekten vorhanden sind:

1. Wählen Sie im linken Bedienfeld Überprüfen aus. Das Bedienfeld **Überprüfen** wird geöffnet.  Alle Überprüfungsprojekte und die aktiven Überprüfungsaufgaben innerhalb der Überprüfungsprojekte, zu denen Sie gehören, werden angezeigt.

   ![](images/web-editor-review-panel.png){width="300" align="left"}
1. Wählen Sie ein Überprüfungsprojekt aus und wählen Sie dann eine Überprüfungsaufgabe aus der Liste aus, um sie zu öffnen.
1. Sie können Ihre Projekte auch wie folgt filtern:

   - Geben Sie den Suchbegriff oder Text ein, den Sie im Titel des Projekts finden möchten. Drücken Sie dann die Eingabetaste, um die Suche durchzuführen. Sie können beispielsweise alle Projekte mit dem Begriff „Leerzeichen“ im Titel durchsuchen.

   - Wählen Sie ![](images/filter-search-icon.svg) aus, um das Dialogfeld **Filter** zu öffnen. Sie können alle oder nur bestimmte Projekte auswählen. Die ausgewählten Projekte werden im Bedienfeld **Überprüfen** aufgelistet.

     ![](images/active-review-select-project.png){width="300" align="left"}

     Aktivieren Sie **Option „Von mir initiierte Aufgaben**, um nur die von Ihnen initiierten Aufgaben anzuzeigen. Der Umschaltstatus dieser Option wird auch nach dem Aktualisieren der Seite beibehalten. Aktivieren Sie die Option **Nur aktive Aufgaben anzeigen**, um die Projektliste so zu filtern, dass die derzeit aktiven Aufgaben angezeigt werden.

1. Standardmäßig werden Sie in Ihrem Überprüfungsprojekt eine flache Liste von Themen anzeigen, denen Kommentare zugeordnet sind. Wenden Sie die erforderlichen Filter in der linken Leiste an, um die Themen basierend auf den darin enthaltenen Überprüfungskommentaren zu filtern:

   - **Alle Themen anzeigen**: Listet alle in den Projekten vorhandenen Themen auf.
   - **Themen mit Kommentaren anzeigen**: Listet nur die Themen auf, die Prüfungskommentare enthalten.
1. Sie können auch den Suchbegriff oder Text eingeben, den Sie im Titel oder Dateipfad des Themas finden möchten. Die Themen, die den Begriff im Titel oder im Dateipfad enthalten, werden aufgelistet.
1. Doppelklicken Sie auf ein Thema, um es in der Autorenansicht zu öffnen. Sie können die Kommentare im Bedienfeld **Kommentare** anzeigen.

   ![](images/active-review-task-comments.png){align="left"}

   >[!NOTE]
   > 
   > Das Bedienfeld **Überprüfen** und das Bedienfeld **Kommentare** sind immer synchron. Im Bedienfeld Kommentare werden die Kommentare basierend auf der im Bedienfeld Überprüfung geladenen Prüfungsaufgabe geladen.
   >Sie können die geschlossenen Prüfungsaufgaben in der linken Leiste des Prüfungsbereichs zusammen mit den aktiven Prüfungsaufgaben anzeigen.
   >Darüber hinaus können Sie für eine geschlossene Überprüfungsaufgabe die Überprüfungskommentare im Kommentarbereich auf der rechten Seite anzeigen, aber die Schaltflächen **Kommentare importieren** und **Version zurücksetzen** sind deaktiviert.
   >Weitere Informationen zum Umgang mit den Kommentaren finden Sie unter [Kommentare zur Adressenüberprüfung](review-address-review-comments.md#).


## Inhaltsbearbeitungsbereich

Im Inhaltsbearbeitungsbereich wird der Inhalt des Themas oder der Karte angezeigt. Sie nehmen alle Inhaltsbearbeitungen in diesem Bereich vor. Es bietet eine WYSIWYG-Ansicht des Inhalts, den Sie bearbeiten.

Unten links im Inhaltsbearbeitungsbereich befindet sich der Breadcrumb des Elements an der aktuellen Cursorposition. In der rechten unteren Ecke werden die verfügbaren Editor-Ansichten angezeigt.

![](images/content-editing-area.png){align="left"}

Weitere Informationen zu den Editor-Ansichten, die für eine Themendatei im Inhaltsbearbeitungsbereich verfügbar sind, finden Sie unter Ansicht [Editor-Ansichten](./web-editor-views.md).

>[!NOTE]
>
> Wenn Sie an einer Zuordnungsdatei arbeiten, werden im Inhaltsbearbeitungsbereich verschiedene Optionen oder Ansichten angezeigt, einschließlich einer **Layout**-Ansicht für die Zuordnungsdatei. Weitere Informationen finden Sie unter [Funktionen des Zuordnungs-Editors](./map-editor-advanced-map-editor.md).

## Rechtes Bedienfeld

Das rechte Bedienfeld enthält Informationen zum aktuell ausgewählten Dokument.

>[!NOTE]
>
> Die Größe des rechten Bedienfelds kann geändert werden. Um die Größe des Bereichs zu ändern, bringen Sie den Cursor auf die Bereichsbegrenzung, der Cursor ändert sich in einen Doppelpfeil, wählen Sie und ziehen Sie, um die Größe des Bereichs zu ändern.

Das rechte Bedienfeld bietet Zugriff auf die folgenden Funktionen:

- [Inhaltseigenschaften](#content-properties)
- [Dateieigenschaften](#file-properties)
- [Überprüfung](#review-1)
- [Änderungen verfolgen](#track-changes)
- [Ingenieur](#schematron)

### Inhaltseigenschaften

Sie können auf die Funktion **Inhaltseigenschaften** zugreifen, indem Sie im rechten Bedienfeld auf **Inhaltseigenschaften** klicken. Das Bedienfeld **Inhaltseigenschaften** enthält Informationen zum Typ des aktuell im Dokument ausgewählten Elements und zu dessen Attributen.

**Typ**: Sie können die Tags der vollständigen Hierarchie für das aktuelle Tag aus der Dropdown-Liste anzeigen und auswählen.

**Attribute**: Das **Attribute** Dropdown-Menü ist in den Ansichten „Layout“, „Autor“ und &quot;Source&quot; verfügbar. Sie können die Attribute einfach hinzufügen, bearbeiten oder löschen.

1. Wählen Sie **Hinzufügen** aus.

   ![Attribute in den Inhaltseigenschaften](images/properties-tab-attributes_cs.png){width="300" align="left"}

1. Wählen **im Dropdown** Bedienfeld „Attribut“ das Attribut aus der Dropdown-Liste aus und geben Sie den Wert eines Attributs an.  Wählen Sie dann **Hinzufügen** aus.

   ![Attributbedienfeld mit mehreren Attributen ](images/attributes-multiple-properties.png){width="300" align="left"}

1. Um das Attribut zu bearbeiten, halten Sie den Mauszeiger darüber und wählen Sie **Bearbeiten** ![edit-icon](images/edit_pencil_icon.svg) aus.

1. Um das Attribut zu löschen, halten Sie den Mauszeiger darüber und wählen Sie **Löschen** ![delete-icon](images/Delete_icon.svg).


>[!NOTE]
>
> Selbst wenn das Thema referenzierten Inhalt enthält, können Sie ihm mithilfe des Bedienfelds „Eigenschaften“ Attribute hinzufügen.

Wenn Ihr Administrator ein Profil für Attribute erstellt hat, erhalten Sie diese Attribute zusammen mit den konfigurierten Werten. Im Bedienfeld Inhaltseigenschaften können Sie diese Attribute auswählen und sie relevanten Inhalten in Ihrem Thema zuweisen. Auf diese Weise können Sie auch bedingte Inhalte erstellen, die dann zur Erstellung einer bedingten Ausgabe verwendet werden können. Weitere Informationen zum Generieren der Ausgabe mithilfe von bedingten Vorgaben finden Sie unter [Verwenden von Bedingungsvorgaben](generate-output-use-condition-presets.md#).

### Dateieigenschaften

Zeigen Sie die Eigenschaften der ausgewählten Datei an, indem Sie im rechten Bereich auf das Symbol Dateieigenschaften klicken. Die Funktion Dateieigenschaften ist in allen vier Modi oder Ansichten verfügbar: Layout, Autor, Source und Vorschau.

Die Dateieigenschaften weisen die folgenden beiden Abschnitte auf:

**Allgemein**

Im Abschnitt Allgemein haben Sie Zugriff auf die folgenden Funktionen:

![file-properties](images/file-properties-general.png){width="300" align="left"}

- **Dateiname**: Zeigt den Dateinamen des ausgewählten Themas an. Der Dateiname ist mit der Eigenschaftenseite der ausgewählten Datei per Hyperlink verknüpft.
- **ID**: Zeigt die ID des ausgewählten Themas an.
- **Tags**: Dies sind die Metadaten-Tags des Themas. Sie werden über das Feld Tags auf der Seite Eigenschaften festgelegt. Sie können sie in der Dropdown-Liste eingeben oder auswählen.  Die Tags werden unter dem Dropdown-Menü angezeigt. Um ein Tag zu löschen, klicken Sie auf das Kreuzsymbol neben dem Tag.
- **Weitere Eigenschaften bearbeiten**: Sie können auf der Seite mit den Dateieigenschaften weitere Eigenschaften bearbeiten.
- **Language**: Zeigt die Sprache des Themas an. Sie wird im Feld Sprache auf der Seite Eigenschaften festgelegt.
- **Erstellt am**: Zeigt Datum und Uhrzeit an, zu der das Thema erstellt wurde.
- **Geändert am**: Zeigt das Datum und die Uhrzeit an, zu der das Thema geändert wurde.
- **Gesperrt von**: Zeigt den Benutzer an, der das Thema gesperrt hat.
- **Dokumentstatus**: Sie können den Dokumentstatus des aktuell geöffneten Themas auswählen und aktualisieren. Weitere Informationen finden Sie unter [Dokumentstatus](web-editor-document-states.md#).

>[!NOTE]
>
> Sie können die Attributwerte der verschiedenen Felder in den Dateieigenschaften in die Zwischenablage kopieren.

**Verweise**

Der Abschnitt Verweise bietet Ihnen Zugriff auf die folgenden Funktionen:

![](images/file-properties-references.png){width="300" align="left"}

- **Verwendet in**: Die Option Verwendet in Verweisen listet die Dokumente auf, auf die die aktuelle Datei verwiesen oder verwendet wird.
- **Ausgehende Links:** Die ausgehenden Links listen die Dokumente auf, auf die im aktuellen Dokument verwiesen wird.

Standardmäßig können Sie die Dateien nach Titeln anzeigen. Wenn Sie mit dem Mauszeiger auf eine Datei zeigen, können Sie den Dateititel und den Dateipfad als QuickInfo anzeigen.

>[!NOTE]
>
> Als Administrator können Sie die Liste der Dateien nach Dateinamen im Editor anzeigen. Wählen Sie die **Dateiname** im Abschnitt **Konfiguration von Editor-Dateien** Benutzereinstellungen **aus**.

>[!NOTE]
>
> Alle in und ausgehenden Referenzen werden durch Hyperlinks mit den Dokumenten verbunden. Sie können die verknüpften Dokumente einfach öffnen und bearbeiten.

Neben dem Öffnen von Dateien können Sie auch viele Aktionen über das Menü **Optionen** im Abschnitt Verweise durchführen. Einige der Aktionen, die Sie ausführen können, sind Bearbeiten, Vorschau, UUID kopieren, Pfad kopieren, Zu Sammlungen hinzufügen, Eigenschaften.

### Überprüfung

Wenn Sie auf das Symbol Überprüfen klicken, wird das Review-Bedienfeld geöffnet, in dem Sie eine Prüfungsaufgabe für das aktuell geöffnete Dokument auswählen und Kommentare anzeigen können.

![](images/review-panel-before-opening.png){width="300" align="left"}

Wenn Sie mehrere Überprüfungsprojekte erstellt haben, können Sie eines aus der Dropdown-Liste auswählen und auf die Überprüfungskommentare zugreifen.

Im Überprüfungsbereich können Sie Antworten zu den Kommentaren zum Thema anzeigen und posten. Sie können die Kommentare einzeln akzeptieren oder ablehnen.

>[!NOTE]
>
> Das Kommentarfeld und das Antwortfeld unterstützen mehrzeilige Einträge und ermöglichen es Benutzern, es nach Bedarf zu erweitern, um umfassende Kommentare sowie detaillierte Antworten auf die Kommentare bereitzustellen. Sie können **Umschalt** + **Eingabetaste** verwenden, um in die nächste Zeile zu wechseln, während Sie die Kommentare oder Antworten schreiben.

Weitere Informationen finden Sie unter [Kommentare zur Adressüberprüfung](review-address-review-comments.md#).

### Änderungen verfolgen

Mit der Funktion „Nachverfolgte Änderungen“ im rechten Bereich können Sie die Informationen zu allen Aktualisierungen in einem Dokument anzeigen. Sie können auch nach bestimmten Aktualisierungen des Dokuments suchen.

>[!NOTE]
>
> Die Funktion „Nachverfolgte Änderungen“ zeigt alle Aktualisierungen an, die mit der Funktion „Änderungen nachverfolgen“ in der [-Leiste aktiviert/deaktiviert ](#tab-bar).

### Ingenieur

„Schematron“ bezieht sich auf eine regelbasierte Validierungssprache, die zum Definieren von Tests für eine XML-Datei verwendet wird. Der Editor unterstützt Schematron-Dateien. Sie können die Schematron-Dateien importieren und auch im Editor bearbeiten. Mithilfe einer Schematron-Datei können Sie bestimmte Regeln definieren und diese dann für ein DITA-Thema oder eine Zuordnung validieren.

Informationen zum Arbeiten mit Schematrondateien in Experience Manager Guides finden Sie unter [Unterstützung für Schematrondateien](./support-schematron-file.md).



**Übergeordnetes Thema**: [Einführung in den Editor](web-editor.md)
