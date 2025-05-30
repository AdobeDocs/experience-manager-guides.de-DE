---
title: EPUB-Voreinstellung
description: Erfahren Sie, wie Sie über das Zuordnungs-Dashboard eine EPUB-Vorgabe erstellen. Konfigurieren der EPUB-Ausgabevorgabe in AEM Guides.
feature: Publishing
role: User
hide: true
exl-id: 1d914a5f-df1f-45eb-86ac-72485fdf07fe
source-git-commit: 1426cdaecdd358f06e76908b09330e65997e8452
workflow-type: tm+mt
source-wordcount: '810'
ht-degree: 1%

---

# EPUB {#id205BED020YT}

Sie können die EPUB-Vorgabe über das Zuordnungs-Dashboard erstellen.

>[!NOTE]
>
> Sie können die Methode zum Generieren von HTML5 mit dem DITA-OT oder FMPS \(wenn Ihr Systemadministrator es konfiguriert hat\) wählen.

Um Ausgabevorgaben für EPUB zu öffnen, klicken Sie auf eine DITA-Zuordnungsdatei, dann auf Ausgabevorgaben und anschließend auf die Option EPUB . Die folgenden Optionen sind für die EPUB-Ausgabe verfügbar:

| EPUB-Optionen | Beschreibung |
| --- | --- |
| Ausgabetyp | Der Typ der Ausgabe, die Sie generieren möchten. Um die EPUB-Ausgabe zu generieren, wählen Sie die Option EPUB . |
| Einstellungsname | Geben Sie einen beschreibenden Namen für die EPUB-Ausgabeeinstellungen an, die Sie erstellen. Sie können beispielsweise &quot;_Kundenausgabe“_ „Endbenutzerausgabe _angeben_. |
| DITA-OT-Befehlszeilenargumente | Geben Sie die zusätzlichen Argumente an, die DITA-OT beim Generieren der Ausgabe verarbeiten soll. Weitere Informationen zu den in DITA-OT unterstützten Befehlszeilenargumenten finden Sie unter [DITA-OT-Dokumentation](https://www.dita-ot.org/). |
| EPub generieren mit | Wählen Sie DITA-OT aus, um die EPUB-Ausgabe zu generieren. |
| Bedingungen anwenden mit | Wählen Sie eine der folgenden Optionen aus:<br><br>* **Keine angewendet**: Wählen Sie diese Option aus, wenn Sie keine Bedingung auf die veröffentlichte Ausgabe anwenden möchten.<br>* **DITAVal-Datei**: Wählen Sie DITAVal-Dateien aus, um personalisierte Inhalte zu generieren. Sie können mehrere DITAVal-Dateien über das Dialogfeld „Durchsuchen“ oder durch Eingabe des Dateipfads auswählen. Verwenden Sie das Kreuz-Symbol neben dem Dateinamen, um ihn zu entfernen. DITAVal-Dateien werden in der angegebenen Reihenfolge ausgewertet, sodass die in der ersten Datei angegebenen Bedingungen Vorrang vor den in späteren Dateien angegebenen übereinstimmenden Bedingungen haben. Sie können die Dateireihenfolge durch Hinzufügen oder Löschen von Dateien beibehalten. Wenn die DITAVal-Datei an einen anderen Speicherort verschoben oder gelöscht wird, wird sie nicht automatisch aus dem Zuordnungs-Dashboard gelöscht. Sie müssen den Speicherort aktualisieren, falls Dateien verschoben oder gelöscht werden. Sie können den Mauszeiger über den Dateinamen bewegen, um den Pfad im AEM-Repository anzuzeigen, in dem die Datei gespeichert ist. Sie können nur DITAVal-Dateien auswählen. Wenn Sie einen anderen Dateityp ausgewählt haben, wird ein Fehler angezeigt. FrameMaker Publishing Server unterstützt nicht mehrere DITAVAL-Dateien.<br>* **Bedingungsvorgabe**: Wählen Sie in der Dropdown-Liste eine Bedingungsvorgabe aus, um eine Bedingung beim Veröffentlichen der Ausgabe anzuwenden. Die Option ist sichtbar, wenn Sie eine Bedingung auf der Registerkarte „Bedingungsvorgaben“ der DITA-Zuordnungskonsole hinzugefügt haben. Weitere Informationen zu Bedingungsvorgaben finden Sie unter [Verwenden von Bedingungsvorgaben](generate-output-use-condition-presets.md#id1825FL004PN). |
| Zielpfad | Der Pfad innerhalb Ihres AEM-Repositorys, in dem die EPUB-Ausgabe gespeichert wird. |
| Dateiname | Geben Sie den Dateinamen an, mit dem Sie die EPUB-Ausgabe speichern möchten.<br><br>**Hinweis**: Wenn Sie keinen Dateinamen angeben, wird der Titel der DITA-Zuordnung verwendet, um den endgültigen EPUB-Ausgabedateinamen zu generieren. Wenn die Zuordnung keinen Titel hat, wird der Dateiname der DITA-Zuordnung verwendet, um die endgültige EPUB-Ausgabe zu benennen. Der Dateiname wird mithilfe der im System konfigurierten Regeln bereinigt, um ungültige Zeichen zu verarbeiten. |
| Name der Umwandlung | Geben Sie den Typ der Ausgabe an, die Sie generieren möchten. Dies ist erforderlich, wenn Sie eine Ausgabe mit Ihrem eigenen benutzerdefinierten Plug-in generieren möchten, das im DITA-OT-Plug-in integriert ist. Wenn Sie beispielsweise eine XHTML-Ausgabe generieren möchten, geben Sie `xhtml` an. Eine Liste der in DITA-OT verfügbaren Transformationen finden Sie unter [DITA-OT-Transformationen (Ausgabeformate)](http://www.dita-ot.org/2.3/user-guide/AvailableTransforms.md) im OASIS DITA-OT-Benutzerhandbuch. |
| Bereinigen temporärer DITA-Dateien | Wählen Sie diese Option, um die von DITA-OT generierten temporären Dateien zu bereinigen. Der Speicherort, an dem DITA-OT temporäre Dateien speichert, finden Sie im Ausgabegenerierungsprotokoll.<br><br>Wenn beim Generieren der Ausgabe über DITA-OT Fehler auftreten, können Sie diese Option deaktivieren, um die temporären Dateien beizubehalten. Anschließend können Sie diese Dateien verwenden, um Fehler bei der Ausgabegenerierung zu beheben. |
| Nachgenerierungs-Workflow ausführen | Wenn Sie diese Option wählen, wird eine neue Dropdown-Liste für den Post-Generation-Workflow angezeigt, die alle in AEM konfigurierten Workflows enthält. Sie müssen einen Workflow auswählen, den Sie nach Abschluss des Workflows zur Ausgabegenerierung ausführen möchten.<br><br>**Hinweis**: Weitere Informationen zum Erstellen eines benutzerdefinierten Workflows für die Post-Output-Generierung finden Sie _Workflow für die Post-Output-Generierung anpassen_ unter Installieren und Konfigurieren von Adobe Experience Manager Guides as a Cloud Service. |
| Baseline verwenden | Wenn Sie eine Baseline für die ausgewählte DITA-Map erstellt haben, wählen Sie diese Option, um die Version anzugeben, die Sie veröffentlichen möchten.<br><br>Weitere Informationen finden [ unter „Arbeiten mit ](generate-output-use-baseline-for-publishing.md#id1825FI0J0PF)&quot;. |
| Eigenschaften | Wählen Sie die Eigenschaften aus, die Sie als Metadaten verarbeiten möchten. Diese Eigenschaften werden auf der Seite Eigenschaften der DITA-Map- oder Bookmap-Datei festgelegt. Die Eigenschaften, die Sie aus der Dropdown-Liste auswählen, werden unter dem Feld Eigenschaften aufgeführt und aus der Dropdown-Liste entfernt. Nach dem Festlegen werden diese Eigenschaften auch in die Themen innerhalb der Zuordnung kopiert.<br><br>**Hinweis**: Sie können die Metadaten auch mithilfe von DITA-OT-Publishing an die Ausgabe übergeben. Weitere Informationen finden Sie unter [Übergeben der Metadaten an die Ausgabe mithilfe von DITA-OT](pass-metadata-dita-ot.md#id21BJ00QD0XA). |

**Übergeordnetes Thema:**&#x200B;[ Verstehen der Ausgabevorgaben](generate-output-understand-presets.md)
