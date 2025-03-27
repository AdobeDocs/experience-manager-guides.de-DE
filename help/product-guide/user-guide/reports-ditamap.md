---
title: DITA-Map-Bericht über das Map-Dashboard
description: Generieren von DITA-Zuordnungsberichten über das Zuordnungs-Dashboard in AEM Guides. Erfahren Sie, wie Sie die CSV-Datei eines DITA-Zuordnungsberichts generieren.
exl-id: 7fe52ee0-e940-467b-9b8d-3d2371de7a84
feature: Report Generation
role: User
source-git-commit: ac83f613d87547fc7f6a18070545e40ad4963616
workflow-type: tm+mt
source-wordcount: '759'
ht-degree: 0%

---

# DITA-Map-Bericht über das Map-Dashboard {#id205BB800EEN}

Adobe Experience Manager Guides bietet Ihren Admins die Reporting-Funktionen, um die Integrität der Dokumentation insgesamt zu überprüfen, bevor sie live geschaltet oder Endbenutzern zur Verfügung gestellt wird. Der DITA-Zuordnungsbericht im Zuordnungs-Dashboard in Experience Manager Guides bietet wertvolle Informationen wie fehlende Themen, Themen mit fehlenden Elementen, UUID referenzierter Themen und Mediendateien sowie den Prüfungsstatus jedes Themas. Ein detaillierter Bericht auf individueller Themenebene enthält auch DITA-inhaltsbezogene Informationen wie Inhaltsreferenzen und fehlende Bilder oder Querverweise.

>[!NOTE]
>
>Experience Manager Guides aktualisiert diesen Bericht bei jedem Ereignis, das zu einer Änderung in Ihrer Zuordnungsdatei führt oder wenn ein Verweis in Ihrer Themendatei aktualisiert wird.

Führen Sie die folgenden Schritte aus, um den DITA Map-Bericht anzuzeigen:

1. Navigieren Sie in der Assets-Benutzeroberfläche zu der DITA-Zuordnungsdatei, für die Sie den Bericht anzeigen möchten, und wählen Sie sie aus.

