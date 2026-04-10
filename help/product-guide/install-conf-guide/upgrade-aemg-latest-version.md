---
title: Adobe Experience Manager Guides aktualisieren
description: Erfahren Sie, wie Sie Adobe Experience Manager Guides aktualisieren
feature: Installation
role: Admin
level: Experienced
source-git-commit: 453da51a42984b912547570f2e1de70806b41171
workflow-type: tm+mt
source-wordcount: '1661'
ht-degree: 0%

---

# Aktualisieren von Adobe Experience Manager Guides für Version 4.6.0 und höher

Dieser Artikel enthält Anweisungen zum Aktualisieren Ihrer Experience Manager Guides-Versionen auf 4.6.0 und höher.

>[!NOTE]
>
> Befolgen Sie die Upgrade-Anweisungen, die für die lizenzierte Version Ihres Produkts gelten.

Sie können Ihre aktuelle Version von Experience Manager Guides auf Version 5.1.0 Service Pack 3 aktualisieren:

- Wenn Sie Version 5.1.0 oder 5.1.x verwenden, können Sie direkt auf Version 5.1.0 Service Pack 3 aktualisieren.
- Wenn Sie Version 4.6.0, 4.6.x, 5.0.0 oder 5.0.x verwenden, müssen Sie auf Version 5.1.0 aktualisieren.
- Wenn Sie eine Version vor 4.6.0 verwenden, finden Sie unter [Upgrade von Adobe Experience Manager Guides für Version 4.4.0 und früher](./upgrade-aemg-prev-versions.md) detaillierte Upgrade-Anweisungen.

>[!NOTE]
>
> Sie müssen das AEM Service Pack installieren, bevor Sie die Experience Manager Guides-Version aktualisieren.

Weitere Informationen finden Sie in den folgenden Verfahren:

