---
title: Benutzerdefiniert
description: Erfahren Sie, wie Sie eine benutzerdefinierte Vorgabe über den Web-Editor und das Zuordnungs-Dashboard erstellen. Konfigurieren einer benutzerdefinierten Ausgabevorgabe in AEM Guides.
feature: Publishing
role: User
hide: true
exl-id: b96e6599-f8f3-491a-8b8f-fcb1e0f58aae
source-git-commit: 26fa1e52920c1f1abd5655b9ca7341600a9bca67
workflow-type: tm+mt
source-wordcount: '961'
ht-degree: 1%

---

# Benutzerdefiniert {#id205BEF00PX0}

Die benutzerdefinierten Ausgabevorgaben sind für benutzerdefinierte DITA-OT-Plug-ins verfügbar. Sie können eine benutzerdefinierte DITA-OT-Ausgabevorgabe erstellen, um Ausgaben mit Ihrem benutzerdefinierten DITA-OT-Plug-in zu veröffentlichen.

Sie können die benutzerdefinierte Vorgabe auf zwei Arten erstellen:

**Im Web-Editor:** Öffnen Sie im Repository-Bereich die DITA-Zuordnungsdatei in der Zuordnungsansicht, wählen Sie dann auf der Registerkarte Ausgabe das Symbol + aus, um eine Ausgabevorgabe zu erstellen, und wählen Sie dann Benutzerdefiniert aus der Dropdown-Liste Typ im Dialogfeld Vorgabe hinzufügen aus.

Im Web-Editor wurden die Konfigurationen auf den Registerkarten Allgemein und Erweitert organisiert:

**Allgemein**

Die Registerkarte **Allgemein** enthält die folgenden Konfigurationen:

- DITA-OT-Befehlszeilenargumente
- Name der Umwandlung
- Dateiname
- Ausgabepfad
- Bedingungen mithilfe von \(Wenn die Bedingungen für eine Zuordnung definiert sind\) anwenden
- Baseline verwenden \(Wenn eine Baseline für eine Zuordnung erstellt wird\)
- Nachgenerierungs-Workflow

**Erweitert**

Die Registerkarte Erweitert enthält die folgenden Konfigurationen:

- Temporäre Dateien aufbewahren
- Dateieigenschaften

