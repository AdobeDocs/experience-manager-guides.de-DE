---
title: AEM Sites
description: Erstellen und konfigurieren Sie die AEM Sites-Vorgabe im Web Editor und generieren Sie die AEM Sites-Ausgabe für DITA-Maps, ausgewählte Themen und verknüpfte Themen.
feature: Publishing
role: User
source-git-commit: fa07db6a9cb8d8f5b133258acd5647631b22e28a
workflow-type: tm+mt
source-wordcount: '2732'
ht-degree: 0%

---

# AEM Sites-Vorgaben im Web-Editor


Sie können AEM Sites-Vorgaben im Web Editor erstellen und so konfigurieren, dass die AEM Sites-Ausgabe generiert wird. Die AEM Sites-Ausgabe basiert auf dem Mapping der zusammengesetzten Komponenten zusammen mit dem Tag &quot;`guides-components`&quot;, was die effiziente Erstellung und Verwaltung von Inhalten erleichtert.

Experience Manager Guides stellt vordefinierte Vorlagen zum Erstellen von AEM Sites bereit. Mithilfe dieser Vorgaben können Sie ein konsistentes Inhaltslayout und eine konsistente Inhaltsstruktur gewährleisten.
- [Erstellen Sie Startseiten](../cs-install-guide/download-install-aem-sites-templates-cs.md#create-a-home-page-using-the-template) anhand dieser vordefinierten Vorlagen.
- Sie können [Themenvorlagen bearbeiten](../cs-install-guide/download-install-aem-sites-templates-cs.md#package-installation) und Stile entsprechend Ihren Anforderungen anwenden.
- Sie können auch [vorhandene AEM Sites-Vorlagen anpassen](../cs-install-guide/download-install-aem-sites-templates-cs.md#customize-existing-aem-sites-templates).



## Erstellen von AEM Sites-Vorgaben

Führen Sie die folgenden Schritte aus, um die AEM Sites-Vorgaben im Web Editor zu erstellen:

1. Öffnen Sie im Bereich &quot;Repository&quot;die DITA-Map-Datei in der Kartenansicht.
1. Wählen Sie auf der Registerkarte **Ausgabe** das Symbol + aus, um eine Ausgabevorgabe zu erstellen.
1. Wählen Sie **AEM Sites** aus der Dropdown-Liste **Typ** im Dialogfeld **Neue Ausgabevorgabe** aus.
1. Deaktivieren Sie im Dialogfeld **Neue Ausgabevorgabe** die Option **Legacy-Komponentenzuordnung verwenden** .

![Neu ](images/new-aem-sites-dialog-box.png)





>[!NOTE]
>
>Bevor Sie die AEM Sites-Vorgaben für Experience Manager Guides konfigurieren, muss Ihr Administrator eine AEM Sites-Struktur mit den Vorlagen erstellen.
- **On-Premise-Software**: Erfahren Sie mehr über das [Herunterladen und Installieren von AEM Sites-Vorlagen](../install-guide/download-install-aem-sites-templates.md) für On-Premise-Software.
- **Cloud Service**: Erfahren Sie mehr über das [Herunterladen und Installieren von AEM Sites-Vorlagen](../cs-install-guide/download-install-aem-sites-templates-cs.md) für den Cloud Service.




### Hinzufügen von Vorgaben zum aktuellen Ordnerprofil

Als Administrator können Sie mit Experience Manager Guides Ausgabevorgaben für die globalen und Ordnerprofile erstellen und verwalten. Wählen Sie im Dialogfeld **Neue Ausgabevorgabe** die Option **Zum aktuellen Ordnerprofil hinzufügen** aus, um eine Ausgabevorgabe für das aktuelle Ordnerprofil zu erstellen. Das Symbol &quot;![Ordnerprofilsymbol](images/global-preset-icon.svg)&quot;zeigt eine Vorgabe auf Ordnerprofilebene an.  Erfahren Sie mehr über [Ausgabevorgaben für Global- und Ordnerprofil verwalten](./web-editor-manage-output-presets.md).

### AEM Sites-Vorgaben basierend auf der alten Komponentenzuordnung

Sie können die AEM Sites-Vorgaben auch mit der alten Komponentenzuordnung erstellen. Um die AEM Sites-Vorgaben basierend auf der alten Komponentenzuordnung zu erstellen, wählen Sie im Dialogfeld **Neue Ausgabevorgabe** die Option **Alte Komponentenzuordnung verwenden** aus.

Einige Optionen unterscheiden sich möglicherweise für die Vorgaben, die die ältere Komponentenzuordnung verwenden.



## Konfigurieren der AEM Sites-Vorgaben

Die Konfigurationen befinden sich auf den Registerkarten **Allgemein**, **Inhalt**, **Themenliste** und **Querverweise**.

![Vorgabeneinstellungen für AEM Sites](images/aem-sites-new-config.png)
**Allgemein**

Die Registerkarte **Allgemein** enthält die folgenden Konfigurationen zur Generierung von Ausgaben:

- Verwenden des Site-Pfads
- Site-Pfad
- Site
- Publish-Pfad
- Themenseitenvorlage
- Generieren von Seitennamen basierend auf
   - Themendateiname
   - Thementitel
- Zuvor generierte Seiten bereinigen
   - Löschen zuvor generierter Seiten für Themen, die aus der Zuordnung entfernt wurden
   - Löschen Sie alle Seiten, die von anderen Quellen unter diesem Pfad erstellt wurden:
- Workflow nach der Erstellung



**Inhalt**

Die Registerkarte **Inhalt** enthält die folgenden Konfigurationen:

- Grundlinie verwenden
- Bedingungsfilterung
- Zusätzliche DITA-OT-Befehlszeilenargumente
- Metadaten
   - Dateieigenschaften (Assets)
   - Verwenden von Zuordnungseigenschaften als Fallback


Weitere Informationen finden Sie unter [AEM Sites-Konfiguration](#aem_sites_config).

**Themenliste**

Die **Themenliste** zeigt die Liste der Themen an, die in der aktuellen Arbeitskopie der DITA-Zuordnung vorhanden sind. Standardmäßig sind alle Themen eingeschlossen. Sie können bestimmte Themen auswählen und die AEM Sites-Ausgabe nur für sie generieren. Beispielsweise haben Sie einige Themen aktualisiert, sodass Sie nur diese Themen veröffentlichen können, anstatt die gesamte DITA-Map zu veröffentlichen.

Die Registerkarte **Themenliste** ist in den AEM Vorgaben vorhanden, die nicht basierend auf der alten Zuordnung erstellt werden.

**Querverweise**
Diese Liste enthält Themen, die Querverweise mit `scope ="peer"` enthalten. Sie können den Veröffentlichungskontext für eine Liste von Querverweisen mit `scope="peer"` zu Themen angeben, die in anderen DITA-Maps verfügbar sind. Diese Registerkarte wird angezeigt, wenn Sie die Experience Manager Guides-Version (UUID) verwenden.



Erfahren Sie mehr über das [Veröffentlichen von verknüpften Themen](#publish-linked-topics).





## AEM Sites-Konfiguration {#aem_sites_config}

Die folgenden Optionen sind für die AEM Sites-Ausgabe verfügbar:

| AEM Sites-Optionen | Beschreibung |
| --- | --- |
| Verwenden des Site-Pfads | Verwenden Sie diese Option, um Ihre Inhalte auf einer Experience Manager-Site zu veröffentlichen. Wählen Sie diese Option aus, wenn Sie den genauen Site-Pfad kennen, in dem die Ausgabe veröffentlicht werden soll. Geben Sie außerdem den vollständigen Pfad im Feld &quot;Sitepfad&quot;an. |
| Site-Pfad | Diese Option wird angezeigt, wenn Sie die Option **Site-Pfad verwenden** auswählen. Durchsuchen Sie den exakten Pfad der Experience Manager-Site, in dem die Ausgabe veröffentlicht werden soll. |
| Site | Name der Experience Manager Sites, in der Sie Inhalte veröffentlichen möchten. Die Optionen in der Dropdown-Liste werden auf der Grundlage der in AEM Sites verfügbaren Sites gefüllt. <br>Wählen Sie das Aktualisierungssymbol **Aktualisieren** ![](images/navtitle-refresh-icon.svg) aus, um eine neue Liste von Optionen abzurufen und die aktualisierten Daten widerzuspiegeln. |
| Publish-Pfad | Der Pfad in Ihrem AEM-Repository, in dem die Ausgabe gespeichert wird. Der Publish-Pfad enthält alle Pfade, die Seiten enthalten, die auf der Grundlage der Homepage-Vorlage erstellt wurden. Die AEM Sites-Ausgabe der DITA-Zuordnung wird unter diesem Pfad generiert.  Wenn Sie beispielsweise die Site als `AEMG-Docs` und den Publish-Pfad als `aemg-docs-en/docs/product-abc.` angeben, wird die AEM Sites-Ausgabe unter dem Knoten `aemg-docs-en/docs/product-abc/` in `crx/de` generiert. |
| Themenseitenvorlage | Die Strukturkomponenten, mit denen Sie Inhalte konsistent über mehrere Dokumente hinweg organisieren können. Diese Vorlagen sind in der Adobe Experience Manager Site-Vorlage vordefiniert. Die Optionen werden mit allen Themenseitenvorlagen gefüllt, die für die ausgewählte Site verfügbar sind. Wählen Sie die Vorlage aus, die Sie auf alle Ausgabedokumente anwenden möchten. |
| Generieren von Seitennamen basierend auf | **Themendateiname**: Verwendet den Dateinamen des DITA-Themas, um die Site-URL zu erstellen. <br> **Thementitel**: Verwendet den DITA-Thementitel, um die Experience Manager-Site-Namen zu erstellen. |
| Zuvor generierte Seiten bereinigen | - **Löschen Sie zuvor generierte Seiten für Themen, die aus der Zuordnung entfernt wurden**: Wenn sich die Struktur der DTIA-Zuordnung ändert, können Sie diese Option verwenden, um die zuvor generierten Seiten für die entfernten Themen zu entfernen. Diese Funktion ist nur für die Vollbildveröffentlichung verfügbar.<br><br>Angenommen, Sie haben eine DITA-Zuordnung veröffentlicht, die die Themen a.dita, b.dita und c.dita enthält. Bevor Sie die Zuordnung erneut veröffentlichen, haben Sie das Thema b.dita aus der Zuordnung entfernt. Wenn Sie jetzt diese Option ausgewählt haben, werden alle Inhalte, die sich auf b.dita beziehen, aus der AEM Sites-Ausgabe entfernt und nur a.dita und c.dita werden veröffentlicht.<br><br>**Hinweis**: Informationen zu gelöschten Seiten werden auch in den Ausgabegenerierungsprotokollen erfasst. Weitere Informationen zum Zugriff auf die Protokolldateien finden Sie unter [Anzeigen und Überprüfen der Protokolldatei](generate-output-basic-troubleshooting.md#id1821I0Y0G0A__id1822G0P0CHS). <br><br>**Vorsicht**: Beim Löschen der Themen stehen die Seiten nicht mehr auf der veröffentlichten Site zur Verfügung. Bevor die Themen gelöscht werden, wird also eine Warnung angezeigt. Sie müssen bestätigen, dass Sie sie löschen möchten.<br><br> - **Löschen aller Seiten, die von anderen Quellen in diesem Pfad erstellt wurden**: Wenn Sie diese Option auswählen, werden alle Seiten, die auf diesem Pfad aus anderen Maps, einzelnen Themen oder einer anderen Quelle veröffentlicht wurden, gelöscht. Die Seiten stehen auch nicht mehr auf der veröffentlichten Site zur Verfügung. Bevor die Themen gelöscht werden, wird also eine Warnung angezeigt. Sie müssen bestätigen, dass Sie sie löschen möchten. |
| Arbeitsablauf nach der Erstellung | Wenn Sie diese Option wählen, wird eine neue Dropdownliste mit dem Workflow nach der Generierung angezeigt, die alle in AEM konfigurierten Workflows enthält. Sie müssen einen Workflow auswählen, der nach Abschluss des Workflows zur Generierung der Ausgabe ausgeführt werden soll. |
| Grundlinie verwenden | Wenn Sie eine Grundlinie für die ausgewählte DITA-Zuordnung erstellt haben, wählen Sie diese Option, um die Version anzugeben, die Sie veröffentlichen möchten.<br><br>**Wichtig**: Wenn Sie eine inkrementelle Ausgabe für die AEM Site generieren, wird die Ausgabe mit der aktuellen Version der Dateien und nicht mit der angehängten Grundlinie erstellt.<br><br>Anzeigen [Arbeiten mit Grundlinie](generate-output-use-baseline-for-publishing.md#id1825FI0J0PF) für weitere Details. |
| Bedingte Filterung | Wählen Sie eine der folgenden Optionen aus:<br><br>**None**: Wählen Sie diese Option aus, wenn Sie keine Bedingung auf die veröffentlichte Ausgabe anwenden möchten.<br>**DITAVAL verwenden**: Wählen Sie DITAVal-Dateien aus, um konditionalisierte Inhalte zu generieren. Sie können mehrere DITAVal-Dateien über das Dialogfeld &quot;Durchsuchen&quot;oder durch Eingabe des Dateipfads auswählen. Verwenden Sie das Kreuzsymbol neben dem Dateinamen, um ihn zu entfernen. DITAVal-Dateien werden in der angegebenen Reihenfolge ausgewertet, sodass die in der ersten Datei angegebenen Bedingungen Vorrang vor den in späteren Dateien angegebenen Bedingungen haben. Sie können die Dateireihenfolge beibehalten, indem Sie Dateien hinzufügen oder löschen. Wenn die DITAVal-Datei an einen anderen Speicherort verschoben oder gelöscht wird, wird sie nicht automatisch aus dem Mapping-Dashboard gelöscht. Sie müssen den Speicherort aktualisieren, falls Dateien verschoben oder gelöscht werden. Sie können den Mauszeiger über den Dateinamen bewegen, um den Pfad im AEM Repository anzuzeigen, in dem die Datei gespeichert ist. Sie können nur DITAVal-Dateien auswählen. Ein Fehler wird angezeigt, wenn Sie einen anderen Dateityp auswählen.<br>**Bedingungsvorgabe**: Wählen Sie aus der Dropdown-Liste eine Bedingungsvorgabe aus, um beim Veröffentlichen der Ausgabe eine Bedingung anzuwenden. Diese Option ist sichtbar, wenn Sie eine Bedingung für die DITA-Map-Datei hinzugefügt haben. Die bedingten Einstellungen sind auf der Registerkarte Bedingungsvorgaben der DITA-Zuordnungskonsole verfügbar. Weitere Informationen zur Bedingungsvorgabe finden Sie unter [Bedingungsvorgaben verwenden](generate-output-use-condition-presets.md#id1825FL004PN). |
| Zusätzliche DITA-OT-Befehlszeilenargumente | Geben Sie die zusätzlichen Argumente an, die DITA-OT beim Generieren der Ausgabe verarbeiten soll. Weitere Informationen zu den in DITA-OT unterstützten Befehlszeilenargumenten finden Sie in der [DITA-OT-Dokumentation](https://www.dita-ot.org/) . |
| Metadaten <br> <br>Dateieigenschaften (Assets) | Wählen Sie die Eigenschaften aus, die Sie als Metadaten verarbeiten möchten. Diese Eigenschaften werden auf der Seite &quot;Eigenschaften&quot;der DITA-Map- oder Bookmap-Datei festgelegt. Die Eigenschaften, die Sie aus der Dropdown-Liste auswählen, werden unter dem Feld **Dateieigenschaften** angezeigt. Wählen Sie das Kreuzsymbol neben der Eigenschaft aus, um sie zu entfernen. <br><br>**Hinweis**: Bei den Metadateneigenschaften wird zwischen Groß- und Kleinschreibung unterschieden.<br><br>*Wenn Sie eine Grundlinie ausgewählt haben, basieren die Werte für die Eigenschaften auf der Version der ausgewählten Grundlinie.<br>* Wenn Sie keine Grundlinie ausgewählt haben, basieren die Werte für die Eigenschaften auf der neuesten Version.<br><br>Sie können die Metadaten auch mithilfe der DITA-OT-Veröffentlichung an die Ausgabe übergeben. Für weitere Details übergeben Sie die Metadaten mithilfe von DITA-OT](pass-metadata-dita-ot.md#id21BJ00QD0XA) an die Ausgabe.[<br><br>**Hinweis**: Wenn Sie die `cq:tags` in der Option &quot;Eigenschaften&quot;nicht definiert haben, werden die Werte für `cq:tags` aus der aktuellen Arbeitskopie ausgewählt, selbst wenn Sie eine Grundlinie für die Veröffentlichung ausgewählt haben. |
| Metadaten <br> <br>Verwenden Sie Zuordnungseigenschaften als Fallback | Wenn diese Option aktiviert ist, werden die für die Zuordnungsdatei definierten Eigenschaften auch in die Themen kopiert, in denen solche Eigenschaften nicht definiert sind. Beachten Sie bei der Verwendung dieser Option die folgenden Punkte: <br><br>*Nur String-, Datum- oder Long-Eigenschaften (einzelne und mehrere Werte) können an die AEM Site-Seiten übergeben werden.<br>* Die Metadatenwerte für eine Eigenschaft vom Typ String unterstützen keine Sonderzeichen (z. B. `@, #, " "`).<br>* Diese Option sollte zusammen mit der `Properties` -Option verwendet werden. |
| Beibehalten temporärer Dateien | Wählen Sie diese Option, um die von DITA-OT generierten temporären Dateien beizubehalten. Wenn beim Generieren der Ausgabe über DITA-OT Fehler auftreten, wählen Sie diese Option, um die temporären Dateien beizubehalten. Sie können diese Dateien dann verwenden, um Fehler bei der Ausgabenerstellung zu beheben.<br> <br> Nachdem Sie die Ausgabe generiert haben, wählen Sie das Symbol **Temporäre Dateien herunterladen** ![Symbol zum Herunterladen temporärer Dateien](images/download-temp-files-icon.png) aus, um den ZIP-Ordner mit den temporären Dateien herunterzuladen. <br><br> **Hinweis**: Wenn Dateieigenschaften während der Generierung hinzugefügt werden, enthalten die temporären Ausgabedateien auch eine *metadata.xml* -Datei, die diese Eigenschaften enthält. |


### Generieren der AEM Sites-Ausgabe mithilfe der Vorlagen

Mit Experience Manager Guides können Sie die vordefinierten Vorlagen verwenden oder eigene AEM Sites-Vorlagen hinzufügen.

Bevor Sie die AEM Sites-Vorgaben konfigurieren, stellen Sie sicher, dass Sie eine AEM Sites-Struktur mithilfe der Vorlagen erstellen.\
Weitere Informationen finden Sie unter [Herunterladen und Installieren von AEM Sites-Vorlagen](../install-guide/download-install-aem-sites-templates.md).



Führen Sie die folgenden Schritte aus, um eine AEM Sites-Vorgabe zu erstellen und zu konfigurieren:
1. Öffnen Sie die Registerkarte **Ausgabevorgaben** der DITA-Map, die Sie veröffentlichen möchten.
1. Wählen Sie die Ausgabevorgabe **AEM Sites** aus.
1. (Optional) Deaktivieren Sie die Option **Legacy component mapping** , um eine nicht ältere AEM Sites-Vorgabe zu erstellen.
1. Klicken Sie auf **Hinzufügen**. Die Vorgabe für AEM Sites wird erstellt.
1. Sie können die Vorlage für native Sites auf zwei Arten konfigurieren:
   1. Wählen Sie **Site** und dann den Veröffentlichungspfad und die Themenseitenvorlagen aus den ausgefüllten Optionen aus:
      1. Wählen Sie die Site aus.
      1. Wählen Sie **Site** aus. Zum Beispiel: `AEMG Docs`.
      1. Die Optionen **Publish-Pfad** und **Themenseitenvorlage** werden automatisch in der Dropdown-Liste festgelegt. Sie können auch die Optionen auswählen. Beispielsweise werden `AEMG-Docs-Site/en/docs/product1` und `Topic page` eingestellt.
   1. Wählen Sie den vollständigen Site-Pfad aus:
      1. Wählen Sie die Option **Site-Pfad verwenden** aus.
      1. Wählen Sie den vollständigen Site-Pfad aus. Zum Beispiel: `/content/AEMG-Docs-Site/en/docs/product1`.
      1. Die &quot;Topic page template&quot;wird automatisch auf `Topic Page` gesetzt.


1. Speichern Sie die an der Vorgabe vorgenommenen Änderungen.
1. Wählen Sie die Option **Erzeugen** aus.
1. Generieren Sie AEM Sites für die entsprechende Zuordnung. Zum Beispiel: `/content/AEMG-Docs-Site/en/docs/product`.


   >[!NOTE]
   >
   > Wenn Sie zum ersten Mal Inhalte auf einer AEM Site veröffentlichen, wird empfohlen, die Seiten auf Site-Ebene zu veröffentlichen. Dadurch wird sichergestellt, dass die Ausgabe auf der Instanz **Publish** ohne CSS-Unterbrechung korrekt angezeigt wird.



### Verknüpfte Publish-Themen

Experience Manager Guides vereinfacht die Veröffentlichung komplexer Dokumente, indem es Ihnen ermöglicht, Themenverweise mit dem `peer @scope` zu erstellen. Anschließend können Sie den Veröffentlichungskontext dieser Verweise aus den AEM Sites-Vorgaben definieren und schließlich die Ausgabe der verknüpften Themen generieren.
Weitere Informationen finden Sie unter [Generate output of linking topics from other maps](../user-guide/generate-output-aem-site.md#generate-output-linking-topics-from-other-maps).




Führen Sie die folgenden Schritte aus, um den Veröffentlichungskontext für verknüpfte Dateien anzugeben:
1. Öffnen Sie die Registerkarte **Ausgabevorgaben** der DITA-Map, die Sie veröffentlichen möchten.
1. Wählen Sie die Ausgabevorgabe **AEM Sites** aus.

   Sie können die Registerkarten &quot;**Allgemein**&quot;, &quot;**Inhalt**&quot;, &quot;**Themenliste**&quot;und &quot;**Querverweise**&quot;anzeigen. Die Registerkarte &quot;**Querverweise**&quot;wird angezeigt, wenn Sie die Experience Manager Guides-Version (UUID) verwenden.

   In den folgenden Fällen können Sie die Querverlinkung nicht anzeigen:
   - Für die Vorgaben, die vor Version 4.6 erstellt wurden. Die Registerkarte Querverweise ist deaktiviert und es wird eine QuickInfo angezeigt, siehe Dashboard zuordnen .
   - Für Vorgaben, die über das Mapping-Dashboard erstellt wurden. Weitere Informationen finden Sie in der QuickInfo zum Dashboard zuordnen .
   - Informationen zu OOTB-Vorgaben finden Sie in der QuickInfo zum Zuordnen des Dashboard-Tools .
   - Erstellen Sie für globale Vorgaben eine lokale Kopie dieser globalen Vorgabe, um Querverweise für die Zuordnung festzulegen.
Wenn Sie AEM Sites-Vorgaben aus dem Web Editor verwenden möchten, erstellen Sie entweder eine neue Vorgabe oder duplizieren Sie die vorhandene.

1. Öffnen Sie die Registerkarte **Querverweise**.

   Ihnen wird eine Liste der Themen und ihrer Verweise angezeigt. Sie können den Veröffentlichungskontext für eine Liste von Querverweisen zu Themen angeben, die in anderen DITA-Maps mit `scope="peer"` verfügbar sind.

   Um das Querverweisbedienfeld vom Web Editor verwenden zu können, muss `<xrefs>` über eindeutige IDs verfügen. Eindeutige IDs für `<xrefs>` werden beim Bearbeiten/Speichern des älteren Inhalts automatisch generiert, wenn die ID nicht vorhanden ist.

   >[!NOTE]
   >
   >Auf der Registerkarte **Querverweise** werden Themen angezeigt, die nur mit dem Wert `scope="peer"` verknüpft sind. Bei Links mit `scope="local"` müssen Sie den Veröffentlichungskontext nicht angeben.

   Bei allen verknüpften Themen ist standardmäßig die neueste Ausgabevorgabe und Zuordnung ausgewählt. Der Veröffentlichungskontext für alle verknüpften Themen ist standardmäßig auf `<Most recently generated>` map festgelegt.

   ![Querverweise ](images/aem-sites-cross-map-references.png)

1. Wenn Sie die zuletzt veröffentlichte Ausgabe jeder abhängigen Datei in der Zuordnung verwenden möchten, wählen Sie **Zuletzt generierten Veröffentlichungskontext verwenden** für alle abhängigen Themen aus.
Sie sollten die als übergeordnete Zuordnung ausgewählte Zuordnung veröffentlichen, bevor Sie die Zuordnung mit verknüpften Themen veröffentlichen. Wenn die Zuordnung mit verknüpften Themen nicht veröffentlicht wird, erscheinen die Links in der AEM Sites-Ausgabe als normaler Text anstelle von Hyperlinks.
Sie sollten denselben Typ der AEM Sites-Vorgabe für das verknüpfte Thema auswählen. Wenn die aktuelle AEM Sites-Vorgabe beispielsweise die Zuordnung älterer Komponenten verwendet, wählen Sie eine ähnliche AEM Sites-Vorgabe des verknüpften Themas aus.
1. Wählen Sie in der Dropdown-Liste Übergeordnete Zuordnung die Zuordnungsdatei aus, mit deren Ausgabe Sie die Ausgabe der aktuellen Zuordnung verknüpfen möchten.
Wenn Sie eine Zuordnungsdatei auswählen, wird die UUID der Zuordnung in der Spalte &quot;Übergeordnete Map - UUID&quot;angezeigt. Die mit der ausgewählten Zuordnung verknüpften Ausgabevorgaben werden in der Liste Voreinstellungen der übergeordneten Zuordnung aufgeführt. Beispielsweise enthält Thema 1 in Karte A einen Verweis auf Thema 2. Thema 2 kann in einer oder mehreren Maps vorhanden sein. Sie können für jeden Link die übergeordnete Zuordnung und eine bestimmte Vorgabe oder die zuletzt veröffentlichte Ausgabe auswählen.

1. Wenn dasselbe Thema mehr als einmal in einer Datei referenziert wird, können Sie für jede Instanz einen anderen Veröffentlichungskontext hinzufügen. Dies bietet mehr Flexibilität und Kontrolle über den Inhalt. Zum Beispiel ist Thema 3 sowohl in Karte B als auch in Karte C vorhanden. Thema 1 enthält zwei Verweise auf Thema 3. Sie können Map B als übergeordnete Zuordnung für den ersten Link und Map C als übergeordnete Zuordnung für den zweiten Link auswählen.

1. Wählen Sie in der Dropdown-Liste Voreinstellung der übergeordneten Zuordnung die Ausgabevorgabe aus, mit der Sie die Ausgabe der aktuellen Zuordnung verknüpfen möchten.
   >[!NOTE]
   >
   > Die verschiedenen AEM Sites-Vorgaben der aktuellen Karte werden in der Dropdown-Liste angezeigt. Wenn Sie keine Vorgabe auswählen, wird ein Warnsymbol angezeigt und die Ausgabegenerierung schlägt fehl.
1. Wählen Sie die erforderliche Zuordnung und deren Ausgabevorgabe für alle Quellthemen und dann **Erzeugen** aus.







**Übergeordnetes Thema:** [Grundlegendes zu den Ausgabevorgaben](generate-output-understand-presets.md)
