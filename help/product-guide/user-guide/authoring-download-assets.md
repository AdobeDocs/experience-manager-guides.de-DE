---
title: Dateien herunterladen
description: Erfahren Sie, wie Sie Dateien von der DITA-Zuordnungskonsole in AEM Guides herunterladen und eine DITA-Zuordnungsdatei in das AEM-Repository exportieren.
exl-id: ae9eb355-d3ac-446a-958b-5f2da43f5533
feature: Content Management
role: User
source-git-commit: 632b253a36822b4b5b93766153f0fc3a1116b616
workflow-type: tm+mt
source-wordcount: '441'
ht-degree: 0%

---

# Dateien herunterladen {#id216MC0H0BE8}

Sie können Assets, einschließlich DITA- und Nicht-DITA-Dateien, herunterladen. Es gibt mehrere Möglichkeiten, Assets herunterzuladen. Einige Methoden sind nativ in Adobe Experience Manager und andere werden von Adobe Experience Manager Guides unterstützt. Informationen zum nativen Herunterladen von Adobe Experience Manager-Assets finden Sie unter [Herunterladen von Assets von Adobe Experience Manager](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/assets/manage/download-assets-from-aem.html) in der Dokumentation zu Adobe Experience Manager. Im folgenden Abschnitt wird der Mechanismus zum Herunterladen von Dateien über die DITA-Zuordnungskonsole in Experience Manager Guides erläutert.

## Exportieren einer DITA-Zuordnungsdatei

Sobald Sie die DITA-Zuordnungsdatei im Adobe Experience Manager-Repository haben, können Sie die Zuordnungsdatei zusammen mit den abhängigen Elementen herunterladen. Dadurch haben Sie die Möglichkeit, die gesamte Zuordnungsdatei für die Offline-Bearbeitung, Validierung, Überprüfung oder einfache Erstellung eines Backups freizugeben.

Führen Sie die folgenden Schritte aus, um eine DITA-Zuordnungsdatei zusammen mit den abhängigen Dateien herunterzuladen:

1. Navigieren Sie in der Assets-Benutzeroberfläche zu der DITA-Karte, die Sie herunterladen möchten.

1. Wählen Sie die DITA-Map aus, um sie in der DITA-Map-Konsole zu öffnen.

1. Wählen Sie die **Themen** aus, um die Liste der in der DITA-Karte verfügbaren Themen anzuzeigen.

1. Wählen Sie in der Hauptsymbolleiste **Karte herunterladen** aus.

   Das Dialogfeld Zuordnung herunterladen wird angezeigt.

   ![](images/download-map.png){width="300" align="left"}

1. Wählen Sie **Herunterladen** aus. Im Dialogfeld Karte herunterladen können Sie die folgenden Optionen auswählen:

   - **Baseline verwenden**: Wählen Sie diese Option, um eine Liste der Baselines zu erhalten, die für die DITA-Zuordnung erstellt wurden. Wenn Sie die Zuordnungsdatei und deren Inhalte basierend auf einer bestimmten Baseline herunterladen möchten, wählen Sie die Baseline aus der Dropdown-Liste aus. Weitere Informationen zum Arbeiten mit Grundlinien finden Sie unter [Arbeiten mit Grundlinien](generate-output-use-baseline-for-publishing.md#).

   - **Dateihierarchie reduzieren**: Wählen Sie diese Option, um alle referenzierten Themen und Mediendateien in einem Ordner zu speichern.


   >[!NOTE]
   >
   > Sie können die Zuordnungsdatei auch herunterladen, ohne eine Option auszuwählen. In diesem Fall wird die letzte persistierte Version der referenzierten Themen und Mediendateien heruntergeladen.

1. Nachdem Sie auf die Schaltfläche **Herunterladen** geklickt haben, wird die Anfrage zum Herunterladen der Zuordnung in die Warteschlange gestellt. Sobald die Karte zum Herunterladen bereit ist, erhalten Sie die folgende Benachrichtigung.

   ![](images/download-map-prompt.png){width="550" align="left"}

   - Wählen Sie **Herunterladen** aus, um die Zuordnungsdatei im ZIP-Format herunterzuladen.

   - Wählen **Später herunterladen**, um die Zuordnungsdatei zu einem späteren Zeitpunkt herunterzuladen. Der Download-Link kann über den Adobe Experience Manager-Benachrichtigungs-Posteingang aufgerufen werden. Wählen Sie die generierte Zuordnungsbenachrichtigung im Posteingang aus, um die Zuordnung im ZIP-Format herunterzuladen.

   >[!NOTE]
   >
   > Standardmäßig bleiben die heruntergeladenen Zuordnungen fünf Tage lang im Adobe Experience Manager-Benachrichtigungs-Posteingang.

![](images/download-map-inbox.png){width="300" align="left"}

Nachdem die Karte heruntergeladen wurde, können Sie die Karte auswählen und das Symbol Öffnen oben verwenden, um den ausgewählten Bericht zu öffnen.

**Übergeordnetes Thema:**&#x200B;[ Inhalte verwalten](authoring.md)
