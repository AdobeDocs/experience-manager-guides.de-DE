---
title: Web-Editor starten
description: Erfahren Sie, wie Sie den Web-Editor über die AEM-Navigationsseite, die AEM Assets-Benutzeroberfläche und die DITA-Zuordnungskonsole in AEM Guides starten.
feature: Authoring, Web Editor
role: User
hide: true
exl-id: 374042e4-0f1c-44cf-926c-c9fefa4b1de0
source-git-commit: ea597cd14469f21e197c700542b9be7c373aef14
workflow-type: tm+mt
source-wordcount: '590'
ht-degree: 0%

---

# Web-Editor starten {#id2056B0140HS}

Sie können den Web-Editor an den folgenden Stellen starten:

- [AEM-Navigationsseite](#id2056BG00RZJ)
- [AEM Assets-Benutzeroberfläche](#id2056BG0307U)
- [DITA Map-Konsole](#id2056BG090BF)

In den folgenden Abschnitten werden die Details beschrieben, wie Sie von verschiedenen Stellen aus auf den Web-Editor zugreifen und ihn starten können.

## AEM-Navigationsseite {#id2056BG00RZJ}

Wenn Sie sich bei AEM anmelden, wird die Navigationsseite angezeigt:

![](images/web-editor-from-navigation-page.png){width="800" align="left"}

Durch Klicken auf **Link** Guides“ gelangen Sie direkt zum Web-Editor.

![](images/web-editor-launch-page.png){width="800" align="left"}

Da Sie den Web-Editor gestartet haben, ohne eine Datei auszuwählen, wird ein leerer Web-Editor-Bildschirm angezeigt. Sie können eine Datei zur Bearbeitung aus dem AEM-Repository oder Ihrer Favoritensammlung öffnen.

- Klicken Sie auf **Guides**-Symbol (![](images/aem-guides-icon.png) ), um zur AEM-Navigationsseite zurückzukehren.

- Die Schaltfläche **Schließen** bringt Sie je nach Einrichtung zu einem Ziel:



  <details>

  <summary> Cloud Services </summary>

  Wenn Sie Cloud-Services verwenden, klicken Sie auf die Schaltfläche **Schließen**, um zur AEM-Navigationsseite zurückzukehren.
  </details>

  <details>

  <summary> On-Premise Software</summary>

  Wenn Sie AEM Guides On-Premise-Software (4.2.1 und höher) verwenden, klicken Sie auf die Schaltfläche **Schließen** auf der rechten Seite, um zu Ihrem aktuellen Dateipfad in der Assets-Benutzeroberfläche zurückzukehren.

  </details>

## AEM Assets-Benutzeroberfläche {#id2056BG0307U}

Ein weiterer Speicherort, von dem aus Sie den Web-Editor starten können, ist die AEM Assets-Benutzeroberfläche. Sie können ein oder mehrere Themen auswählen und direkt im Web-Editor öffnen. Gehen Sie wie folgt vor, um ein Thema im Web-Editor zu öffnen:

1. Navigieren Sie in der Assets-Benutzeroberfläche zu dem Thema, das Sie bearbeiten möchten.

   >[!NOTE]
   >
   > Außerdem wird die UUID des Themas angezeigt.

   .

   ![](images/assets_ui_with_uuid_cs.png){width="800" align="left"}

   >[!IMPORTANT]
   >
   > Stellen Sie sicher, dass Sie über Lese- und Schreibberechtigungen für den Ordner verfügen, der das zu bearbeitende Thema enthält.

1. Um eine exklusive Sperre für das Thema zu erhalten, wählen Sie das Thema aus und klicken Sie auf **Auschecken**.

   >[!IMPORTANT]
   >
   > Wenn Ihr Administrator die Option **Bearbeitung ohne Auschecken deaktivieren** konfiguriert hat, müssen Sie die Datei vor der Bearbeitung auschecken. Wenn Sie die Datei nicht auschecken, wird die Option Bearbeiten nicht angezeigt.

1. Schließen Sie den Asset-Auswahlmodus und klicken Sie auf das Thema, das Sie bearbeiten möchten.

   Die Vorschau des Themas wird angezeigt.

   Sie können den Web-Editor in der Listenansicht, Kartenansicht und im Vorschaumodus öffnen.

   >[!IMPORTANT]
   >
   > Wenn Sie mehrere Themen zur Bearbeitung öffnen möchten, wählen Sie die gewünschten Themen in der Asset-Benutzeroberfläche aus und klicken Sie auf Bearbeiten. Vergewissern Sie sich, dass in Ihrem Browser die Popup-Blocker nicht aktiviert sind, da ansonsten nur das erste Thema in der ausgewählten Liste zur Bearbeitung geöffnet wird.

   ![](images/edit-from-preview_cs.png){width="800" align="left"}

   Wenn Sie ein Thema nicht in der Vorschau anzeigen und es direkt im Web-Editor öffnen möchten, klicken Sie in der Kartenansicht im Schnellaktionsmenü auf das Symbol Bearbeiten :

   ![](images/edit-topic-from-quick-action_cs.png){width="800" align="left"}

1. Klicken Sie **Bearbeiten**, um das Thema im Web-Editor zu öffnen.

   ![](images/edit-mode.png){width="800" align="left"}


## DITA Map-Konsole {#id2056BG090BF}

Gehen Sie wie folgt vor, um den Web-Editor über die DITA-Zuordnungskonsole zu öffnen:

1. Navigieren Sie in der Assets-Benutzeroberfläche zu der DITA-Zuordnungsdatei, die das zu bearbeitende Thema enthält, und klicken Sie darauf.

   Die DITA-Zuordnungskonsole wird angezeigt.

1. Klicken Sie auf **Themen**.

   Eine Liste von Themen in der Zuordnungsdatei wird angezeigt. Die UUID der Themen wird unter dem Thementitel angezeigt.

1. Wählen Sie die Themendatei aus, die Sie bearbeiten möchten.

1. Klicken Sie **Thema bearbeiten**.

   ![](images/edit-topics-map-console_cs.png){width="800" align="left"}

1. Das Thema wird im Web-Editor geöffnet.

   >[!IMPORTANT]
   >
   > Wenn Ihr Administrator die Option **Bearbeitung ohne Auschecken deaktivieren** konfiguriert hat, müssen Sie die Datei vor der Bearbeitung auschecken. Wenn Sie die Datei nicht auschecken, wird das Dokument im Editor im schreibgeschützten Modus geöffnet.


**Übergeordnetes Thema:**[ Arbeiten mit dem Web-Editor](web-editor.md)
