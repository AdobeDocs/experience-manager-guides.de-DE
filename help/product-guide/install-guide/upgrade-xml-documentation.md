---
title: Adobe Experience Manager Guides aktualisieren
description: Erfahren Sie, wie Sie Adobe Experience Manager Guides aktualisieren
exl-id: f058b39f-7408-4874-942b-693e133886cf
feature: Installation
role: Admin
level: Experienced
source-git-commit: 5e02c3bdecda68dfcaac225626a2a47e4af5f30f
workflow-type: tm+mt
source-wordcount: '6943'
ht-degree: 0%

---

# Adobe Experience Manager Guides aktualisieren {#id224MBE0M0XA}

>[!NOTE]
>
> Befolgen Sie die Upgrade-Anweisungen für die lizenzierte Version Ihres Produkts.

Sie können Ihre aktuelle Version von Experience Manager Guides auf Version 4.6.0 aktualisieren:


- Wenn Sie Version 4.4, 4.3.1 oder 4.3.0 verwenden, können Sie direkt auf Version 4.6.0 aktualisieren.
- Wenn Sie Version 4.2, 4.2.1 (Hotfix 4.2.1.3), 4.1 oder 4.1.x verwenden, müssen Sie auf Version 4.4 aktualisieren, bevor Sie auf Version 4.6.0 aktualisieren.
- Wenn Sie Version 4.0 verwenden, müssen Sie auf Version 4.2 aktualisieren, bevor Sie auf Version 4.3.x aktualisieren.
- Wenn Sie Version 3.8.5 verwenden, müssen Sie auf Version 4.0 aktualisieren, bevor Sie auf Version 4.2 aktualisieren.
- Wenn Sie eine Version vor 3.8.5 verwenden, lesen Sie den Abschnitt &quot;Aktualisieren von Experience Manager Guides&quot;im produktspezifischen Installationshandbuch, das im [Adobe Experience Manager Guides-PDF-Archiv](https://helpx.adobe.com/xml-documentation-for-experience-manager/archive.html) verfügbar ist.


>[!NOTE]
>
> Sie müssen AEM Service Pack installieren, bevor Sie die Experience Manager Guides-Version aktualisieren.

Weitere Informationen finden Sie in den folgenden Verfahren:

- [Upgrade von 3.8.5 auf Version 4.0](#id2256DK003E1)
- [Upgrade auf Version 4.2](#id22A3F500SXA)
- [Upgrade auf Version 4.2.1](#upgrade-version-4-2-1)
- [Upgrade auf Version 4.3.0](#upgrade-version-4-3)
- [Upgrade auf Version 4.3.1](#upgrade-version-4-3-1)
- [Upgrade auf Version 4.3.1.5](#upgrade-version-4-3-1-5)
- [Upgrade auf Version 4.4.0](#upgrade-version-4-4-0)
- [Upgrade auf Version 4.6.0](#upgrade-version-4-6-0)



>[!IMPORTANT]
>
> Bevor Sie mit der Aktualisierung beginnen, führen Sie eine vollständige Systemsicherung durch, um Datenverlust zu vermeiden.

## Upgrade von Version 3.8.5 auf Version 4.0 {#id2256DK003E1}

Wenn Sie Experience Manager Guides Version 3.8.5 verwenden, können Sie auf Version 4.0 von Experience Manager Guides aktualisieren. Mit der Upgrade-Funktion müssen Sie die vorherige Version von Experience Manager Guides nicht deinstallieren.

Bevor Sie den Prozess ausführen, müssen Sie bestimmte Aufgaben ausführen. In den folgenden Unterabschnitten werden Sie durch die Voraussetzungen, die Berichterstellung und den Migrationsprozess geführt. Außerdem können Sie nach der Installation von Experience Manager Guides Version 4.0 verschiedene Konfigurationen entsprechend den Kundeneinstellungen anpassen.

>[!NOTE]
>
> Dieser Aktualisierungsprozess gilt nur von Version 3.8.5 auf Version 4.0. Informationen zum Upgrade von Version 3.4 oder höher auf Version 3.8.5 finden Sie im Abschnitt *Aktualisieren von Experience Manager Guides* im produktspezifischen Installationshandbuch, das auf dem [Adobe Experience Manager Guides-PDF-Archiv](https://helpx.adobe.com/xml-documentation-for-experience-manager/archive.html) verfügbar ist.



****Voraussetzungen****

Bevor Sie mit dem Experience Manager Guides-Upgrade-Prozess beginnen, stellen Sie Folgendes sicher:

1. Die Überprüfungskommentare wurden in Themen importiert, die zur Überprüfung geöffnet sind.
1. Alle aktiven Rezensionen wurden geschlossen.
1. Alle Übersetzungsaufgaben wurden geschlossen.
1. Deinstallieren Sie alle Experience Manager Guides-Hotfixes, die auf der vorherigen Version von Experience Manager Guides installiert sind (Haupt- oder Patch-Version\).

**Vor der Installation von Version 4.0**

Führen Sie vor der Installation von Version 4.0 die folgenden Schritte aus:

1. Stellen Sie an dieser Stelle sicher, dass Experience Manager Guides auf Version 3.8.5 ist.
1. Laden Sie das Aktualisierungsskript-Paket herunter. Suchen Sie dazu auf dem [Adobe Software Distribution Portal](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html) nach &quot;XML Documentation solution 4.0 Upgrade Package&quot;, das eine ZIP-Datei herunterlädt.
1. Laden Sie dieses Paket über Package Manager in AEM hoch und installieren Sie es.
1. Nachdem das Upgrade-Paket installiert wurde, führen Sie die folgenden angegebenen Skripte in derselben Reihenfolge aus und befolgen Sie die angegebenen Anweisungen:

**Überprüfen Sie die Upgrade-Kompatibilitäts-API**

Diese API dient dazu, den aktuellen Systemstatus zu bewerten und darüber zu berichten, ob eine Aktualisierung möglich ist oder nicht. Um dieses Skript auszuführen, geben Sie den folgenden angegebenen Endpunkt ein:

| Endpunkt | /bin/dxml/upgrade/3xto4x/report |
| --- | --- |
| Abfragetyp | **GET** Sie können einen Webbrowser verwenden, in dem Sie als Administrator bei der AEM-Instanz angemeldet sind. |
| Erwartete Antwort | -   Falls alle erforderlichen Knoten verschoben werden können, erhalten Sie eine übergebene Prüfung. <br>-   Wenn sich ein Knoten am Zielspeicherort befindet, wird ein relevanter Fehler ausgegeben. Bereinigen Sie das Repository \(Löschen-Knoten /var/dxml\), installieren Sie das Aktualisierungspaket neu und führen Sie dann erneut einen Trigger für diesen Endpunkt durch. <br>**Hinweis:** Dies ist kein häufiger Fehler, da der Zielspeicherort von 3.x Experience Manager Guides nicht früher verwendet wird. <br> -   Wenn dieses Skript nicht erfolgreich ist, fahren Sie nicht fort und melden Sie es Ihrem Kundenerfolgsteam. |

**Systemdatenmigration-API**

Diese API wurde entwickelt, um die Systemdaten zu migrieren, wie im Abschnitt **Migrationszuordnung** beschrieben.

1. Führen Sie dieses Skript nicht aus, wenn die API zur Prüfung der Upgrade-Kompatibilität fehlschlägt \(fahren Sie nicht fort\).
1. Sobald die API zur Prüfung der Upgrade-Kompatibilität erfolgreich ist, können Sie das Aktualisierungsskript ausführen.

| Endpunkt | /bin/dxml/upgrade/3xto4x |
| --- | --- |
| Abfragetyp | **POST** Dieses Skript ist eine POST-Anfrage. Daher sollte es über Agenten wie Postman ausgeführt werden. |
| Erwartete Antwort | -   Nach erfolgreicher Migration können Sie die XML Documentation-Lösungsversion 4.0 installieren.<br>-   Wenn Fehler auftreten, stellen Sie den letzten Checkpoint wieder her und geben Sie die Fehlerprotokolle zusammen mit der API-Ausgabe für Ihr Customer Success Team frei. |

**Migrationszuordnung**: Die oben genannte API migriert alle Daten unter dem Quellspeicherort zum Zielspeicherort.

| Quelle | Target |
|------|------|
| /content/fmdita | /var/dxml |
| /content/dxml | /var/dxml |
| /etc/fmdita | /libs/fmdita |

## Installieren Sie Version 4.0 {#id23598G006XA}

1. Installieren Sie Version 4.0 nur, wenn die Aktualisierungsschritte erfolgreich waren.
1. Laden Sie das 4.0-Versionspaket vom [Adobe Software Distribution-Portal](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html) herunter:

   - Wenn Sie die UUID-Version der Software verwenden, suchen Sie nach &quot;4.0 UUID Release for XML Documentation solution for AEM 6.5&quot;.
   - Wenn Sie die Nicht-UUID-Version der Software verwenden, suchen Sie nach &quot;4.0 Non-UUID Release for XML Documentation solution for AEM 6.5&quot;.
Laden Sie das Paket mithilfe von CRX Package Manager in die vorhandene AEM-Serverinstanz hoch und installieren Sie es.

   >[!NOTE]
   >
   > Warten Sie, bis alle Systemkomponenten gestartet sind.

1. Löschen Sie den Browser-Cache nach der Installation des Pakets.
1. Wenn ein Dispatcher in AEM -Autoreninstanz konfiguriert ist, führen Sie die folgenden Schritte aus:
   - Stellen Sie sicher, dass Folgendes in Dispatcher-Regeln verarbeitet wird:
   - Das URL-Muster /home/users/\*/Preferences ist auf der Whitelist.
   - Das URL-Muster /libs/cq/security/userinfo.json wird nicht zwischengespeichert.
1. Löschen Sie den Dispatcher-Cache \(um alle im Cache gespeicherten `clientlibs` zu löschen\).

## Upgrade auf Version 4.2 {#id22A3F500SXA}

Die Aktualisierung auf Version 4.2 hängt von der aktuellen Version von Experience Manager Guides ab.

Wenn Sie Version 4.0, 4.1 oder 4.1.x verwenden, können Sie direkt auf Version 4.2 aktualisieren.

****Voraussetzungen****

Bevor Sie mit dem Upgrade-Prozess für Experience Manager Guides 4.2 beginnen, stellen Sie Folgendes sicher:

1. Aktualisierung auf Experience Manager Guides-Versionen 4.0, 4.1 oder 4.1.x.
1. Alle Übersetzungsaufgaben wurden geschlossen.
1. Die Protokollebene für die `com.adobe.fmdita.translationservices.TranslationMapUpgradeScript` -Klasse wurde zu **INFO** geändert und diese Protokolle werden in eine neue Protokolldatei angehängt, z. B. `logs/translation_upgrade.log.`

>[!NOTE]
>
> Sie sollten alle aktiven Rezensionen schließen. Wenn die Prüfungsaufgaben beim Upgrade auf Version 4.2 nicht abgeschlossen werden, nehmen die älteren laufenden Prüfungsaufgaben weiterhin Benutzer auf den älteren Prüfungsseiten auf und die nach dem Upgrade erstellten Prüfungsaufgaben zeigen die neuesten Funktionsaktualisierungen an.

## Installieren Sie Version 4.2 {#id2245IK0E0EV}

1. Laden Sie das 4.2-Versionspaket vom [Adobe Software Distribution-Portal](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html) herunter.
1. Installieren Sie das Paket der Version 4.2.
1. Warten Sie nach Abschluss der Paketinstallation auf die folgende(n) Meldung(en\) in den Protokollen:

   `Completed the post deployment setup script`

   Die obige Meldung weist darauf hin, dass alle Installationsschritte abgeschlossen sind.

   Sollten Sie auf eines der folgenden FEHLER-Präfixe stoßen, melden Sie diese Ihrem Kundenerfolgsteam:

   - Fehler beim Setup-Skript nach der Bereitstellung
   - Ausnahme beim Importieren der Übersetzungs-MAP
   - Die Übersetzungszuordnung kann nicht von v1 auf v2 für die Eigenschaft portiert werden
1. Aktualisieren Sie das Oxygen Connector-Plugin, das mit Version 4.2 veröffentlicht wurde \(falls erforderlich\).
1. Löschen Sie den Browser-Cache nach der Installation des Pakets.
1. Fahren Sie mit der Aktualisierung der Anpassungen fort, wie im nächsten Abschnitt beschrieben.

## Nach der Installation von Version 4.2 {#id2326F02004K}

>[!IMPORTANT]
>
> Die Hi-Tech-Vorlage wird auf dem aktualisierten Server nicht angezeigt. Um die Hi-Tech-Vorlage auf Ihren Server einzufügen, können Sie sie kopieren: Source: /libs/fmdita/pdf/Hi-Tech Destination: /content/dam/dita-templates/pdf

Nach der Installation von Experience Manager Guides können Sie die verschiedenen Konfigurationen zusammenführen, die von der neu installierten Version zu Ihrem Setup gehören.

>[!NOTE]
>
> Das Modell dam-update-asset kann angepasst werden. Wenn also Anpassungen vorgenommen wurden, müssen wir die Anpassungen und Experience Manager Guides mit der Arbeitskopie des Modells synchronisieren.

1. **DAM-Update-Asset-Workflow \(Nachbearbeitungs-Änderungen\):**

1. URL öffnen:

   ```http
   http://localhost:4502/libs/cq/workflow/admin/console/content/models.html
   ```

1. Wählen Sie **DAM-Update-Asset-Workflow** aus.
1. Klicken Sie auf **Bearbeiten**.
1. Wenn die Komponente **DXML Post Process Initiator** vorhanden ist, stellen Sie sicher, dass die Anpassungen synchronisiert werden.
1. Wenn die Komponente **DXML Post Process Initiator** fehlt, führen Sie die folgenden Schritte aus, um sie einzufügen:

1. Klicken Sie auf **Komponente einfügen** \(verantwortlich für die Experience Manager Guides-Nachbearbeitung als letzten Schritt im Prozess\).
1. Konfigurieren Sie den **Prozessschritt** mit den folgenden Details:

   **Registerkarte &quot;Allgemein&quot;**

   **Titel:** DXML-Nachbearbeitungs-Initiator

   **Beschreibung**: DXML-Nachbearbeitungs-Initiatorschritt, der einen Sling-Auftrag für die DXML-Nachbearbeitung des geänderten/erstellten Assets Trigger

   **Registerkarte &quot;Prozess&quot;**

   - Wählen Sie **DXML Post Process Initiator** aus der Dropdown-Liste **Process** aus.

   - Wählen Sie **Handler-Modus** aus

   - Wählen Sie **Fertig** aus

1. Klicken Sie oben rechts nach Abschluss der Änderungen auf **Synchronisieren** . Sie erhalten eine Erfolgsbenachrichtigung.

   >[!NOTE]
   >
   > Aktualisieren Sie und überprüfen Sie, ob benutzerdefinierte Änderungen und der Experience Manager Guides-Anschlussvorgang im endgültigen Workflow-Modell vorhanden sind.

1. Nachdem der Workflow **DAM-Update-Asset** validiert wurde, überprüfen Sie die entsprechenden Starter-Konfigurationen. Gehen Sie dazu zur Workflow-Oberfläche AEM und öffnen Sie Starter.

   ```http
   http://localhost:4502/libs/cq/workflow/content/console.html
   ```

   Suchen Sie nach den folgenden beiden Startern \(die aktiv sein sollten\), die **DAM Update Asset Workflow** entsprechen, und nehmen Sie Änderungen vor \(falls erforderlich\):

1. Starter für &quot;*Knoten erstellt*&quot;für **DAM-Update-Asset-Workflow** - für Bedingung `"jcr:content/jcr:mimeType!=video"` sollte der Wert &quot;Globbing&quot;wie folgt lauten:

   ```json
   /content/dam(/((?!/subassets|/translation_output).)*/)renditions/original
   ```

   - &#39;excludeList&#39; sollte `"event-user-data:changedByWorkflowProcess"` aufweisen.
   - Starter für &quot;*Node Modified*&quot; für **DAM Update Asset Workflow -** für Bedingung &quot;`jcr:content/jcr:mimeType!=video`&quot;,
   - Der Wert &quot;Globbing&quot;sollte wie folgt lauten:

   ```json
   /content/dam(/((?!/subassets|/translation_output).)*/)renditions/original
   ```

   - &#39;excludeList&#39; sollte `"event-user-data:changedByWorkflowProcess"` aufweisen.
1. Nachdem das Upgrade abgeschlossen ist, stellen Sie sicher, dass alle Anpassungen/Überlagerungen validiert und aktualisiert wurden, um dem neuen Anwendungscode zu entsprechen. Nachfolgend finden Sie einige Beispiele:
   - Alle aus /libs/fmditaor/libsüberlagerten Komponenten sollten mit dem neuen Produktcode verglichen werden und Aktualisierungen sollten in überlagerten Dateien unter/apps vorgenommen werden.
   - Alle clientlib-Kategorien, die vom Produkt verwendet werden, sollten auf Änderungen überprüft werden. Alle überschriebenen Konfigurationen \(Beispiele unten\) sollten mit den neuesten verglichen werden, um die neuesten Funktionen zu erhalten:
   - elementmapping.xml
   - ui\_config.json\(möglicherweise in Ordnerprofilen festgelegt\)
   - geänderte `com.adobe.fmdita.config.ConfigManager`
   - Überprüfen Sie, ob der benutzerspezifische Code alte Pfade verwendet hat \(wie im Abschnitt [Migrationszuordnung](#id2244LE040XA) erwähnt), und sollten auf die neuen Pfade aktualisiert werden, damit die Anpassungen auch wie erwartet funktionieren.
1. Informieren Sie sich über alle neuen Konfigurationen, die in der aktuellen Version vorgenommen wurden \(überprüfen Sie [Versionshinweise](../release-info/release-notes-4-3.md)\), überprüfen Sie, ob irgendwelche Funktionen betroffen sind, und ergreifen Sie geeignete Maßnahmen. Ein Beispiel könnte die Verwendung der in Version 4.0 eingeführten &quot;verbesserten Handhabung von Dateien und Versionen&quot; sein, für die Sie eine Konfiguration aktivieren müssen.

## Schritte zum Indexieren des vorhandenen Inhalts, um das neue Suchen und Ersetzen zu verwenden:

Führen Sie die folgenden Schritte für die Indizierung des vorhandenen Inhalts aus und verwenden Sie den neuen Suchen- und Ersetzen-Text auf Zuordnungsebene:

- Führen Sie eine POST-Anfrage an den Server aus \(mit korrekter Authentifizierung\) - `http://<server:port\>/bin/guides/map-find/indexing`. \(Optional: Sie können bestimmte Pfade der Maps übergeben, um sie zu indizieren. Standardmäßig werden alle Maps indiziert \|\| Beispiel: `https://<Server:port\>/bin/guides/map-find/indexing?paths=<map\_path\_in\_repository\>`\)

- Die API gibt eine jobId zurück. Um den Status des Auftrags zu überprüfen, können Sie eine GET-Anfrage mit Auftrags-ID an denselben Endpunkt senden -

`http://<server:port\>/bin/guides/map-find/indexing?jobId=\{jobId\}`\(Beispiel: `http://localhost:8080/bin/guides/map-find/indexing?jobId=2022/9/15/7/27/7dfa1271-981e-4617-b5a4-c18379f11c42`\)

- Nach Abschluss des Auftrags antwortet die obige GET-Anfrage mit Erfolg und gibt an, ob Zuordnungen fehlgeschlagen sind. Die erfolgreich indizierten Maps können über die Serverprotokolle bestätigt werden.

Wenn der Aktualisierungsauftrag fehlschlägt und das Fehlerprotokoll den folgenden Fehler anzeigt:

&quot;Die *Abfrage* hat mehr als *10000 Knoten* gelesen oder durchlaufen. Um andere Aufgaben nicht zu beeinträchtigen, wurde die Verarbeitung angehalten.&quot;

Dies kann vorkommen, da der Index für die bei der Aktualisierung verwendete Abfrage nicht ordnungsgemäß eingerichtet ist. Sie können die folgende Problemumgehung ausprobieren:

1. Fügen Sie im oak-Index damAssetLucene die boolesche Eigenschaft `indexNodeName` als `true` im Knoten hinzu.
   `/oak:index/damAssetLucene/indexRules/dam:Asset`
1. Fügen Sie einen neuen Knoten mit dem Namensausschnitt unter dem Knoten hinzu.

   `/oak:index/damAssetLucene/indexRules/dam:Asset/properties`
und legen Sie die folgenden Eigenschaften im Knoten fest:

   ```
   name - rep:excerpt
   propertyIndex - {Boolean}true
   notNullCheckEnabled - {Boolean}true
   ```

   Die Struktur von `damAssetLucene` sollte ungefähr so aussehen:

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

1. Neuindizieren des `damAssetLucene` -Index (indem Sie die Neuindizierungskennzeichnung als `true` unter festlegen
und warten Sie, bis es wieder `false` ist (dies zeigt an, dass die Neuindizierung abgeschlossen ist). Beachten Sie, dass es je nach Größe des Index einige Stunden dauern kann.
1. Führen Sie das Indizierungsskript erneut aus, indem Sie die vorherigen Schritte ausführen.


## Upgrade auf Version 4.2.1 {#upgrade-version-4-2-1}

>[!TIP]
>
>Es wird empfohlen, Hotfix 4.2.1.3 zusätzlich zu Version 4.2.1 zu installieren.

Die Aktualisierung auf Version 4.2.1 hängt von der aktuellen Version von Experience Manager Guides ab. Wenn Sie Version 4.1, 4.1.x oder 4.2 verwenden, können Sie direkt auf Version 4.2.1 aktualisieren.

>[!NOTE]
>
>Die Nachbearbeitung und Indizierung kann einige Stunden dauern. Es wird empfohlen, den Aktualisierungsprozess außerhalb der Spitzenzeiten zu starten.

****Voraussetzungen****

Bevor Sie mit dem Upgrade-Prozess für Experience Manager Guides 4.2.1 beginnen, stellen Sie Folgendes sicher:

1. Aktualisierung auf Experience Manager Guides-Version 4.1, 4.1.x oder 4.2.
1. Alle Übersetzungsaufgaben wurden geschlossen.
1. Die Protokollebene für die `com.adobe.fmdita.translationservices.TranslationMapUpgradeScript` -Klasse wurde zu **INFO** geändert und diese Protokolle werden in eine neue Protokolldatei angehängt, z. B. `logs/translation_upgrade.log.`

>[!NOTE]
>
> Sie sollten alle aktiven Rezensionen schließen. Wenn die Prüfungsaufgaben beim Upgrade auf Version 4.2 nicht abgeschlossen werden, nehmen die älteren laufenden Prüfungsaufgaben weiterhin Benutzer auf den älteren Prüfungsseiten auf und die nach dem Upgrade erstellten Prüfungsaufgaben zeigen die neuesten Funktionsaktualisierungen an.

## Installieren Sie Version 4.2.1

1. Laden Sie das 4.2.1-Versionspaket vom [Adobe Software Distribution-Portal](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html) herunter.
1. Installieren Sie das Paket der Version 4.2.1.
1. Sie können den Trigger drücken, um den Aktualisierungsauftrag für die Übersetzungskarte zu starten. Weitere Informationen finden Sie unter [Aktivieren des Skript-Triggers über ein Servlet](#enable-trigger-serverlet).


1. Warten Sie nach Abschluss der Paketinstallation auf die folgende(n) Meldung(en\) in den Protokollen:

   `Completed the post deployment setup script`

   Die obige Meldung weist darauf hin, dass alle Installationsschritte abgeschlossen sind.

   Sollten Sie auf eines der folgenden FEHLER-Präfixe stoßen, melden Sie diese Ihrem Kundenerfolgsteam:

   - Fehler beim Setup-Skript nach der Bereitstellung
   - Ausnahme beim Importieren der Übersetzungs-MAP
   - Die Übersetzungszuordnung kann nicht von v1 auf v2 für die Eigenschaft portiert werden
1. Aktualisieren Sie das Oxygen Connector-Plugin, das mit Version 4.2 veröffentlicht wurde \(falls erforderlich\).
1. Löschen Sie den Browser-Cache nach der Installation des Pakets.
1. Fahren Sie mit der Aktualisierung der Anpassungen fort, wie im nächsten Abschnitt beschrieben.

### Aktivieren des Triggers eines Skripts über ein Servlet{#enable-trigger-serverlet}

POST:

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

In der obigen Antwort-JSON enthält der Schlüssel `lockNodePath` den Pfad zum Knoten, der im Repository erstellt wurde und auf den gesendeten Auftrag verweist. Er wird automatisch gelöscht, sobald der Auftrag abgeschlossen ist. Bis dahin können Sie den aktuellen Status des Auftrags in diesem Knoten nachlesen.

Beispielprotokoll:
Im Folgenden finden Sie ein Beispiel von Protokollen, die in der Protokolldatei angezeigt werden, nachdem Sie das Skript Trigger haben.

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

Suchen Sie nach `com.adobe.fmdita.translationservices.TranslationMapUpgradeScript Completed porting of translation map from V1 to V2` und `com.adobe.fmdita.xmltranslation.ots.TranslationMapUpgradeOTS Completed the thread to upgrade translation map from V1 to V2` , bevor Sie mit den nächsten Schritten fortfahren.



## Nach der Installation von Version 4.2.1

>[!IMPORTANT]
>
> Die Hi-Tech-Vorlage wird auf dem aktualisierten Server nicht angezeigt. Um die Hi-Tech-Vorlage auf Ihren Server einzufügen, können Sie sie kopieren: Source: /libs/fmdita/pdf/Hi-Tech Destination: /content/dam/dita-templates/pdf

Nach der Installation von Experience Manager Guides können Sie die verschiedenen Konfigurationen zusammenführen, die von der neu installierten Version zu Ihrem Setup gehören.

>[!NOTE]
>
> Das Modell dam-update-asset kann angepasst werden. Wenn also Anpassungen vorgenommen wurden, müssen wir die Anpassungen und Experience Manager Guides mit der Arbeitskopie des Modells synchronisieren.

1. **DAM-Update-Asset-Workflow \(Nachbearbeitungs-Änderungen\):**

1. URL öffnen:

   ```http
   http://localhost:4502/libs/cq/workflow/admin/console/content/models.html
   ```

1. Wählen Sie **DAM-Update-Asset-Workflow** aus.
1. Klicken Sie auf **Bearbeiten**.
1. Wenn die Komponente **DXML Post Process Initiator** vorhanden ist, stellen Sie sicher, dass die Anpassungen synchronisiert werden.
1. Wenn die Komponente **DXML Post Process Initiator** fehlt, führen Sie die folgenden Schritte aus, um sie einzufügen:

1. Klicken Sie auf **Komponente einfügen** \(verantwortlich für die Experience Manager Guides-Nachbearbeitung als letzten Schritt im Prozess\).
1. Konfigurieren Sie den **Prozessschritt** mit den folgenden Details:

   **Registerkarte &quot;Allgemein&quot;**

   **Titel:** DXML-Nachbearbeitungs-Initiator

   **Beschreibung**: DXML-Nachbearbeitungs-Initiatorschritt, der einen Sling-Auftrag für die DXML-Nachbearbeitung des geänderten/erstellten Assets Trigger

   **Registerkarte &quot;Prozess&quot;**

   - Wählen Sie **DXML Post Process Initiator** aus der Dropdown-Liste **Process** aus.

   - Wählen Sie **Handler-Modus** aus

   - Wählen Sie **Fertig** aus

1. Klicken Sie oben rechts nach Abschluss der Änderungen auf **Synchronisieren** . Sie erhalten eine Erfolgsbenachrichtigung.

   >[!NOTE]
   >
   > Aktualisieren Sie und überprüfen Sie, ob benutzerdefinierte Änderungen und der Experience Manager Guides-Anschlussvorgang im endgültigen Workflow-Modell vorhanden sind.

1. Nachdem der Workflow **DAM-Update-Asset** validiert wurde, überprüfen Sie die entsprechenden Starter-Konfigurationen. Gehen Sie dazu zur Workflow-Oberfläche AEM und öffnen Sie Starter.

   ```http
   http://localhost:4502/libs/cq/workflow/content/console.html
   ```

   Suchen Sie nach den folgenden beiden Startern \(die aktiv sein sollten\), die **DAM Update Asset Workflow** entsprechen, und nehmen Sie Änderungen vor \(falls erforderlich\):

1. Starter für &quot;*Knoten erstellt*&quot;für **DAM-Update-Asset-Workflow** - für Bedingung `"jcr:content/jcr:mimeType!=video"` sollte der Wert &quot;Globbing&quot;wie folgt lauten:

   ```json
   /content/dam(/((?!/subassets|/translation_output).)*/)renditions/original
   ```

   - &#39;excludeList&#39; sollte `"event-user-data:changedByWorkflowProcess"` aufweisen.
   - Der Starter für &quot;*Node Modified*&quot;für **DAM Update Asset Workflow -** für Bedingung &quot;`jcr:content/jcr:mimeType!=video`&quot;, sollte der Wert &quot;Globbing&quot;lauten:

   ```json
   /content/dam(/((?!/subassets|/translation_output).)*/)renditions/original
   ```

   - `excludeList` sollte `"event-user-data:changedByWorkflowProcess"` haben.

1. Nachdem das Upgrade abgeschlossen ist, stellen Sie sicher, dass alle Anpassungen/Überlagerungen validiert und aktualisiert wurden, um dem neuen Anwendungscode zu entsprechen. Nachfolgend finden Sie einige Beispiele:
   - Alle aus /libs/fmditaor/libsüberlagerten Komponenten sollten mit dem neuen Produktcode verglichen werden und Aktualisierungen sollten in überlagerten Dateien unter/apps vorgenommen werden.
   - Alle clientlib-Kategorien, die vom Produkt verwendet werden, sollten auf Änderungen überprüft werden. Alle überschriebenen Konfigurationen \(Beispiele unten\) sollten mit den neuesten verglichen werden, um die neuesten Funktionen zu erhalten:
   - elementmapping.xml
   - ui\_config.json\(möglicherweise in Ordnerprofilen festgelegt\)
   - geänderte `com.adobe.fmdita.config.ConfigManager`
   - Überprüfen Sie, ob der benutzerspezifische Code alte Pfade verwendet hat \(wie im Abschnitt [Migrationszuordnung](#id2244LE040XA) erwähnt), und sollten auf die neuen Pfade aktualisiert werden, damit die Anpassungen auch wie erwartet funktionieren.
1. Informieren Sie sich über alle neuen Konfigurationen, die in der aktuellen Version vorgenommen wurden \(überprüfen Sie [Versionshinweise](../release-info/release-notes-4-2-1.md)\), überprüfen Sie, ob irgendwelche Funktionen betroffen sind, und ergreifen Sie geeignete Maßnahmen. Ein Beispiel könnte die Verwendung der in Version 4.0 eingeführten &quot;verbesserten Handhabung von Dateien und Versionen&quot; sein, für die Sie eine Konfiguration aktivieren müssen.

## Schritte zum Indexieren des vorhandenen Inhalts, um das neue Suchen und Ersetzen zu verwenden:

Führen Sie die folgenden Schritte für die Indizierung des vorhandenen Inhalts aus und verwenden Sie den neuen Suchen- und Ersetzen-Text auf Zuordnungsebene:

- Stellen Sie sicher, dass die `damAssetLucene` -Indizierung abgeschlossen ist. Je nach der auf dem Server vorhandenen Datenmenge kann es bis zu einigen Stunden dauern. Sie können bestätigen, dass die Neuindizierung abgeschlossen ist, indem Sie überprüfen, ob das Neuindizierungsfeld in
  `http://<server:port>/oak:index/damAssetLucene`.  Wenn Sie in `damAssetLucene` Anpassungen hinzugefügt haben, müssen Sie diese möglicherweise erneut anwenden.

- Führen Sie eine POST-Anfrage an den Server aus \(mit korrekter Authentifizierung\) - `http://<server:port\>/bin/guides/map-find/indexing`. (Optional: Sie können bestimmte Pfade der Maps übergeben, um sie zu indizieren. Standardmäßig werden alle Maps indiziert \|\| Beispiel: `https://<Server:port\>/bin/guides/map-find/indexing?paths=<map\_path\_in\_repository\>`)

- Sie können auch einen Stammordner übergeben, um die DITA-Maps eines bestimmten Ordners (und seiner Unterordner) zu indizieren. Beispiel: `http://<server:port\>/bin/guides/map-find/indexing?root=/content/dam/test`. Beachten Sie, dass nur der Pfadparameter berücksichtigt wird, wenn sowohl der Pfadparameter als auch der Stammparameter übergeben werden.

- Die API gibt eine jobId zurück. Um den Auftragsstatus zu überprüfen, können Sie eine GET-Anfrage mit Auftrags-ID an denselben Endpunkt senden - `http://<server:port\>/bin/guides/map-find/indexing?jobId=\{jobId\}`\(z. B. `http://localhost:8080/bin/guides/map-find/indexing?jobId=2022/9/15/7/27/7dfa1271-981e-4617-b5a4-c18379f11c42`\)


- Nach Abschluss des Auftrags antwortet die obige GET-Anfrage mit Erfolg und gibt an, ob Zuordnungen fehlgeschlagen sind. Die erfolgreich indizierten Maps können über die Serverprotokolle bestätigt werden.


## Upgrade auf Version 4.3.0 {#upgrade-version-4-3}

Die Aktualisierung auf Version 4.3.0 hängt von der aktuellen Version von Experience Manager Guides ab. Wenn Sie Version 4.2 oder 4.2.x verwenden, können Sie direkt auf Version 4.3.0 aktualisieren.

>[!NOTE]
>
>Die Nachbearbeitung und Indizierung kann einige Stunden dauern. Es wird empfohlen, den Aktualisierungsprozess außerhalb der Spitzenzeiten zu starten.

****Voraussetzungen****

Bevor Sie mit dem Upgrade-Prozess für Experience Manager Guides 4.3.0 beginnen, stellen Sie Folgendes sicher:

1. Aktualisierung auf Experience Manager Guides-Version 4.2 oder 4.2.x und Abschluss des jeweiligen Installationsschritts.
1. Alle Übersetzungsaufgaben wurden geschlossen.



## Installieren Sie Version 4.3.0

1. Laden Sie das 4.3.0-Versionspaket vom [Adobe Software Distribution-Portal](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html) herunter.
1. Installieren Sie das Paket Version 4.3.0 .
1. Löschen Sie den Browser-Cache nach der Installation des Pakets.
1. Aktualisieren Sie die Datei &quot;`ui_config.json`&quot;auf der Registerkarte &quot;**XML-Editor-Konfiguration**&quot;im Ordnerprofil.


## Nach der Installation von Version 4.3.0

Nach der Installation von Experience Manager Guides können Sie die verschiedenen Konfigurationen zusammenführen, die von der neu installierten Version zu Ihrem Setup gehören.

## Schritte zum Nachbearbeiten des vorhandenen Inhalts zur Verwendung des Berichts über einen fehlerhaften Link


Führen Sie die folgenden Schritte aus, um den vorhandenen Inhalt nachzubearbeiten und den neuen Bericht zu fehlerhaften Links zu verwenden:

1. (Optional) Wenn mehr als 100.000 Datendateien im System vorhanden sind, aktualisieren Sie den `queryLimitReads` unter `org.apache.jackrabbit.oak.query.QueryEngineSettingsService` auf einen größeren Wert (ein beliebiger Wert, der größer ist als die Anzahl der vorhandenen Assets, z. B. 200.000), und stellen Sie dann erneut bereit.

   | PID | Eigenschaftenschlüssel | Eigenschaftswert |
   |---|---|---|
   | org.apache.jackrabbit.oak.query.QueryEngineSettingsService | queryLimitReads | Wert: 200000 <br> Standardwert: 10000 |

1. Führen Sie die folgenden APIs aus, um die Nachbearbeitung für alle Dateien auszuführen:

   | Endpunkt | /bin/guides/reports/upgrade |
   |---|---|
   | Abfragetyp | **POST** Dieses Skript ist eine POST-Anfrage. Daher sollte es über Agenten wie Postman ausgeführt werden. |
   | Erwartete Antwort | Die API gibt eine jobId zurück. Um den Auftragsstatus zu überprüfen, können Sie eine GET-Anfrage mit Auftrags-ID an denselben Endpunkt senden.<br> Beispiel-URL: `http://<server:port>/bin/guides/reports/upgrade` |

   | Endpunkt | /bin/guides/reports/upgrade |
   |---|---|
   | Abfragetyp | **GET** |
   | Parameter | jobId: Übergeben Sie die jobId, die von der vorherigen POST-Anfrage empfangen wurde. |
   | Erwartete Antwort | - Nach Abschluss des Auftrags antwortet die GET-Anfrage erfolgreich. <br> - Im Fall von Fehlern sollten Sie die Fehlerprotokolle zusammen mit der API-Ausgabe für Ihr Customer Success Team freigeben.  <br>Beispiel-URL: `http://<server:port>/bin/guides/reports/upgrade?jobId=2022/9/15/7/27/7dfa1271-981e-4617-b5a4-c18379f11c42_678` |


1. Kehren Sie zurück zum standardmäßigen oder vorherigen vorhandenen Wert von `queryLimitReads` zurück, wenn Sie ihn in Schritt 1 geändert haben.



## Upgrade auf Version 4.3.1 {#upgrade-version-4-3-1}

Die Aktualisierung auf Version 4.3.1 hängt von der aktuellen Version von Experience Manager Guides ab. Wenn Sie Version 4.3.0, 4.2 oder 4.2.1 verwenden, können Sie direkt auf Version 4.3.1 aktualisieren.

>[!NOTE]
>
>Die Nachbearbeitung und Indizierung kann einige Stunden dauern. Es wird empfohlen, den Aktualisierungsprozess außerhalb der Spitzenzeiten zu starten.

****Voraussetzungen****

Bevor Sie mit dem Upgrade-Prozess für Experience Manager Guides 4.3.1 beginnen, stellen Sie Folgendes sicher:

1. Aktualisierung auf Experience Manager Guides-Version 4.3.0, 4.2 oder 4.2.1 und Abschluss des jeweiligen Installationsschritts.
1. (Optional) Alle Übersetzungsaufgaben wurden geschlossen.
1. Die Protokollebene für die Klasse `com.adobe.fmdita.translationservices.TranslationMapUpgradeScript` wurde zu **INFO** geändert und diese Protokolle werden an eine neue Protokolldatei angehängt, z. B. `logs/translation_upgrade.log`.


## Installieren Sie Version 4.3.1

1. Laden Sie das 4.3.1-Versionspaket vom [Adobe Software Distribution-Portal](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html) herunter.
1. Installieren Sie das Paket der Version 4.3.1.
1. Sie können den Trigger drücken, um den Aktualisierungsauftrag für die Übersetzungskarte zu starten. Weitere Informationen finden Sie unter [Aktivieren des Skript-Triggers über ein Servlet](#enable-trigger-serverlet-4-3-1).


1. Warten Sie nach Abschluss der Paketinstallation auf die folgende(n) Meldung(en\) in den Protokollen:

   `Completed the post deployment setup script`

   Die obige Meldung weist darauf hin, dass alle Installationsschritte abgeschlossen sind.

   Sollten Sie auf eines der folgenden FEHLER-Präfixe stoßen, melden Sie diese Ihrem Kundenerfolgsteam:

   - Fehler beim Setup-Skript nach der Bereitstellung
   - Ausnahme beim Importieren der Übersetzungs-MAP
   - Die Übersetzungszuordnung kann nicht von v1 auf v2 für die Eigenschaft portiert werden
1. Aktualisieren Sie das Oxygen Connector-Plugin, das mit Version 4.2 veröffentlicht wurde \(falls erforderlich\).
1. Löschen Sie den Browser-Cache nach der Installation des Pakets.
1. Fahren Sie mit der Aktualisierung der Anpassungen fort, wie im nächsten Abschnitt beschrieben.

### Aktivieren des Triggers eines Skripts über ein Servlet{#enable-trigger-serverlet-4-3-1}

POST:

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

In der obigen Antwort-JSON enthält der Schlüssel `lockNodePath` den Pfad zum Knoten, der im Repository erstellt wurde und auf den gesendeten Auftrag verweist. Er wird automatisch gelöscht, sobald der Auftrag abgeschlossen ist. Bis dahin können Sie den aktuellen Status des Auftrags in diesem Knoten nachlesen.

Beispielprotokoll:
Im Folgenden finden Sie ein Beispiel von Protokollen, die in der Protokolldatei angezeigt werden, nachdem Sie das Skript Trigger haben.

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

Suchen Sie nach `com.adobe.fmdita.translationservices.TranslationMapUpgradeScript Completed porting of translation map from V1 to V2` und `com.adobe.fmdita.xmltranslation.ots.TranslationMapUpgradeOTS Completed the thread to upgrade translation map from V1 to V2` , bevor Sie mit den nächsten Schritten fortfahren.

## Nach der Installation von Version 4.3.1



Nach der Installation von Experience Manager Guides können Sie die verschiedenen Konfigurationen zusammenführen, die von der neu installierten Version zu Ihrem Setup gehören.

>[!NOTE]
>
> Das Modell dam-update-asset kann angepasst werden. Wenn also Anpassungen vorgenommen wurden, müssen wir die Anpassungen und Experience Manager Guides mit der Arbeitskopie des Modells synchronisieren.

1. **DAM-Update-Asset-Workflow \(Nachbearbeitungs-Änderungen\):**

1. URL öffnen:

   ```
   http://localhost:4502/libs/cq/workflow/admin/console/content/models.html 
   ```

1. Wählen Sie **DAM-Update-Asset-Workflow** aus.
1. Klicken Sie auf **Bearbeiten**.
1. Wenn die Komponente **DXML Post Process Initiator** vorhanden ist, stellen Sie sicher, dass die Anpassungen synchronisiert werden.
1. Wenn die Komponente **DXML Post Process Initiator** fehlt, führen Sie die folgenden Schritte aus, um sie einzufügen:

1. Klicken Sie auf **Komponente einfügen** \(verantwortlich für die Experience Manager Guides-Nachbearbeitung als letzten Schritt im Prozess\).
1. Konfigurieren Sie den **Prozessschritt** mit den folgenden Details:

   **Registerkarte &quot;Allgemein&quot;**

   **Titel:** DXML-Nachbearbeitungs-Initiator

   **Beschreibung**: DXML-Nachbearbeitungs-Initiatorschritt, der einen Sling-Auftrag für die DXML-Nachbearbeitung des geänderten/erstellten Assets Trigger

   **Registerkarte &quot;Prozess&quot;**

   - Wählen Sie **DXML Post Process Initiator** aus der Dropdown-Liste **Process** aus.

   - Wählen Sie **Handler-Modus** aus

   - Wählen Sie **Fertig** aus

1. Klicken Sie oben rechts nach Abschluss der Änderungen auf **Synchronisieren** . Sie erhalten eine Erfolgsbenachrichtigung.

   >[!NOTE]
   >
   > Aktualisieren Sie und überprüfen Sie, ob benutzerdefinierte Änderungen und der Experience Manager Guides-Anschlussvorgang im endgültigen Workflow-Modell vorhanden sind.

1. Nachdem der Workflow **DAM-Update-Asset** validiert wurde, überprüfen Sie die entsprechenden Starter-Konfigurationen. Gehen Sie dazu zur Workflow-Oberfläche AEM und öffnen Sie Starter.

   ```http
   http://localhost:4502/libs/cq/workflow/content/console.html
   ```

   Suchen Sie nach den folgenden beiden Startern \(die aktiv sein sollten\), die **DAM Update Asset Workflow** entsprechen, und nehmen Sie Änderungen vor \(falls erforderlich\):

1. Starter für &quot;*Knoten erstellt*&quot;für **DAM-Update-Asset-Workflow** - für Bedingung `"jcr:content/jcr:mimeType!=video"` sollte der Wert &quot;Globbing&quot;wie folgt lauten:

   ```json
   /content/dam(/((?!/subassets|/translation_output).)*/)renditions/original
   ```

   - &#39;excludeList&#39; sollte `"event-user-data:changedByWorkflowProcess"` aufweisen.
   - Der Starter für &quot;*Node Modified*&quot;für **DAM Update Asset Workflow -** für Bedingung &quot;`jcr:content/jcr:mimeType!=video`&quot;, sollte der Wert &quot;Globbing&quot;lauten:

   ```json
   /content/dam(/((?!/subassets|/translation_output).)*/)renditions/original
   ```

   - `excludeList` sollte `"event-user-data:changedByWorkflowProcess"` haben.

1. Nachdem das Upgrade abgeschlossen ist, stellen Sie sicher, dass alle Anpassungen/Überlagerungen validiert und aktualisiert wurden, um dem neuen Anwendungscode zu entsprechen. Nachfolgend finden Sie einige Beispiele:
   - Alle aus /libs/fmditaor/libsüberlagerten Komponenten sollten mit dem neuen Produktcode verglichen werden und Aktualisierungen sollten in überlagerten Dateien unter/apps vorgenommen werden.
   - Alle clientlib-Kategorien, die vom Produkt verwendet werden, sollten auf Änderungen überprüft werden. Alle überschriebenen Konfigurationen \(Beispiele unten\) sollten mit den neuesten verglichen werden, um die neuesten Funktionen zu erhalten:
   - elementmapping.xml
   - ui\_config.json\(möglicherweise in Ordnerprofilen festgelegt\)
   - geänderte `com.adobe.fmdita.config.ConfigManager`


## Schritte zum Indexieren des vorhandenen Inhalts

>[!NOTE]
>
> Sie müssen diese Schritte nicht ausführen, wenn Sie ein Upgrade von 4.3.0 oder 4.2.1 durchführen.

Führen Sie die folgenden Schritte für die Indizierung des vorhandenen Inhalts aus und verwenden Sie den neuen Suchen- und Ersetzen-Text auf Zuordnungsebene:


- Führen Sie eine POST-Anfrage an den Server aus \(mit korrekter Authentifizierung\) - `http://<server:port\>/bin/guides/map-find/indexing`. (Optional: Sie können bestimmte Pfade der Maps übergeben, um sie zu indizieren. Standardmäßig werden alle Maps indiziert \|\| Beispiel: `https://<Server:port\>/bin/guides/map-find/indexing?paths=<map\_path\_in\_repository\>`)


- Die API gibt eine jobId zurück. Um den Auftragsstatus zu überprüfen, können Sie eine GET-Anfrage mit Auftrags-ID an denselben Endpunkt senden - `http://<server:port\>/bin/guides/map-find/indexing?jobId=\{jobId\}`\(z. B. `http://localhost:8080/bin/guides/map-find/indexing?jobId=2022/9/15/7/27/7dfa1271-981e-4617-b5a4-c18379f11c42`\)


- Nach Abschluss des Auftrags antwortet die obige GET-Anfrage mit Erfolg und gibt an, ob Zuordnungen fehlgeschlagen sind. Die erfolgreich indizierten Maps können über die Serverprotokolle bestätigt werden.

## Schritte zum Nachbearbeiten des vorhandenen Inhalts zur Verwendung des Berichts über einen fehlerhaften Link

>[!NOTE]
>
> Sie müssen diese Schritte nicht ausführen, wenn Sie ein Upgrade von 4.3.0 durchführen

Führen Sie die folgenden Schritte aus, um den vorhandenen Inhalt nachzubearbeiten und den neuen Bericht zu fehlerhaften Links zu verwenden:

1. (Optional) Wenn mehr als 100.000 Datendateien im System vorhanden sind, aktualisieren Sie den `queryLimitReads` unter `org.apache.jackrabbit.oak.query.QueryEngineSettingsService` auf einen größeren Wert (ein beliebiger Wert, der größer ist als die Anzahl der vorhandenen Assets, z. B. 200.000), und stellen Sie dann erneut bereit.

   | PID | Eigenschaftenschlüssel | Eigenschaftswert |
   |---|---|---|
   | org.apache.jackrabbit.oak.query.QueryEngineSettingsService | queryLimitReads | Wert: 200000 <br> Standardwert: 10000 |

1. Führen Sie die folgenden APIs aus, um die Nachbearbeitung für alle Dateien auszuführen:

   | Endpunkt | /bin/guides/reports/upgrade |
   |---|---|
   | Abfragetyp | **POST** Dieses Skript ist eine POST-Anfrage. Daher sollte es über Agenten wie Postman ausgeführt werden. |
   | Erwartete Antwort | Die API gibt eine jobId zurück. Um den Auftragsstatus zu überprüfen, können Sie eine GET-Anfrage mit Auftrags-ID an denselben Endpunkt senden.<br> Beispiel-URL: `http://<server:port>/bin/guides/reports/upgrade` |

   | Endpunkt | /bin/guides/reports/upgrade |
   |---|---|
   | Abfragetyp | **GET** |
   | Parameter | jobId: Übergeben Sie die jobId, die von der vorherigen POST-Anfrage empfangen wurde. |
   | Erwartete Antwort | - Nach Abschluss des Auftrags antwortet die GET-Anfrage erfolgreich. <br> - Im Fall von Fehlern sollten Sie die Fehlerprotokolle zusammen mit der API-Ausgabe für Ihr Customer Success Team freigeben.  <br>Beispiel-URL: `http://<server:port>/bin/guides/reports/upgrade?jobId=2022/9/15/7/27/7dfa1271-981e-4617-b5a4-c18379f11c42_678` |


1. Kehren Sie zurück zum standardmäßigen oder vorherigen vorhandenen Wert von `queryLimitReads` zurück, wenn Sie ihn in Schritt 1 geändert haben.



## Upgrade auf Version 4.3.1.5 {#upgrade-version-4-3-1-5}

Die Aktualisierung auf Version 4.3.1.5 hängt von der aktuellen Version von Experience Manager Guides ab. Wenn Sie Version 4.3.1 verwenden, können Sie direkt auf Version 4.3.1.5 aktualisieren.



## Installieren Sie Version 4.3.1.5.

1. Laden Sie das 4.3.1.5-Versionspaket vom [Adobe Software Distribution-Portal](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html) herunter.
1. Installieren Sie das Paket der Version 4.3.1.5.

1. Warten Sie, bis der Installationsprozess erfolgreich abgeschlossen wurde.
1. Fahren Sie mit der Aktualisierung der Anpassungen fort, wie im nächsten Abschnitt beschrieben.


## Nach der Installation von Version 4.3.1.5


>[!NOTE]
>
>Wenn Sie das Bundle org.apache.Velocity verwenden möchten, führen Sie die folgenden Schritte aus, bevor Sie das Bundle hochladen:
> 1. Rufen Sie `<server>:<port>/system/console/bundles` auf.
> 1. Suchen Sie nach org.apache.Velocity.
> 1. Deinstallieren Sie das gesuchte Bundle.
> 1. Installieren Sie das erforderliche Velocity-Bundle.


1. Nachdem das Upgrade abgeschlossen ist, stellen Sie sicher, dass alle Anpassungen/Überlagerungen validiert und aktualisiert wurden, um dem neuen Anwendungscode zu entsprechen. Nachfolgend finden Sie einige Beispiele:
   - Alle Komponenten, die aus `/libs/fmdita` oder ` /libs` überlagert wurden, sollten mit dem neuen Produktcode verglichen werden und Aktualisierungen sollten in überlagerten Dateien unter `/apps` vorgenommen werden.
   - Alle clientlib-Kategorien, die vom Produkt verwendet werden, sollten auf Änderungen überprüft werden. Alle überschriebenen Konfigurationen \(Beispiele unten\) sollten mit den neuesten verglichen werden, um die neuesten Funktionen zu erhalten:
   - `elementmapping.xml`
   - `ui\_config.json\` (möglicherweise in Ordnerprofilen festgelegt\)
   - geänderte `com.adobe.fmdita.config.ConfigManager`







## Upgrade auf Version 4.4.0 {#upgrade-version-4-4-0}

Die Aktualisierung auf Version 4.4.0 hängt von der aktuellen Version von Experience Manager Guides ab. Wenn Sie Version 4.3.1, 4.3.0, 4.2 oder 4.2.1 (Hotfix 4.2.1.3) verwenden, können Sie direkt auf Version 4.4.0 aktualisieren

>[!NOTE]
>
>Die Nachbearbeitung und Indizierung kann einige Stunden dauern. Es wird empfohlen, den Aktualisierungsprozess außerhalb der Spitzenzeiten zu starten.

****Voraussetzungen****

Bevor Sie mit dem Upgrade-Prozess für Experience Manager Guides 4.4.0 beginnen, stellen Sie Folgendes sicher:

1. Aktualisierung auf Experience Manager Guides-Version 4.3.1, 4.3.0 oder 4.2.1 (Hotfix 4.2.1.3) und Abschluss des jeweiligen Installationsschritts.
1. (Optional) Alle Übersetzungsaufgaben wurden geschlossen.
1. Die Protokollebene für die Klasse `com.adobe.fmdita.translationservices.TranslationMapUpgradeScript` wurde zu **INFO** geändert und diese Protokolle werden an eine neue Protokolldatei angehängt, z. B. `logs/translation_upgrade.log`.


## Installieren Sie Version 4.4.0

1. Laden Sie das 4.4.0-Versionspaket vom [Adobe Software Distribution-Portal](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html) herunter.
1. Installieren Sie das Paket der Version 4.4.0.
1. Sie können den Trigger drücken, um den Aktualisierungsauftrag für die Übersetzungskarte zu starten. Weitere Informationen finden Sie unter [Aktivieren des Skript-Triggers über ein Servlet](#enable-trigger-serverlet-4-4-0).

1. Warten Sie nach Abschluss der Paketinstallation auf die folgende(n) Meldung(en\) in den Protokollen:

   `Completed the post deployment setup script`

   Die obige Meldung weist darauf hin, dass alle Installationsschritte abgeschlossen sind.

   Sollten Sie auf eines der folgenden FEHLER-Präfixe stoßen, melden Sie diese Ihrem Kundenerfolgsteam:

   - Fehler beim Setup-Skript nach der Bereitstellung
   - Ausnahme beim Importieren der Übersetzungs-MAP
   - Die Übersetzungszuordnung kann nicht von v1 auf v2 für die Eigenschaft portiert werden
1. Aktualisieren Sie das Oxygen Connector-Plugin, das mit Version 4.4.0 veröffentlicht wurde \(falls erforderlich\).
1. Löschen Sie den Browser-Cache nach der Installation des Pakets.
1. Fahren Sie mit der Aktualisierung der Anpassungen fort, wie im nächsten Abschnitt beschrieben.


## Nach der Installation von Version 4.4.0

Nach der Installation von Experience Manager Guides können Sie die verschiedenen Konfigurationen zusammenführen, die von der neu installierten Version zu Ihrem Setup gehören.

>[!NOTE]
>
> Das Modell dam-update-asset kann angepasst werden. Wenn also Anpassungen vorgenommen wurden, müssen wir die Anpassungen und Experience Manager Guides mit der Arbeitskopie des Modells synchronisieren.

1. **DAM-Update-Asset-Workflow \(Nachbearbeitungs-Änderungen\):**

1. URL öffnen:

   ```
   http://localhost:4502/libs/cq/workflow/admin/console/content/models.html 
   ```

1. Wählen Sie **DAM-Update-Asset-Workflow** aus.
1. Klicken Sie auf **Bearbeiten**.
1. Wenn die Komponente **DXML Post Process Initiator** vorhanden ist, stellen Sie sicher, dass die Anpassungen synchronisiert werden.
1. Wenn die Komponente **DXML Post Process Initiator** fehlt, führen Sie die folgenden Schritte aus, um sie einzufügen:

1. Klicken Sie auf **Komponente einfügen** \(verantwortlich für die Experience Manager Guides-Nachbearbeitung als letzten Schritt im Prozess\).
1. Konfigurieren Sie den **Prozessschritt** mit den folgenden Details:

   **Registerkarte &quot;Allgemein&quot;**

   **Titel:** DXML-Nachbearbeitungs-Initiator

   **Beschreibung**: DXML-Nachbearbeitungs-Initiatorschritt, der einen Sling-Auftrag für die DXML-Nachbearbeitung des geänderten/erstellten Assets Trigger

   **Registerkarte &quot;Prozess&quot;**

   - Wählen Sie **DXML Post Process Initiator** aus der Dropdown-Liste **Process** aus.

   - Wählen Sie **Handler-Modus** aus

   - Wählen Sie **Fertig** aus

1. Klicken Sie oben rechts nach Abschluss der Änderungen auf **Synchronisieren** . Sie erhalten eine Erfolgsbenachrichtigung.

   >[!NOTE]
   >
   > Aktualisieren Sie und überprüfen Sie, ob benutzerdefinierte Änderungen und der Experience Manager Guides-Anschlussvorgang im endgültigen Workflow-Modell vorhanden sind.

1. Nachdem der Workflow **DAM-Update-Asset** validiert wurde, überprüfen Sie die entsprechenden Starter-Konfigurationen. Gehen Sie dazu zur Workflow-Oberfläche AEM und öffnen Sie Starter.

   ```http
   http://localhost:4502/libs/cq/workflow/content/console.html
   ```

   Suchen Sie nach den folgenden beiden Startern \(die aktiv sein sollten\), die **DAM Update Asset Workflow** entsprechen, und nehmen Sie Änderungen vor \(falls erforderlich\):

1. Starter für &quot;*Knoten erstellt*&quot;für **DAM-Update-Asset-Workflow** - für Bedingung `"jcr:content/jcr:mimeType!=video"` sollte der Wert &quot;Globbing&quot;wie folgt lauten:

   ```json
   /content/dam(/((?!/subassets|/translation_output).)*/)renditions/original
   ```

   - &#39;excludeList&#39; sollte `"event-user-data:changedByWorkflowProcess"` aufweisen.
   - Der Starter für &quot;*Node Modified*&quot;für **DAM Update Asset Workflow -** für Bedingung &quot;`jcr:content/jcr:mimeType!=video`&quot;, sollte der Wert &quot;Globbing&quot;lauten:

   ```json
   /content/dam(/((?!/subassets|/translation_output).)*/)renditions/original
   ```

   - `excludeList` sollte `"event-user-data:changedByWorkflowProcess"` haben.

1. Nachdem das Upgrade abgeschlossen ist, stellen Sie sicher, dass alle Anpassungen/Überlagerungen validiert und aktualisiert wurden, um dem neuen Anwendungscode zu entsprechen. Nachfolgend finden Sie einige Beispiele:
   - Alle aus /libs/fmditaor/libsüberlagerten Komponenten sollten mit dem neuen Produktcode verglichen werden und Aktualisierungen sollten in überlagerten Dateien unter/apps vorgenommen werden.
   - Alle clientlib-Kategorien, die vom Produkt verwendet werden, sollten auf Änderungen überprüft werden. Alle überschriebenen Konfigurationen \(Beispiele unten\) sollten mit den neuesten verglichen werden, um die neuesten Funktionen zu erhalten:
   - elementmapping.xml
   - ui\_config.json\(möglicherweise in Ordnerprofilen festgelegt\)
   - geänderte `com.adobe.fmdita.config.ConfigManager`

1. Wenn Sie in damAssetLucene Anpassungen hinzugefügt haben, müssen Sie diese möglicherweise erneut anwenden. Nachdem Sie diese Änderungen vorgenommen haben, setzen Sie reindex auf true. Dadurch werden alle vorhandenen Knoten mit den Anpassungen neu indiziert. Nach Abschluss des Vorgangs wird das reindex-Flag erneut auf &quot;false&quot;gesetzt. Dies kann abhängig von der Anzahl der Assets im System einige Stunden dauern.

## Schritte zum Indexieren des vorhandenen Inhalts

>[!NOTE]
>
> Sie müssen diese Schritte nicht ausführen, wenn Sie ein Upgrade von 4.3.0 oder 4.3.1 durchführen.

Führen Sie die folgenden Schritte für die Indizierung des vorhandenen Inhalts aus und verwenden Sie den neuen Suchen- und Ersetzen-Text auf Zuordnungsebene:

- Führen Sie eine POST-Anfrage an den Server aus \(mit korrekter Authentifizierung\) - `http://<server:port\>/bin/guides/map-find/indexing`. (Optional: Sie können bestimmte Pfade der Maps übergeben, um sie zu indizieren. Standardmäßig werden alle Maps indiziert \|\| Beispiel: `https://<Server:port\>/bin/guides/map-find/indexing?paths=<map\_path\_in\_repository\>`)

- Die API gibt eine jobId zurück. Um den Auftragsstatus zu überprüfen, können Sie eine GET-Anfrage mit Auftrags-ID an denselben Endpunkt senden - `http://<server:port\>/bin/guides/map-find/indexing?jobId=\{jobId\}`\(z. B. `http://localhost:8080/bin/guides/map-find/indexing?jobId=2022/9/15/7/27/7dfa1271-981e-4617-b5a4-c18379f11c42`\)

- Nach Abschluss des Auftrags antwortet die obige GET-Anfrage mit Erfolg und gibt an, ob Zuordnungen fehlgeschlagen sind. Die erfolgreich indizierten Maps können über die Serverprotokolle bestätigt werden.

## Schritte zum Nachbearbeiten des vorhandenen Inhalts zur Verwendung des Berichts über einen fehlerhaften Link

>[!NOTE]
>
> Sie müssen diese Schritte nicht ausführen, wenn Sie ein Upgrade von 4.3.0 oder 4.3.1 durchführen.

Führen Sie die folgenden Schritte aus, um den vorhandenen Inhalt nachzubearbeiten und den neuen Bericht zu fehlerhaften Links zu verwenden:

1. (Optional) Wenn mehr als 100.000 Datendateien im System vorhanden sind, aktualisieren Sie den `queryLimitReads` unter `org.apache.jackrabbit.oak.query.QueryEngineSettingsService` auf einen größeren Wert (ein beliebiger Wert, der größer ist als die Anzahl der vorhandenen Assets, z. B. 200.000), und stellen Sie dann erneut bereit.

   | PID | Eigenschaftenschlüssel | Eigenschaftswert |
   |---|---|---|
   | org.apache.jackrabbit.oak.query.QueryEngineSettingsService | queryLimitReads | Wert: 200000 <br> Standardwert: 10000 |

1. Führen Sie die folgenden APIs aus, um die Nachbearbeitung für alle Dateien auszuführen:

   | Endpunkt | /bin/guides/reports/upgrade |
   |---|---|
   | Abfragetyp | **POST** Dieses Skript ist eine POST-Anfrage. Daher sollte es über Agenten wie Postman ausgeführt werden. |
   | Erwartete Antwort | Die API gibt eine jobId zurück. Um den Auftragsstatus zu überprüfen, können Sie eine GET-Anfrage mit Auftrags-ID an denselben Endpunkt senden.<br> Beispiel-URL: `http://<server:port>/bin/guides/reports/upgrade` |

   | Endpunkt | /bin/guides/reports/upgrade |
   |---|---|
   | Abfragetyp | **GET** |
   | Parameter | jobId: Übergeben Sie die jobId, die von der vorherigen POST-Anfrage empfangen wurde. |
   | Erwartete Antwort | - Nach Abschluss des Auftrags antwortet die GET-Anfrage erfolgreich. <br> - Im Fall von Fehlern sollten Sie die Fehlerprotokolle zusammen mit der API-Ausgabe für Ihr Customer Success Team freigeben.  <br>Beispiel-URL: `http://<server:port>/bin/guides/reports/upgrade?jobId=2022/9/15/7/27/7dfa1271-981e-4617-b5a4-c18379f11c42_678` |

1. Kehren Sie zurück zum standardmäßigen oder vorherigen vorhandenen Wert von `queryLimitReads` zurück, wenn Sie ihn in Schritt 1 geändert haben.

### Aktivieren des Triggers eines Skripts über ein Servlet{#enable-trigger-serverlet-4-4-0}

>[!NOTE]
>
> Sie müssen diese Schritte nicht ausführen, wenn Sie ein Upgrade von 4.3.0 oder 4.3.1 durchführen.

POST:

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

In der obigen Antwort-JSON enthält der Schlüssel `lockNodePath` den Pfad zum Knoten, der im Repository erstellt wurde und auf den gesendeten Auftrag verweist. Er wird automatisch gelöscht, sobald der Auftrag abgeschlossen ist. Bis dahin können Sie den aktuellen Status des Auftrags in diesem Knoten nachlesen.

Suchen Sie nach `com.adobe.fmdita.translationservices.TranslationMapUpgradeScript Completed porting of translation map from V1 to V2` und `com.adobe.fmdita.xmltranslation.ots.TranslationMapUpgradeOTS Completed the thread to upgrade translation map from V1 to V2` , bevor Sie mit den nächsten Schritten fortfahren.

>[!NOTE]
>
> Sie sollten überprüfen, ob der Knoten noch vorhanden ist und den Status des Auftrags.

**GET**: `http://<aem_domain>/var/dxml/executor-locks/translation-map-upgrade/1683190032886.json`



## Schritte zur Handhabung des `'fmdita rewriter'`-Konflikts

Experience Manager Guides verfügt über ein [**benutzerdefinierter Sling-Rewriter**](../cs-install-guide/conf-output-generation.md#custom-rewriter) -Modul für die Verarbeitung der im Fall von Querverweisen generierten Links (Links zwischen den Themen zweier verschiedener Maps).

Wenn Sie in Ihrer Codebasis über einen anderen benutzerdefinierten Sling-Rewriter verfügen, verwenden Sie einen `'order'` -Wert größer als 50, da der Experience Manager Guides Sling-Rewriter `'order'` 50 verwendet.  Um dies zu überschreiben, benötigen Sie einen Wert > 50. Weitere Informationen finden Sie unter [Pipelines zum Neuschreiben der Ausgabe ](https://sling.apache.org/documentation/bundles/output-rewriting-pipelines-org-apache-sling-rewriter.html).

Da während dieses Upgrades der Wert `'order'` von 1000 auf 50 geändert wird, müssen Sie die vorhandene benutzerdefinierte Rewriter, falls vorhanden, mit `'fmdita-rewriter'` zusammenführen.


**Übergeordnetes Thema:**[ Herunterladen und Installieren](download-install.md)


## Upgrade auf Version 4.6.0 {#upgrade-version-4-6-0}

Die Aktualisierung auf Version 4.6.0 hängt von der aktuellen Version von Experience Manager Guides ab. Wenn Sie Version 4.4.0, 4.3.1, 4.3.0, 4.2 oder 4.2.1 (Hotfix 4.2.1.3) verwenden, können Sie direkt auf Version 4.6.0 aktualisieren.

>[!NOTE]
>
>Die Nachbearbeitung und Indizierung kann einige Stunden dauern. Es wird empfohlen, den Aktualisierungsprozess außerhalb der Spitzenzeiten zu starten.

****Voraussetzungen****

Bevor Sie mit dem Upgrade-Prozess für Experience Manager Guides 4.6.0 beginnen, stellen Sie Folgendes sicher:

1. Aktualisierung auf Experience Manager Guides-Version 4.3.1, 4.3.0 oder 4.2.1 (Hotfix 4.2.1.3) und Abschluss des jeweiligen Installationsschritts.
1. (Optional) Alle Übersetzungsaufgaben wurden geschlossen.
1. Die Protokollebene für die Klasse `com.adobe.fmdita.translationservices.TranslationMapUpgradeScript` wurde zu **INFO** geändert und diese Protokolle werden an eine neue Protokolldatei angehängt, z. B. `logs/translation_upgrade.log`.


## Installieren Sie Version 4.6.0

1. Laden Sie das 4.6.0-Versionspaket vom [Adobe Software Distribution-Portal](https://experience.adobe.com/#/downloads/content/software-distribution/de/aem.html) herunter.
1. Installieren Sie das Paket Version 4.6.0 .
1. Sie können den Trigger drücken, um den Aktualisierungsauftrag für die Übersetzungskarte zu starten. Weitere Informationen finden Sie unter [Aktivieren des Skript-Triggers über ein Servlet](#enable-trigger-serverlet-4-6-0).

1. Warten Sie nach Abschluss der Paketinstallation auf die folgende(n) Meldung(en\) in den Protokollen:

   `Completed the post deployment setup script`

   Die obige Meldung weist darauf hin, dass alle Installationsschritte abgeschlossen sind.

   Sollten Sie auf eines der folgenden FEHLER-Präfixe stoßen, melden Sie diese Ihrem Kundenerfolgsteam:

   - Fehler beim Setup-Skript nach der Bereitstellung
   - Ausnahme beim Importieren der Übersetzungs-MAP
   - Die Übersetzungszuordnung kann nicht von v1 auf v2 für die Eigenschaft portiert werden
1. Aktualisieren Sie das Oxygen Connector-Plugin, das mit Version 4.6.0 veröffentlicht wurde \(falls erforderlich\).
1. Löschen Sie den Browser-Cache nach der Installation des Pakets.

## Nach der Installation von Version 4.6.0

Nach der Installation von Experience Manager Guides können Sie die verschiedenen Konfigurationen zusammenführen, die von der neu installierten Version zu Ihrem Setup gehören.

>[!NOTE]
>
> Das Modell dam-update-asset kann angepasst werden. Wenn also Anpassungen vorgenommen wurden, müssen wir die Anpassungen und Experience Manager Guides mit der Arbeitskopie des Modells synchronisieren.

1. **DAM-Update-Asset-Workflow \(Nachbearbeitungs-Änderungen\):**

1. URL öffnen:

   ```
   http://localhost:4502/libs/cq/workflow/admin/console/content/models.html 
   ```

1. Wählen Sie **DAM-Update-Asset-Workflow** aus.
1. Klicken Sie auf **Bearbeiten**.
1. Wenn die Komponente **DXML Post Process Initiator** vorhanden ist, stellen Sie sicher, dass die Anpassungen synchronisiert werden.
1. Wenn die Komponente **DXML Post Process Initiator** fehlt, führen Sie die folgenden Schritte aus, um sie einzufügen:

1. Klicken Sie auf **Komponente einfügen** \(verantwortlich für die Experience Manager Guides-Nachbearbeitung als letzten Schritt im Prozess\).
1. Konfigurieren Sie den **Prozessschritt** mit den folgenden Details:

   **Registerkarte &quot;Allgemein&quot;**

   **Titel:** DXML-Nachbearbeitungs-Initiator

   **Beschreibung**: DXML-Nachbearbeitungs-Initiatorschritt, der einen Sling-Auftrag für die DXML-Nachbearbeitung des geänderten/erstellten Assets Trigger

   **Registerkarte &quot;Prozess&quot;**

   - Wählen Sie **DXML Post Process Initiator** aus der Dropdown-Liste **Process** aus.

   - Wählen Sie **Handler-Modus** aus

   - Wählen Sie **Fertig** aus

1. Klicken Sie oben rechts nach Abschluss der Änderungen auf **Synchronisieren** . Sie erhalten eine Erfolgsbenachrichtigung.

   >[!NOTE]
   >
   > Aktualisieren Sie und überprüfen Sie, ob benutzerdefinierte Änderungen und der Experience Manager Guides-Anschlussvorgang im endgültigen Workflow-Modell vorhanden sind.

1. Nachdem der Workflow **DAM-Update-Asset** validiert wurde, überprüfen Sie die entsprechenden Starter-Konfigurationen. Gehen Sie dazu zur Workflow-Oberfläche AEM und öffnen Sie Starter.

   ```http
   http://localhost:4502/libs/cq/workflow/content/console.html
   ```

   Suchen Sie nach den folgenden beiden Startern \(die aktiv sein sollten\), die **DAM Update Asset Workflow** entsprechen, und nehmen Sie Änderungen vor \(falls erforderlich\):

1. Starter für &quot;*Knoten erstellt*&quot;für **DAM-Update-Asset-Workflow** - für Bedingung `"jcr:content/jcr:mimeType!=video"` sollte der Wert &quot;Globbing&quot;wie folgt lauten:

   ```json
   /content/dam(/((?!/subassets|/translation_output).)*/)renditions/original
   ```

   - &#39;excludeList&#39; sollte `"event-user-data:changedByWorkflowProcess"` aufweisen.
   - Der Starter für &quot;*Node Modified*&quot;für **DAM Update Asset Workflow -** für Bedingung &quot;`jcr:content/jcr:mimeType!=video`&quot;, sollte der Wert &quot;Globbing&quot;lauten:

   ```json
   /content/dam(/((?!/subassets|/translation_output).)*/)renditions/original
   ```

   - `excludeList` sollte `"event-user-data:changedByWorkflowProcess"` haben.

1. Nachdem das Upgrade abgeschlossen ist, stellen Sie sicher, dass alle Anpassungen/Überlagerungen validiert und aktualisiert wurden, um dem neuen Anwendungscode zu entsprechen. Nachfolgend finden Sie einige Beispiele:
   - Alle aus /libs/fmditaor/libsüberlagerten Komponenten sollten mit dem neuen Produktcode verglichen werden und Aktualisierungen sollten in überlagerten Dateien unter/apps vorgenommen werden.
   - Alle clientlib-Kategorien, die vom Produkt verwendet werden, sollten auf Änderungen überprüft werden. Alle überschriebenen Konfigurationen \(Beispiele unten\) sollten mit den neuesten verglichen werden, um die neuesten Funktionen zu erhalten:
   - elementmapping.xml
   - ui\_config.json\(möglicherweise in Ordnerprofilen festgelegt\)
   - geänderte `com.adobe.fmdita.config.ConfigManager`

1. Wenn Sie in damAssetLucene Anpassungen hinzugefügt haben, müssen Sie diese möglicherweise erneut anwenden. Nachdem Sie diese Änderungen vorgenommen haben, setzen Sie reindex auf true. Dadurch werden alle vorhandenen Knoten mit den Anpassungen neu indiziert. Nach Abschluss des Vorgangs wird das reindex-Flag erneut auf &quot;false&quot;gesetzt. Dies kann abhängig von der Anzahl der Assets im System einige Stunden dauern.

## Schritte zur Neuindizierung der Experience Manager Guides-Indizes

1. Öffnen Sie `crx/de` und navigieren Sie zum Indexpfad: `/oak:index/guidesAssetProperties`
2. Legen Sie die Eigenschaft reindex auf `true` (`false` standardmäßig) fest und klicken Sie auf **Alle speichern**.
3. Sobald die Neuindizierung abgeschlossen ist, wird die Eigenschaft reindex erneut auf `false` gesetzt und die Anzahl der Neuindizes wird um 1 erhöht.

   >[!NOTE]
   >
   > Dies kann abhängig von der Menge der vorhandenen Daten einige Minuten dauern.
4. Führen Sie dieselben Schritte für andere hinzugefügte oder geänderte Indizes aus: `guidesBulkActivation`, `guidesPeerLinkIndex` und `guidesKonnectTemplateIndex`.

## Schritte zum Indexieren des vorhandenen Inhalts



Führen Sie die folgenden Schritte zur Indizierung des vorhandenen Inhalts aus:

- Führen Sie eine POST-Anfrage an den Server aus \(mit korrekter Authentifizierung\) - `http://<server:port\>/bin/guides/map-find/indexing`. (Optional: Sie können bestimmte Pfade der Maps übergeben, um sie zu indizieren. Standardmäßig werden alle Maps indiziert || Beispiel : `https://<Server:port\>/bin/guides/map-find/indexing?paths=<map\_path\_in\_repository\>`)

- Die API gibt eine jobId zurück. Um den Auftragsstatus zu überprüfen, können Sie eine GET-Anfrage mit Auftrags-ID an denselben Endpunkt senden - `http://<server:port\>/bin/guides/map-find/indexing?jobId=\{jobId\}`\ (z. B. ` http://localhost:8080/bin/guides/map-find/indexing?jobId=2022/9/15/7/27/7dfa1271-981e-4617-b5a4-c18379f11c42_678`)

- Nach Abschluss des Auftrags antwortet die obige GET-Anfrage mit Erfolg und gibt an, ob Zuordnungen fehlgeschlagen sind. Die erfolgreich indizierten Maps können über die Serverprotokolle bestätigt werden.


>[!NOTE]
>
> Wenn Sie das benutzerdefinierte Schema verwenden, müssen Sie den Pfad der benutzerdefinierten DTD- und XSD-catalog.xml-Dateien im AEM-Repository in der Option **Kataloge integrieren** definieren.




## Schritte zur Handhabung des `'fmdita rewriter'`-Konflikts

Experience Manager Guides verfügt über ein [**benutzerdefinierter Sling-Rewriter**](../cs-install-guide/conf-output-generation.md#custom-rewriter) -Modul für die Verarbeitung der im Fall von Querverweisen generierten Links (Links zwischen den Themen zweier verschiedener Maps).

Wenn Sie in Ihrer Codebasis über einen anderen benutzerdefinierten Sling-Rewriter verfügen, verwenden Sie einen `'order'` -Wert größer als 50, da der Experience Manager Guides Sling-Rewriter `'order'` 50 verwendet.  Um dies zu überschreiben, benötigen Sie einen Wert > 50. Weitere Informationen finden Sie unter [Pipelines zum Neuschreiben der Ausgabe ](https://sling.apache.org/documentation/bundles/output-rewriting-pipelines-org-apache-sling-rewriter.html).

Da während dieses Upgrades der Wert `'order'` von 1000 auf 50 geändert wird, müssen Sie die vorhandene benutzerdefinierte Rewriter, falls vorhanden, mit `'fmdita-rewriter'` zusammenführen.






**Übergeordnetes Thema:** [Herunterladen und Installieren](download-install.md)