Weitere Informationen finden Sie unter &quot;[&#x200B; Konfiguration](#id231KJA00REJ).

**Vom Zuordnungs-Dashboard**

Um Ausgabevorgaben für PDF zu öffnen, klicken Sie in der Assets-Benutzeroberfläche auf eine DITA-Zuordnungsdatei, klicken Sie dann auf Ausgabevorgaben und dann auf die Option HTML5 . Klicken Sie im Zuordnungs-Dashboard oben auf **Bearbeiten**, um die verschiedenen Konfigurationen zu aktualisieren, und klicken Sie dann auf **Speichern**.

**Benutzerdefinierte Konfiguration**

Die folgenden Optionen sind für die benutzerdefinierte Ausgabevorgabe verfügbar:

| Benutzerdefinierte Ausgabeoptionen | Beschreibung |
| --- | --- |
| Ausgabetyp | Der Typ der Ausgabe, die Sie generieren möchten. Um eine Ausgabe mit dem benutzerdefinierten DITA-OT-Plug-in zu generieren, wählen Sie die Option Benutzerdefiniert aus. |
| Einstellungsname | Geben Sie den Ausgabeeinstellungen, die Sie erstellen, einen beschreibenden Namen. Sie können beispielsweise &quot;_Kundenausgabe“_ „Endbenutzerausgabe _angeben_. |
| DITA-OT-Befehlszeilenargumente | Geben Sie die zusätzlichen Argumente an, die DITA-OT beim Generieren der Ausgabe verarbeiten soll. Weitere Informationen zu den in DITA-OT unterstützten Befehlszeilenargumenten finden Sie unter [DITA-OT-Dokumentation](https://www.dita-ot.org/). |
| Name der Umwandlung | Geben Sie den Typ der Ausgabe an, die Sie generieren möchten. Dies ist erforderlich, wenn Sie eine Ausgabe mit Ihrem eigenen benutzerdefinierten Plug-in generieren möchten, das im DITA-OT-Plug-in integriert ist. Wenn Sie beispielsweise eine XHTML-Ausgabe generieren möchten, geben Sie `xhtml` an. Eine Liste der in DITA-OT verfügbaren Transformationen finden Sie unter [DITA-OT-Transformationen (Ausgabeformate)](http://www.dita-ot.org/2.3/user-guide/AvailableTransforms.html) im OASIS DITA-OT-Benutzerhandbuch. |
| Dateiname | Geben Sie den Dateinamen an, mit dem die Ausgabe gespeichert werden soll.<br><br>**Hinweis**: Wenn Sie keinen Dateinamen angeben, wird der Titel der DITA-Zuordnung verwendet, um den endgültigen Namen der Ausgabedatei zu generieren. Wenn die Zuordnung keinen Titel hat, wird der Dateiname der DITA-Zuordnung verwendet, um die endgültige Ausgabe zu benennen. Der Dateiname wird mithilfe der im System konfigurierten Regeln bereinigt, um ungültige Zeichen zu verarbeiten. |
| Bedingungen anwenden mit | Wählen Sie eine der folgenden Optionen aus:<br><br>* **Keine angewendet**: Wählen Sie diese Option aus, wenn Sie keine Bedingung auf die veröffentlichte Ausgabe anwenden möchten.<br>* **DITAVal-Datei**: Wählen Sie DITAVal-Dateien aus, um personalisierte Inhalte zu generieren. Sie können mehrere DITAVal-Dateien über das Dialogfeld „Durchsuchen“ oder durch Eingabe des Dateipfads auswählen. Verwenden Sie das Kreuz-Symbol neben dem Dateinamen, um ihn zu entfernen. DITAVal-Dateien werden in der angegebenen Reihenfolge ausgewertet, sodass die in der ersten Datei angegebenen Bedingungen Vorrang vor den in späteren Dateien angegebenen übereinstimmenden Bedingungen haben. Sie können die Dateireihenfolge durch Hinzufügen oder Löschen von Dateien beibehalten. Wenn die DITAVal-Datei an einen anderen Speicherort verschoben oder gelöscht wird, wird sie nicht automatisch aus dem Zuordnungs-Dashboard gelöscht. Sie müssen den Speicherort aktualisieren, falls Dateien verschoben oder gelöscht werden. Sie können den Mauszeiger über den Dateinamen bewegen, um den Pfad im AEM-Repository anzuzeigen, in dem die Datei gespeichert ist. Sie können nur DITAVal-Dateien auswählen. Wenn Sie einen anderen Dateityp ausgewählt haben, wird ein Fehler angezeigt.<br>* **Bedingungsvorgabe**: Wählen Sie in der Dropdown-Liste eine Bedingungsvorgabe aus, um eine Bedingung beim Veröffentlichen der Ausgabe anzuwenden. Die Option ist sichtbar, wenn Sie eine Bedingung auf der Registerkarte „Bedingungsvorgaben“ der DITA-Zuordnungskonsole hinzugefügt haben. Weitere Informationen zu Bedingungsvorgaben finden Sie unter [Verwenden von Bedingungsvorgaben](generate-output-use-condition-presets.md#id1825FL004PN). |
| Zielpfad | Der Pfad innerhalb Ihres AEM-Repositorys, in dem die EPUB-Ausgabe gespeichert wird. |
| Temporäre Dateien aufbewahren | Wählen Sie diese Option, um die von DITA-OT generierten temporären Dateien beizubehalten. Wenn beim Generieren der Ausgabe über DITA-OT Fehler auftreten, wählen Sie diese Option aus, um die temporären Dateien beizubehalten. Anschließend können Sie diese Dateien verwenden, um Fehler bei der Ausgabegenerierung zu beheben.<br> <br> Klicken Sie nach dem Generieren der Ausgabe auf das Symbol **Temporäre Dateien herunterladen** ![Symbol für temporäre Dateien herunterladen](images/download-temp-files-icon.png), um den ZIP-Ordner mit den temporären Dateien herunterzuladen. <br><br> **Hinweis**: Wenn Dateieigenschaften während der Generierung hinzugefügt werden, enthalten die temporären Ausgabedateien auch eine *metadata.xml*-Datei, die diese Eigenschaften enthält. |
| Nachgenerierungs-Workflow ausführen | Wenn Sie diese Option wählen, wird eine neue Dropdown-Liste für den Post-Generation-Workflow angezeigt, die alle in AEM konfigurierten Workflows enthält. Sie müssen einen Workflow auswählen, den Sie nach Abschluss des Workflows zur Ausgabegenerierung ausführen möchten.<br><br>**Hinweis**: Weitere Informationen zum Erstellen eines benutzerdefinierten Workflows für die Post-Output-Generierung finden Sie _Workflow für die Post-Output-Generierung anpassen_ unter Installieren und Konfigurieren von Adobe Experience Manager Guides as a Cloud Service. |
| Baseline verwenden | Wenn Sie eine Baseline für die ausgewählte DITA-Map erstellt haben, wählen Sie diese Option, um die Version anzugeben, die Sie veröffentlichen möchten.<br><br>Weitere Informationen finden [&#x200B; unter „Arbeiten mit &#x200B;](generate-output-use-baseline-for-publishing.md#id1825FI0J0PF)&quot;. |
| Dateieigenschaften | Wählen Sie die Eigenschaften aus, die Sie als Metadaten verarbeiten möchten. Diese Eigenschaften werden auf der Seite Eigenschaften der DITA-Map- oder Bookmap-Datei festgelegt. Die aus der Dropdown-Liste ausgewählten Eigenschaften werden unter dem Feld **Dateieigenschaften** angezeigt. Klicken Sie auf das Kreuzsymbol neben der Eigenschaft, um sie zu entfernen. <br><br>**Hinweis**: Sie können die Metadaten auch mithilfe von DITA-OT-Publishing an die Ausgabe übergeben. Weitere Informationen finden Sie unter [Übergeben der Metadaten an die Ausgabe mithilfe von DITA-OT](pass-metadata-dita-ot.md#id21BJ00QD0XA). |

**Übergeordnetes Thema:**&#x200B;[&#x200B; Verstehen der Ausgabevorgaben](generate-output-understand-presets.md)
