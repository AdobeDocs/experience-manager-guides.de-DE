---
title: Migration von Nicht-UUID-zu-UUID-Inhalten
description: Erfahren Sie, wie Sie Nicht-UUID-Inhalte in UUID-Inhalte migrieren.
feature: Migration
role: Admin
level: Experienced
source-git-commit: d721c263384703f8b4db7c6cfed7d54fa77ac42b
workflow-type: tm+mt
source-wordcount: '1503'
ht-degree: 2%

---

# Migration von Nicht-UUID-zu-UUID-Inhalten {#id226TI0U20XA}


Führen Sie diese Schritte aus, um Ihren Inhalt von Nicht-UUID-Version 4.3.1 auf UUID-Version 4.3.2 zu migrieren.

>[!IMPORTANT]
>
> * Bevor Sie den Migrationsprozess starten, stellen Sie Folgendes sicher:
>
>   1. Alle aktiven Rezensionen wurden geschlossen.
>   1. Alle Übersetzungsaufgaben wurden geschlossen.
> * Bevor Sie Inhalte auf den UUID-Server migrieren, stellen Sie sicher, dass auf dem Server ein Nicht-UUID-Server mit einer kompatiblen AEM Guides-Version installiert ist.
> * Wenn Sie eine Version vor 4.3.1 verwenden, aktualisieren Sie auf Version 4.3.1. Befolgen Sie die [Upgrade-Anweisungen](./upgrade-xml-documentation.md) speziell für die lizenzierte Version Ihres Produkts.
> * Derzeit werden Versionen, die älter als 4.3.1 sind, für die Migration nicht unterstützt.


## Paketinstallation

Laden Sie die erforderlichen Pakete von Adobe Software Distribution Portal herunter, je nach Version:


1. **Vormigration**: [com.adobe.guides.pre-uuid-migration-1.2.27.zip](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html?package=%2Fcontent%2Fsoftware-distribution%2Fen%2Fdetails.html%2Fcontent%2Fdam%2Faem%2Fpublic%2Faemdox%2Fother-packages%2Fuuid-migration%2F3-0%2Fcom.adobe.guides.pre-uuid-migration-1.2.27.zip)
1. **UUID-Version 4.3.2**: [com.adobe.fmdita-6.5-uuid-4.3.2.1977.zip](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html?package=%2Fcontent%2Fsoftware-distribution%2Fen%2Fdetails.html%2Fcontent%2Fdam%2Faem%2Fpublic%2Faemdox%2Fother-packages%2Fuuid-migration%2F3-0%2Fcom.adobe.fmdita-6.5-uuid-4.3.2.1977.zip)
1. **Migration**: [com.adobe.guides.uuid-upgrade-1.2.110.zip](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html?package=%2Fcontent%2Fsoftware-distribution%2Fen%2Fdetails.html%2Fcontent%2Fdam%2Faem%2Fpublic%2Faemdox%2Fother-packages%2Fuuid-migration%2F3-0%2Fcom.adobe.guides.uuid-upgrade-1.2.110.zip)

## Vorab-Prüfungen

Führen Sie die folgenden Prüfungen für Nicht-UUID-Version 4.3.1 durch:

1. Installieren Sie das Vormigrationspaket [com.adobe.guides.pre-uuid-migration-1.2.27.zip](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html?package=%2Fcontent%2Fsoftware-distribution%2Fen%2Fdetails.html%2Fcontent%2Fdam%2Faem%2Fpublic%2Faemdox%2Fother-packages%2Fuuid-migration%2F3-0%2Fcom.adobe.guides.pre-uuid-migration-1.2.27.zip) über Version 4.3.1.

   >[!NOTE]
   >
   >* Sie benötigen Administratorrechte, um die Migration ausführen zu können.
   >* Es wird empfohlen, die Dateien mit Fehlern zu beheben, bevor Sie mit der Migration fortfahren.

