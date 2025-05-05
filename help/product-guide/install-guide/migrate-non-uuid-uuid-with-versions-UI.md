---
title: Konvertieren von Nicht-UUID-Inhalten mit Versionen in UUID-Inhalte über die Benutzeroberfläche
description: Erfahren Sie, wie Sie Nicht-UUID-Inhalte mit Versionen 4.3.x migrieren.
source-git-commit: f18c19eb493cd4d2003f68b082e71ebe7b3e6b7a
workflow-type: tm+mt
source-wordcount: '688'
ht-degree: 1%

---

# Migrieren von Nicht-UUID-Inhalten mit Versionen über die Benutzeroberfläche

Wenn Sie Version 4.3.x oder höher verwenden, führen Sie diese Schritte aus, um Ihren Nicht-UUID-Inhalt mit Versionen auf UUID-Inhalt zu migrieren.

## Kompatibilitätsmatrix

| Aktuelle AEM Guides-Version (nicht UUID) | Erforderliche Version für die Migration zu UUID | Unterstützter Aktualisierungspfad |
|---|---|---|
| 4.3.x oder höher | 4.3.0 non-UUID | Installieren von 4.3.1 (UUID) |

## Erforderliche Pakete

1. **Versionsbereinigung**: `com.adobe.guides.version-purge-1.0.11.zip` (optional)
1. **Vor der Migration**: `com.adobe.guides.pre-uuid-migration-1.1.2 .zip`
1. **Migration**: `com.adobe.guides.uuid-upgrade-1.1.13.zip`



## Vor der Migration

1. (Optional) Führen Sie eine Versionsbereinigung für den Inhalt durch, um unnötige Versionen zu entfernen und den Migrationsprozess zu beschleunigen. Um eine Versionsbereinigung unter Version 4.1 durchzuführen (in 4.0 NICHT unterstützt), installieren Sie das Paket `com.adobe.guides.version-purge-1.0.11.zip` und navigieren Sie zur Benutzeroberfläche über diese URL-`http://<server-name> /libs/fmdita/clientlibs/xmleditor_version_purge/page.html`.

   >[!NOTE]
   >
   >Dieses Dienstprogramm entfernt keine Versionen, die in Baselines oder Reviews verwendet werden, und hat keine Kennzeichnungen.
1. Installieren Sie das Paket vor der Migration (`ccom.adobe.guides.pre-uuid-migration-1.1.2 .zip`).

   >[!NOTE]
   >
   >* Sie benötigen Administratorrechte, um die Migration auszuführen.
   >* Es wird empfohlen, die Dateien mit Fehlern zu beheben, bevor Sie mit der Migration fortfahren.

1. Wählen Sie **Kompatibilitätsbewertung** im linken Bedienfeld aus und durchsuchen Sie einen Ordnerpfad.
1. Überprüfen Sie die Kompatibilität , um die folgenden Informationen aufzulisten:
   * Gesamtzahl der Dateien
   * Versionen insgesamt
   * Geschätzte Migrationszeit
   * Anzahl fehlerhafter Dateien



![Registerkarte „Kompatibilitätsbewertung“ in der Migration](assets/migration-compatibility-assessment.png){width="800" align="left"}


1. Wählen **im linken Bedienfeld** Validierungen konfigurieren“ aus. Wählen **anschließend &quot;**&quot; und **Voreinstellung auswählen** der Zuordnung aus, um sie zu konfigurieren. In der Liste der aktuellen Ausgabevalidierungen werden die vor der Migration vorhandenen Ausgabedateien angezeigt und sie können anhand der Ausgabedateien validiert werden, die nach der Migration generiert werden.

![Registerkarte „Validierungen“ in der Migration konfigurieren](assets/migration-configure-validation.png){width="800" align="left"}




## Migration

### Schritt 1: Konfiguration aktualisieren

