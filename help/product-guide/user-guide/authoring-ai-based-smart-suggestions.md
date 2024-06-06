---
title: KI-gestützte intelligente Vorschläge zum Erstellen von Inhalten
description: Erfahren Sie, wie Sie KI-gestützte intelligente Vorschläge im Web-Editor anzeigen und nutzen können.
exl-id: 23c5285e-0d4f-484a-a062-fe1ba1608b8d
source-git-commit: 75425d82ee55485503ea6678030c5e919e50a691
workflow-type: tm+mt
source-wordcount: '789'
ht-degree: 0%

---

# KI-gestützte intelligente Vorschläge zum Erstellen von Inhalten

Experience Manager-Handbücher bieten die **Smart-Empfehlungen** -Funktion, mit der Sie konsistente und genaue Inhalte erstellen können.

Während Sie Inhalte erstellen, wird die **Smart-Empfehlungen** -Funktion kann mit AI suchen und den vorhandenen Inhalt anzeigen, der semantisch Ihrem Inhalt ähnlich ist. Sie können dann den am besten passenden Inhalt auswählen, den Sie in Ihr aktuelles Thema aufnehmen möchten.

Auf diese Weise können Sie vorhandenen Inhalt aus Ihrem Dokumentations-Repository wiederverwenden und konsistente Inhalte erstellen. Sie erstellen beispielsweise ein Dokument mit Informationen zu **Adobe Firefly**, einschließlich eines Absatzes zu **Adobe**. In diesem Fall können Sie die Inhaltsreferenz schnell über ein anderes Thema anzeigen und hinzufügen, z. B. **Adobe Photoshop**, der denselben Absatz enthält.





Wenn Sie ein Thema im Web Editor öffnen, wird die **Smart-Empfehlungen** wird rechts angezeigt.

>[!NOTE]
>
> Ihr Administrator muss die **Smart-Empfehlungen** Funktion. Weitere Informationen finden Sie unter [KI-gestützte intelligente Vorschläge für das Authoring konfigurieren](../cs-install-guide/conf-smart-suggestions.md) im Installations- und Konfigurationshandbuch für Cloud Service.

![Smart-Empfehlungs-Bedienfeld](images/smart-suggestions-panel.png){width="300" align="left"}

*Anzeigen der **Smart-Empfehlungen**Bedienfeld.*

Führen Sie die folgenden Schritte aus, um die intelligenten Vorschläge zum Hinzufügen entsprechender Inhaltsreferenzen zu Ihrem Thema anzuzeigen:

