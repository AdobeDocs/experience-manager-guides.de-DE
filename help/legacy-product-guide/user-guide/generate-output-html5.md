---
title: Verwenden von HTML5
description: Erfahren Sie, wie Sie eine HTML5-Vorgabe über den Web-Editor und das Zuordnungs-Dashboard erstellen. Konfigurieren der HTML5-Ausgabevorgabe in AEM Guides.
feature: Publishing
role: User
hide: true
exl-id: e0ea38ac-84f1-4022-91e3-4827f123b26f
source-git-commit: 6e23f52fc9124d0f07f8108da1b5fe574f553469
workflow-type: tm+mt
source-wordcount: '1224'
ht-degree: 1%

---

# HTML5 {#id205BE700XO1}

Die HTML5-Ausgabe wird in einer flachen Ordnerhierarchie generiert. Dies bedeutet, dass die vom Inhalt im Repository verwendete Ordnerstruktur nicht in der HTML5-Ausgabe repliziert wird. Der gesamte Inhalt wird im HTML5-Ausgabeformat veröffentlicht und in einem einzigen Ordner gespeichert. Die Dateinamen werden in der generierten Ausgabe ebenfalls durch die UUIDs der Dateien ersetzt. Die einzige Datei ohne UUID-basierten Dateinamen ist die Datei index.html.

Sie können die HTML-Vorgabe auf zwei Arten erstellen:

**Im Web-Editor:** Öffnen Sie im Repository-Bereich die DITA-Zuordnungsdatei in der Zuordnungsansicht, wählen Sie dann auf der Registerkarte Ausgabe das Symbol + aus, um eine Ausgabevorgabe zu erstellen, und wählen Sie dann HTML5 aus der Dropdown-Liste Typ im Dialogfeld Vorgabe hinzufügen aus.

>[!NOTE]
>
> Sie können die Methode zum Generieren von HTML5 mit dem DITA-OT oder FMPS \(wenn Ihr Systemadministrator es konfiguriert hat\) wählen.

Im Web-Editor wurden die Konfigurationen auf den Registerkarten Allgemein und Erweitert organisiert:

**Allgemein**

Die Registerkarte **Allgemein** enthält die folgenden Konfigurationen:

- Ausgabepfad
- DITA-OT-Befehlszeilenargumente
- Dateiname
- Bedingungen mithilfe von \(Wenn die Bedingungen für eine Zuordnung definiert sind\) anwenden
- Baseline verwenden \(Wenn eine Baseline für eine Zuordnung erstellt wird\)
- Nachgenerierungs-Workflow

**Erweitert**

Die Registerkarte Erweitert enthält die folgenden Konfigurationen:

- Name der Umwandlung
- Temporäre Dateien aufbewahren
- Dateieigenschaften

