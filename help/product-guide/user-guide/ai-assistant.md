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
source-git-commit: 71ddd55d2a6848449d5810701b60e9f69a29112b
workflow-type: tm+mt
source-wordcount: '615'
ht-degree: 0%
---
# KI-Assistent (Beta)

Der **KI-Assistent** in Adobe Experience Manager Guides ist ein leistungsstarkes, KI-gesteuertes Tool, das Ihre Produktivität durch intelligente Hilfe-, Authoring- und Tagging-Funktionen steigert. Im **Standard**-Modus werden zwei robuste KI-Funktionen - **Authoring** und **Hilfe** in der Experience Manager Guides-Benutzeroberfläche zusammengeführt, sodass Sie Inhalte und Informationen aus der Experience Manager Guides-Dokumentation schneller und effizienter erstellen und darauf zugreifen können. Im **Agent**-Modus bietet der KI-Assistent stattdessen **Smart-Tagging**, mit dem Sie über ein Konversationsaufforderungsfenster Tag-Empfehlungen für Ihre Inhalte anfordern und sie auf ein oder mehrere Themen anwenden können.

>[!NOTE]
>
> Die Funktion KI-Assistent ist derzeit für Adobe Experience Manager Guides as a Cloud Service verfügbar.

## KI-Assistentenmodi

>[!NOTE]
>
>Wenden Sie sich an das Customer Success-Team , um den KI-Assistenten für Ihre Umgebung im Agentenmodus zu aktivieren.

Der KI-Assistent ist in zwei Modi verfügbar: **Agent** und **Standard**. Administratoren können zwischen den beiden Modi im Abschnitt **KI-Assistent** der Registerkarte **Allgemein** in den **Workspace-Einstellungen**. Das Bedienfeld des KI-Assistenten bleibt in beiden Modi im Editor gleich, aber die darin verfügbaren Funktionen unterscheiden sich:

* **Agent**-Modus verwendet die **Smart-Tagging**-Fähigkeit von Adobe CX Enterprise Coworker, um Ihren Inhalt zu analysieren und relevante Tags basierend auf der Taxonomie Ihres Unternehmens zu empfehlen.
* **Standard**-Modus bietet das vorhandene KI-Assistentenerlebnis mit den Registerkarten **Hilfe** und **Authoring** im KI-Assistenten-Bedienfeld.

## Agent-Modus

### Smart-Tagging

Der KI-Assistent im Agentenmodus macht das Tagging Ihres Inhalts durch ein dialogorientiertes Eingabeaufforderungsfenster schneller und einfacher. Bei Verwendung der agenten Smart-Tagging-Fähigkeit von Adobe CX Enterprise Coworker empfiehlt der KI-Assistent relevante Tags für Ihren Inhalt, wenn Sie ihn darum bitten. Sie behalten die Kontrolle, indem Sie die vorgeschlagenen Tags überprüfen und sie auf ein oder mehrere Themen anwenden, einschließlich mehrerer Themen in einer Zuordnung.

Weitere Informationen finden Sie unter [Erste Schritte mit dem Agent-KI-Assistenten](./ai-assistant-agentic.md).

![KI-Assistent für Smart-Tagging](./images/suggested-prompts.png)

## Standardmodus

### Authoring

Wenn der KI-Assistent im **Standard**-Modus konfiguriert ist, **die Funktion Authoring** im KI-Assistenten Ihren Authoring-Prozess intelligenter und schneller. Es bietet Funktionen wie das Generieren intelligenter Vorschläge für die Wiederverwendung von Inhalten, das Übersetzen von Inhalten, die Verbesserung der Inhaltsqualität und mehr, die alle auf Ihren ausgewählten Inhalten basieren. Diese Funktion verbessert das allgemeine Authoring-Erlebnis und die Produktivität von Autoren.

Weitere Informationen finden Sie unter [Authoring](./ai-assistant-right-panel.md).

![KI-Assistent](./images/ai-assistant-panel.png)

### Hilfe

Wenn der KI-Assistent im **Standard**-Modus konfiguriert ist, bietet die **Hilfe**-Funktion ein intuitives, chatbasiertes Erlebnis, das Ihnen hilft, Experience Manager Guides zu verstehen, Probleme zu beheben und Informationen in der Dokumentation zu Adobe Experience Manager Guides zu finden. Anstatt in Benutzerhandbüchern und Referenzdokumenten zu suchen, können Sie die Funktion **Hilfe** verwenden, um schnell relevante Antworten auf Ihre Fragen zu finden. Dies spart Zeit und ermöglicht es Ihnen, sich auf die Inhaltserstellung zu konzentrieren, was zu höherer Produktivität und Effizienz führt.

Weitere Informationen finden Sie unter [Hilfe](./ai-based-smart-help.md).


![Smartes Hilfebedienfeld](images/smart-help-panel.png)

## Erste Schritte mit dem KI-Assistenten im Standardmodus

Wenn Sie den **KI** Assistenten im Standardmodus zum ersten Mal verwenden, werden Sie aufgefordert, Ihr Einverständnis einzureichen, bevor Sie die Funktionen der generativen KI von Experience Manager Guides verwenden.

Führen Sie die folgenden Schritte aus, um den KI-Assistenten zu starten:

1. Melden Sie sich bei Experience Manager Guides an.
1. Wählen Sie auf der Startseite **KI-Assistent** aus. Stellen Sie sicher, dass Ihr Administrator die Funktion KI-Assistent im gewünschten Modus aktiviert hat.

Der KI-Assistent zeigt die wichtigsten Funktionen, den Link zu Benutzerrichtlinien und eine Schaltfläche **Erste Schritte** an.

![Smartes Hilfebedienfeld](images/get-started-ai.png)

Lesen Sie die Benutzerrichtlinien sorgfältig durch und wählen Sie dann **Erste Schritte** aus, um den KI-Assistenten zu starten.

**Verwandte Themen**

[Häufig gestellte Fragen zur Sicherheit des KI-Assistenten](./ai-assistant-faq.md)

[Adobe Experience Manager Guides Generative AI-Offenlegungen](./adobe-generative-ai-disclosures.md)

[Konfigurieren des KI-Assistenten für die intelligente Hilfe und das Authoring](../cs-install-guide/conf-smart-suggestions.md)
