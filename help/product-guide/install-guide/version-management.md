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

Die Versionierung ist ein wichtiger Aspekt jedes Content-Management-Systems. Damit können Sie einen Schnappschuss Ihres digitalen Assets zu einem bestimmten Zeitpunkt erstellen. Wenn eine Version eines digitalen Assets vorhanden ist, können Sie die erforderliche Version des Assets wiederherstellen und aktualisieren. Beim Erstellen einer Version eines Assets checken Sie normalerweise das gewünschte Asset aus und ein.

Als Administrator können Sie Regeln durchsetzen, die Benutzer daran hindern, eine Datei zu bearbeiten, ohne sie auszuchecken. Auf ähnliche Weise können Sie sicherstellen, dass alle ausgecheckten Dateien wieder eingecheckt werden, um Datenverlust zu vermeiden.

In einer Umgebung mit mehreren Verwendungszwecken muss außerdem sichergestellt werden, dass Benutzerinnen und Benutzer keine Dateien aus dem System löschen. Diese Anforderung ist wichtiger für Dateien, die von anderen Benutzern ausgecheckt werden. Sie können zulassen oder verhindern, dass Benutzer Dateien überschreiben, die von anderen Benutzern ausgecheckt wurden. Um zu verhindern, dass Benutzer versehentlich ausgecheckte Dateien aus dem System löschen, stellt AEM Guides eine Konfiguration bereit, die Sie verwenden können. Zusätzlich zu ausgecheckten Dateien können Sie auch das Löschen von Dateien steuern, die Verweise enthalten oder von anderen Dateien referenziert werden. Außerdem können Sie auch eine neue Version für hochgeladene Dateien erstellen.

## Neue Version für hochgeladene Datei erstellen

>[!NOTE]
>
> Diese Konfiguration gilt nur beim Hochladen von Dateien.

Um eine neue Version der hochgeladenen Datei zu erstellen, führen Sie die folgenden Schritte aus:

1. Öffnen Sie die Seite Konfiguration der Adobe Experience Manager-Web-Konsole .

   Die Standard-URL für den Zugriff auf die Konfigurationsseite lautet:

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Suchen Sie nach dem Bundle **com.adobe.fmdita.config.ConfigManager** und klicken Sie darauf.

1. Wählen Sie die **Neue Version für hochgeladene Datei erstellen** aus.

   Standardmäßig ist diese Option deaktiviert.

   Wenn die Option ausgewählt ist, wird ein neuer Versionsverwaltungsmechanismus ausgeführt, der das standardmäßige Upload-Verhalten überschreibt, das bei jedem nachfolgenden Upload gilt. Der Inhalt der hochgeladenen Datei wird als neue Version gespeichert. Wenn die Option deaktiviert ist, verwendet AEM Guides den standardmäßigen Versionsverwaltungsmechanismus der AEM.

1. Klicken Sie auf **Speichern**.


>[!NOTE]
>
> Sie können Dateien in Stapeln von 70 oder weniger hochladen, wenn Sie die Eigenschaft **Neue Version für hochgeladene Datei erstellen** \(create.ver.new.content\) aktivieren und die **Assets-Benutzeroberfläche** verwenden, um Assets stapelweise hochzuladen.

## Einstellungen konfigurieren, um die Bearbeitung von ausgecheckten Dateien zu ermöglichen

Mit dem Web-Editor von AEM Guides können Sie DITA-Themen erstellen und aktualisieren. Sie können den Web-Editor so konfigurieren, dass nur die Dokumente bearbeitet werden können, die aus dem Repository ausgecheckt wurden. Dadurch wird sichergestellt, dass kein anderer Autor versehentlich ein Thema überschreibt, das von einem anderen Autor zur Bearbeitung geöffnet wird. Sobald ein Thema zur Bearbeitung geöffnet wurde, kann ein Autor die Datei zum Zeitpunkt des Schließens der Datei einchecken.

