---
title: Dateien herunterladen
description: Erfahren Sie, wie Sie Dateien von der DITA-Zuordnungskonsole in AEM Guides herunterladen und eine DITA-Zuordnungsdatei in das AEM-Repository exportieren.
exl-id: ae9eb355-d3ac-446a-958b-5f2da43f5533
feature: Content Management
role: User
TQID: https://experienceleague.adobe.com/xwz0wuugvwPsmIX78kuwv5te2NGcNTik-qoJvijRzzg
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2:
  - id: a3bd6397-2eb2-4908-a61c-226e26855dca
  - id: ab01a588-7dea-43f2-a699-0b3f128465d6
subfeature_v2:
  - id: a7bba4a6-624b-4427-a9b8-dd411a1bfd41
  - id: ad602516-aca3-4247-9ae8-f393d958efa9
  - id: f9dbea21-a714-40dd-bc90-080d8046c93f
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 864
ht-degree: 0%

---

# Dateien herunterladen {#id216MC0H0BE8}

Sie können Assets, einschließlich DITA- und Nicht-DITA-Dateien, herunterladen. Es gibt mehrere Möglichkeiten, Assets herunterzuladen. Einige Methoden sind nativ in Adobe Experience Manager und andere werden von Adobe Experience Manager Guides unterstützt. Informationen zum nativen Herunterladen von Adobe Experience Manager-Assets finden Sie unter [Herunterladen von Assets von Adobe Experience Manager](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/assets/manage/download-assets-from-aem.html?lang=de) in der Dokumentation zu Adobe Experience Manager. Im folgenden Abschnitt wird der Mechanismus zum Herunterladen von Dateien in Experience Manager Guides erläutert.

## Herunterladen einer DITA-Map-Datei aus dem Editor

Führen Sie die folgenden Schritte aus, um eine DITA-Zuordnungsdatei aus dem Editor herunterzuladen:

1. Navigieren Sie zur DITA-Karte, die Sie herunterladen möchten.
1. Wählen Sie die DITA-Karte aus, um sie im Editor zu öffnen.

1. Wählen Sie in der Kartenansicht das Symbol **Optionen** und dann **Karte herunterladen** aus der Liste aus.

   ![](images/download-map-option-editor.png)

   Das **„Karte**&quot; wird angezeigt.

   ![](images/download-map-dialog-new.png){width="300"}

