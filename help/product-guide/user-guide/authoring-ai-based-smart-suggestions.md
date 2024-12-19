---
title: KI-gestützte Smart Suggestions zum Erstellen von Inhalten
description: Erfahren Sie, wie Sie KI-gestützte Smart-Vorschläge im Web-Editor anzeigen und verwenden können.
exl-id: 23c5285e-0d4f-484a-a062-fe1ba1608b8d
source-git-commit: 6cf65f70252e133cf8977ce925f0a103dc79c0ec
workflow-type: tm+mt
source-wordcount: '684'
ht-degree: 0%

---

# KI-gestützte intelligente Vorschläge zum Erstellen von Inhalten

Experience Manager Guides bietet die intelligenten Vorschläge, mit denen Sie konsistente und genaue Inhalte erstellen können.

Während Sie Inhalte erstellen, kann die Funktion **Wiederverwendbare Inhalte vorschlagen** im Tool KI-Assistent mithilfe von KI suchen und die vorhandenen Inhalte anzeigen, die Ihren Inhalten semantisch ähnlich sind. Anschließend können Sie den am besten übereinstimmenden Inhalt auswählen, den Sie in Ihr aktuelles Thema als Referenz aufnehmen möchten.

Auf diese Weise können Sie vorhandene Inhalte aus Ihrem Dokumentations-Repository wiederverwenden und konsistente Inhalte erstellen. Sie erstellen beispielsweise ein Dokument, das Informationen zu **Adobe Firefly** enthält, einschließlich eines Absatzes über **Adobe**. In diesem Fall können Sie den Inhaltsverweis schnell aus einem anderen Thema anzeigen und hinzufügen, z. B. **Adobe Photoshop**, das denselben Absatz enthält.
>[!NOTE]
>
> In den [globalen Profilen oder Profilen auf Ordnerebene](../cs-install-guide/conf-folder-level.md#conf-ai-smart-suggestions) muss Ihr Administrator die Dateien oder Ordner definieren, die für Smart-Vorschläge indiziert werden sollen, die Mindestanzahl von Zeichen, die Sie eingeben müssen, um die Vorschläge anzuzeigen, und die maximale Anzahl von Vorschlägen, die Sie in der Liste anzeigen können.

Führen Sie die folgenden Schritte aus, um die intelligenten Vorschläge zum Hinzufügen geeigneter Inhaltsreferenzen zu Ihrem Thema anzuzeigen:


1. Wählen Sie den Inhalt in Ihrem Thema aus, um die entsprechenden Vorschläge anzuzeigen. Stellen Sie sicher, dass die Zeichenlänge des Inhalts den Wert überschreitet, den Ihr Administrator im Ordnerprofil festgelegt hat, damit die Inhaltsvorschläge angezeigt werden.
1. Wählen Sie im Bedienfeld des KI-Assistenten die Option **Wiederverwendbaren Inhalt vorschlagen** ![Symbol für wiederverwendbaren Inhalt vorschlagen ](./images/ai-suggest-reusable-content-icon.svg).

1. Wählen Sie ein Tag aus, um die Authoring-Vorschläge für das aktuelle Tag anzuzeigen.  Die Vorschläge zum Anzeigen und Hinzufügen von Inhaltsreferenzen aus den indizierten Dateien werden basierend auf dem Inhalt des aktuellen Tags angezeigt. Sie können auch mehrere Tags auswählen.


1. Wählen Sie alle Tags aus, um die Vorschläge basierend auf dem Inhalt des vollständigen Dokuments anzuzeigen.  Das Symbol **Wiederverwendbaren Inhalt vorschlagen** ![ai schlägt wiederverwendbaren Inhalt vor](./images/ai-suggest-reusable-content-icon.svg) wird neben dem Inhalt angezeigt, für den eine geeignete Übereinstimmung gefunden wurde.



   >[!NOTE]
   >
   > Sie können nur die Vorschläge für das aktuelle Darstellungsfeld (den auf dem Bildschirm sichtbaren Inhalt) anzeigen. Um Vorschläge für andere Inhalte im Dokument anzuzeigen, scrollen Sie nach oben oder unten, um sie im Ansichtsfenster anzuzeigen, und wählen Sie dann **Wiederverwendbaren Inhalt vorschlagen** ![ai Symbol für wiederverwendbaren Inhalt vorschlagen ](./images/ai-suggest-reusable-content-icon.svg).


1. Sie können die Smart-Vorschläge im Bedienfeld Vorschläge anzeigen.  Experience Manager Guides bietet Inhaltsvorschläge, die kontextuell ähnlich sind oder die gleiche Bedeutung haben. Sie können beispielsweise nach dem Thema suchen, das die genaue Versionsnummer enthält, z. B. „Version 2023.03.12“. Sie können auch nach &quot;Adobe hat seinen Hauptsitz in San Jose, Kalifornien“ suchen und ähnliche Inhalte finden wie „San Jose hat die Quartale vieler Software-Unternehmen wie Adobe.“
1. Wählen Sie **Inhaltsinformationen** ![Inhaltsinformationen](images/smart-suggestions-content-info-icon.svg) aus, um die Details anzuzeigen.

   ![Bedienfeld „Inhaltsinformationen“](images/smart-suggestions-content-information.png){width="300" align="left"}

   *Anzeigen der detaillierten Informationen zur Inhaltsreferenz.*

   1. Der Titel des Themas, das die Inhaltsreferenz enthält, wird als Hyperlink angezeigt.
   1. Der Pfad der Datei, die die Inhaltsreferenz enthält.
   1. Der Referenztyp, auf den der Inhalt verweist.
   1. Die Namen der DITA-Dateien, auf die das Thema verweist, werden als Hyperlinks angezeigt.
1. Wählen Sie **Vorschau** ![Vorschausymbol](./images/expand-icon.svg) aus, um den aktuellen Inhalt mit dem vorgeschlagenen Inhalt zu vergleichen. Auf diese Weise können Sie die Unterschiede vergleichen und bestimmen, ob Sie die Inhaltsreferenz für den vorgeschlagenen Inhalt hinzufügen und konsistent machen oder Ihren aktuellen Inhalt beibehalten möchten.

   ![Vorschlagen einer wiederverwendbaren Inhaltsvorschau](images/ai-assistant-suggest-reusable-content.png)

   *Vorschau des Vergleichs zwischen dem aktuellen Inhalt und den vorgeschlagenen Inhalten.*

1. Klicken Sie **Akzeptieren**, um die vorgeschlagene Inhaltsreferenz in der Vorschau **Wiederverwendbaren Inhalt vorschlagen** hinzuzufügen.
1. Sie können für die entsprechenden Empfehlungen auch **Akzeptieren** oder **Verwerfen** im Bedienfeld „Vorschläge“ auswählen.


Diese intelligente Funktion ist praktisch und minimiert den Aufwand für die manuelle Inhaltssuche, sodass Sie sich mehr auf die Erstellung neuer Inhalte konzentrieren können. Dies erleichtert auch eine bessere Zusammenarbeit im Team und hilft bei der Beibehaltung der Konsistenz der von verschiedenen Autoren erstellten Inhalte.

>[!NOTE]
>
>Intelligente Vorschläge bewahren Ihre Daten nicht über die aktuelle Sitzung hinaus auf. Smart-Vorschläge basieren bei Antworten ausschließlich auf dem Index, der für den Inhalt erstellt wurde, der sich in Ihrer internen Datenbank befindet. Es werden keine externen KI-Tools verwendet, um sicherzustellen, dass Ihre Daten im System bleiben.
