---
title: Konvertieren von Nicht-UUID-Inhalten mit Versionen in UUID-Inhalt
description: Erfahren Sie, wie Sie Nicht-UUID-Inhalte mit Versionen zu UUID-Inhalten migrieren.
source-git-commit: b4ba381cad13960f2fd514b23c66016f0e08e273
workflow-type: tm+mt
source-wordcount: '755'
ht-degree: 1%

---

# Migrieren versionierter Inhalte

Führen Sie diese Schritte aus, um Inhalte ohne UUID-Version in UUID-Inhalte zu migrieren.

>[!NOTE]
>
>Befolgen Sie die [Upgrade-Anweisungen](./upgrade-xml-documentation.md) spezifisch für die lizenzierte Version Ihres Produkts.

## Kompatibilitätsmatrix

| Aktuelle Version der Experience Manager-Handbücher (nicht UUID) | Erforderliche Version für die Migration zu UUID | Unterstützter Aktualisierungspfad |
|---|---|---|
| 3.8.5, 4.0.x oder 4.1.x | 4.1 Nicht-UUID | Installieren Sie 4.1 (UUID) und führen Sie die Migration aus. |
| 4.2, 4.2.x oder 4.3 | 4.3.0 Nicht-UUID | Installieren Sie 4.3.1 (UUID) und führen Sie die Migration aus. |
| 4.3.1 | nicht vorhanden | nicht vorhanden |

## Paketinstallation

Laden Sie die erforderlichen Pakete von Adobe Software Distribution Portal herunter, je nach Version:
<details>
<summary>  Pakete für den Aktualisierungspfad der Version 4.1</summary>

1. **Vormigration**: [com.adobe.guides.pre-uuid-migration-1.0.9.zip](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html?package=%2Fcontent%2Fsoftware-distribution%2Fen%2Fdetails.html%2Fcontent%2Fdam%2Faem%2Fpublic%2Faemdox%2Fother-packages%2Fuuid-migration%2F1-0%2Fcom.adobe.guides.pre-uuid-migration-1.0.9.zip)
1. **Migration**: [com.adobe.guides.uuid-upgrade-1.0.19.zip](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html?package=%2Fcontent%2Fsoftware-distribution%2Fen%2Fdetails.html%2Fcontent%2Fdam%2Faem%2Fpublic%2Faemdox%2Fother-packages%2Fuuid-migration%2F1-0%2Fcom.adobe.guides.uuid-upgrade-1.0.19.zip)
</details>


<details>
<summary> Pakete für den Aktualisierungspfad der Version 4.3.1</summary>

1. **Vormigration**: [com.adobe.guides.pre-uuid-migration-1.1.3.zip](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html?package=%2Fcontent%2Fsoftware-distribution%2Fen%2Fdetails.html%2Fcontent%2Fdam%2Faem%2Fpublic%2Faemdox%2Fother-packages%2Fuuid-migration%2Fcom.adobe.guides.pre-uuid-migration-1.1.3.zip)
1. **Migration**: [com.adobe.guides.uuid-upgrade-1.1.15.zip](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html?package=%2Fcontent%2Fsoftware-distribution%2Fen%2Fdetails.html%2Fcontent%2Fdam%2Faem%2Fpublic%2Faemdox%2Fother-packages%2Fuuid-migration%2Fcom.adobe.guides.uuid-upgrade-1.1.15.zip)

</details>

## Vormigration

Führen Sie die folgenden Prüfungen für die Nicht-UUID-Version durch (4.1 Nicht-UUID oder 4.3.0 Nicht-UUID):

1. Installieren Sie das Vormigrationspaket entsprechend Ihrer Version.

   >[!NOTE]
   >
   >* Sie benötigen Administratorrechte, um die Migration ausführen zu können.
   >* Es wird empfohlen, die Dateien mit Fehlern zu beheben, bevor Sie mit der Migration fortfahren.

1. (Optional) Führen Sie eine Versionsbereinigung für den Inhalt durch, um unnötige Versionen zu entfernen und den Migrationsprozess zu beschleunigen. Um die Versionsbereinigung durchzuführen, wählen Sie die Option **Versionsbereinigung** vom Migrationsbildschirm aus und rufen Sie die Benutzeroberfläche mit der URL auf `http://<server- name>/libs/fmdita/clientlibs/xmleditor_uuid_upgrade/page.html`.
   >[!NOTE]
   >
   >Dieses Dienstprogramm entfernt keine Versionen, die in Grundlinien- oder Rezensionen verwendet werden, oder hat Beschriftungen.
1. Launch `http://<server-name>/libs/fmdita/clientlibs/xmleditor_uuid_upgrade/page.html`.
1. Auswählen **Kompatibilitätsbewertung**  aus dem linken Bedienfeld aus und durchsuchen Sie einen Ordnerpfad.
1. Überprüfen Sie die Kompatibilität, um die folgenden Informationen aufzulisten:
   * Dateien insgesamt
   * Versionen insgesamt
   * Geschätzte Migrationszeit
   * Fehlerfreie Dateien

   ![Registerkarte &quot;Kompatibilitätsbewertung&quot;der Migration](assets/migration-compatibility-assessment.png){width="800" align="left"}


1. Auswählen **Validierungen konfigurieren** aus dem linken Bereich. Dann **Zuordnung auswählen** und **Vorgabe auswählen** der Karte, um sie zu konfigurieren. In der aktuellen Liste der Ausgabeprüfungen werden die vor der Migration vorhandenen Ausgabedateien angezeigt. Sie können anhand der Ausgabedateien validiert werden, die nach der Migration generiert wurden.

   ![Registerkarte &quot;Überprüfungen&quot;bei der Migration konfigurieren](assets/migration-configure-validation.png){width="800" align="left"}