1. Im Dialogfeld Karte herunterladen können Sie die folgenden Optionen auswählen:

   - **Baseline verwenden**: Wählen Sie diese Option, um eine Liste der Baselines zu erhalten, die für die DITA-Zuordnung erstellt wurden. Wenn Sie die Zuordnungsdatei und deren Inhalte basierend auf einer bestimmten Baseline herunterladen möchten, wählen Sie die Baseline aus der Dropdown-Liste aus. Weitere Informationen zum Arbeiten mit Grundlinien finden Sie unter [Arbeiten mit Grundlinien](generate-output-use-baseline-for-publishing.md#).

   - **Dateihierarchieoptionen**: Sie können auch das Dropdown-Menü „Dateihierarchie“ verwenden, um festzulegen, wie die Ordnerstruktur für Ihre heruntergeladenen Zuordnungsdateien verarbeitet werden soll. Folgende Optionen sind verfügbar:

      - **Dateihierarchie beibehalten**: Wählen Sie diese Option aus der Dropdown-Liste, um die vorhandene Ordnerstruktur für die heruntergeladenen Dateien beizubehalten.
      - **Dateihierarchie reduzieren**: Wählen Sie diese Option aus der Dropdown-Liste, um alle referenzierten Themen und Mediendateien in einen Ordner herunterzuladen.

     Für jede Option können Sie außerdem angeben, wie Dateinamen für heruntergeladene Dateien verarbeitet werden. Die folgenden Dateinamenoptionen sind verfügbar:

      - **GUID-Dateinamen verwenden**: Lädt die Zuordnungsdatei mit GUID als Dateinamen herunter.
      - **Tatsächlichen Dateinamen verwenden**: Lädt die Zuordnungsdatei mit dem ursprünglichen Dateinamen herunter. Wenn diese Option mit Dateihierarchie reduzieren verwendet wird, werden alle doppelten Dateinamen in der Zuordnung automatisch durch Anhängen numerischer Suffixe (_2, _3 usw.) aufgelöst, um eindeutige Dateinamen sicherzustellen.

   >[!NOTE]
   >
   > Sie können die Zuordnungsdatei auch herunterladen, ohne eine Option auszuwählen. In diesem Fall wird die letzte persistierte Version der referenzierten Themen und Mediendateien heruntergeladen.


1. Wählen Sie **Herunterladen** aus.

   Die Anfrage zum Herunterladen der Zuordnung wird in die Warteschlange gestellt.

   ![](images/download-map-notification.png)

   Sobald die Karte zum Herunterladen bereit ist, erhalten Sie die folgende Benachrichtigung.

   ![](images/download-map-success-message.png){width="550"}

1. Klicken Sie **Herunterladen**, um die Zuordnungsdatei im `.zip`-Format herunterzuladen. Oder laden Sie sie später aus dem AEM-Posteingang herunter.

   >[!NOTE]
   >
   > Standardmäßig bleiben die heruntergeladenen Zuordnungen fünf Tage lang im Adobe Experience Manager-Benachrichtigungs-Posteingang.

Nachdem die Karte heruntergeladen wurde, können Sie die Karte auswählen und das Symbol Öffnen oben verwenden, um den heruntergeladenen Inhalt zu öffnen. Um die zugehörigen Metadaten der heruntergeladenen Zuordnung anzuzeigen, öffnen Sie die im heruntergeladenen Inhalt enthaltene `metdata.json`. Diese Datei ist für die beiden Optionen *Dateihierarchie* „Dateihierarchie reduzieren“ und „Dateihierarchie beibehalten“ verfügbar.

## Herunterladen einer DITA-Map-Datei vom Map-Dashboard

Sobald Sie die DITA-Zuordnungsdatei im Adobe Experience Manager-Repository haben, können Sie die Zuordnungsdatei zusammen mit den abhängigen Elementen herunterladen. Dadurch haben Sie die Möglichkeit, die gesamte Zuordnungsdatei für die Offline-Bearbeitung, Validierung, Überprüfung oder einfache Erstellung eines Backups freizugeben.

Führen Sie die folgenden Schritte aus, um eine DITA-Zuordnungsdatei zusammen mit den abhängigen Dateien herunterzuladen:

1. Navigieren Sie in der Assets-Benutzeroberfläche zu der DITA-Karte, die Sie herunterladen möchten.

1. Wählen Sie die DITA-Map aus, um sie in der DITA-Map-Konsole zu öffnen.

1. Wählen Sie die **Themen** aus, um die Liste der in der DITA-Karte verfügbaren Themen anzuzeigen.

1. Wählen Sie in der Hauptsymbolleiste **Karte herunterladen** aus.

   Das Dialogfeld Zuordnung herunterladen wird angezeigt.

   ![](images/download-map.png){width="300"}

1. Wählen Sie **Herunterladen** aus. Im Dialogfeld Karte herunterladen können Sie die folgenden Optionen auswählen:

   - **Baseline verwenden**: Wählen Sie diese Option, um eine Liste der Baselines zu erhalten, die für die DITA-Zuordnung erstellt wurden. Wenn Sie die Zuordnungsdatei und deren Inhalte basierend auf einer bestimmten Baseline herunterladen möchten, wählen Sie die Baseline aus der Dropdown-Liste aus. Weitere Informationen zum Arbeiten mit Grundlinien finden Sie unter [Arbeiten mit Grundlinien](generate-output-use-baseline-for-publishing.md#).

   - **Dateihierarchie reduzieren**: Wählen Sie diese Option, um alle referenzierten Themen und Mediendateien in einem Ordner zu speichern.


   >[!NOTE]
   >
   > Sie können die Zuordnungsdatei auch herunterladen, ohne eine Option auszuwählen. In diesem Fall wird die letzte persistierte Version der referenzierten Themen und Mediendateien heruntergeladen.

1. Nachdem Sie auf die Schaltfläche **Herunterladen** geklickt haben, wird die Anfrage zum Herunterladen der Zuordnung in die Warteschlange gestellt. Sobald die Karte zum Herunterladen bereit ist, erhalten Sie die folgende Benachrichtigung.

   ![](images/download-map-prompt.png){width="550"}

   - Wählen Sie **Herunterladen** aus, um die Zuordnungsdatei im ZIP-Format herunterzuladen.

   - Wählen **Später herunterladen**, um die Zuordnungsdatei zu einem späteren Zeitpunkt herunterzuladen. Der Download-Link kann über den Adobe Experience Manager-Benachrichtigungs-Posteingang aufgerufen werden. Wählen Sie die generierte Zuordnungsbenachrichtigung im Posteingang aus, um die Zuordnung im ZIP-Format herunterzuladen.

   >[!NOTE]
   >
   > Standardmäßig bleiben die heruntergeladenen Zuordnungen fünf Tage lang im Adobe Experience Manager-Benachrichtigungs-Posteingang.

![](images/download-map-inbox.png){width="300"}

Nachdem die Karte heruntergeladen wurde, können Sie die Karte auswählen und das Symbol Öffnen oben verwenden, um den heruntergeladenen Inhalt zu öffnen.

**Übergeordnetes Thema:**&#x200B;[&#x200B; Inhalte verwalten](authoring.md)
