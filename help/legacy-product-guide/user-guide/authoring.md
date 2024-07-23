---
title: Inhalt verwalten
description: Verwalten Sie Inhalte und identifizieren Sie Ihre Rollen und Berechtigungen in AEM Guides. Erfahren Sie mehr über die wichtigsten Konzepte des Content Managements und der Arbeit mit globalen Profilen oder Profilen auf Ordnerebene.
feature: Content Management
role: User
source-git-commit: 76c731c6a0e496b5b1237b9b9fb84adda8fa8a92
workflow-type: tm+mt
source-wordcount: '717'
ht-degree: 10%

---

# Inhalt verwalten {#id164JBG0M0T1}

Bevor Sie mit der eigentlichen Inhaltserstellung beginnen, müssen Sie sich mit einigen Grundkonzepten des Content Managements in AEM Guides vertraut machen. Beginnen Sie dann mit dem Erstellen verschiedener Benutzergruppen und dem Organisieren Ihrer Assets.

## Schlüsselkonzepte

Einige der wichtigsten Konzepte des Content Managements in AEM sind:

**Asset-Verwaltung**

AEM Guides verwendet AEM Digital Asset Management \(DAM\), um Ihre DITA-Dateien zu verwalten. Die Dateien, die Sie in DAM hochladen oder einchecken, werden als digitale Assets gespeichert. Sie können Ihre Assets in AEM Assets verwalten und bearbeiten. Weitere Informationen zur Asset-Verwaltung finden Sie unter [Verwalten von Assets](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/assets/manage/manage-digital-assets.html?lang=de).

**Linkverwaltung**

Verschieben oder umbenennen Sie Dateien oder ändern Sie die Ordnerstruktur im Inhalts-Repository, ohne sich Gedanken über fehlerhafte Verweise machen zu müssen. Alle Verweise auf und aus den betroffenen Inhalten werden automatisch aktualisiert. Erhalten Sie Warnungen beim Löschen von Inhalten, auf die an anderer Stelle verwiesen wird, um unbeabsichtigte Unterbrechungen zu verhindern.

**Verwalten von Versionen**

AEM Guides bietet Versionsverwaltung für Ihre digitalen Assets. Sie können diese Funktion einfach über eine DITA-Authoring-Anwendung Ihrer Wahl aktivieren. Ermöglicht es Ihren Autoren, die standardmäßigen Versionskontrollfunktionen wie Einchecken und Auschecken auszuführen.

