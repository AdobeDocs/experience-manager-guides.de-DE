---
title: Dateien herunterladen
description: Erfahren Sie, wie Sie Dateien von der DITA-Zuordnungskonsole in AEM Guides herunterladen und eine DITA-Zuordnungsdatei in das AEM-Repository exportieren.
feature: Content Management
role: User
hide: true
exl-id: b04a0abe-a029-44ac-b8f4-138d78908d44
TQID: https://experienceleague.adobe.com/iCZL0VgkFqcKWqnTpNWkXvJUXyMbLUL6wENBvVXe40Y
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2:
  - id: a3bd6397-2eb2-4908-a61c-226e26855dca
  - id: ab01a588-7dea-43f2-a699-0b3f128465d6
subfeature_v2:
  - id: f9dbea21-a714-40dd-bc90-080d8046c93f
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 440
ht-degree: 0%

---

# Dateien herunterladen {#id216MC0H0BE8}

Sie können Assets, einschließlich DITA- und Nicht-DITA-Dateien, herunterladen. Es gibt mehrere Möglichkeiten, Assets herunterzuladen. Einige Methoden sind nativ in AEM und andere werden von AEM Guides unterstützt. Informationen zum nativen Herunterladen von AEM-Assets finden Sie unter [Herunterladen von Assets von Adobe Experience Manager](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/assets/manage/download-assets-from-aem.html) in der AEM-Dokumentation. Im folgenden Abschnitt wird der Mechanismus zum Herunterladen von Dateien über die DITA-Zuordnungskonsole in AEM Guides erläutert.

## Exportieren einer DITA-Zuordnungsdatei

Sobald Sie die DITA-Zuordnungsdatei im AEM-Repository haben, können Sie die Zuordnungsdatei zusammen mit den abhängigen Elementen herunterladen. Dadurch haben Sie die Möglichkeit, die gesamte Zuordnungsdatei für die Offline-Bearbeitung, Validierung, Überprüfung oder einfache Erstellung eines Backups freizugeben.

Führen Sie die folgenden Schritte aus, um eine DITA-Zuordnungsdatei zusammen mit den abhängigen Dateien herunterzuladen:

1. Navigieren Sie in der Assets-Benutzeroberfläche zu der DITA-Karte, die Sie herunterladen möchten.

1. Klicken Sie auf die DITA-Map, um sie in der DITA-Map-Konsole zu öffnen.

1. Wählen Sie die **Themen** aus, um eine Liste der in der DITA-Karte verfügbaren Themen anzuzeigen.

1. Klicken Sie in der Hauptsymbolleiste auf **Karte herunterladen**.

   Das Dialogfeld Zuordnung herunterladen wird angezeigt.

   ![](images/download-map.png){width="300"}

1. Klicken Sie auf **Herunterladen**. Im Dialogfeld Karte herunterladen können Sie die folgenden Optionen auswählen:

   - **Baseline verwenden**: Wählen Sie diese Option, um eine Liste der Baselines zu erhalten, die für die DITA-Zuordnung erstellt wurden. Wenn Sie die Zuordnungsdatei und deren Inhalte basierend auf einer bestimmten Baseline herunterladen möchten, wählen Sie die Baseline aus der Dropdown-Liste aus. Weitere Informationen zum Arbeiten mit Grundlinien finden Sie unter [Arbeiten mit Grundlinien](generate-output-use-baseline-for-publishing.md#).
   - **Dateihierarchie reduzieren**: Wählen Sie diese Option, um alle referenzierten Themen und Mediendateien in einem Ordner zu speichern.
   >[!NOTE]
   >
   > Sie können die Zuordnungsdatei auch herunterladen, ohne eine Option auszuwählen. In diesem Fall wird die letzte persistierte Version der referenzierten Themen und Mediendateien heruntergeladen.

1. Nachdem Sie auf die Schaltfläche **Herunterladen** geklickt haben, wird die Anfrage zum Herunterladen der Zuordnung in die Warteschlange gestellt. Sobald die Karte zum Herunterladen bereit ist, erhalten Sie die folgende Benachrichtigung.

   ![](images/download-map-prompt.png){width="550"}

   - Klicken Sie **Herunterladen**, um die Zuordnungsdatei im ZIP-Format herunterzuladen.

   - Klicken Sie **Später herunterladen**, um die Zuordnungsdatei zu einem späteren Zeitpunkt herunterzuladen. Der Download-Link kann über den AEM-Benachrichtigungs-Posteingang aufgerufen werden. Klicken Sie auf die generierte Zuordnungsbenachrichtigung im Posteingang, um die Zuordnung im ZIP-Format herunterzuladen.

   >[!NOTE]
   >
   > Standardmäßig bleiben die heruntergeladenen Zuordnungen fünf Tage lang im AEM-Benachrichtigungs-Posteingang.

![](images/download-map-inbox.png){width="300"}

Nachdem die Karte heruntergeladen wurde, können Sie die Karte auswählen und das Symbol Öffnen oben verwenden, um den ausgewählten Bericht zu öffnen.

**Übergeordnetes Thema:**&#x200B;[&#x200B; Inhalte verwalten](authoring.md)
