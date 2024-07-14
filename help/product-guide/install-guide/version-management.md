---
title: Versionsverwaltung
description: Funktionsweise der Versionsverwaltung
exl-id: 24e44618-9c4e-4547-a00d-216ef3fb4854
feature: Version Management
role: Admin
level: Experienced
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '1662'
ht-degree: 0%

---

# Versionsverwaltung {#id181GB000XY4}

Die Versionierung ist ein wichtiger Aspekt jedes Content Management-Systems. Damit können Sie zu einem bestimmten Zeitpunkt eine Momentaufnahme Ihres digitalen Assets erstellen. Wenn eine Version eines digitalen Assets vorhanden ist, können Sie die erforderliche Version des Assets wiederherstellen und aktualisieren. In der Regel würden Sie zum Erstellen einer Version eines Assets das erforderliche Asset auschecken und einchecken.

Als Administrator können Sie Regeln durchsetzen, die Benutzer daran hindern, eine Datei zu bearbeiten, ohne sie auszuchecken. Ebenso können Sie sicherstellen, dass alle ausgecheckten Dateien wieder eingecheckt werden, um Datenverlust zu vermeiden.

In einer Umgebung mit mehreren Anwendungen ist es auch wichtig sicherzustellen, dass Benutzer keine Dateien aus dem System löschen. Diese Anforderung ist besonders wichtig für Dateien, die von anderen Benutzern ausgecheckt werden. Sie können zulassen oder verhindern, dass Benutzer Dateien überschreiben, die von anderen Benutzern ausgecheckt wurden. Um zu verhindern, dass Benutzer versehentlich ausgecheckte Dateien aus dem System löschen, stellt AEM Guides eine Konfiguration bereit, die Sie verwenden können. Zusätzlich zu ausgecheckten Dateien können Sie auch das Löschen von Dateien steuern, die Verweise enthalten oder aus anderen Dateien referenziert werden. Außerdem können Sie auch eine neue Version für hochgeladene Dateien erstellen.

## Neue Version für hochgeladene Datei erstellen

>[!NOTE]
>
> Diese Konfiguration gilt nur beim Hochladen von Dateien.

Um eine neue Version der hochgeladenen Datei zu erstellen, führen Sie die folgenden Schritte aus:

1. Öffnen Sie die Seite Adobe Experience Manager Web Console Configuration .

   Die Standard-URL für den Zugriff auf die Konfigurationsseite lautet:

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Suchen Sie nach dem Bundle **com.adobe.fmdita.config.ConfigManager** und klicken Sie darauf.

1. Wählen Sie die Option **Neue Version für hochgeladene Datei erstellen** aus.

   Standardmäßig ist diese Option deaktiviert.

   Wenn die Option ausgewählt ist, wird ein neuer Versionsverwaltungsmechanismus eingesetzt, der das standardmäßige Upload-Verhalten für alle nachfolgenden Uploads außer Kraft setzt. Dadurch wird der Inhalt der hochgeladenen Datei als neue Version gespeichert. Wenn die Option deaktiviert ist, verwendet AEM Guides den standardmäßigen Versionsverwaltungsmechanismus AEM.

1. Klicken Sie auf **Speichern**.


>[!NOTE]
>
> Sie können Dateien in Stapeln von 70 oder weniger hochladen, wenn Sie die Eigenschaft **Neue Version für hochgeladene Datei erstellen** \(create.ver.new.content\) aktivieren und die **Assets-Benutzeroberfläche** verwenden, um Assets stapelweise hochzuladen.

## Einstellungen konfigurieren, um die Bearbeitung ausgecheckter Dateien zu ermöglichen

Mit dem Web Editor von AEM Guides können Sie DITA-Themen erstellen und aktualisieren. Sie können den Web Editor so konfigurieren, dass nur die Dokumente bearbeitet werden können, die aus dem Repository ausgecheckt wurden. Dadurch wird sichergestellt, dass kein anderer Autor versehentlich ein Thema überschreibt, das von einem anderen Autor zur Bearbeitung geöffnet wird. Sobald ein Thema zur Bearbeitung geöffnet ist, kann ein Autor die Datei zum Zeitpunkt des Schließens der Datei einchecken.

