---
title: Editor-Einstellungen
description: Erfahren Sie, wie Sie Editor-Einstellungen in AEM Guides konfigurieren.
feature: Web Editor
role: User
source-git-commit: 3f38264b6ce09366d07cdd302c9c53e8abcf4b7c
workflow-type: tm+mt
source-wordcount: '467'
ht-degree: 0%

---

# Editor-Einstellungen

>[!INFO]
>
> Dieser Artikel gilt für den neuen Editor. Wenden Sie sich an das AEM Guides Customer Success-Team , um den neuen Editor in Ihrer Umgebung aktivieren zu lassen.

Die Editor-Einstellungen bieten ein zentralisiertes Konfigurationsbedienfeld, mit dem Sie das Editor-Verhalten auf individueller Autorenebene anpassen können. Sie bietet mehr Flexibilität, Konsistenz und Kontrolle während des Authoring-Prozesses.

Mit diesem zentralen Einstellungsbedienfeld können Sie wichtige Editor-Voreinstellungen von einem zentralen Ort aus verwalten, wodurch die Notwendigkeit verstreuter oder manueller Konfigurationen reduziert wird. Die Editor-Einstellungen können über die Registerkarte **Weitere Aktionen** aufgerufen werden.

![Editor-Einstellungen](./images/conf-editor-settings.png){width="650"}

## Unterstützte Konfigurationsoptionen

Je nach Ihren Voreinstellungen können Sie die folgenden Optionen aktivieren oder deaktivieren:

![Editor-Einstellungen](./images/editor-settings-dialog.png){width="350"}

- **Leerzeichen ohne Unterbrechung**: Aktivieren Sie diese Option, um beim Bearbeiten im Editor einen Indikator für die Leerzeichen ohne Unterbrechung anzuzeigen. Er ist nur in der Autorenansicht für DITA-Themen und DITA-Zuordnungen sichtbar
- **XML-Kommentare**: Ermöglicht es Autoren, XML-Kommentare direkt im Autorenmodus anzuzeigen, zu bearbeiten und einzufügen, um eine bessere Sichtbarkeit innerhalb des Inhalts zu erzielen. Wenn diese Option aktiviert ist, können Autoren XML-Kommentare direkt im Inhalt im Autorenmodus selbst anzeigen, einfügen, bearbeiten und löschen, was das Hinzufügen von kontextuellen Anmerkungen für Mitwirkende erleichtert. Wenn diese Option deaktiviert ist, sind XML-Kommentare im Autorenmodus ausgeblendet und können nicht im Autorenmodus eingefügt oder geändert werden, um ein saubereres Authoring-Erlebnis für Benutzende zu gewährleisten, die sie nicht benötigen. Sie können weiterhin XML-Kommentare im Quellmodus mithilfe der `<!-- test comment -->`-Syntax anzeigen und erstellen.

  ![XML-Kommentare konfigurieren](./images/config-xml-comments.png){width="650"}

- **Tags**: Steuert die Sichtbarkeit von Tags im Editor. Wenn diese Option aktiviert ist, werden im Inhalt strukturelle Tags angezeigt, sodass Autoren die zugrunde liegende DITA-Struktur anzeigen und verwalten können. Wenn diese Option deaktiviert ist, werden diese Tags ausgeblendet, um ein saubereres und fokussierteres Authoring-Erlebnis zu bieten.

  ![Tags konfigurieren](./images/config-tags.png){width="650"}

  Wenn **Einstellungen** Tags anzeigen) aktiviert sind, können Sie auch **Attribute anzeigen** aktivieren, um die mit einem Element verknüpften Attribute anzuzeigen und zu validieren. Wenn einem Element mehr als drei Attribute zugeordnet sind, wird ein Zählindikator angezeigt. Wenn Sie den Mauszeiger über den Indikator bewegen, wird die vollständige Liste der auf dieses Element angewendeten Attribute angezeigt.

  ![Tags mit Attributen konfigurieren](./images/config-tags-attributes.png) {width="650"}

- **Menü „Schnelleinfügung“ im Editor**: Ermöglicht das direkte Hinzufügen von Elementen während der Bearbeitung im Autorenmodus an der Cursorposition ohne Navigieren zur Symbolleiste. Häufig verwendete Elemente können auch in den „Favoriten **konfiguriert werden,** den Zugriff zu beschleunigen. Das Schnelleinfügemenü steht direkt im Editor zur Verfügung, wenn Sie unter Windows **Strg + /** oder bei macOS **Befehl + /** auf die Cursorposition drücken.

  ![Menü „Schnelleinfügung“ im Editor](./images/quick-insert-menu-in-editor.png){width="650"}

  Sie können nach Elementen suchen und diese zu Ihren Favoriten hinzufügen, zuvor hinzugefügte Elemente entfernen und sie mit einfachem Drag-and-Drop neu anordnen. Zu den Favoriten gehören die am häufigsten verwendeten Elemente. Die hier festgelegte Reihenfolge wird beim Zugriff über den Editor im Menü „Schnelleinfügung“ angezeigt.




