---
title: Verwenden des KI-Assistenten zur intelligenten Erstellung von Dokumenten "
description: Erfahren Sie, wie Sie mit dem KI-Assistenten Dokumente in Adobe Experience Manager Guides intelligent suchen und erstellen können.
exl-id: c18e8761-333e-40ef-9e16-e71a194a754a
TQID: https://experienceleague.adobe.com/pg9zeEg8m3NeDbN-j945SqPbaMX0GgBmuquAsQcrjOM
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
    internal-label: Experience Manager Guides
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
    internal-label: Experience Manager
feature_v2:
  - id: ab01a588-7dea-43f2-a699-0b3f128465d6
    internal-label: Authoring
  - id: ec4263d9-bf7c-44c7-b3f1-3e664861c8f2
    internal-label: Generative AI
subfeature_v2:
  - id: ad602516-aca3-4247-9ae8-f393d958efa9
    internal-label: Editor
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
topic_v2:
  - id: d095671a-1355-40aa-8b5f-06c33c68080b
    internal-label: Security
  - id: f5c2a4bb-71ca-4d7e-8efd-442250e6ba48
    internal-label: Content reuse
source-git-commit: b3c2c68321080aa4dde16befe4bfd0022bf9f61c
workflow-type: tm+mt
source-wordcount: '757'
ht-degree: 0%
---
# KI-Assistent

>[!NOTE]
>
> Die Funktion KI-Assistent ist derzeit für Adobe Experience Manager Guides as a Cloud Service verfügbar.

Der KI-Assistent in Adobe Experience Manager Guides ist ein KI-gestütztes Tool, das durch die Vereinfachung von Workflows zur Inhaltserstellung, -verwaltung und -bearbeitung die Produktivität steigert. Es bietet zwei Modi: Agent und Standard. Im **Agentenmodus** können Sie mit dem KI-Assistenten inhaltsbezogene Aufgaben durch Interaktionen in natürlicher Sprache ausführen, mit Fähigkeiten wie Importieren, Erstellen und Smart-Tagging, um die Inhaltserstellung, Organisation und Metadatenverwaltung zu optimieren. Im **Standardmodus** bietet der KI-Assistent Unterstützung beim Authoring, damit Sie Inhalte effizienter erstellen, verfeinern und verwalten können.

## KI-Assistentenmodi

Der KI-Assistent ist in zwei Modi verfügbar: **Agent** und **Standard**. Administratoren können den Modus im Abschnitt **KI-Funktionen** der Registerkarte **Allgemein** in den **Workspace-Einstellungen**. Das KI-Assistenten-Bedienfeld im Editor bleibt in beiden Modi gleich, die verfügbaren Funktionen unterscheiden sich jedoch:

- **Agentenmodus:** Verwendet Kenntnisse **Import**, **Erstellen** und **Smart-Tagging**, um Dateien in strukturierte Themen zu konvertieren, einen ersten Entwurf von Inhalten zu erstellen und relevante Tags basierend auf der Taxonomie Ihres Unternehmens zu empfehlen.
- **Standardmodus:** bietet KI-gestützte Authoring-Unterstützung durch kontextuelle Aktionen wie die Wiederverwendung von Inhalten, Übersetzung und Verbesserungen der Inhaltsqualität, um Authoring-Workflows zu optimieren.

## Agent-Modus

>[!NOTE]
>
> Um den KI-Assistenten im Agentenmodus zu verwenden, muss sich Ihr Unternehmen in Adobe CX Enterprise Coworker einarbeiten lassen und über verfügbare Credits verfügen. Wenden Sie sich nach der Einführung an Ihr Customer Success-Team, um die Funktion zu aktivieren. Konfigurationsdetails finden Sie unter [Konfigurieren des KI-Assistenten im Agentenmodus](../install-conf-guide/configure-ai-assistant-agentic-mode-cs.md).

Der Agentenmodus im KI-Assistenten ermöglicht es Ihnen, eine Vielzahl von inhaltsbezogenen Aufgaben durch Interaktionen in natürlicher Sprache auszuführen, z. B. das Erstellen und Importieren von Inhalten, das Zusammenfassen von Themen, das Hinzufügen von Themen zu Karten und das Verwalten von Metadaten. Sie können Ihre Anforderungen im Chat-Bedienfeld beschreiben, und der KI-Assistent plant und führt Aufgaben aus, während er für Einblick in deren Fortschritt sorgt. Der Agentenmodus bietet schnellen Zugriff auf die folgenden Fähigkeiten:

- **Importieren**: Konvertiert PDF-, Word- oder Markdown-Dateien aus Ihrem Geräte- oder Content-Repository in strukturierte Themen. Weitere Informationen finden Sie unter [Inhalt mit KI-Assistenten importieren](./import-ai-assistant.md).

- **Erstellen**: Generiert Themenentwürfe und Karten aus Eingabematerialien wie Spezifikationen, Whiteboard-Bildern, Screenshots und anderen Referenzinhalten mit der Option, vorhandene Inhalte für Ton und Stil zu verwenden. Weitere Informationen finden Sie unter [Erstellen von Inhalten mit dem KI-Assistenten](./create-ai-assistant.md).

- **Smart-Tagging**: Empfiehlt relevante Tags für Themen basierend auf der Taxonomie Ihres Unternehmens, um die Konsistenz der Metadaten zu verbessern. Weitere Informationen finden Sie unter [Smart-Tagging mit dem KI-Assistenten](./ai-assistant-agentic.md).

Die folgenden Komponenten des KI-Assistenten-Bedienfelds helfen Ihnen beim Hinzufügen von Inhalten, beim Eingeben von Eingabeaufforderungen und beim Starten von Aufgaben:

![KI-Assistent für Smart-Tagging](./images/panel-new-agentic.png)

- **(A)** Konversationsverlauf: Frühere Konversationen anzeigen und erneut öffnen, um frühere Anfragen und Antworten zu überprüfen.
- **(B)** Vollbild: Erweitert das Bedienfeld des KI-Assistenten auf Vollbild.
- **(C)** Leertaste eingeben: Geben Sie eine Eingabeaufforderung ein, oder geben Sie `/` ein, um Dateien hinzuzufügen und Tags zu generieren.
- **(D)** Dateien anhängen oder Kontext hinzufügen: Fügt Themen, Karten oder Dateien aus Ihrem lokalen System hinzu, um den Inhalt bereitzustellen, mit dem der KI-Assistent arbeitet.
- **(E)** Senden: Senden Sie Ihre Eingabeaufforderung und angehängten Inhalte an den KI-Assistenten.
- **(F)** Schnellaktionen: Starten Sie eine Aufgabe direkt über eine der folgenden Tastaturbefehle: **Importieren**, **Erstellen** oder **Tag**.

## Standardmodus

Der Standardmodus macht den Authoring-Prozess intelligenter und schneller. Wenn Sie Text im Editor auswählen, bietet der KI-Assistent schnelle Aktionen, wie das Generieren intelligenter Vorschläge für die Wiederverwendung von Inhalten, das Übersetzen von Inhalten, die Verbesserung der Inhaltsqualität und mehr, die alle auf Ihren ausgewählten Inhalten basieren. Dies verbessert das allgemeine Authoring-Erlebnis und die Produktivität von Autoren.

Weitere Informationen finden Sie unter [Erstellen von Dokumenten mit dem KI-Assistenten](./ai-assistant-right-panel.md).

![KI-Assistent](./images/ai-assistant-panel.png)


## Erste Schritte mit dem KI-Assistenten

Wenn Sie den **KI-Assistenten** zum ersten Mal verwenden, werden Sie aufgefordert, Ihr Einverständnis einzureichen, bevor Sie die Funktionen der generativen KI von Experience Manager Guides verwenden.

Führen Sie die folgenden Schritte aus, um den KI-Assistenten zu starten:

1. Melden Sie sich bei Experience Manager Guides an.
1. Wählen Sie auf der Startseite **KI-Assistent** aus. Stellen Sie sicher, dass Ihr Administrator die Funktion KI-Assistent im gewünschten Modus aktiviert hat.
Der KI-Assistent zeigt die wichtigsten Funktionen, den Link zu Benutzerrichtlinien und eine Schaltfläche **Erste Schritte** an.
1. Lesen Sie die Benutzerrichtlinien sorgfältig durch und wählen Sie dann **Erste Schritte** aus, um den KI-Assistenten zu starten.

>[!NOTE]
>
>Wenn Sie den Richtlinien für die Verwendung der Hilfe-Assistentenfunktion bereits zugestimmt haben, werden Sie nicht erneut zur Einwilligung aufgefordert und können die KI-Assistentenfunktion weiterhin verwenden.

**Verwandte Themen**

[Häufig gestellte Fragen zur Sicherheit des KI-Assistenten](./ai-assistant-faq.md)

[Adobe Experience Manager Guides Generative AI-Offenlegungen](./adobe-generative-ai-disclosures.md)

[Konfigurieren des KI-Assistenten für die intelligente Hilfe und das Authoring](../cs-install-guide/conf-smart-suggestions.md)
