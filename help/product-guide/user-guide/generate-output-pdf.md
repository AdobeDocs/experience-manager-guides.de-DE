---
title: PDF-Vorgabentypen
description: Erfahren Sie mehr über die Typen von PDF-Voreinstellungen, die Sie mit Adobe Experience Manager Guides erstellen können.
exl-id: f12c91fd-3f95-478e-a9cd-68d037206ee8
feature: Publishing
role: User
source-git-commit: 558cc1a724a483353eb5d912354e1ab37dab348a
workflow-type: tm+mt
source-wordcount: '324'
ht-degree: 0%

---

# Übersicht über die PDF-Ausgabevorgabe {#id205BE600HAH}

Mit Experience Manager Guides können Sie PDF-Vorgaben erstellen, um PDFs einzelner Themen oder eine gesamte Zuordnungsdatei zu generieren. Sie können Ihre Inhalte in einem PDF-Format veröffentlichen, indem Sie eine der drei folgenden Methoden verwenden:

**DITA-OT**

Verwenden Sie diese Methode, um eine PDF-Ausgabe für eine Zuordnung über die Zuordnungskonsole oder das Zuordnungs-Dashboard zu generieren. Sie können vor dem Generieren der PDF Veröffentlichungseigenschaften festlegen, indem Sie eine Ausgabevorgabe für die Zuordnung erstellen, die in der Zuordnungskonsole oder im Zuordnungs -Dashboard geöffnet ist.

Weitere Informationen zum Erstellen einer PDF-Ausgabevorgabe mit der DITA-OT-Methode finden Sie unter [Erstellen einer DITA-OT PDF-Ausgabevorgabe](./generate-output-pdf-dita-ot.md)

**FrameMaker Publishing Server (FMPS)**

>[!NOTE]
>
> Die Veröffentlichungsoption „FMPS“ ist nur im Zuordnungs-Dashboard verfügbar.

Verwenden Sie diese Methode, um eine PDF-Ausgabe nicht nur aus dem DITA-Inhalt, sondern auch aus FrameMaker-Dokumenten (.book und .fm) zu generieren, die in Ihrem AEM-Repository verfügbar sind. Die PDF kann durch Konfigurieren einer Ausgabevorgabe erstellt und mithilfe von FrameMaker Publishing Server (FMPS) veröffentlicht werden. Sie können das Erscheinungsbild Ihrer Ausgabe für PDF und andere Formate entwerfen und konfigurieren und in einer Einstellungsdatei (.sts) speichern. Diese Einstellungsdatei wird dann von FMPS verwendet, um eine Ausgabe für eine DITA-Map- oder Buchdatei zu generieren. Um eine Ausgabevorgabe zu erstellen oder zu bearbeiten, rufen Sie [ Ansicht auf (Grundlegendes zu den Ausgabevorgaben](../user-guide/generate-output-understand-presets.md).

Weitere Informationen zum Konfigurieren von FMPS finden Sie unter [Generieren von Ausgaben aus FrameMaker-Dokumenten](../user-guide/fm-output-generatation.md).

**Native PDF**

Verwenden Sie diese Methode, um eine funktionsreiche PDF-Ausgabe auf der Grundlage von W3C CSS3- und CSS-Seitenmedienstandards zu generieren. Mit der nativen PDF-Veröffentlichung können Sie Vorlagen verwenden, um das Layout und die Formatierung für Ihre Inhalte festzulegen und verschiedene Einstellungen anzuwenden, um Ihre PDF zu optimieren. Darüber hinaus können Sie mit dem Vorlageneditor Ihre eigenen Vorlagen ändern und erstellen.

Weitere Informationen zur Erstellung von nativen PDF-Vorgaben finden Sie unter [Erstellen einer nativen PDF-Ausgabevorgabe](../web-editor/native-pdf-web-editor.md).





**Übergeordnetes Thema:**&#x200B;[ Verstehen der Ausgabevorgaben](generate-output-understand-presets.md)
