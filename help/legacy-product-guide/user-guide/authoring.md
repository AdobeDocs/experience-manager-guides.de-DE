---
title: Inhalt verwalten
description: Verwalten von Inhalten und Identifizieren Ihrer Rollen und Berechtigungen in AEM Guides. Lernen Sie die wichtigsten Konzepte des Content-Managements kennen und erfahren Sie, wie Sie mit den Profilen auf globaler oder Ordnerebene arbeiten.
feature: Content Management
role: User
exl-id: 54b960cf-fb00-4d4a-a836-9de4738c49a8
source-git-commit: 86fb9cc382689beb493847cb506c788199a2d3f4
workflow-type: tm+mt
source-wordcount: '717'
ht-degree: 10%

---

# Inhalt verwalten {#id164JBG0M0T1}

Bevor Sie mit der eigentlichen Inhaltserstellung beginnen, müssen Sie sich mit einigen Grundkonzepten des Content-Managements in AEM Guides vertraut machen. Erstellen Sie dann zunächst verschiedene Benutzergruppen und organisieren Sie Ihre Assets.

## Wichtige Konzepte

Einige Schlüsselkonzepte des Content-Managements in AEM sind:

**Asset-Management**

AEM Guides verwendet das Digital Asset Management \(DAM\) von AEM zur Verwaltung Ihrer DITA-Dateien. Die Dateien, die Sie in DAM hochladen oder einchecken, werden als digitale Assets gespeichert. Sie können Ihre Assets in AEM Assets verwalten und bearbeiten. Weitere Informationen zum Asset-Management finden Sie unter [Verwalten von Assets](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/assets/manage/manage-digital-assets.html?lang=de).

**Link-Verwaltung**

Verschieben oder Umbenennen von Dateien oder Ändern der Ordnerstruktur im Content-Repository, ohne sich Gedanken über fehlerhafte Verweise machen zu müssen. Alle Verweise auf und vom betroffenen Inhalt werden automatisch aktualisiert. Beim Löschen von Inhalten, auf die an anderer Stelle verwiesen wird, werden Warnungen angezeigt, um unbeabsichtigte Beschädigungen zu verhindern.

**Verwalten von Versionen**

AEM Guides bietet Versionsverwaltung für digitale Assets. Sie können diese Funktion einfach über eine beliebige DITA-Authoring-Anwendung aktivieren. Sie ermöglichen es Ihren Autoren, die standardmäßigen Versionssteuerungsfunktionen wie Ein- und Auschecken auszuführen.