Eine weitere wichtige Regel besteht darin sicherzustellen, dass ausgecheckte Dateien wieder in das System eingecheckt werden. Dadurch wird verhindert, dass Benutzer die Dateien versehentlich schließen, ohne sie erneut einzuchecken.

Führen Sie die folgenden Schritte aus, um diese Funktionen zu aktivieren:

1. Öffnen Sie die Seite Adobe Experience Manager Web Console Configuration .

   Die Standard-URL für den Zugriff auf die Konfigurationsseite lautet:

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Suchen Sie nach dem Bundle **com.adobe.fmdita.xmleditor.config.XmlEditorConfig** und klicken Sie darauf.

1. Wählen Sie die Option **Bearbeitung ohne Checkout deaktivieren** aus.

   ![](assets/xml-editor-config.png){width="650" align="left"}

   Mit dieser Option wird Benutzern die Option Bearbeiten in der Symbolleiste erst angezeigt, wenn sie eine Datei auschecken.

1. Wählen Sie die Option **Check-in bei Schließen verlangen** aus, um eine Warnmeldung anzuzeigen, sobald eine ausgecheckte Datei geschlossen wird, ohne sie zu speichern oder wieder in das Repository zu checken.

1. Klicken Sie auf **Speichern**.


>[!NOTE]
>
> Unabhängig davon, ob Sie diese Funktion aktivieren oder deaktivieren, sind die Optionen &quot;Auschecken&quot;und &quot;Einchecken&quot;immer in einer Themenvorschau verfügbar.

## Ausgecheckte Datei beim Hochladen überschreiben

>[!NOTE]
>
> Diese Konfiguration ist nur anwendbar, wenn Sie Dateien über die Assets-Benutzeroberfläche erstellen und nicht, wenn Sie Dateien mit dem WebDAV-Tool hochladen.

So können Benutzer die Datei beim Hochladen überschreiben, die von ihnen oder einem anderen Benutzer ausgecheckt wurde:

1. Öffnen Sie die Seite Adobe Experience Manager Web Console Configuration .

   Die Standard-URL für den Zugriff auf die Konfigurationsseite lautet:

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Suchen Sie nach dem Bundle **com.adobe.fmdita.config.ConfigManager** und klicken Sie darauf.

1. Wählen Sie die Option **Ausgecheckte Datei beim Hochladen überschreiben** aus.

   Standardmäßig ist diese Option aktiviert. Wenn diese Option aktiviert ist, können Benutzer ausgecheckte Dateien überschreiben. Wenn die Option nicht ausgewählt ist, kann die Datei nicht überschrieben werden, wenn sie von ihnen oder einem anderen Benutzer ausgecheckt wurde.

1. Klicken Sie auf **Speichern**.


## Löschen ausgecheckter Dateien verhindern

Um zu verhindern, dass Benutzer versehentlich Dateien löschen, die von ihnen oder einem anderen Benutzer ausgecheckt wurden, führen Sie die folgenden Schritte aus:

1. Öffnen Sie die Seite Adobe Experience Manager Web Console Configuration .

   Die Standard-URL für den Zugriff auf die Konfigurationsseite lautet:

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Suchen Sie nach dem Bundle **com.adobe.fmdita.xmleditor.config.XmlEditorConfig** und klicken Sie darauf.

1. Wählen Sie die Option **Löschung des ausgecheckten Inhalts verhindern** aus.

   Standardmäßig ist diese Option aktiviert. Wenn diese Option aktiviert ist, können Benutzer ausgecheckte Dateien nicht löschen.

1. Klicken Sie auf **Speichern**.


Um diese Funktion zu unterstützen, wird in `oak:index` die neue Indexeigenschaft `drivelock` hinzugefügt:

`/oak:index/damAssetLucene/indexRules/dam:Asset/properties/drivelock`

![](assets/index-property-oak-index-drivelock.png){width="800" align="left"}