Weitere Informationen finden Sie unter [HTML5-Konfiguration](#id231KJA00REJ).

**Vom Zuordnungs-Dashboard**

Um Ausgabevorgaben für PDF zu öffnen, klicken Sie in der Assets-Benutzeroberfläche auf eine DITA-Zuordnungsdatei, klicken Sie dann auf Ausgabevorgaben und dann auf die Option HTML5 . Klicken Sie im Zuordnungs-Dashboard oben auf **Bearbeiten**, um die verschiedenen Konfigurationen zu aktualisieren, und klicken Sie dann auf **Speichern**.

**HTML5-Konfiguration**

Für die HTML5-Ausgabe stehen die folgenden Optionen zur Verfügung:

| HTML5-Optionen | Beschreibung |
| --- | --- |
| Ausgabetyp | Der Typ der Ausgabe, die Sie generieren möchten. Um die HTML5-Ausgabe zu generieren, wählen Sie die Option HTML5 aus. |
| Einstellungsname | Geben Sie einen beschreibenden Namen für die HTML5-Ausgabeeinstellungen an, die Sie erstellen. Sie können beispielsweise &quot;_Kundenausgabe“_ „Endbenutzerausgabe _angeben_. |
| DITA-OT-Befehlszeilenargumente | Geben Sie die zusätzlichen Argumente an, die DITA-OT beim Generieren der Ausgabe verarbeiten soll. Weitere Informationen zu den in DITA-OT unterstützten Befehlszeilenargumenten finden Sie unter [DITA-OT-Dokumentation](https://www.dita-ot.org/). |
| Generieren eines responsiven Formulars mit | Wählen Sie DITA-OT aus, um die HTML5-Ausgabe zu generieren. |
| Bedingungen anwenden mit | Wählen Sie eine der folgenden Optionen aus:<br><br>* **Keine angewendet**: Wählen Sie diese Option aus, wenn Sie keine Bedingung auf die veröffentlichte Ausgabe anwenden möchten.<br>* **DITAVal-Datei**: Wählen Sie DITAVal-Dateien aus, um personalisierte Inhalte zu generieren. Sie können mehrere DITAVal-Dateien über das Dialogfeld „Durchsuchen“ oder durch Eingabe des Dateipfads auswählen. Verwenden Sie das Kreuz-Symbol neben dem Dateinamen, um ihn zu entfernen. DITAVal-Dateien werden in der angegebenen Reihenfolge ausgewertet, sodass die in der ersten Datei angegebenen Bedingungen Vorrang vor den in späteren Dateien angegebenen übereinstimmenden Bedingungen haben. Sie können die Dateireihenfolge durch Hinzufügen oder Löschen von Dateien beibehalten. Wenn die DITAVal-Datei an einen anderen Speicherort verschoben oder gelöscht wird, wird sie nicht automatisch aus dem Zuordnungs-Dashboard gelöscht. Sie müssen den Speicherort aktualisieren, falls Dateien verschoben oder gelöscht werden. Sie können den Mauszeiger über den Dateinamen bewegen, um den Pfad im AEM-Repository anzuzeigen, in dem die Datei gespeichert ist. Sie können nur DITAVal-Dateien auswählen. Wenn Sie einen anderen Dateityp ausgewählt haben, wird ein Fehler angezeigt. FrameMaker Publishing Server unterstützt nicht mehrere DITAVAL-Dateien.<br>* **Bedingungsvorgabe**: Wählen Sie in der Dropdown-Liste eine Bedingungsvorgabe aus, um eine Bedingung beim Veröffentlichen der Ausgabe anzuwenden. Die Option ist sichtbar, wenn Sie eine Bedingung auf der Registerkarte „Bedingungsvorgaben“ der DITA-Zuordnungskonsole hinzugefügt haben. Weitere Informationen zu Bedingungsvorgaben finden Sie unter [Verwenden von Bedingungsvorgaben](generate-output-use-condition-presets.md#id1825FL004PN).<br><br>Sie können mehrere DITAVAL-Dateien über das Dialogfeld „Durchsuchen“ oder durch Eingabe des Dateipfads auswählen. Verwenden Sie das Kreuz-Symbol neben dem Dateinamen, um ihn zu entfernen. DITAVAL-Dateien werden in der angegebenen Reihenfolge ausgewertet, sodass die in der ersten Datei angegebenen Bedingungen Vorrang vor den in späteren Dateien angegebenen übereinstimmenden Bedingungen haben. Sie können die Dateireihenfolge durch Hinzufügen oder Löschen von Dateien beibehalten. Sie müssen den Speicherort aktualisieren, falls Dateien verschoben oder gelöscht werden. Sie können den Mauszeiger über den Dateinamen bewegen, um den Pfad im AEM-Repository anzuzeigen, in dem die Datei gespeichert ist. Sie können nur DITAVAL-Dateien speichern. Wenn Sie eine andere Datei ausgewählt haben, wird ein Fehler angezeigt.<br><br>**Hinweis**: FrameMaker Publishing Server unterstützt nicht mehrere DITAVAL-Dateien. |
| Name der Umwandlung | Geben Sie den Typ der Ausgabe an, die Sie generieren möchten. Dies ist erforderlich, wenn Sie eine Ausgabe mit Ihrem eigenen benutzerdefinierten Plug-in generieren möchten, das im DITA-OT-Plug-in integriert ist. Wenn Sie beispielsweise eine XHTML-Ausgabe generieren möchten, geben Sie `xhtml` an. Eine Liste der in DITA-OT verfügbaren Transformationen finden Sie unter [DITA-OT-Transformationen (Ausgabeformate)](http://www.dita-ot.org/2.3/user-guide/AvailableTransforms.html) im OASIS DITA-OT-Benutzerhandbuch. |
| Dateiname | Geben Sie den Dateinamen an, mit dem Sie die HTML5-Ausgabe speichern möchten.<br><br>**Hinweis**:If Wenn Sie keinen Dateinamen angeben, wird der Titel der DITA-Zuordnung verwendet, um den endgültigen HTML5-Ausgabedateinamen zu generieren. Wenn die Zuordnung keinen Titel hat, wird der Dateiname der DITA-Zuordnung verwendet, um die endgültige HTML5-Ausgabe zu benennen. Der Dateiname wird mithilfe der im System konfigurierten Regeln bereinigt, um ungültige Zeichen zu verarbeiten. |
| Nachgenerierungs-Workflow ausführen | Wenn Sie diese Option wählen, wird eine neue Dropdown-Liste für den Post-Generation-Workflow angezeigt, die alle in AEM konfigurierten Workflows enthält. Sie müssen einen Workflow auswählen, den Sie nach Abschluss des Workflows zur Ausgabegenerierung ausführen möchten.<br><br>**Hinweis**:For Weitere Informationen zum Erstellen eines benutzerdefinierten Workflows für die Nachbearbeitungsgenerierung finden Sie unter _Anpassen des Workflows für die Nachbearbeitungsgenerierung_ in Installieren und Konfigurieren von Adobe Experience Manager Guides as a Cloud Service. |
| Zielpfad | Der Pfad innerhalb Ihres AEM-Repositorys, in dem die HTML5-Ausgabe gespeichert wird. |
| Temporäre Dateien aufbewahren | Wählen Sie diese Option, um die von DITA-OT generierten temporären Dateien beizubehalten. Wenn beim Generieren der Ausgabe über DITA-OT Fehler auftreten, wählen Sie diese Option aus, um die temporären Dateien beizubehalten. Anschließend können Sie diese Dateien verwenden, um Fehler bei der Ausgabegenerierung zu beheben.<br> <br> Klicken Sie nach dem Generieren der Ausgabe auf das Symbol **Temporäre Dateien herunterladen** ![Symbol für temporäre Dateien herunterladen](images/download-temp-files-icon.png), um den ZIP-Ordner mit den temporären Dateien herunterzuladen. <br><br> **Hinweis**: Wenn Dateieigenschaften während der Generierung hinzugefügt werden, enthalten die temporären Ausgabedateien auch eine *metadata.xml*-Datei, die diese Eigenschaften enthält. |
| Dateihierarchie reduzieren | Wählen Sie die Option aus, um die HTML5-Ausgabe in einer flachen Ordnerhierarchie zu generieren. Der gesamte Inhalt wird im HTML5-Ausgabeformat in einer flachen Dateihierarchie veröffentlicht und in einem einzigen Ordner gespeichert. <br> Wenn Sie diese Option deaktivieren, wird die Ausgabe in einer verschachtelten Ordnerhierarchie generiert und die gesamte Ordnerstruktur repliziert. |
| Baseline verwenden | Wenn Sie eine Baseline für die ausgewählte DITA-Map erstellt haben, wählen Sie diese Option, um die Version anzugeben, die Sie veröffentlichen möchten.<br><br>Weitere Informationen finden [&#x200B; unter „Arbeiten mit &#x200B;](generate-output-use-baseline-for-publishing.md#id1825FI0J0PF)&quot;. |
| Dateieigenschaften | Wählen Sie die Eigenschaften aus, die Sie als Metadaten verarbeiten möchten. Diese Eigenschaften werden auf der Seite Eigenschaften der DITA-Map- oder Bookmap-Datei festgelegt. Die aus der Dropdown-Liste ausgewählten Eigenschaften werden unter dem Feld **Dateieigenschaften** angezeigt. Klicken Sie auf das Kreuzsymbol neben der Eigenschaft, um sie zu entfernen. <br><br>**Hinweis**: Sie können die Metadaten auch mithilfe von DITA-OT-Publishing an die Ausgabe übergeben. Weitere Informationen finden Sie unter [Übergeben der Metadaten an die Ausgabe mithilfe von DITA-OT](pass-metadata-dita-ot.md#id21BJ00QD0XA). |

**Übergeordnetes Thema:**&#x200B;[&#x200B; Verstehen der Ausgabevorgaben](generate-output-understand-presets.md)
