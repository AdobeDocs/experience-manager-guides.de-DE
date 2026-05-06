---
title: Versionshinweise | Neue Funktionen in Adobe Experience Manager Guides Version 2026.05.0
description: Erfahren Sie mehr über die neuen und erweiterten Funktionen der Version 2026.05.0 von Adobe Experience Manager Guides
role: Leader
source-git-commit: b04438c1036248c40e002c1a56b6b68e654e7748
workflow-type: tm+mt
source-wordcount: '1043'
ht-degree: 0%

---

# Neue Funktionen in der Version 2026.05.0 (Mai 2026)

Dieser Artikel behandelt die neuen und erweiterten Funktionen, die mit der Version 2026.05.0 von Adobe Experience Manager Guides as a Cloud Service eingeführt wurden.

Eine Liste der in dieser Version behobenen Probleme finden Sie unter [Behobene Probleme in Version 2026.05.0](fixed-issues-2026-05-0.md).

Erfahren Sie mehr [Upgrade-Anweisungen für die Version 2026.05.0](../release-info/upgrade-instructions-2026-05-0.md).

## Einführung in Editor 2.0

Editor 2.0 (auch als „Neuer Editor“ bezeichnet) bietet vereinfachtes Authoring, sodass Sie Inhalte durch ein intuitiveres Erlebnis sowohl im Tag- als auch im Nicht-Tag-Modus effizienter erstellen können. Die -Version bietet eine verbesserte Leistung durch schnelleres Laden von Seiten und eine reibungslosere Bearbeitung selbst für große und komplexe Themen. Außerdem wird durch die Schließung wichtiger Authoring-Lücken, insbesondere im Bereich Navigation und Cursor-Verhalten, die Stabilität verbessert. Darüber hinaus bietet eine moderne Benutzeroberfläche eine aktualisierte und benutzerfreundliche Benutzeroberfläche, die Funktionalität und Benutzerfreundlichkeit in Einklang bringt. Weitere Informationen finden Sie unter [Einführung in den Editor](../user-guide/web-editor.md).

Im Folgenden finden Sie ein Übersichtsvideo zu den Funktionen von Editor 2.0.