1. Auswählen **Smart-Empfehlungen** ![Symbol für intelligente Vorschläge](images/smart-suggestions-icon.svg) , um das Bedienfeld zu öffnen.



   >[!NOTE]
   >
   > Im [globale Profile oder Profile auf Ordnerebene](../cs-install-guide/conf-folder-level.md#conf-ai-smart-suggestions)muss Ihr Administrator die Dateien oder Ordner definieren, die für intelligente Vorschläge indexiert werden sollen, die Mindestanzahl der Zeichen, die Sie eingeben müssen, um die Vorschläge anzuzeigen, und die maximale Anzahl an Vorschlägen, die Sie in der Liste anzeigen können.

1. Geben Sie den Inhalt in Ihr Thema ein, um die entsprechenden Vorschläge anzuzeigen. Stellen Sie sicher, dass die Zeichenlänge des Inhalts die vom Administrator im Ordnerprofil festgelegte Länge überschreitet, damit die Inhaltsvorschläge angezeigt werden.

1. Auswählen **Vorschläge für das aktuelle Tag** ![Symbol für intelligente Vorschläge für aktuelles Tag](images/smart-suggestions-current-tag-icon.svg) um die Bearbeitungsvorschläge für das aktuelle Tag anzuzeigen, in dem Sie den Mauszeiger platzieren.  Die Vorschläge zum Anzeigen und Hinzufügen von Inhaltsverweisen aus den indizierten Dateien werden basierend auf dem Inhalt im aktuellen Tag angezeigt.

   Tastaturbefehl: **Windows** (*Strg* + *K*),  **macOS** (*Befehl* + *K*)
1. Auswählen **Vorschläge für das vollständige Dokument**  ![Symbol &quot;intelligente Vorschläge für vollständige Dokumente&quot;](images/smart-suggestions-complete-document-icon.svg) um die Vorschläge auf der Grundlage des Inhalts des vollständigen Dokuments anzuzeigen.  Die intelligenten Vorschläge![Symbol für intelligente Vorschläge](images/smart-suggestions-complete-document-icon.svg) neben dem Inhalt angezeigt wird, bei dem eine passende Übereinstimmung gefunden wurde.

   Tastaturbefehl: **Windows** ( *Strg* + *Umschalt* +  *K* ),  **macOS** (*Befehl* + *Umschalt* + *K* )

   >[!NOTE]
   >
   > Sie können nur die Vorschläge für den aktuellen Viewport (den auf dem Bildschirm sichtbaren Inhalt) anzeigen. Um Vorschläge für andere Inhalte im Dokument anzuzeigen, scrollen Sie nach oben oder unten, um sie im Viewport anzuzeigen, und wählen Sie dann die ![Symbol für intelligente Vorschläge](images/smart-suggestions-complete-document-icon.svg) Symbol .

1. Wählen Sie die **Smart-Empfehlungen** ![Symbol für intelligente Vorschläge](images/smart-suggestions-complete-document-icon.svg) -Symbol neben den Tags, die Sie zum Dokument hinzugefügt haben, um die intelligenten Vorschläge anzuzeigen.
1. Sie können die intelligenten Vorschläge im **Inhaltswiederverwendung** Vorschläge.  Experience Manager-Handbücher enthalten Vorschläge für die exakte Übereinstimmung von Inhalten und Inhalten mit derselben Bedeutung. Sie können beispielsweise nach dem Thema suchen, das die exakte Versionsnummer enthält, z. B. &quot;Release version 2023.03.12&quot;. Sie können auch nach &quot;Adobe mit Hauptsitz in San Jose, Kalifornien&quot;suchen und ähnliche Inhalte wie &quot;San Jose hat die Quartale vieler Softwareunternehmen wie Adobe&quot; finden.
1. Auswählen **Inhaltsinformationen** ![Inhaltsinformationen](images/smart-suggestions-content-info-icon.svg) um die Details anzuzeigen.
   ![Inhaltsinformationsbereich](images/smart-suggestions-content-information.png){width="300" align="left"}

   *Zeigen Sie detaillierte Informationen zum Inhaltsverweis an.*

   1. Der Titel des Themas, das die Inhaltsreferenz enthält, wird als Hyperlink angezeigt.
   1. Der Pfad der Datei, die den Inhaltsverweis enthält.
   1. Die Art der Referenz, auf die der Inhalt verwiesen wird.
   1. Die Namen der DITA-Dateien, auf die das Thema verwiesen wird, werden als Hyperlinks angezeigt.
1. Auswählen **Vorschau des vorgeschlagenen Inhalts** ![Symbol für die Vorschau mit intelligenten Vorschlägen](images/smart-suggestions-preview-icon.svg) , um den aktuellen Inhalt mit dem vorgeschlagenen Inhalt zu vergleichen. Auf diese Weise können Sie die Unterschiede vergleichen und feststellen, ob Sie den Inhaltsverweis für den vorgeschlagenen Inhalt hinzufügen und ihn konsistent machen oder Ihren aktuellen Inhalt beibehalten möchten.

   ![Vorschau des vorgeschlagenen Inhalts](images/smart-suggestions-suggested-content-preview.png){width="800" align="left"}

   *Vorschau des Vergleichs zwischen dem aktuellen Inhalt und dem vorgeschlagenen Inhalt*

1. Klicks **Accept** , um die vorgeschlagene Inhaltsreferenz in der **Vorschau des vorgeschlagenen Inhalts** Dialogfeld.
1. Sie können auch **Accept** oder **Ablehnen** im **Inhaltswiederverwendung** Empfehlungen für die entsprechenden Empfehlungen.


Diese intelligente Funktion ist praktisch und minimiert den Aufwand für die manuelle Inhaltssuche, sodass Sie sich mehr auf die Erstellung neuer Inhalte konzentrieren können. Außerdem wird eine bessere Teamzusammenarbeit ermöglicht und die Konsistenz der von verschiedenen Autoren erstellten Inhalte wird gewahrt.

>[!NOTE]
>
>Intelligente Vorschläge behalten Ihre Daten nicht über die aktuelle Sitzung hinaus bei. Bei Antworten basieren intelligente Vorschläge ausschließlich auf dem Index, der für den in Ihrer internen Datenbank enthaltenen Inhalt erstellt wurde. Externe KI-Tools werden nicht verwendet, um sicherzustellen, dass Ihre Daten im System verbleiben.
