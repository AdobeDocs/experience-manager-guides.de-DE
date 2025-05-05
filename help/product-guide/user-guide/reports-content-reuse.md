---
title: Bericht zur Wiederverwendung von Inhalt
description: Erfahren Sie, wie Sie den Bericht zur Wiederverwendung von Inhalten in AEM Guides anzeigen. Erstellen Sie den Bericht, um den Prozentsatz der Wiederverwendung des Inhalts zu ermitteln.
exl-id: ccae4303-75b1-4077-829a-7ef6a14fd8ad
feature: Report Generation
role: User
source-git-commit: ac83f613d87547fc7f6a18070545e40ad4963616
workflow-type: tm+mt
source-wordcount: '422'
ht-degree: 0%

---

# Bericht zur Wiederverwendung von Inhalt {#id205BB900OQD}

Ein weiterer nützlicher Bericht, den Sie generieren können, ist der Bericht zur Wiederverwendung von Inhalten. Dieser Bericht berechnet den durchschnittlichen Prozentsatz der Inhaltsnutzung, was für Projekt-Manager und Geschäftsinhaber sehr nützlich ist, um die Menge der wiederverwendeten Inhalte anzuzeigen.

>[!TIP]
>
> Um das ordnungsgemäße Funktionieren des Berichts zur Wiederverwendung von Inhalten sicherzustellen, müssen Sie den Nachbearbeitungs-Workflow aktivieren. Wenden Sie sich an Ihren Systemadministrator, um Nachbearbeitungs-Workflows zu aktivieren.

Führen Sie die folgenden Schritte aus, um den Bericht zur Wiederverwendung von Inhalten anzuzeigen:

1. Klicken Sie oben auf das Adobe Experience Manager-Logo und anschließend auf **Tools**.

1. Wählen Sie **Guides** aus der Liste der Tools aus.

1. Wählen Sie die **Bericht zur Wiederverwendung von Inhalten** aus.

1. Wählen Sie **Durchsuchen**, um einen Pfad auszuwählen, in dem sich Ihre Themen befinden, oder geben Sie den Pfad manuell ein.

   Der Bericht wird durch Überprüfen des Inhalts in den übergeordneten und allen untergeordneten Ordnern erstellt.

1. Wählen Sie **Bericht generieren**, um den Bericht zur Wiederverwendung von Inhalten abzurufen.

   ![](images/content-reuse-uuid.png){align="left"}

   Die Berichtseite ist in zwei Teile unterteilt:

   - **Berichtszusammenfassung:**

     Listet die durchschnittliche Wiederverwendung von Inhalten auf, die als Instanzen der Inhaltswiederverwendung/Gesamtzahl der Themen berechnet wird. Dieser Bericht berücksichtigt alle direkten Inhaltsreferenzen und Themenreferenzen der ersten Ebene für die Berechnung. Die Instanzen zur Wiederverwendung von Inhalten werden als Summe der Werte im Feld Anzahl der Wiederverwendungen berechnet. Das Thema, das am häufigsten wiederverwendet wird, wird auch in der Zusammenfassung des Berichts aufgeführt. Wenn Sie den Link des Themas im am häufigsten wiederverwendeten Thema auswählen, wird die Vorschau des Themas geöffnet.

   - **Details:**

     Der Abschnitt Details enthält die folgenden Spalten:

      - **Titel**: Der Titel des Themas. Wenn Sie den Link Titel des Themas auswählen, wird die Themenvorschau geöffnet.

      - **UUID**: Die universell eindeutige Kennung \(UUID\) der Datei.

      - **size**: Dateigröße in Byte.

      - **Status**: Der aktuelle Status des Dokuments - Entwurf, In Überprüfung oder Überarbeitet.

      - **Häufigkeit der Wiederverwendung**: Gibt an, wie oft das entsprechende Thema wiederverwendet wurde. Dies wird als Summe der Einträge in den Spalten „Referenziert von“ minus 1 berechnet.

      - **Referenziert von**: Die Themen, in denen das entsprechende Thema referenziert wurde. Hier werden nur die direkten \(first level\)-Verweise berücksichtigt. Mehrere Themen werden durch Kommas getrennt. Die UUID der referenzierten Datei wird auch in Klammern aufgeführt. Wenn Sie auf den Titel-Link des Themas klicken, wird die Themenvorschau geöffnet.


>[!NOTE]
>
> Sie können auch den Bericht zur Wiederverwendung von Inhalten im CSV-Format exportieren. Klicken Sie dazu in der linken oberen Ecke des Bildschirms auf In CSV exportieren und wählen Sie einen Speicherort für die CSV-Datei aus. Sie können diese CSV-Datei dann in einem beliebigen CSV-Editor öffnen.

**Übergeordnetes Thema:**&#x200B;[ Einführung in Berichte](reports-intro.md)