1. Wählen Sie **Berichte** aus.

   ![](images/reports-page-uuid-new.png){align="left"}

   Die Seite Berichte ist in zwei Teile unterteilt:

   - **Themenzusammenfassung:**

     Listet die Gesamtübersicht der ausgewählten Zuordnungsdatei auf. Wenn Sie sich die Zusammenfassung ansehen, können Sie schnell die Gesamtzahl der Themen in der Zuordnung, fehlende Themen, die Anzahl der Themen mit fehlenden Elementen, den Status der Themen - im Entwurf, In Überprüfung oder Überprüft - ermitteln.

   - **Details:**

     Wenn Sie ein Thema auswählen, wird ein detaillierter Bericht zum ausgewählten Thema angezeigt.

     ![](images/detailed-report-uuid-new.png){align="left"}

     Nachfolgend werden die unter **A**, **B**, **C** und **D** hervorgehobenen Punkte beschrieben:

      - **Thema**: Der Titel des in der DITA-Zuordnung angegebenen Themas. Wenn Sie den Mauszeiger über den Titel des Themas bewegen, wird der vollständige Pfad des Themas angezeigt. Wenn das Thema Probleme aufweist, z. B. fehlende Verweise oder Bilder, wird ein roter Punkt vor dem Titel des Themas angezeigt.

      - **Dateiname**: Name der Datei.

      - **UUID**: Die universell eindeutige Kennung \(UUID\) der Datei.

      - **Autor**: Benutzer, der zuletzt an diesem Thema gearbeitet hat.

      - **Dokumentstatus**: Der aktuelle Status des Dokuments - Entwurf, In Überprüfung oder Überprüft.

      - **Fehlende Elemente**: Listet die Anzahl fehlender Bilder oder beschädigter Querverweise auf, falls vorhanden.

      - **Fehlende Themen \(B\)**: Wenn es Themen mit fehlerhaften Verweisen gibt, werden diese Themen unter der Liste „Fehlende Themen“ aufgeführt.

      - **In FrameMaker öffnen \(C\)**: Listet die Anzahl der fehlenden Bilder oder beschädigten Querverweise auf, falls vorhanden.

      - **Im Editor öffnen \(D\)**: Wenn Sie auf dieses Symbol klicken, wird das Thema im Editor geöffnet.


   Nachfolgend werden die unter **E** hervorgehobenen Elemente beschrieben:

   - **Multimedia**: Der Pfad der im Thema verwendeten Bilder wird zusammen mit der UUID angezeigt. Wenn Sie den Bildpfad auswählen, wird das entsprechende Bild in einem Popup-Fenster geöffnet. Beschädigte Bildverknüpfungen werden rot angezeigt.

   - **Inhaltsreferenzen**: Der Pfad des im Thema referenzierten Inhalts wird zusammen mit der UUID angezeigt. Wenn Sie den Titel des referenzierten Inhalts auswählen, wird das entsprechende Thema im Vorschaumodus geöffnet.

   - **Querverweis**: Der Pfad des referenzierten Inhalts wird zusammen mit der UUID angezeigt. Wenn Sie den Titel des referenzierten Inhalts auswählen, wird das entsprechende Thema im Vorschaumodus geöffnet. Unterbrochene Querverweise werden rot angezeigt.

   - **Überprüfen**: Zeigt den Status der Prüfungsaufgabe des Themas an. Sie können den Status \(Öffnen oder Schließen\), das Fälligkeitsdatum und den Verantwortlichen für das zu überprüfende Thema anzeigen. Wenn Sie auf den Themen-Link klicken, wird das Thema im Prüfungsmodus geöffnet.

   - **Verwendet in**: Zeigt eine Liste anderer Themen oder Karten an, in denen das Thema verwendet wird. Die UUID aller dieser Themen und Karten wird ebenfalls aufgelistet.

Neben dem Bericht für jedes einzelne Thema haben Admins auch Zugriff auf Informationen wie den Veröffentlichungsverlauf einer DITA-Karte. Weitere Informationen zum Verlauf der generierten Ausgaben finden Sie im Abschnitt [Anzeigen des Status ](generate-output-for-a-dita-map.md#viewing_output_history) Ausgabenerstellungsaufgabe .

## CSV-Datei des DITA-Zuordnungsberichts erstellen

Sie können die CSV-Datei eines DITA-Zuordnungsberichts herunterladen und exportieren. Die CSV-Datei enthält den detaillierten DITA-Zuordnungsbericht.

Führen Sie die folgenden Schritte aus, um die CSV-Datei eines DITA-Zuordnungsberichts zu generieren:

1. Wählen **oben** die Option „Bericht generieren“ aus, um den DITA-Zuordnungsbericht zu generieren.

   ![](images/generate-DITA-map-report-new.png){align="left"}

1. Sie erhalten eine Benachrichtigung, sobald der Bericht zum Herunterladen bereit ist. Wählen Sie **Herunterladen**, um die CSV-Datei des generierten Berichts herunterzuladen.

   ![](images/download-report-dialog-new.png){width="550" align="left"}


   Sie können die CSV-Datei des generierten Berichts auch später aus dem Experience Manager-Benachrichtigungs-Posteingang herunterladen.

   Wählen Sie den generierten Bericht im Posteingang aus, um den Bericht herunterzuladen.

   ![](images/report-inbox--notification.png){width="300" align="left"}

Sobald der Bericht in den Posteingang heruntergeladen wurde, können Sie auch den Bericht auswählen und das Symbol Öffnen oben verwenden, um den ausgewählten Bericht zu öffnen.

**Übergeordnetes Thema:**[ Einführung in Berichte](reports-intro.md)
