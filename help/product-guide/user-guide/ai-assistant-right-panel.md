---
title: Verwenden des KI-Assistenten zur intelligenten Erstellung von Dokumenten "
description: Erfahren Sie, wie Sie mit dem KI-Assistenten Dokumente mit intelligenter Effizienz erstellen können.
exl-id: 47d37323-20bf-4444-a2c9-41c44b2c8daf
source-git-commit: 558cc1a724a483353eb5d912354e1ab37dab348a
workflow-type: tm+mt
source-wordcount: '1037'
ht-degree: 0%

---

# Intelligentes Erstellen von Dokumenten mit dem KI-Assistenten (Beta)

Adobe Experience Manager Guides bietet ein KI-Assistenten-Tool, mit dem Sie Ihre Inhaltserstellung intelligenter und schneller gestalten können. Zeigen Sie mit diesem Tool die intelligenten Vorschläge zur Wiederverwendung der Inhalte aus dem vorhandenen Inhalts-Repository an. Verwenden Sie die Textaufforderungsfunktion, um eine Eingabeaufforderung bereitzustellen und den Inhalt gemäß Ihren Anforderungen zu ändern. Verwenden Sie den KI-Assistenten, um einen Absatz intelligent in eine Liste zu konvertieren. Sie können für das aktuelle Thema eine kurze Beschreibung basierend auf dem ausgewählten Inhalt erstellen. Mit dieser Funktion können Sie auch die ausgewählten Inhalte einfach verbessern und übersetzen.

>[!NOTE]
>
> Diese Authoring-Funktion ist nur für DITA-Themen verfügbar und kann nur über die Editor-Oberfläche aufgerufen werden. Auf der Startseite und in der Kartenkonsole wird nur das Bedienfeld **Hilfe** angezeigt.

Nachdem Sie den Text in einem Thema ausgewählt haben, können Sie eine der KI-Assistentenaktionen ausführen:

![KI-Assistent](./images/ai-assistant-panel.png){width="300" align="left"}

## Wiederverwendbaren Inhalt vorschlagen


Verwenden Sie das Symbol **Wiederverwendbaren Inhalt vorschlagen** ![ai schlägt wiederverwendbare Inhalte vor](./images/ai-suggest-reusable-content-icon.svg) um Inhalte konsistent und präzise zu erstellen. Sie können den Inhalt auswählen. Experience Manager Guides bietet Vorschläge dazu, wie der vorhandene Inhalt in Ihrem Repository wiederverwendet werden kann.
Erfahren Sie mehr über die Verwendung von [KI-gestützten Smart-Vorschlägen zum Erstellen von Inhalten](authoring-ai-based-smart-suggestions.md).


## Textaufforderung verwenden

Eine Textaufforderung ist eine Anweisung, eine Frage oder eine Anweisung, die den KI-Assistenten bei der Generierung einer bestimmten Antwort anleitet.

Sie können eine Textaufforderung verwenden, um den Inhalt zu ändern. Sie können beispielsweise den Inhalt des aktuellen Themas auswählen und die Eingabeaufforderung *Text knapper gestalten* verwenden. Ebenso können Sie eine Textaufforderung verwenden, um dem Tag, das im ausgewählten Inhalt verwendet wird, ein Attribut hinzuzufügen.

1. Wählen Sie den Text aus, für den Sie die Textaufforderung verwenden möchten.
1. Wählen **Textaufforderung verwenden**![ai-Symbol „Textaufforderung verwenden](./images/ai-use-text-prompt.svg) im Bedienfeld **Authoring** aus.
1. Geben Sie eine Eingabeaufforderung auf eine der folgenden Arten ein:

   - Wählen Sie eine Eingabeaufforderung aus den vorgeschlagenen Eingabeaufforderungen aus.
   - Bearbeiten Sie eine vorgeschlagene Eingabeaufforderung, um eine benutzerdefinierte Eingabeaufforderung gemäß Ihren Anforderungen zu erstellen.

     >[!NOTE]
     >
     > Die empfohlenen Eingabeaufforderungen werden in der `ui_config.json` von Ihrem Administrator konfiguriert.

   - Geben Sie die Eingabeaufforderung in das Textfeld ein.


1. Wählen Sie **Regenerieren** ![Symbol „Regenerieren](./images/refresh-icon.svg) für eine andere Antwort oder Ausgabe basierend auf Ihrer Eingabeaufforderung aus.

1. (Optional) Wählen Sie **Erweitern** ![expandicon](./images/expand-icon.svg) aus, um den **Textaufforderung verwenden** zu öffnen. Es zeigt den aktuellen und den generierten Inhalt an. Sie können den Quell-Layout-Inhalt bearbeiten und die Vorschau überprüfen.

   ![AI-Assistent-Textaufforderungs-Editor](./images/text-prompt.png)


   >[!NOTE]
   >
   > Die Antworten werden basierend auf dem ausgewählten Inhalt generiert.



1. Sie können die Eingabeaufforderung auch im Editor bearbeiten und die Antwort neu generieren. Sie können beispielsweise die Eingabeaufforderung ändern, um den Text auf etwa 40 Wörter zu verkürzen.

1. Sie können die Quelle des generierten Inhalts überprüfen und bei Bedarf bearbeiten.

1. Wählen Sie **Akzeptieren** aus, um den ausgewählten Inhalt im Thema durch den generierten Inhalt zu ersetzen.
1. **Abbrechen**: Bricht die Textaufforderungsaktion ab. Kehrt zum Bearbeitungsfenster zurück.

   >[!NOTE]
   >
   > Durch Auswahl **Symbols &quot;**&quot; im Authoring-Bedienfeld kehren Sie zum Ausgangsstatus des KI-Assistenten zurück.

