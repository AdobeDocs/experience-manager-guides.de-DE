---
title: Generieren von PDF mit DITA-OT
description: Erfahren Sie, wie Sie eine PDF-Vorgabe mit DITA-OT in der Zuordnungskonsole und im Zuordnungs-Dashboard erstellen. Konfigurieren der PDF-Ausgabevorgabe in AEM Guides.
feature: Publishing
role: User
exl-id: 6ac82dad-34af-4f9e-8b52-4e4f2eb982a4
source-git-commit: 9ae2690c52ab5408a9d17e9a40a89fe1f902042f
workflow-type: tm+mt
source-wordcount: '1349'
ht-degree: 0%

---

# Erstellen einer DITA-OT-PDF-Ausgabevorgabe {#id205BE600HAH}

Sie können die DITA-OT-PDF-Ausgabevorgabe auf zwei Arten erstellen:

- [Erstellen der DITA-OT-PDF-Vorgabe über die Zuordnungskonsole](#create-the-dita-ot-pdf-preset-from-the-map-console)
- [Erstellen der DITA-OT-PDF-Vorgabe über das Zuordnungs-Dashboard](#create-the-dita-ot-pdf-preset-from-the-map-dashboard)

## Erstellen der DITA-OT-PDF-Vorgabe über die Zuordnungskonsole

Führen Sie die folgenden Schritte aus, um die PDF-Voreinstellung über die Zuordnungskonsole zu erstellen:

1. [Öffnen Sie eine DITA-Zuordnungsdatei in der Zuordnungskonsole](./open-files-map-console.md).

   Sie können auf die Zuordnungsdatei auch über das Widget **Letzte Dateien** im Abschnitt [Übersicht](./intro-home-page.md#overview) zugreifen. Die ausgewählte Zuordnungsdatei wird dann in der Zuordnungskonsole geöffnet.
1. Klicken **auf der Registerkarte** Ausgabevorgaben“ auf das Symbol + , um eine Ausgabevorgabe zu erstellen.
1. Wählen Sie **PDF** aus der Dropdown-Liste Typ im Dialogfeld **Neue**) aus.
1. Geben Sie **Feld** einen Namen für diese Voreinstellung ein.
1. Wählen Sie im Feld **PDF generieren mit** die Option **DITA-OT**.
1. Wählen Sie die **Zum aktuellen Ordnerprofil hinzufügen**, um eine Ausgabevorgabe innerhalb des aktuellen Ordnerprofils zu erstellen. Das ![Ordnerprofilsymbol](images/global-preset-icon.svg) gibt eine Vorgabe auf Ordnerprofilebene an.

   Weitere Informationen zu [Verwalten globaler und Ordnerprofil-Ausgabevorgaben](./web-editor-manage-output-presets.md).

1. Wählen Sie **Hinzufügen** aus.

   Die Voreinstellung für PDF wird erstellt.

   ![](./images/pdf-preset-map-console.png){width="350" align="left"}

In der Zuordnungskonsole sind die voreingestellten Konfigurationsoptionen für DITA-OT auf den Registerkarten **Allgemein** und **Erweitert** in der Zuordnungskonsole organisiert.

![](./images/dita-ot-preset-config.png){width="350" align="left"}

**Allgemein**

Die **Allgemein** enthält die folgenden Konfigurationsoptionen:

- Ausgabepfad
- DITA-OT-Befehlszeilenargumente
- PDF-Dateiname
- Bedingte Filterung \(Wenn die Bedingungen für eine Zuordnung definiert sind\)
- Baseline verwenden \(Wenn eine Baseline für eine Zuordnung erstellt wird\)
- Nachgenerierungs-Workflow

**Erweitert**

Die **Erweitert**-Registerkarte enthält die folgenden Konfigurationsoptionen:

- Aktivierung der Versionierung
- Temporäre Dateien aufbewahren
- Dateieigenschaften

Weitere Informationen zu den Voreinstellungskonfigurationsoptionen finden Sie im Abschnitt [PDF-Voreinstellungskonfiguration](#pdf-preset-configuration).


## Erstellen der DITA-OT-PDF-Vorgabe über das Zuordnungs-Dashboard

Führen Sie die folgenden Schritte aus, um die PDF-Voreinstellung über das Zuordnungs-Dashboard zu erstellen:

1. Navigieren Sie in der Assets-Benutzeroberfläche zu und wählen Sie die DITA-Karte aus, um sie im Karten-Dashboard zu öffnen.
1. Stellen Sie sicher **dass die Registerkarte** Ausgabevorgaben“ ausgewählt ist.
1. Wählen **Erstellen** in der Symbolleiste aus.

   Ein neues Formular zur Erstellung von Ausgabevorgaben wird angezeigt.

1. Geben Sie die erforderlichen Konfigurationsdetails für die PDF-Voreinstellung ein.
1. Klicken Sie **Fertig**, um die Voreinstellungen zu speichern.

## Konfiguration der PDF-Voreinstellung

Die Konfigurationsoptionen variieren geringfügig, je nachdem, ob Sie die Vorgabe über die Zuordnungskonsole oder das Zuordnungs -Dashboard konfigurieren. Einige Optionen gelten nur für das Zuordnungs -Dashboard, während andere für beide gelten.

Wenn dieselbe Konfiguration zwei verschiedene Feldbezeichnungen hat, werden diese in der folgenden Tabelle durch ein **/** getrennt. Das erste steht für die Beschriftung in der Zuordnungskonsole und das zweite steht für die Beschriftung im Zuordnungs -Dashboard.

Beispiel: **Ausgabepfad/Zielpfad** - Hier ist **Ausgabepfad** die in der Zuordnungskonsole verwendete Beschriftung, während **Zielpfad** die Beschriftung ist, die im Zuordnungs-Dashboard für dieselbe Konfiguration verwendet wird.

| PDF-Optionen | Beschreibung |
| --- | --- |
| Ausgabetyp (*nur für Zuordnungs-Dashboard*) | Der Typ der Ausgabe, die Sie generieren möchten. Um die PDF-Ausgabe zu generieren, wählen Sie die Option PDF . |
| Name der Einstellung (*nur für das Zuordnungs-Dashboard*) | Geben Sie einen beschreibenden Namen für die PDF-Ausgabeeinstellungen an, die Sie erstellen. Sie können beispielsweise &quot;_Kundenausgabe“_ „Endbenutzerausgabe _angeben_. |
| PDF generieren mit (*nur für Map-Dashboard*) | Wählen Sie **DITA-OT** aus, um die PDF-Ausgabe zu generieren. Wählen Sie **FrameMaker Publishing Server** aus, wenn Ihr Administrator diese Option konfiguriert hat. Einige der Konfigurationsoptionen variieren, wenn FMPS ausgewählt wird. Außerdem ist die FMPS-Konfigurationsoption nur im Zuordnungs-Dashboard verfügbar. |
| Ausgabepfad/Zielpfad | Der Pfad innerhalb Ihres AEM-Repositorys, in dem die PDF gespeichert ist.<br><br>Sie können beim Festlegen des Zielpfads auch Variablen verwenden. Weitere Informationen zur Verwendung von Variablen finden Sie unter [Verwenden von Variablen zum Festlegen der Optionen Zielpfad, Site-Name oder Dateiname](generate-output-use-variables.md#id18BUG70K05Z). |
| DITA-OT-Befehlszeilenargumente | Geben Sie die zusätzlichen Argumente an, die DITA-OT beim Generieren der Ausgabe verarbeiten soll. Weitere Informationen zu den in DITA-OT unterstützten Befehlszeilenargumenten finden Sie unter [DITA-OT-Dokumentation](https://www.dita-ot.org/). |
| Name der Umwandlung | Geben Sie den Typ der Ausgabe an, die Sie generieren möchten. Dies ist erforderlich, wenn Sie eine Ausgabe mit Ihrem eigenen benutzerdefinierten Plug-in generieren möchten, das im DITA-OT-Plug-in integriert ist. Wenn Sie beispielsweise eine XHTML-Ausgabe generieren möchten, geben Sie `xhtml` an. Eine Liste der in DITA-OT verfügbaren Transformationen finden Sie [DITA-OT-Transformationen (Ausgabeformate)](http://www.dita-ot.org/2.3/user-guide/AvailableTransforms.html) im OASIS DITA-OT-Benutzerhandbuch. |
| PDF-Dateiname/-Dateiname | Geben Sie den Dateinamen an, mit dem Sie die PDF speichern möchten.<br><br>Sie können beim Festlegen des PDF-Dateinamens auch Variablen verwenden. Weitere Informationen zur Verwendung von Variablen finden Sie unter [Verwenden von Variablen zum Festlegen der Optionen Zielpfad, Site-Name oder Dateiname](generate-output-use-variables.md#id18BUG70K05Z).<br><br>**Hinweis**: Wenn Sie keinen Dateinamen angeben, wird der Titel der DITA-Zuordnung verwendet, um den endgültigen Dateinamen von PDF zu generieren. Wenn die Zuordnung keinen Titel hat, wird der Dateiname der DITA-Zuordnung verwendet, um den endgültigen PDF zu benennen. Der Dateiname wird mithilfe der im System konfigurierten Regeln bereinigt, um ungültige Zeichen zu verarbeiten. |
| Bedingte Filterung/Bedingungen anwenden mit | Wählen Sie eine der folgenden Optionen aus:<br><br>* **Keine angewendet**: Wählen Sie diese Option aus, wenn Sie keine Bedingung auf die veröffentlichte Ausgabe anwenden möchten.<br>* **DITAVal-Datei**: Wählen Sie DITAVal-Dateien aus, um personalisierte Inhalte zu generieren. Sie können mehrere DITAVal-Dateien über das Dialogfeld „Durchsuchen“ oder durch Eingabe des Dateipfads auswählen. Verwenden Sie das Kreuz-Symbol neben dem Dateinamen, um ihn zu entfernen. DITAVal-Dateien werden in der angegebenen Reihenfolge ausgewertet, sodass die in der ersten Datei angegebenen Bedingungen Vorrang vor den in späteren Dateien angegebenen übereinstimmenden Bedingungen haben. Sie können die Dateireihenfolge durch Hinzufügen oder Löschen von Dateien beibehalten. Wenn die DITAVal-Datei an einen anderen Speicherort verschoben oder gelöscht wird, wird sie nicht automatisch aus dem Zuordnungs-Dashboard gelöscht. Sie müssen den Speicherort aktualisieren, falls Dateien verschoben oder gelöscht werden. Sie können den Mauszeiger über den Dateinamen bewegen, um den Pfad im AEM-Repository anzuzeigen, in dem die Datei gespeichert ist. Sie können nur DITAVal-Dateien auswählen. Wenn Sie einen anderen Dateityp ausgewählt haben, wird ein Fehler angezeigt. FrameMaker Publishing Server unterstützt nicht mehrere DITAVAL-Dateien.<br>* **Bedingungsvorgabe**: Wählen Sie in der Dropdown-Liste eine Bedingungsvorgabe aus, um eine Bedingung beim Veröffentlichen der Ausgabe anzuwenden. Die Option ist sichtbar, wenn Sie eine Bedingung auf der Registerkarte „Bedingungsvorgaben“ der DITA-Zuordnungskonsole hinzugefügt haben. Weitere Informationen zu Bedingungsvorgaben finden Sie unter [Verwenden von Bedingungsvorgaben](generate-output-use-condition-presets.md#id1825FL004PN). |
| Nachgenerierungs-Workflow ausführen | Wenn Sie diese Option wählen, wird eine neue Dropdown-Liste für den Post-Generation-Workflow angezeigt, die alle in AEM konfigurierten Workflows enthält. Sie müssen einen Workflow auswählen, den Sie nach Abschluss des Workflows zur Ausgabegenerierung ausführen möchten.<br><br>**Hinweis**: Weitere Informationen zum Erstellen eines benutzerdefinierten Workflows für die Post-Output-Generierung finden Sie unter Anpassen des Workflows für die Post-Output-Generierung in Installieren und Konfigurieren von Adobe Experience Manager Guides as a Cloud Service . |
| Baseline verwenden | Wenn Sie eine Baseline für die ausgewählte DITA-Map erstellt haben, wählen Sie diese Option, um die Version anzugeben, die Sie veröffentlichen möchten.<br><br>Weitere Informationen finden Sie [ „Arbeiten mit ](generate-output-use-baseline-for-publishing.md#id1825FI0J0PF)&quot;. |
| Temporäre Dateien aufbewahren | Wählen Sie diese Option, um die von DITA-OT generierten temporären Dateien beizubehalten. Wenn beim Generieren der Ausgabe über DITA-OT Fehler auftreten, wählen Sie diese Option aus, um die temporären Dateien beizubehalten. Anschließend können Sie diese Dateien verwenden, um Fehler bei der Ausgabegenerierung zu beheben.<br> <br> Klicken Sie nach dem Generieren der Ausgabe auf das Symbol **Temporäre Dateien herunterladen** ![Symbol für temporäre Dateien herunterladen](images/download-temp-files-icon.png), um den ZIP-Ordner mit den temporären Dateien herunterzuladen. Die heruntergeladenen Dateien enthalten auch `system_config.json` Datei mit Informationen zur Autoren-URL, zur lokalen URL und zur Veröffentlichungs-URL.<br><br> **Hinweis**: Wenn Dateieigenschaften während der Generierung hinzugefügt werden, enthalten die temporären Ausgabedateien auch eine *metadata.xml*-Datei, die diese Eigenschaften enthält. |
| Dateieigenschaften | Wählen Sie die Eigenschaften aus, die Sie als Metadaten verarbeiten möchten. Diese Eigenschaften werden auf der Seite Eigenschaften der DITA-Map- oder Bookmap-Datei festgelegt. Die aus der Dropdown-Liste ausgewählten Eigenschaften werden unter dem Feld **Dateieigenschaften** angezeigt. Klicken Sie auf das Kreuzsymbol neben der Eigenschaft, um sie zu entfernen. <br><br>Hinweis: Sie können die Metadaten auch mithilfe von DITA-OT-Publishing an die Ausgabe übergeben. Für eine weitere Detailansicht ([ Sie die Metadaten mithilfe von DITA-OT an die Ausgabe ](pass-metadata-dita-ot.md#id21BJ00QD0XA). |


**Übergeordnetes Thema:**&#x200B;[ Verstehen der Ausgabevorgaben](generate-output-understand-presets.md)