Eine weitere wichtige Regel besteht darin, sicherzustellen, dass Dateien, die ausgecheckt wurden, wieder in das System eingecheckt werden. Dadurch wird verhindert, dass Benutzer die Dateien versehentlich schließen, ohne sie wieder einzuchecken.

Führen Sie die folgenden Schritte aus, um diese Funktionen zu aktivieren:

1. Öffnen Sie die Seite Konfiguration der Adobe Experience Manager-Web-Konsole .

   Die Standard-URL für den Zugriff auf die Konfigurationsseite lautet:

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Suchen Sie nach dem Bundle **com.adobe.fmdita.xmeditor.config.XmlEditorConfig** und klicken Sie darauf.

1. Wählen Sie die Option **Bearbeitung ohne Auschecken deaktivieren** aus.

   ![](assets/xml-editor-config.png){width="650" align="left"}

   Bei dieser Option wird die Option Bearbeiten in der Symbolleiste erst angezeigt, wenn eine Datei ausgecheckt wurde.

1. Wählen Sie die Option **Beim Schließen zum Einchecken auffordern**, um eine Warnmeldung anzuzeigen, wenn eine ausgecheckte Datei geschlossen wird, ohne sie zu speichern oder wieder in das Repository einzuchecken.

1. Klicken Sie auf **Speichern**.


>[!NOTE]
>
> Unabhängig davon, ob Sie diese Funktion aktivieren oder deaktivieren, sind die Optionen zum Auschecken und Einchecken von Dateien immer in einer Themenvorschau verfügbar.

## Ausgecheckte Datei beim Hochladen überschreiben

>[!NOTE]
>
> Diese Konfiguration gilt nur, wenn Sie Dateien über die Assets-Benutzeroberfläche erstellen, nicht aber, wenn Sie Dateien mit dem WebDAV-Tool hochladen.

Führen Sie die folgenden Schritte aus, um Benutzern das Überschreiben der Datei beim Hochladen zu ermöglichen, die von ihnen oder einem anderen Benutzer ausgecheckt wurde:

1. Öffnen Sie die Seite Konfiguration der Adobe Experience Manager-Web-Konsole .

   Die Standard-URL für den Zugriff auf die Konfigurationsseite lautet:

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Suchen Sie nach dem Bundle **com.adobe.fmdita.config.ConfigManager** und klicken Sie darauf.

1. Wählen Sie die **Ausgecheckte Datei beim Hochladen überschreiben** aus.

   Standardmäßig ist diese Option aktiviert. Wenn diese Option aktiviert ist, können Benutzer ausgecheckte Dateien überschreiben. Wenn die Option nicht ausgewählt ist, kann die Datei nicht überschrieben werden, wenn sie von ihnen oder einem anderen Benutzer ausgecheckt wurde.

1. Klicken Sie auf **Speichern**.


## Verhindern des Löschens ausgecheckter Dateien

Führen Sie die folgenden Schritte aus, um zu verhindern, dass Benutzer versehentlich Dateien löschen, die von ihnen oder einem anderen Benutzer ausgecheckt wurden:

1. Öffnen Sie die Seite Konfiguration der Adobe Experience Manager-Web-Konsole .

   Die Standard-URL für den Zugriff auf die Konfigurationsseite lautet:

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Suchen Sie nach dem Bundle **com.adobe.fmdita.xmeditor.config.XmlEditorConfig** und klicken Sie darauf.

1. Wählen Sie die **Löschen von ausgechecktem Inhalt verhindern** aus.

   Standardmäßig ist diese Option aktiviert. Wenn diese Option aktiviert ist, können Benutzer ausgecheckte Dateien nicht löschen.

1. Klicken Sie auf **Speichern**.


Um diese Funktion zu unterstützen, wird in `oak:index` eine neue `drivelock` für die Indexeigenschaft hinzugefügt:

`/oak:index/damAssetLucene/indexRules/dam:Asset/properties/drivelock`

![](assets/index-property-oak-index-drivelock.png){width="800" align="left"}