## Migration

### Schritt 1: Konfiguration aktualisieren

1. Stellen Sie sicher, dass der verfügbare freie Speicherplatz mindestens zehnmal so groß ist wie der Speicherplatz, den AEM (crx-quickstart-Verzeichnis) während der Migration benötigt. Nach Abschluss der Migration können Sie den Großteil des Festplattenspeichers durch Ausführung der Komprimierung zurückgewinnen (siehe [Revisionsbereinigung](https://experienceleague.adobe.com/docs/experience-manager-65/deploying/deploying/revision-cleanup.html?lang=de)).

1. Aktivieren *Aktivieren von Workflow-Startern für Nachbearbeitung* in `com.adobe.fmdita.config.ConfigManager` und *Aktivieren der Versionspostverarbeitung* in `com.adobe.fmdita.postprocess.version.PostProcessVersionObservation.`

1. Installieren Sie die UUID-Version der unterstützten Version über die Nicht-UUID-Version. Wenn Sie beispielsweise den Build 4.1 non-UUID verwenden, müssen Sie UUID Version 4.1 installieren und die Migration ausführen.

1. Installieren Sie das neue Paket für die UUID-Migration.

1. Deaktivieren Sie die folgenden Workflows und jeden anderen Workflow, der ausgeführt wird `/content/dam` Verwenden von Startern in `http://<server-name>/libs/cq/workflow/content/console.html`.

   * Workflow „DAM-Update-Asset“
   * DAM-Metadaten-Writeback-Workflow

1. Deaktivieren *Aktivieren von Workflow-Startern für Nachbearbeitung* in `com.adobe.fmdita.config.ConfigManager` und deaktivieren *Aktivieren der Versionspostverarbeitung* in `com.adobe.fmdita.postprocess.version.PostProcessVersionObservation`.

1. Deaktivieren Sie die Eigenschaft Validierung aktivieren (`validation.enabled`) in Day CQ Tagging Service.

1. Stellen Sie sicher, dass `uuid.regex` Eigenschaftsordner wird ordnungsgemäß in `com.adobe.fmdita.config.ConfigManager`. Wenn es leer ist, setzen Sie es auf den Standardwert - `^GUID-(?<id>.*)`.
1. Hinzufügen einer separaten Protokollfunktion für `com.adobe.fmdita.uuid` Die Browserantwort ist auch unter folgender Adresse verfügbar: `/content/uuid-upgrade/logs`.

### Schritt 2: Ausführen der Migration und Validieren

#### Migrationspaket installieren

1. Launch `http://<server-name>/libs/fmdita/clientlibs/xmleditor_uuid_upgrade/page.html`.

   ![Registerkarte &quot;Systemaktualisierung&quot;bei der Migration](assets/migration-system-upgrade.png){width="800" align="left"}

1. Auswählen **Systemaktualisierung** im linken Bereich, um die Migration auszuführen. Starten Sie einen Ordner mit kleineren Daten, bevor Sie ihn ausführen. `/content/dam`.

1. Auswählen **Bericht herunterladen** während die Migration ausgeführt wird, um zu überprüfen, ob alle Dateien im Ordner ordnungsgemäß aktualisiert wurden und ob alle Funktionen nur für diesen Ordner funktionieren.


>[!NOTE]
>
> Die Inhaltsmigration kann auf Ordnerebene ausgeführt werden. `/content/dam`oder denselben Ordner (Migration erneut ausführen).

Außerdem muss sichergestellt werden, dass die Inhaltsmigration für alle Medien-Assets erfolgt, z. B. für Bilder und Grafiken, die Sie im DITA-Inhalt verwendet haben.

#### Grundlegende und überprüfte Migration

Auswählen **Grundlinien-/Prüfungsaktualisierung** im linken Bereich, um die Grundlinien zu migrieren und auf Ordnerebene zu überprüfen.

![Registerkarte &quot;Grundlinien und Überprüfung&quot;in der Migration](assets/migration-baseline-review-upgrade.png){width="800" align="left"}


### Schritt 3: Konfiguration wiederherstellen

Aktivieren Sie nach erfolgreicher Migration des Servers die Nachbearbeitung, das Tagging und die folgenden Workflows (einschließlich aller anderen Workflows, die während der Migration ursprünglich deaktiviert wurden), um weiterhin auf dem Server zu arbeiten.

* Workflow „DAM-Update-Asset“
* DAM-Metadaten-Workflow

>[!NOTE]
>
>Wenn einige Dateien vor der Migration nicht verarbeitet oder beschädigt werden, werden sie vor der Migration beschädigt und bleiben auch nach der Migration beschädigt.

## Migrationsvalidierung

1. Nachdem die Migration abgeschlossen ist, wählen Sie **Systemaktualisierung überprüfen** im linken Bereich und überprüfen Sie die Ausgabedateien vor und nach der Migration, um sicherzustellen, dass die Migration erfolgreich ist.

   ![Registerkarte &quot;Systemaktualisierung überprüfen&quot;bei der Migration](assets/migration-validate-system-upgrade.png){width="800" align="left"}


1. Nach Abschluss der Validierung kann der Großteil des Festplattenspeichers durch Ausführen der Komprimierung zurückgewonnen werden (siehe `https://experienceleague.adobe.com/docs/experience-manager-65/deploying/deploying/revision-cleanup.html?lang=en`).

