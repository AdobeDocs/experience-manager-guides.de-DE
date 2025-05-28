---
title: Versionshinweise zu | Neue Funktionen in Adobe Experience Manager Guides Version 2025.06.0
description: Erfahren Sie mehr über die neuen und erweiterten Funktionen der Version 2025.06.0 von Adobe Experience Manager Guides
role: Leader
source-git-commit: 147bd8cce875178f94dae5742bc6573b51f24d3a
workflow-type: tm+mt
source-wordcount: '467'
ht-degree: 3%

---

# Neue Funktionen in der Version 2025.06.0 (Juni 2025)

Dieser Artikel behandelt die neuen und erweiterten Funktionen, die mit der Version 2025.06.0 von Adobe Experience Manager Guides as a Cloud Service eingeführt wurden.

Eine Liste der in dieser Version behobenen Probleme finden Sie im Artikel [Behobene Probleme in Version 2025.06.0](fixed-issues-2025-06-0.md).

Erfahren Sie mehr [Upgrade-Anweisungen für die Version 2025.06.0](../release-info/upgrade-instructions-2025-06-0.md).

## Temporäre Dateien für die veröffentlichte Ausgabe enthalten jetzt Autoren- und Veröffentlichungs-URLs in einer neuen Konfigurationsdatei

Die neuesten Veröffentlichungsverbesserungen für Experience Manager Guides fügen jetzt eine neue `system_config.json`-Datei zu den temporären Dateien hinzu, die beim Veröffentlichen von HTML-, PDF- und JSON-Ausgaben mit DITA-OT generiert wurden, sowie die native PDF-Ausgabe. Diese Datei wird automatisch in den Veröffentlichungsauftrag aufgenommen und kann auch über temporäre Dateien aufgerufen werden, wenn Sie die Option **Temporäre Dateien beibehalten** für die Voreinstellungen aktivieren und die Ausgabe generieren.

Die `system_config.json`-Datei enthält wichtige Instanzdetails wie die Autoren-URL, die lokale URL und die Veröffentlichungs-URL, die einen klareren Kontext bieten und die Rückverfolgbarkeit der heruntergeladenen URLs verbessern.

Weitere Informationen finden Sie unter [Grundlegendes zu Ausgabevorgaben](../user-guide/generate-output-understand-presets.md).

## Eingabeaufforderung für Sitzungs-Timeout, um versehentlichen Inhaltsverlust zu verhindern

Eine Popup-Meldung informiert Sie jetzt darüber, wenn Ihre Adobe Experience Manager-Sitzung abläuft und Sie aufgrund von Inaktivität abgemeldet werden. Diese Nachricht wird ausgelöst, wenn Sie versuchen, Inhalte in Experience Manager Guides zu bearbeiten, nachdem die Sitzung beendet wurde. Die Funktion trägt dazu bei, das Risiko des Verlusts nicht gespeicherter Arbeit zu reduzieren, und verbessert die Zuverlässigkeit und Fließfähigkeit des Erlebnisses insgesamt, auch in Zeiträumen der Inaktivität.

![](assets/sign-out-prompt.png)

Weitere Informationen zur [Sitzungs-Zeitüberschreitungsaufforderung](../user-guide/session-timeout-prompt.md) in Experience Manager Guides.

## Verbesserte Download-Optionen für Karten im Editor

Experience Manager Guides führt eine neue Option **Verwenden tatsächlicher Dateinamen** im Dialogfeld **Karte herunterladen** ein. Wenn Sie jetzt Zuordnungsdateien herunterladen, können Sie die ursprünglichen Dateinamen anstelle der standardmäßigen UUIDs beibehalten, was die Erkennung und Verwaltung Ihrer Dateien erheblich erleichtert. Diese Option ist nur verfügbar, wenn Sie **Dateihierarchie beibehalten** auswählen. Sie ist deaktiviert, wenn Sie **Dateihierarchie reduzieren** auswählen, was Ihnen mehr Flexibilität bei der Organisation Ihrer heruntergeladenen Karten gibt.

Weitere Informationen finden Sie unter [Dateien ](../user-guide/authoring-download-assets.md#download-a-dita-map-file-from-the-editor).

![](assets/download-map-dialog-new.png){width="300" align="left"}


## Verbesserte `navref` im Editor

Die neuesten Verbesserungen am Editor verbessern die Handhabung von `navref` in einer DITA-Zuordnung. Wenn Sie nun ein `navref` Element zu einer Karte hinzufügen, wird das Dialogfeld **Pfad auswählen** geöffnet, in dem Sie einfach die Kartenverweise auswählen können, die als Navigations-Links in Ihre Karte aufgenommen werden sollen. Nach dem Hinzufügen wird der Titel der hinzugefügten Zuordnung sowohl in der Autoren- als auch in der Layout-Ansicht angezeigt, wodurch die enthaltene Navigation beim Authoring besser sichtbar wird.  Darüber hinaus wird das hinzugefügte `navref` automatisch aufgelöst, um die referenzierte Zuordnung im Editor anzuzeigen.

Weitere Informationen finden Sie unter [Navigationsverweise hinzufügen](../user-guide/map-editor-other-features.md#add-navigation-references).
