---
title: Generieren einer PDF
description: Erfahren Sie, wie Sie eine PDF-Vorgabe aus dem Web-Editor und dem Zuordnungs-Dashboard erstellen. Konfigurieren der PDF-Ausgabevorgabe in AEM Guides.
exl-id: f12c91fd-3f95-478e-a9cd-68d037206ee8
feature: Publishing
role: User
source-git-commit: c2a97a134b9e7367689778a2a1e1f4bbead9860b
workflow-type: tm+mt
source-wordcount: '1032'
ht-degree: 1%

---

# PDF {#id205BE600HAH}

Sie können die PDF-Vorgabe auf zwei Arten erstellen:

**Im Web-Editor:** Öffnen Sie im Repository-Bereich die DITA-Zuordnungsdatei in der Zuordnungsansicht, wählen Sie dann auf der Registerkarte Ausgabe das Symbol + aus, um eine Ausgabevorgabe zu erstellen, und wählen Sie dann PDF aus der Dropdown-Liste Typ im Dialogfeld Vorgabe hinzufügen aus.

>[!NOTE]
>
> Sie können die Methode zum Generieren von PDF mit DITA-OT, Native PDF oder FMPS auswählen \(falls Ihr Systemadministrator sie konfiguriert hat\).

Im Web-Editor wurden die Konfigurationen auf den Registerkarten Allgemein und Erweitert organisiert:

**Allgemein**

Die Registerkarte **Allgemein** enthält die folgenden Konfigurationen:

- Ausgabepfad
- DITA-OT-Befehlszeilenargumente
- Name der Umwandlung
- PDF Dateiname
- Bedingungen mithilfe von \(Wenn die Bedingungen für eine Zuordnung definiert sind\) anwenden
- Baseline verwenden \(Wenn eine Baseline für eine Zuordnung erstellt wird\)
- Nachgenerierungs-Workflow

**Erweitert**

Die Registerkarte Erweitert enthält die folgenden Konfigurationen:

- Versionierung aktivieren
- Temporäre Dateien aufbewahren

