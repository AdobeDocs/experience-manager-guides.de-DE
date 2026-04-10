---
title: Aktualisieren von Adobe Experience Manager Guides On-Premise-Vorgängerversionen
description: Erfahren Sie, wie Sie Adobe Experience Manager Guides aktualisieren
feature: Installation
role: Admin
level: Experienced
source-git-commit: 6f3f05419f4f5cdd45ab580cdee6fa869f20f01d
workflow-type: tm+mt
source-wordcount: '3159'
ht-degree: 0%

---

# Upgrade von Adobe Experience Manager Guides On-Premise (Version 4.4.0 und früher)

Dieser Artikel enthält Anweisungen zum Aktualisieren von **Adobe Experience Manager Guides**-Versionen **vor 4.6.0** (bis einschließlich **4.4.0**).

Wenn Sie eine Version **vor 3.8.5** verwenden, lesen Sie den Abschnitt **Upgrade von Experience Manager Guides** im produktspezifischen Installationshandbuch, das auf der [Adobe Experience Manager Guides-Hilfe für PDF Archive verfügbar ist](https://helpx.adobe.com/de/xml-documentation-for-experience-manager/archive.html).

Aktualisierungsanweisungen für neuere Versionen finden Sie unter [Adobe Experience Manager Guides für Version 4.6.0 und höher aktualisieren](./upgrade-aemg-latest-version.md).

## Vorbereitung

>[!NOTE]
>
> Sie müssen spezifische Anweisungen für die lizenzierte Version Ihres Produkts aktualisieren und das AEM Service Pack installieren, bevor Sie die Experience Manager Guides-Version aktualisieren.

>[!IMPORTANT]
>
> Bevor Sie mit dem Upgrade beginnen, sollten Sie eine **vollständige Systemsicherung** durchführen, um Datenverluste zu vermeiden.

## In diesem Artikel behandelte Aktualisierungspfade

Dieser Artikel enthält Verfahren für:

- [Aktualisierung auf Version 4.4.0](#upgrade-to-version-440)
- [Aktualisieren auf Version 4.3.1.5](#upgrade-to-version-4315)
- [Aktualisierung auf Version 4.3.1](#upgrade-to-version-431)
- [Aktualisierung auf Version 4.3.0](#upgrade-to-version-430)
- [Aktualisierung auf Version 4.2.1](#upgrade-to-version-421)
- [Aktualisierung auf Version 4.2](#upgrade-to-version-42)
- [Upgrade von 3.8.5 auf Version 4.0](#upgrade-from-version-385-to-version-40)


## Globale Voraussetzungen (gilt für alle Upgrades, sofern in einem Verfahren nichts anderes festgelegt ist)

Führen Sie vor dem Ausführen des Upgrade-Prozesses die folgenden Aufgaben aus:

1. Importieren von Prüfungskommentaren in Themen, die zur Überprüfung offen sind.
2. Alle aktiven Rezensionen schließen.
3. Schließen Sie alle Übersetzungsaufgaben.
4. Deinstallieren Sie alle Experience Manager Guides-Hotfixes, die zusätzlich zur vorherigen Version (Haupt- oder Patch-Version) installiert wurden.

Bei einigen Upgrades ist es außerdem erforderlich, für eine Upgrade-Klasse für Übersetzungen die Protokollebene auf `INFO` festzulegen und die Protokollierung in einer separaten Datei vorzunehmen. Diese Anforderungen werden in den entsprechenden Upgrade-Verfahren aufgeführt.

## Upgrade von Version 3.8.5 auf Version 4.0

>[!NOTE]
>
> Dieses Upgrade-Verfahren gilt **nur** von **3.8.5** auf **4.0**. Informationen zu Upgrades von **3.4 oder höher** auf **3.8.5** finden Sie im produktspezifischen Installationshandbuch, das auf der [Adobe Experience Manager Guides-Hilfe für PDF Archive](https://helpx.adobe.com/de/xml-documentation-for-experience-manager/archive.html) verfügbar ist.

Wenn Sie Experience Manager Guides Version **3.8.5** verwenden, können Sie auf Version **4.0** aktualisieren, ohne die vorherige Version zu deinstallieren.

### Vor der Installation von Version 4.0

1. Stellen Sie sicher, dass Experience Manager Guides Version **.3.8.5**.
2. Laden Sie das Upgrade-Skriptpaket herunter: Suchen Sie **&quot;XML Documentation-Lösung 4.0-Upgrade-Paket“** im Adobe Software Distribution-Portal (lädt eine `.zip` herunter).
3. Laden Sie das Paket über **Package Manager** in AEM hoch und installieren Sie es.
4. Führen Sie nach der Installation des Aktualisierungspakets die Skripte in der unten beschriebenen Reihenfolge aus.

**Upgrade-Kompatibilitäts-API überprüfen**

Diese API dient dazu, den aktuellen Systemstatus zu bewerten und Berichte zu erstellen, ob das Upgrade möglich ist oder nicht. Um dieses Skript auszuführen, geben Sie den folgenden Trigger für den Endpunkt ein:

| Endpunkt | /bin/dxml/upgrade/3xto4x/report |
| --- | --- |
| Abfragetyp | **GET** <br> **Hinweis**: Sie können einen Webbrowser verwenden, in dem Sie als Admin bei der AEM-Instanz angemeldet sind. |
| Erwartete Antwort | -   Wenn alle erforderlichen Knoten verschoben werden können, erhalten Sie eine bestandene Prüfung. <br>-   Wenn am Zielspeicherort ein Knoten vorhanden ist, wird ein relevanter Fehler angezeigt. Bereinigen Sie das Repository \(löschen Sie den Knoten /var/dxml\) und installieren Sie das Aktualisierungspaket erneut. Führen Sie dann erneut einen Trigger mit diesem Endpunkt durch. <br>**Hinweis:** Dies ist kein häufiger Fehler, da der Zielspeicherort von 3.x Experience Manager Guides nicht zuvor verwendet wird. <br> -   Wenn dieses Skript nicht erfolgreich ist, fahren Sie nicht fort und melden Sie es Ihrem Customer Success-Team. |

**Systemdatenmigrations-API**

Diese API dient zur Migration der Systemdaten, wie im Abschnitt **Migrationszuordnung** beschrieben.

1. Führen Sie dieses Skript nicht aus, wenn die API zur Überprüfung der Upgrade-Kompatibilität fehlschlägt \(fahren Sie nicht fort\).
1. Sobald die API zur Überprüfung der Aktualisierungskompatibilität erfolgreich war, können Sie das Aktualisierungsskript ausführen.

| Endpunkt | /bin/dxml/upgrade/3xto4x |
| --- | --- |
| Abfragetyp | **POST** <br>**Hinweis**: Dieses Skript ist eine POST-Anfrage und sollte daher über Agenten wie Postman ausgeführt werden. |
| Erwartete Antwort | -   Nach erfolgreicher Migration können Sie die XML Documentation-Lösung Version 4.0.<br>-   Wenn Fehler auftreten, stellen Sie den letzten Checkpoint wieder her und geben Sie die Fehlerprotokolle zusammen mit der API-Ausgabe an Ihr Customer Success-Team weiter. |


**Migrationszuordnung**

Diese API migriert alle Daten unter dem Quellspeicherort zum Zielspeicherort.

| Quelle | Ziel |
|------|------|
| /content/fmdita | /var/dxml |
| /content/dxml | /var/dxml |
| /etc/fmdita | /libs/fmdita |

### Installieren von Version 4.0

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

Sie können direkt auf Version **4.2** aktualisieren, wenn Sie Version **4.0**, **4.1** oder **4.1.x** verwenden.

### Vor der Installation von Version 4.2

Bevor Sie mit dem Upgrade auf Experience Manager Guides 4.2 beginnen, stellen Sie Folgendes sicher:

1. Aktualisierung auf Experience Manager Guides **4.0**, **4.1** oder **4.1.x**.
2. Alle Übersetzungsaufgaben geschlossen.
3. Setzen Sie die Protokollebene auf `INFO` für `com.adobe.fmdita.translationservices.TranslationMapUpgradeScript` und melden Sie sich in einer neuen Protokolldatei an (z. B. `logs/translation_upgrade.log`).

   >[!NOTE]
   > 
   > Sie sollten alle aktiven Rezensionen schließen. Wenn beim Upgrade auf 4.2 keine Überprüfungen geschlossen werden, können ältere Prüfungsaufgaben weiterhin ältere Prüfungsseiten öffnen. Nach dem Upgrade erstellte neue Prüfungsaufgaben zeigen die neuesten Funktionsaktualisierungen an.

### Installieren von Version 4.2

1. Laden Sie das **4.2**-Paket vom [Adobe Software Distribution Portal](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html) herunter.
2. Installieren Sie das Paket 4.2.
3. Warten Sie nach der Installation in den Protokollen auf die folgende Meldung:

   `Completed the post deployment setup script`

   Die obige Meldung weist darauf hin, dass alle Installationsschritte abgeschlossen sind.

   Wenn einer der folgenden Fehler auftritt, diese dem Customer Success melden:

   - `Error in post deployment setup script`
   - `Exception while porting the translation MAP`
   - `Unable to port translation map from v1 to v2 for property`

4. (Optional) Upgrade des Oxygen Connector-Plug-ins, das mit Version 4.2 veröffentlicht wurde.
5. Löschen Sie den Browser-Cache nach der Installation des Pakets.
6. Fahren Sie mit dem Upgrade der Anpassungen fort, wie im nächsten Abschnitt beschrieben.

### Nach der Installation von Version 4.2

>[!IMPORTANT]
>
> Die High-Tech-Vorlage wird auf dem aktualisierten Server nicht angezeigt. Um die High-Tech-Vorlage auf Ihrem Server einzubinden, können Sie sie kopieren: Source: `/libs/fmdita/pdf/Hi-Tech` Ziel: `/content/dam/dita-templates/pdf`.

Fahren Sie dann mit den freigegebenen Aufgaben nach dem Upgrade in [Allgemeine Aufgaben nach dem Upgrade (alle Versionen) fort](#common-postupgrade-tasks-all-versions).

## Aktualisierung auf Version 4.2.1

>[!TIP]
>
> Es wird empfohlen, **Hotfix4.2.1.3** auf Version **.2.1 zu**.

Sie können direkt auf Version **4.2.1**, wenn Sie **4.1**, **4.1.x** oder **4.2** verwenden.

>[!NOTE]
>
> Die Nachbearbeitung und Indizierung kann einige Stunden dauern. Starten Sie das Upgrade außerhalb der Spitzenzeiten.

### Vor der Installation von Version 4.2.1

1. Aktualisieren auf Experience Manager Guides **4.1**, **4.1.x** oder **4.2**.
2. Schließen Sie alle Übersetzungsaufgaben.
3. Setzen Sie die Protokollebene auf `INFO` für `com.adobe.fmdita.translationservices.TranslationMapUpgradeScript` und melden Sie sich in einer neuen Datei an (z. B. `logs/translation_upgrade.log`).

>[!NOTE]
>
> Sie sollten alle aktiven Reviews schließen (gleiches Verhalten wie 4.2).

### Installieren von Version 4.2.1

1. Laden Sie das **4.2.1**-Paket vom [Adobe Software Distribution Portal](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html) herunter.
2. Installieren Sie das Paket 4.2.1.
3. Optional können Sie einen Trigger für den Upgrade-Auftrag für die Übersetzungskarte erstellen. Weitere Informationen finden Sie unter [Aktivieren des Skript-Triggers über ein Servlet](#enable-trigger-of-script-via-a-servlet).

4. Warten Sie nach der Installation: `Completed the post deployment setup script` in den Protokollen.

   Melden Sie diese Fehler dem Customer Success:

   - `Error in post deployment setup script`
   - `Exception while porting the translation MAP`
   - `Unable to port translation map from v1 to v2 for property`
5. (Optional) Upgrade des Oxygen Connector-Plug-ins, das mit Version **4.2 veröffentlicht wurde**
6. Browser-Cache löschen.
7. Fahren Sie mit [Allgemeine Aufgaben nach einem Upgrade (alle Versionen) &#x200B;](#common-postupgrade-tasks-all-versions).

### Nach der Installation von Version 4.2.1

>[!IMPORTANT]
>
> Die High-Tech-Vorlage wird auf dem aktualisierten Server nicht angezeigt. Um die High-Tech-Vorlage auf Ihrem Server einzubinden, können Sie sie kopieren: Source: `/libs/fmdita/pdf/Hi-Tech` Ziel: `/content/dam/dita-templates/pdf`.

Fahren Sie mit [Allgemeine Aufgaben nach einem Upgrade (alle Versionen)](#common-postupgrade-tasks-all-versions) und (falls erforderlich) [Indizieren Sie vorhandenen Inhalt für das Suchen und Ersetzen von Karten](#index-existing-content-for-map-find-and-replace) fort.


## Aktualisierung auf Version 4.3.0

Die Aktualisierung auf Version 4.3.0 hängt von der aktuellen Version von Experience Manager Guides ab. Wenn Sie Version 4.2 oder 4.2.x verwenden, können Sie direkt auf Version 4.3.0 aktualisieren.

>[!NOTE]
>
>Die Nachbearbeitung und Indizierung kann einige Stunden dauern. Es wird empfohlen, den Upgrade-Prozess außerhalb der Spitzenzeiten zu starten.

### Vor der Installation von Version 4.3.0

Stellen Sie vor dem Start des Upgrades auf Experience Manager Guides 4.3.0 Folgendes sicher:

1. auf Experience Manager Guides Version 4.2 oder 4.2.x aktualisiert und der entsprechende Installationsschritt abgeschlossen.
1. Alle Übersetzungsaufgaben geschlossen.

### Installieren von Version 4.3.0

1. Laden Sie das Versionspaket 4.3.0 vom [Adobe Software Distribution Portal](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html) herunter.
1. Installieren Sie das Paket Version 4.3.0.
1. Löschen Sie den Browser-Cache nach der Installation des Pakets.
1. Aktualisieren Sie die Datei `ui_config.json` auf der Registerkarte **XML-Editor** im Ordnerprofil.

### Nach der Installation von Version 4.3.0

Weiter mit:

- [Häufige Aufgaben nach einem Upgrade (alle Versionen)](#common-postupgrade-tasks-all-versions)
- Falls zutreffend: [Vorhandenen Inhalt für fehlerhaften Link-Bericht nachverarbeiten](#post-process-existing-content-for-broken-link-report)

## Aktualisierung auf Version 4.3.1

Die Aktualisierung auf Version 4.3.1 hängt von der aktuellen Version von Experience Manager Guides ab. Wenn Sie Version 4.3.0, 4.2 oder 4.2.1 verwenden, können Sie direkt auf Version 4.3.1 aktualisieren.

>[!NOTE]
>
>Die Nachbearbeitung und Indizierung kann einige Stunden dauern. Es wird empfohlen, den Upgrade-Prozess außerhalb der Spitzenzeiten zu starten.

### Vor der Installation von Version 4.3.1

Stellen Sie vor dem Start des Upgrades auf Experience Manager Guides 4.3.1 Folgendes sicher:

1. auf Experience Manager Guides Version 4.3.0, 4.2 oder 4.2.1 aktualisiert und der entsprechende Installationsschritt abgeschlossen.
1. (Optional) Alle Übersetzungsaufgaben wurden geschlossen.
1. Protokollebene für **Klasse in &quot;**&quot; `com.adobe.fmdita.translationservices.TranslationMapUpgradeScript` und diese Protokolle in einer neuen Protokolldatei anhängen, z. B. `logs/translation_upgrade.log`.

### Installieren von Version 4.3.1

1. Laden Sie das Versionspaket 4.3.1 vom [Adobe Software Distribution Portal](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html) herunter.
1. Installieren Sie das Paket Version 4.3.1 .
1. Optional können Sie einen Trigger für den Upgrade-Auftrag für die Übersetzungskarte erstellen. Weitere Informationen finden Sie unter [Aktivieren des Skript-Triggers über ein Servlet](#enable-trigger-of-script-via-a-servlet).
1. Warten Sie nach der Installation: `Completed the post deployment setup script` in den Protokollen.
Melden Sie diese Fehler dem Customer Success:\
   `Error in post deployment setup script`, `Exception while porting the translation MAP`, `Unable to port translation map from v1 to v2 for property`
1. (Optional) Upgrade des Oxygen Connector-Plug-ins, das mit Version **4.2** veröffentlicht wurde.
1. Browser-Cache löschen.

### Nach der Installation von Version 4.3.1

Weiter mit:

- [Häufige Aufgaben nach einem Upgrade (alle Versionen)](#common-postupgrade-tasks-all-versions)
- Falls zutreffend: [Vorhandenen Inhalt für Map suchen und ersetzen](#index-existing-content-for-map-find-and-replace)
- Falls zutreffend: [Vorhandenen Inhalt für fehlerhaften Link-Bericht nachverarbeiten](#post-process-existing-content-for-broken-link-report)


## Aktualisieren auf Version 4.3.1.5

Sie können direkt auf **4.3.1.5** aktualisieren, wenn Sie Version **4.3.1** verwenden.

### Installieren von Version 4.3.1.5

1. Laden Sie das **4.3.1.5** Paket vom [Adobe Software Distribution Portal](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html) herunter.
2. Installieren Sie das 4.3.1.5.
3. Warten Sie, bis der Installationsprozess erfolgreich abgeschlossen wurde.
4. Fahren Sie mit dem Upgrade der Anpassungen fort, wie im nächsten Abschnitt beschrieben.

## Nach der Installation von Version 4.3.1.5

>[!NOTE]
>
>Wenn Sie das Bundle org.apache.velocity verwenden möchten, führen Sie die folgenden Schritte aus, bevor Sie das Bundle hochladen:
> 1. Wechseln zu `<server>:<port>/system/console/bundles`
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

Sie können direkt auf **4.4.0** aktualisieren, wenn Sie **4.3.1**, **4.3.0**, **4.2** oder **4.2.1 (Hotfix 4.2.1.3)** verwenden.

>[!NOTE]
>
>Die Nachbearbeitung und Indizierung kann einige Stunden dauern. Es wird empfohlen, den Upgrade-Prozess außerhalb der Spitzenzeiten zu starten.

### Vor der Installation von Version 4.4.0

Stellen Sie vor dem Start des Upgrades auf Experience Manager Guides 4.4.0 Folgendes sicher:

1. auf Experience Manager Guides Version 4.3.1, 4.3.0 oder 4.2.1 (Hotfix 4.2.1.3) aktualisiert und der entsprechende Installationsschritt abgeschlossen.
1. (Optional) Alle Übersetzungsaufgaben wurden geschlossen.
1. Protokollebene für **Klasse in &quot;**&quot; `com.adobe.fmdita.translationservices.TranslationMapUpgradeScript` und diese Protokolle in einer neuen Protokolldatei anhängen, z. B. `logs/translation_upgrade.log`.

### Installieren von Version 4.4.0

1. Laden Sie das Versionspaket 4.4.0 vom [Adobe Software Distribution Portal](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html) herunter.
2. Installieren Sie das Paket 4.4.0.
3. Optional können Sie einen Trigger für den Upgrade-Auftrag für die Übersetzungskarte erstellen. Weitere Informationen finden Sie unter [Aktivieren des Skript-Triggers über ein Servlet](#enable-trigger-of-script-via-a-servlet).
4. Warten Sie nach Abschluss der Paketinstallation in den Protokollen auf die folgende Meldung:

   `Completed the post deployment setup script`

   Die obige Meldung weist darauf hin, dass alle Installationsschritte abgeschlossen sind.

   Falls Sie auf eines der folgenden FEHLER-Präfixe stoßen, melden Sie dies Ihrem Customer Success-Team:

   - `Error in post deployment setup script`
   - `Exception while porting the translation MAP`
   - `Unable to port translation map from v1 to v2 for property`
5. (Optional) Upgrade des Oxygen Connector-Plug-ins, das mit Version **4.4.0** veröffentlicht wurde.
6. Browser-Cache löschen.
7. Weiter mit:

   - [Häufige Aufgaben nach einem Upgrade (alle Versionen)](#common-ppostupgrade-tasks-all-versions)
   - [Vorhandenen Inhalt für Map suchen und ersetzen &#x200B;](#index-existing-content-for-map-find-and-replace)Nur falls zutreffend)
   - [Vorhandenen Inhalt für Bericht zu fehlerhaftem Link nachverarbeiten](#post-process-existing-content-for-broken-link-report) (Nur falls zutreffend)
   - [Upgrade der Übersetzungszuordnung (Servlet-Trigger)](#translation-map-upgrade-servlet-trigger) (Nur falls zutreffend)


## Häufige Aufgaben nach einem Upgrade (alle Versionen)

Nach der Installation von Experience Manager Guides müssen Sie möglicherweise die Konfigurationen der neu installierten Version mit Ihrem Setup zusammenführen.

>[!NOTE]
>
> Das **DAM Update Asset**-Workflow-Modell kann angepasst werden. Wenn Sie Anpassungen haben, synchronisieren Sie diese mit Experience Manager Guides-Änderungen in der Arbeitskopie des Modells.

### Workflow „DAM-Update-Asset validieren“ (Änderungen nach der Verarbeitung)

1. Öffnen Sie die Benutzeroberfläche AEM Workflow-Modelle (Beispiel aus der Quelle):\
   `http://<host>:4502/libs/cq/workflow/admin/console/content/models.html`
2. Wählen Sie **Workflow DAM-Update-Asset**.
3. Wählen Sie **Bearbeiten** aus.
4. Wenn die **DXML Post Process Initiator**-Komponente vorhanden ist, stellen Sie sicher, dass die Anpassungen synchronisiert werden.
5. Wenn die Komponente nicht vorhanden ist, fügen Sie sie ein:
   1. Klicken Sie **Komponente einfügen** (Verantwortlich für die Nachbearbeitung von Handbüchern als letzten Schritt).
   2. Konfigurieren Sie den **Prozessschritt**:
      **Registerkarte „Allgemein“**
- Titel: `DXML Post Process Initiator`
- Beschreibung: `DXML post process initiator step which will trigger a sling job for DXML post-processing of the modified/created asset`
      **Registerkarte „Prozess“**
- Prozess: `DXML Post Process Initiator` auswählen
- `Handler Advance` auswählen
- `Done` auswählen
   3. Klicken Sie **rechts oben** den Änderungen auf „Synchronisieren“. Sie erhalten eine Erfolgsbenachrichtigung.

>[!NOTE]
>
> Aktualisieren Sie und überprüfen Sie, ob benutzerdefinierte Änderungen und der Experience Manager Guides-Nachbearbeitungsschritt im endgültigen Workflow-Modell vorhanden sind.

### Validieren von Starter-Konfigurationen

1. Wechseln Sie zur Benutzeroberfläche des AEM-Workflows und öffnen Sie **Starter**.

```http
    http://localhost:4502/libs/cq/workflow/content/console.html
```

1. Suchen Sie die beiden folgenden Starter \(die aktiv sein sollten\) und nehmen Sie entsprechende Änderungen vor \(falls erforderlich\), die dem Workflow **DAM-Update-Asset entsprechen**:

1. Starter für &quot;*Knoten erstellt*&quot; für **Workflow DAM-Update-Asset**- für `"jcr:content/jcr:mimeType!=video"` sollte der Wert „Globbing“ sein:

   ```json
   /content/dam(/((?!/subassets|/translation_output).)*/)renditions/original
   ```

   - `excludeList` sollte `"event-user-data:changedByWorkflowProcess"` haben.
   - Starter für *Knoten geändert* für **DAM-Update-Asset-Workflow -** für Bedingung &quot;`jcr:content/jcr:mimeType!=video`&quot;, sollte der Wert „Globbing“ sein:

   ```json
   /content/dam(/((?!/subassets|/translation_output).)*/)renditions/original
   ```

   - `excludeList` sollte `"event-user-data:changedByWorkflowProcess"` haben.

### Überprüfen von Überlagerungen und Anpassungen

Nach Abschluss des Upgrades:

1. Nachdem das Upgrade abgeschlossen ist, stellen Sie sicher, dass alle Anpassungen/Überlagerungen validiert und aktualisiert werden, damit sie dem neuen Anwendungs-Code entsprechen. Im Folgenden finden Sie einige Beispiele:
   - Alle Komponenten, die von /libs/fmdidator/libs überlagert sind, sollten mit dem neuen Produkt-Code verglichen werden und Aktualisierungen sollten in überlagerten Dateien unter /apps vorgenommen werden.
   - Alle Client-Bibliothekskategorien, die vom Produkt verwendet werden, sollten auf Änderungen überprüft werden. Alle überschriebenen Konfigurationen \(Beispiele unten\) sollten mit den neuesten verglichen werden, um die neuesten Funktionen zu erhalten:
   - elementmapping.xml
   - ui\_config.json\(wurde möglicherweise in Ordnerprofilen festgelegt\)
   - geänderte `com.adobe.fmdita.config.ConfigManager`

1. Wenn Sie Anpassungen in damAssetLucene hinzugefügt haben, müssen Sie diese möglicherweise erneut anwenden. Nachdem Sie diese Änderungen vorgenommen haben, setzen Sie die Neuindizierung auf „true“. Dadurch werden alle vorhandenen Knoten mit den Anpassungen neu indiziert. Nach Abschluss wird das Neuindizierungs-Flag erneut auf „false“ gesetzt. Dies kann je nach Anzahl der Assets im System einige Stunden dauern.

## Vorhandenen Inhalt für Zuordnung zum Suchen und Ersetzen indizieren

In diesem Abschnitt wird das wiederholte **Indizierungsverfahren** zusammengefasst, das zum Aktivieren der neuen Funktionen **Suchen und Ersetzen auf** verwendet wird.

**Wenn Sie die Indizierung überspringen können**

Die Quelle enthält je nach Upgrade-Pfad „Überspringen“-Hinweise (z. B. „Sie müssen diese Schritte nicht ausführen, wenn Sie von 4.3.0 oder 4.3.1 aktualisieren“ und ähnliche Hinweise). Befolgen Sie die Anweisungen zum Überspringen im Upgrade-Abschnitt.

Führen Sie die folgenden Schritte aus, um den vorhandenen Inhalt zu indizieren und den neuen Text „Suchen und Ersetzen“ auf Zuordnungsebene zu verwenden:

1. Ausführen einer POST-Anfrage (mit Authentifizierung):

```http
POST http://<server:port>/bin/guides/map-find/indexing
```

Optionale Parameter, die in der Quelle unterstützt werden:

- Indexspezifische Zuordnungspfade (standardmäßig werden alle Zuordnungen indiziert):

  ```http
  POST http://<server:port>/bin/guides/map-find/indexing?paths=<map_path_in_repository>
  ```

- DITA-Index-Maps unter einem Stammordner (und dessen Unterordnern):

  ```http
  POST http://<server:port>/bin/guides/map-find/indexing?root=/content/dam/test
  ```

  >[!NOTE]
  >
  > Wenn sowohl `paths` als auch `root` übergeben werden, wird nur `paths` berücksichtigt.

1. Die -API gibt ein -`jobId` zurück. Um den Status zu überprüfen, senden Sie eine GET-Anfrage:

   ```http
   GET http://<server:port>/bin/guides/map-find/indexing?jobId={jobId}
   ```

   Erwartetes Abschlussverhalten:

   - Nach Abschluss antwortet GET mit Erfolg und gibt an, ob Zuordnungen fehlgeschlagen sind.
   - Bestätigen Sie die erfolgreich indizierten Zuordnungen in den Server-Protokollen.

### Sicherstellen, dass die damAssetLucene-Indizierung abgeschlossen ist (falls zutreffend)

Die Quelle merkt an, dass die damAssetLucene-Indizierung je nach Datengröße mehrere Stunden dauern kann. Sie können den Abschluss bestätigen, wenn `reindex` unter `false` wird:

`http://<server:port>/oak:index/damAssetLucene`

Wenn Sie in `damAssetLucene` Anpassungen hinzugefügt haben, müssen Sie diese möglicherweise nach Abschluss der Neuindizierung erneut anwenden.

### Problemumgehung für „Mehr als 100000 Knoten durch Abfrage lesen oder durchlaufen“ (wenn der Vorgang fehlschlägt)

Wenn der Indizierungsauftrag fehlschlägt und der Fehler angezeigt wird:

„Die Abfrage hat mehr als 100000 Knoten gelesen oder durchlaufen. Um andere Aufgaben nicht zu beeinträchtigen, wurde die Verarbeitung angehalten.“

Probieren Sie diese Problemumgehung aus der Quelle aus:

1. Fügen Sie im `damAssetLucene` Oak-Index die boolesche Eigenschaft `indexNodeName=true` in `/oak:index/damAssetLucene/indexRules/dam:Asset` hinzu.
2. Fügen Sie einen neuen Knoten mit dem Namen `excerpt` unter `/oak:index/damAssetLucene/indexRules/dam:Asset/properties` hinzu und legen Sie die Eigenschaften wie in der Quelle gezeigt fest:
   - `name=rep:excerpt`
   - `propertyIndex=true`
   - `notNullCheckEnabled=true`
3. Indizieren Sie `damAssetLucene` neu, indem Sie `reindex=true` festlegen und warten Sie, bis sie erneut `false` wird (kann Stunden dauern).
4. Führen Sie das Indizierungsskript erneut aus (wiederholen Sie den POST-Test und das Job-Tracking).

## Vorhandenen Inhalt für Bericht zu fehlerhaftem Link nachverarbeiten

In diesem Abschnitt wird das wiederholte **Nachbearbeitungsverfahren** zusammengefasst, das zum Aktivieren des **Berichts über fehlerhafte Links** verwendet wird.

**Wann Sie die Nachbearbeitung überspringen können**

Die Quelle enthält je nach Upgrade-Pfad „Überspringen“-Hinweise (z. B. „Sie müssen diese Schritte nicht ausführen, wenn Sie von 4.3.0 oder 4.3.1 aktualisieren„). Befolgen Sie die Anweisungen zum Überspringen im Upgrade-Abschnitt.

Führen Sie die folgenden Schritte aus, um den Bericht „Beschädigter Link“ zu aktivieren:

1. (Optional) Erhöhen von Oak queryLimitReads für große Repositorys

   Wenn mehr als **100.000 DITA-Dateien vorhanden sind** aktualisieren Sie `queryLimitReads` unter `org.apache.jackrabbit.oak.query.QueryEngineSettingsService` auf einen Wert, der größer ist als die Anzahl der Assets (Beispiel: `200000`), stellen Sie erneut bereit und fahren Sie fort.

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

## Aktivieren des Skript-Triggers über ein Servlet

Mehrere Versionen enthalten einen optionalen Schritt zum Trigger eines Übersetzungszuordnungs-Upgrade-Auftrags über ein Servlet. Dieser Abschnitt konsolidiert dieses wiederholte Verfahren und enthält alle Details, die in der Quelle angegeben sind.


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


### Schritte zum Umgang mit dem „fmedia rewriter“-Konflikt

Experience Manager Guides enthält ein benutzerdefiniertes Sling Rewriter-Modul (`fmditarewriter`) für die Verarbeitung von Links, die für Cross-Map-Links generiert wurden.

Wenn Sie einen anderen benutzerdefinierten Sling-Rewriter in Ihrer Codebasis haben:

- Verwenden Sie einen `order` Wert **größer als 50** da Guides `order=50` verwenden.
- Während dieses Upgrades ändert sich der `order` von `1000` in `50`. Daher müssen Sie Ihren vorhandenen benutzerdefinierten Rewriter (falls vorhanden) mit `fmditarewriter` zusammenführen.

