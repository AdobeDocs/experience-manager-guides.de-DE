---
title: KI-gestützte Smart Suggestions zum Erstellen von Inhalten
description: Erfahren Sie, wie Sie KI-gestützte Smart-Vorschläge im Web-Editor anzeigen und verwenden können.
hide: true
exl-id: 30c85d46-61ba-486c-979c-1a2ed95f5a32
source-git-commit: a70b3ce942b3e69445ad1d7ba6c8f7542e0ff176
workflow-type: tm+mt
source-wordcount: '687'
ht-degree: 0%

---

# KI-gestützte intelligente Vorschläge zum Erstellen von Inhalten

Experience Manager Guides bietet die intelligenten Vorschläge, mit denen Sie konsistente und genaue Inhalte erstellen können.

Während Sie Inhalte erstellen, kann die Funktion **Wiederverwendbare Inhalte vorschlagen** im Tool KI-Assistent mithilfe von KI suchen und die vorhandenen Inhalte anzeigen, die Ihren Inhalten semantisch ähnlich sind. Anschließend können Sie den am besten übereinstimmenden Inhalt auswählen, den Sie in Ihr aktuelles Thema als Referenz aufnehmen möchten.

Auf diese Weise können Sie vorhandene Inhalte aus Ihrem Dokumentations-Repository wiederverwenden und konsistente Inhalte erstellen. Sie erstellen beispielsweise ein Dokument, das Informationen zu **Adobe Firefly** enthält, einschließlich eines Absatzes zu **Adobe**. In diesem Fall können Sie den Inhaltsverweis schnell aus einem anderen Thema anzeigen und hinzufügen, z. B. **Adobe Photoshop**, das denselben Absatz enthält.
>[!NOTE]
>
> In den [globalen Profilen oder Profilen auf Ordnerebene](/help/product-guide/cs-install-guide/conf-folder-level.md#conf-ai-smart-suggestions) muss Ihr Administrator die Dateien oder Ordner definieren, die für Smart-Vorschläge indiziert werden sollen, die Mindestanzahl von Zeichen, die Sie eingeben müssen, um die Vorschläge anzuzeigen, und die maximale Anzahl von Vorschlägen, die Sie in der Liste anzeigen können.

Führen Sie die folgenden Schritte aus, um die intelligenten Vorschläge zum Hinzufügen geeigneter Inhaltsreferenzen zu Ihrem Thema anzuzeigen:


1. Wählen Sie den Inhalt in Ihrem Thema aus, um die entsprechenden Vorschläge anzuzeigen. Stellen Sie sicher, dass die Zeichenlänge des Inhalts den Wert überschreitet, den Ihr Administrator im Ordnerprofil festgelegt hat, damit die Inhaltsvorschläge angezeigt werden.
1. Wählen Sie im Bedienfeld des KI-Assistenten die Option **Wiederverwendbaren Inhalt vorschlagen** ![Symbol für wiederverwendbaren Inhalt vorschlagen &#x200B;](./images/ai-suggest-reusable-content-icon.svg).

1. Wählen Sie ein Tag aus, um die Authoring-Vorschläge für das aktuelle Tag anzuzeigen.  Die Vorschläge zum Anzeigen und Hinzufügen von Inhaltsreferenzen aus den indizierten Dateien werden basierend auf dem Inhalt des aktuellen Tags angezeigt. Sie können auch mehrere Tags auswählen.


1. Wählen Sie alle Tags aus, um die Vorschläge basierend auf dem Inhalt des vollständigen Dokuments anzuzeigen.  Das Symbol **Wiederverwendbaren Inhalt vorschlagen** ![ai schlägt wiederverwendbaren Inhalt vor](./images/ai-suggest-reusable-content-icon.svg) wird neben dem Inhalt angezeigt, für den eine geeignete Übereinstimmung gefunden wurde.



   >[!NOTE]
   >
   > Sie können nur die Vorschläge für das aktuelle Darstellungsfeld (den auf dem Bildschirm sichtbaren Inhalt) anzeigen. Um Vorschläge für andere Inhalte im Dokument anzuzeigen, scrollen Sie nach oben oder unten, um sie im Ansichtsfenster anzuzeigen, und wählen Sie dann **Wiederverwendbaren Inhalt vorschlagen** ![ai Symbol für wiederverwendbaren Inhalt vorschlagen &#x200B;](./images/ai-suggest-reusable-content-icon.svg).


1. Sie können die Smart-Vorschläge im Bedienfeld Vorschläge anzeigen.  Experience Manager Guides bietet Inhaltsvorschläge, die kontextuell ähnlich sind oder die gleiche Bedeutung haben. Sie können beispielsweise nach dem Thema suchen, das die genaue Versionsnummer enthält, z. B. „Version 2023.03.12“. Sie können auch nach &quot;Adobe hat seinen Hauptsitz in San Jose, Kalifornien“ suchen und ähnliche Inhalte finden wie „San Jose hat die Quartiere von vielen Softwareunternehmen wie Adobe&quot;.
1. Select **Content Information** ![Content Information](images/smart-suggestions-content-info-icon.svg) to view the details.

   ![Content information panel](images/smart-suggestions-content-information.png){width="300" align="left"}

   *View the detailed information about the content reference.*

   1. The title of the topic that contains the content reference is displayed as a hyperlink.
   1. The path of the file that contains the content reference.
   1. The type of reference where the content is referred.
   1. The names of DITA files where the topic is referred to are displayed as hyperlinks.
1. Select **Preview** ![preview icon](./images/expand-icon.svg) to compare the current content with the suggested content. This helps you compare the differences and determine if you want to add the content reference for the suggested content and make it consistent or retain your current content.

   ![Suggest reusable content preview](images/ai-assistant-suggest-reusable-content.png)

   *Preview the comparison between the current content and the suggested content.*

1. Click **Accept** to add the suggested content reference in the **Suggest reusable content** preview.
1. You can also select **Accept** or **Dismiss** in the suggestions panel for the appropriate recommendations.


This intelligent feature is handy and minimizes the effort of manual content searching, allowing you to concentrate more on generating new content. It also facilitates better team collaboration and helps maintain consistency in the content created by various authors.

>[!NOTE]
>
>Smart suggestions don&#39;t retain your data beyond the current session. For responses, smart suggestions rely solely upon the index created on the content residing within your internal database. External AI tools are not used, ensuring your data remains within the system.
