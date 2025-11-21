---
title: AEM Sites
description: Erstellen und konfigurieren Sie die AEM Sites-Vorgabe in der Zuordnungskonsole mit der Zuordnung zusammengesetzter Komponenten und der Zuordnung veralteter Komponenten.
feature: Publishing
role: User
exl-id: f3657268-9dee-43af-b643-499dbc3ca948
source-git-commit: 6e23f52fc9124d0f07f8108da1b5fe574f553469
workflow-type: tm+mt
source-wordcount: '3592'
ht-degree: 0%

---

# AEM Sites-Vorgabe in der Zuordnungskonsole

Sie können die AEM Sites-Vorgabe über die Zuordnungskonsole erstellen und sie so konfigurieren, dass sie die AEM Sites-Ausgabe generiert. Es gibt zwei Möglichkeiten, die AEM Sites-Ausgabe zu erstellen:

- [Verwenden der Zuordnung von zusammengesetzten Komponenten](#use-composite-component-mapping)
- [Verwenden der Zuordnung veralteter Komponenten](#use-legacy-component-mapping)

>[!TIP]
>
> Es wird empfohlen, für eine verbesserte Leistung die Komponentenzuordnung zu verwenden, die in der Experience Manager Guides-Version 2502 und neueren Versionen verfügbar ist.

## Verwenden der Zuordnung von zusammengesetzten Komponenten

Die Zuordnung zusammengesetzter Komponenten bietet eine schnellere und skalierbare Veröffentlichung in AEM Sites im Vergleich zur bisherigen Komponentenzuordnung. Sie enthält im Lieferumfang enthaltene bearbeitbare Vorlagen, die mithilfe des AEM-Vorlageneditors Ihren Anforderungen entsprechend angepasst werden können. Die Vorlagen verwenden eine Mischung aus WCM-Kernkomponenten und spezialisierten `guides-components`, um sicherzustellen, dass Ihre Endbenutzer das beste Erlebnis auf Ihren AEM Sites-Seiten erhalten. Sie können Ihre vorhandenen Vorlagen auch mithilfe der Zuordnungsmethode für zusammengesetzte Komponenten anpassen.

Experience Manager Guides bietet vordefinierte Vorlagen zum Erstellen von AEM Sites. Mit diesen Vorlagen können Sie Konsistenz im Inhaltslayout und in der Inhaltsstruktur sicherstellen.
- [Erstellen Sie Startseiten](../cs-install-guide/download-install-aem-sites-templates-cs.md#create-a-home-page-using-the-template) basierend auf diesen vordefinierten Vorlagen.
- Sie können [Themenvorlagen bearbeiten](../cs-install-guide/download-install-aem-sites-templates-cs.md#package-installation) und Stile Ihren Anforderungen entsprechend anwenden.
- Sie können auch [vorhandene AEM Sites-Vorlagen anpassen](../cs-install-guide/download-install-aem-sites-templates-cs.md#customize-existing-aem-sites-templates).


**AEM Sites-Voreinstellung erstellen**

Führen Sie die folgenden Schritte aus, um die AEM Sites-Vorgabe mithilfe der Zuordnung zusammengesetzter Komponenten zu erstellen:

1. [Öffnen Sie die DITA-Zuordnungsdatei in der Zuordnungskonsole](./open-files-map-console.md).
1. Wählen Sie **Bedienfeld &quot;**&quot; das Symbol + , um eine Ausgabevorgabe zu erstellen.
1. Wählen Sie **AEM Sites** aus der Dropdown **Liste „Typ** im Dialogfeld **Neue**) aus.
1. Deaktivieren Sie die Option **Veraltete Komponentenzuordnung verwenden**.
1. Wählen Sie die **Zum aktuellen Ordnerprofil hinzufügen**, um eine Ausgabevorgabe innerhalb des aktuellen Ordnerprofils zu erstellen. Das ![Ordnerprofilsymbol](images/global-preset-icon.svg) gibt eine Vorgabe auf Ordnerprofilebene an.

   Weitere Informationen zu [Verwalten globaler und Ordnerprofil-Ausgabevorgaben](./web-editor-manage-output-presets.md).

1. Wählen Sie **Hinzufügen** aus.

   Die Voreinstellung für AEM Sites wird erstellt.


   ![Neue ](images/new-aem-sites-dialog-box.png){width="300" align="left"}

<!-----------------------
### Generate the AEM Sites output using the templates

Once, the preset is created, you can configure the various options available for AEM Sites output generation. Experience Manager Guides allows you to use the out of the box templates or add your own AEM Sites templates.

You can configure the Out-of-the-box Sites template  in two ways:

- In the **Sites** field, select the AEM sites where you want to publish your output.  For example, `AEMG Docs`.

    The **Publish path** and the **Topic page template** options are automatically set in the dropdown.  For example,  `AEMG-Docs-Site/en/docs/product1` and `Topic page` are set respectively. You can also choose the other options from the dropdown.

- Or, Select the **Use Sites path** option to select the complete Sites path, and then select a **Map page template**. 

    You can browse a predefined Sites path or specify a custom path even if the specified path has not been pre-created within the AEM Sites structure. In such cases, the system creates the necessary structure during the publishing process by using the selected map homepage template.

   For example, you can specify the path `/content/AEMG-Docs-Site/en/docs/product4` where the `product4`does not exist in the strcuture. In this case, the system automatically creates `product4` using the selected **Map page template** and publish the output within this newly created page. 
   
   The **Topic page template** is automatically set as `Topic Page`. However, you can choose to select other available options in the dropdown.

--->

### AEM Sites-Vorgabenkonfiguration für die Zuordnung von zusammengesetzten Komponenten

>[!NOTE]
>
> Bevor Sie die AEM Sites-Vorgabe für Experience Manager Guides konfigurieren, muss Ihr Administrator eine AEM Sites-Struktur mithilfe der Vorlagen erstellen.

- **On-Premise-Software**: Erfahren Sie mehr über das [Herunterladen und Installieren von AEM Sites-Vorlagen](../install-guide/download-install-aem-sites-templates.md) für On-Premise-Software.
- **Cloud Service**: Erfahren Sie mehr darüber, wie Sie [AEM Sites-Vorlagen herunterladen und installieren](../cs-install-guide/download-install-aem-sites-templates-cs.md) für Cloud Service.

In der Zuordnungskonsole sind die voreingestellten Konfigurationsoptionen für die Zuordnung zusammengesetzter Komponenten auf den folgenden Registerkarten organisiert:

- Allgemein
- Inhalt
- Themenliste
- Querverweise auf Zuordnungen

![Neue ](images/aem-sites-new-config.png){width="650" align="left"}

**Allgemein**

Die **Allgemein** enthält die folgenden Konfigurationsoptionen:

| AEM Sites-Optionen | Beschreibung |
| --- | --- |
| Site-Pfad verwenden | Verwenden Sie diese Option, um Ihre Inhalte auf einer Experience Manager-Site zu veröffentlichen. |
| Site-Pfad | **Diese Option wird angezeigt, wenn Sie die Option** Site-Pfad verwenden **auswählen**. Durchsuchen Sie den vordefinierten Pfad der Experience Manager-Site oder geben Sie einen benutzerdefinierten Pfad an, unter dem die Ausgabe veröffentlicht werden soll. Mit **Option „Sites**&quot; können Sie den gesamten Veröffentlichungspfad angeben, auch wenn der angegebene Pfad nicht in der AEM Sites-Struktur vorab erstellt wurde. In solchen Fällen erstellt das System die notwendige Struktur während des Publishing-Prozesses, indem es die ausgewählte Map-Homepage-Vorlage verwendet.<br><br>Sie können beim Festlegen des Site-Pfads auch Variablen verwenden. Weitere Informationen finden Sie unter [Verwenden von Variablen zum Festlegen der Optionen Zielpfad, Site-Name oder Dateiname](./generate-output-use-variables.md) |
| Seitenvorlage zuordnen | **Diese Option wird angezeigt, wenn Sie die Option** Site-Pfad verwenden **auswählen**. Wählen Sie eine Vorlage aus, die Sie für die Zuordnungs-Startseiten anwenden möchten. |
| Site | Name der Experience Manager Sites, in der Sie Ihre Inhalte veröffentlichen möchten. Die Optionen in der Dropdown-Liste werden basierend auf der Liste der in AEM Sites verfügbaren Sites ausgefüllt. <br>Wählen Sie **Aktualisieren** ![Aktualisierungssymbol ](images/navtitle-refresh-icon.svg), um eine neue Liste von Optionen abzurufen und die aktualisierten Daten widerzuspiegeln. |
| Veröffentlichungspfad | Der Pfad innerhalb Ihres AEM-Repositorys, in dem die Ausgabe gespeichert wird. Der Veröffentlichungspfad wird mit allen Pfaden gefüllt, die Seiten enthalten, die basierend auf der Startseitenvorlage erstellt wurden. Unter diesem Pfad wird die AEM Sites-Ausgabe der DITA-Zuordnung generiert.  Wenn Sie beispielsweise die Site als `AEMG-Docs` und den Veröffentlichungspfad als `aemg-docs-en/docs/product-abc.` angeben, wird die AEM Sites-Ausgabe unter dem `aemg-docs-en/docs/product-abc/` in `crx/de` generiert. |
| Themenseitenvorlage | Wählen Sie die Vorlage aus, die Sie auf alle Ausgabethemen anwenden möchten. |
| Seitennamen generieren basierend auf | **Themendateiname**: Verwendet den Dateinamen des DITA-Themas, um die Website-URL zu erstellen. <br> **Thementitel**: Verwendet den Titel des DITA-Themas zum Erstellen der Experience Manager-Site-Namen. |
| Bereinigen von zuvor generierten Seiten | - **Löschen Sie zuvor generierte Seiten für ein Thema, das aus der Zuordnung entfernt wurde**: Wenn sich die Struktur der DTIA-Zuordnung ändert, können Sie diese Option verwenden, um die zuvor generierten Seiten für die entfernten Themen zu entfernen. Diese Funktion ist nur für die vollständige Veröffentlichung von Karten verfügbar.<br><br>Angenommen, Sie haben eine DITA-Karte veröffentlicht, die die Themen a.dita, b.dita und c.dita enthält. Bevor Sie die Karte erneut veröffentlichen, haben Sie das Thema b.dita aus der Karte entfernt. Wenn Sie diese Option jetzt ausgewählt haben, wird der gesamte Inhalt, der mit b.dita zusammenhängt, aus der AEM Sites-Ausgabe entfernt und nur a.dita und c.dita werden veröffentlicht.<br><br>**Hinweis**: Informationen zu gelöschten Seiten werden ebenfalls in den Ausgabegenerierungsprotokollen erfasst. Weitere Informationen zum Zugriff auf die Protokolldateien finden Sie [Anzeigen und Überprüfen der Protokolldatei](generate-output-basic-troubleshooting.md#id1821I0Y0G0A__id1822G0P0CHS). <br><br>**Achtung**: Beim Löschen der Themen sind die Seiten dann nicht mehr auf der veröffentlichten Site verfügbar. Bevor die Themen gelöscht werden, wird eine Warnung angezeigt. Sie müssen das Löschen bestätigen.<br><br>- **Löschen Sie alle Seiten, die von anderen Quellen unter diesem Pfad erstellt wurden**: Wenn Sie diese Option auswählen, werden alle Seiten, die unter diesem Pfad aus anderen Karten, einzelnen Themen oder einer anderen Quelle veröffentlicht wurden, gelöscht. Die Seiten werden auch auf der veröffentlichten Site nicht mehr verfügbar sein. Bevor die Themen gelöscht werden, wird eine Warnung angezeigt. Sie müssen das Löschen bestätigen. |
| Nachgenerierungs-Workflow | Wenn Sie diese Option wählen, wird eine neue Dropdown-Liste für den Post-Generation-Workflow angezeigt, die alle in AEM konfigurierten Workflows enthält. Sie müssen einen Workflow auswählen, den Sie nach Abschluss des Workflows zur Ausgabegenerierung ausführen möchten. |

**Inhalt**

Die **Inhalt**-Registerkarte enthält die folgenden Konfigurationsoptionen:

| AEM Sites-Optionen | Beschreibung |
| --- | --- |
| Baseline verwenden | Wenn Sie eine Baseline für die ausgewählte DITA-Map erstellt haben, wählen Sie diese Option, um die Version anzugeben, die Sie veröffentlichen möchten.<br><br>Weitere Informationen finden Sie [ „Arbeiten mit ](generate-output-use-baseline-for-publishing.md#id1825FI0J0PF)&quot;. |
| Bedingte Filterung | Eine der folgenden Optionen auswählen:<br><br>**None**: Wählen Sie diese Option aus, wenn Sie keine Bedingung auf die veröffentlichte Ausgabe anwenden möchten.<br>**Verwenden von DITAVAL**: Wählen Sie DITAVal-Datei(en) aus, um bedingte Inhalte zu generieren. Sie können mehrere DITAVal-Dateien über das Dialogfeld „Durchsuchen“ oder durch Eingabe des Dateipfads auswählen. Verwenden Sie das Kreuz-Symbol neben dem Dateinamen, um ihn zu entfernen. DITAVal-Dateien werden in der angegebenen Reihenfolge ausgewertet, sodass die in der ersten Datei angegebenen Bedingungen Vorrang vor den in späteren Dateien angegebenen übereinstimmenden Bedingungen haben. Sie können die Dateireihenfolge durch Hinzufügen oder Löschen von Dateien beibehalten. Wenn die DITAVal-Datei an einen anderen Speicherort verschoben oder gelöscht wird, wird sie nicht automatisch aus dem Zuordnungs-Dashboard gelöscht. Sie müssen den Speicherort aktualisieren, falls Dateien verschoben oder gelöscht werden. Sie können den Mauszeiger über den Dateinamen bewegen, um den Pfad im AEM-Repository anzuzeigen, in dem die Datei gespeichert ist. Sie können nur DITAVal-Dateien auswählen. Wenn Sie einen anderen Dateityp auswählen, wird ein Fehler angezeigt.<br>**Bedingungsvorgabe**: Wählen Sie in der Dropdown-Liste eine Bedingungsvorgabe aus, um eine Bedingung beim Veröffentlichen der Ausgabe anzuwenden. Diese Option ist sichtbar, wenn Sie eine Bedingung für die DITA-Zuordnungsdatei hinzugefügt haben. Die bedingten Einstellungen sind auf der Registerkarte „Bedingungsvorgaben“ der DITA-Zuordnungskonsole verfügbar. Weitere Informationen zu Bedingungsvorgaben finden Sie unter [Verwenden von Bedingungsvorgaben](generate-output-use-condition-presets.md#id1825FL004PN). |
| Zusätzliche DITA-OT-Befehlszeilenargumente | Geben Sie die zusätzlichen Argumente an, die DITA-OT beim Generieren der Ausgabe verarbeiten soll. Weitere Informationen zu den in DITA-OT unterstützten Befehlszeilenargumenten finden Sie unter [DITA-OT-Dokumentation](https://www.dita-ot.org/). |
| Metadaten <br> <br>Dateieigenschaften (Assets) | Wählen Sie die Eigenschaften aus, die Sie als Metadaten verarbeiten möchten. Diese Eigenschaften werden auf der Seite Eigenschaften der DITA-Map- oder Bookmap-Datei festgelegt. Die aus der Dropdown-Liste ausgewählten Eigenschaften werden unter dem Feld **Dateieigenschaften** angezeigt. Klicken Sie auf das Kreuzsymbol neben der Eigenschaft, um sie zu entfernen. <br><br>**Hinweis**: Bei den Metadateneigenschaften wird zwischen Groß- und Kleinschreibung unterschieden.<br><br>*Wenn Sie eine Baseline ausgewählt haben, basieren die Werte für die Eigenschaften auf der Version der ausgewählten Baseline.<br>* Wenn Sie keine Baseline ausgewählt haben, basieren die Werte für die Eigenschaften auf der neuesten Version.<br><br>Sie können die Metadaten auch mithilfe von DITA-OT-Publishing an die Ausgabe übergeben. Für eine weitere Detailansicht ([ Sie die Metadaten mithilfe von DITA-OT an die Ausgabe ](pass-metadata-dita-ot.md#id21BJ00QD0XA).<br><br>**Hinweis**: Wenn Sie die `cq:tags` nicht in der Option Eigenschaften definiert haben, werden die Werte für `cq:tags` aus der aktuellen Arbeitskopie ausgewählt, selbst wenn Sie eine Baseline für die Veröffentlichung ausgewählt haben. |
| Metadaten <br> <br>Verwenden von Zuordnungseigenschaften als Fallback | Wenn diese Option aktiviert ist, werden die für die Zuordnungsdatei definierten Eigenschaften auch in die Themen kopiert, in denen diese Eigenschaften nicht definiert sind. Beachten Sie bei Verwendung dieser Option die folgenden Punkte <br><br>*Nur Zeichenfolgen-, Datums- oder Lange-Eigenschaften (einzelne und mehrwertige Eigenschaften) können an die Seiten der AEM-Site übergeben werden.<br>* Die Metadatenwerte für eine Eigenschaft vom Typ Zeichenfolge unterstützen keine Sonderzeichen (z. B. `@, #, " "`).<br>* Diese Option sollte zusammen mit der Option `Properties` verwendet werden. |

**Themenliste**

Auf **Registerkarte** Themenliste) wird die Liste der Themen angezeigt, die in der aktuellen Arbeitskopie der DITA-Zuordnung vorhanden sind. Standardmäßig sind alle Themen enthalten. Sie können bestimmte Themen auswählen und die AEM Sites-Ausgabe nur für sie generieren. Sie haben beispielsweise einige Themen aktualisiert, sodass Sie nur diese Themen veröffentlichen können, anstatt die gesamte DITA-Karte zu veröffentlichen.

![AEM Sites-Themenliste](images/aem-presets-topic-list.png) {align="left"}


>[!NOTE]
>
> Wenn auf der Registerkarte **Inhalt“ eine Baseline ausgewählt**, zeigt die Themenliste Themen und deren Versionen aus der angehängten Baseline an. Außerdem sollte die inkrementelle Veröffentlichung über die Themenliste nur verwendet werden, wenn sich die Struktur der Zuordnung nicht ändert. Wenn sich die Zuordnungsstruktur/das Inhaltsverzeichnis ändert, sollte die gesamte Zuordnung einmal veröffentlicht werden, um das Inhaltsverzeichnis zu aktualisieren.

**Querverweise auf Zuordnungen**

Diese Liste enthält Themen mit Querverweisen auf `scope ="peer"`. Sie können den Veröffentlichungskontext für eine Liste von Querverweiskarten mit `scope="peer"` zu Themen angeben, die in anderen DITA-Zuordnungen verfügbar sind. Diese Registerkarte wird angezeigt, wenn Sie die Experience Manager Guides-Version (UUID) verwenden.

Weitere Informationen finden Sie im Abschnitt [Arbeiten mit verknüpften Themen](#working-with-linked-topics) unten.

Speichern Sie nach der Konfiguration die vorgenommenen Änderungen an der Voreinstellung und wählen Sie **Generieren** aus, um AEM Sites für die entsprechende Zuordnung zu generieren.

>[!NOTE]
>
> Wenn Sie Inhalte zum ersten Mal auf AEM Sites veröffentlichen, wird empfohlen, die Seiten auf Site-Ebene zu veröffentlichen. Dadurch wird sichergestellt, dass die Ausgabe ohne CSS **Unterbrechung korrekt** der Veröffentlichungsinstanz angezeigt wird.

## Verwenden der Zuordnung veralteter Komponenten

Die Schritte zum Erstellen der AEM Sites-Vorgabe mit der Zuordnung veralteter Komponenten sind mit denen identisch, die im Abschnitt [Zuordnung ](#use-composite-component-mapping) zusammengesetzten Komponenten“ oben beschrieben wurden. Stellen Sie jedoch beim Erstellen der Vorgabe sicher, dass Sie die Option **Alte Komponentenzuordnung verwenden** im Dialogfeld **Neue**&quot; auswählen.

![](images/aem-sites-output-legacy.png) {width="300" align="left"}

In der Zuordnungskonsole sind die voreingestellten Konfigurationsoptionen für die Zuordnung veralteter Komponenten auf den folgenden Registerkarten organisiert:

- Allgemein
- Inhalt
- Querverweise auf Zuordnungen

![Neue ](images/aem-sites-preset-legacy-config.png){width="500" align="left"}

**Allgemein**

Die **Allgemein** enthält die folgenden Konfigurationsoptionen:

| AEM Sites-Optionen | Beschreibung |
| --- | --- |
| Site-Name | Ein Site-Name, unter dem die Ausgabe in Ihrem AEM-Repository gespeichert wird.<br><br>Ein Knoten im AEM-Repository wird mit dem hier angegebenen Namen erstellt. Wenn Sie den Site-Namen nicht angeben, wird der Site-Knoten mit dem DITA-Map-Dateinamen erstellt.<br><br>Der hier angegebene Site-Name wird auch als Titel auf der Browser-Registerkarte verwendet.<br><br>Sie können beim Festlegen des Site-Namens auch Variablen verwenden. Weitere Informationen finden Sie unter [Verwenden von Variablen zum Festlegen der Optionen Zielpfad, Site-Name oder Dateiname](./generate-output-use-variables.md) |
| Ausgabepfad | Der Pfad innerhalb Ihres AEM-Repositorys, in dem die Ausgabe gespeichert wird. Beim Generieren der endgültigen Ausgabe werden der Site-Name und der Ausgabepfad kombiniert. Wenn Sie beispielsweise den Site-Namen als `user-guide` und den Ausgabepfad als `/content/output/aem-guides` angeben, wird die endgültige Ausgabe unter dem `/content/output/aem-guides/user-guide`-Knoten generiert.<br><br>Sie können beim Festlegen des Ausgabepfads auch Variablen verwenden. Weitere Informationen finden Sie unter [Verwenden von Variablen zum Festlegen der Optionen Zielpfad, Site-Name oder Dateiname](./generate-output-use-variables.md) |
| Vorhandene Ausgabeseiten | Wählen Sie die Option **Inhalt überschreiben**, um den Inhalt auf den vorhandenen Seiten zu überschreiben. Diese Option überschreibt nur den Inhalt, der unter den Inhalts- und Kopfknoten der Seite vorhanden ist. Diese Option ermöglicht die gemischte Veröffentlichung von Inhalten. Durch Auswahl dieser Option können Sie das Löschen verwaister Seiten aus der veröffentlichten Ausgabe auswählen. Dies ist auch die Option *Standard* zum Erstellen der AEM Sites-Ausgabe.<br><br>Wählen Sie die Option **Löschen und Erstellen**, um das Löschen vorhandener Seiten während der Veröffentlichung zu erzwingen. Diese Option löscht den Seitenknoten sowie den Inhalt und alle untergeordneten Seiten. Verwenden Sie diese Option, wenn Sie die Design-Vorlage Ihrer Ausgabevorgabe geändert haben oder wenn Sie möchten, dass zusätzliche Seiten, die bereits im Ziel vorhanden sind, entfernt werden. |
| Löschen von zuvor generierten Seiten für Themen, die aus der Zuordnung entfernt wurden | Wenn sich die Struktur der Datenzuordnung ändert, können Sie diese Option verwenden, um die zuvor generierten Seiten für die entfernten Themen zu entfernen. Diese Funktion ist nur für die vollständige Veröffentlichung von Karten verfügbar.<br><br>Angenommen, Sie haben eine DITA-Karte veröffentlicht, die die Themen a.dita, b.dita und c.dita enthält. Bevor Sie die Karte erneut veröffentlichen, haben Sie das Thema b.dita aus der Karte entfernt. Wenn Sie diese Option jetzt ausgewählt haben, wird der gesamte Inhalt, der mit b.dita zusammenhängt, aus der AEM Sites-Ausgabe entfernt und nur a.dita und c.dita werden veröffentlicht.<br><br>**Hinweis**: Informationen zu gelöschten Seiten werden ebenfalls in den Ausgabegenerierungsprotokollen erfasst. Weitere Informationen zum Zugriff auf die Protokolldateien finden Sie [Anzeigen und Überprüfen der Protokolldatei](generate-output-basic-troubleshooting.md#id1821I0Y0G0A__id1822G0P0CHS). <br><br>**Achtung**: Beim Löschen der Themen sind die Seiten dann nicht mehr auf der veröffentlichten Site verfügbar. Bevor die Themen gelöscht werden, wird eine Warnung angezeigt. Sie müssen das Löschen bestätigen. |
| Design | Wählen Sie die Design-Vorlage aus, die Sie zum Generieren der Ausgabe verwenden möchten.<br><br>Weitere Informationen zur Verwendung benutzerdefinierter Design-Vorlagen zum Generieren von Ausgaben erhalten Sie von Ihrem Veröffentlichungsadministrator. |
| Nachgenerierungs-Workflow | Wenn Sie diese Option wählen, wird eine neue Dropdown-Liste für den Post-Generation-Workflow angezeigt, die alle in AEM konfigurierten Workflows enthält. Sie müssen einen Workflow auswählen, den Sie nach Abschluss des Workflows zur Ausgabegenerierung ausführen möchten. |
| Temporäre Dateien aufbewahren | Wählen Sie diese Option, um die von DITA-OT generierten temporären Dateien beizubehalten. Wenn beim Generieren der Ausgabe über DITA-OT Fehler auftreten, wählen Sie diese Option aus, um die temporären Dateien beizubehalten. Anschließend können Sie diese Dateien verwenden, um Fehler bei der Ausgabegenerierung zu beheben.<br> <br> Klicken Sie nach dem Generieren der Ausgabe auf das Symbol **Temporäre Dateien herunterladen** ![Symbol für temporäre Dateien herunterladen](images/download-temp-files-icon.svg), um den ZIP-Ordner mit den temporären Dateien herunterzuladen. <br><br> **Hinweis**: Wenn Dateieigenschaften während der Generierung hinzugefügt werden, enthalten die temporären Ausgabedateien auch eine *metadata.xml*-Datei, die diese Eigenschaften enthält. |

**Inhalt**

![Neue ](images/aem-sites-content-tab.png){width="650" align="left"}

Die **Inhalt**-Registerkarte enthält die folgenden Konfigurationsoptionen:

| AEM Sites-Optionen | Beschreibung |
| --- | --- |
| Baseline verwenden | Wenn Sie eine Baseline für die ausgewählte DITA-Map erstellt haben, wählen Sie diese Option, um die Version anzugeben, die Sie veröffentlichen möchten.<br><br>Weitere Informationen finden Sie [ „Arbeiten mit ](./web-editor-baseline.md)&quot;. |
| Bedingte Filterung | Eine der folgenden Optionen auswählen:<br><br>**None**: Wählen Sie diese Option aus, wenn Sie keine Bedingung auf die veröffentlichte Ausgabe anwenden möchten.<br>**Verwenden von DITAVAL**: Wählen Sie DITAVal-Datei(en) aus, um bedingte Inhalte zu generieren. Sie können mehrere DITAVal-Dateien über das Dialogfeld „Durchsuchen“ oder durch Eingabe des Dateipfads auswählen. Verwenden Sie das Kreuz-Symbol neben dem Dateinamen, um ihn zu entfernen. DITAVal-Dateien werden in der angegebenen Reihenfolge ausgewertet, sodass die in der ersten Datei angegebenen Bedingungen Vorrang vor den in späteren Dateien angegebenen übereinstimmenden Bedingungen haben. Sie können die Dateireihenfolge durch Hinzufügen oder Löschen von Dateien beibehalten. Wenn die DITAVal-Datei an einen anderen Speicherort verschoben oder gelöscht wird, wird sie nicht automatisch aus dem Zuordnungs-Dashboard gelöscht. Sie müssen den Speicherort aktualisieren, falls Dateien verschoben oder gelöscht werden. Sie können den Mauszeiger über den Dateinamen bewegen, um den Pfad im AEM-Repository anzuzeigen, in dem die Datei gespeichert ist. Sie können nur DITAVal-Dateien auswählen. Wenn Sie einen anderen Dateityp auswählen, wird ein Fehler angezeigt.<br>**Bedingungsvorgabe**: Wählen Sie in der Dropdown-Liste eine Bedingungsvorgabe aus, um eine Bedingung beim Veröffentlichen der Ausgabe anzuwenden. Diese Option ist sichtbar, wenn Sie eine Bedingung für die DITA-Zuordnungsdatei hinzugefügt haben. Die bedingten Einstellungen sind auf der Registerkarte „Bedingungsvorgaben“ der DITA-Zuordnungskonsole verfügbar. Weitere Informationen zu Bedingungsvorgaben finden Sie unter [Verwenden von Bedingungsvorgaben](generate-output-use-condition-presets.md#id1825FL004PN). |
| Metadaten <br> <br>Dateieigenschaften (Assets) | Wählen Sie die Eigenschaften aus, die Sie als Metadaten verarbeiten möchten. Diese Eigenschaften werden auf der Seite Eigenschaften der DITA-Map- oder Bookmap-Datei festgelegt. Die aus der Dropdown-Liste ausgewählten Eigenschaften werden unter dem Feld **Dateieigenschaften** angezeigt. Klicken Sie auf das Kreuzsymbol neben der Eigenschaft, um sie zu entfernen. <br><br>**Hinweis**: Bei den Metadateneigenschaften wird zwischen Groß- und Kleinschreibung unterschieden.<br><br>*Wenn Sie eine Baseline ausgewählt haben, basieren die Werte für die Eigenschaften auf der Version der ausgewählten Baseline.<br>* Wenn Sie keine Baseline ausgewählt haben, basieren die Werte für die Eigenschaften auf der neuesten Version.<br><br>Sie können die Metadaten auch mithilfe von DITA-OT-Publishing an die Ausgabe übergeben. Für eine weitere Detailansicht ([ Sie die Metadaten mithilfe von DITA-OT an die Ausgabe ](pass-metadata-dita-ot.md#id21BJ00QD0XA).<br><br>**Hinweis**: Wenn Sie die `cq:tags` nicht in der Option Eigenschaften definiert haben, werden die Werte für `cq:tags` aus der aktuellen Arbeitskopie ausgewählt, selbst wenn Sie eine Baseline für die Veröffentlichung ausgewählt haben. |
| Metadaten <br> <br>Verwenden von Zuordnungseigenschaften als Fallback | Wenn diese Option aktiviert ist, werden die für die Zuordnungsdatei definierten Eigenschaften auch in die Themen kopiert, in denen diese Eigenschaften nicht definiert sind. Beachten Sie bei Verwendung dieser Option die folgenden Punkte <br><br>*Nur Zeichenfolgen-, Datums- oder Lange-Eigenschaften (einzelne und mehrwertige Eigenschaften) können an die Seiten der AEM-Site übergeben werden.<br>* Die Metadatenwerte für eine Eigenschaft vom Typ Zeichenfolge unterstützen keine Sonderzeichen (z. B. `@, #, " "`).<br>* Diese Option sollte zusammen mit der Option `Properties` verwendet werden. |

**Querverweise auf Zuordnungen**

Diese Liste enthält Themen mit Querverweisen auf `scope ="peer"`. Sie können den Veröffentlichungskontext für eine Liste von Querverweiskarten mit `scope="peer"` zu Themen angeben, die in anderen DITA-Zuordnungen verfügbar sind. Diese Registerkarte wird angezeigt, wenn Sie die Experience Manager Guides-Version (UUID) verwenden.

Weitere Informationen finden Sie im Abschnitt [Arbeiten mit verknüpften Themen](#working-with-linked-topics) unten.

## Arbeiten mit verknüpften Themen

Mit Experience Manager Guides können Sie Themenreferenzen mithilfe der `peer @scope` erstellen. Anschließend können Sie den Veröffentlichungskontext dieser Verweise über die AEM Sites-Vorgaben definieren und schließlich die Ausgabe der verknüpften Themen generieren.

Weitere Informationen finden Sie unter [Generieren einer Ausgabe von verknüpfenden Themen aus anderen Karten](../user-guide/generate-output-aem-site.md#generate-output-linking-topics-from-other-maps).


Führen Sie die folgenden Schritte aus, um den Veröffentlichungskontext für vernetzte Dateien anzugeben:

1. Öffnen Sie **Registerkarte** Querverweise“. Um diese Registerkarte anzuzeigen, stellen Sie sicher, dass die `<xrefs>` eindeutige IDs haben. Beim Bearbeiten/Speichern des älteren Inhalts werden automatisch eindeutige IDs für `<xrefs>` generiert, wenn die ID nicht vorhanden ist.

   In den folgenden Fällen können Sie die Kreuzkartenverknüpfung nicht anzeigen:
   - Für die Voreinstellungen, die vor Version 4.6 erstellt wurden, ist die Registerkarte Querverweise deaktiviert und es wird eine QuickInfo **siehe Karten-Dashboard** angezeigt.
   - Für Vorgaben, die über das Zuordnungs-Dashboard erstellt wurden, wird **siehe Zuordnungs-Dashboard** QuickInfo angezeigt.
   - Für vordefinierte Vorgaben wird **siehe Zuordnungs-Dashboard** QuickInfo angezeigt.
   - Erstellen Sie für globale Vorgaben eine lokale Kopie dieser globalen Vorgabe, um Querverweise auf Zuordnungen festzulegen.


1. Eine Liste der Themen und der zugehörigen Referenzen wird angezeigt

   >[!NOTE]
   >
   >Die Registerkarte **Querverweise** zeigt Themen an, die nur über die `scope="peer"` verknüpft sind. Für Links mit `scope="local"` müssen Sie den Veröffentlichungskontext nicht angeben.

   Für alle verknüpften Themen ist die neueste Ausgabevorgabe und Zuordnung standardmäßig ausgewählt. Der Veröffentlichungskontext für alle verknüpften Themen ist standardmäßig auf `<Most recently generated>` Zuordnung festgelegt.

   ![Querverweise auf Zuordnungen](images/aem-sites-preset-cross-map-references.png)

1. Wenn Sie die zuletzt veröffentlichte Ausgabe jeder abhängigen Datei in der Zuordnung verwenden möchten, wählen Sie **Zuletzt generierte verwenden** Veröffentlichungskontext für alle abhängigen Themen verwenden.
Sie sollten die als übergeordnete Zuordnung ausgewählte Zuordnung veröffentlichen, bevor Sie die Zuordnung mit verknüpften Themen veröffentlichen. Wenn die Zuordnung mit verknüpften Themen nicht veröffentlicht wird, werden die Links in der AEM Sites-Ausgabe als normaler Text anstelle von Hyperlinks angezeigt.
Sie sollten denselben Typ von AEM Sites-Vorgabe für das verknüpfte Thema auswählen. Wenn die aktuelle AEM Sites-Vorgabe beispielsweise die Zuordnung veralteter Komponenten verwendet, wählen Sie eine ähnliche AEM Sites-Vorgabe des verknüpften Themas aus.
1. Wählen Sie in der Dropdown-Liste Übergeordnete Zuordnung die Zuordnungsdatei aus, mit deren Ausgabe Sie die Ausgabe der aktuellen Zuordnung verknüpfen möchten.
Wenn Sie eine Zuordnungsdatei auswählen, wird die UUID der Zuordnung in der Spalte Übergeordnete UUID der Zuordnung angezeigt. Die mit der ausgewählten Zuordnung verknüpften Ausgabevorgaben werden in der Liste der Voreinstellungen der übergeordneten Zuordnung aufgeführt. Beispielsweise enthält Thema 1 in Karte A einen Verweis auf Thema 2. Thema 2 kann in einzelnen oder mehreren Karten vorhanden sein. Sie können für jeden Link die übergeordnete Zuordnung und eine bestimmte Vorgabe oder die zuletzt veröffentlichte Ausgabe auswählen.

1. Wenn dasselbe Thema mehrmals in einer Datei referenziert wird, können Sie für jede Instanz einen anderen Veröffentlichungskontext hinzufügen. Dies bietet mehr Flexibilität und Kontrolle über ihre Inhalte. Beispielsweise ist Thema 3 sowohl in Karte B als auch in Karte C vorhanden. Thema 1 enthält zwei Verweise auf Thema 3. Sie können Zuordnung B als übergeordnete Zuordnung für den ersten Link und Zuordnung C als übergeordnete Zuordnung für den zweiten Link auswählen.

1. Wählen Sie in der Dropdown-Liste Vorgabe der übergeordneten Zuordnung die Ausgabevorgabe aus, mit der Sie die Ausgabe der aktuellen Zuordnung verknüpfen möchten.
   >[!NOTE]
   >
   > Die verschiedenen AEM Sites-Vorgaben der aktuellen Zuordnung werden in der Dropdown-Liste angezeigt. Wenn Sie keine Vorgabe auswählen, wird ein Warnsymbol angezeigt, und die Ausgabegenerierung schlägt fehl.

1. Wählen Sie die erforderliche Zuordnung und die Ausgabevorgabe für alle Quellthemen aus und klicken Sie auf **Generieren**.




**Übergeordnetes Thema:** [Verstehen der Ausgabevorgaben](generate-output-understand-presets.md)