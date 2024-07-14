---
title: JSON
description: Erfahren Sie, wie Sie eine JSON-Vorgabe aus dem Web-Editor und dem Map-Dashboard erstellen. Konfigurieren Sie die JSON-Ausgabevorgabe in AEM Guides.
exl-id: 9eb426fc-ca0a-4932-8a55-fea731281a0a
feature: Publishing
role: User
source-git-commit: b82f1f3b42f85cce8420d3962c69cd3bafc5728d
workflow-type: tm+mt
source-wordcount: '733'
ht-degree: 0%

---

# JSON {#id231KK0180T4}

Sie können die JSON-Vorgabe im Web Editor erstellen:

Öffnen Sie im Bereich &quot;Repository&quot;die DITA-Zuordnungsdatei in der Zuordnungsansicht, wählen Sie dann auf der Registerkarte &quot;Ausgabe&quot;das Symbol + aus, um eine Ausgabevorgabe zu erstellen, und wählen Sie dann JSON aus der Dropdown-Liste Typ im Dialogfeld Vorgabe hinzufügen aus.

Im Web-Editor wurden die folgenden Konfigurationen auf der Registerkarte **Allgemein** organisiert:

- Ausgabepfad
- Indexdatei
- Bedingungen anwenden mit \(Wenn die Bedingungen für eine Zuordnung definiert sind\)
- Grundlinie verwenden \(Wenn eine Grundlinie für eine Zuordnung erstellt wird\)
- Herunterladen temporärer Dateien
- Eigenschaften zum Propagieren in der Ausgabe
- Post-Generierungsarbeitsablauf