1. Stellen Sie sicher, dass der verfügbare Speicherplatz mindestens 10-mal so groß ist wie der von AEM während der Migration belegte (CRX-Schnellstartordner). Nach Abschluss der Migration können Sie den Großteil des Festplattenspeichers zurückgewinnen, indem Sie die Komprimierung ausführen (siehe [Revisionsbereinigung](https://experienceleague.adobe.com/docs/experience-manager-65/deploying/deploying/revision-cleanup.html?lang=de)).

1. Aktivieren *Startprogramme für Nachbearbeitungs-Workflows aktivieren* in `com.adobe.fmdita.config.ConfigManager` und *Versionsnachbearbeitung aktivieren* in `com.adobe.fmdita.postprocess.version.PostProcessVersionObservation.`

1. Installieren Sie die UUID-Version der unterstützten Version gegenüber der Nicht-UUID-Version. Wenn Sie beispielsweise einen 4.0-Build ohne UUID oder einen 4.1-Build ohne UUID verwenden, müssen Sie UUID Version 4.1 installieren.

1. Installieren Sie das neue Paket für die UUID-Migration (`com.adobe.guides.uuid-upgrade-1.1.13`).

1. Deaktivieren Sie die folgenden Workflows und alle anderen Workflows, die auf `/content/dam` ausgeführt werden, indem Sie in `http://localhost:4502/libs/cq/workflow/content/console.html` Starter verwenden.

   * Workflow „DAM-Update-Asset“
   * Workflow „DAM-Metadaten-Writeback“

1. Deaktivieren Sie *Starter des Nachbearbeitungs-Workflows aktivieren* in `com.adobe.fmdita.config.ConfigManager` und deaktivieren Sie *Versionsnachbearbeitung aktivieren* in `com.adobe.fmdita.postprocess.version.PostProcessVersionObservation`.

1. Deaktivieren Sie die Eigenschaft Validierung aktivieren (`validation.enabled`) im Day CQ-Tagging-Service.

1. Stellen Sie sicher, dass `uuid.regex` Eigenschaftenordner in `com.adobe.fmdita.config.ConfigManager` ordnungsgemäß festgelegt ist. Wenn es leer ist, setzen Sie es auf den Standardwert - `^GUID-(?<id>.*)`.
1. Fügen Sie einen separaten Logger für `com.adobe.fmdita.uuid.upgrade.UuidUpgrade` hinzu. Die Browser-Antwort ist auch unter verfügbar`/content/uuid-upgrade/logs`.

### Schritt 2: Migration ausführen und validieren

#### Installieren des Migrationspakets

![Registerkarte „System-Upgrade“ bei der Migration](assets/migration-system-upgrade.png){width="800" align="left"}

* Wählen Sie **linken Bedienfeld** System-Upgrade“ aus, um die Migration auszuführen. Beginnen Sie mit einem Ordner mit kleineren Daten, bevor Sie ihn auf `/content/dam` ausführen.

* Wählen Sie **Bericht herunterladen** während der Migration aus, um zu überprüfen, ob alle Dateien im Ordner korrekt aktualisiert wurden und ob alle Funktionen nur für diesen Ordner funktionieren.


>[!NOTE]
>
> Die Inhaltsmigration kann auf Ordnerebene, im vollständigen `/content/dam` oder im selben Ordner ausgeführt werden (Migration erneut ausführen).

Darüber hinaus müssen Sie sicherstellen, dass die Inhaltsmigration auch für alle Medien-Assets durchgeführt wird, z. B. für Bilder und Grafiken, die Sie im DITA-Inhalt verwendet haben.

#### Baseline und Migration überprüfen

Wählen Sie **Baseline/Review-Upgrade** im linken Bereich aus, um die Baselines zu migrieren und auf Ordnerebene zu überprüfen.

![Registerkarte „Baseline und Überprüfung“ bei der Migration](assets/migration-baseline-review-upgrade.png){width="800" align="left"}


### Schritt 3: Wiederherstellen der Konfiguration

Wenn der Server erfolgreich migriert wurde, aktivieren Sie Nachbearbeitung, Tagging und die folgenden Workflows (einschließlich aller anderen Workflows, die anfänglich während der Migration deaktiviert wurden), um weiterhin auf dem Server zu arbeiten.

* Workflow „DAM-Update-Asset“
* Workflow „DAM-Metadaten“

>[!NOTE]
>
>Wenn einige Dateien vor der Migration nicht verarbeitet oder beschädigt werden und sie vor der Migration beschädigt werden und auch nach der Migration beschädigt bleiben.

## Validierung der Migration

Wählen Sie nach Abschluss der Migration im linken Bereich die Option **Systemaktualisierung überprüfen** und validieren Sie die Ausgabedateien vor und nach der Migration, um sicherzustellen, dass die Migration erfolgreich ist.

![Registerkarte „Systemaktualisierung überprüfen“ bei der Migration](assets/migration-validate-system-upgrade.png){width="800" align="left"}


1. Nach Abschluss der Migration kann der größte Teil des Festplattenspeichers durch Ausführen der Komprimierung zurückgewonnen werden (siehe `https://experienceleague.adobe.com/docs/experience-manager-65/deploying/deploying/revision-cleanup.html?lang=de`).

