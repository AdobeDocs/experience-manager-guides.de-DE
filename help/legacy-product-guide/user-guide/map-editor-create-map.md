---
title: Erstellen einer Zuordnung
description: Erstellen Sie in AEM Guides eine Zuordnung mit dem Zuordnungs-Editor. Erfahren Sie, wie Sie eine Zuordnungsdatei basierend auf einer Zuordnungsvorlage erstellen.
feature: Authoring, Map Editor
role: User
hide: true
exl-id: 981ecaeb-9b1f-4c7a-8336-7746a739bedc
source-git-commit: ea597cd14469f21e197c700542b9be7c373aef14
workflow-type: tm+mt
source-wordcount: '469'
ht-degree: 0%

---

# Erstellen einer Zuordnung {#id176FEN0D05Z}

AEM Guides bietet zwei vordefinierte Kartenvorlagen - DITA-Karte und Bookmap. Sie können auch eigene Zuordnungsvorlagen erstellen und diese für Ihre Autoren freigeben, um Zuordnungsdateien zu erstellen.

Führen Sie die folgenden Schritte aus, um eine Zuordnungsdatei zu erstellen:

1. Navigieren Sie in der Assets-Benutzeroberfläche zu dem Speicherort, an dem Sie die Zuordnungsdatei erstellen möchten.

1. Klicken Sie **Erstellen** \> **DITA Map**.

1. Wählen Sie auf der Blueprint-Seite den Typ der zu verwendenden Zuordnungsvorlagen aus und klicken Sie auf **Weiter**.

   >[!NOTE]
   >
   > Die Art und Weise, wie die Themen in einer Zuordnungsdatei referenziert werden, hängt von der Zuordnungsvorlage ab. Wenn Sie beispielsweise die Zuordnungsvorlage auswählen, werden die Themenreferenzen \(`topicref`\) verwendet, um auf Themen zu verweisen. Im Falle einer Bookmap werden Themenreferenzen mit dem `chapter` Element in DITA erstellt.

   ![](images/map-template.png){width="650" align="left"}

1. Geben Sie auf der Seite Eigenschaften die Zuordnung (**)**.

1. \(Optional\) Geben Sie die Datei **Name** an.

   Wenn Ihr Admin einen automatischen Dateinamen basierend auf einer UUID-Einstellung konfiguriert hat, wird die Option zum Angeben des Dateinamens nicht angezeigt. Ein UUID-basierter Dateiname wird der Datei automatisch zugewiesen.

   Wenn die Option zur Dateibenennung verfügbar ist, wird auch der Name basierend auf dem Titel Ihrer Zuordnung automatisch vorgeschlagen. Wenn Sie den Namen der Zuordnungsdatei manuell angeben möchten, stellen Sie sicher, dass der Dateiname keine Leerzeichen, Apostrophe oder geschweifte Klammern enthält und mit `.ditamap` endet.

1. Klicken Sie auf **Erstellen**.

   Die Meldung Map Created wird angezeigt.

   Jeder neuen Zuordnungsdatei, die Sie über die Assets-Benutzeroberfläche (**)**> **DITA Map** oder den Web-Editor erstellen, wird eine eindeutige Zuordnungs-ID zugewiesen. Außerdem wird die neue Zuordnung als neueste Arbeitskopie in DAM gespeichert. Bis zum Speichern einer Revision einer neu erstellten Zuordnung wird im Versionsverlauf keine Versionsnummer angezeigt. Wenn Sie die Zuordnung zur Bearbeitung öffnen, werden die Versionsinformationen in der rechten oberen Ecke der Registerkarte der Zuordnungsdatei angezeigt:

   ![](images/first-version-map-none.png){width="650" align="left"}

   Die Versionsinformationen für eine neu erstellte Zuordnung werden als *Keine* angezeigt. Wenn Sie eine neue Version speichern, wird ihr eine Versionsnummer als 1.0 zugewiesen. Weitere Informationen zum Speichern einer neuen Version finden Sie unter [Als neue Version speichern](web-editor-features.md#save-as-new-version-id209ME400GXA).

   Sie können die Zuordnung zur Bearbeitung im konfigurierten Zuordnungs-Editor öffnen oder im AEM-Repository speichern.

   >[!NOTE]
   >
   > Um den erweiterten Zuordnungs-Editor zu verwenden, greifen Sie auf die Zuordnungsdatei im Web-Editor zu. Falls Ihr Administrator den erweiterten Zuordnungs-Editor als Standard-Editor in den Zuordnungsdateien konfiguriert hat, wird die Zuordnungsdatei direkt im erweiterten Zuordnungs-Editor zur Bearbeitung geöffnet. Siehe *Festlegen des erweiterten Zuordnungs-Editors als Standard* in Installieren und Konfigurieren von Adobe Experience Manager Guides as a Cloud Service.


**Übergeordnetes Thema:**&#x200B;[ Arbeiten mit dem Zuordnungs-Editor](map-editor.md)
