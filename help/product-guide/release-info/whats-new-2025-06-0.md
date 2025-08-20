---
title: Versionshinweise zu | Neue Funktionen in Adobe Experience Manager Guides Version 2025.06.0
description: Erfahren Sie mehr über die neuen und erweiterten Funktionen der Version 2025.06.0 von Adobe Experience Manager Guides
role: Leader
exl-id: 48f27aa6-d870-4228-8e62-db81699a25f7
source-git-commit: d418ffb254b11430509609b91e0174690815cf73
workflow-type: tm+mt
source-wordcount: '409'
ht-degree: 4%

---

# Neue Funktionen in der Version 2025.06.0 (Juni 2025)

Dieser Artikel behandelt die neuen und erweiterten Funktionen, die mit der Version 2025.06.0 von Adobe Experience Manager Guides as a Cloud Service eingeführt wurden.

Eine Liste der in dieser Version behobenen Probleme finden Sie im Artikel [Behobene Probleme in Version 2025.06.0](fixed-issues-2025-06-0.md).

Erfahren Sie mehr [Upgrade-Anweisungen für die Version 2025.06.0](../release-info/upgrade-instructions-2025-06-0.md).

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

## Leistungsverbesserungen im KI-Assistenten

Die Version führt Verbesserungen an der KI-Assistenten-Backend-Engine ein, die eine verbesserte Leistung und größere Stabilität bietet. So aktivieren Sie diese Aktualisierung und verwenden weiterhin die Hilfe des KI-Assistenten:

- Aktualisieren Sie die `chat.url`, um die neue Endpunkt-URL widerzuspiegeln.
- Fügen Sie in Cloud Manager eine neue `GUIDES_AI_SITE_ID` hinzu.

Weitere Informationen finden Sie unter [Konfigurieren des KI-Assistenten](../cs-install-guide/conf-smart-suggestions.md).