>[!VIDEO](https://video.tv.adobe.com/v/3484007)


>[!NOTE]
>
> Wenden Sie sich an das AEM Guides Customer Success-Team , um den Editor 2.0 in Ihrer Umgebung aktivieren zu lassen.

Im Folgenden finden Sie Verbesserungen, die das Authoring einfacher und effizienter machen.

### Neu gestaltete Benutzeroberfläche und Erlebnis

Eine aktualisierte Benutzeroberfläche verbessert die allgemeine Benutzerfreundlichkeit, wodurch die Navigation und Inhaltserstellung intuitiver und konsistenter werden.

- **Umfassenderes CSS für Elemente im Autoren- und Vorschaumodus**: Das erweiterte standardmäßige CSS für Elemente bietet einen verbesserten Stil und eine bessere visuelle Konsistenz sowohl für den Autoren- als auch für den Vorschaumodus.

  ![](assets/rich-css.png){width="650"}

- **Unterstützung dunkler Designs**: Die Unterstützung für dunkle Designs im Inhaltsbearbeitungsbereich verbessert das Authoring-Erlebnis für Benutzende, die lieber mit einer dunklen Oberfläche arbeiten.

  ![](assets/dark-theme.png){width="650"}

- **Konsolidierte Editor-Einstellungen auf Benutzerebene**: Ein neues zentralisiertes Einstellungsbedienfeld, das Autorinnen und Autoren eine bessere Kontrolle über das Editor-Verhalten bietet, sodass Benutzerinnen und Benutzer Voreinstellungen leichter von einem einzigen Ort aus verwalten können. Zu den Konfigurationsoptionen gehören die Möglichkeit, Folgendes zu aktivieren/deaktivieren:

   - Geschützte Leerzeichen im Autorenmodus
   - Einstellungen für die Tag-Sichtbarkeit mit oder ohne Attribute
   - XML-Kommentare im Autorenmodus
   - Menü „Schnelleinfügung“ zum Einfügen von Elementen im Editor

  ![](assets/editor-settings-dialog.png){width="350"}


  Weitere Informationen zum Konfigurieren der Editor-Einstellungen finden Sie unter [Editor-Einstellungen](../user-guide/config-editor-settings.md).

- **Bessere Darstellung bedingter Inhalte im Autorenmodus**: Bedingte Inhalte werden im Autorenmodus klarer angezeigt, sodass Autoren Varianten besser identifizieren und verwalten können. Weitere Informationen finden Sie [Bedingungen](../user-guide/web-editor-left-panel.md#conditions) im linken Editor-Bereich.

  ![](assets/multiple-conditions-applied_cs-editor-2-0.png){width="650"}


### Verbesserte Authoring-Funktionen

Bietet verbesserte Tools und Flexibilität, um die Erstellung und Bearbeitung von Inhalten zu optimieren.

- **Attribute zusammen mit Elementen im Tag-Modus anzeigen**: Autoren können jetzt Elementattribute mit dem Tag-Modus anzeigen, was eine bessere Sichtbarkeit und Kontrolle über strukturierte Inhalte bietet. Um diese Funktion zu konfigurieren, rufen Sie [Editor-Einstellungen](../user-guide/config-editor-settings.md) auf.

  ![](assets/config-tags-attributes.png){width="650"}

- **Menü „Schnelleinfügung**: Ermöglicht das direkte Hinzufügen von Elementen während der Bearbeitung im Autorenmodus an der Cursorposition, ohne zur Symbolleiste zu navigieren. Häufig verwendete Elemente können auch im Abschnitt Favoriten über die Editor-Einstellungen konfiguriert werden, um den Zugriff zu beschleunigen. Weitere Informationen finden Sie unter [Themen bearbeiten](../user-guide/web-editor-edit-topics.md).

  ![](assets/quick-insert-menu.png){width="650"}

- **Anzeige, Bearbeitung und Einfügen von XML-Kommentaren im Autorenmodus**: Ermöglicht es Autoren, XML-Kommentare direkt im Autorenmodus anzuzeigen, zu bearbeiten und einzufügen, um die Sichtbarkeit innerhalb des Inhalts zu verbessern. Um diese Funktion zu konfigurieren, rufen Sie [Editor-Einstellungen](../user-guide/config-editor-settings.md) auf.

  ![](assets/config-xml-comments.png){width="650"}

- **Nebeneinander-Modus**: Ermöglicht die gleichzeitige Anzeige des Authoring- und Source-Modus, wobei beide Ansichten perfekt synchronisiert bleiben, um Inhaltsänderungen leichter vergleichen, bearbeiten und validieren zu können. Weitere Informationen finden Sie unter [Editor-Ansichten](../user-guide/web-editor-views.md).

  ![](assets/side-by-side-editor-2-0.png){width="650"}

- **Verbessertes Tabellen-Authoring**: Verbessert das allgemeine Erlebnis beim Erstellen von Tabellen durch intuitivere und effizientere Interaktionen beim Erstellen und Verwalten von Tabellen.

   - Fließende und intuitive Interaktionen: Einfaches Einfügen von Zeilen und Spalten sowie Drag-and-Drop-Unterstützung für die Neuanordnung von Zeilen und Spalten.
   - Kontextuelle Symbolleiste : Greifen Sie auf tabellenspezifische Aktionen wie Formatierung, Ausrichtung, Zusammenführung und andere zusätzliche Aktionen direkt in der Tabelle zu.
   - Konfigurieren von Tabellen: Mehrere Zeilen oder Spalten in einer Aktion hinzufügen, wodurch sich wiederholende Schritte reduzieren und die Effizienz verbessert wird.

  ![](assets/config-table.png){width="650"}

  Weitere Informationen finden Sie unter [Arbeiten mit Tabellen](../user-guide/web-editor-other-features.md#work-with-tables-in-the-new-editor).

### Verbesserte Leistung bei großen Themen

Der neue Editor verbessert das Erlebnis bei der Arbeit mit großen und komplexen Themen durch schnelleres Rendern von Inhalten, zuverlässigere Funktionen zum Rückgängigmachen und Wiederholen und eine unsaubere Markierung, um nicht gespeicherte Änderungen deutlich anzuzeigen.

## Greifen Sie auf den Pfad und die UUID von Verweisen in Dateien über das Bedienfeld Inhaltseigenschaften zu

Jetzt können Sie **Link-Pfad** verwenden, um den relativen Pfad der ausgewählten Referenz anzuzeigen, und **Link-UUID**, um die eindeutige Kennung im Bedienfeld Inhaltseigenschaften anzuzeigen. Sie können auch den vollständigen absoluten Pfad und die zugehörige UUID direkt aus der Benutzeroberfläche kopieren, indem Sie die Symbole neben Link-Pfad und Link-UUID verwenden. Dies erleichtert das Nachverfolgen und Wiederverwenden verknüpfter Assets.

Weitere Informationen finden Sie unter [Inhaltseigenschaften](../user-guide/web-editor-right-panel.md#content-properties).


## Verbesserungen bei Überprüfungen

Im Rahmen dieser Version wurden die folgenden Verbesserungen vorgenommen:

- Sie können jetzt **automatische Erinnerungen** aktivieren, um AEM-Benachrichtigungen und E-Mail-Erinnerungen für Prüfer zu planen, und zwar sowohl vor als auch nach dem Fälligkeitsdatum einer Prüfungsaufgabe. Sie können jeweils mehrere Erinnerungen konfigurieren, wobei überfällige Erinnerungen in einer definierten Reihenfolge gesendet und überfällige Erinnerungen ausgelöst werden, nachdem die Aufgabe basierend auf dem konfigurierten Erinnerungszeitplan als überfällig markiert wurde. Weitere Informationen zum Konfigurieren der Erinnerungen für Prüfungsaufgaben finden Sie unter [Senden von Themen zur Überprüfung](../user-guide/review-manage-tasks-review-dashboard.md).

- Reviewer können jetzt auf den Versionsverlauf für zu überprüfende Themen zugreifen, sodass sie zuvor überprüfte und aktualisierte Versionen desselben Themas in vorherigen Prüfungsaufgaben anzeigen und vergleichen können. Auf diese Weise können Validierungsverantwortliche Änderungen, die seit früheren Überprüfungszyklen vorgenommen wurden, validieren und die Kontinuität gewahrt werden, indem sie Kommentare, Beschriftungen und andere zugehörige Details im aktuellen Überprüfungskontext überprüfen. Weitere Informationen finden Sie unter [Versionsverlauf für den Reviewer](../user-guide/review-topics.md#version-history-for-the-reviewer).

## Neue grundlegende Erfahrung in Experience Manager Guides eingeführt

>[!NOTE]
>
> Wenden Sie sich an das AEM Guides Customer Success-Team , um neue Baseline in Ihrer Umgebung aktivieren zu lassen.

Die Verwaltung großer, komplexer Baselines ist jetzt schneller, stabiler und einfacher zu skalieren mit dem **neuen Baseline-Erlebnis**, das auf einer neu gestalteten Baseline-Architektur basiert. Diese Aktualisierung löst langjährige Leistungs- und Zuverlässigkeitsprobleme und bewahrt gleichzeitig bestehende Workflows.

Dieses Update ist als Beta-Verbesserung verfügbar und bietet Lösungen für gängige Probleme wie langsames Laden, inkonsistente Baseline-Status und eingeschränkte Verwaltbarkeit, indem es ein schnelleres, stabileres und vorhersehbareres Baseline-Erlebnis mit zusätzlicher Unterstützung für Automatisierung und umfangreiche Baseline-Vorgänge bereitstellt. Die wichtigsten Verbesserungen sind:

- Verbesserte Leistung und Skalierbarkeit
- Bessere Benutzeroberflächen- und Backend-Konsistenz
- Erweiterte Filter-, Navigations- und Abhängigkeitssichtbarkeit

Weitere Informationen finden Sie unter [Neues Baseline-Erlebnis (Beta) in Experience Manager Guides](../user-guide/web-editor-baseline-v2.md).






