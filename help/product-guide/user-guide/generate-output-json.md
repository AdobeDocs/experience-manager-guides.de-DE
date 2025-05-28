---
title: JSON
description: Erfahren Sie, wie Sie eine JSON-Voreinstellung über die Zuordnungskonsole erstellen. Konfigurieren der JSON-Ausgabevorgabe in Experience Manager Guides.
exl-id: 9eb426fc-ca0a-4932-8a55-fea731281a0a
feature: Publishing
role: User
source-git-commit: 9ae2690c52ab5408a9d17e9a40a89fe1f902042f
workflow-type: tm+mt
source-wordcount: '813'
ht-degree: 0%

---

# JSON {#id231KK0180T4}

Führen Sie die folgenden Schritte aus, um die JSON-Voreinstellung über die Zuordnungskonsole zu erstellen:

1. [Öffnen Sie eine DITA-Zuordnungsdatei in der Zuordnungskonsole](./open-files-map-console.md).

   Sie können auf die Zuordnungsdatei auch über das Widget **Letzte Dateien** im Abschnitt [Übersicht](./intro-home-page.md#overview) zugreifen. Die ausgewählte Zuordnungsdatei wird dann in der Zuordnungskonsole geöffnet.
1. Klicken **auf der Registerkarte** Ausgabevorgaben“ auf das Symbol + , um eine Ausgabevorgabe zu erstellen.
1. Wählen Sie **JSON** aus der Dropdown-Liste Typ im Dialogfeld **Neue**&quot; aus.
1. Geben Sie **Feld** einen Namen für diese Voreinstellung ein.
1. Wählen Sie die **Zum aktuellen Ordnerprofil hinzufügen**, um eine Ausgabevorgabe innerhalb des aktuellen Ordnerprofils zu erstellen. Das ![Ordnerprofilsymbol](images/global-preset-icon.svg) gibt eine Vorgabe auf Ordnerprofilebene an.

   Weitere Informationen zu [Verwalten globaler und Ordnerprofil-Ausgabevorgaben](./web-editor-manage-output-presets.md).

1. Wählen Sie **Hinzufügen** aus.

   Die JSON-Voreinstellung wird erstellt.

   ![](images/json-preset-dialog-new.png){width="300" align="left"}

Nachdem die Voreinstellung erstellt wurde, können Sie die folgenden Voreinstellungskonfigurationen konfigurieren, die auf der Registerkarte Allgemein verfügbar sind.

- Ausgabepfad
- Indexdatei
- Bedingungen mithilfe von \(Wenn die Bedingungen für eine Zuordnung definiert sind\) anwenden
- Baseline verwenden \(Wenn eine Baseline für eine Zuordnung erstellt wird\)
- Temporäre Dateien aufbewahren
- In der Ausgabe zu übertragende Eigenschaften
- Nachgenerierungs-Workflow

Weitere Informationen finden Sie unter [JSON-](#json-configuration).

![](images/json-preset-config.png){align="left"}

## JSON-Konfiguration

Die folgenden Optionen sind für die JSON-Voreinstellung verfügbar:

>[!NOTE]
>
> Sie können die JSON-Datei auch im Editor bearbeiten.

| JSON-Optionen | Beschreibung |
| --- | --- |
| Ausgabepfad | Der Pfad innerhalb Ihres AEM-Repositorys, in dem die JSON-Ausgabe gespeichert wird. |
| Indexdatei | Sie können einen Namen für die Indexdatei angeben, die Sie für die JSON-Ausgabe erstellen. Standardmäßig wählt sie den Dateinamen der DITA-Zuordnung aus und fügt ein Suffix hinzu (z. B. `map_filename_index.json`).<br><br>Sie können beim Festlegen der Indexdatei auch Variablen verwenden. Weitere Informationen zur Verwendung von Variablen finden Sie unter [Verwenden von Variablen zum Festlegen der Optionen Zielpfad, Site-Name oder Dateiname](generate-output-use-variables.md#id18BUG70K05Z). |
| Bedingungen anwenden mit | Wählen Sie eine der folgenden Optionen aus:<br><br>* **Keine angewendet**: Wählen Sie diese Option aus, wenn Sie keine Bedingung auf die veröffentlichte Ausgabe anwenden möchten.<br>* **DITAVAL-**: Wählen Sie DITAVAL-Datei(en), um personalisierte Inhalte zu generieren. Sie können mehrere DITAVAL-Dateien über das Dialogfeld „Durchsuchen“ oder durch Eingabe des Dateipfads auswählen. Verwenden Sie das Kreuz-Symbol neben dem Dateinamen, um ihn zu entfernen. DITAVAL-Dateien werden in der angegebenen Reihenfolge ausgewertet, sodass die in der ersten Datei angegebenen Bedingungen Vorrang vor den in späteren Dateien angegebenen übereinstimmenden Bedingungen haben. Sie können die Dateireihenfolge durch Hinzufügen oder Löschen von Dateien beibehalten. Wenn die DITAVAL-Datei an einen anderen Speicherort verschoben oder gelöscht wird, wird sie nicht automatisch aus dem Karten-Dashboard gelöscht. Sie müssen den Speicherort aktualisieren, falls Dateien verschoben oder gelöscht werden. Sie können den Mauszeiger über den Dateinamen bewegen, um den Pfad im AEM-Repository anzuzeigen, in dem die Datei gespeichert ist. Sie können nur DITAVAL-Dateien auswählen. Wenn Sie einen anderen Dateityp ausgewählt haben, wird ein Fehler angezeigt.<br>* **Bedingungsvorgabe**: Wählen Sie in der Dropdown-Liste eine Bedingungsvorgabe aus, um eine Bedingung beim Veröffentlichen der Ausgabe anzuwenden. Die Option ist sichtbar, wenn Sie eine Bedingung auf der Registerkarte „Bedingungsvorgaben“ der DITA-Zuordnungskonsole hinzugefügt haben. Weitere Informationen zu Bedingungsvorgaben finden Sie unter [Verwenden von Bedingungsvorgaben](generate-output-use-condition-presets.md#id1825FL004PN). |
| Baseline verwenden | Wenn Sie eine Baseline für die ausgewählte DITA-Map erstellt haben, wählen Sie diese Option, um die Version anzugeben, die Sie veröffentlichen möchten.<br><br>Weitere Informationen finden Sie [ „Arbeiten mit ](generate-output-use-baseline-for-publishing.md#id1825FI0J0PF)&quot;. |
| Temporäre Dateien aufbewahren | Wählen Sie diese Option, um die von DITA-OT generierten temporären Dateien beizubehalten. Wenn beim Generieren der Ausgabe über DITA-OT Fehler auftreten, wählen Sie diese Option aus, um die temporären Dateien beizubehalten. Anschließend können Sie diese Dateien verwenden, um Fehler bei der Ausgabegenerierung zu beheben.<br> <br> Klicken Sie nach dem Generieren der Ausgabe auf das Symbol **Temporäre Dateien herunterladen** ![Symbol für temporäre Dateien herunterladen](images/download-temp-files-icon.svg), um den ZIP-Ordner mit den temporären Dateien herunterzuladen. Die heruntergeladenen Dateien enthalten auch `system_config.json` Datei mit Informationen zur Autoren-URL, zur lokalen URL und zur Veröffentlichungs-URL. <br><br> **Hinweis**: Wenn Dateieigenschaften während der Generierung hinzugefügt werden, enthalten die temporären Ausgabedateien auch eine *metadata.xml*-Datei, die diese Eigenschaften enthält. |
| In der Ausgabe zu übertragende Eigenschaften | Wählen Sie die Eigenschaften aus, die Sie als Metadaten verarbeiten möchten. Diese Eigenschaften werden auf der Seite Eigenschaften der DITA-Map- oder Bookmap-Datei festgelegt. Die Eigenschaften, die Sie aus der Dropdown-Liste auswählen, werden unter dem Feld Eigenschaften aufgeführt.<br><br>**Hinweis**: Sie können auch benutzerdefinierte Eigenschaften definieren und die Metadaten mithilfe von DITA-OT-Publishing an die Ausgabe übergeben. Weitere Informationen finden Sie unter [Arbeiten mit Metadaten](metadata-dita.md#id21BJ00QD0XA). |
| Nachgenerierungs-Workflow | Wenn Sie diese Option wählen, wird eine neue Dropdown-Liste für den Post-Generation-Workflow angezeigt, die alle in AEM konfigurierten Workflows enthält. Sie müssen einen Workflow auswählen, den Sie nach Abschluss des Workflows zur Ausgabegenerierung ausführen möchten.<br><br>**Hinweis**: Weitere Informationen zum Erstellen eines benutzerdefinierten Workflows für die Post-Output-Generierung finden Sie _Workflow für die Post-Output-Generierung anpassen_ im Handbuch Installieren und Konfigurieren von Adobe Experience Manager Guides as a Cloud Service . |

**Übergeordnetes Thema:**&#x200B;[ Verstehen der Ausgabevorgaben](generate-output-understand-presets.md)
