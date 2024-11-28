---
title: KI-gestützte intelligente Vorschläge zum Erstellen von Inhalten
description: Erfahren Sie, wie Sie KI-gestützte intelligente Vorschläge im Web Editor anzeigen und nutzen können.
source-git-commit: 324b9b1364c14117740a924e825395f7c9d5c424
workflow-type: tm+mt
source-wordcount: '684'
ht-degree: 0%

---

# KI-gestützte intelligente Vorschläge zum Erstellen von Inhalten

Experience Manager Guides bietet die intelligenten Vorschläge, mit denen Sie konsistente und genaue Inhalte erstellen können.

Während Sie Inhalte erstellen, kann die Funktion **Wiederverwendbaren Inhalt vorschlagen** im AI-Assistenten-Tool mit AI suchen und den vorhandenen Inhalt anzeigen, der semantisch Ihrem Inhalt ähnlich ist. Sie können dann den am besten passenden Inhalt auswählen, den Sie in Ihr aktuelles Thema aufnehmen möchten.

Auf diese Weise können Sie vorhandenen Inhalt aus Ihrem Dokumentations-Repository wiederverwenden und konsistente Inhalte erstellen. Sie erstellen beispielsweise ein Dokument mit Informationen zu **Adobe Firefly**, einschließlich eines Absatzes über **Adobe**. In diesem Fall können Sie den Inhaltsverweis schnell von einem anderen Thema wie **Adobe Photoshop** anzeigen und hinzufügen, das denselben Absatz enthält.
>[!NOTE]
>
> In den Profilen [global oder auf Ordnerebene](/help/product-guide/cs-install-guide/conf-folder-level.md#conf-ai-smart-suggestions) muss Ihr Administrator die Dateien oder Ordner definieren, die für intelligente Vorschläge indiziert werden sollen, die Mindestanzahl der Zeichen, die Sie eingeben müssen, um die Vorschläge anzuzeigen, und die maximale Anzahl an Vorschlägen, die Sie in der Liste anzeigen können.

Führen Sie die folgenden Schritte aus, um die intelligenten Vorschläge zum Hinzufügen entsprechender Inhaltsreferenzen zu Ihrem Thema anzuzeigen:


1. Wählen Sie den Inhalt in Ihrem Thema aus, um die entsprechenden Vorschläge anzuzeigen. Stellen Sie sicher, dass die Zeichenlänge des Inhalts die vom Administrator im Ordnerprofil festgelegte Länge überschreitet, damit die Inhaltsvorschläge angezeigt werden.
1. Wählen Sie im Bedienfeld &quot;KI-Assistent&quot;die Option **Vorschlagen wiederverwendbarer Inhalte** ![ai rät das Symbol für wiederverwendbaren Inhalt ](./images/ai-suggest-reusable-content-icon.svg) vor.

1. Wählen Sie ein Tag aus, um die Bearbeitungsvorschläge für das aktuelle Tag anzuzeigen.  Die Vorschläge zum Anzeigen und Hinzufügen von Inhaltsverweisen aus den indizierten Dateien werden basierend auf dem Inhalt im aktuellen Tag angezeigt. Sie können auch mehrere Tags auswählen.


1. Wählen Sie alle Tags aus, um die Vorschläge basierend auf dem Inhalt des vollständigen Dokuments anzuzeigen.  Das Symbol **Wiederverwendbaren Inhalt vorschlagen** ![ai schlägt vor, dass das Symbol für wiederverwendbaren Inhalt ](./images/ai-suggest-reusable-content-icon.svg) neben dem Inhalt angezeigt wird, bei dem eine passende Übereinstimmung gefunden wurde.



   >[!NOTE]
   >
   > Sie können nur die Vorschläge für den aktuellen Viewport (den auf dem Bildschirm sichtbaren Inhalt) anzeigen. Um Vorschläge für andere Inhalte im Dokument anzuzeigen, scrollen Sie nach oben oder unten, um sie im Viewport anzuzeigen, und wählen Sie dann **Wiederverwendbaren Inhalt vorschlagen** ![ai schlägt das Symbol für wiederverwendbaren Inhalt vor ](./images/ai-suggest-reusable-content-icon.svg).


1. Sie können die intelligenten Vorschläge im Bereich &quot;Vorschläge&quot;anzeigen.  Experience Manager Guides bietet Vorschläge für Inhalte, die kontextuell ähnlich sind oder dieselbe Bedeutung haben. Sie können beispielsweise nach dem Thema suchen, das die exakte Versionsnummer enthält, z. B. &quot;Release version 2023.03.12&quot;. Sie können auch nach &quot;Adobe mit Hauptsitz in San Jose, Kalifornien&quot;suchen und ähnliche Inhalte wie &quot;San Jose hat die Quartale vieler Softwareunternehmen wie Adobe&quot; finden.
1. Wählen Sie **Inhaltsinformationen** ![Inhaltsinformationen](images/smart-suggestions-content-info-icon.svg) aus, um die Details anzuzeigen.

   ![Informationsbereich für Inhalte](images/smart-suggestions-content-information.png){width="300" align="left"}

   *Zeigen Sie die detaillierten Informationen zum Inhaltsverweis an.*

   1. Der Titel des Themas, das die Inhaltsreferenz enthält, wird als Hyperlink angezeigt.
   1. Der Pfad der Datei, die den Inhaltsverweis enthält.
   1. Die Art der Referenz, auf die der Inhalt verwiesen wird.
   1. Die Namen der DITA-Dateien, auf die das Thema verwiesen wird, werden als Hyperlinks angezeigt.
1. Wählen Sie **Vorschau** ![Vorschausymbol](./images/expand-icon.svg) aus, um den aktuellen Inhalt mit dem vorgeschlagenen Inhalt zu vergleichen. Auf diese Weise können Sie die Unterschiede vergleichen und feststellen, ob Sie den Inhaltsverweis für den vorgeschlagenen Inhalt hinzufügen und ihn konsistent machen oder Ihren aktuellen Inhalt beibehalten möchten.

   ![Vorschlagen einer wiederverwendbaren Inhaltsvorschau](images/ai-assistant-suggest-reusable-content.png)

   *Sehen Sie sich den Vergleich zwischen dem aktuellen Inhalt und dem vorgeschlagenen Inhalt in der Vorschau an.*

1. Klicken Sie auf **Akzeptieren** , um die vorgeschlagene Inhaltsreferenz zur Vorschau von **Wiederverwendbaren Inhalt vorschlagen** hinzuzufügen.
1. Sie können auch **Akzeptieren** oder **Beenden** im Bereich &quot;Vorschläge&quot;für die entsprechenden Empfehlungen auswählen.


Diese intelligente Funktion ist praktisch und minimiert den Aufwand für die manuelle Inhaltssuche, sodass Sie sich mehr auf die Erstellung neuer Inhalte konzentrieren können. Außerdem wird eine bessere Teamzusammenarbeit ermöglicht und die Konsistenz der von verschiedenen Autoren erstellten Inhalte wird gewahrt.

>[!NOTE]
>
>Intelligente Vorschläge behalten Ihre Daten nicht über die aktuelle Sitzung hinaus bei. Bei Antworten basieren intelligente Vorschläge ausschließlich auf dem Index, der für den in Ihrer internen Datenbank enthaltenen Inhalt erstellt wurde. Externe KI-Tools werden nicht verwendet, um sicherzustellen, dass Ihre Daten im System verbleiben.
