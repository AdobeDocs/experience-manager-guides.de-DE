---
title: Map-Konsole in Adobe Experience Manager Guides
description: Erfahren Sie mehr über die Kartenkonsole und die verschiedenen verfügbaren Funktionen, mit denen Sie Karten in Adobe Experience Manager Guides veröffentlichen und verwalten können.
feature: Publishing
role: User
exl-id: b273b1ae-fbb2-4b35-abce-0df78eeb2e11
TQID: https://experienceleague.adobe.com/RFlLBJ4tFUBVo2FyGFur21uIResNd0qFWpKszJbnBIk
product_v2: id: fae5e35a-80c9-4b94-9352-1a060a6aab1did: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2: id: a3bd6397-2eb2-4908-a61c-226e26855dcaid: d90290ec-3e61-4ebd-8649-bcafe0836803
subfeature_v2: id: d6596f3f-92a7-43ec-b444-237db6adad05id: f9dbea21-a714-40dd-bc90-080d8046c93fid: fd456af4-cb12-4a34-8cc4-b74adf885626id: fd6cc9e1-e5e5-494e-b7b1-a32f2d6cd7c9
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554
topic_v2: id: a004cc84-67b9-4a33-a3a7-8ec7273ef4dc
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 773
ht-degree: 0%

---

# Übersicht über die Zuordnungskonsole

Adobe Experience Manager Guides bietet eine dedizierte Konsole, die **Map-Konsole**, um alle Zuordnungsverwaltungs- und Veröffentlichungsaufgaben zu optimieren. Diese zentrale Benutzeroberfläche verbessert die Produktivität und Genauigkeit bei Ihren Zuordnungsaktivitäten, indem sie Optionen zum Generieren von Ausgaben, Übersetzen von Inhalten, Zugreifen auf Berichte und mehr bietet - alles an einem Ort.

![Registerkarte „Optionen“ der Dateieigenschaften](./images/map-console-screen.png)

Die Benutzeroberfläche der Map-Konsole ist hauptsächlich in zwei Abschnitte unterteilt - **Navigationsleiste** und **Linkes Bedienfeld**.

![Neu](images/map-console-sections.png)

- (**A**) **Navigationsleiste**: Die Navigationsleiste zeigt Tools zum Umschalten der Navigation, Anpassen der Seitenansicht und Anzeigen des Namens der ausgewählten Zuordnungsdatei an.

  In der Navigationsleiste verfügbare Funktionen werden wie folgt erläutert:

   - **Navigationsumschalter**: Ermöglicht die nahtlose Navigation zu anderen Seiten - Editor oder Homepage:
   - **Ausgewählte Zuordnungsdatei**: Zeigt den Namen der aktuell ausgewählten Zuordnungsdatei an. Sie können sie im Editor öffnen oder eine andere Zuordnungsdatei für die Zuordnungskonsole auswählen.
   - **Weitere Aktionen**: Bietet Optionen zum Navigieren zur **Assets-Benutzeroberfläche** zu den **Workspace-Einstellungen**. Weitere Informationen finden Sie in der [Registerkartenleiste](./web-editor-tab-bar.md).

  >[!NOTE]
  >
  > Wenn Sie die Adobe Experience Manager Guides in einem On-Premise-Setup verwenden, wird die Option Workspace-Einstellungen weiterhin als **Einstellungen** im Menü Mehr Aktionen angezeigt.

   - **Ansicht erweitern**: Ermöglicht das Erweitern der Seitenansicht mithilfe des Symbols **Erweitern**. In dieser Ansicht ist die Kopfzeilenleiste ausgeblendet, was den Inhaltsbereich maximiert. Um zur Standardansicht zurückzukehren, verwenden Sie das Symbol **Erweiterte Ansicht beenden**.

  >[!NOTE]
  >
  > Bei Verwendung der Adobe Experience Manager Guides as a Cloud Service wird eine zusätzliche Funktion [KI](./ai-assistant.md)Assistent) in der Navigationsleiste angezeigt.

