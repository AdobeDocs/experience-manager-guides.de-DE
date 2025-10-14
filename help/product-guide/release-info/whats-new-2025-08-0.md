---
title: Versionshinweise zu | Neue Funktionen in Adobe Experience Manager Guides Version 2025.08.0
description: Erfahren Sie mehr über die neuen und erweiterten Funktionen der Version 2025.08.0 von Adobe Experience Manager Guides
role: Leader
exl-id: c3461d0a-6394-4275-9d54-b2b1545d7c18
source-git-commit: 1a44af3522060ebc531393d4d01b1cd00eb02c10
workflow-type: tm+mt
source-wordcount: '843'
ht-degree: 2%

---

# Neue Funktionen in der Version 2025.08.0 (August 2025)

Dieser Artikel behandelt die neuen und erweiterten Funktionen, die mit der Version 2025.08.0 von Adobe Experience Manager Guides as a Cloud Service eingeführt wurden.

Eine Liste der in dieser Version behobenen Probleme finden Sie im Artikel [Behobene Probleme in Version 2025.08.0](fixed-issues-2025-08-0.md).

Erfahren Sie mehr [Upgrade-Anweisungen für die Version 2025.08.0](../release-info/upgrade-instructions-2025-08-0.md).


## Verbesserter Überprüfungs-Workflow

Mit dieser Version wurde der Überprüfungs-Workflow erheblich verbessert, um die nahtlose Kommunikation zwischen Autoren und Prüfern zu verbessern. Zu den wichtigsten Aktualisierungen gehören:

- Aufgabenverwaltungs-Workflows mit verwertbaren Benachrichtigungen
- Möglichkeit, Benutzende zu taggen, um sofortige Aufmerksamkeit zu erhalten
- Einfacherer Zugriff auf Projekt- und Aufgabendetails über das Überprüfungsfeld

Mit diesen Verbesserungen können Benutzer jetzt Folgendes erwarten:

- Effiziente und zeitnahe Überprüfungszyklen
- Reduzierter manueller Aufwand beim Austausch von Feedback

Weitere Informationen finden Sie unter [Einführung in die Überprüfung](../user-guide/review.md)

## Konfigurierbare KI-Assistentenaktionen in den Editor-Einstellungen

Die neueste Aktualisierung führt eine erweiterte Konfiguration für **Authoring-Schnellaktionen** im KI-Assistenten ein, sodass Admins die Authoring-Umgebung an bestimmte Workflows und Voreinstellungen anpassen können.

Sobald der Umschalter **KI** Assistent) aktiviert ist, können Admins selektiv auswählen, welche Schnellaktionen auf der Registerkarte **Authoring** angezeigt werden sollen, um die Autoreninteraktionen zu optimieren. Diese Sichtbarkeitseinstellungen sind für jedes Ordnerprofil spezifisch.

