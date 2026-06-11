---
title: Importieren von Inhalten aus Git-Repositorys mit dem Git-Connector (Beta) in Experience Manager Guides
description: Erfahren Sie, wie Sie mit dem Git-Connector (Beta) in Experience Manager Guides Inhalte aus Git-Repositorys importieren, Aktualisierungen erneut abrufen, GUIDs beibehalten und Konflikte verwalten können.
feature: Authoring, Features of Web Editor
role: User
TQID: https://experienceleague.adobe.com/DDAXW8cUFjvHUeJIbtL6FaHYSU7NW5fkzTai-7n90ms
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2:
  - id: ab01a588-7dea-43f2-a699-0b3f128465d6
  - id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
subfeature_v2:
  - id: ad602516-aca3-4247-9ae8-f393d958efa9
  - id: d4f22c6d-7923-41e5-9da3-527ff8df4bc8
  - id: f89f75b0-cf2e-4e96-aec8-fe8c39cbd0ef
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
topic_v2:
  - id: a004cc84-67b9-4a33-a3a7-8ec7273ef4dc
source-git-commit: 5f626c210e74c6d11e2441f719cfbfeb33bf55c5
workflow-type: tm+mt
source-wordcount: 941
ht-degree: 0%

---

# Importieren von Inhalten mit dem Git-Connector (Beta)

>[!IMPORTANT]
>
> Der Git-Connector ist derzeit als Beta-Funktion verfügbar und standardmäßig deaktiviert. Wenden Sie sich zur Aktivierung dieser Funktion an das Customer Success-Team.

Mit dem Git-Connector können Sie Inhalte aus verbundenen Git-Repositorys in Experience Manager Guides importieren. Nachdem die Inhalte importiert wurden, können Sie die Funktionen für Authoring, Review, Übersetzung und Publishing von Experience Manager Guides verwenden, um Dokumentation zu entwickeln und bereitzustellen.

Wenn sich Inhalte im Quell-Repository ändern, können Sie Aktualisierungen erneut abrufen, Konflikte überprüfen und die neuesten Änderungen mit Experience Manager Guides synchronisieren.

## Voraussetzungen

Bevor Sie mit der Verwendung dieser Funktion beginnen, stellen Sie Folgendes sicher:

- Die Git-Connector-Funktion muss für Ihre Umgebung aktiviert sein.
- (*falls aktiviert*) Ihr Administrator hat den Git-Connector in Ihrer Umgebung konfiguriert. Weitere Informationen finden Sie unter [Erstellen und Konfigurieren des Git-Connectors über die Benutzeroberfläche](../install-conf-guide/conf-git-connector.md).
- Sie haben *Lesezugriff* auf das Git-Repository, das den Inhalt enthält, den Sie importieren möchten.
- Sie wissen, welche Repository-Verzweigung und welcher Quellordner Sie importieren möchten.
- Sie kennen den Zielordner in Experience Manager Guides, in dem die importierten Inhalte gespeichert werden.

## Importieren von Inhalten aus dem verbundenen Git-Repository

Nachdem Ihr Administrator den Git-Connector konfiguriert hat, können Sie ihn im Editor verwenden, um mit dem Import von Inhalten aus einem Git-Repository zu beginnen.  Führen Sie die folgenden Schritte aus, um Inhalte aus einem Git-Repository zu importieren:

1. Öffnen Sie im Editor den linken Bereich.
1. Wählen Sie **Datenquellen** aus.

   Die verbundenen Datenquellen werden angezeigt.

1. Wählen Sie die Kachel **Git-Connector** aus.

1. Klicken Sie auf das Symbol &quot;+&quot; und dann auf **Massenimport**.

   Das **Massenimport** Dialogfeld wird angezeigt.

   ![](images/git-bulk-importer-dialog.png)

1. Geben **im Dialogfeld &quot;**-Import“ einen Namen für den Import ein, wählen Sie einen Unterordner aus Ihrem konfigurierten Git-Repository aus und klicken Sie auf **Speichern und abrufen**.  Die Liste der für den Import verfügbaren Dateien wird im Dialogfeld angezeigt. Überprüfen Sie die Liste und validieren Sie den Inhalt, bevor Sie fortfahren.

   ![](images/git-bulk-importer-import-all.png)

1. Wählen Sie nach der Überprüfung der Dateien **Alle importieren** aus, um den Inhalt in Experience Manager Guides zu importieren.

   >[!NOTE]
   >
   > Sie können **Automatische Synchronisierung** aktivieren, um Inhalte aus Ihrem Git-Repository automatisch zu synchronisieren und in Experience Manager Guides zu importieren. Wenn Fehler erkannt werden, wird die automatische Synchronisierung nicht ausgelöst und der Autor muss den Inhalt manuell importieren, indem er **Alle importieren)**. Nach der Aktivierung kann die automatische Synchronisierung für das Import-Tool nicht mehr deaktiviert werden.

Nachdem der Inhalt importiert wurde, wird er beim Einrichten **Git-Connectors unter dem konfigurierten** Target-AEM-Stammverzeichnis“ gespeichert.

## Git-importierte Inhalte verwalten

Nachdem Inhalte in Experience Manager Guides importiert wurden, können Sie die verfügbaren Aktionen verwenden, um die Inhalte zu verwalten und mit den Änderungen im Quell-Repository synchronisiert zu halten.