- (**B**) **Linker Bereich**: Der linke Bereich bietet schnellen Zugriff auf die Funktionen „Ausgabegenerierung“, „Berichterstellung und -verwaltung“, „Baseline“, „Bedingungsvorgaben“, „Inhaltsübersetzung“ und &quot;Workfront (nur wenn konfiguriert)“.

  Weitere Informationen finden Sie im folgenden Abschnitt [Funktionen der ](#map-console-features) zuordnen“.

## Funktionen der Zuordnungskonsole

Die folgenden Funktionen sind im linken Bereich verfügbar, wenn Sie [eine DITA-Zuordnungsdatei in der Zuordnungskonsole öffnen](./open-files-map-console.md).

**Ausgabenerstellung**

Mit der Map-Konsole können Sie effizient Ausgaben in verschiedenen Formaten generieren, einschließlich AEM Sites, PDF, HTML5, EPUB, JSON, und benutzerdefinierte Ausgaben durch DITA-OT, native PDF-Veröffentlichung und FMPS. Sie können eine Ausgabe für eine gesamte DITA-Map generieren oder nur einige Themen, die Sie aktualisiert haben, selektiv veröffentlichen. Sie können die Funktion „Baseline-Veröffentlichung“ auch verwenden, um eine bestimmte Version Ihrer DITA-Karte oder Ihres Themas selektiv zu veröffentlichen.

Weitere Informationen finden Sie unter [Ausgabegenerierung](./generate-output.md).

**Berichterstellung und -verwaltung**

In einem organisatorischen Setup sollten Sie die Vollständigkeit Ihrer technischen Dokumentation insgesamt überprüfen, bevor Sie mit der Arbeit daran beginnen oder die Dokumente live verschieben. Ein solcher Bedarf wird in Umgebungen mit mehreren Benutzern und großen Umgebungen noch wichtiger. Mit der Zuordnungskonsole erhalten Sie Zugriff auf Experience Manager Guides-Berichte, die eine nützliche insight zum Gesamtzustand der Inhalte in Ihrem Repository und zur Verwendung von Inhalten im Dokumentationsprozess geben.

Weitere Informationen finden Sie unter [Berichte in Experience Manager Guides](./reports-intro.md).

**Baseline**

Experience Manager Guides bietet die Funktion „Grundlinien“, mit der Sie eine Version Ihrer Themen und Assets erstellen können, die dann zur Veröffentlichung oder Übersetzung verwendet werden können. Sie können auch mehrere Ausgabevorgaben derselben DITA-Zuordnung parallel veröffentlichen.

Erfahren Sie, wie [ Baselines in Experience Manager Guides erstellen und verwalten ](./web-editor-baseline.md).

**Bedingungsvorgaben**

Mit Experience Manager Guides können Sie Attribute in Ihren DITA-Themen definieren und mithilfe der Bedingungsvorgabe festlegen, was mit dem Attribut in der endgültigen Ausgabe geschehen soll. Sie können beispielsweise Attribute als Version 1.0 und Version 2.0 in Ihrem Inhalt hinzufügen und eine Bedingungsvorgabe verwenden, um Version 1.0 für Version 1.0 einzuschließen und Version 2.0 auszuschließen. Ebenso können Sie Ihrem Inhalt Attribute wie Betriebssystem Windows und Betriebssystem Linux hinzufügen und dann den relevanten Inhalt für Ihre endgültige Ausgabe je nach Betriebssystem ein- oder ausschließen.

Weitere Informationen zu [Bedingungsvorgaben](./generate-output-use-condition-presets.md).

**Inhaltsübersetzung**

Experience Manager Guides verfügt über leistungsstarke Funktionen, mit denen Sie Ihre Inhalte in mehrere Sprachen übersetzen können. Sowohl Workflows für menschliche als auch maschinelle Übersetzungen werden von Experience Manager Guides unterstützt.

In der Map-Konsole haben Sie Zugriff auf alle Optionen, die für die ersten Schritte mit Übersetzungs-Workflows erforderlich sind. Weitere Informationen finden Sie unter [Inhalte übersetzen](./translation.md).


**Workfront**

Die Workfront-Funktion ist auch in der Zuordnungskonsole verfügbar, über die Sie direkt in der Experience Manager Guides mit Adobe Workfront-Aufgaben arbeiten können.

Erfahren Sie mehr über die Integration von [Adobe Workfront in Experience Manager Guides](./workfront-integration.md).

Sie können auf diese Funktion nur zugreifen, wenn Ihr Administrator die **Adobe Workfront**-Integration in Ihrer Experience Manager Guides-Instanz konfiguriert hat.
