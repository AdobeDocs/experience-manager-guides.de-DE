---
title: AEM Site
description: Erstellen und konfigurieren Sie die AEM-Sites-Voreinstellung in AEM Guides über das Zuordnungs-Dashboard. Verwenden Sie die AEM Sites-Unterstützung, um eine artikelbasierte Ausgabe zu generieren, verknüpfte Themen zu veröffentlichen , zu conref hinzuzufügen und eine Zeichenfolge innerhalb des Inhalts zu suchen.
feature: Publishing
role: User
hide: true
exl-id: 41c0d4d5-5c46-4d2b-90b3-8c441fee8e99
source-git-commit: 26fa1e52920c1f1abd5655b9ca7341600a9bca67
workflow-type: tm+mt
source-wordcount: '2404'
ht-degree: 0%

---

# AEM Sites-Vorgaben im Zuordnungs-Dashboard {#id205BE3008SW}

Sie können AEM Sites-Vorgaben über das Zuordnungs-Dashboard erstellen und sie so konfigurieren, dass sie die AEM Sites-Ausgabe generieren.


Für die AEM Sites-Ausgabe stehen die folgenden Optionen zur Verfügung:

| AEM Sites-Optionen | Beschreibung |
| --- | --- |
| Ausgabetyp | Der Typ der Ausgabe, die Sie generieren möchten. Um eine responsive AEM Sites-Ausgabe zu generieren, wählen Sie die Option AEM Sites aus. |
| Einstellungsname | Geben Sie einen beschreibenden Namen für die AEM Sites-Einstellungen, die Sie erstellen. Sie können beispielsweise &quot;*Kundenausgabe“* „Endbenutzerausgabe *angeben*. |
| Site-Name | Ein Site-Name, unter dem die Ausgabe in Ihrem AEM-Repository gespeichert wird.<br><br>Ein Knoten im AEM-Repository wird mit dem hier angegebenen Namen erstellt. Wenn Sie den Site-Namen nicht angeben, wird der Site-Knoten mit dem DITA-Map-Dateinamen erstellt.<br><br>Der hier angegebene Site-Name wird auch als Titel auf der Browser-Registerkarte verwendet.<br><br>Sie können beim Festlegen des Site-Namens auch Variablen verwenden. Weitere Informationen zur Verwendung von Variablen finden Sie [Verwenden von Variablen zum Festlegen der Optionen Zielpfad, Site-Name oder Dateiname](generate-output-use-variables.md#id18BUG70K05Z). |
| Design | Wählen Sie die Design-Vorlage aus, die Sie zum Generieren der Ausgabe verwenden möchten.<br><br>Weitere Informationen zur Verwendung benutzerdefinierter Design-Vorlagen zum Generieren von Ausgaben erhalten Sie von Ihrem Veröffentlichungsadministrator. |
| Zielpfad | Der Pfad innerhalb Ihres AEM-Repositorys, in dem die Ausgabe gespeichert wird. Bei der Erstellung der endgültigen Ausgabe werden der Site-Name und der Zielpfad kombiniert. Wenn Sie beispielsweise den Site-Namen als `user-guide` und den Zielpfad als `/content/output/aem-guides` angeben, wird die endgültige Ausgabe unter dem `/content/output/aem-guides/user-guide` Knoten generiert.<br><br>Sie können beim Festlegen des Zielpfads auch Variablen verwenden. Weitere Informationen zur Verwendung von Variablen finden Sie [Verwenden von Variablen zum Festlegen der Optionen Zielpfad, Site-Name oder Dateiname](generate-output-use-variables.md#id18BUG70K05Z). |
| Bedingungen anwenden mit | Eine der folgenden Optionen auswählen:<br><br>**Keine angewendet**: Wählen Sie diese Option aus, wenn Sie keine Bedingung auf die veröffentlichte Ausgabe anwenden möchten.<br>**DITAVal-Datei**: Wählen Sie DITAVal-Datei(en), um bedingte Inhalte zu generieren. Sie können mehrere DITAVal-Dateien über das Dialogfeld „Durchsuchen“ oder durch Eingabe des Dateipfads auswählen. Verwenden Sie das Kreuz-Symbol neben dem Dateinamen, um ihn zu entfernen. DITAVal-Dateien werden in der angegebenen Reihenfolge ausgewertet, sodass die in der ersten Datei angegebenen Bedingungen Vorrang vor den in späteren Dateien angegebenen übereinstimmenden Bedingungen haben. Sie können die Dateireihenfolge durch Hinzufügen oder Löschen von Dateien beibehalten. Wenn die DITAVal-Datei an einen anderen Speicherort verschoben oder gelöscht wird, wird sie nicht automatisch aus dem Zuordnungs-Dashboard gelöscht. Sie müssen den Speicherort aktualisieren, falls Dateien verschoben oder gelöscht werden. Sie können den Mauszeiger über den Dateinamen bewegen, um den Pfad im AEM-Repository anzuzeigen, in dem die Datei gespeichert ist. Sie können nur DITAVal-Dateien auswählen. Wenn Sie einen anderen Dateityp auswählen, wird ein Fehler angezeigt.<br>**Bedingungsvorgabe**: Wählen Sie in der Dropdown-Liste eine Bedingungsvorgabe aus, um eine Bedingung beim Veröffentlichen der Ausgabe anzuwenden. Diese Option ist sichtbar, wenn Sie eine Bedingung für die DITA-Zuordnungsdatei hinzugefügt haben. Die bedingten Einstellungen sind auf der Registerkarte „Bedingungsvorgaben“ der DITA-Zuordnungskonsole verfügbar. Weitere Informationen zu Bedingungsvorgaben finden Sie unter [Verwenden von Bedingungsvorgaben](generate-output-use-condition-presets.md#id1825FL004PN). |
| Vorhandene Ausgabeseiten | Wählen Sie die Option **Inhalt überschreiben**, um den Inhalt auf den vorhandenen Seiten zu überschreiben. Diese Option überschreibt nur den Inhalt, der unter den Inhalts- und Kopfknoten der Seite vorhanden ist. Diese Option ermöglicht die gemischte Veröffentlichung von Inhalten. Durch Auswahl dieser Option können Sie das Löschen verwaister Seiten aus der veröffentlichten Ausgabe auswählen. Dies ist auch die Option *Standard* zum Erstellen der AEM Sites-Ausgabe.<br><br>Wählen Sie die Option **Löschen und Erstellen**, um das Löschen vorhandener Seiten während der Veröffentlichung zu erzwingen. Diese Option löscht den Seitenknoten sowie den Inhalt und alle untergeordneten Seiten. Verwenden Sie diese Option, wenn Sie die Design-Vorlage Ihrer Ausgabevorgabe geändert haben oder wenn Sie möchten, dass zusätzliche Seiten, die bereits im Ziel vorhanden sind, entfernt werden. |
| Verwaiste Seiten löschen | Wenn Sie in der Einstellung **Vorhandene Ausgabeseiten** die Option **Inhalt überschreiben** auswählen, wird diese Option angezeigt. Wenn Sie diese Option auswählen, werden alle verwaisten Seiten aus der veröffentlichten AEM-Site gelöscht. Damit diese Funktion erfolgreich ausgeführt werden kann, müssen Sie die gesamte DITA-Zuordnung veröffentlichen und nicht die inkrementelle Veröffentlichung verwenden.<br><br>Angenommen, Sie haben eine DITA-Karte veröffentlicht, die die Themen a.dita, b.dita und c.dita enthält. Bevor Sie die Karte erneut veröffentlichen, haben Sie das Thema b.dita aus der Karte entfernt. Wenn Sie diese Option jetzt ausgewählt haben, wird der gesamte Inhalt, der mit b.dita zusammenhängt, aus der AEM Sites-Ausgabe entfernt und nur a.dita und c.dita werden veröffentlicht.<br><br>Diese Funktion entfernt keine veröffentlichten untergeordneten Zuordnungen. Wenn Ihre übergeordnete Zuordnung beispielsweise eine untergeordnete Zuordnung enthält und Sie die gesamte untergeordnete Zuordnung entfernen, wird der Inhalt der untergeordneten Zuordnung nicht aus der veröffentlichten Ausgabe gelöscht. Wenn Sie jedoch ein Thema aus einer untergeordneten Zuordnung entfernen und erneut veröffentlichen, wird der Inhalt des entfernten Themas aus der Site-Ausgabe gelöscht.<br><br>Wenn referenzierte Inhalte vorhanden sind und diese Inhalte vor der erneuten Veröffentlichung entfernt werden, werden die Daten der referenzierten Inhalte nicht entfernt.<br><br>**Hinweis**: Informationen zu gelöschten verwaisten Seiten werden ebenfalls in den Ausgabegenerierungsprotokollen erfasst. Weitere Informationen zum Zugriff auf die Protokolldateien finden Sie unter [Protokolldatei anzeigen und überprüfen](generate-output-basic-troubleshooting.md#id1821I0Y0G0A__id1822G0P0CHS). |
| Temporäre Dateien aufbewahren | Wählen Sie diese Option, um die von DITA-OT generierten temporären Dateien beizubehalten. Wenn beim Generieren der Ausgabe über DITA-OT Fehler auftreten, wählen Sie diese Option aus, um die temporären Dateien beizubehalten. Anschließend können Sie diese Dateien verwenden, um Fehler bei der Ausgabegenerierung zu beheben.<br> <br> Klicken Sie nach dem Generieren der Ausgabe auf das Symbol **Temporäre Dateien herunterladen** ![Symbol für temporäre Dateien herunterladen](images/download-temp-files-icon.png), um den ZIP-Ordner mit den temporären Dateien herunterzuladen. <br><br> **Hinweis**: Wenn Dateieigenschaften während der Generierung hinzugefügt werden, enthalten die temporären Ausgabedateien auch eine *metadata.xml*-Datei, die diese Eigenschaften enthält. |
| Für jedes Thema separate PDF generieren | Wenn diese Option aktiviert ist, wird für jedes Thema in der DITA-Karte auch eine PDF erstellt. Wenn Sie diese Option wählen, wird die neue Option PDF-Pfad aufteilen angezeigt.<br><br>Geben Sie im Feld PDF-Pfad aufteilen den Pfad zum Speichern der für jedes Thema generierten PDF-Dateien an.<br><br>**Hinweis**: AEM Guides verwendet das DITA-OT-Plug-in „pdfx“, um für jedes Thema PDF zu generieren. Dieses Plug-in ist im Lieferumfang des DITA-OT-Pakets enthalten. Sie können dieses Plug-in anpassen, um PDF gemäß Ihren Anforderungen zu generieren. Wenn Sie ein benutzerdefiniertes DITA-OT-Plug-in verwenden, stellen Sie sicher, dass Sie das pdfx-Plug-in integrieren, um PDF-Generierungsfunktionen auf Themenebene zu erhalten. |
| Nachgenerierungs-Workflow ausführen | Wenn Sie diese Option wählen, wird eine neue Dropdown-Liste für den Post-Generation-Workflow angezeigt, die alle in AEM konfigurierten Workflows enthält. Sie müssen einen Workflow auswählen, den Sie nach Abschluss des Workflows zur Ausgabegenerierung ausführen möchten. |
| Baseline verwenden | Wenn Sie eine Baseline für die ausgewählte DITA-Map erstellt haben, wählen Sie diese Option, um die Version anzugeben, die Sie veröffentlichen möchten.<br><br>**Wichtig**: Wenn Sie eine inkrementelle Ausgabe für die AEM-Site generieren, wird die Ausgabe anhand der aktuellen Dateiversion und nicht anhand der angehängten Baseline erstellt.<br><br>Weitere Informationen finden [ unter „Arbeiten mit ](generate-output-use-baseline-for-publishing.md#id1825FI0J0PF)&quot;. |
| Eigenschaften | Wählen Sie die Eigenschaften aus, die Sie als Metadaten verarbeiten möchten. Diese Eigenschaften werden auf der Seite Eigenschaften der DITA-Map- oder Bookmap-Datei festgelegt. Die aus der Dropdown-Liste ausgewählten Eigenschaften werden unter dem Feld **Dateieigenschaften** angezeigt. Klicken Sie auf das Kreuzsymbol neben der Eigenschaft, um sie zu entfernen. <br><br>**Hinweis**: Bei den Metadateneigenschaften wird zwischen Groß- und Kleinschreibung unterschieden.<br><br>*Wenn Sie eine Baseline ausgewählt haben, basieren die Werte für die Eigenschaften auf der Version der ausgewählten Baseline.<br>* Wenn Sie keine Baseline ausgewählt haben, basieren die Werte für die Eigenschaften auf der neuesten Version.<br><br>Sie können die Metadaten auch mithilfe von DITA-OT-Publishing an die Ausgabe übergeben. Weitere Informationen finden Sie unter [Übergeben der Metadaten an die Ausgabe mithilfe von DITA-OT](pass-metadata-dita-ot.md#id21BJ00QD0XA).<br><br>**Hinweis**: Wenn Sie die `cq:tags` nicht in der Option Eigenschaften definiert haben, werden die Werte für `cq:tags` aus der aktuellen Arbeitskopie ausgewählt, selbst wenn Sie eine Baseline für die Veröffentlichung ausgewählt haben. |
| Zuordnungseigenschaften als Standard verwenden | Wenn diese Option aktiviert ist, werden die für die Zuordnungsdatei definierten Eigenschaften auch in die Themen kopiert, in denen diese Eigenschaften nicht definiert sind. Beachten Sie bei Verwendung dieser Option die folgenden Punkte <br><br>*Nur Zeichenfolgen-, Datums- oder Lange-Eigenschaften (einzelne und mehrwertige Eigenschaften) können an die AEM Sites-Seiten übergeben werden.<br>* Die Metadatenwerte für eine Eigenschaft vom Typ Zeichenfolge unterstützen keine Sonderzeichen (z. B. `@, #, " "`).<br>* Diese Option sollte zusammen mit der Option `Properties` verwendet werden. |

## Zusätzlicher Hinweis zu AEM Sites

### Artikelbasierte Ausgabe aus dem Web-Editor generieren

Sie können die AEM Sites-Ausgabe für ein oder mehrere Themen oder die gesamte DITA-Zuordnung aus dem Web-Editor generieren. Sie müssen Ausgabevorgaben für Ihre DITA-Zuordnung erstellen und dann können Sie einfach die AEM Sites-Ausgabe für Ihre Zuordnung generieren. Wenn Sie einige Themen in Ihrer Zuordnung aktualisiert haben, können Sie die AEM Sites-Ausgabe auch nur für diese Themen aus dem Web-Editor generieren. Weitere Informationen finden Sie unter [Artikelbasierte Veröffentlichung im Web-Editor](web-editor-article-publishing.md#id218CK0U019I).

### Ausgabe von Verknüpfungsthemen aus anderen Karten generieren

Häufig wird eine umfangreiche Dokumentation in mehreren Ordnern und DITA-Zuordnungen bereitgestellt. Das Veröffentlichen von Inhalten, die von verschiedenen Stellen aus verknüpft sind, wird extrem komplex. Standardmäßig werden alle `<xref>` Links mit dem `local` `@scope` erstellt. Die Veröffentlichung solcher Themen stellt keine Herausforderung dar, da sie einen direkten Link zum Thema verwendet. Falls sich das Thema außerhalb der aktuellen DITA-Zuordnung befindet, wird der verknüpfte Inhalt nicht angezeigt.

Eine andere Möglichkeit, Inhalte zu verknüpfen, besteht darin, einen Link mithilfe der `peer`-`@scope` zu erstellen. Für solche Inhalte wird der Link zur Laufzeit aufgelöst, indem der Titel der Datei und der konfigurierte Kontext für das verknüpfte Thema aus dem Veröffentlichungskontext der DITA-Zuordnung ausgewählt werden. Der folgende Screenshot zeigt das Bedienfeld Eigenschaften für einen Link mit dem `peer` `@scope`:

![](images/peer-link-scope-link.png){width="800" align="left"}

Um die Veröffentlichung komplexer Zuordnungen und Themen zu vereinfachen, die mit anderen Themen in anderen Zuordnungen verknüpft sind, können Sie in AEM Guides den Veröffentlichungskontext für jede Ausgabevorgabe festlegen.

Im Veröffentlichungskontext können Sie angeben, welches Thema aus welcher Zuordnung für die Veröffentlichung einer bestimmten Ausgabe verwendet werden soll. Lassen Sie uns dies anhand eines Beispiels verstehen - nehmen wir an, Sie haben vier Ordner: Beispiel A, Beispiel B, Beispiel C und Beispiel D. Jeder Ordner enthält eine DITA-Karte - DITA-Karte A, DITA-Karte B, DITA-Karte C und DITA-Karte D. Eine Kreuzkartenverknüpfung erfolgt, wenn ein Thema in DITA-Karte A mit einem Thema in DITA-Karte B, C oder D verknüpft ist. Im folgenden Screenshot enthält ein Beispielkonzeptthema Links \(oder Verweise\) zu Dateien, die Teil anderer DITA-Zuordnungen sind.

![](images/sample-concept-link-to-other.png){width="350" align="left"}

Wenn Sie jetzt die AEM Sites-Veröffentlichungseinstellungen für die Zuordnungsdatei konfigurieren, die dieses Thema enthält, können Sie auswählen, welcher Veröffentlichungskontext für den verknüpften Inhalt beim Veröffentlichen verwendet wird. Ein Veröffentlichungskontext ist eine Kombination aus DITA-Zuordnung und Ausgabevorgabe. Die Ausgabevorgabe wiederum enthält eine bestimmte Version des Inhalts und bedingte Vorgaben. Diese gesamte Kombination aus DITA-Zuordnung, Ausgabevorgabe, \(Dateien\)-Version und Bedingungen definiert den Veröffentlichungskontext für eine verknüpfte Zuordnung.

Führen Sie die folgenden Schritte aus, um den Veröffentlichungskontext für vernetzte Dateien anzugeben:

1. Öffnen Sie die **Ausgabevorgaben** der DITA-Zuordnung, die Sie veröffentlichen möchten.

1. Wählen Sie die Ausgabevorgabe **AEM-Site** aus.

   Sie erhalten die Registerkarten AEM-Voreinstellungen und Veröffentlichungskontext .

   ![](images/aem-site-publish-settings.png){width="800" align="left"}

1. Öffnen Sie die Registerkarte **Veröffentlichungskontext**.

   Es wird eine Liste der abhängigen Themen angezeigt. Dies sind die Themen, die von einem Thema in der aktuellen Karte verlinkt sind, aber in einigen anderen DITA-Karten verfügbar sind.

   >[!NOTE]
   >
   > Auf der Registerkarte Veröffentlichungskontext werden Themen angezeigt, die nur über die `peer` `@scope` verknüpft sind. Für Links mit `local` `@scope` müssen Sie den Veröffentlichungskontext nicht angeben.

   Standardmäßig sind für alle verknüpften Themen die neueste Ausgabevorgabe und Zuordnung ausgewählt.

   ![](images/default-publish-context.png){width="800" align="left"}

1. Um die Standardauswahl von DITA-Zuordnung und -Vorgabe zu ändern, klicken Sie auf **Bearbeiten** \(in der Haupt-Symbolleiste\).

1. Wenn Sie die zuletzt veröffentlichte Ausgabe jeder abhängigen Datei in der Zuordnung verwenden möchten, wählen Sie **Zuletzt generierten Veröffentlichungskontext für alle abhängigen Themen verwenden**.

1. Wählen **in der Dropdown** Liste Übergeordnete Zuordnung die Zuordnungsdatei aus, mit deren Ausgabe Sie die Ausgabe der aktuellen Zuordnung verknüpfen möchten.

   Bei Auswahl einer Zuordnungsdatei wird die UUID der Zuordnung in der Spalte Übergeordnete UUID der Zuordnung angezeigt. Die mit der ausgewählten Zuordnung verknüpften Ausgabevorgaben werden in der Liste der Voreinstellungen der übergeordneten Zuordnung aufgeführt.

1. Wählen Sie in **Dropdown-Liste Vorgabe** übergeordneten Zuordnung die Ausgabevorgabe aus, mit der Sie die Ausgabe der aktuellen Zuordnung verknüpfen möchten.

1. Wählen Sie die gewünschte Zuordnung und ihre Ausgabevorgabe für alle abhängigen Themen aus und klicken Sie auf **Fertig**.

   Der Kontext für die abhängigen Themen ist jetzt festgelegt. Sie können die Ausgabe für die aktuelle Zuordnung generieren. Weitere Informationen zum Generieren einer Ausgabe finden Sie unter [Generieren einer Ausgabe für eine DITA-Zuordnung über die Zuordnungskonsole](generate-output-for-a-dita-map.md#).

### Gemischte Veröffentlichung

AEM Guides unterstützt die Veröffentlichung von DITA-Inhalten auf Ihrer bestehenden AEM-Site. Wenn Sie beispielsweise über eine bereits vorhandene Site verfügen, können Sie die AEM Sites-Ausgabe verwenden, um nur die DITA-Inhalte auf dieser Site zu veröffentlichen. In diesem Prozess wird der vorhandene Nicht-DITA-Inhalt nicht durch den Veröffentlichungsprozess geändert. Weitere Informationen dazu, wie Sie Ihre Site so einrichten, dass nur DITA-Inhalte veröffentlicht werden, erhalten Sie von Ihrem Veröffentlichungsadministrator.

### Veröffentlichung `conref`

Wenn Sie `conref` in Ihrem Inhalt verwenden, wird dieser als normaler oder eingebetteter Inhalt zusammen mit dem Inhalt im \(oder verweisenden\) Quellthema veröffentlicht. Der `conref` Inhalt wird zusammen mit dem Hauptinhalt gerendert, und es wird keine separate Website-Seite für dieselbe erstellt. Wenn Sie nach dem Inhalt suchen, auf den in der `conref` verwiesen wird, wird nur das Hauptthema oder die Hauptseite mit dem `conref` Inhalt in den Suchergebnissen angezeigt.

>[!NOTE]
>
>Wenn Sie mit AEM Guides Version 3.5 oder früher separate Seiten für den `conref` Inhalt generiert haben, wird empfohlen, diese Seiten mithilfe der Option [Löschen verwaister Site-Seiten](#delete-orphan-page-aem-site) zu bereinigen/löschen.


### Eine Zeichenfolge im Inhalt durchsuchen

Sie können in der AEM Sites-Ausgabe nach einer Zeichenfolge suchen. Standardmäßig können Sie nur in den Titeln nach der Zeichenfolge suchen. Um nach der Zeichenfolge im Inhalt oder im Hauptteil der AEM Sites-Ausgabe zu suchen, wenden Sie sich an Ihren Systemadministrator, um die Flattling.enabled-Eigenschaft zu aktivieren.

![AEM Sites-Ausgabe durchsuchen](images/aem-output-search.png){width="650" align="left"}

Weitere Informationen finden Sie *Abschnitt „Reduzieren der Knotenstruktur der AEM-Site konfigurieren* im Handbuch zum Installieren und Konfigurieren von Adobe Experience Manager Guides .

**Übergeordnetes Thema:**[ Verstehen der Ausgabevorgaben](generate-output-understand-presets.md)