![](images/git-connector-imported-content-options.png){width="600"}

- **Vorschau**: Vorschau importierter Inhalte. Wenn das Quell-Repository Aktualisierungen enthält, überprüfen Sie die Unterschiede und verwenden Sie die Option **Refetch**, um die neuesten Änderungen zu importieren.
- **Löschen**: Importierte Inhalte entfernen, die nicht mehr benötigt werden.
- **Umbenennen**: Umbenennen importierter Inhalte, um die Identifizierung zu erleichtern.
- **Protokoll anzeigen**: Anzeigen des Importprotokolls, um Details zum Importvorgang anzuzeigen.
- **Bericht anzeigen**: Anzeigen und Herunterladen des **Massenimportberichts** der Details wie:

   - Gesamtzahl der importierten Dateien
   - Anzahl erfolgreicher Importe
   - Anzahl fehlgeschlagener Importe

  ![](images/git-connector-view-report.png){width="600"}

  Sie können auch den detaillierten Bericht herunterladen. Wenn einige Dateien nicht importiert werden können, verwenden Sie **Fehlgeschlagene Importe wiederholen**, um erneut zu versuchen, sie zu importieren.

## Überprüfen und Beheben von Inhaltskonflikten

Wenn Sie Inhalte erneut aus einem Git-Repository abrufen, werden Unterschiede im Inhalt zwischen der Repository-Version und den entsprechenden in Experience Manager Guides verfügbaren Inhalten als Konflikte angezeigt. Sie müssen diese Konflikte lösen und zusammenführen, bevor Sie die Daten in Experience Manager Guides importieren.

Führen Sie die folgenden Schritte aus, um Konflikte zu lösen und zusammenzuführen:

1. Öffnen Sie das Dialogfeld Massenimport-Tool und wählen Sie **Erneut abrufen** aus.
1. Wenn Konflikte erkannt werden, wird die Registerkarte **Zusammenführen erforderlich** mit den Dateien angezeigt, die Konflikte enthalten. Wählen Sie die Registerkarte **Zusammenführen erforderlich** und wählen Sie dann eine Datei aus der Liste aus, um die Konflikte zu überprüfen und zu lösen.
1. Überprüfen Sie den Inhalt in den folgenden Abschnitten:

   ![](images/git-connector-resolve-conflicts.png){width="600"}

   - Im Abschnitt **AEM** wird die aktuelle Version des in Experience Manager Guides vorhandenen Inhalts angezeigt.
   - Im **Git**-Abschnitt wird die neueste Version des Inhalts aus dem Repository angezeigt.
   - Im Abschnitt **Zusammenführen** wird der zusammengeführte Inhalt angezeigt.

1. Überprüfen Sie die im Editor hervorgehobenen Unterschiede und lösen Sie die Konflikte mithilfe der Zusammenführungssteuerelemente:

   - Wenn Sie die neuesten Änderungen aus dem Git-Repository verwenden möchten, stellen Sie sicher, dass das Kontrollkästchen für den Konflikt im Abschnitt **Git** ausgewählt ist, und wählen Sie dann das entsprechende `<<<` aus. Der ausgewählte Git-Inhalt ersetzt den widersprüchlichen Inhalt im Abschnitt **Zusammenführen**.

     ![](images/git-connector-replace-with-git.png){width="600"}

   - Wenn Sie Inhalte aus beiden Versionen beibehalten möchten, deaktivieren Sie das Kontrollkästchen für den Konflikt und fügen Sie dann mit dem `<<<`-Steuerelement die erforderlichen Inhalte zum Abschnitt **Zusammenführen** hinzu, ohne den vorhandenen Inhalt zu ersetzen.

     ![](images/git-connector-keep-both-versions.png){width="600"}

   - Ebenso können Sie das `>>>` im Abschnitt AEM verwenden, um die derzeit in Experience Manager Guides verfügbare Version beizubehalten.

     ![](images/git-connector-accept-aem-version.png){width="600"}

1. Führen Sie nach der Überprüfung des zusammengeführten Inhalts eine der folgenden Aktionen aus:

   - Verwenden Sie **Änderungen von Git annehmen** wenn die Repository-Version den widersprüchlichen Inhalt ersetzen soll.
   - Verwenden Sie **Als zusammengeführt markieren**, nachdem Sie die zusammengeführte Version überprüft und aktualisiert haben, um sicherzustellen, dass sie den Inhalt enthält, den Sie beibehalten möchten.
   - Verwenden Sie **Zurücksetzen**, um alle zusammengeführten Aktualisierungen zu verwerfen und den Inhalt in den Originalzustand zurückzuversetzen.

Nachdem alle Dateien, die die Konflikte enthalten, als zusammengeführt markiert wurden **ist die Schaltfläche &quot;** importieren“ aktiviert. Wählen Sie **Alle importieren**, um den Prozess zum Lösen von Konflikten abzuschließen.

Wenn das Repository vollständig neue Inhalte enthält, z. B. ein neues Thema, einen neuen Absatz oder eine neue Zeile, die nicht mit vorhandenen Inhalten in Konflikt stehen, wird sie unter **Aktualisierungen bereinigen** angezeigt. Diese Aktualisierungen erfordern keine Konfliktlösung und können direkt importiert werden.

![](images/git-connector-clean-updates.png){width="600"}