Stellen Sie zusätzlich zur neuen Indexeigenschaft sicher, dass die folgenden Eigenschaften für `/oak:index/damAssetLucene` festgelegt sind:

- `jcr:primaryType`=`"oak:QueryIndexDefinition"`
- `async`=`"async"`
- `compatVersion`=`"{Long}2"`
- `evaluatePathRestrictions`=`"{Boolean}true"`
- `reindex`=`"{Boolean}false"`
- `reindexCount`=`"{Long}3"` *\(Anzahl der Neuindizierungen; wird durch die Installation des Pakets ersetzt\)*
- `type`=`"lucene"`

>[!NOTE]
>
> Sie können den Wert von `reindex` auf `"{Boolean}true"` ändern. Dies ermöglicht schnellere Suchergebnisse für die ausgecheckten Dateien innerhalb einer Ordnerhierarchie.

## Verhindern des Löschens referenzierter Dateien

Als Administrator können Sie steuern, wer Dateien aus dem AEM-Repository löschen kann. Insbesondere wenn eine Datei Verweise enthält oder von einer anderen Datei referenziert wird, können Sie definieren, wer diese Dateien löschen kann.

Mit dieser Konfiguration können Sie zulassen oder verbieten, dass alle Benutzer Dateien löschen, oder nur einer bestimmten Benutzergruppe erlauben, Dateien zu löschen. Wenn das Löschen von Dateien zulässig ist, wird der folgende Prozess ausgeführt:

- Wenn Sie einen Ordner löschen, der alle referenzierten und referenzierenden Dateien enthält, werden alle Dateien gelöscht. Der Prozess löscht zunächst alle Dateien, die keine Verweise enthalten, gefolgt von den Dateien, die Verweise enthalten oder auf die verwiesen wird.

- Wenn Sie einen Ordner löschen und eine Datei innerhalb des Ordners von einer Datei außerhalb dieses Ordners referenziert wird, werden Sie vor dem Löschen der Datei aufgefordert, den Verweis zu entfernen.


Um festzulegen, wer eine Datei löschen kann, die Verweise enthält oder von anderen Dateien referenziert wird, führen Sie die folgenden Schritte aus:

1. Öffnen Sie die Seite Konfiguration der Adobe Experience Manager-Web-Konsole .

   Die Standard-URL für den Zugriff auf die Konfigurationsseite lautet:

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Suchen Sie nach dem Bundle **com.adobe.fmdita.config.ConfigManager** und klicken Sie darauf.

1. Suchen Sie die Option **Blocklöschung für referenzierte Assets**.

1. Geben Sie je nachdem, wem Sie Zugriff zum Löschen gewähren möchten, eine der folgenden Konstanten an:

   - allow\_unsafe\_delete\_for\_all: Erteilen Sie allen Benutzern die Berechtigung zum Löschen von Dateien. Wenn die Datei(en) Verweise enthält (enthalten) oder von anderen Dateien auf sie verwiesen wird, kann das Löschen der Datei(en) erzwungen werden. Vor dem Löschen der Datei wird eine Eingabeaufforderung mit den Verweisen angezeigt. Sie können den Löschvorgang abbrechen, die Verweise entfernen und schließlich die Datei(en) löschen. Alternativ können Sie die Datei(en) erzwingen löschen, ohne die Verweise zu entfernen.

     ![](assets/allow_unsafe_delete-force-delete.PNG){width="550" align="left"}

   - allow\_unsafe\_delete\_for\_delete\_assets\_group: Ein Administrator oder ein Benutzer, der zur Gruppe *delete-assets* gehört, darf Dateien löschen. Wenn andere Benutzer versuchen, Dateien mit Verweisen zu löschen, dürfen sie diese Dateien erst löschen, nachdem alle Verweise entfernt wurden. Der folgende Screenshot wird angezeigt, wenn ein Benutzer ohne Berechtigungen versucht, Dateien zu löschen.

     ![](assets/allow_unsafe_delete_for_delete_assets_group.PNG){width="550" align="left"}

   - block\_unsafe\_delete\_for\_all: Verhindern Sie, dass alle Benutzer \(einschließlich Administratoren\) Dateien löschen, bis die Verweise auf und von den Datei(en) entfernt wurden.

