---
title: Versionshinweise zu | Es wurden Probleme in Adobe Experience Manager Guides Version 2025.06.0 behoben
description: Erfahren Sie mehr über die Fehlerbehebungen in der Version 2025.06.0 von Adobe Experience Manager Guides as a Cloud Service.
source-git-commit: 78d8896982ff73e954de6d6daa9832faf30ed3b3
workflow-type: tm+mt
source-wordcount: '514'
ht-degree: 4%

---

# Es wurden Probleme in der Version 2025.06.0 behoben

Dieser Artikel behandelt die in verschiedenen Bereichen der Version 2025.06.0 von Adobe Experience Manager Guides as a Cloud Service behobenen Fehler.

Weitere Informationen zu den neuen Funktionen und Verbesserungen finden Sie unter [Neue Funktionen in Version 2025.06.0](whats-new-2025-06-0.md).

Erfahren Sie mehr [Upgrade-Anweisungen für die Version 2025.06.0](upgrade-instructions-2025-06-0.md).

## Authoring

- Beim Öffnen einer DITA-Zuordnung mit aktivierter Unified Shell wird der Editor gelegentlich aktualisiert. (GUIDES-26919)
- Wenn JCR-Sitzungsverbindungen beim Aktualisieren oder Erstellen von Themen nicht geschlossen werden, führt dies zu Speicherlecks und Service-Ausfallzeiten. (GUIDES-26282)
- Durch Ziehen der Spalten wird deren Breite von Prozentsatz zu Pixelwerten geändert, was zu verzerrten oder falsch ausgerichteten Tabellen führt.(GUIDES-23128)
- Wenn Inhalte in ein `code block` eingefügt werden oder Leerzeichen im `code block` hinzugefügt werden und die Ansicht gewechselt wird, gehen die Leerzeichen verloren. (GUIDES-27478)
- Beim Hinzufügen einer Zuordnung zum `bookmap` wird diese in `fmditatopicrefs` anstatt in `fmditamaprefs` gespeichert. (GUIDES-25480)
- Das **„Bild einfügen** kann auf einem hochauflösenden oder auszoomten Bildschirm nicht korrekt gerendert werden, wodurch der Bildtitel und die alternativen Textfelder verschwinden. (GUIDES-26459)


## Publishing

- Die native PDF-Veröffentlichung wird auf unbestimmte Zeit fortgesetzt, wenn der DITA-Inhalt über einen Weblink verfügt, ohne dass der Umfang wie `external` vorhanden ist. (GUIDES-26434)
- Die Veröffentlichung nativer PDFs und AEM-Sites verzögert sich und wird in die Warteschlange gestellt, wenn Fehler im Inhalt auftreten. (GUIDES-26516)
- Beim Erstellen einer neuen Baseline mit einer großen Anzahl von Kennzeichnungen wird verhindert, dass alle Kennzeichnungen abgerufen werden. (GUIDES-16232)
- Beim Generieren von AEM Site-Seiten mit Titeln, die mehrere Wörter enthalten, die durch Leerzeichen getrennt sind, zeigt der Zuordnungstitel Bindestriche anstelle von Leerzeichen an. (GUIDES-27903)
- Bei der nativen PDF wird ein ungültiger Metadaten-Eigenschaftsname nicht aufgelöst und wie `unresolved property name` in **Dokumenteigenschaften** angezeigt. (GUIDES-25680)
- Mehrzeiliger Text in `codeblock` verursacht Probleme mit Textüberläufen während der PDF-Generierung. (GUIDES-15541)
- Beim Hinzufügen von Zuordnungen zur Zuordnungssammlung werden andere Assets als Zuordnungen (z. B. Themen usw.) angezeigt und die übersetzten Zuordnungssprachen werden ebenfalls nicht ordnungsgemäß sortiert.(GUIDES-25085)


## Überprüfung

- Die Dokumentansicht in der Überprüfungs-Benutzeroberfläche umschließt den Inhalt für einige Bildschirmgrößen nicht, sodass Benutzende horizontal scrollen müssen, um den gesamten Inhalt anzuzeigen. (GUIDES-25292)


## Bekannte Probleme

Adobe hat das folgende bekannte Problem in Version 2025.06.0 identifiziert:

- Wenn Sie die Option Suchen und Ersetzen verwenden, können nach dem Anwenden des Vorgangs Einmaliges Vorkommen ersetzen auf eine Datei im Bedienfeld Suchen und Ersetzen keine weiteren Aktionen ausgeführt werden. (GUIDES-28930)

- Wenn in einem Ordnerprofil ein bereits indiziertes Asset aus der Benutzeroberfläche gelöscht wird, wird der entsprechende indizierte Pfad nicht entfernt, und der Versuch einer Neuindizierung schlägt mit einer Fehlermeldung fehl. (GUIDES-29147) <br>**Problemumgehung:** Sie müssen den veralteten Pfad, der nicht mehr vorhanden ist, entfernen, bevor Sie die Neuindizierung starten.

- Wenn eine Zuordnung zyklische Abhängigkeiten enthält und Sie die Zuordnungsvorschau öffnen, ist der Zugriff auf die Ansichten Source, Author und Layout erst möglich, wenn die Seite aktualisiert wird. (GUIDES-28334) <br>**Problemumgehung:** Sie müssen die Seite aktualisieren, um den Zugriff auf diese Ansichten wiederherzustellen.