- [Aktualisierung auf Version 5.1.0](#upgrade-to-version-510)
- [Aktualisieren auf Version 5.0.0](#upgrade-to-version-500)
- [Aktualisieren auf Version 4.6.0](#upgrade-to-version-460)

>[!IMPORTANT]
>
> Bevor Sie mit dem Upgrade beginnen, sollten Sie ein vollständiges System-Backup erstellen, um Datenverluste zu vermeiden.


## Aktualisierung auf Version 5.1.0


>[!IMPORTANT]
>
> Wenn Sie derzeit AEM 6.5 verwenden und planen, auf AEM 6.5 LTS zu wechseln, stellen Sie sicher, dass Sie zuerst das AEM-Upgrade abschließen, bevor Sie mit dem Experience Manager Guides 5.1.0-Upgrade fortfahren. Weitere Informationen finden Sie unter [Upgrade auf Adobe Experience Manager (AEM) 6.5 LTS](https://experienceleague.adobe.com/en/docs/experience-manager-65-lts/content/implementing/deploying/upgrading/upgrade).

**Voraussetzungen**

>[!NOTE]
>
>Wenn Sie ein Upgrade auf 5.1.0 Service Pack 3 durchführen, müssen Sie Version 5.1.0 oder 5.1.x von Experience Manager Guides verwenden. Der Upgrade-Prozess für Version 5.1.0 Service Pack 3 erfolgt in denselben Schritten wie für Version 5.1.0.

Stellen Sie vor dem Start des Upgrades auf Experience Manager Guides 5.1.0 Folgendes sicher:

1. Auf Experience Manager Guides Version 4.6.3, 4.6.4, 5.0.0 oder 5.0.0 Service Pack 1 aktualisiert.
1. (Optional) Alle Übersetzungsaufgaben wurden geschlossen.
1. Protokollebene für **Klasse in &quot;**&quot; `com.adobe.fmdita.translationservices.TranslationMapUpgradeScript` und diese Protokolle in einer neuen Protokolldatei anhängen, z. B. `logs/translation_upgrade.log`.

>[!NOTE]
>
> Die Nachbearbeitung und Indizierung kann einige Stunden dauern. Es wird empfohlen, den Upgrade-Prozess außerhalb der Spitzenzeiten zu starten.

**Installieren Sie Version 5.1.0**

Laden Sie das Versionspaket 5.1.0 vom [Adobe Software Distribution Portal](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html) herunter und befolgen Sie die Anweisungen unter [Workflow für Installation und ](#installation-and-post-installation-upgrade-workflow) nach der Installation), um den Upgrade-Vorgang abzuschließen.


## Aktualisieren auf Version 5.0.0

>[!TIP]
>
> Die Aktualisierung auf Version 5.0.0 Service Pack 3 hängt von der aktuellen Version von Experience Manager Guides ab. Wenn Sie Version 5.0.0 Service Pack 2, 5.0.0 Service Pack 1 oder 5.0.0 verwenden, können Sie direkt auf Version 5.0.0 Service Pack 3 aktualisieren. Die Upgrade-Schritte entsprechen denen für Version 5.0.0.

>[!NOTE]
>
> Die Nachbearbeitung und Indizierung kann einige Stunden dauern. Es wird empfohlen, den Upgrade-Prozess außerhalb der Spitzenzeiten zu starten.

**Voraussetzungen**

Stellen Sie vor dem Start des Upgrades auf Experience Manager Guides 5.0.0 Folgendes sicher:

1. Auf Experience Manager Guides Version 4.6.3, 4.6.1, 4.6.0 oder 4.4 aktualisiert.
1. (Optional) Alle Übersetzungsaufgaben wurden geschlossen.
1. Protokollebene für **Klasse in &quot;**&quot; `com.adobe.fmdita.translationservices.TranslationMapUpgradeScript` und diese Protokolle in einer neuen Protokolldatei anhängen, z. B. `logs/translation_upgrade.log`.


**Installieren Sie Version 5.0.0**

Laden Sie das Versionspaket 5.0.0 vom [Adobe Software Distribution Portal](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html) herunter und befolgen Sie die Anweisungen unter [Workflow für Installation und ](#installation-and-post-installation-upgrade-workflow) nach der Installation), um den Upgrade-Vorgang abzuschließen.

## Aktualisieren auf Version 4.6.0

>[!TIP]
>
> Es wird empfohlen, 4.6.0 Service Pack 4 auf Version 4.6.0 , 4.6.0 Service Pack 1 oder 4.6.0 Service Pack 3 zu installieren. Der Upgrade-Prozess für Version 4.6.0 Service Pack 4 folgt denselben Schritten wie für Version 4.6.0.

Die Aktualisierung auf Version 4.6.0 hängt von der aktuellen Version von Experience Manager Guides ab. Wenn Sie Version 4.4.0, 4.3.1, 4.3.0, 4.2 oder 4.2.1 (Hotfix 4.2.1.3) verwenden, können Sie direkt auf Version 4.6.0 aktualisieren.

>[!NOTE]
>
> Die Nachbearbeitung und Indizierung kann einige Stunden dauern. Es wird empfohlen, den Upgrade-Prozess außerhalb der Spitzenzeiten zu starten.

**Voraussetzungen**

Stellen Sie vor dem Start des Upgrades auf Experience Manager Guides 4.6.0 Folgendes sicher:

1. Auf Experience Manager Guides Version 4.3.1, 4.3.0 oder 4.2.1 (Hotfix 4.2.1.3) aktualisiert.
1. (Optional) Alle Übersetzungsaufgaben wurden geschlossen.
1. Protokollebene für **Klasse in &quot;**&quot; `com.adobe.fmdita.translationservices.TranslationMapUpgradeScript` und diese Protokolle in einer neuen Protokolldatei anhängen, z. B. `logs/translation_upgrade.log`.

**Installieren Sie Version 4.6.0**

Laden Sie das Versionspaket 4.6.0 vom [Adobe Software Distribution Portal](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html) herunter und befolgen Sie die Anweisungen unter [Workflow für Installation und ](#installation-and-post-installation-upgrade-workflow) nach der Installation), um den Upgrade-Vorgang abzuschließen.

## Workflow für Installation und Upgrade nach der Installation

### Installieren des Versionspakets

Führen Sie die folgenden Schritte aus, um das Versionspaket zu installieren:

1. Installieren Sie das Versionspaket, auf dem Sie das Upgrade durchführen möchten.
1. Sie können den Trigger auswählen, um den Upgrade-Auftrag für die Übersetzungskarte zu starten. Weitere Informationen finden Sie unter [Aktivieren des Skript-Triggers über ein Servlet](#enable-trigger-of-script-via-a-servlet).

1. Warten Sie nach Abschluss der Paketinstallation in den Protokollen auf die folgende Meldung:

   `Completed the post deployment setup script`

   Die obige Meldung weist darauf hin, dass alle Installationsschritte abgeschlossen sind.

   Wenn Sie auf einen der folgenden Fehler stoßen, melden Sie diese Ihrem Customer Success-Team:

   - Fehler im Setup-Skript nach der Bereitstellung
   - Ausnahme bei der Portierung des Übersetzungs-MAP
   - Die Übersetzungszuordnung kann für die Eigenschaft nicht von v1 auf v2 portiert werden
1. (Optional) Upgrade des Oxygen Connector-Plug-ins, das mit der Version veröffentlicht wurde, auf die Sie ein Upgrade durchführen.
1. Löschen Sie den Browser-Cache nach der Installation des Pakets.

### Nach der Installation

Nach der Installation von Experience Manager Guides können Sie die verschiedenen Konfigurationen, die für die neu installierte Version gelten, mit Ihrem Setup zusammenführen.

>[!NOTE]
>
> Das Modell dam-update-asset kann angepasst werden. Wenn also Anpassungen vorgenommen wurden, müssen wir die Anpassungen und Experience Manager Guides mit der Arbeitskopie des Modells synchronisieren.

**Workflow „DAM-Update-Asset“ \(Änderungen nach der Verarbeitung\):**

1. URL öffnen:

   ```
   http://localhost:4502/libs/cq/workflow/admin/console/content/models.html 
   ```

1. Wählen Sie **Workflow DAM-Update-Asset**.
1. Wählen Sie **Bearbeiten** aus.
1. Wenn die **DXML Post Process Initiator**-Komponente vorhanden ist, stellen Sie sicher, dass die Anpassungen synchronisiert werden.
1. Wenn die **DXML Post Process Initiator**-Komponente fehlt, führen Sie die folgenden Schritte aus, um sie einzufügen:

   - Wählen Sie **Komponente einfügen** \(Verantwortlich für die Experience Manager Guides-Nachbearbeitung als letzten Schritt im Prozess\) aus.
   - Konfigurieren Sie den **Prozessschritt** mit den folgenden Details:

     **Registerkarte „Allgemein“:**

      - **title:** DXML-Nachbearbeitungs-Initiator

      - **Beschreibung**: Schritt „DXML-Nachbearbeitungs-Initiator“, der einen Sling-Auftrag für die DXML-Nachbearbeitung des geänderten/erstellten Assets Trigger

     **Registerkarte „Prozess“**

      - Wählen Sie **DXML Post Process Initiator** aus der **Prozess** Dropdown aus
      - Wählen Sie **Handler-Fortschritt** aus
      - Wählen Sie **Fertig**

1. Wählen **oben rechts** Synchronisieren“ aus, nachdem Sie die Änderungen abgeschlossen haben. Sie erhalten eine Erfolgsbenachrichtigung.

   >[!NOTE]
   >
   > Aktualisieren Sie und überprüfen Sie, ob benutzerdefinierte Änderungen und der Experience Manager Guides-Nachbearbeitungsschritt im endgültigen Workflow-Modell vorhanden sind.

1. Nachdem **Workflow DAM-Update-Asset** validiert wurde, überprüfen Sie die entsprechenden Starter-Konfigurationen. Gehen Sie dazu zur Workflow-Benutzeroberfläche von AEM und öffnen Sie Starter.

   ```http
   http://localhost:4502/libs/cq/workflow/content/console.html
   ```

   Suchen Sie die beiden folgenden Starter \(die aktiv sein sollten\) und nehmen Sie entsprechende Änderungen vor \(falls erforderlich\), die dem Workflow **DAM-Update-Asset entsprechen**:

1. Starter für &quot;*Knoten erstellt*&quot; für **Workflow DAM-Update-Asset**- für `"jcr:content/jcr:mimeType!=video"` sollte der Wert „Globbing“ sein:

   ```json
   /content/dam(/((?!/subassets|/translation_output).)*/)renditions/original
   ```

   - „excludeList“ muss `"event-user-data:changedByWorkflowProcess"` haben.
   - Starter für &quot;*Node Modified*&quot; für **DAM Update Asset Workflow -** Für Bedingung &quot;`jcr:content/jcr:mimeType!=video`&quot; sollte der Wert „Globbing“ sein:

   ```json
   /content/dam(/((?!/subassets|/translation_output).)*/)renditions/original
   ```

   - `excludeList` sollte `"event-user-data:changedByWorkflowProcess"` haben.

1. Nachdem das Upgrade abgeschlossen ist, stellen Sie sicher, dass alle Anpassungen/Überlagerungen validiert und aktualisiert werden, damit sie dem neuen Anwendungs-Code entsprechen. Im Folgenden finden Sie einige Beispiele:
   - Alle Komponenten, die von überlagert sind, `/libs/fmditaor/libsshould` mit dem neuen Produkt-Code verglichen werden. Aktualisierungen sollten in überlagerten Dateien unter /apps vorgenommen werden.
   - Alle vom Produkt verwendeten `clientlib` sollten auf Änderungen überprüft werden. Alle überschriebenen Konfigurationen `\(examples below\)` sollten mit den neuesten verglichen werden, um die neuesten Funktionen zu erhalten:
   - elementmapping.xml
   - `ui\_config.json\(may have been set in folder profiles\)`
   - geänderte `com.adobe.fmdita.config.ConfigManager`

1. Wenn Sie Anpassungen in damAssetLucene hinzugefügt haben, müssen Sie diese möglicherweise erneut anwenden. Nachdem Sie diese Änderungen vorgenommen haben, setzen Sie die Neuindizierung auf „true“. Dadurch werden alle vorhandenen Knoten mit den Anpassungen neu indiziert. Nach Abschluss wird das Neuindizierungs-Flag erneut auf „false“ gesetzt. Dies kann je nach Anzahl der Assets im System einige Stunden dauern.

### Neuindizierung der Experience Manager Guides-Indizes

1. Öffnen Sie `crx/de` und navigieren Sie zum Indexpfad: `/oak:index/guidesAssetProperties`
2. Legen Sie die Eigenschaft für die Neuindizierung auf `true` fest (standardmäßig `false`) und klicken Sie auf **Alle speichern**.
3. Sobald die Neuindizierung abgeschlossen ist, wird die Eigenschaft für die Neuindizierung erneut auf `false` festgelegt und die Neuindizierungsanzahl um 1 erhöht.

   >[!NOTE]
   >
   > Dies kann je nach Menge der vorhandenen Daten einige Minuten dauern.
4. Führen Sie dieselben Schritte für andere hinzugefügte oder geänderte Indizes aus: `guidesBulkActivation`, `guidesPeerLinkIndex` und `guidesKonnectTemplateIndex`.

### Schritte zum Indizieren des vorhandenen Inhalts

Führen Sie die folgenden Schritte aus, um den vorhandenen Inhalt zu indizieren:

- Führen Sie eine POST-Anfrage an den Server \(mit korrekter Authentifizierung\) - `http://<server:port\>/bin/guides/map-find/indexing` aus. (Optional: Sie können bestimmte Pfade der Zuordnungen übergeben, um sie zu indizieren. Standardmäßig werden alle Zuordnungen indiziert. | Beispiel: `https://<Server:port\>/bin/guides/map-find/indexing?paths=<map\_path\_in\_repository\>`)

- Die API gibt ein -`jobId` zurück. Um den Auftragsstatus zu überprüfen, können Sie eine GET-Anfrage mit Auftrags-ID an denselben Endpunkt senden - `http://<server:port\>/bin/guides/map-find/indexing?jobId=\{jobId\}`\(zum Beispiel: ` http://localhost:8080/bin/guides/map-find/indexing?jobId=2022/9/15/7/27/7dfa1271-981e-4617-b5a4-c18379f11c42_678`)

- Sobald der Vorgang abgeschlossen ist, wird die obige GET-Anfrage erfolgreich beantwortet und es wird angegeben, ob Zuordnungen fehlgeschlagen sind. Die erfolgreich indizierten Zuordnungen können aus den Serverprotokollen bestätigt werden.


>[!NOTE]
>
> Wenn Sie das benutzerdefinierte Schema verwenden, müssen Sie den Pfad der benutzerdefinierten DTD- und XSD-Datei catalog.xml-Dateien im AEM-Repository in der Option **Integrationskataloge** definieren.

### Schritte zum Umgang mit dem `'fmdita rewriter'`

Experience Manager Guides verfügt über [**Modul „Benutzerdefiniertes Sling Rewriter**](../install-conf-guide/conf-output-generation.md#custom-rewriter), in dem die Links verarbeitet werden, die bei Kreuzzuordnungen (Verknüpfungen zwischen den Themen zweier verschiedener Zuordnungen) generiert werden.

Wenn Sie einen anderen benutzerdefinierten Sling Rewriter in Ihrer Codebasis haben, verwenden Sie einen `'order'` Wert größer als 50, da der Experience Manager Guides Sling Rewriter `'order'` 50 verwendet.  Um dies zu überschreiben, benötigen Sie einen Wert >50. Weitere Informationen finden Sie unter [Output-Umschreibungs-Pipelines](https://sling.apache.org/documentation/bundles/output-rewriting-pipelines-org-apache-sling-rewriter.html).

Da während dieses Upgrades der `'order'` von 1000 auf 50 geändert wird, müssen Sie den vorhandenen benutzerdefinierten Rewriter (sofern vorhanden) mit `'fmdita-rewriter'` zusammenführen.


### Schritte zur Neuindizierung von damAssetLucene

Die Indexdefinition wird für damAssetLucene mit AEM Guides aktualisiert. Informationen zur Neuindizierung von damAssetLucene finden Sie nach [ Upgrade auf ](https://experienceleague.adobe.com/en/docs/experience-cloud-kcs/kbarticles/ka-16460) erforderliche Version in diesem Artikel.

>[!NOTE]
>
> Stellen Sie beim Befolgen der Dokumentation sicher, dass beide Eigenschaften (`reindex=true` und `reindex-async=true` für `/oak:index/damAssetLucene`) gleichzeitig über den Vorgang Speichern aktualisiert werden.