1. Klicken Sie auf **Speichern**.


## Bereinigen älterer Versionen von DITA-Dateien

Wenn Sie Inhalte aktualisieren und neue Versionen erstellen, werden die vorherigen Versionen der DITA-Dateien im Repository gepflegt. Es kann vorkommen, dass über einen bestimmten Zeitraum viele Versionen für Ihre DITA-Dateien erstellt werden, die zusammen viel Speicherplatz in Ihrem Repository belegen. Mit AEM Guides können Sie die älteren Versionen konfigurieren, die aus dem Repository gelöscht werden sollen.

Wenn Sie über Administratorrechte verfügen, können Sie über die angegebene URL auf dieses Dienstprogramm zugreifen:

`<server folder path> /libs/fmdita/clientlibs/xmleditor_version_purge/page.html`

Die Version einer DITA-Datei, die eines der angegebenen Kriterien erfüllt, wird beibehalten und nicht bereinigt:

- Ist die erste Version einer Datei
- Ist in einer Baseline enthalten
- Ist in jedem Übersetzungs- oder Review-Workflow enthalten
- wurde eine Kennzeichnung zugewiesen
- Erfüllt die definierten Kriterien für Alter oder Anzahl der Versionen

Führen Sie die folgenden Schritte aus, um die älteren Versionen zu bereinigen:

1. Geben Sie die folgenden Details zu den Dateien ein, die Sie bereinigen möchten:

   ![](assets/preview-purge-report.png){width="350" align="left"}

1. &#x200B;
   - **Anzahl der Versionen, die von der neuesten Version beibehalten werden sollen**: Geben Sie die Anzahl der Versionen ein, die beibehalten und nicht gelöscht werden sollen. Wenn Sie beispielsweise „5“ eingeben, werden die letzten 5 Versionen beibehalten und die Versionen davor werden gelöscht, wenn andere Bereinigungsbedingungen erfüllt sind.
- **Innerhalb der Zeitspanne erstellte Versionen beibehalten \(in Tagen\)**: Geben Sie das maximale Alter einer Version in Tagen ein. Die Versionen, die älter als die angegebene Anzahl von Tagen sind, werden bereinigt, wenn andere Bereinigungsbedingungen erfüllt sind. Wenn wir beispielsweise „100“ eingeben, werden alle Versionen, die vor 100 Tagen erstellt wurden, gelöscht, falls andere Bereinigungsbedingungen erfüllt sind.
- **Path**: Wählen Sie den Pfad der Datei oder des Ordners aus, deren Dateien Sie bereinigen möchten.

  >[!NOTE]
  >
  > Sie können nur DITA-Dateien bereinigen.

1. Klicken Sie auf **Vorschau des Bereinigungsberichts**.

   >[!NOTE]
   >
   > Es kann jeweils nur eine Bereinigungsaufgabe geben. Sie können keinen weiteren Versionsbereinigungsvorgang starten, wenn gerade ein Vorgang ausgeführt wird.

   Der Bericht zur Versionsbereinigung wird generiert.

1. Laden Sie den Bericht zur Versionsbereinigung herunter und überprüfen Sie die Dateien und Versionen, die bereinigt werden sollen.
1. Sie können **Bereinigung abbrechen** oder **Bereinigung starten**.

   ![](assets/download-purge-report.png){width="350" align="left"}

   Der Löschstatus wird angezeigt.

   Klicken Sie **Versionsbereinigungsbericht herunterladen**, um die bereinigten Versionen anzuzeigen. Dieser Bericht enthält den Bereinigungsstatus für alle Versionen sowie die Gründe, warum eine bestimmte Version beibehalten wurde oder warum sie gelöscht wurde.


>[!NOTE]
>
> Der Bericht wird unter folgendem Speicherort heruntergeladen: /var/dxml/versionpurge
