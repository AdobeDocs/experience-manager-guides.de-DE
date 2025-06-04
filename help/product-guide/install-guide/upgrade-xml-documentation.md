---
title: Adobe Experience Manager Guides aktualisieren
description: Erfahren Sie, wie Sie Adobe Experience Manager Guides aktualisieren
exl-id: f058b39f-7408-4874-942b-693e133886cf
feature: Installation
role: Admin
level: Experienced
source-git-commit: 579be351210f8a32d9cb66950b935bfad039f51b
workflow-type: tm+mt
source-wordcount: '8041'
ht-degree: 0%

---

# Adobe Experience Manager Guides aktualisieren {#id224MBE0M0XA}

>[!NOTE]
>
> Befolgen Sie die Upgrade-Anweisungen, die für die lizenzierte Version Ihres Produkts gelten.

Sie können Ihre aktuelle Version von Experience Manager Guides auf Version 5.0.0 Service Pack 1 aktualisieren:


- Wenn Sie Version 5.0.0, 4.6.x, 4.6 oder 4.4 verwenden, können Sie direkt auf Version 5.0.0 Service Pack 1 aktualisieren.
- Wenn Sie Version 4.3.x, 4.2, 4.2.1 (Hotfix 4.2.1.3), 4.1 oder 4.1.x verwenden, müssen Sie vor dem Upgrade auf Version 5.0.0 ein Upgrade auf Version 4.4 durchführen.
- Wenn Sie Version 4.0 verwenden, müssen Sie auf Version 4.2 aktualisieren, bevor Sie auf Version 4.3.x aktualisieren.
- Wenn Sie Version 3.8.5 verwenden, müssen Sie auf Version 4.0 aktualisieren, bevor Sie auf Version 4.2 aktualisieren.
- Wenn Sie eine Version vor 3.8.5 verwenden, lesen Sie den Abschnitt zum Upgrade von Experience Manager Guides im produktspezifischen Installationshandbuch, das auf der [Adobe Experience Manager Guides-Hilfe für PDF Archive](https://helpx.adobe.com/xml-documentation-for-experience-manager/archive.html) verfügbar ist.


>[!NOTE]
>
> Sie müssen das AEM Service Pack installieren, bevor Sie die Experience Manager Guides-Version aktualisieren.

Weitere Informationen finden Sie in den folgenden Verfahren:

- [Upgrade von 3.8.5 auf Version 4.0](#upgrade-from-version-385-to-version-40)
- [Aktualisierung auf Version 4.2](#upgrade-to-version-42)
- [Aktualisierung auf Version 4.2.1](#upgrade-to-version-421)
- [Aktualisierung auf Version 4.3.0](#upgrade-to-version-430)
- [Aktualisierung auf Version 4.3.1](#upgrade-to-version-431)
- [Aktualisieren auf Version 4.3.1.5](#upgrade-to-version-4315)
- [Aktualisierung auf Version 4.4.0](#upgrade-to-version-440)
- [Aktualisieren auf Version 4.6.0](#upgrade-to-version-460)
- [Aktualisieren auf Version 5.0.0](#upgrade-to-version-500)



>[!IMPORTANT]
>
> Bevor Sie mit dem Upgrade beginnen, sollten Sie ein vollständiges System-Backup erstellen, um Datenverluste zu vermeiden.

## Upgrade von Version 3.8.5 auf Version 4.0

Wenn Sie Experience Manager Guides Version 3.8.5 verwenden, können Sie auf Version 4.0 von Experience Manager Guides aktualisieren. Mit der Upgrade-Funktion müssen Sie die vorherige Version von Experience Manager Guides nicht deinstallieren.

Vor Ausführung des Prozesses gibt es bestimmte Aufgaben, die Sie abschließen müssen. Die folgenden Unterabschnitte führen Sie durch die Voraussetzungen, die Berichterstellung und den Migrationsprozess. Nach der Installation von Experience Manager Guides Version 4.0 können Sie außerdem verschiedene Konfigurationen entsprechend den Kundeneinstellungen anpassen.

>[!NOTE]
>
> Dieser Upgrade-Prozess gilt nur für die Versionen 3.8.5 bis 4.0. Informationen zum Upgrade von Version 3.4 oder höher auf 3.8.5 finden Sie im Abschnitt *Upgrade von Experience Manager Guides* im produktspezifischen Installationshandbuch, das auf der [Adobe Experience Manager Guides-Hilfe für PDF Archive](https://helpx.adobe.com/xml-documentation-for-experience-manager/archive.html) verfügbar ist.



****Voraussetzungen****

Bevor Sie mit dem Experience Manager Guides-Upgrade-Prozess beginnen, stellen Sie sicher, dass die folgenden Punkte erfüllt sind:

1. Die Überprüfungskommentare in Themen importiert, die zur Überprüfung geöffnet sind.
1. Alle aktiven Rezensionen wurden geschlossen.
1. Alle Übersetzungsaufgaben geschlossen.
1. Deinstallieren Sie alle Experience Manager Guides-Hotfixes, die oben auf der vorherigen Version \(Haupt- oder Patch-Version\) von Experience Manager Guides installiert sind.

**Vor der Installation von Version 4.0**

Führen Sie vor der Installation von Version 4.0 die folgenden Schritte aus:

1. Stellen Sie sicher, dass Experience Manager Guides derzeit Version 3.8.5 verwendet.
1. Laden Sie das Paket mit dem Upgrade-Skript herunter. Suchen Sie dazu im [ Adobe Software Distribution-Portal nach &quot;XML Documentation-Lösungs-4.0-Upgrade](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html)Paket“, wodurch eine ZIP-Datei heruntergeladen wird.
1. Laden Sie dieses Paket über Package Manager in AEM hoch und installieren Sie es.
1. Sobald das Upgrade-Paket installiert ist, führen Sie die folgenden Skripte in der gleichen Reihenfolge aus und befolgen Sie die angegebenen Anweisungen:

**Upgrade-Kompatibilitäts-API überprüfen**

Diese API dient dazu, den aktuellen Systemstatus zu bewerten und Berichte zu erstellen, ob das Upgrade möglich ist oder nicht. Um dieses Skript auszuführen, geben Sie den folgenden Trigger für den Endpunkt ein:

| Endpunkt | /bin/dxml/upgrade/3xto4x/report |
| --- | --- |
| Abfragetyp | **GET** Sie können einen Webbrowser verwenden, in dem Sie bei der AEM-Instanz als Admin angemeldet sind. |
| Erwartete Antwort | -   Wenn alle erforderlichen Knoten verschoben werden können, erhalten Sie eine bestandene Prüfung. <br>-   Wenn am Zielspeicherort ein Knoten vorhanden ist, wird ein relevanter Fehler angezeigt. Bereinigen Sie das Repository \(löschen Sie den Knoten /var/dxml\) und installieren Sie das Aktualisierungspaket erneut. Führen Sie dann erneut einen Trigger mit diesem Endpunkt durch. <br>**Hinweis:** Dies ist kein häufiger Fehler, da der Zielspeicherort von 3.x Experience Manager Guides nicht zuvor verwendet wird. <br> -   Wenn dieses Skript nicht erfolgreich ist, fahren Sie nicht fort und melden Sie es Ihrem Customer Success-Team. |

**Systemdatenmigrations-API**

Diese API dient zur Migration der Systemdaten, wie im Abschnitt **Migrationszuordnung** beschrieben.

1. Führen Sie dieses Skript nicht aus, wenn die API zur Überprüfung der Upgrade-Kompatibilität fehlschlägt \(fahren Sie nicht fort\).
1. Sobald die API zur Überprüfung der Aktualisierungskompatibilität erfolgreich war, können Sie das Aktualisierungsskript ausführen.

| Endpunkt | /bin/dxml/upgrade/3xto4x |
| --- | --- |
| Abfragetyp | **POST** Dieses Skript ist eine POST-Anfrage und sollte daher über Agenten wie Postman ausgeführt werden. |
| Erwartete Antwort | -   Nach erfolgreicher Migration können Sie die XML Documentation-Lösung Version 4.0.<br>-   Wenn Fehler auftreten, stellen Sie den letzten Checkpoint wieder her und geben Sie die Fehlerprotokolle zusammen mit der API-Ausgabe an Ihr Customer Success-Team weiter. |

**Migrationszuordnung**: Die obige API migriert alle Daten unter dem Quellspeicherort zum Zielspeicherort.

| Quelle | Ziel |
|------|------|
| /content/fmdita | /var/dxml |
| /content/dxml | /var/dxml |
| /etc/fmdita | /libs/fmdita |

## Installieren von Version 4.0 {#id23598G006XA}

1. Installieren Sie Version 4.0 nur, wenn die Upgrade-Schritte erfolgreich waren.
1. Laden Sie das Versionspaket 4.0 vom [Adobe Software Distribution-Portal herunter](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html):

   - Wenn Sie die UUID-Version der -Software verwenden, suchen Sie nach „4.0 UUID Release for XML Documentation Solution for AEM 6.5“.
   - Wenn Sie eine Nicht-UUID-Version von Software verwenden, suchen Sie nach „4.0 Non-UUID Release for XML Documentation Solution for AEM 6.5“.
Laden Sie das Paket mit CRX Package Manager in die bestehende(n) AEM-Server-Instanz(en) hoch und installieren Sie es.

   >[!NOTE]
   >
   > Warten Sie, bis alle Systemkomponenten gestartet wurden.

1. Löschen Sie den Browser-Cache nach der Installation des Pakets.
1. Wenn ein Dispatcher in der AEM-Autoreninstanz konfiguriert ist, führen Sie die folgenden Schritte aus:
   - Stellen Sie sicher, dass in Dispatcher-Regeln Folgendes verarbeitet wird:
   - Das URL-Muster /home/users/\*/preferences wird auf die Whitelist gesetzt.
   - Das URL-Muster /libs/cq/security/userinfo.json wird nicht zwischengespeichert.
1. Dispatcher-Cache löschen \(um alle zwischengespeicherten `clientlibs` zu löschen\).

## Aktualisierung auf Version 4.2

Die Aktualisierung auf Version 4.2 hängt von der aktuellen Version von Experience Manager Guides ab.

Wenn Sie Version 4.0, 4.1 oder 4.1.x verwenden, können Sie direkt auf Version 4.2 aktualisieren.

****Voraussetzungen****

Bevor Sie mit dem Upgrade auf Experience Manager Guides 4.2 beginnen, stellen Sie Folgendes sicher:

1. Auf Experience Manager Guides Version 4.0, 4.1 oder 4.1.x aktualisiert.
1. Alle Übersetzungsaufgaben geschlossen.
1. Protokollebene für `com.adobe.fmdita.translationservices.TranslationMapUpgradeScript` Klasse in &quot;**&quot;** und diese Protokolle in einer neuen Protokolldatei anhängen, z. B. `logs/translation_upgrade.log.`

>[!NOTE]
>
> Sie sollten alle aktiven Rezensionen schließen. Wenn die Prüfungsaufgaben beim Upgrade auf 4.2 nicht geschlossen werden, nehmen die älteren Prüfungsaufgaben weiterhin Benutzer auf die älteren Prüfungsseiten auf, und die Prüfungsaufgaben, die nach dem Upgrade erstellt wurden, zeigen die neuesten Aktualisierungen in der Funktion an.

## Installieren von Version 4.2 {#id2245IK0E0EV}

1. Laden Sie das Versionspaket 4.2 vom [Adobe Software Distribution Portal](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html) herunter.
1. Installieren Sie das Paket Version 4.2 .
1. Warten Sie nach Abschluss der Paketinstallation in den Protokollen auf die folgende(n) Meldung(en):

   `Completed the post deployment setup script`

   Die obige Meldung weist darauf hin, dass alle Installationsschritte abgeschlossen sind.

   Falls Sie auf eines der folgenden FEHLER-Präfixe stoßen, melden Sie dies Ihrem Customer Success-Team:

   - Fehler im Setup-Skript nach der Bereitstellung
   - Ausnahme bei der Portierung des Übersetzungs-MAP
   - Die Übersetzungszuordnung kann für die Eigenschaft nicht von v1 auf v2 portiert werden
1. Upgrade des Oxygen Connector-Plug-ins, das mit Version 4.2 veröffentlicht wurde \(falls erforderlich\).
1. Löschen Sie den Browser-Cache nach der Installation des Pakets.
1. Fahren Sie mit dem Upgrade der Anpassungen fort, wie im nächsten Abschnitt beschrieben.

## Nach der Installation von Version 4.2 {#id2326F02004K}

>[!IMPORTANT]
>
> Die High-Tech-Vorlage wird auf dem aktualisierten Server nicht angezeigt. Um die High-Tech-Vorlage auf Ihrem Server einzubinden, können Sie sie kopieren: Source: /libs/fmdita/pdf/Hi-Tech-Ziel: /content/dam/dita-templates/pdf

Nach der Installation von Experience Manager Guides können Sie die verschiedenen Konfigurationen, die für die neu installierte Version gelten, mit Ihrem Setup zusammenführen.

>[!NOTE]
>
> Das Modell dam-update-asset kann angepasst werden. Wenn also Anpassungen vorgenommen wurden, müssen wir die Anpassungen und Experience Manager Guides mit der Arbeitskopie des Modells synchronisieren.

1. **Workflow „DAM-Update-Asset“ \(Änderungen nach der Verarbeitung\):**

1. URL öffnen:

   ```http
   http://localhost:4502/libs/cq/workflow/admin/console/content/models.html
   ```

1. Wählen Sie **Workflow DAM-Update-Asset**.
1. Klicken Sie auf **Bearbeiten**.
1. Wenn die **DXML Post Process Initiator**-Komponente vorhanden ist, stellen Sie sicher, dass die Anpassungen synchronisiert werden.
1. Wenn die **DXML Post Process Initiator**-Komponente fehlt, führen Sie die folgenden Schritte aus, um sie einzufügen:

1. Klicken Sie **Komponente einfügen** \(Verantwortlich für die Nachbearbeitung von Experience Manager Guides als letzter Schritt im Prozess\).
1. Konfigurieren Sie den **Prozessschritt** mit den folgenden Details:

   **Registerkarte „Allgemein“**

   **title:** DXML-Nachbearbeitungs-Initiator

   **Beschreibung**: Schritt „DXML-Nachbearbeitungs-Initiator“, der einen Sling-Auftrag für die DXML-Nachbearbeitung des geänderten/erstellten Assets Trigger

   **Registerkarte „Prozess“**

   - Wählen Sie **DXML Post Process Initiator** aus der Dropdown **Prozess** aus

   - Wählen Sie **Handler-Fortschritt** aus

   - Wählen Sie **Fertig**

1. Klicken Sie **rechts oben** den Änderungen auf „Synchronisieren“. Sie erhalten eine Erfolgsbenachrichtigung.

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
   - Starter für &quot;*Node Modified*&quot; für **DAM Update Asset Workflow -** für Bedingung &quot;`jcr:content/jcr:mimeType!=video`&quot;,
   - Der Wert für „Globbing“ sollte sein:

   ```json
   /content/dam(/((?!/subassets|/translation_output).)*/)renditions/original
   ```

   - „excludeList“ muss `"event-user-data:changedByWorkflowProcess"` haben.
1. Nachdem das Upgrade abgeschlossen ist, stellen Sie sicher, dass alle Anpassungen/Überlagerungen validiert und aktualisiert werden, damit sie dem neuen Anwendungs-Code entsprechen. Im Folgenden finden Sie einige Beispiele:
   - Alle Komponenten, die von /libs/fmdidator/libs überlagert sind, sollten mit dem neuen Produkt-Code verglichen werden und Aktualisierungen sollten in überlagerten Dateien unter /apps vorgenommen werden.
   - Alle Client-Bibliothekskategorien, die vom Produkt verwendet werden, sollten auf Änderungen überprüft werden. Alle überschriebenen Konfigurationen \(Beispiele unten\) sollten mit den neuesten verglichen werden, um die neuesten Funktionen zu erhalten:
   - elementmapping.xml
   - ui\_config.json\(wurde möglicherweise in Ordnerprofilen festgelegt\)
   - geänderte `com.adobe.fmdita.config.ConfigManager`
   - Überprüfen Sie, ob einer der benutzerdefinierten Codes alte Pfade verwendet hat \(wie im Abschnitt [Migrationszuordnung](#id2244LE040XA)\) - sollte auf die neuen Pfade aktualisiert werden, damit die Anpassungen ebenfalls erwartungsgemäß funktionieren.
1. Lesen Sie alle neuen Konfigurationen, die in der aktuellen Version bereitgestellt werden \(überprüfen Sie [Versionshinweise](../release-info/release-notes-4-3.md)\), und überprüfen Sie, ob Funktionen betroffen sind. Ein Beispiel könnte die Verwendung von „Verbessertes Datei- und Versionsmanagement“ sein, die in Version 4.0 eingeführt wurde und für die Sie eine Konfiguration aktivieren müssen.

## Schritte zum Indizieren des vorhandenen Inhalts für die Verwendung des neuen Such- und Ersetzungsmodus:

Führen Sie die folgenden Schritte aus, um den vorhandenen Inhalt zu indizieren und den neuen Text „Suchen und Ersetzen“ auf Zuordnungsebene zu verwenden:

- Führen Sie eine POST-Anfrage an den Server \(mit korrekter Authentifizierung\) - `http://<server:port\>/bin/guides/map-find/indexing` aus. \(Optional: Sie können bestimmte Pfade der Zuordnungen übergeben, um sie zu indizieren. Standardmäßig werden alle Zuordnungen indiziert. \|\| Beispiel: `https://<Server:port\>/bin/guides/map-find/indexing?paths=<map\_path\_in\_repository\>`\)

- Die API gibt eine jobId zurück. Um den Auftragsstatus zu überprüfen, können Sie eine GET-Anfrage mit Auftrags-ID an denselben Endpunkt senden -

`http://<server:port\>/bin/guides/map-find/indexing?jobId=\{jobId\}`\(Beispiel: `http://localhost:8080/bin/guides/map-find/indexing?jobId=2022/9/15/7/27/7dfa1271-981e-4617-b5a4-c18379f11c42`\)

- Sobald der Vorgang abgeschlossen ist, wird die obige GET-Anfrage erfolgreich beantwortet und es wird angegeben, ob Zuordnungen fehlgeschlagen sind. Die erfolgreich indizierten Zuordnungen können aus den Serverprotokollen bestätigt werden.

Wenn der Upgrade-Auftrag fehlschlägt und das Fehlerprotokoll den folgenden Fehler anzeigt:

„Die *Abfrage* mehr als *100000 Knoten gelesen oder durchlaufen*. Um andere Aufgaben nicht zu beeinträchtigen, wurde die Verarbeitung angehalten.“

Dies kann vorkommen, da der Index für die beim Upgrade verwendete Abfrage nicht ordnungsgemäß eingerichtet ist. Sie können die folgende Problemumgehung ausprobieren:

1. Fügen Sie im damAssetLucene-Oak-Index die boolesche Eigenschaft `indexNodeName` wie im Knoten `true` hinzu.
   `/oak:index/damAssetLucene/indexRules/dam:Asset`
1. Fügen Sie einen neuen Knoten mit dem Namen „excerpt“ unter dem Knoten hinzu.

   `/oak:index/damAssetLucene/indexRules/dam:Asset/properties`
und legen Sie die folgenden Eigenschaften im Knoten fest:

   ```
   name - rep:excerpt
   propertyIndex - {Boolean}true
   notNullCheckEnabled - {Boolean}true
   ```

   Die Struktur von `damAssetLucene` sollte in etwa so aussehen:

   ```
   <damAssetLucene compatVersion="{Long}2" async="async, nrt" jcr:primaryType="oak:QueryIndexDefinition" evaluatePathRestrictions="{Boolean}true" type="lucene">
   <indexRules jcr:primaryType="nt:unstructured">
     <dam:Asset indexNodeName="{Boolean}true" jcr:primaryType="nt:unstructured">
       <properties jcr:primaryType="nt:unstructured">
         <excerpt name="rep:excerpt" propertyIndex="{Boolean}true" jcr:primaryType="nt:unstructured" notNullCheckEnabled="{Boolean}true"/>
       </properties>
       </dam:Asset>
     </indexRules>
   </damAssetLucene>    
   ```


   (zusammen mit anderen vorhandenen Knoten und Eigenschaften)

1. Indizieren Sie den `damAssetLucene` neu (indem Sie das Flag für die Neuindizierung auf `true` unter festlegen).
und warten Sie, bis sie erneut `false` wird (dies bedeutet, dass die Neuindizierung abgeschlossen ist). Beachten Sie, dass es je nach Größe des Index einige Stunden dauern kann.
1. Führen Sie das Indizierungsskript erneut aus, indem Sie die vorherigen Schritte ausführen.


## Aktualisierung auf Version 4.2.1

>[!TIP]
>
>Es wird empfohlen, Hotfix 4.2.1.3 über Version 4.2.1 zu installieren.

Die Aktualisierung auf Version 4.2.1 hängt von der aktuellen Version von Experience Manager Guides ab. Wenn Sie Version 4.1, 4.1.x oder 4.2 verwenden, können Sie direkt auf Version 4.2.1 aktualisieren.

>[!NOTE]
>
>Die Nachbearbeitung und Indizierung kann einige Stunden dauern. Es wird empfohlen, den Upgrade-Prozess außerhalb der Spitzenzeiten zu starten.

****Voraussetzungen****

Stellen Sie vor dem Start des Upgrades auf Experience Manager Guides 4.2.1 Folgendes sicher:

1. Auf Experience Manager Guides Version 4.1, 4.1.x oder 4.2 aktualisiert.
1. Alle Übersetzungsaufgaben geschlossen.
1. Protokollebene für `com.adobe.fmdita.translationservices.TranslationMapUpgradeScript` Klasse in &quot;**&quot;** und diese Protokolle in einer neuen Protokolldatei anhängen, z. B. `logs/translation_upgrade.log.`

>[!NOTE]
>
> Sie sollten alle aktiven Rezensionen schließen. Wenn die Prüfungsaufgaben beim Upgrade auf 4.2 nicht geschlossen werden, nehmen die älteren Prüfungsaufgaben weiterhin Benutzer auf die älteren Prüfungsseiten auf, und die Prüfungsaufgaben, die nach dem Upgrade erstellt wurden, zeigen die neuesten Aktualisierungen in der Funktion an.

## Installieren von Version 4.2.1

1. Laden Sie das Versionspaket 4.2.1 vom [Adobe Software Distribution Portal](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html) herunter.
1. Installieren Sie das Paket Version 4.2.1 .
1. Sie können den Trigger drücken, um den Upgrade-Auftrag für die Übersetzungskarte zu starten. Weitere Informationen finden Sie unter [Aktivieren des Skript-Triggers über ein Servlet](#enable-trigger-of-script-via-a-servlet-for-421).


1. Warten Sie nach Abschluss der Paketinstallation in den Protokollen auf die folgende(n) Meldung(en):

   `Completed the post deployment setup script`

   Die obige Meldung weist darauf hin, dass alle Installationsschritte abgeschlossen sind.

   Falls Sie auf eines der folgenden FEHLER-Präfixe stoßen, melden Sie dies Ihrem Customer Success-Team:

   - Fehler im Setup-Skript nach der Bereitstellung
   - Ausnahme bei der Portierung des Übersetzungs-MAP
   - Die Übersetzungszuordnung kann für die Eigenschaft nicht von v1 auf v2 portiert werden
1. Upgrade des Oxygen Connector-Plug-ins, das mit Version 4.2 veröffentlicht wurde \(falls erforderlich\).
1. Löschen Sie den Browser-Cache nach der Installation des Pakets.
1. Fahren Sie mit dem Upgrade der Anpassungen fort, wie im nächsten Abschnitt beschrieben.

### Aktivieren des Skript-Triggers über ein Servlet (für 4.2.1)

BEITRAG:

```
http://localhost:4503/bin/guides/script/start?jobType=translation-map-upgrade
```

Antwort:

```
{
"msg": "Job is successfully submitted and lock node is created for future reference",
"lockNodePath": "/var/dxml/executor-locks/translation-map-upgrade/1683190032886",
"status": "SCHEDULED"
}
```

In der obigen Antwort-JSON enthält der `lockNodePath` den Pfad zum Knoten , der im Repository erstellt wurde und auf den gesendeten Auftrag verweist. Sie wird automatisch gelöscht, sobald der Auftrag abgeschlossen ist. Bis dahin können Sie in diesem Knoten den aktuellen Status des Auftrags abrufen.

Beispielprotokoll:
Im Folgenden finden Sie ein Beispiel für Protokolle, die in der Protokolldatei angezeigt werden, nachdem Sie das Skript Trigger haben.

```
04.05.2023 14:17:12.876 *INFO* [[0:0:0:0:0:0:0:1] [1683190032736] POST /bin/guides/script/start HTTP/1.1] com.adobe.dxml.common.executor.RunnableSynchronizedOTS Acquiring lock for job : translation-map-upgrade
04.05.2023 14:17:12.897 *INFO* [pool-59-thread-1] com.adobe.fmdita.xmltranslation.ots.TranslationMapUpgradeOTS Starting the thread to upgrade translation map from V1 to V2
04.05.2023 14:17:12.899 *INFO* [pool-59-thread-1] com.adobe.dxml.common.executor.RunnableSynchronizedOTS Initiating lock for node : /var/dxml/executor-locks/translation-map-upgrade/1683190032886
04.05.2023 14:17:12.901 *INFO* [pool-59-thread-1] com.adobe.fmdita.translationservices.TranslationMapUpgradeScript Starting porting of translation map from V1 to V2
04.05.2023 14:17:12.904 *INFO* [pool-59-thread-1] com.adobe.fmdita.translationservices.TranslationMapUpgradeScript Memory increase is of : 764 kB
04.05.2023 14:17:12.906 *INFO* [pool-59-thread-1] com.adobe.fmdita.translationservices.TranslationMapUpgradeScript Completed porting of translation map from V1 to V2
04.05.2023 14:17:12.907 *INFO* [pool-59-thread-1] com.adobe.dxml.common.executor.RunnableSynchronizedOTS Releasing lock for node : /var/dxml/executor-locks/translation-map-upgrade/1683190032886
04.05.2023 14:17:12.909 *INFO* [pool-59-thread-1] com.adobe.fmdita.xmltranslation.ots.TranslationMapUpgradeOTS Completed the thread to upgrade translation map from V1 to V2
```

Suchen Sie nach `com.adobe.fmdita.translationservices.TranslationMapUpgradeScript Completed porting of translation map from V1 to V2` und `com.adobe.fmdita.xmltranslation.ots.TranslationMapUpgradeOTS Completed the thread to upgrade translation map from V1 to V2`, bevor Sie mit den nächsten Schritten fortfahren.



## Nach der Installation von Version 4.2.1

>[!IMPORTANT]
>
> Die High-Tech-Vorlage wird auf dem aktualisierten Server nicht angezeigt. Um die High-Tech-Vorlage auf Ihrem Server einzubinden, können Sie sie kopieren: Source: /libs/fmdita/pdf/Hi-Tech-Ziel: /content/dam/dita-templates/pdf

Nach der Installation von Experience Manager Guides können Sie die verschiedenen Konfigurationen, die für die neu installierte Version gelten, mit Ihrem Setup zusammenführen.

>[!NOTE]
>
> Das Modell dam-update-asset kann angepasst werden. Wenn also Anpassungen vorgenommen wurden, müssen wir die Anpassungen und Experience Manager Guides mit der Arbeitskopie des Modells synchronisieren.

1. **Workflow „DAM-Update-Asset“ \(Änderungen nach der Verarbeitung\):**

1. URL öffnen:

   ```http
   http://localhost:4502/libs/cq/workflow/admin/console/content/models.html
   ```

1. Wählen Sie **Workflow DAM-Update-Asset**.
1. Klicken Sie auf **Bearbeiten**.
1. Wenn die **DXML Post Process Initiator**-Komponente vorhanden ist, stellen Sie sicher, dass die Anpassungen synchronisiert werden.
1. Wenn die **DXML Post Process Initiator**-Komponente fehlt, führen Sie die folgenden Schritte aus, um sie einzufügen:

1. Klicken Sie **Komponente einfügen** \(Verantwortlich für die Nachbearbeitung von Experience Manager Guides als letzter Schritt im Prozess\).
1. Konfigurieren Sie den **Prozessschritt** mit den folgenden Details:

   **Registerkarte „Allgemein“**

   **title:** DXML-Nachbearbeitungs-Initiator

   **Beschreibung**: Schritt „DXML-Nachbearbeitungs-Initiator“, der einen Sling-Auftrag für die DXML-Nachbearbeitung des geänderten/erstellten Assets Trigger

   **Registerkarte „Prozess“**

   - Wählen Sie **DXML Post Process Initiator** aus der Dropdown **Prozess** aus

   - Wählen Sie **Handler-Fortschritt** aus

   - Wählen Sie **Fertig**

1. Klicken Sie **rechts oben** den Änderungen auf „Synchronisieren“. Sie erhalten eine Erfolgsbenachrichtigung.

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
   - Alle Komponenten, die von /libs/fmdidator/libs überlagert sind, sollten mit dem neuen Produkt-Code verglichen werden und Aktualisierungen sollten in überlagerten Dateien unter /apps vorgenommen werden.
   - Alle Client-Bibliothekskategorien, die vom Produkt verwendet werden, sollten auf Änderungen überprüft werden. Alle überschriebenen Konfigurationen \(Beispiele unten\) sollten mit den neuesten verglichen werden, um die neuesten Funktionen zu erhalten:
   - elementmapping.xml
   - ui\_config.json\(wurde möglicherweise in Ordnerprofilen festgelegt\)
   - geänderte `com.adobe.fmdita.config.ConfigManager`
   - Überprüfen Sie, ob einer der benutzerdefinierten Codes alte Pfade verwendet hat \(wie im Abschnitt [Migrationszuordnung](#id2244LE040XA)\) - sollte auf die neuen Pfade aktualisiert werden, damit die Anpassungen ebenfalls erwartungsgemäß funktionieren.
1. Lesen Sie alle neuen Konfigurationen, die in der aktuellen Version bereitgestellt werden \(überprüfen Sie [Versionshinweise](../release-info/release-notes-4-2-1.md)\), und überprüfen Sie, ob Funktionen betroffen sind. Ein Beispiel könnte die Verwendung von „Verbessertes Datei- und Versionsmanagement“ sein, die in Version 4.0 eingeführt wurde und für die Sie eine Konfiguration aktivieren müssen.

## Schritte zum Indizieren des vorhandenen Inhalts für die Verwendung des neuen Such- und Ersetzungsmodus:

Führen Sie die folgenden Schritte aus, um den vorhandenen Inhalt zu indizieren und den neuen Text „Suchen und Ersetzen“ auf Zuordnungsebene zu verwenden:

- Stellen Sie sicher, dass die `damAssetLucene` Indizierung abgeschlossen wurde. Je nach der auf dem Server vorhandenen Datenmenge kann dies bis zu ein paar Stunden dauern. Sie können bestätigen, dass die Neuindizierung abgeschlossen ist, indem Sie überprüfen, ob das Neuindizierungsfeld in auf „false“ gesetzt ist
  `http://<server:port>/oak:index/damAssetLucene`.  Wenn Sie außerdem Anpassungen in `damAssetLucene` hinzugefügt haben, müssen Sie diese möglicherweise erneut anwenden.

- Führen Sie eine POST-Anfrage an den Server \(mit korrekter Authentifizierung\) - `http://<server:port\>/bin/guides/map-find/indexing` aus. (Optional) Sie können bestimmte Pfade der Zuordnungen übergeben, um sie zu indizieren. Standardmäßig werden alle Zuordnungen indiziert \|\| Beispiel: `https://<Server:port\>/bin/guides/map-find/indexing?paths=<map\_path\_in\_repository\>`)

- Sie können auch einen Stammordner übergeben, um die DITA-Zuordnungen eines bestimmten Ordners (und seiner Unterordner) zu indizieren. Beispiel: `http://<server:port\>/bin/guides/map-find/indexing?root=/content/dam/test`. Beachten Sie, dass nur der Pfadparameter berücksichtigt wird, wenn sowohl der Pfadparameter als auch der Stammparameter übergeben werden.

- Die API gibt eine jobId zurück. Zur Überprüfung des Auftragsstatus können Sie eine GET-Anfrage mit Auftrags-ID an denselben Endpunkt senden - `http://<server:port\>/bin/guides/map-find/indexing?jobId=\{jobId\}`\(Beispiel: `http://localhost:8080/bin/guides/map-find/indexing?jobId=2022/9/15/7/27/7dfa1271-981e-4617-b5a4-c18379f11c42`\)


- Sobald der Vorgang abgeschlossen ist, wird die obige GET-Anfrage erfolgreich beantwortet und es wird angegeben, ob Zuordnungen fehlgeschlagen sind. Die erfolgreich indizierten Zuordnungen können aus den Serverprotokollen bestätigt werden.


## Aktualisierung auf Version 4.3.0

Die Aktualisierung auf Version 4.3.0 hängt von der aktuellen Version von Experience Manager Guides ab. Wenn Sie Version 4.2 oder 4.2.x verwenden, können Sie direkt auf Version 4.3.0 aktualisieren.

>[!NOTE]
>
>Die Nachbearbeitung und Indizierung kann einige Stunden dauern. Es wird empfohlen, den Upgrade-Prozess außerhalb der Spitzenzeiten zu starten.

****Voraussetzungen****

Stellen Sie vor dem Start des Upgrades auf Experience Manager Guides 4.3.0 Folgendes sicher:

1. auf Experience Manager Guides Version 4.2 oder 4.2.x aktualisiert und der entsprechende Installationsschritt abgeschlossen.
1. Alle Übersetzungsaufgaben geschlossen.



## Installieren von Version 4.3.0

1. Laden Sie das Versionspaket 4.3.0 vom [Adobe Software Distribution Portal](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html) herunter.
1. Installieren Sie das Paket Version 4.3.0.
1. Löschen Sie den Browser-Cache nach der Installation des Pakets.
1. Aktualisieren Sie die Datei `ui_config.json` auf der Registerkarte **XML-Editor** im Ordnerprofil.


## Nach der Installation von Version 4.3.0

Nach der Installation von Experience Manager Guides können Sie die verschiedenen Konfigurationen, die für die neu installierte Version gelten, mit Ihrem Setup zusammenführen.

## Schritte zur Nachbearbeitung des vorhandenen Inhalts, um den Bericht über fehlerhafte Links zu verwenden


Führen Sie die folgenden Schritte aus, um den vorhandenen Inhalt nachzuverarbeiten und den neuen Bericht „Beschädigter Link“ zu verwenden:

1. (Optional) Wenn mehr als 100.000 DITA-Dateien im System vorhanden sind, aktualisieren Sie die `queryLimitReads` unter `org.apache.jackrabbit.oak.query.QueryEngineSettingsService` auf einen größeren Wert (einen beliebigen Wert, der größer ist als die Anzahl der vorhandenen Assets, z. B. 200.000) und stellen Sie dann erneut bereit.

   | PID | Eigenschaftsschlüssel | Eigenschaftswert |
   |---|---|---|
   | org.apache.jackrabbit.oak.query.QueryEngineSettingsService | queryLimitReads | Wert: 200000 <br> Standardwert: 100000 |

1. Führen Sie die folgenden APIs aus, um die Nachbearbeitung für alle Dateien auszuführen:

   | Endpunkt | /bin/guides/reports/upgrade |
   |---|---|
   | Abfragetyp | **POST** Dieses Skript ist eine POST-Anfrage und sollte daher über Agenten wie Postman ausgeführt werden. |
   | Erwartete Antwort | Die API gibt eine jobId zurück. Um den Auftragsstatus zu überprüfen, können Sie eine GET-Anfrage mit Auftrags-ID an denselben Endpunkt senden.<br> Beispiel-URL: `http://<server:port>/bin/guides/reports/upgrade` |

   | Endpunkt | /bin/guides/reports/upgrade |
   |---|---|
   | Abfragetyp | **GET** |
   | Parameter | jobId: Übergeben Sie die jobId, die von der vorherigen POST-Anfrage erhalten wurde. |
   | Erwartete Antwort | - Nachdem der Vorgang abgeschlossen ist, wird die GET-Anfrage erfolgreich beantwortet. <br> - Wenn Fehler auftreten, teilen Sie die Fehlerprotokolle zusammen mit der API-Ausgabe mit Ihrem Customer Success-Team.  <br>Beispiel-URL: `http://<server:port>/bin/guides/reports/upgrade?jobId=2022/9/15/7/27/7dfa1271-981e-4617-b5a4-c18379f11c42_678` |


1. Kehren Sie zum Standardwert oder vorherigen vorhandenen Wert von `queryLimitReads` zurück, wenn Sie ihn in Schritt 1 geändert haben.



## Aktualisierung auf Version 4.3.1

Die Aktualisierung auf Version 4.3.1 hängt von der aktuellen Version von Experience Manager Guides ab. Wenn Sie Version 4.3.0, 4.2 oder 4.2.1 verwenden, können Sie direkt auf Version 4.3.1 aktualisieren.

>[!NOTE]
>
>Die Nachbearbeitung und Indizierung kann einige Stunden dauern. Es wird empfohlen, den Upgrade-Prozess außerhalb der Spitzenzeiten zu starten.

****Voraussetzungen****

Stellen Sie vor dem Start des Upgrades auf Experience Manager Guides 4.3.1 Folgendes sicher:

1. auf Experience Manager Guides Version 4.3.0, 4.2 oder 4.2.1 aktualisiert und der entsprechende Installationsschritt abgeschlossen.
1. (Optional) Alle Übersetzungsaufgaben wurden geschlossen.
1. Protokollebene für `com.adobe.fmdita.translationservices.TranslationMapUpgradeScript` Klasse in &quot;**&quot;** und diese Protokolle in einer neuen Protokolldatei anhängen, z. B. `logs/translation_upgrade.log`.


## Installieren von Version 4.3.1

1. Laden Sie das Versionspaket 4.3.1 vom [Adobe Software Distribution Portal](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html) herunter.
1. Installieren Sie das Paket Version 4.3.1 .
1. Sie können den Trigger drücken, um den Upgrade-Auftrag für die Übersetzungskarte zu starten. Weitere Informationen finden Sie unter [Aktivieren des Skript-Triggers über ein Servlet](#enable-trigger-of-script-via-a-servlet-for-431).


1. Warten Sie nach Abschluss der Paketinstallation in den Protokollen auf die folgende(n) Meldung(en):

   `Completed the post deployment setup script`

   Die obige Meldung weist darauf hin, dass alle Installationsschritte abgeschlossen sind.

   Falls Sie auf eines der folgenden FEHLER-Präfixe stoßen, melden Sie dies Ihrem Customer Success-Team:

   - Fehler im Setup-Skript nach der Bereitstellung
   - Ausnahme bei der Portierung des Übersetzungs-MAP
   - Die Übersetzungszuordnung kann für die Eigenschaft nicht von v1 auf v2 portiert werden
1. Upgrade des Oxygen Connector-Plug-ins, das mit Version 4.2 veröffentlicht wurde \(falls erforderlich\).
1. Löschen Sie den Browser-Cache nach der Installation des Pakets.
1. Fahren Sie mit dem Upgrade der Anpassungen fort, wie im nächsten Abschnitt beschrieben.

### Aktivieren des Skript-Triggers über ein Servlet (für 4.3.1)

BEITRAG:

```
http://localhost:4503/bin/guides/script/start?jobType=translation-map-upgrade
```

Antwort:

```
{
"msg": "Job is successfully submitted and lock node is created for future reference",
"lockNodePath": "/var/dxml/executor-locks/translation-map-upgrade/1683190032886",
"status": "SCHEDULED"
}
```

In der obigen Antwort-JSON enthält der `lockNodePath` den Pfad zum Knoten , der im Repository erstellt wurde und auf den gesendeten Auftrag verweist. Sie wird automatisch gelöscht, sobald der Auftrag abgeschlossen ist. Bis dahin können Sie in diesem Knoten den aktuellen Status des Auftrags abrufen.

Beispielprotokoll:
Im Folgenden finden Sie ein Beispiel für Protokolle, die in der Protokolldatei angezeigt werden, nachdem Sie das Skript Trigger haben.

```
04.05.2023 14:17:12.876 *INFO* [[0:0:0:0:0:0:0:1] [1683190032736] POST /bin/guides/script/start HTTP/1.1] com.adobe.dxml.common.executor.RunnableSynchronizedOTS Acquiring lock for job : translation-map-upgrade
04.05.2023 14:17:12.897 *INFO* [pool-59-thread-1] com.adobe.fmdita.xmltranslation.ots.TranslationMapUpgradeOTS Starting the thread to upgrade translation map from V1 to V2
04.05.2023 14:17:12.899 *INFO* [pool-59-thread-1] com.adobe.dxml.common.executor.RunnableSynchronizedOTS Initiating lock for node : /var/dxml/executor-locks/translation-map-upgrade/1683190032886
04.05.2023 14:17:12.901 *INFO* [pool-59-thread-1] com.adobe.fmdita.translationservices.TranslationMapUpgradeScript Starting porting of translation map from V1 to V2
04.05.2023 14:17:12.904 *INFO* [pool-59-thread-1] com.adobe.fmdita.translationservices.TranslationMapUpgradeScript Memory increase is of : 764 kB
04.05.2023 14:17:12.906 *INFO* [pool-59-thread-1] com.adobe.fmdita.translationservices.TranslationMapUpgradeScript Completed porting of translation map from V1 to V2
04.05.2023 14:17:12.907 *INFO* [pool-59-thread-1] com.adobe.dxml.common.executor.RunnableSynchronizedOTS Releasing lock for node : /var/dxml/executor-locks/translation-map-upgrade/1683190032886
04.05.2023 14:17:12.909 *INFO* [pool-59-thread-1] com.adobe.fmdita.xmltranslation.ots.TranslationMapUpgradeOTS Completed the thread to upgrade translation map from V1 to V2
```

Suchen Sie nach `com.adobe.fmdita.translationservices.TranslationMapUpgradeScript Completed porting of translation map from V1 to V2` und `com.adobe.fmdita.xmltranslation.ots.TranslationMapUpgradeOTS Completed the thread to upgrade translation map from V1 to V2`, bevor Sie mit den nächsten Schritten fortfahren.

## Nach der Installation von Version 4.3.1



Nach der Installation von Experience Manager Guides können Sie die verschiedenen Konfigurationen, die für die neu installierte Version gelten, mit Ihrem Setup zusammenführen.

>[!NOTE]
>
> Das Modell dam-update-asset kann angepasst werden. Wenn also Anpassungen vorgenommen wurden, müssen wir die Anpassungen und Experience Manager Guides mit der Arbeitskopie des Modells synchronisieren.

1. **Workflow „DAM-Update-Asset“ \(Änderungen nach der Verarbeitung\):**

1. URL öffnen:

   ```
   http://localhost:4502/libs/cq/workflow/admin/console/content/models.html 
   ```

1. Wählen Sie **Workflow DAM-Update-Asset**.
1. Klicken Sie auf **Bearbeiten**.
1. Wenn die **DXML Post Process Initiator**-Komponente vorhanden ist, stellen Sie sicher, dass die Anpassungen synchronisiert werden.
1. Wenn die **DXML Post Process Initiator**-Komponente fehlt, führen Sie die folgenden Schritte aus, um sie einzufügen:

1. Klicken Sie **Komponente einfügen** \(Verantwortlich für die Nachbearbeitung von Experience Manager Guides als letzter Schritt im Prozess\).
1. Konfigurieren Sie den **Prozessschritt** mit den folgenden Details:

   **Registerkarte „Allgemein“**

   **title:** DXML-Nachbearbeitungs-Initiator

   **Beschreibung**: Schritt „DXML-Nachbearbeitungs-Initiator“, der einen Sling-Auftrag für die DXML-Nachbearbeitung des geänderten/erstellten Assets Trigger

   **Registerkarte „Prozess“**

   - Wählen Sie **DXML Post Process Initiator** aus der Dropdown **Prozess** aus

   - Wählen Sie **Handler-Fortschritt** aus

   - Wählen Sie **Fertig**

1. Klicken Sie **rechts oben** den Änderungen auf „Synchronisieren“. Sie erhalten eine Erfolgsbenachrichtigung.

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
   - Alle Komponenten, die von /libs/fmdidator/libs überlagert sind, sollten mit dem neuen Produkt-Code verglichen werden und Aktualisierungen sollten in überlagerten Dateien unter /apps vorgenommen werden.
   - Alle Client-Bibliothekskategorien, die vom Produkt verwendet werden, sollten auf Änderungen überprüft werden. Alle überschriebenen Konfigurationen \(Beispiele unten\) sollten mit den neuesten verglichen werden, um die neuesten Funktionen zu erhalten:
   - elementmapping.xml
   - ui\_config.json\(wurde möglicherweise in Ordnerprofilen festgelegt\)
   - geänderte `com.adobe.fmdita.config.ConfigManager`


## Schritte zum Indizieren des vorhandenen Inhalts

>[!NOTE]
>
> Sie müssen diese Schritte nicht ausführen, wenn Sie von 4.3.0 oder 4.2.1 aktualisieren.

Führen Sie die folgenden Schritte aus, um den vorhandenen Inhalt zu indizieren und den neuen Text „Suchen und Ersetzen“ auf Zuordnungsebene zu verwenden:


- Führen Sie eine POST-Anfrage an den Server \(mit korrekter Authentifizierung\) - `http://<server:port\>/bin/guides/map-find/indexing` aus. (Optional) Sie können bestimmte Pfade der Zuordnungen übergeben, um sie zu indizieren. Standardmäßig werden alle Zuordnungen indiziert \|\| Beispiel: `https://<Server:port\>/bin/guides/map-find/indexing?paths=<map\_path\_in\_repository\>`)


- Die API gibt eine jobId zurück. Zur Überprüfung des Auftragsstatus können Sie eine GET-Anfrage mit Auftrags-ID an denselben Endpunkt senden - `http://<server:port\>/bin/guides/map-find/indexing?jobId=\{jobId\}`\(Beispiel: `http://localhost:8080/bin/guides/map-find/indexing?jobId=2022/9/15/7/27/7dfa1271-981e-4617-b5a4-c18379f11c42`\)


- Sobald der Vorgang abgeschlossen ist, wird die obige GET-Anfrage erfolgreich beantwortet und es wird angegeben, ob Zuordnungen fehlgeschlagen sind. Die erfolgreich indizierten Zuordnungen können aus den Serverprotokollen bestätigt werden.

## Schritte zur Nachbearbeitung des vorhandenen Inhalts, um den Bericht über fehlerhafte Links zu verwenden

>[!NOTE]
>
> Sie müssen diese Schritte nicht ausführen, wenn Sie von 4.3.0 aktualisieren

Führen Sie die folgenden Schritte aus, um den vorhandenen Inhalt nachzuverarbeiten und den neuen Bericht „Beschädigter Link“ zu verwenden:

1. (Optional) Wenn mehr als 100.000 DITA-Dateien im System vorhanden sind, aktualisieren Sie die `queryLimitReads` unter `org.apache.jackrabbit.oak.query.QueryEngineSettingsService` auf einen größeren Wert (einen beliebigen Wert, der größer ist als die Anzahl der vorhandenen Assets, z. B. 200.000) und stellen Sie dann erneut bereit.

   | PID | Eigenschaftsschlüssel | Eigenschaftswert |
   |---|---|---|
   | org.apache.jackrabbit.oak.query.QueryEngineSettingsService | queryLimitReads | Wert: 200000 <br> Standardwert: 100000 |

1. Führen Sie die folgenden APIs aus, um die Nachbearbeitung für alle Dateien auszuführen:

   | Endpunkt | /bin/guides/reports/upgrade |
   |---|---|
   | Abfragetyp | **POST** Dieses Skript ist eine POST-Anfrage und sollte daher über Agenten wie Postman ausgeführt werden. |
   | Erwartete Antwort | Die API gibt eine jobId zurück. Um den Auftragsstatus zu überprüfen, können Sie eine GET-Anfrage mit Auftrags-ID an denselben Endpunkt senden.<br> Beispiel-URL: `http://<server:port>/bin/guides/reports/upgrade` |

   | Endpunkt | /bin/guides/reports/upgrade |
   |---|---|
   | Abfragetyp | **GET** |
   | Parameter | jobId: Übergeben Sie die jobId, die von der vorherigen POST-Anfrage erhalten wurde. |
   | Erwartete Antwort | - Nachdem der Vorgang abgeschlossen ist, wird die GET-Anfrage erfolgreich beantwortet. <br> - Wenn Fehler auftreten, teilen Sie die Fehlerprotokolle zusammen mit der API-Ausgabe mit Ihrem Customer Success-Team.  <br>Beispiel-URL: `http://<server:port>/bin/guides/reports/upgrade?jobId=2022/9/15/7/27/7dfa1271-981e-4617-b5a4-c18379f11c42_678` |


1. Kehren Sie zum Standardwert oder vorherigen vorhandenen Wert von `queryLimitReads` zurück, wenn Sie ihn in Schritt 1 geändert haben.



## Aktualisieren auf Version 4.3.1.5

Das Upgrade auf Version 4.3.1.5 hängt von der aktuellen Version von Experience Manager Guides ab. Wenn Sie Version 4.3.1 verwenden, können Sie direkt auf Version 4.3.1.5 aktualisieren.



## Installieren von Version 4.3.1.5

1. Laden Sie 4.3.1.5 Versionspaket vom [Adobe Software Distribution Portal](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html) herunter.
1. Installieren Sie Version 4.3.1.5 Pakets.

1. Warten Sie, bis der Installationsprozess erfolgreich abgeschlossen wurde.
1. Fahren Sie mit dem Upgrade der Anpassungen fort, wie im nächsten Abschnitt beschrieben.


## Nach der Installation von Version 4.3.1.5


>[!NOTE]
>
>Wenn Sie das Bundle org.apache.velocity verwenden möchten, führen Sie die folgenden Schritte aus, bevor Sie das Bundle hochladen:
> 1. Rufen Sie `<server>:<port>/system/console/bundles` auf.
> 1. Suchen Sie nach org.apache.velocity.
> 1. Deinstallieren Sie das gesuchte Bundle.
> 1. Installieren Sie das erforderliche Velocity-Bundle.


1. Nachdem das Upgrade abgeschlossen ist, stellen Sie sicher, dass alle Anpassungen/Überlagerungen validiert und aktualisiert werden, damit sie dem neuen Anwendungs-Code entsprechen. Im Folgenden finden Sie einige Beispiele:
   - Alle Komponenten, die von `/libs/fmdita` oder ` /libs` überlagert sind, sollten mit dem neuen Produkt-Code verglichen werden und Aktualisierungen sollten in überlagerten Dateien unter `/apps` erfolgen.
   - Alle Client-Bibliothekskategorien, die vom Produkt verwendet werden, sollten auf Änderungen überprüft werden. Alle überschriebenen Konfigurationen \(Beispiele unten\) sollten mit den neuesten verglichen werden, um die neuesten Funktionen zu erhalten:
   - `elementmapping.xml`
   - `ui\_config.json\` (kann in Ordnerprofilen festgelegt worden sein\)
   - geänderte `com.adobe.fmdita.config.ConfigManager`







## Aktualisierung auf Version 4.4.0

Die Aktualisierung auf Version 4.4.0 hängt von der aktuellen Version von Experience Manager Guides ab. Wenn Sie Version 4.3.1, 4.3.0, 4.2 oder 4.2.1 (Hotfix 4.2.1.3) verwenden, können Sie direkt auf Version 4.4.0 aktualisieren

>[!NOTE]
>
>Die Nachbearbeitung und Indizierung kann einige Stunden dauern. Es wird empfohlen, den Upgrade-Prozess außerhalb der Spitzenzeiten zu starten.

****Voraussetzungen****

Stellen Sie vor dem Start des Upgrades auf Experience Manager Guides 4.4.0 Folgendes sicher:

1. auf Experience Manager Guides Version 4.3.1, 4.3.0 oder 4.2.1 (Hotfix 4.2.1.3) aktualisiert und der entsprechende Installationsschritt abgeschlossen.
1. (Optional) Alle Übersetzungsaufgaben wurden geschlossen.
1. Protokollebene für `com.adobe.fmdita.translationservices.TranslationMapUpgradeScript` Klasse in &quot;**&quot;** und diese Protokolle in einer neuen Protokolldatei anhängen, z. B. `logs/translation_upgrade.log`.


## Installieren von Version 4.4.0

1. Laden Sie das Versionspaket 4.4.0 vom [Adobe Software Distribution Portal](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html) herunter.
1. Installieren Sie das Paket Version 4.4.0.
1. Sie können den Trigger drücken, um den Upgrade-Auftrag für die Übersetzungskarte zu starten. Weitere Informationen finden Sie unter [Aktivieren des Skript-Triggers über ein Servlet](#enable-trigger-of-script-via-a-servlet).

1. Warten Sie nach Abschluss der Paketinstallation in den Protokollen auf die folgende(n) Meldung(en):

   `Completed the post deployment setup script`

   Die obige Meldung weist darauf hin, dass alle Installationsschritte abgeschlossen sind.

   Falls Sie auf eines der folgenden FEHLER-Präfixe stoßen, melden Sie dies Ihrem Customer Success-Team:

   - Fehler im Setup-Skript nach der Bereitstellung
   - Ausnahme bei der Portierung des Übersetzungs-MAP
   - Die Übersetzungszuordnung kann für die Eigenschaft nicht von v1 auf v2 portiert werden
1. Upgrade des Oxygen Connector-Plug-ins, das mit Version 4.4.0 veröffentlicht wurde \(falls erforderlich\).
1. Löschen Sie den Browser-Cache nach der Installation des Pakets.
1. Fahren Sie mit dem Upgrade der Anpassungen fort, wie im nächsten Abschnitt beschrieben.


## Nach der Installation von Version 4.4.0

Nach der Installation von Experience Manager Guides können Sie die verschiedenen Konfigurationen, die für die neu installierte Version gelten, mit Ihrem Setup zusammenführen.

>[!NOTE]
>
> Das Modell dam-update-asset kann angepasst werden. Wenn also Anpassungen vorgenommen wurden, müssen wir die Anpassungen und Experience Manager Guides mit der Arbeitskopie des Modells synchronisieren.

1. **Workflow „DAM-Update-Asset“ \(Änderungen nach der Verarbeitung\):**

1. URL öffnen:

   ```
   http://localhost:4502/libs/cq/workflow/admin/console/content/models.html 
   ```

1. Wählen Sie **Workflow DAM-Update-Asset**.
1. Klicken Sie auf **Bearbeiten**.
1. Wenn die **DXML Post Process Initiator**-Komponente vorhanden ist, stellen Sie sicher, dass die Anpassungen synchronisiert werden.
1. Wenn die **DXML Post Process Initiator**-Komponente fehlt, führen Sie die folgenden Schritte aus, um sie einzufügen:

1. Klicken Sie **Komponente einfügen** \(Verantwortlich für die Nachbearbeitung von Experience Manager Guides als letzter Schritt im Prozess\).
1. Konfigurieren Sie den **Prozessschritt** mit den folgenden Details:

   **Registerkarte „Allgemein“**

   **title:** DXML-Nachbearbeitungs-Initiator

   **Beschreibung**: Schritt „DXML-Nachbearbeitungs-Initiator“, der einen Sling-Auftrag für die DXML-Nachbearbeitung des geänderten/erstellten Assets Trigger

   **Registerkarte „Prozess“**

   - Wählen Sie **DXML Post Process Initiator** aus der Dropdown **Prozess** aus

   - Wählen Sie **Handler-Fortschritt** aus

   - Wählen Sie **Fertig**

1. Klicken Sie **rechts oben** den Änderungen auf „Synchronisieren“. Sie erhalten eine Erfolgsbenachrichtigung.

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
   - Alle Komponenten, die von /libs/fmdidator/libs überlagert sind, sollten mit dem neuen Produkt-Code verglichen werden und Aktualisierungen sollten in überlagerten Dateien unter /apps vorgenommen werden.
   - Alle Client-Bibliothekskategorien, die vom Produkt verwendet werden, sollten auf Änderungen überprüft werden. Alle überschriebenen Konfigurationen \(Beispiele unten\) sollten mit den neuesten verglichen werden, um die neuesten Funktionen zu erhalten:
   - elementmapping.xml
   - ui\_config.json\(wurde möglicherweise in Ordnerprofilen festgelegt\)
   - geänderte `com.adobe.fmdita.config.ConfigManager`

1. Wenn Sie Anpassungen in damAssetLucene hinzugefügt haben, müssen Sie diese möglicherweise erneut anwenden. Nachdem Sie diese Änderungen vorgenommen haben, setzen Sie die Neuindizierung auf „true“. Dadurch werden alle vorhandenen Knoten mit den Anpassungen neu indiziert. Nach Abschluss wird das Neuindizierungs-Flag erneut auf „false“ gesetzt. Dies kann je nach Anzahl der Assets im System einige Stunden dauern.

## Schritte zum Indizieren des vorhandenen Inhalts

>[!NOTE]
>
> Sie müssen diese Schritte nicht ausführen, wenn Sie von 4.3.0 oder 4.3.1 aktualisieren.

Führen Sie die folgenden Schritte aus, um den vorhandenen Inhalt zu indizieren und den neuen Text „Suchen und Ersetzen“ auf Zuordnungsebene zu verwenden:

- Führen Sie eine POST-Anfrage an den Server \(mit korrekter Authentifizierung\) - `http://<server:port\>/bin/guides/map-find/indexing` aus. (Optional) Sie können bestimmte Pfade der Zuordnungen übergeben, um sie zu indizieren. Standardmäßig werden alle Zuordnungen indiziert \|\| Beispiel: `https://<Server:port\>/bin/guides/map-find/indexing?paths=<map\_path\_in\_repository\>`)

- Die API gibt eine jobId zurück. Zur Überprüfung des Auftragsstatus können Sie eine GET-Anfrage mit Auftrags-ID an denselben Endpunkt senden - `http://<server:port\>/bin/guides/map-find/indexing?jobId=\{jobId\}`\(Beispiel: `http://localhost:8080/bin/guides/map-find/indexing?jobId=2022/9/15/7/27/7dfa1271-981e-4617-b5a4-c18379f11c42`\)

- Sobald der Vorgang abgeschlossen ist, wird die obige GET-Anfrage erfolgreich beantwortet und es wird angegeben, ob Zuordnungen fehlgeschlagen sind. Die erfolgreich indizierten Zuordnungen können aus den Serverprotokollen bestätigt werden.

## Schritte zur Nachbearbeitung des vorhandenen Inhalts, um den Bericht über fehlerhafte Links zu verwenden

>[!NOTE]
>
> Sie müssen diese Schritte nicht ausführen, wenn Sie von 4.3.0 oder 4.3.1 aktualisieren.

Führen Sie die folgenden Schritte aus, um den vorhandenen Inhalt nachzuverarbeiten und den neuen Bericht „Beschädigter Link“ zu verwenden:

1. (Optional) Wenn mehr als 100.000 DITA-Dateien im System vorhanden sind, aktualisieren Sie die `queryLimitReads` unter `org.apache.jackrabbit.oak.query.QueryEngineSettingsService` auf einen größeren Wert (einen beliebigen Wert, der größer ist als die Anzahl der vorhandenen Assets, z. B. 200.000) und stellen Sie dann erneut bereit.

   | PID | Eigenschaftsschlüssel | Eigenschaftswert |
   |---|---|---|
   | org.apache.jackrabbit.oak.query.QueryEngineSettingsService | queryLimitReads | Wert: 200000 <br> Standardwert: 100000 |

1. Führen Sie die folgenden APIs aus, um die Nachbearbeitung für alle Dateien auszuführen:

   | Endpunkt | /bin/guides/reports/upgrade |
   |---|---|
   | Abfragetyp | **POST** Dieses Skript ist eine POST-Anfrage und sollte daher über Agenten wie Postman ausgeführt werden. |
   | Erwartete Antwort | Die API gibt eine jobId zurück. Um den Auftragsstatus zu überprüfen, können Sie eine GET-Anfrage mit Auftrags-ID an denselben Endpunkt senden.<br> Beispiel-URL: `http://<server:port>/bin/guides/reports/upgrade` |

   | Endpunkt | /bin/guides/reports/upgrade |
   |---|---|
   | Abfragetyp | **GET** |
   | Parameter | jobId: Übergeben Sie die jobId, die von der vorherigen POST-Anfrage erhalten wurde. |
   | Erwartete Antwort | - Nachdem der Vorgang abgeschlossen ist, wird die GET-Anfrage erfolgreich beantwortet. <br> - Wenn Fehler auftreten, teilen Sie die Fehlerprotokolle zusammen mit der API-Ausgabe mit Ihrem Customer Success-Team.  <br>Beispiel-URL: `http://<server:port>/bin/guides/reports/upgrade?jobId=2022/9/15/7/27/7dfa1271-981e-4617-b5a4-c18379f11c42_678` |

1. Kehren Sie zum Standardwert oder vorherigen vorhandenen Wert von `queryLimitReads` zurück, wenn Sie ihn in Schritt 1 geändert haben.

### Aktivieren des Skript-Triggers über ein Servlet

>[!NOTE]
>
> Sie müssen diese Schritte nicht ausführen, wenn Sie von 4.3.0 oder 4.3.1 aktualisieren.

BEITRAG:

```
http://localhost:4503/bin/guides/script/start?jobType=translation-map-upgrade
```

Antwort:

```
{
"msg": "Job is successfully submitted and lock node is created for future reference",
"lockNodePath": "/var/dxml/executor-locks/translation-map-upgrade/1683190032886",
"status": "SCHEDULED"
}
```

In der obigen Antwort-JSON enthält der `lockNodePath` den Pfad zum Knoten , der im Repository erstellt wurde und auf den gesendeten Auftrag verweist. Sie wird automatisch gelöscht, sobald der Auftrag abgeschlossen ist. Bis dahin können Sie in diesem Knoten den aktuellen Status des Auftrags abrufen.

Suchen Sie nach `com.adobe.fmdita.translationservices.TranslationMapUpgradeScript Completed porting of translation map from V1 to V2` und `com.adobe.fmdita.xmltranslation.ots.TranslationMapUpgradeOTS Completed the thread to upgrade translation map from V1 to V2`, bevor Sie mit den nächsten Schritten fortfahren.

>[!NOTE]
>
> Überprüfen Sie, ob der Knoten noch vorhanden ist, und den Status des Auftrags.

**GET**: `http://<aem_domain>/var/dxml/executor-locks/translation-map-upgrade/1683190032886.json`



## Schritte zum Umgang mit dem `'fmdita rewriter'`

Experience Manager Guides verfügt über [**Modul „Benutzerdefiniertes Sling Rewriter**](../cs-install-guide/conf-output-generation.md#custom-rewriter), in dem die Links verarbeitet werden, die bei Kreuzzuordnungen (Verknüpfungen zwischen den Themen zweier verschiedener Zuordnungen) generiert werden.

Wenn Sie einen anderen benutzerdefinierten Sling Rewriter in Ihrer Codebasis haben, verwenden Sie einen `'order'` Wert größer als 50, da der Experience Manager Guides Sling Rewriter `'order'` 50 verwendet.  Um dies zu überschreiben, benötigen Sie einen Wert >50. Weitere Informationen finden Sie unter [Output-Umschreibungs-Pipelines](https://sling.apache.org/documentation/bundles/output-rewriting-pipelines-org-apache-sling-rewriter.html).

Da während dieses Upgrades der `'order'` von 1000 auf 50 geändert wird, müssen Sie den vorhandenen benutzerdefinierten Rewriter (sofern vorhanden) mit `'fmdita-rewriter'` zusammenführen.


**Übergeordnetes Thema:**[ Herunterladen und installieren](download-install.md)


## Aktualisieren auf Version 4.6.0

>[!TIP]
>
> Es wird empfohlen, 4.6.0 Service Pack 4 auf Version 4.6.0 , 4.6.0 Service Pack 1 oder 4.6.0 Service Pack 3 zu installieren. Der Upgrade-Prozess für Version 4.6.0 Service Pack 4 folgt denselben Schritten wie für Version 4.6.0.

Die Aktualisierung auf Version 4.6.0 hängt von der aktuellen Version von Experience Manager Guides ab. Wenn Sie Version 4.4.0, 4.3.1, 4.3.0, 4.2 oder 4.2.1 (Hotfix 4.2.1.3) verwenden, können Sie direkt auf Version 4.6.0 aktualisieren.

>[!NOTE]
>
> Die Nachbearbeitung und Indizierung kann einige Stunden dauern. Es wird empfohlen, den Upgrade-Prozess außerhalb der Spitzenzeiten zu starten.

****Voraussetzungen****

Stellen Sie vor dem Start des Upgrades auf Experience Manager Guides 4.6.0 Folgendes sicher:

1. auf Experience Manager Guides Version 4.3.1, 4.3.0 oder 4.2.1 (Hotfix 4.2.1.3) aktualisiert und der entsprechende Installationsschritt abgeschlossen.
1. (Optional) Alle Übersetzungsaufgaben wurden geschlossen.
1. Protokollebene für `com.adobe.fmdita.translationservices.TranslationMapUpgradeScript` Klasse in &quot;**&quot;** und diese Protokolle in einer neuen Protokolldatei anhängen, z. B. `logs/translation_upgrade.log`.


## Installieren von Version 4.6.0

1. Laden Sie das Versionspaket 4.6.0 vom [Adobe Software Distribution Portal](https://experience.adobe.com/#/downloads/content/software-distribution/de/aem.html) herunter.
1. Installieren Sie das Paket Version 4.6.0.
1. Sie können den Trigger drücken, um den Upgrade-Auftrag für die Übersetzungskarte zu starten. Weitere Informationen finden Sie unter [Aktivieren des Skript-Triggers über ein Servlet](#enable-trigger-of-script-via-a-servlet).

1. Warten Sie nach Abschluss der Paketinstallation in den Protokollen auf die folgende(n) Meldung(en):

   `Completed the post deployment setup script`

   Die obige Meldung weist darauf hin, dass alle Installationsschritte abgeschlossen sind.

   Falls Sie auf eines der folgenden FEHLER-Präfixe stoßen, melden Sie dies Ihrem Customer Success-Team:

   - Fehler im Setup-Skript nach der Bereitstellung
   - Ausnahme bei der Portierung des Übersetzungs-MAP
   - Die Übersetzungszuordnung kann für die Eigenschaft nicht von v1 auf v2 portiert werden
1. Upgrade des Oxygen Connector-Plug-ins, das mit Version 4.6.0 veröffentlicht wurde \(falls erforderlich\).
1. Löschen Sie den Browser-Cache nach der Installation des Pakets.

## Nach der Installation von Version 4.6.0

Nach der Installation von Experience Manager Guides können Sie die verschiedenen Konfigurationen, die für die neu installierte Version gelten, mit Ihrem Setup zusammenführen.

>[!NOTE]
>
> Das Modell dam-update-asset kann angepasst werden. Wenn also Anpassungen vorgenommen wurden, müssen wir die Anpassungen und Experience Manager Guides mit der Arbeitskopie des Modells synchronisieren.

1. **Workflow „DAM-Update-Asset“ \(Änderungen nach der Verarbeitung\):**

1. URL öffnen:

   ```
   http://localhost:4502/libs/cq/workflow/admin/console/content/models.html 
   ```

1. Wählen Sie **Workflow DAM-Update-Asset**.
1. Klicken Sie auf **Bearbeiten**.
1. Wenn die **DXML Post Process Initiator**-Komponente vorhanden ist, stellen Sie sicher, dass die Anpassungen synchronisiert werden.
1. Wenn die **DXML Post Process Initiator**-Komponente fehlt, führen Sie die folgenden Schritte aus, um sie einzufügen:

1. Klicken Sie **Komponente einfügen** \(Verantwortlich für die Nachbearbeitung von Experience Manager Guides als letzter Schritt im Prozess\).
1. Konfigurieren Sie den **Prozessschritt** mit den folgenden Details:

   **Registerkarte „Allgemein“**

   **title:** DXML-Nachbearbeitungs-Initiator

   **Beschreibung**: Schritt „DXML-Nachbearbeitungs-Initiator“, der einen Sling-Auftrag für die DXML-Nachbearbeitung des geänderten/erstellten Assets Trigger

   **Registerkarte „Prozess“**

   - Wählen Sie **DXML Post Process Initiator** aus der **Prozess** Dropdown aus

   - Wählen Sie **Handler-Fortschritt** aus

   - Wählen Sie **Fertig**

1. Klicken Sie **rechts oben** den Änderungen auf „Synchronisieren“. Sie erhalten eine Erfolgsbenachrichtigung.

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
   - Alle Komponenten, die von /libs/fmdidator/libs überlagert sind, sollten mit dem neuen Produkt-Code verglichen werden und Aktualisierungen sollten in überlagerten Dateien unter /apps vorgenommen werden.
   - Alle Client-Bibliothekskategorien, die vom Produkt verwendet werden, sollten auf Änderungen überprüft werden. Alle überschriebenen Konfigurationen \(Beispiele unten\) sollten mit den neuesten verglichen werden, um die neuesten Funktionen zu erhalten:
   - elementmapping.xml
   - ui\_config.json\(wurde möglicherweise in Ordnerprofilen festgelegt\)
   - geänderte `com.adobe.fmdita.config.ConfigManager`

1. Wenn Sie Anpassungen in damAssetLucene hinzugefügt haben, müssen Sie diese möglicherweise erneut anwenden. Nachdem Sie diese Änderungen vorgenommen haben, setzen Sie die Neuindizierung auf „true“. Dadurch werden alle vorhandenen Knoten mit den Anpassungen neu indiziert. Nach Abschluss wird das Neuindizierungs-Flag erneut auf „false“ gesetzt. Dies kann je nach Anzahl der Assets im System einige Stunden dauern.

## Neuindizierung der Experience Manager Guides-Indizes

1. Öffnen Sie `crx/de` und navigieren Sie zum Indexpfad: `/oak:index/guidesAssetProperties`
2. Legen Sie die Eigenschaft für die Neuindizierung auf `true` fest (standardmäßig `false`) und klicken Sie auf **Alle speichern**.
3. Sobald die Neuindizierung abgeschlossen ist, wird die Eigenschaft für die Neuindizierung erneut auf `false` festgelegt und die Neuindizierungsanzahl um 1 erhöht.

   >[!NOTE]
   >
   > Dies kann je nach Menge der vorhandenen Daten einige Minuten dauern.
4. Führen Sie dieselben Schritte für andere hinzugefügte oder geänderte Indizes aus: `guidesBulkActivation`, `guidesPeerLinkIndex` und `guidesKonnectTemplateIndex`.

## Schritte zum Indizieren des vorhandenen Inhalts



Führen Sie die folgenden Schritte aus, um den vorhandenen Inhalt zu indizieren:

- Führen Sie eine POST-Anfrage an den Server \(mit korrekter Authentifizierung\) - `http://<server:port\>/bin/guides/map-find/indexing` aus. (Optional) Sie können bestimmte Pfade der Karten übergeben, um sie zu indizieren. Standardmäßig werden alle Karten indiziert || Beispiel : `https://<Server:port\>/bin/guides/map-find/indexing?paths=<map\_path\_in\_repository\>`)

- Die API gibt eine jobId zurück. Um den Auftragsstatus zu überprüfen, können Sie eine GET-Anfrage mit Auftrags-ID an denselben Endpunkt senden - `http://<server:port\>/bin/guides/map-find/indexing?jobId=\{jobId\}`\(zum Beispiel: ` http://localhost:8080/bin/guides/map-find/indexing?jobId=2022/9/15/7/27/7dfa1271-981e-4617-b5a4-c18379f11c42_678`)

- Sobald der Vorgang abgeschlossen ist, wird die obige GET-Anfrage erfolgreich beantwortet und es wird angegeben, ob Zuordnungen fehlgeschlagen sind. Die erfolgreich indizierten Zuordnungen können aus den Serverprotokollen bestätigt werden.


>[!NOTE]
>
> Wenn Sie das benutzerdefinierte Schema verwenden, müssen Sie den Pfad der benutzerdefinierten DTD- und XSD-Datei catalog.xml-Dateien im AEM-Repository in der Option **Integrationskataloge** definieren.




## Schritte zum Umgang mit dem `'fmdita rewriter'`

Experience Manager Guides verfügt über [**Modul „Benutzerdefiniertes Sling Rewriter**](../cs-install-guide/conf-output-generation.md#custom-rewriter), in dem die Links verarbeitet werden, die bei Kreuzzuordnungen (Verknüpfungen zwischen den Themen zweier verschiedener Zuordnungen) generiert werden.

Wenn Sie einen anderen benutzerdefinierten Sling Rewriter in Ihrer Codebasis haben, verwenden Sie einen `'order'` Wert größer als 50, da der Experience Manager Guides Sling Rewriter `'order'` 50 verwendet.  Um dies zu überschreiben, benötigen Sie einen Wert >50. Weitere Informationen finden Sie unter [Output-Umschreibungs-Pipelines](https://sling.apache.org/documentation/bundles/output-rewriting-pipelines-org-apache-sling-rewriter.html).

Da während dieses Upgrades der `'order'` von 1000 auf 50 geändert wird, müssen Sie den vorhandenen benutzerdefinierten Rewriter (sofern vorhanden) mit `'fmdita-rewriter'` zusammenführen.


## Aktualisieren auf Version 5.0.0

>[!TIP]
>
> Die Aktualisierung auf Version 5.0.0 Service Pack 1 hängt von der aktuellen Version von Experience Manager Guides ab. Wenn Sie Version 5.0.0, 4.6.4, 4.6.3, 4.6.1, 4.6.0 oder 4.4 verwenden, können Sie direkt auf Version 5.0.0 Service Pack 1 aktualisieren.

>[!NOTE]
>
> Die Nachbearbeitung und Indizierung kann einige Stunden dauern. Es wird empfohlen, den Upgrade-Prozess außerhalb der Spitzenzeiten zu starten.

****Voraussetzungen****

Stellen Sie vor dem Start des Upgrades auf Experience Manager Guides 5.0.0 Folgendes sicher:

1. auf Experience Manager Guides Version 4.6.3, 4.6.1, 4.6.0 oder 4.4 aktualisiert und der entsprechende Installationsschritt abgeschlossen.
1. (Optional) Alle Übersetzungsaufgaben wurden geschlossen.
1. Protokollebene für `com.adobe.fmdita.translationservices.TranslationMapUpgradeScript` Klasse in &quot;**&quot;** und diese Protokolle in einer neuen Protokolldatei anhängen, z. B. `logs/translation_upgrade.log`.


## Installieren von Version 5.0.0

1. Laden Sie das Versionspaket 5.0.0 vom [Adobe Software Distribution Portal](https://experience.adobe.com/#/downloads/content/software-distribution/de/aem.html) herunter.
1. Installieren Sie das Paket Version 5.0.0.
1. Sie können den Trigger drücken, um den Upgrade-Auftrag für die Übersetzungskarte zu starten. Weitere Informationen finden Sie unter [Aktivieren des Skript-Triggers über ein Servlet](#enable-trigger-of-script-via-a-servlet).

1. Warten Sie nach Abschluss der Paketinstallation in den Protokollen auf die folgende(n) Meldung(en):

   `Completed the post deployment setup script`

   Die obige Meldung weist darauf hin, dass alle Installationsschritte abgeschlossen sind.

   Falls Sie auf eines der folgenden FEHLER-Präfixe stoßen, melden Sie dies Ihrem Customer Success-Team:

   - Fehler im Setup-Skript nach der Bereitstellung
   - Ausnahme bei der Portierung des Übersetzungs-MAP
   - Die Übersetzungszuordnung kann für die Eigenschaft nicht von v1 auf v2 portiert werden
1. Upgrade des Oxygen Connector-Plug-ins, das mit Version 5.0.0 veröffentlicht wurde \(falls erforderlich\).
1. Löschen Sie den Browser-Cache nach der Installation des Pakets.

## Nach der Installation von Version 5.0.0

Nach der Installation von Experience Manager Guides können Sie die verschiedenen Konfigurationen, die für die neu installierte Version gelten, mit Ihrem Setup zusammenführen.

>[!NOTE]
>
> Das Modell dam-update-asset kann angepasst werden. Wenn also Anpassungen vorgenommen wurden, müssen wir die Anpassungen und Experience Manager Guides mit der Arbeitskopie des Modells synchronisieren.

1. **Workflow „DAM-Update-Asset“ \(Änderungen nach der Verarbeitung\):**

1. URL öffnen:

   ```
   http://localhost:4502/libs/cq/workflow/admin/console/content/models.html 
   ```

1. Wählen Sie **Workflow DAM-Update-Asset**.
1. Klicken Sie auf **Bearbeiten**.
1. Wenn die **DXML Post Process Initiator**-Komponente vorhanden ist, stellen Sie sicher, dass die Anpassungen synchronisiert werden.
1. Wenn die **DXML Post Process Initiator**-Komponente fehlt, führen Sie die folgenden Schritte aus, um sie einzufügen:

1. Klicken Sie **Komponente einfügen** \(Verantwortlich für die Nachbearbeitung von Experience Manager Guides als letzter Schritt im Prozess\).
1. Konfigurieren Sie den **Prozessschritt** mit den folgenden Details:

   **Registerkarte „Allgemein“**

   **title:** DXML-Nachbearbeitungs-Initiator

   **Beschreibung**: Schritt „DXML-Nachbearbeitungs-Initiator“, der einen Sling-Auftrag für die DXML-Nachbearbeitung des geänderten/erstellten Assets Trigger

   **Registerkarte „Prozess“**

   - Wählen Sie **DXML Post Process Initiator** aus der **Prozess** Dropdown aus

   - Wählen Sie **Handler-Fortschritt** aus

   - Wählen Sie **Fertig**

1. Klicken Sie **rechts oben** den Änderungen auf „Synchronisieren“. Sie erhalten eine Erfolgsbenachrichtigung.

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
   - Alle Komponenten, die von /libs/fmdidator/libs überlagert sind, sollten mit dem neuen Produkt-Code verglichen werden und Aktualisierungen sollten in überlagerten Dateien unter /apps vorgenommen werden.
   - Alle Client-Bibliothekskategorien, die vom Produkt verwendet werden, sollten auf Änderungen überprüft werden. Alle überschriebenen Konfigurationen \(Beispiele unten\) sollten mit den neuesten verglichen werden, um die neuesten Funktionen zu erhalten:
   - elementmapping.xml
   - ui\_config.json\(wurde möglicherweise in Ordnerprofilen festgelegt\)
   - geänderte `com.adobe.fmdita.config.ConfigManager`

1. Wenn Sie Anpassungen in damAssetLucene hinzugefügt haben, müssen Sie diese möglicherweise erneut anwenden. Nachdem Sie diese Änderungen vorgenommen haben, setzen Sie die Neuindizierung auf „true“. Dadurch werden alle vorhandenen Knoten mit den Anpassungen neu indiziert. Nach Abschluss wird das Neuindizierungs-Flag erneut auf „false“ gesetzt. Dies kann je nach Anzahl der Assets im System einige Stunden dauern.

## Neuindizierung der Experience Manager Guides-Indizes

1. Öffnen Sie `crx/de` und navigieren Sie zum Indexpfad: `/oak:index/guidesAssetProperties`
2. Legen Sie die Eigenschaft für die Neuindizierung auf `true` fest (standardmäßig `false`) und klicken Sie auf **Alle speichern**.
3. Sobald die Neuindizierung abgeschlossen ist, wird die Eigenschaft für die Neuindizierung erneut auf `false` festgelegt und die Neuindizierungsanzahl um 1 erhöht.

   >[!NOTE]
   >
   > Dies kann je nach Menge der vorhandenen Daten einige Minuten dauern.
4. Führen Sie dieselben Schritte für andere hinzugefügte oder geänderte Indizes aus: `guidesBulkActivation`, `guidesPeerLinkIndex` und `guidesKonnectTemplateIndex`.

## Schritte zum Indizieren des vorhandenen Inhalts



Führen Sie die folgenden Schritte aus, um den vorhandenen Inhalt zu indizieren:

- Führen Sie eine POST-Anfrage an den Server \(mit korrekter Authentifizierung\) - `http://<server:port\>/bin/guides/map-find/indexing` aus. (Optional) Sie können bestimmte Pfade der Karten übergeben, um sie zu indizieren. Standardmäßig werden alle Karten indiziert || Beispiel : `https://<Server:port\>/bin/guides/map-find/indexing?paths=<map\_path\_in\_repository\>`)

- Die API gibt eine jobId zurück. Um den Auftragsstatus zu überprüfen, können Sie eine GET-Anfrage mit Auftrags-ID an denselben Endpunkt senden - `http://<server:port\>/bin/guides/map-find/indexing?jobId=\{jobId\}`\(zum Beispiel: ` http://localhost:8080/bin/guides/map-find/indexing?jobId=2022/9/15/7/27/7dfa1271-981e-4617-b5a4-c18379f11c42_678`)

- Sobald der Vorgang abgeschlossen ist, wird die obige GET-Anfrage erfolgreich beantwortet und es wird angegeben, ob Zuordnungen fehlgeschlagen sind. Die erfolgreich indizierten Zuordnungen können aus den Serverprotokollen bestätigt werden.


>[!NOTE]
>
> Wenn Sie das benutzerdefinierte Schema verwenden, müssen Sie den Pfad der benutzerdefinierten DTD- und XSD-Datei catalog.xml-Dateien im AEM-Repository in der Option **Integrationskataloge** definieren.




## Schritte zum Umgang mit dem `'fmdita rewriter'`

Experience Manager Guides verfügt über [**Modul „Benutzerdefiniertes Sling Rewriter**](../cs-install-guide/conf-output-generation.md#custom-rewriter), in dem die Links verarbeitet werden, die bei Kreuzzuordnungen (Verknüpfungen zwischen den Themen zweier verschiedener Zuordnungen) generiert werden.

Wenn Sie einen anderen benutzerdefinierten Sling Rewriter in Ihrer Codebasis haben, verwenden Sie einen `'order'` Wert größer als 50, da der Experience Manager Guides Sling Rewriter `'order'` 50 verwendet.  Um dies zu überschreiben, benötigen Sie einen Wert >50. Weitere Informationen finden Sie unter [Output-Umschreibungs-Pipelines](https://sling.apache.org/documentation/bundles/output-rewriting-pipelines-org-apache-sling-rewriter.html).

Da während dieses Upgrades der `'order'` von 1000 auf 50 geändert wird, müssen Sie den vorhandenen benutzerdefinierten Rewriter (sofern vorhanden) mit `'fmdita-rewriter'` zusammenführen.



## Schritte zur Neuindizierung von damAssetLucene

Die Indexdefinition wird für damAssetLucene mit Handbüchern aktualisiert. Informationen [ Neuindizierung von damAssetLucene nach ](https://experienceleague.adobe.com/en/docs/experience-cloud-kcs/kbarticles/ka-16460) Aktualisierung auf Version 5.0.0 finden Sie in diesem Artikel .

>[!NOTE]
>
> Stellen Sie bei Beachtung der Dokumentation sicher, dass beide Eigenschaften (reindex=true und reindex-async=true für /oak:index/damAssetLucene) gleichzeitig über den Speichervorgang aktualisiert werden.


**Übergeordnetes Thema:** [Herunterladen und installieren](download-install.md)