Weitere Informationen finden Sie unter [JSON-Konfiguration](#id231KJA00REJ).


**JSON-Konfiguration**

Die folgenden Optionen sind für die JSON-Vorgabe verfügbar:

>[!NOTE]
>
> Sie können die JSON-Datei auch im Web Editor bearbeiten.

| JSON-Optionen | Beschreibung |
| --- | --- |
| Ausgabepfad | Der Pfad in Ihrem AEM-Repository, in dem die JSON-Ausgabe gespeichert wird. |
| Indexdatei | Sie können einen Namen für die Indexdatei angeben, die Sie für die JSON-Ausgabe erstellen. Standardmäßig wird der Dateiname der DITA-Map ausgewählt und ein Suffix hinzugefügt (z. B. `map_filename_index.json`).<br><br>Sie können auch Variablen beim Festlegen der Indexdatei verwenden. Weitere Informationen zur Verwendung von Variablen finden Sie unter [Verwenden von Variablen zum Festlegen der Optionen &quot;Zielpfad&quot;, &quot;Site-Name&quot;oder &quot;Dateiname&quot;](generate-output-use-variables.md#id18BUG70K05Z). |
| Bedingungen anwenden mit | Wählen Sie eine der folgenden Optionen aus:<br><br>* **Keine angewendet**: Wählen Sie diese Option aus, wenn Sie keine Bedingung auf die veröffentlichte Ausgabe anwenden möchten.<br>* **DITAVAL file**: Wählen Sie DITAVAL-Dateien aus, um personalisierten Inhalt zu generieren. Sie können mehrere DITAVAL-Dateien über das Dialogfeld &quot;Durchsuchen&quot;oder durch Eingabe des Dateipfads auswählen. Verwenden Sie das Kreuzsymbol neben dem Dateinamen, um ihn zu entfernen. DITAVAL-Dateien werden in der angegebenen Reihenfolge ausgewertet, sodass die in der ersten Datei angegebenen Bedingungen Vorrang vor den in späteren Dateien angegebenen Bedingungen haben. Sie können die Dateireihenfolge beibehalten, indem Sie Dateien hinzufügen oder löschen. Wenn die DITAVAL-Datei an einen anderen Speicherort verschoben oder gelöscht wird, wird sie nicht automatisch aus dem Mapping-Dashboard gelöscht. Sie müssen den Speicherort aktualisieren, falls Dateien verschoben oder gelöscht werden. Sie können den Mauszeiger über den Dateinamen bewegen, um den Pfad im AEM Repository anzuzeigen, in dem die Datei gespeichert ist. Sie können nur DITAVAL-Dateien auswählen. Wenn Sie einen anderen Dateityp ausgewählt haben, wird ein Fehler angezeigt.<br>* **Bedingungsvorgabe**: Wählen Sie eine Bedingungsvorgabe aus der Dropdown-Liste aus, um beim Veröffentlichen der Ausgabe eine Bedingung anzuwenden. Die Option ist sichtbar, wenn Sie eine Bedingung auf der Registerkarte Bedingungsvorgaben der DITA-Zuordnungskonsole hinzugefügt haben. Weitere Informationen zur Bedingungsvorgabe finden Sie unter [Bedingungsvorgaben verwenden](generate-output-use-condition-presets.md#id1825FL004PN). |
| Grundlinie verwenden | Wenn Sie eine Grundlinie für die ausgewählte DITA-Zuordnung erstellt haben, wählen Sie diese Option, um die Version anzugeben, die Sie veröffentlichen möchten.<br><br>Weitere Informationen finden Sie unter [Arbeiten mit Grundlinie](generate-output-use-baseline-for-publishing.md#id1825FI0J0PF) . |
| Herunterladen temporärer Dateien | Wählen Sie diese Option, um die von DITA-OT generierten temporären Dateien herunterzuladen. Der Speicherort, an dem DITA-OT temporäre Dateien speichert, finden Sie im Ausgabegenerierungsprotokoll. Wenn beim Generieren der Ausgabe über DITA-OT Fehler auftreten, wählen Sie diese Option, um die temporären Dateien beizubehalten. Sie können diese Dateien dann verwenden, um Fehler bei der Ausgabenerstellung zu beheben.<br> <br> Nachdem Sie die Ausgabe generiert haben, wählen Sie das Symbol **Temporäre Dateien herunterladen** ![Symbol zum Herunterladen temporärer Dateien](images/download-temp-files-icon.png) aus, um den ZIP-Ordner mit den temporären Dateien herunterzuladen. <br><br> **Hinweis**: Wenn Sie einige Dateieigenschaften auswählen und dann die temporären Dateien herunterladen, erhalten Sie auch die Datei *metadata.xml* im ZIP-Ordner. |
| Eigenschaften zum Propagieren in der Ausgabe | Wählen Sie die Eigenschaften aus, die Sie als Metadaten verarbeiten möchten. Diese Eigenschaften werden auf der Seite &quot;Eigenschaften&quot;der DITA-Map- oder Bookmap-Datei festgelegt. Die Eigenschaften, die Sie aus der Dropdown-Liste auswählen, sind unter dem Feld Eigenschaften aufgeführt.<br><br>**Hinweis**: Sie können auch benutzerdefinierte Eigenschaften definieren und die Metadaten mithilfe der DITA-OT-Veröffentlichung an die Ausgabe übergeben. Weitere Informationen finden Sie unter [Arbeiten mit Metadaten](metadata-dita.md#id21BJ00QD0XA). |
| Post-Generierungsarbeitsablauf | Wenn Sie diese Option wählen, wird eine neue Dropdown-Liste für den Post-Arbeitsablauf angezeigt, die alle in AEM konfigurierten Workflows enthält. Sie müssen einen Workflow auswählen, der nach Abschluss des Workflows zur Generierung der Ausgabe ausgeführt werden soll.<br><br>**Hinweis**: Weitere Informationen zum Erstellen eines benutzerdefinierten Workflows für die Generierung nach der Ausgabe finden Sie unter _Workflow für die Generierung nach der Ausgabe anpassen_ im Handbuch &quot;Installieren und Konfigurieren von Adobe Experience Manager Guides as a Cloud Service&quot;. |

**Übergeordnetes Thema:**[ Grundlegendes zu den Ausgabevorgaben](generate-output-understand-presets.md)