Weitere Informationen zum [KI-Assistenten in den Editor-Einstellungen](../cs-install-guide/workspace-settings.md#general) in Experience Manager Guides.

![](assets/authoring-quick-actions.png){width="350" align="left"}


## Verbessertes Erlebnis bei der Erstellung und Verwendung von DITAVAL-Dateien

Diese Aktualisierung führt mehrere Verbesserungen ein, die die Erstellung, Verwaltung und Anwendung von DITAVAL-Dateien vereinfachen und eine bessere Kontrolle über bedingte Inhalte und Stile in allen Ausgaben ermöglichen.

Die wichtigsten Highlights sind:

- **Verbesserte Unterstützung für das Markieren in der Bearbeitung von DITAVAL-Dateien:** Experience Manager Guides bietet neue Funktionen zum Anpassen der Inhaltsveröffentlichung durch verbesserte Unterstützung für das Markieren in DITAVAL-Dateien. Sie können jetzt Start- und End-Flags um bestimmte Inhalte, einschließlich Bildern, anwenden und markierte Abschnitte mit Formatierungsoptionen wie fett, kursiv und mehr anreichern. Um Bedingungsüberschneidungen zu handhaben, kann der **Stilkonflikt** konfiguriert werden. Dazu gehört das Festlegen einer standardmäßigen Hintergrund- und Textfarbe, um Klarheit und Konsistenz in der Ausgabe sicherzustellen. Diese Flags werden in der nativen PDF-Generierung vollständig unterstützt, und die resultierende Ausgabe spiegelt alle angewendeten Stilelemente genau und umfassend wider.
Weitere Informationen finden Sie unter [Verwenden des DITAVAL-Editors](../user-guide/ditaval-editor.md).

  ![](assets/ditaval-flag-style-new.png){width="350" align="left"}

- **Unterstützung mehrerer DITAVAL-Dateien für native PDF:** Für native PDF können jetzt mehrere DITAVAL-Dateien hinzugefügt werden, die jeweils als getaggter Eintrag angezeigt werden, um sie leicht zu identifizieren und zu entfernen. Dies bietet mehr Flexibilität und Kontrolle über bedingte Inhalte in PDF-Ausgaben

  Darüber hinaus verbessert diese Aktualisierung die Erstellung von Ausgabevorgaben, indem bearbeitbare DITAVAL-Felder in allen Formaten aktiviert werden, sodass Benutzende DITAVAL-Pfade manuell angeben können.

  Weitere Informationen finden Sie unter [ von Ausgabevorgaben ](../user-guide/generate-output-understand-presets.md) Experience Manager Guides.

## Verbesserte Protokollfilterung der Ausgabenerstellung

Diese Version bietet Verbesserungen an der Benutzeroberfläche für die Filterfunktion für Ausgabegenerierungsprotokolle. Sie können jetzt die Ausgabenerstellungsprotokolle besser nach allen vier verschiedenen Ebenen filtern: **Info**, **Warn**, **Error** (einschließlich Fehler und Ausnahmen) und **Fatal** mit verbesserten und intuitiven farbcodierten Indikatoren, die die Analyse vereinfachen und die Sichtbarkeit im gesamten Protokollstrom verbessern. Diese Verbesserung ermöglicht eine effizientere Navigation in Protokollen und eine präzise Lokalisierung kritischer Probleme.

Weitere Informationen finden Sie unter [Allgemeine Fehlerbehebung](../user-guide/generate-output-basic-troubleshooting.md).

![](./assets/log-file-new.png){align="left"}


## Temporäre Dateien für die veröffentlichte Ausgabe enthalten jetzt Autoren- und Veröffentlichungs-URLs in einer neuen Konfigurationsdatei

Die neuesten Veröffentlichungsverbesserungen für Experience Manager Guides fügen jetzt eine neue `system_config.xml`-Datei zu den temporären Dateien hinzu, die beim Veröffentlichen von HTML-, PDF- und JSON-Ausgaben mit DITA-OT generiert wurden, sowie die native PDF-Ausgabe. Diese Datei wird automatisch in den Veröffentlichungsauftrag aufgenommen und kann auch über temporäre Dateien aufgerufen werden, wenn Sie die Option **Temporäre Dateien beibehalten** für die Voreinstellungen aktivieren und die Ausgabe generieren.

Die `system_config.xml`-Datei enthält Details zur AEM-Instanz, einschließlich der Autoren-URL, der lokalen URL und der Veröffentlichungs-URL, wodurch der Kontext klarer wird und die Rückverfolgbarkeit der heruntergeladenen URLs verbessert wird.

Weitere Informationen finden Sie unter [Grundlegendes zu Ausgabevorgaben](../user-guide/generate-output-understand-presets.md).

## Neue Unterstützung von Ausgabepfadvariablen für die Ausgabegenerierung

Dieses Update führt die dynamische `output path` für Ausgabevorgaben wie native PDF, DITA-OT-PDF, JSON, HTML5 und benutzerdefinierte Einstellungen ein. Statt einen festen Pfad zu verwenden, können Benutzer jetzt den Ausgabespeicherort während der Installation mit der Variablen `${base_output_path}` definieren, was eine größere Flexibilität bietet. Der vorherige Standardpfad `/content/dam/fmdita-outputs` ist nicht mehr erforderlich.

Alle Ausgabepfade, die mit den globalen Ordnerprofilvorgaben verknüpft sind, werden automatisch migriert, um die neue Basisausgabepfadvariable zu nutzen. Bei benutzerdefinierten Ordnerprofilen erfolgt die Migration jedoch nicht automatisch. Es wird empfohlen, sich an das Customer Success-Team zu wenden, um Unterstützung zu erhalten.

Weitere Informationen finden Sie unter [Grundlegendes zu Ausgabevorgaben](../user-guide/generate-output-understand-presets.md).

## Verbesserungen der Benutzeroberfläche in der Editor-Symbolleiste und Benutzereinstellungen

Mit dieser Version wurden die Einstellungen in **Benutzereinstellungen** auf der Startseite für die Registerkarten „Allgemein“ und „Erscheinungsbild“ neu strukturiert. Dazu gehört das Umbenennen der Beschriftung **Öffnen der Voreinstellungen für**) und das Verschieben des Umschalters Leerzeichen ohne Unterbrechung in die Editor-Symbolleiste.

Darüber hinaus sind in der Editor-Symbolleiste einige Umschalter für den Schnellzugriff zum Aktivieren oder Deaktivieren von Änderungen, Tags und nicht umbrechenden Leerzeichen jetzt unter der Option **Anzeigen** im Dropdown-Menü gruppiert, um die Benutzerfreundlichkeit zu verbessern.

Weitere Informationen finden Sie unter [Symbolleiste im Editor](../user-guide/web-editor-toolbar.md#menu-dropdown).