Weitere Informationen zum Erstellen von Versionen oder Wiederherstellen auf eine bestimmte Version finden Sie unter [Verzweigung, Wiederherstellung und nachfolgende Versionierung](web-editor-preview-topics.md#id193PG0Y051X).

**Native DITA-Verarbeitung**

AEM Guides behält die Struktur Ihrer DITA-Dateien bei, ermöglicht es AEM jedoch auch, DITA nativ mithilfe der Elementzuordnung zu verarbeiten, um die DITA-Elemente AEM Komponenten zuzuordnen. Die native DITA-Handhabung wird in Funktionen wie Themenvorschau, AEM Sites-Veröffentlichung und den Überprüfungs-Workflows verwendet.

## Rolle und Berechtigungen identifizieren {#id181TF0K0MHT}

AEM Guides bietet drei vordefinierte Gruppen. Diese Gruppen sind: *Autoren*, *Überprüfer* und *Herausgeber*. Abhängig von der Gruppe, der Sie zugeordnet sind, sind Sie berechtigt, bestimmte Aufgaben wie in der unten stehenden Tabelle beschrieben auszuführen. Beispielsweise kann eine Veröffentlichungsaufgabe nur von einem Herausgeber, aber nicht von einem Autor oder Überprüfer ausgeführt werden. Auf ähnliche Weise kann ein Autor ein neues Thema erstellen und ein Überprüfer kann nur ein Thema überprüfen.

>[!TIP]
>
> Best Practices zum Festlegen von Benutzerberechtigungen finden Sie im Abschnitt *Berechtigungen* im Best Practices-Handbuch.

In der folgenden Tabelle sind verschiedene Aufgaben und die Gruppen aufgeführt, die diese Aufgaben ausführen können:

| Aufgabe | Autoren | Prüfer | Herausgeber |
|----|-------|---------|----------|
| DITA-Thema erstellen | Ja |   | Ja |
| DITA Map erstellen | Ja |   | Ja |
| Sammlungen zuordnen | Ja |   | Ja |
| Bewertungsaufgabe erstellen | Ja |   | Ja |
| Prüfungsthema[1](#fntarg_1) | Ja | Ja | Ja |
| Schlüsselauflösung | Ja |   | Ja |
| Auschecken/Einchecken | Ja |   | Ja |
| Thema bearbeiten | Ja |   | Ja |
| Verschieben-Thema | Ja |   | Ja |
| Eigenschaften von Themen bearbeiten | Ja |   | Ja |
| Kopieren | Ja |   | Ja |
| Löschen | Ja |   | Ja |
| Link freigeben | Ja |   | Ja |
| **Dokumentstatus** |
| Dokumentstatusprofil erstellen/bearbeiten |   |   | Ja |
| Dokumentstatus ändern[2](#fntarg_2) | Ja | Ja | Ja |
| **In der DITA-Map-Konsole verfügbare Funktionen \(Registerkarte &quot;Ausgabevorgaben&quot;\)** |
| Generieren |   |   | Ja |
| Bearbeiten |   |   | Ja |
| Duplizieren |   |   | Ja |
| Erstellen |   |   | Ja |
| Vorgabe löschen |   |   | Ja |
| **In der DITA-Map-Konsole verfügbare Funktionen \(Registerkarte &quot;Ausgaben&quot;\)** |
| Anzeigen der generierten Ausgabe | Ja |   | Ja |
| **In der DITA-Zuordnungskonsole verfügbare Funktionen \(Registerkarte &quot;Themen&quot;\)** |
| Bewertungsaufgabe erstellen | Ja |   | Ja |
| Bearbeiten | Ja |   | Ja |
| **In der DITA-Zuordnungskonsole verfügbare Funktionen \(Registerkarte &quot;Grundlinien&quot;\)** |
| Erstellen |   |   | Ja |
| Bearbeiten |   |   | Ja |
| Duplizieren |   |   | Ja |
| Remove |   |   | Ja |
| DITA-Map-Konsole \(Registerkarte &quot;Berichte&quot;\) | Ja |   | Ja |
| **In der DITA-Zuordnungskonsole verfügbare Funktionen \(Bedingungsvorgaben\)** |
| Bedingungsvorgabe erstellen/bearbeiten |   |   | Ja |

[1](#fnsrc_1) Wenn *Autoren* und *Herausgeber* zur Überprüfung eingeladen werden.

[2](#fnsrc_2) Abhängig von den Berechtigungen, die dem Benutzer im Dokumentenstatusprofil zugewiesen wurden.

## Voraussetzungen für die Inhaltserstellung

**Arbeiten mit globalen Profilen oder Profilen auf Ordnerebene**

In einem Unternehmen können verschiedene Gruppen oder Produkte verschiedene Authoring-Vorlagen, Ausgabevorlagen, bedingte Attributprofile \(oder Betreffschemata\) und Web-Editor-Konfigurationen verwenden. Die Konfiguration dieser Vorlagen nur auf Unternehmensebene (oder global\) kann Autoren das Erlebnis erschweren, da sie Vorlagen oder Profile sehen, die für sie nicht relevant sind.

Mit AEM Guides können Sie Authoring- \(Themen- oder Zuordnungsvorlagen), Ausgabevorlagen, bedingte Attribute und Web-Editor-Konfigurationen auf Unternehmens- \(global\)- sowie Ordnerebene konfigurieren. Auf diese Weise können Sie die Konfigurationen für verschiedene Abteilungen oder Produkte in Ihrem Unternehmen trennen.

Außerdem können Sie die ordnerspezifischen Konfigurationen an eine Abteilung oder Produktadministratoren delegieren, um die Verwaltung zu dezentralisieren.

Weitere Informationen zum Einrichten von globalen Profilen und Profilen auf Ordnerebene finden Sie unter *Konfigurieren globaler Profile oder Profile auf Ordnerebene* in Installieren und Konfigurieren von Adobe Experience Manager Guides as a Cloud Service.