Stellen Sie neben der neuen Indexeigenschaft sicher, dass die folgenden Eigenschaften auf `/oak:index/damAssetLucene` festgelegt sind:

- `jcr:primaryType`=`"oak:QueryIndexDefinition"`
- `async`=`"async"`
- `compatVersion`=`"{Long}2"`
- `evaluatePathRestrictions`=`"{Boolean}true"`
- `reindex`=`"{Boolean}false"`
- `reindexCount`=`"{Long}3"` *\(Dies ist die Anzahl der Neuindizierungen, die durch die Installation unseres Pakets ersetzt werden\)*
- `type`=`"lucene"`

>[!NOTE]
>
> Sie können den Wert von `reindex` in `"{Boolean}true"` ändern. Dies ermöglicht schnellere Suchergebnisse für die ausgecheckten Dateien innerhalb einer Ordnerhierarchie.

## Löschen referenzierter Dateien verhindern

Als Administrator können Sie steuern, wer Dateien aus dem AEM-Repository löschen kann. Wenn eine Datei Verweise enthält oder von einer anderen Datei referenziert wird, können Sie definieren, wer diese Dateien löschen kann.

Mit dieser Konfiguration können Sie das Löschen von Dateien durch alle Benutzer zulassen oder verweigern oder zulassen, dass nur eine bestimmte Benutzergruppe Dateien löscht. Wenn das Löschen von Dateien zulässig ist, wird der folgende Prozess ausgeführt:

- Wenn Sie einen Ordner löschen, der alle referenzierten und referenzierenden Dateien enthält, werden alle Dateien gelöscht. Der Prozess löscht zunächst alle Dateien, die keine Verweise enthalten, gefolgt von Dateien, die Verweise enthalten oder darauf verwiesen wird.

- Wenn Sie einen Ordner löschen und eine beliebige Datei im Ordner von einer Datei außerhalb dieses Ordners referenziert wird, werden Sie aufgefordert, den Verweis zu entfernen, bevor Sie die Datei löschen.


So definieren Sie, wer eine Datei löschen kann, die Verweise enthält oder von anderen Dateien referenziert wird:

1. Öffnen Sie die Seite Adobe Experience Manager Web Console Configuration .

   Die Standard-URL für den Zugriff auf die Konfigurationsseite lautet:

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Suchen Sie nach dem Bundle **com.adobe.fmdita.config.ConfigManager** und klicken Sie darauf.

1. Suchen Sie die Option **Löschung für referenzierte Assets blockieren** .

1. Je nachdem, wem Sie Zugriff auf das Löschen gewähren möchten, geben Sie eine der folgenden Konstanten an:

   - allow\_unsafe\_delete\_for\_all: Erteilen Sie allen Benutzern die Berechtigung zum Löschen von Dateien. Wenn in diesem Fall die Datei\(en\) Verweise enthält oder von anderen Dateien referenziert wird, können Sie diese Dateien auch erzwungen löschen\(en\). Vor dem Löschen der Datei wird Ihnen eine Eingabeaufforderung mit den Verweisen angezeigt. Sie können den Löschvorgang abbrechen, die Verweise entfernen und schließlich die Datei löschen\(en\). Alternativ können Sie die Datei\(en\) erzwungen löschen, ohne die Verweise zu entfernen.

     ![](assets/allow_unsafe_delete-force-delete.PNG){width="550" align="left"}

   - allow\_unsafe\_delete\_for\_delete\_assets\_group: Ein Administrator oder ein Benutzer, der der Gruppe *delete-assets* angehört, darf Dateien löschen. Wenn ein anderer Benutzer versucht, Dateien mit Verweisen zu löschen, kann er diese Dateien erst löschen, wenn alle Verweise entfernt wurden. Der folgende Screenshot wird angezeigt, wenn ein Benutzer, der keine Berechtigungen hat, versucht, Dateien zu löschen.

     ![](assets/allow_unsafe_delete_for_delete_assets_group.PNG){width="550" align="left"}

   - block\_unsafe\_delete\_for\_all: Deaktivieren Sie alle Benutzer \(einschließlich Administratoren\) vom Löschen von Dateien, bis die Verweise auf und aus der Datei\(en\) entfernt werden.

