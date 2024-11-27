---
title: Benutzerdefiniert
description: Erfahren Sie, wie Sie benutzerdefinierte Vorgaben im Web-Editor und im Dashboard zuordnen. Konfigurieren Sie eine benutzerdefinierte Ausgabevorgabe in AEM Guides.
feature: Publishing
role: User
source-git-commit: fa07db6a9cb8d8f5b133258acd5647631b22e28a
workflow-type: tm+mt
source-wordcount: '961'
ht-degree: 1%

---

# Benutzerdefiniert {#id205BEF00PX0}

Die benutzerdefinierten Ausgabevorgaben sind für benutzerdefinierte DITA-OT-Plug-ins verfügbar. Sie können eine benutzerdefinierte DITA-OT-Ausgabevorgabe erstellen, um die Ausgabe mithilfe Ihres benutzerdefinierten DITA-OT-Plug-ins zu veröffentlichen.

Sie können die benutzerdefinierte Vorgabe auf zwei Arten erstellen:

**Öffnen Sie im Web Editor:** Öffnen Sie im Bereich &quot;Repository&quot;die DITA-Zuordnungsdatei in der Zuordnungsansicht. Wählen Sie dann auf der Registerkarte &quot;Ausgabe&quot;das Symbol + , um eine Ausgabevorgabe zu erstellen, und wählen Sie dann im Dropdown-Menü Typ im Dialogfeld Vorgabe hinzufügen die Option Benutzerdefiniert aus.

Im Web-Editor wurden die Konfigurationen unter den Registerkarten Allgemein und Erweitert organisiert:

**Allgemein**

Die Registerkarte **Allgemein** enthält die folgenden Konfigurationen:

- DITA-OT-Befehlszeilenargumente
- Name der Umwandlung
- Dateiname
- Ausgabepfad
- Bedingungen anwenden mit \(Wenn die Bedingungen für eine Zuordnung definiert sind\)
- Grundlinie verwenden \(Wenn eine Grundlinie für eine Zuordnung erstellt wird\)
- Arbeitsablauf nach der Erstellung

**Erweitert**

Die Registerkarte Erweitert enthält die folgenden Konfigurationen:

- Beibehalten temporärer Dateien
- Dateieigenschaften

