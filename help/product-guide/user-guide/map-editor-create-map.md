---
title: Erstellen einer Karte
description: Erstellen Sie eine Karte mit dem Map Editor in AEM Guides. Suchen Sie nach den Schritten zum Erstellen einer Map-Datei basierend auf einer Map-Vorlage.
exl-id: b9cda118-ab6f-4d6b-9616-a083180ba069
feature: Authoring, Map Editor
role: User
source-git-commit: be06612d832785a91a3b2a89b84e0c2438ba30f2
workflow-type: tm+mt
source-wordcount: '469'
ht-degree: 0%

---

# Erstellen einer Karte {#id176FEN0D05Z}

AEM Guides bietet zwei vordefinierte Zuordnungsvorlagen - DITA-Zuordnung und Bookmap. Sie können auch eigene Zuordnungsvorlagen erstellen und diese für Ihre Autoren freigeben, um Zuordnungsdateien zu erstellen.

Führen Sie die folgenden Schritte aus, um eine Zuordnungsdatei zu erstellen:

1. Navigieren Sie in der Assets-Benutzeroberfläche zu dem Speicherort, an dem Sie die Zuordnungsdatei erstellen möchten.

1. Klicken Sie auf **Erstellen** \> **DITA Map**.

1. Wählen Sie auf der Blueprint-Seite den Typ der zu verwendenden Zuordnungsvorlagen aus und klicken Sie auf **Weiter**.

   >[!NOTE]
   >
   > Wie die Themen in einer Map-Datei referenziert werden, hängt von der Zuordnungsvorlage ab. Wenn Sie beispielsweise die Zuordnungsvorlage auswählen, werden die Themenverweise \(`topicref`\) verwendet, um auf Themen zu verweisen. Im Falle einer Bookmap werden Themenverweise mit dem Element `chapter` in DITA erstellt.

   ![](images/map-template.png){width="650" align="left"}

1. Geben Sie auf der Seite Eigenschaften die Zuordnung **Titel** an.

1. \(Optional\) Geben Sie die Datei **Name** an.

   Wenn Ihr Administrator einen automatischen Dateinamen basierend auf der UUID-Einstellung konfiguriert hat, wird Ihnen die Option zum Angeben des Dateinamens nicht angezeigt. Der Datei wird automatisch ein UUID-basierter Dateiname zugewiesen.

   Wenn die Dateibenennungsoption verfügbar ist, wird automatisch auch der Name basierend auf dem Titel Ihrer Zuordnung vorgeschlagen. Wenn Sie den Namen der Zuordnungsdatei manuell angeben möchten, stellen Sie sicher, dass der Dateiname keine Leerzeichen, Apostroph oder Klammern enthält und mit `.ditamap` endet.

1. Klicken Sie auf **Erstellen**.

   Die Meldung Zuordnungserstellung wird angezeigt.

   Jeder neuen Zuordnungsdatei, die Sie über die Assets-Benutzeroberfläche **Erstellen** \> **DITA Map** oder den Web Editor erstellen, wird eine eindeutige Zuordnungs-ID zugewiesen. Außerdem wird die neue Karte als neueste Arbeitskopie in DAM gespeichert. Bis Sie eine Revision einer neu erstellten Zuordnung speichern, wird keine Versionsnummer im Versionsverlauf angezeigt. Wenn Sie die Karte zur Bearbeitung öffnen, werden die Versionsinformationen in der rechten oberen Ecke der Registerkarte der Zuordnungsdatei angezeigt:

   ![](images/first-version-map-none.png){width="650" align="left"}

   Die Versionsinformationen für eine neu erstellte Zuordnung werden als *none* angezeigt. Wenn Sie eine neue Version speichern, wird ihr die Versionsnummer 1.0 zugewiesen. Weitere Informationen zum Speichern einer neuen Version finden Sie unter [Als neue Version speichern](web-editor-features.md#save-as-new-version-id209ME400GXA).

   Sie können die Map zur Bearbeitung im konfigurierten Map-Editor öffnen oder die Map-Datei im AEM-Repository speichern.

   >[!NOTE]
   >
   > Um den erweiterten Map-Editor zu verwenden, greifen Sie im Web Editor auf die Map-Datei zu. Falls Ihr Administrator den erweiterten Map-Editor als Standardeditor in den Zuordnungsdateien konfiguriert hat, wird die Zuordnungsdatei direkt im erweiterten Map-Editor zur Bearbeitung geöffnet. Siehe Abschnitt *Einrichten des erweiterten Map-Editors als Standard* unter Installieren und Konfigurieren von Adobe Experience Manager Guides as a Cloud Service .


**Übergeordnetes Thema:**[ Arbeiten mit dem Map-Editor](map-editor.md)