1. Wenn mehr als 100.000 DITA-Dateien im System vorhanden sind, aktualisieren Sie die Konfigurationen für die Abfragebegrenzung, damit das Skript funktioniert:

   * Navigieren Sie zu `/system/console/configMgr and increase both the configs to more than number of assets - queryLimitInMemory` und `queryLimitReads under org.apache.jackrabbit.oak.query.QueryEngineSettingsService`

1. Starten Sie `http://<server-name>/libs/fmdita/clientlibs/xmleditor_uuid_upgrade/page.html`.
1. Wählen Sie im linken Bereich die Option **Kompatibilitätsbewertung** aus und durchsuchen Sie den Ordnerpfad für alle Assets.`/content/dam`
1. Überprüfen Sie die Kompatibilität, um die folgenden Informationen aufzulisten:
   * Gesamtzahl der Dateien
   * Geschätzte Migrationszeit
   * Fehlerfreie Dateien
   * Dateien mit GUID-Dateinamen

   Registerkarte ![Kompatibilitätsbewertung bei Migration](assets/migration-compatibility-assessment.png)


1. Wenn der Fehler auftritt, analysieren Sie die Protokolle und beheben Sie diese Fehler. Sie können die Kompatibilitätsmatrix erneut ausführen, nachdem Sie die Fehler behoben haben.

1. Wählen Sie im linken Bereich **Überprüfungen konfigurieren** aus. Wählen Sie dann **map** und **preset** der Zuordnung aus, um sie zu konfigurieren. In der aktuellen Liste der Ausgabeprüfungen werden die vor der Migration vorhandenen Ausgabedateien angezeigt. Sie können anhand der Ausgabedateien validiert werden, die nach der Migration generiert wurden.

   Durch die Auswahl mehrerer und großer DITA-Maps können Sie überprüfen, ob der gesamte Inhalt ohne Probleme erfolgreich migriert wurde. Durch die Auswahl von Vorgaben mit Grundlinien wird außerdem sichergestellt, dass Grundlinien und Versionen erfolgreich migriert werden.

   ![Registerkarte &quot;Überprüfungen konfigurieren&quot;bei der Migration](assets/migration-configure-validation.png)


1. (Optional) Führen Sie eine Versionsbereinigung für den Inhalt durch, um unnötige Versionen zu entfernen und den Migrationsprozess zu beschleunigen. Um die Versionsbereinigung durchzuführen, wählen Sie im Migrationsbildschirm die Option **Versionsbereinigung** aus und wechseln Sie mithilfe der URL `http://<server- name>/libs/fmdita/clientlibs/xmleditor_uuid_upgrade/page.html` zur Benutzeroberfläche.
   >[!NOTE]
   >
   >Dieses Dienstprogramm entfernt keine Versionen, die in Grundlinien- oder Rezensionen verwendet werden, oder hat Beschriftungen.

Weitere Informationen finden Sie unter [Löschen älterer Versionen](../install-guide/version-management.md#purge-older-versions-of-dita-files).


## Migrationsvoraussetzungen

1. Führen Sie die UUID-Migration nur auf einer Autoreninstanz aus.
1. Stellen Sie sicher, dass die folgende Infrastruktur bereit ist:
   * Die Autoreninstanz wird in Bezug auf CPU und Speicher aktualisiert, um eine schnellere Verarbeitung und zusätzlichen Speicher zu unterstützen, der für Massenaktivitäten benötigt wird. Wenn die aktuell zugewiesene CPU und der Arbeitsspeicher beispielsweise 8 vCPU und 24 GB Heap sind, verwenden Sie für diese Aktivität die doppelte Größe.
   * Der gesamte Festplattenspeicher und der temporäre Speicherplatz `(crx-quickstart directory)` sollten einen Puffer von 10-mal so viel haben, wie bereits belegt ist. Nachdem Sie die Migration abgeschlossen haben, können Sie den Großteil des Festplattenspeichers durch Ausführen der Komprimierung zurückgewinnen.
   * Führen Sie **Offline-Tar-Verdichtung** aus, bevor Sie diese Aktivität starten.
   * Stellen Sie sicher, dass während des Fensters dieser Migration keine Indizierung oder Systemwartung geplant ist.

1. Installieren Sie die UUID-Version der unterstützten Version über die Nicht-UUID-Version. Wenn Sie z. B. den Nicht-UUID-Build 4.3.1 verwenden, müssen Sie die UUID-Version 4.3.2 [com.adobe.fmdita-6.5-uid-4.3.2.1977.zip](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html?package=%2Fcontent%2Fsoftware-distribution%2Fen%2Fdetails.html%2Fcontent%2Fdam%2Faem%2Fpublic%2Faemdox%2Fother-packages%2Fuuid-migration%2F3-0%2Fcom.adobe.fmdita-6.5-uuid-4.3.2.1977.zip)) installieren und die Migration ausführen.