## Inhalt verbessern

Verwenden Sie die **Inhalt verbessern**, um die Qualität des ausgewählten Inhalts des aktuellen Themas zu verbessern. Sie können den Inhalt auswählen, um Rechtschreibung, Sprache und grammatische Struktur zu überprüfen und eine bessere Version des Inhalts vorzuschlagen. Es verbessert auch die Qualität der Sätze.

1. Inhalt auswählen.
1. Wählen Sie **Inhalt verbessern** ![Symbol für KI-Verbesserung des Inhalts](./images/ai-improve-icon.svg) aus, um die Vorschläge für den verbesserten Inhalt zu finden.
1. Wählen Sie **Erneut generieren**, um einen weiteren Vorschlag für verbesserte Inhalte zu erhalten.

1. (Optional) Klicken Sie auf **Erweitern**, um den verbesserten Inhaltseditor zu öffnen. Es zeigt den aktuellen und den generierten Inhalt an. Sie können den Inhalt im Quell-Layout bearbeiten und auch die Vorschau überprüfen.



   ![KI-Assistent - Inhalt-Editor verbessern](./images/ai-assisstant-improve-content.png)

Akzeptieren Sie den Vorschlag, bearbeiten Sie die Antwort in der Quellansicht, bevor Sie ihn akzeptieren, generieren Sie sie für eine andere Antwort neu oder brechen Sie die Aktion ab, um zum vorherigen Status zurückzukehren.





## Kurzwahlnummern erstellen

Erstellen Sie eine kurze Beschreibung für das Thema basierend auf dem ausgewählten Inhalt in etwa 30-50 Wörtern. Die kurze Beschreibung hilft Benutzern, nach relevanten Inhalten zu suchen und diese zu finden.
Sie können beispielsweise die Systemanforderungen auflisten und entsprechend eine kurze Beschreibung generieren.



1. Inhalt auswählen.
1. Wählen Sie **Kurzbeschreibung erstellen** ![Symbol „Kurzbeschreibung erstellen“](./images/ai-create-shortdesc-icon.svg), um eine Kurzbeschreibung für das aktuelle Thema zu erstellen.
1. Wählen **Akzeptieren**, um eine neue Kurzbeschreibung zu erstellen, falls die Kurzbeschreibung noch nicht vorhanden ist. Wenn eine Kurzbeschreibung vorhanden ist, müssen Sie sie bestätigen, bevor Sie sie durch die neue Kurzbeschreibung ersetzen.

Sie können auch die folgenden Aktionen ausführen:

- Wählen Sie **Regenerieren**, um eine weitere kurze Beschreibung für Ihr Thema zu generieren.
- Wählen Sie **Erweitern** aus, um den **Shortdesc erstellen** zu öffnen.

  ![KI-Assistent zum Erstellen des Kurzbeschreibungseditors](./images/ai-assistant-create-short-desc.png)




## Inhalt auflisten

Diese Funktion wandelt einen ausgewählten Absatz intelligent in eine Liste um.  Er analysiert den Inhalt und erstellt eine logische Liste von Elementen. Sie müssen die Elemente nicht manuell erstellen. Wenn Sie beispielsweise über einen Absatz verfügen, der die Schritte zum Erstellen eines Benutzerkontos detailliert beschreibt, kann das Tool dies in eine schrittweise Liste umwandeln, sodass Elemente nicht manuell einzeln erstellt werden müssen.

![KI-Assistent - Symbol für Inhaltsauflistung](./images/ai-assisstant-itemise-content.png)



1. Inhalt auswählen.
1. Wählen Sie **Inhalt** KI![Symbol für Inhalt ](./images/ai-itemize-icon.svg) aus, um den ausgewählten Inhalt in eine Liste zu konvertieren.
Das Authoring-Tool im Bedienfeld des KI-Assistenten konvertiert den Inhalt intelligent in eine Liste von Elementen.
1. (Optional) Klicken Sie auf **Erweitern**, um den Editor **Inhalt auflisten** zu öffnen.
1. Sobald Ihre Liste fertig ist, akzeptieren Sie die Änderungen am generierten Inhalt. Der generierte Inhalt ersetzt dann den ausgewählten Inhalt.



## Inhalte übersetzen

Verwenden Sie diese intelligente Funktion, um die ausgewählten Inhalte in die Zielsprache zu übersetzen. Dies ist besonders nützlich, wenn Sie Notizen in verschiedenen Sprachen hinzufügen. Sie können beispielsweise Inhalte auf Englisch hinzufügen und schnell ins Arabische übersetzen.

Führen Sie die folgenden Schritte aus, um die Inhalte zu übersetzen:

1. Wählen Sie die Inhalte aus, die Sie übersetzen möchten.
1. Wählen Sie **Inhalt übersetzen** ![ai-Symbol „Inhalt übersetzen](./images/ai-translate-content-icon.svg) im Bedienfeld **Authoring** aus.
1. Wählen Sie im Dropdown-Menü die Zielsprache aus. Die übersetzten Inhalte werden im Bedienfeld KI-Assistent angezeigt.

1. (Optional) Wählen Sie **Erweitern** aus, um den Editor **Inhalte übersetzen** zu öffnen.
1. Sie können auch eine andere Sprache aus dem Dropdown-Menü auswählen und den Inhalt in der ausgewählten Sprache neu generieren. Wenn Sie beispielsweise Französisch auswählen und dann **Regenerieren** wählen, wird der Inhalt ins Französische übersetzt.

![KI-Assistent - Inhalte übersetzen](./images/ai-assisstant-translate-content.png)