1. Klicken Sie auf **Speichern**.


## Löschen älterer Versionen von DITA-Dateien

Wenn Sie Inhalte aktualisieren und neue Versionen erstellen, werden die vorherigen Versionen der DITA-Dateien im Repository verwaltet. Viele Versionen werden möglicherweise über einen bestimmten Zeitraum für Ihre DITA-Dateien erstellt und können gemeinsam eine große Menge an Speicherplatz in Ihrem Repository beanspruchen. Mit AEM Guides können Sie die älteren Versionen konfigurieren, die aus dem Repository gelöscht werden sollen.

Wenn Sie über Administratorrechte verfügen, können Sie über die angegebene URL auf dieses Dienstprogramm zugreifen:

`<server folder path> /libs/fmdita/clientlibs/xmleditor_version_purge/page.html`

Die Version einer DITA-Datei, die eines der angegebenen Kriterien erfüllt, wird beibehalten und nicht bereinigt:

- Ist die erste Version einer Datei
- Ist in eine Grundlinie eingeschlossen
- Ist in einem Übersetzungs- oder Überprüfungs-Workflow enthalten
- Hat eine Beschriftung darauf angewendet
- Erfüllt das definierte Alter oder die Anzahl der Versionskriterien

Führen Sie die folgenden Schritte aus, um die älteren Versionen zu bereinigen:

1. Geben Sie die folgenden Details zu den Dateien ein, die Sie bereinigen möchten:

   ![](assets/preview-purge-report.png){width="350" align="left"}

1. 
   - **Anzahl der Versionen, die von der neuesten Version beibehalten werden sollen**: Geben Sie die Anzahl der Versionen ein, die beibehalten und nicht bereinigt werden sollen. Wenn wir beispielsweise 5 eingeben, werden die letzten fünf Versionen beibehalten und die Versionen vor diesen werden für die Bereinigung qualifiziert, falls andere Bereinigungsbedingungen erfüllt sind.
- **Erstellte Versionen in Zeitspanne beibehalten \(in Tagen\)**: Geben Sie das Höchstalter für eine Version in Tagen ein. Die Versionen, die älter als die angegebene Anzahl von Tagen sind, sind für die Bereinigung qualifiziert, falls andere Bereinigungsbedingungen erfüllt sind. Wenn Sie beispielsweise 100 eingeben, werden alle Versionen, die vor 100 Tagen erstellt wurden, für die Bereinigung qualifiziert, falls andere Bereinigungsbedingungen erfüllt sind.
- **Pfad**: Wählen Sie den Pfad der Datei oder des Ordners aus, deren Dateien Sie bereinigen möchten.

  >[!NOTE]
  >
  > Sie können nur DITA-Dateien bereinigen.

1. Klicken Sie auf **Bericht zur Bereinigung der Vorschau**.

   >[!NOTE]
   >
   > Es kann jeweils nur eine Bereinigungsaufgabe geben. Sie können keinen anderen Versionsbereinigungsvorgang starten, wenn einer gerade ausgeführt wird.

   Der Versionsbereinigungsbericht wird generiert.

1. Laden Sie den Versionsbereinigungsbericht herunter und überprüfen Sie die Dateien und Versionen, die bereinigt werden sollen.
1. Sie können zwischen **Bereinigung abbrechen** oder **Bereinigung starten** wählen.

   ![](assets/download-purge-report.png){width="350" align="left"}

   Der Bereinigungsstatus wird angezeigt.

   Klicken Sie auf **Versionsbereinigungsbericht herunterladen** , um die bereinigten Versionen anzuzeigen. Dieser Bericht liefert den Bereinigungsstatus für alle Versionen zusammen mit den Gründen, warum eine bestimmte Version beibehalten wurde oder warum sie bereinigt wurde.


>[!NOTE]
>
> Der Bericht wird unter folgendem Pfad heruntergeladen: /var/dxml/versionpurge