1. Installieren Sie das uuid migration upgrade package [com.adobe.guides.uuid-upgrade-1.2.110.zip](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html?package=%2Fcontent%2Fsoftware-distribution%2Fen%2Fdetails.html%2Fcontent%2Fdam%2Faem%2Fpublic%2Faemdox%2Fother-packages%2Fuuid-migration%2F3-0%2Fcom.adobe.guides.uuid-upgrade-1.2.110.zip).
1. Deaktivieren Sie Starter für die folgenden Workflows mithilfe der URL: `http://<server-name>/libs/cq/workflow/content/console.html`.

   * Workflow „DAM-Update-Asset“
   * DAM-Metadaten-Writeback-Workflow

   >[!NOTE]
   >
   >Idealerweise sollten alle Workflow-Starter, die auf einem beliebigen Pfad innerhalb von `content/dam` ausgeführt werden, deaktiviert werden.

1. Aktualisieren Sie die folgenden Konfigurationen gemäß den vorgeschlagenen Änderungen:

   | Konfiguration | Eigenschaft | Wert |
   |---|---|---|
   | `com.adobe.fmdita.config.ConfigManager` | Aktivieren von Workflow-Startern für Nachbearbeitung | Deaktivieren |
   | `com.adobe.fmdita.config.ConfigManager` | uuid. regex | `^GUID-(?<id>.*)` |
   | `com.adobe.fmdita.postprocess.version.PostProcessVersionObservation` | Aktivieren der Versionspostverarbeitung | Deaktivieren |
   | Day CQ Tagging Service | Validierung aktivieren (validation.enabled) | Deaktivieren |

1. Fügen Sie eine separate Protokollfunktion für hinzu:
   * `com.adobe.fmdita.uuid`
   * `com.adobe.guides.uuid`.


1. (Wenn nicht bereits geschehen) Wenn mehr als 100.000 DITA-Dateien im System vorhanden sind, aktualisieren Sie die `queryLimitReads` unter `org.apache.jackrabbit.oak.query.QueryEngineSettingsService` auf einen größeren Wert (ein beliebiger Wert, der größer ist als die Anzahl der vorhandenen Assets, z. B. 200.000).

   | PID | Eigenschaftenschlüssel | Eigenschaftswert |
   |---|---|---|
   | org.apache.jackrabbit.oak.query.QueryEngineSettingsService | queryLimitReads | Wert: 200000 <br> Standardwert: 10000 |

## Migration

1. Starten Sie `http://<server-name>/libs/fmdita/clientlibs/xmleditor_uuid_upgrade/page.html`.

   ![Registerkarte &quot;Systemaktualisierung&quot;bei der Migration](assets/migration-system-upgrade.png)
   >[!NOTE]
   >
   > Wenn Sie &quot;DITA-Asset-Sicherung aktivieren&quot;auswählen, werden die temporären Backup-Dateien unter &quot;`/content/uuid-upgrade`&quot;gespeichert und die DITA-Dateisicherungen werden gelöscht, wenn die Migration einer Datei abgeschlossen ist.


1. Wählen Sie im linken Bereich die Option **Systemaktualisierung** aus, um die Migration auszuführen. Es wird empfohlen, alle Daten gleichzeitig zu migrieren, da das System die Stapelverarbeitung intern optimal handhabt. Nur Dateien, die keine DITA-Assets sind und in keinen DITA-Assets verwendet werden, können zur Migration übersprungen werden.

