---
title: KI-gestützte intelligente Vorschläge zum Erstellen von Inhalten
description: Erfahren Sie, wie Sie KI-gestützte intelligente Vorschläge im Web-Editor anzeigen und nutzen können.
source-git-commit: 76c731c6a0e496b5b1237b9b9fb84adda8fa8a92
workflow-type: tm+mt
source-wordcount: '789'
ht-degree: 0%

---

# KI-gestützte intelligente Vorschläge zum Erstellen von Inhalten

Experience Manager Guides bietet die Funktion **Smart Suggestions** , mit der Sie konsistente und genaue Inhalte erstellen können.

Während Sie Inhalte erstellen, kann die Funktion **Smart Suggestions** mit AI suchen und vorhandenen Inhalt anzeigen, der semantisch Ihrem Inhalt ähnlich ist. Sie können dann den am besten passenden Inhalt auswählen, den Sie in Ihr aktuelles Thema aufnehmen möchten.

Auf diese Weise können Sie vorhandenen Inhalt aus Ihrem Dokumentations-Repository wiederverwenden und konsistente Inhalte erstellen. Sie erstellen beispielsweise ein Dokument mit Informationen zu **Adobe Firefly**, einschließlich eines Absatzes über **Adobe**. In diesem Fall können Sie den Inhaltsverweis schnell von einem anderen Thema wie **Adobe Photoshop** anzeigen und hinzufügen, das denselben Absatz enthält.





Wenn Sie ein Thema im Web Editor öffnen, wird rechts das Bedienfeld **Smart-Vorschläge** angezeigt.

>[!NOTE]
>
> Ihr Administrator muss die Funktion **Smart Suggestions** konfigurieren. Weitere Informationen finden Sie im Abschnitt [KI-gestützte intelligente Vorschläge für die Bearbeitung konfigurieren](/help/product-guide/cs-install-guide/conf-smart-suggestions.md) im Installations- und Konfigurationshandbuch für Cloud Service.

![Bedienfeld mit intelligenten Vorschlägen](images/smart-suggestions-panel.png){width="300" align="left"}

*Zeigen Sie das Bedienfeld **Smart Suggestions**an.*

Führen Sie die folgenden Schritte aus, um die intelligenten Vorschläge zum Hinzufügen entsprechender Inhaltsreferenzen zu Ihrem Thema anzuzeigen:

1. Wählen Sie das Symbol **Smart Suggestions** ![Smart-Vorschläge](images/smart-suggestions-icon.svg) aus, um das Bedienfeld zu öffnen.



   >[!NOTE]
   >
   > In den Profilen [global oder auf Ordnerebene](/help/product-guide/cs-install-guide/conf-folder-level.md#conf-ai-smart-suggestions) muss Ihr Administrator die Dateien oder Ordner definieren, die für intelligente Vorschläge indiziert werden sollen, die Mindestanzahl der Zeichen, die Sie eingeben müssen, um die Vorschläge anzuzeigen, und die maximale Anzahl an Vorschlägen, die Sie in der Liste anzeigen können.

1. Geben Sie den Inhalt in Ihr Thema ein, um die entsprechenden Vorschläge anzuzeigen. Stellen Sie sicher, dass die Zeichenlänge des Inhalts die vom Administrator im Ordnerprofil festgelegte Länge überschreitet, damit die Inhaltsvorschläge angezeigt werden.

1. Wählen Sie **Vorschläge für das aktuelle Tag** ![Smartempfehlungen für das aktuelle Tag-Symbol](images/smart-suggestions-current-tag-icon.svg) aus, um die Bearbeitungsvorschläge für das aktuelle Tag anzuzeigen, in dem Sie den Mauszeiger platzieren.  Die Vorschläge zum Anzeigen und Hinzufügen von Inhaltsverweisen aus den indizierten Dateien werden basierend auf dem Inhalt im aktuellen Tag angezeigt.

   Tastaturbefehl: **Windows** (*Strg* + *K*), **macOS** (*Befehl* + *K*)
1. Wählen Sie das Symbol **Vorschläge für das vollständige Dokument** ![Smart-Vorschläge-Gesamtdokument](images/smart-suggestions-complete-document-icon.svg) aus, um die Vorschläge basierend auf dem Inhalt im vollständigen Dokument anzuzeigen.  Neben dem Inhalt, bei dem eine geeignete Übereinstimmung gefunden wird, wird das Symbol für intelligente Vorschläge![Symbol für intelligente Vorschläge](images/smart-suggestions-complete-document-icon.svg) angezeigt.

   Tastaturbefehl: **Windows** ( *Strg* + *Umschalt* + *K* ), **macOS** (*Befehl* + *Umschalt* + *K* )

   >[!NOTE]
   >
   > Sie können nur die Vorschläge für den aktuellen Viewport (den auf dem Bildschirm sichtbaren Inhalt) anzeigen. Um Vorschläge für andere Inhalte im Dokument anzuzeigen, scrollen Sie nach oben oder unten, um sie im Viewport anzuzeigen, und wählen Sie dann das Symbol ![Smart-Vorschläge-Symbol](images/smart-suggestions-complete-document-icon.svg) aus.

1. Wählen Sie das Symbol **Smart-Empfehlungen** ![Smart-Vorschläge-Symbol](images/smart-suggestions-complete-document-icon.svg) neben den Tags aus, die Sie Ihrem Dokument hinzugefügt haben, um die intelligenten Vorschläge anzuzeigen.
1. Sie können die intelligenten Vorschläge im Feld &quot;**Wiederverwendung von Inhalten**&quot; anzeigen.  Experience Manager Guides bietet Vorschläge für die exakte Übereinstimmung von Inhalten und Inhalten mit der gleichen Bedeutung. Sie können beispielsweise nach dem Thema suchen, das die exakte Versionsnummer enthält, z. B. &quot;Release version 2023.03.12&quot;. Sie können auch nach &quot;Adobe mit Hauptsitz in San Jose, Kalifornien&quot;suchen und ähnliche Inhalte wie &quot;San Jose hat die Quartale vieler Softwareunternehmen wie Adobe&quot; finden.
1. Wählen Sie **Inhaltsinformationen** ![Inhaltsinformationen](images/smart-suggestions-content-info-icon.svg) aus, um die Details anzuzeigen.
   ![Informationsbereich für Inhalte](images/smart-suggestions-content-information.png){width="300" align="left"}

   *Zeigen Sie die detaillierten Informationen zum Inhaltsverweis an.*

   1. Der Titel des Themas, das die Inhaltsreferenz enthält, wird als Hyperlink angezeigt.
   1. Der Pfad der Datei, die den Inhaltsverweis enthält.
   1. Die Art der Referenz, auf die der Inhalt verwiesen wird.
   1. Die Namen der DITA-Dateien, auf die das Thema verwiesen wird, werden als Hyperlinks angezeigt.
1. Wählen Sie das Symbol **Vorschau für empfohlene Inhalte** ![Vorschausymbol für intelligente Vorschläge](images/smart-suggestions-preview-icon.svg) , um den aktuellen Inhalt mit dem vorgeschlagenen Inhalt zu vergleichen. Auf diese Weise können Sie die Unterschiede vergleichen und feststellen, ob Sie den Inhaltsverweis für den vorgeschlagenen Inhalt hinzufügen und ihn konsistent machen oder Ihren aktuellen Inhalt beibehalten möchten.

   ![Vorschau für vorgeschlagenen Inhalt](images/smart-suggestions-suggested-content-preview.png){width="800" align="left"}

   *Sehen Sie sich den Vergleich zwischen dem aktuellen Inhalt und dem vorgeschlagenen Inhalt in der Vorschau an.*

1. Klicken Sie auf **Akzeptieren** , um die vorgeschlagene Inhaltsreferenz im Dialogfeld **Vorschau für empfohlene Inhalte** hinzuzufügen.
1. Sie können auch **Accept** oder **Decline** im Feld **Inhaltswiederverwendung** für die entsprechenden Empfehlungen auswählen.


Diese intelligente Funktion ist praktisch und minimiert den Aufwand für die manuelle Inhaltssuche, sodass Sie sich mehr auf die Erstellung neuer Inhalte konzentrieren können. Außerdem wird eine bessere Teamzusammenarbeit ermöglicht und die Konsistenz der von verschiedenen Autoren erstellten Inhalte wird gewahrt.

>[!NOTE]
>
>Intelligente Vorschläge behalten Ihre Daten nicht über die aktuelle Sitzung hinaus bei. Bei Antworten basieren intelligente Vorschläge ausschließlich auf dem Index, der für den in Ihrer internen Datenbank enthaltenen Inhalt erstellt wurde. Externe KI-Tools werden nicht verwendet, um sicherzustellen, dass Ihre Daten im System verbleiben.