Weitere Informationen zum Erstellen von Versionen oder zum Wiederherstellen einer bestimmten Version finden Sie unter [Verzweigung, Wiederherstellung und nachfolgende Versionierung](web-editor-preview-topics.md#id193PG0Y051X).

**Native DITA-Verarbeitung**

AEM Guides behält zwar die Struktur Ihrer DITA-Dateien bei, ermöglicht es AEM aber auch, DITA nativ mithilfe der Elementzuordnung zu verarbeiten, um die DITA-Elemente AEM-Komponenten zuzuordnen. Die native DITA-Verarbeitung wird in Funktionen wie der Themenvorschau, der AEM Sites-Veröffentlichung und den Überprüfungs-Workflows verwendet.

## Identifizieren von Rolle und Berechtigungen {#id181TF0K0MHT}

AEM Guides bietet drei vordefinierte Gruppen. Diese Gruppen sind: *Autoren*, *Prüfer* und *Herausgeber*. Je nach der Gruppe, der Sie zugeordnet sind, haben Sie die Berechtigung, bestimmte Aufgaben wie in der folgenden Tabelle aufgeführt auszuführen. Beispielsweise kann eine Veröffentlichungsaufgabe nur von einem Herausgeber, nicht aber von einem Autor oder einem Prüfer ausgeführt werden. Auf ähnliche Weise kann ein Autor ein neues Thema erstellen und ein Prüfer kann nur ein Thema überprüfen.

>[!TIP]
>
> Best Practices *Festlegen von* finden Sie im Abschnitt „Berechtigungen“ im Handbuch zu Best Practices.

In der folgenden Tabelle sind verschiedene Aufgaben sowie die Gruppen aufgeführt, die diese Aufgaben ausführen können:

| Aufgabe | Autoren | Prüfer | Herausgeber |
|----|-------|---------|----------|
| DITA-Thema erstellen | Ja |   | Ja |
| DITA-Map erstellen | Ja |   | Ja |
| Zuordnen von Sammlungen | Ja |   | Ja |
| Bewertungsaufgabe erstellen | Ja |   | Ja |
| Prüfungsthema[1](#fntarg_1) | Ja | Ja | Ja |
| Tastenauflösung | Ja |   | Ja |
| Auschecken/Einchecken | Ja |   | Ja |
| Thema bearbeiten | Ja |   | Ja |
| Thema verschieben | Ja |   | Ja |
| Themeneigenschaften bearbeiten | Ja |   | Ja |
| Kopieren | Ja |   | Ja |
| Löschen | Ja |   | Ja |
| Link freigeben | Ja |   | Ja |
| **Dokumentstatus** |
| Dokumentenstatusprofil erstellen/bearbeiten |   |   | Ja |
| Dokumentstatus ändern[2](#fntarg_2) | Ja | Ja | Ja |
| **In der DITA-Zuordnungskonsole verfügbare Funktionen \(Registerkarte „Ausgabevorgaben“\)** |
| Generieren |   |   | Ja |
| Bearbeiten |   |   | Ja |
| Duplizieren |   |   | Ja |
| Erstellen |   |   | Ja |
| Vorgabe löschen |   |   | Ja |
| **In der DITA-Zuordnungskonsole verfügbare Funktionen \(Registerkarte „Ausgaben“\)** |
| Erzeugte Ausgabe anzeigen | Ja |   | Ja |
| **In der DITA-Zuordnungskonsole verfügbare Funktionen \(Registerkarte Themen\)** |
| Bewertungsaufgabe erstellen | Ja |   | Ja |
| Bearbeiten | Ja |   | Ja |
| **In der DITA-Zuordnungskonsole verfügbare Funktionen \(Registerkarte „Baselines“\)** |
| Erstellen |   |   | Ja |
| Bearbeiten |   |   | Ja |
| Duplizieren |   |   | Ja |
| Remove |   |   | Ja |
| DITA Map Console \(Registerkarte „Berichte“\) | Ja |   | Ja |
| **In der DITA-Zuordnungskonsole verfügbare Funktionen \(Bedingungsvorgaben\)** |
| Erstellen/Bearbeiten einer Bedingungsvorgabe |   |   | Ja |

[1](#fnsrc_1) Wenn *Autoren* und *Herausgeber* zu einer Überprüfung eingeladen werden.

[2](#fnsrc_2) Abhängig von den Berechtigungen, die dem Benutzer im Dokumentstatusprofil gewährt wurden.

## Voraussetzungen für die Inhaltserstellung

**Arbeiten mit globalen Profilen oder Profilen auf Ordnerebene**

In einem Unternehmen können verschiedene Gruppen oder Produkte unterschiedliche Authoring-Vorlagen, Ausgabevorlagen, bedingte Attributprofile \(oder Betreffschemata\) und Web-Editor-Konfigurationen verwenden. Wenn Sie diese nur auf Enterprise-\(oder globaler\) Ebene konfigurieren, kann dies Autorinnen und Autoren Schwierigkeiten bereiten, da sie Vorlagen oder Profile sehen, die für sie nicht relevant sind.

Mit AEM Guides können Sie die Erstellung von \(topic oder map\) Vorlagen, Ausgabevorlagen, bedingten Attributen und Web-Editor-Konfigurationen auf Enterprise \(global\)-Ebene sowie auf Ordnerebene konfigurieren. Auf diese Weise können Sie die Konfigurationen für verschiedene Abteilungen oder Produkte in Ihrem Unternehmen trennen.

Außerdem können Sie die ordnerspezifischen Konfigurationen an eine Abteilung oder Produktadministratoren delegieren, um die Administration zu dezentralisieren.

Weitere Informationen zum Einrichten globaler Profile und Profile auf Ordnerebene finden Sie unter *Konfigurieren globaler Profile oder Profile auf Ordnerebene* unter Installieren und Konfigurieren von Adobe Experience Manager Guides as a Cloud Service.