Weitere Informationen finden Sie unter [PDF-Konfiguration](#id231KIM004X1).

**Vom Zuordnungs-Dashboard**

Um die Ausgabevorgaben für das PDF zu öffnen, klicken Sie in der Assets-Benutzeroberfläche auf eine DITA-Zuordnungsdatei, klicken Sie dann auf Ausgabevorgaben und dann auf die Option PDF . Klicken Sie im Zuordnungs-Dashboard oben auf **Bearbeiten**, um die verschiedenen Konfigurationen zu aktualisieren, und klicken Sie dann auf **Speichern**.

**PDF-Konfiguration**

Folgende Optionen stehen für die PDF-Ausgabe zur Verfügung:

| PDF-Optionen | Beschreibung |
| --- | --- |
| Ausgabetyp | Der Typ der Ausgabe, die Sie generieren möchten. Um die PDF-Ausgabe zu generieren, wählen Sie die Option PDF aus. |
| Einstellungsname | Geben Sie einen beschreibenden Namen für die PDF-Ausgabeeinstellungen an, die Sie erstellen. Sie können beispielsweise &quot;_Kundenausgabe“_ „Endbenutzerausgabe _angeben_. |
| DITA-OT-Befehlszeilenargumente | Geben Sie die zusätzlichen Argumente an, die DITA-OT beim Generieren der Ausgabe verarbeiten soll. Weitere Informationen zu den in DITA-OT unterstützten Befehlszeilenargumenten finden Sie unter [DITA-OT-Dokumentation](https://www.dita-ot.org/). |
| Bedingungen anwenden mit | Wählen Sie eine der folgenden Optionen aus:<br><br>* **Keine angewendet**: Wählen Sie diese Option aus, wenn Sie keine Bedingung auf die veröffentlichte Ausgabe anwenden möchten.<br>* **DITAVal-Datei**: Wählen Sie DITAVal-Dateien aus, um personalisierte Inhalte zu generieren. Sie können mehrere DITAVal-Dateien über das Dialogfeld „Durchsuchen“ oder durch Eingabe des Dateipfads auswählen. Verwenden Sie das Kreuz-Symbol neben dem Dateinamen, um ihn zu entfernen. DITAVal-Dateien werden in der angegebenen Reihenfolge ausgewertet, sodass die in der ersten Datei angegebenen Bedingungen Vorrang vor den in späteren Dateien angegebenen übereinstimmenden Bedingungen haben. Sie können die Dateireihenfolge durch Hinzufügen oder Löschen von Dateien beibehalten. Wenn die DITAVal-Datei an einen anderen Speicherort verschoben oder gelöscht wird, wird sie nicht automatisch aus dem Zuordnungs-Dashboard gelöscht. Sie müssen den Speicherort aktualisieren, falls Dateien verschoben oder gelöscht werden. Sie können den Mauszeiger über den Dateinamen bewegen, um den Pfad im AEM-Repository anzuzeigen, in dem die Datei gespeichert ist. Sie können nur DITAVal-Dateien auswählen. Wenn Sie einen anderen Dateityp ausgewählt haben, wird ein Fehler angezeigt. FrameMaker Publishing Server unterstützt nicht mehrere DITAVAL-Dateien.<br>* **Bedingungsvorgabe**: Wählen Sie in der Dropdown-Liste eine Bedingungsvorgabe aus, um eine Bedingung beim Veröffentlichen der Ausgabe anzuwenden. Die Option ist sichtbar, wenn Sie eine Bedingung auf der Registerkarte „Bedingungsvorgaben“ der DITA-Zuordnungskonsole hinzugefügt haben. Weitere Informationen zu Bedingungsvorgaben finden Sie unter [Verwenden von Bedingungsvorgaben](generate-output-use-condition-presets.md#id1825FL004PN). |
| PDF generieren mit | Wählen Sie DITA-OT aus, um die PDF zu generieren. |
| Nachgenerierungs-Workflow ausführen | Wenn Sie diese Option wählen, wird eine neue Dropdown-Liste für den Post-Generation-Workflow angezeigt, die alle in AEM konfigurierten Workflows enthält. Sie müssen einen Workflow auswählen, den Sie nach Abschluss des Workflows zur Ausgabegenerierung ausführen möchten.<br><br>**Hinweis**: Weitere Informationen zum Erstellen eines benutzerdefinierten Workflows für die Post-Output-Generierung finden Sie unter Anpassen des Workflows für die Post-Output-Generierung in Adobe Experience Manager Guides as a Cloud Service installieren und konfigurieren. |
| Name der Umwandlung | Geben Sie den Typ der Ausgabe an, die Sie generieren möchten. Dies ist erforderlich, wenn Sie eine Ausgabe mit Ihrem eigenen benutzerdefinierten Plug-in generieren möchten, das im DITA-OT-Plug-in integriert ist. Wenn Sie beispielsweise eine XHTML-Ausgabe generieren möchten, geben Sie `xhtml` an. Eine Liste der in DITA-OT verfügbaren Transformationen finden Sie unter [DITA-OT-Transformationen (Ausgabeformate)](http://www.dita-ot.org/2.3/user-guide/AvailableTransforms.html) im OASIS DITA-OT-Benutzerhandbuch. |
| Dateiname | Geben Sie den Dateinamen an, mit dem Sie die PDF speichern möchten.<br><br>Sie können beim Festlegen des PDF-Dateinamens auch Variablen verwenden. Weitere Informationen zur Verwendung von Variablen finden Sie [Verwenden von Variablen zum Festlegen der Optionen Zielpfad, Site-Name oder Dateiname](generate-output-use-variables.md#id18BUG70K05Z).<br><br>**Hinweis**: Wenn Sie keinen Dateinamen angeben, wird der Titel der DITA-Zuordnung verwendet, um den endgültigen Dateinamen der PDF zu generieren. Wenn die Zuordnung keinen Titel hat, wird der Dateiname der DITA-Zuordnung verwendet, um die endgültige PDF zu benennen. Der Dateiname wird mithilfe der im System konfigurierten Regeln bereinigt, um ungültige Zeichen zu verarbeiten. |
| Zielpfad | Der Pfad innerhalb Ihres AEM-Repositorys, in dem die PDF gespeichert ist.<br><br>Sie können beim Festlegen des Zielpfads auch Variablen verwenden. Weitere Informationen zur Verwendung von Variablen finden Sie [Verwenden von Variablen zum Festlegen der Optionen Zielpfad, Site-Name oder Dateiname](generate-output-use-variables.md#id18BUG70K05Z). |
| Temporäre Dateien aufbewahren | Wählen Sie diese Option, um die von DITA-OT generierten temporären Dateien beizubehalten. Wenn beim Generieren der Ausgabe über DITA-OT Fehler auftreten, wählen Sie diese Option aus, um die temporären Dateien beizubehalten. Anschließend können Sie diese Dateien verwenden, um Fehler bei der Ausgabegenerierung zu beheben.<br> <br> Klicken Sie nach dem Generieren der Ausgabe auf das Symbol **Temporäre Dateien herunterladen** ![Symbol für temporäre Dateien herunterladen](images/download-temp-files-icon.png), um den ZIP-Ordner mit den temporären Dateien herunterzuladen. <br><br> **Hinweis**: Wenn Dateieigenschaften während der Generierung hinzugefügt werden, enthalten die temporären Ausgabedateien auch eine *metadata.xml*-Datei, die diese Eigenschaften enthält. |
| Baseline verwenden | Wenn Sie eine Baseline für die ausgewählte DITA-Map erstellt haben, wählen Sie diese Option, um die Version anzugeben, die Sie veröffentlichen möchten.<br><br>Weitere Informationen finden [ unter „Arbeiten mit ](generate-output-use-baseline-for-publishing.md#id1825FI0J0PF)&quot;. |
| Dateieigenschaften | Wählen Sie die Eigenschaften aus, die Sie als Metadaten verarbeiten möchten. Diese Eigenschaften werden auf der Seite Eigenschaften der DITA-Map- oder Bookmap-Datei festgelegt. Die aus der Dropdown-Liste ausgewählten Eigenschaften werden unter dem Feld **Dateieigenschaften** angezeigt. Klicken Sie auf das Kreuzsymbol neben der Eigenschaft, um sie zu entfernen. <br><br>Hinweis: Sie können die Metadaten auch mithilfe von DITA-OT-Publishing an die Ausgabe übergeben. Weitere Informationen finden Sie unter [Übergeben der Metadaten an die Ausgabe mithilfe von DITA-OT](pass-metadata-dita-ot.md#id21BJ00QD0XA). |

**Übergeordnetes Thema:**[ Verstehen der Ausgabevorgaben](generate-output-understand-presets.md)