Weitere Informationen finden Sie unter [Benutzerdefinierte Konfiguration](#id231KJA00REJ).

**Aus dem Landkarten-Dashboard**

Um Ausgabevorgaben für das PDF zu öffnen, klicken Sie in der Assets-Benutzeroberfläche auf eine DITA-Zuordnungsdatei, klicken Sie dann auf Ausgabevorgaben und dann auf die Option HTML5 . Klicken Sie oben im Dashboard &quot;Map&quot;auf **Bearbeiten** , um die verschiedenen Konfigurationen zu aktualisieren, und klicken Sie dann auf **Speichern**.

**Benutzerdefinierte Konfiguration**

Die folgenden Optionen sind für die benutzerdefinierte Ausgabevorgabe verfügbar:

| Benutzerdefinierte Ausgabeoptionen | Beschreibung |
| --- | --- |
| Ausgabetyp | Der Typ der Ausgabe, die Sie generieren möchten. Um die Ausgabe mithilfe des benutzerdefinierten DITA-OT-Plug-ins zu generieren, wählen Sie die Option Benutzerdefiniert . |
| Einstellungsname | Geben Sie einen beschreibenden Namen für die Ausgabeeinstellungen ein, die Sie erstellen. Sie können beispielsweise die Ausgabe _Interne Kunden_ oder die Ausgabe _der Endbenutzer_ angeben. |
| DITA-OT-Befehlszeilenargumente | Geben Sie die zusätzlichen Argumente an, die DITA-OT beim Generieren der Ausgabe verarbeiten soll. Weitere Informationen zu den in DITA-OT unterstützten Befehlszeilenargumenten finden Sie in der [DITA-OT-Dokumentation](https://www.dita-ot.org/). |
| Name der Umwandlung | Geben Sie den Typ der Ausgabe an, die Sie generieren möchten. Dies ist erforderlich, wenn Sie die Ausgabe mithilfe Ihres eigenen benutzerdefinierten Plug-ins generieren möchten, das in das DITA-OT-Plug-in integriert ist. Wenn Sie beispielsweise eine XHTML-Ausgabe generieren möchten, geben Sie `xhtml` an. Eine Liste der in DITA-OT verfügbaren Transformationen finden Sie unter [DITA-OT-Transformationen (Ausgabeformate)](http://www.dita-ot.org/2.3/user-guide/AvailableTransforms.html) im OASIS DITA-OT-Benutzerhandbuch. |
| Dateiname | Geben Sie den Dateinamen an, mit dem Sie die Ausgabe speichern möchten.<br><br>**Hinweis**: Wenn Sie keinen Dateinamen angeben, wird der Titel der DITA-Zuordnung verwendet, um den endgültigen Namen der Ausgabedatei zu generieren. Wenn die Zuordnung keinen Titel hat, wird der Dateiname der DITA-Zuordnung verwendet, um die endgültige Ausgabe zu benennen. Der Dateiname wird mithilfe der im System konfigurierten Regeln bereinigt, um ungültige Zeichen zu verarbeiten. |
| Bedingungen anwenden mit | Wählen Sie eine der folgenden Optionen aus:<br><br>* **Keine angewendet**: Wählen Sie diese Option aus, wenn Sie keine Bedingung auf die veröffentlichte Ausgabe anwenden möchten.<br>* **DITAVal-Datei**: Wählen Sie DITAVal-Dateien aus, um personalisierten Inhalt zu generieren. Sie können mehrere DITAVal-Dateien über das Dialogfeld &quot;Durchsuchen&quot;oder durch Eingabe des Dateipfads auswählen. Verwenden Sie das Kreuzsymbol neben dem Dateinamen, um ihn zu entfernen. DITAVal-Dateien werden in der angegebenen Reihenfolge ausgewertet, sodass die in der ersten Datei angegebenen Bedingungen Vorrang vor den in späteren Dateien angegebenen Bedingungen haben. Sie können die Dateireihenfolge beibehalten, indem Sie Dateien hinzufügen oder löschen. Wenn die DITAVal-Datei an einen anderen Speicherort verschoben oder gelöscht wird, wird sie nicht automatisch aus dem Mapping-Dashboard gelöscht. Sie müssen den Speicherort aktualisieren, falls Dateien verschoben oder gelöscht werden. Sie können den Mauszeiger über den Dateinamen bewegen, um den Pfad im AEM Repository anzuzeigen, in dem die Datei gespeichert ist. Sie können nur DITAVal-Dateien auswählen. Wenn Sie einen anderen Dateityp ausgewählt haben, wird ein Fehler angezeigt.<br>* **Bedingungsvorgabe**: Wählen Sie eine Bedingungsvorgabe aus der Dropdown-Liste aus, um beim Veröffentlichen der Ausgabe eine Bedingung anzuwenden. Die Option ist sichtbar, wenn Sie eine Bedingung auf der Registerkarte Bedingungsvorgaben der DITA-Zuordnungskonsole hinzugefügt haben. Weitere Informationen zur Bedingungsvorgabe finden Sie unter [Bedingungsvorgaben verwenden](generate-output-use-condition-presets.md#id1825FL004PN). |
| Zielpfad | Der Pfad in Ihrem AEM-Repository, in dem die EPUB-Ausgabe gespeichert wird. |
| Beibehalten temporärer Dateien | Wählen Sie diese Option, um die von DITA-OT generierten temporären Dateien beizubehalten. Wenn beim Generieren der Ausgabe über DITA-OT Fehler auftreten, wählen Sie diese Option, um die temporären Dateien beizubehalten. Sie können diese Dateien dann verwenden, um Fehler bei der Ausgabenerstellung zu beheben.<br> <br> Nachdem Sie die Ausgabe generiert haben, wählen Sie das Symbol **Temporäre Dateien herunterladen** ![Symbol zum Herunterladen temporärer Dateien](images/download-temp-files-icon.png) aus, um den ZIP-Ordner mit den temporären Dateien herunterzuladen. <br><br> **Hinweis**: Wenn Dateieigenschaften während der Generierung hinzugefügt werden, enthalten die temporären Ausgabedateien auch eine *metadata.xml* -Datei, die diese Eigenschaften enthält. |
| Workflow &quot;Nach der Erstellung ausführen&quot; | Wenn Sie diese Option wählen, wird eine neue Dropdownliste mit dem Workflow nach der Generierung angezeigt, die alle in AEM konfigurierten Workflows enthält. Sie müssen einen Workflow auswählen, der nach Abschluss des Workflows zur Generierung der Ausgabe ausgeführt werden soll.<br><br>**Hinweis**: Weitere Informationen zum Erstellen eines benutzerdefinierten Workflows für die Generierung nach der Ausgabe finden Sie unter _Workflow für die Generierung nach der Ausgabe anpassen_ in Installieren und Konfigurieren von Adobe Experience Manager Guides as a Cloud Service. |
| Grundlinie verwenden | Wenn Sie eine Grundlinie für die ausgewählte DITA-Zuordnung erstellt haben, wählen Sie diese Option, um die Version anzugeben, die Sie veröffentlichen möchten.<br><br>Weitere Informationen finden Sie unter [Arbeiten mit Grundlinie](generate-output-use-baseline-for-publishing.md#id1825FI0J0PF) . |
| Dateieigenschaften | Wählen Sie die Eigenschaften aus, die Sie als Metadaten verarbeiten möchten. Diese Eigenschaften werden auf der Seite &quot;Eigenschaften&quot;der DITA-Map- oder Bookmap-Datei festgelegt. Die Eigenschaften, die Sie aus der Dropdown-Liste auswählen, werden unter dem Feld **Dateieigenschaften** angezeigt. Wählen Sie das Kreuzsymbol neben der Eigenschaft aus, um sie zu entfernen. <br><br>**Hinweis**: Sie können die Metadaten auch mithilfe der DITA-OT-Veröffentlichung an die Ausgabe übergeben. Weitere Informationen finden Sie unter [Übergeben der Metadaten an die Ausgabe mithilfe von DITA-OT](pass-metadata-dita-ot.md#id21BJ00QD0XA). |

**Übergeordnetes Thema:**[ Grundlegendes zu den Ausgabevorgaben](generate-output-understand-presets.md)