1. (Optional) Wählen Sie die Ordner aus, für die Sie die Migration überspringen möchten. Verwenden Sie diese Option, um diese Ordner später zu migrieren oder die Migration zu überspringen. Stellen Sie sicher, dass diese Ordner keine DITA-Assets aufweisen und nicht von DITA-Assets referenziert werden (und zukünftig nicht von referenziert werden). Zum Beispiel: `content/dam/projects`.

1. Wählen Sie *Dia Asset-Sicherung aktivieren* aus, um vor der Migration eine Asset-Sicherung zu erstellen. Diese Sicherung wird für das Rollback verwendet, falls bei der Migration einer Datei ein Fehler auftritt. Die Sicherung wird gelöscht, wenn die Migration erfolgreich war. Dies verlangsamt jedoch den Migrationsprozess.

1. Starten Sie die Migration.
   >[!NOTE]
   >
   > Laden Sie die vollständigen Protokolle herunter und beobachten Sie, ob Fehler aufgetreten sind. Wenn ein Fehler oder eine Ausnahme gefunden wird *Fahren Sie nicht fort*, beheben Sie jedoch zuerst den Fehler. Häufige Fehler werden am Ende dieses Artikels aufgelistet.

1. Sobald die Migration abgeschlossen ist, steht der Bericht zum Herunterladen zur Verfügung und komplette Protokolle können ebenfalls heruntergeladen werden.

1. Wählen Sie **Bericht herunterladen** , während die Migration ausgeführt wird, um zu überprüfen, ob alle Dateien im Ordner korrekt aktualisiert wurden und ob alle Funktionen nur für diesen Ordner funktionieren.


   >[!NOTE]
   >
   > Die Inhaltsmigration kann auf Ordnerebene, dem vollständigen Tag `/content/dam` oder im selben Ordner ausgeführt werden (Neuausführung der Migration).

   Außerdem muss sichergestellt werden, dass die Inhaltsmigration für alle Medien-Assets erfolgt, z. B. für Bilder und Grafiken, die Sie im DITA-Inhalt verwendet haben.

1. Nachdem alle Dateien migriert wurden, wählen Sie im linken Bereich die Option **Grundlinien-/Überprüfungsaktualisierung** aus, um die Grundlinien zu migrieren und auf Ordnerebene zu überprüfen.

![Registerkarte &quot;Grundlinie und Überprüfung&quot;in der Migration](assets/migration-baseline-review-upgrade.png)

>[!NOTE]
>
>Wenn Sie das System neu starten oder die Migration abgebrochen wird, wird das Skript fortgesetzt, wenn Sie es mit denselben Parametern wie zuvor erneut ausführen. Wenden Sie sich an Ihr Customer Success Team, wenn Probleme aufgrund des Herunterfahrens auftreten.

## Berichte aus jedem Schritt analysieren

**Schritt: Systemaktualisierung**

| Zusammenfassung nach Abschluss des Prozesses | Wie kann ich interpretieren? | Aktion |
|---|---|---|
| Gesamtzahl der Dateien: 345997 | Gesamtzahl der Dateien, die unter dem angegebenen Ordnersatz verarbeitet wurden. | nicht vorhanden |
| Anzahl der erfolgreich aktualisierten Dateien: 344516 | Anzahl der erfolgreich in UUID migrierten Dateien. | nicht vorhanden |
| Anzahl der fehlerhaften Dateien: 29 | In diesen Dateien sind Fehler aufgetreten und sollten mit denen im Vormigrationsschritt berichtet werden. | nicht vorhanden |
| Anzahl der übersprungenen Dateien: 1452 | Einige Dateien im DAM-Repository verfügen möglicherweise über Teil-Assets, und diese Teil-Assets werden übersprungen, da sie nicht für die UUID-Migration infrage kommen. | nicht vorhanden |
| Anzahl der Dateien, die nicht aktualisiert werden konnten: 0 | Wenn die Anzahl nicht 0 beträgt, müssen die Protokolle auf Probleme analysiert werden. | Überprüfen Sie die Ausnahme. Möglicherweise müssen Sie den Fehler beheben und die Migration erneut ausführen. |
| Gesamtbesuchszeit: 2:40:06.157 |  |  |

