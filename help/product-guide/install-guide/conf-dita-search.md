---
title: Konfigurieren der Suche in der AEM Assets-Benutzeroberfläche
description: Erfahren Sie, wie Sie die Suche für die AEM Assets-Benutzeroberfläche konfigurieren
exl-id: b920ba7f-e8fc-4af6-aa8a-b8516b1cffc0
feature: Search Configuration
role: Admin
level: Experienced
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '1695'
ht-degree: 1%

---

# Konfigurieren der Suche in der AEM Assets-Benutzeroberfläche {#id192SC800MY4}

Standardmäßig erkennt AEM DITA-Inhalte nicht, bietet daher keinen Mechanismus zum Durchsuchen von DITA-Inhalten in seinem Repository. Mit AEM Guides können Sie die DITA-Inhaltssuchfunktion in AEM Repository hinzufügen.

Standardmäßig erkennt AEM DITA-Inhalte nicht, bietet daher keinen Mechanismus zum Durchsuchen von DITA-Inhalten in seinem Repository. Außerdem gibt es keine OOTB-Fähigkeit, Inhalte basierend auf ihrer UUID zu suchen. Mit AEM Guides können Sie die DITA-Inhaltssuche und UUID-basierten Suchfunktionen zum AEM-Repository hinzufügen.

Die Konfiguration der DITA-Inhaltssuche umfasst die folgenden Aufgaben:

1. [Hinzufügen der DITA-Element-Suchkomponente in der Assets-Benutzeroberfläche](#id192SF0F50HS)
1. [Hinzufügen einer UUID-basierten Suchkomponente in der Assets-Benutzeroberfläche](#id2034F04K05Z)
1. [Bereitstellen von Berechtigungen für Benutzer](#id192SF0G0RUI)
1. [Hinzufügen benutzerdefinierter Elemente oder Attribute zur Suche](#id192SF0G10YK)
1. [Extrahieren von Metadaten aus vorhandenem Inhalt](#id192SF0GA0HT)

Zusätzlich zur Suchfunktion können Sie auch die Ordner konfigurieren, die nicht in die Suche aufgenommen werden sollen. Weitere Informationen finden Sie unter [Ausschließen temporärer Dateien aus Suchergebnissen](#id197AHI0035Z).

## Hinzufügen der DITA-Element-Suchkomponente in der Assets-Benutzeroberfläche {#id192SF0F50HS}

Führen Sie die folgenden Schritte aus, um die DITA-Inhaltssuchkomponente in der AEM Assets-Benutzeroberfläche hinzuzufügen:

1. Melden Sie sich bei Adobe Experience Manager als Administrator an.

1. Klicken Sie oben auf den Link **Adobe Experience Manager** und wählen Sie **Tools** aus.

1. Wählen Sie **Allgemein** aus der Toolliste und klicken Sie auf die Kachel **Forms durchsuchen** .

1. Wählen Sie in der Liste **Forms durchsuchen** die **Assets Admin-Suchschiene** aus.

1. Klicken Sie auf **Bearbeiten**.
1. Scrollen Sie auf der Registerkarte **Eigenschaft auswählen** zum Ende der Liste.

1. Ziehen Sie **DITA-Elementeigenschaft** an die gewünschte Position im Suchformular.

   ![](assets/drag-search-predicate.png){width="650" align="left"}

1. Klicken Sie auf **Fertig** , um Ihre Änderungen zu speichern.

   Wenn Sie in der Assets-Benutzeroberfläche auf die Option Filter zugreifen, erhalten Sie die Filteroption DITA-Elementsuche .

   ![](assets/search-filter-asset-console.png){width="350" align="left"}


## Hinzufügen einer UUID-basierten Suchkomponente in der Assets-Benutzeroberfläche {#id2034F04K05Z}

Führen Sie Folgendes aus, um die UUID-basierte Suchkomponente in der AEM Assets-Benutzeroberfläche hinzuzufügen:

1. Melden Sie sich bei Adobe Experience Manager als Administrator an.

1. Klicken Sie oben auf den Link **Adobe Experience Manager** und wählen Sie **Tools** aus.

1. Wählen Sie **Allgemein** aus der Toolliste und klicken Sie auf die Kachel **Forms durchsuchen** .

1. Wählen Sie in der Liste **Forms durchsuchen** die **Assets Admin-Suchschiene** aus.

1. Klicken Sie auf **Bearbeiten**.
1. Wählen Sie auf der Registerkarte **Eigenschaft auswählen** die Option **Eigenschaftsprädikat** aus und ziehen Sie sie per Drag-and-Drop an die gewünschte Position im Suchformular.

1. Geben Sie auf der Registerkarte **Einstellungen** die folgenden Details für die neu hinzugefügte Komponente **Eigenschaftsprädikat** an:

   - **Feldbezeichnung**: UUID
   - **Eigenschaftsname**: jcr:content/fmUuid
1. Klicken Sie auf **Fertig** , um Ihre Änderungen zu speichern.

   Wenn Sie in der Assets-Benutzeroberfläche auf die Option Filter zugreifen, erhalten Sie die UUIS-basierte Suchfilteroption.


## Bereitstellen von Berechtigungen für Benutzer {#id192SF0G0RUI}

Autoren und Herausgeber benötigen explizite Berechtigungen, um über die Assets-Benutzeroberfläche auf die Suchfunktionen zugreifen zu können. Wenn Sie diese Berechtigungen nicht erteilen, können Ihre Benutzer DITA-Inhalte nicht anhand ihrer Element-/Attributwerte oder UUID durchsuchen.

Führen Sie die folgenden Schritte aus, um Zugriff auf die DITA-Suchfunktion zu gewähren:

1. Rufen Sie die Seite mit den Benutzer- und Gruppenberechtigungen auf. Die Standard-URL für den Zugriff auf die Seite lautet:

   `http://<server name>:<port>/useradmin.html`

1. Suchen Sie nach der Benutzergruppe oder einem einzelnen Benutzer, dem Sie Zugriff gewähren möchten. Um beispielsweise allen Benutzern in der Gruppe &quot;Autoren&quot;Zugriff zu gewähren, geben Sie &quot;Autoren&quot;in das Feld **Filterabfrage** ein und drücken Sie die Eingabetaste **3}.**

   ![](assets/authors-group-permission.png){width="350" align="left"}

1. Wählen Sie die Gruppe **authors** aus.

1. Wählen Sie im rechten Bereich die Registerkarte **Berechtigungen** aus.

1. Navigieren Sie zum folgenden Ordnerspeicherort:

   /conf/global/settings/dam/search

1. Erteilen Sie die Berechtigung **Lesen** für den Suchordner.

   ![](assets/read-permission-authors.png){width="650" align="left"}

1. Klicken Sie auf **Speichern**.


Der ausgewählte Benutzer oder die ausgewählte Benutzergruppe hat jetzt Zugriff auf die DITA-Inhaltsfunktion in der Assets-Benutzeroberfläche.

## Hinzufügen benutzerdefinierter Elemente oder Attribute zur Suche {#id192SF0G10YK}

Damit die DITA-Suche funktioniert, ist eine gewisse Vorverarbeitung des DITA-Inhalts erforderlich. Dieser Vorverarbeitungsschritt extrahiert selektive Inhalte aus einzelnen DITA-Maps und -Themen, damit sie für eine schnellere Suche indiziert werden können. Intern heißt dieser Prozess *Serialisierung*. Die Serialisierung von DITA-Dateien erfolgt beim Hochladen von Inhalten oder kann auch bei Bedarf ausgeführt werden. Es verwendet eine Konfigurationsdatei, um zu bestimmen, wie viel Inhalt aus jeder DITA-Datei indiziert werden soll. Der Standardspeicherort der Serialisierungsdatei lautet:

/libs/fmdita/config/serializationconfig.xml

Mit der Standardsuchkonfiguration können Sie im DITA `prolog` -Element nach allen Elementen und Attributen suchen. Wenn Sie anhand anderer Elemente oder Attribute suchen möchten, müssen Sie die Serialisierungsdatei für die Suche konfigurieren.

>[!NOTE]
>
> Wenn Sie die Standardsuchkonfiguration im Element `prolog` verwenden möchten, können Sie diesen Prozess überspringen.

Diese Datei enthält zwei Hauptabschnitte: Attributsatz und Regelsatz. Im Folgenden finden Sie einen Ausschnitt des Regelsatzabschnitts:

```XML
<ruleset filetypes="xml dita"><!-- Element rules --><rule xpath="//[contains(@class, 'topic/topic')]/[contains(@class, 'topic/prolog')]//*[not(*)]" text="yes" attributeset="all-attrs" /><!-- Attribute rules --><rule xpath="//[contains(@class, 'topic/topic')]/[contains(@class, 'topic/prolog')]///@[local-name() != 'class']" /></ruleset>
```

Im Regelsatzabschnitt können Sie Folgendes angeben:

- Regeln zum Extrahieren der Elemente

- Regeln zum Extrahieren von Attributen


Eine Regel besteht aus folgenden Elementen:

xpath
:   Dies ist die XPath-Abfrage, die die Elemente oder Attribute aus DITA-Dateien abruft. Die Standardkonfiguration für die Elementregel ruft alle `prolog` -Elemente ab. Außerdem ruft die Standardkonfiguration für die Attributregel alle Attribute von `prolog` -Elementen ab. Sie können eine XPath-Abfrage angeben, um die Elemente oder Attribute zu serialisieren, nach denen Sie suchen möchten.

Die XPath-Abfrage enthält den Klassennamen des Dokumenttyps. Die `topic/topic` -Klasse wird für DITA-Dokumente des Thementyps verwendet. Wenn Sie eine Regel für andere DITA-Dokumente erstellen möchten, müssen Sie die folgenden Klassennamen verwenden:

| Dokumenttyp | Klassenname |
|-------------|----------|
| Thema | - topic/topic |
| Aufgabe | - topic/topic/task/task |
| Konzept | - topic/topic concept/concept |
| Referenz | - topic/topic reference/reference |
| Map | - map/map |

text
:   Wenn Sie nach dem Text innerhalb des angegebenen Elements suchen möchten, geben Sie den Wert yes an. Wenn Sie &quot;Nein&quot;als Wert angeben, werden nur die Attribute innerhalb des Elements serialisiert. Die Attribute, nach denen Sie suchen möchten, müssen im Abschnitt &quot;Attributsatz&quot;angegeben werden.

attributeset
:   Geben Sie die Kennung des Attributsatzes an, den Sie mit dieser Regel verknüpfen möchten. Der Wert &quot;all-attrs&quot;ist ein Sonderfall, der angibt, dass alle Attribute für diese Regel serialisiert werden müssen.

Ein Attributsatz enthält eine Liste von Attributen, nach denen Sie in DITA-Inhalten suchen möchten. Der Attributsatz enthält Folgendes:

id
:   Eine eindeutige Kennung für den Attributsatz. Diese ID wird im Parameter attributeset eines Regelsatzes angegeben.

attribute
:   Eine Liste der Attribute, die durchsucht werden sollen. Für jedes Attribut müssen Sie einen einzelnen Eintrag im Element `attribute` erstellen.

Führen Sie die folgenden Schritte aus, um benutzerdefinierte DITA-Elemente oder -Attribute zur Serialisierungsdatei für die Suche hinzuzufügen:

1. Melden Sie sich bei AEM an und öffnen Sie den CRXDE Lite-Modus.

1. Navigieren Sie zur Konfigurationsdatei für die Serialisierung, die unter folgendem Speicherort verfügbar ist:

   /libs/fmdita/config/serializationconfig.xml

1. Erstellen Sie einen Überlagerungsknoten des Ordners `config` im Knoten `apps` .

1. Navigieren Sie zur Konfigurationsdatei, die im Knoten `apps` verfügbar ist:

   `/apps/fmdita/config/serializationconfig.xml`

1. Fügen Sie die erforderlichen Element- oder Attributregelsätze hinzu.

1. Speichern Sie die Datei.

1. Öffnen Sie die Seite Adobe Experience Manager Web Console Configuration . Die Standard-URL für den Zugriff auf die Konfigurationsseite lautet:

   http://&lt;Servername\>:&lt;Port\>/system/console/configMgr

1. Suchen Sie nach dem Bundle *com.adobe.fmdita.config.ConfigManager* und klicken Sie darauf.

1. Klicken Sie auf **Speichern**.


Die neuen Serialisierungsinformationen werden gespeichert und für die Suche aktiviert. Sie müssen die Metadaten jedoch aus Ihrem vorhandenen DITA-Inhalt extrahieren, um für die Suche verfügbar zu sein.

## Extrahieren von Metadaten aus vorhandenem Inhalt {#id192SF0GA0HT}

Nachdem Sie die standardmäßige Serialisierungsdatei für die Suche geändert haben, müssen Sie die Option DITA-Metadatenextraktion im Bundle *com.adobe.fmdita.config.ConfigManager* aktivieren und dann den Workflow zum Extrahieren von Metadaten ausführen. Dadurch werden die erforderlichen Metadaten aus den vorhandenen DITA-Dateien extrahiert und dieselben werden dann für die Suche bereitgestellt.

Wenn Sie nach dem Aktualisieren der Serialisierungsdatei neue Dateien erstellen oder eine Datei bearbeiten, werden die Metadaten automatisch aus diesen Dateien extrahiert. Der Prozess zum Extrahieren von Metadaten ist nur für Dateien erforderlich, die bereits im AEM Repository vorhanden sind.

Das Extrahieren von Metadaten aus vorhandenen DITA-Dateien umfasst zwei Aufgaben:

1. Aktivieren der Metadatenextraktionsoption in der configMgr
1. Ausführen des Workflows für die Metadatenextraktion

Führen Sie die folgenden Schritte aus, um die Metadatenextraktionsoption in configMgr zu aktivieren:

1. Öffnen Sie die Seite Adobe Experience Manager Web Console Configuration . Die Standard-URL für den Zugriff auf die Konfigurationsseite lautet:

   http://&lt;Servername\>:&lt;Port\>/system/console/configMgr

1. Suchen Sie nach dem Bundle *com.adobe.fmdita.config.ConfigManager* und klicken Sie darauf.

1. Wählen Sie die Option **DITA-Metadatenextraktion aktivieren** aus.

1. Klicken Sie auf **Speichern**.


Führen Sie die folgenden Schritte aus, um den Workflow zur Metadatenextraktion auszuführen:

1. Melden Sie sich bei Adobe Experience Manager als Administrator an.

1. Klicken Sie oben auf den Link **Adobe Experience Manager** und wählen Sie **Tools** aus.

1. Wählen Sie **Guides** aus der Liste der Tools und klicken Sie auf die Kachel **DITA-Metadatenextraktion** .

1. Wenn Sie Metadaten aus einer einzelnen Datei und deren Abhängigkeiten extrahieren möchten, klicken Sie auf den Link **Datei auswählen** und suchen Sie nach einer Datei.

1. Wenn Sie Metadaten aus mehreren Dateien in einem Ordner extrahieren möchten, klicken Sie auf den Link **Ordner auswählen\(s\)** , suchen Sie den gewünschten Ordner und wählen Sie ihn aus. Klicken Sie auf die Schaltfläche **Hinzufügen** , um den Ordner zur Liste der Serialisierungsaufgaben hinzuzufügen.

   >[!NOTE]
   >
   > Sie können mehrere Ordner auswählen und zu einer Serialisierungsaufgabe hinzufügen.

1. Klicken Sie auf **Starten**.

1. Klicken Sie im Dialogfeld &quot;Extraktion von Metadaten bestätigen&quot;auf **OK**.


## Ausschließen temporärer Dateien aus Suchergebnissen {#id197AHI0035Z}

Standardmäßig wird die Suche für das gesamte Repository der AEM durchgeführt. Es kann einige Orte geben, die Sie von der Suche ausschließen möchten. Wenn Sie beispielsweise den Arbeitsablauf für die Inhaltsübersetzung starten, bleiben die nicht genehmigten Dateien an einem temporären Ordnerspeicherort. Wenn Sie die Suche durchführen, werden auch Dateien von diesem temporären Speicherort in den Suchergebnissen zurückgegeben.

Um zu verhindern, dass AEM Guides den Speicherort des temporären Übersetzungsordners durchsucht, müssen Sie den temporären Ordnerspeicherort in der Ausschlussliste hinzufügen.

Führen Sie die folgenden Schritte aus, um den temporären Übersetzungsordner von der Suche auszuschließen:

>[!NOTE]
>
> Mit diesem Verfahren können Sie der Ausschlussliste einen beliebigen anderen Ordnerspeicherort hinzufügen.

1. Melden Sie sich bei AEM an und öffnen Sie den CRXDE Lite-Modus.

1. Navigieren Sie zum Knoten damAssetLucene , der unter folgendem Speicherort verfügbar ist:

   /oak:index/damAssetLucene

1. Fügen Sie die folgende Eigenschaft im Knoten damAssetLucene hinzu:

   | Eigenschaftsname | Typ | Wert |
   |-------------|----|-----|
   | excludedPaths | String\[\] | Fügen Sie dieser Eigenschaft den folgenden Wert hinzu: <br>/content/dam/projects/translation\_output |

1. Navigieren Sie zum Knoten lucene , der unter folgendem Speicherort verfügbar ist:

   /oak:index/lucene

1. Fügen Sie die folgende Eigenschaft im Knoten lucene hinzu:

   | Eigenschaftsname | Typ | Wert |
   |-------------|----|-----|
   | excludedPaths | String\[\] | Fügen Sie dieser Eigenschaft die folgenden Werte hinzu: <br><ul><li>/var/dxml</li><li>/content/dam/projects/translation\_output</li></ul> |