**Schritt: Upgrade der Grundlinien**

| Zusammenfassung nach Abschluss des Prozesses | Wie kann ich interpretieren? | Aktion |
|---|---|---|
| Gesamtzahl der Dateien: 4833 | Anzahl der DITA-Maps mit mindestens 1 Grundlinie. |
| Anzahl der erfolgreich aktualisierten Dateien: 4705 | Anzahl der DITA-Maps, erfolgreich mit allen Grundlinien aktualisiert. |
| Anzahl der fehlerhaften Dateien: 0 | Anzahl der DITA-Maps, deren Grundlinien nicht aktualisiert wurden. |
| Anzahl der übersprungenen Dateien: 1647 | Anzahl der DITA-Maps ohne Grundlinie. |
| Anzahl der Dateien, die nicht aktualisiert werden konnten: 128 | Die Anzahl der Grundlinien-Objekte, die nicht gültig waren (sie waren leer), wird im Bericht (Excel) aufgeführt. | Überprüfen Sie, ob andere Fehler als: `baselineObj not found on` vorliegen. |


## Postmigration

1. Nachdem die Migration abgeschlossen ist, wählen Sie im linken Bereich die Option **Systemaktualisierung überprüfen** aus und validieren Sie die Ausgabedateien vor und nach der Migration, um sicherzustellen, dass die Migration erfolgreich ist.

   ![Registerkarte &quot;Systemaktualisierung bei Migration überprüfen&quot;](assets/migration-validate-system-upgrade.png)

1. Nach der erfolgreichen Migration des Servers können Sie die folgenden Workflows und Konfigurationen (einschließlich aller anderen Workflows, die während der Migration ursprünglich deaktiviert wurden) aktivieren, um weiterhin auf dem Server zu arbeiten:

   * Workflow „DAM-Update-Asset“
   * DAM-Metadaten-Workflow

   >[!NOTE]
   >
   >Idealerweise alle Workflow-Starter, die auf einem beliebigen Pfad innerhalb von `content/dam` ausgeführt wurden, bevor die Migration aktiviert werden sollte.

1. Aktivieren Sie die folgenden Konfigurationen:

   | Konfiguration | Eigenschaft | Wert |
   |---|---|---|
   | `com.adobe.fmdita.config.ConfigManager` | *Aktivieren der Workflow-Starter für die Nachbearbeitung* | Aktivieren |
   | `com.adobe.fmdita.postprocess.version.PostProcessVersionObservation` | *Aktivieren der Versionspostverarbeitung* | Aktivieren |
   | Day CQ Tagging Service | *Validierung aktivieren (validation.enabled)* | Aktivieren |

1. Assets-Eigenschaften zum Überprüfen der Post-Migration:

   | Konfiguration | Eigenschaft | Vormigrationswert für Nicht-UUID | Wert nach der Migration auf UUID |
   |---|---|---|---|
   | `com.adobe.fmdita.config.ConfigManager` | **Verwenden Sie den Titel für AEM Seitennamen der Site** | False (Standardwert) | True |

   >[!NOTE]
   >
   > Wenn vor der Migration die Eigenschaft **Titel für Seitennamen AEM Site verwenden** innerhalb von `com.adobe.fmdita.config.ConfigManager` auf *False* festgelegt ist, muss diese Eigenschaft nach der Migration aktualisiert werden.

1. Nach Abschluss der Validierung kann der Großteil des Festplattenspeichers durch Ausführen der Komprimierung zurückgewonnen werden (siehe `https://experienceleague.adobe.com/docs/experience-manager-65/deploying/deploying/revision-cleanup.html?lang=en`).