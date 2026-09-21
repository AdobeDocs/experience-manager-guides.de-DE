---
title: Versionshinweise | Behobene Probleme in Adobe Experience Manager Guides 5.2.0 Service Pack 1
description: Erfahren Sie mehr über die Fehlerbehebungen in Version 5.2.0 Service Pack 1 von Adobe Experience Manager Guides
role: Leader
TQID: https://experienceleague.adobe.com/HEWV5RxPUfqUYf6m6kQW-fU-LiAM0UFGbfzKjtOCZxk
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
    internal-label: Experience Manager Guides
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
    internal-label: Experience Manager
feature_v2:
  - id: a3bd6397-2eb2-4908-a61c-226e26855dca
    internal-label: Publishing
role_v2:
  - id: f8a45b24-4be7-4f1b-909b-60d06b483a20
    internal-label: Leader
source-git-commit: 429d2abf0aad8722ac30c08c9c9d134be0759ff4
workflow-type: tm+mt
source-wordcount: '1181'
ht-degree: 0%
---
# Es wurden Probleme in Version 5.2.0 Service Pack 1 (September 2026) behoben

Dieser Artikel behandelt die in verschiedenen Bereichen von Version 5.2.0 Service Pack 1 von Adobe Experience Manager Guides behobenen Fehler.

Erfahren Sie mehr über [Upgrade-Anweisungen für die Version 5.2.0 Service Pack 1](upgrade-instructions-5-2-0-sp1.md).

## Authoring

- Auf Bildschirmen mit niedriger Auflösung wird das Dialogfeld Keyword einfügen beim Einfügen eines Keywords aus der Symbolleiste nicht angezeigt, während es bei Verwendung der Option **Mehr** wie erwartet geöffnet wird. (GUIDES-48304)
- Durch Einfügen eines Querverweises mit der Option **Weblink** wird ein `scope=local` Link hinzugefügt und der `href` geändert, anstatt wie erwartet einen `scope=external` Link einzufügen. (GUIDES-48457)
- Das Speichern einer referenzierenden Zuordnung führt zu einem fehlerhaften Verweis, anstatt zur richtigen Zuordnung aufgelöst zu werden, wenn ein Autor die referenzierte Zuordnung verschiebt, während ein anderer Autor gleichzeitig einen Verweis zu ihr in einer nicht gespeicherten Zuordnung hinzufügt. (GUIDES-47467)
- Zum Wörterbuch hinzugefügte alphanumerische Begriffe werden von der AEM-Rechtschreibprüfung weiterhin gekennzeichnet, anstatt ignoriert zu werden. (GUIDES-48587)
- Wenn Sie den Fokus zwischen den Feldern **Breite** und **Höhe** im Dialogfeld Bildeigenschaften mithilfe von einheitsbasierten Größen wie `in`, `mm` oder `px` umschalten, erhöhen sich die Werte schrittweise, anstatt stabil zu bleiben. (GUIDES-45929)

## Editor 2.0

- Leerzeichen, die unmittelbar vor dem Löschen eines Inline-Tags in einer Tabellenzelle eingegeben `<entry>`. (GUIDES-49144)
- Beim Einfügen eines Elements an der `tgroup` Position wird eine **#text-Warnung angezeigt** die verhindert, dass eine normale Tabelle an dieser Position eingefügt wird. (GUIDES-47446)
- Beim Kopieren einer Tabelle aus einer Excel-Tabelle und Einfügen in den neuen Editor wird der gesamte kopierte Zelleninhalt in eine einzige Tabellenzelle eingefügt, anstatt ihn auf die entsprechenden Zellen zu verteilen. (GUIDES-47435)
- Eine benutzerdefinierte Schaltfläche **Als PDF exportieren** die über `editor_toolbar.json` konfiguriert wurde, wird gerendert und bleibt im Vorschaumodus klickbar, führt jedoch beim Klicken keine Aktion aus. (GUIDES-47402)
- Das Öffnen bestimmter Themen, die Tabellen enthalten, fügt ein unerwartetes `<foreign>`-Tag mit zwei neuen Spalten hinzu, auch wenn am Thema keine Änderungen vorgenommen wurden. (GUIDES-46748)
- Wenn eine MathML-Gleichung als `conref` eingefügt wird, wird sie nicht korrekt dargestellt. (GUIDES-46601)
- MathML- und SVG-Elemente rendern nicht den vollständigen Satz von Attributen, sodass benutzerdefinierte CSS-Klassen und auf diese Elemente angewendete bedingte Attribute beschädigt werden. (GUIDES-46371)
- Das **scale**-Attribut gilt nicht für Bilder in der Autorenansicht. (GUIDES-45996)
- Beim Anwenden eines `scale`-Attributs auf eine Tabelle wird die Tabelle im Autoren- und Vorschaumodus nicht in der konfigurierten Größe gerendert. (GUIDES-45984)
- Durch Einfügen von Bildern, die aus externen Quellen wie Paint oder dem Snipping Tool kopiert wurden, wird das Bild nicht in das Thema eingefügt. (GUIDES-45983)
- Durch Kopieren und Einfügen von `<keywords>` innerhalb von `<topicmeta>` innerhalb eines `<keydef>` oder einer `<topicref>` werden die Keywords in unerwünschte fremde Tags eingefügt. (GUIDES-45800)
- In der Tag-Ansicht einer Tabelle wird durch Drücken der Nach-oben-Taste bei der Positionierung des Cursors in der Zelle direkt unter einem reduzierten Einstiegs-Tag das reduzierte Tag übersprungen und der Cursor an den Anfang des Dokuments bewegt. (GUIDES-45408)
- Wenn Sie einen Vorgang über die kontextuelle Symbolleiste der Tabelle ausführen, wird die Symbolleiste unerwartet geschlossen, wodurch nachfolgende Tabellenvorgänge unterbrochen werden. (GUIDES-45405)
- Die **MathML bearbeiten**-Option wird im schreibgeschützten Modus oder beim Auschecken einer Datei durch einen anderen Benutzer falsch angezeigt, sodass Benutzende MathML-Inhalte aktualisieren können, obwohl die Datei nicht bearbeitbar sein sollte. (GUIDES-45172)
- Nach Verwendung von **Einfügen nach** oder **Einfügen vor** in der Gliederungsansicht oder im Breadcrumb wird der Cursor an eine beliebige Position verschoben, anstatt innerhalb des neu hinzugefügten Tags. (GUIDES-45147)
- Wenn Sie bei aktivierter Tag-Ansicht per Drag-and-Drop Inhalte mit partiellen XML- oder DITA-Tags auswählen, bleiben unerwünschte verwaiste Tags zurück, was zu falschen Inhalten oder Ansichten führt. (GUIDES-28191)

## Asset-Management

- Die Versionsbereinigung kann in mehreren Szenarien nicht abgeschlossen werden, darunter bestimmte Dateitypen, Assets mit fehlenden Metadaten und große Berichte, anstatt die Bereinigung abzuschließen und einen genauen Bericht zu generieren. (GUIDES-43453)

## Publishing

- Nicht englische Dateinamen in den generierten Seitennamen werden durch Bindestriche ersetzt, sodass es beim Veröffentlichen der AEM Sites-Ausgabe mit der Legacy-Komponentenzuordnung schwierig ist, das zugehörige Thema oder die zugehörige Datei zu identifizieren. (GUIDES-48387)
- JARs für anfällige `jackson-databind` (Version 2.9.8) im Paket mit AEM Guides im DITA-OT-Paket werden identifiziert. (GUIDES-43081)

## Überprüfung

- Beim Öffnen **nebeneinanderliegenden** im Kommentarbedienfeld wird die Arbeitskopie neben der kommentierten Version angezeigt, die Bereiche werden jedoch nicht horizontal synchronisiert gescrollt, und durch Klicken auf einen Kommentar wird der Cursor nicht zum entsprechenden Text bewegt. (GUIDES-44083)

## Plattform

- Wenn Sie `scope="external"` für einen Verweis auf DAM-Inhalte in einem Thema oder einer Zuordnung verwenden, wird der relative Pfad des Assets durch eine GUID ersetzt. (GUIDES-35605)
- Bei Inhalten, die vor der UUID-Migration erstellt wurden, werden beim Herunterladen einer Zuordnung mit den Optionen **Dateihierarchie beibehalten** und **Tatsächlichen Dateinamen verwenden** die `href` von `topicref`-, `xref`- und `conref`-Elementen mit `scope="external"` in GUID-basierte Dateinamen konvertiert, anstatt die ursprünglichen relativen Dateipfade beizubehalten. Daher sind die externen Verweise fehlerhaft. (GUIDES-46526)
- Beim Hochladen von Assets über die Assets-Benutzeroberfläche wird der Upload-Status nicht angezeigt. (GUIDES-7207)

## Bekannte Probleme

- Beim Durchführen eines Überprüfungsvorgangs innerhalb eines Codeblocks wird beim ersten Versuch eine Warnung **Vorgang nicht zulässig** angezeigt, der Vorgang ist jedoch erfolgreich, wenn er wiederholt wird. (GUIDES-56749)
- Wenn eine Prüfungsaufgabe für Inhalte erstellt wird, die eine `code block` enthalten, wird die durchgestrichene Formatierung nach dem Import nicht korrekt angewendet und die hervorgehobenen Inhalte fehlen in der parallelen Vergleichsansicht. (GUIDES-56811)
- In einigen Fällen werden auf der Registerkarte **Themenliste** im Bedienfeld Berichte keine Ergebnisse angezeigt, selbst wenn die Karte mehrere Themen enthält. (GUIDES-56893) <br> **Problemumgehung:** Indizieren Sie den betroffenen Inhalt neu, um die Beziehungen der übergeordneten Zuordnung neu zu erstellen. Die Themen werden dann wie erwartet auf der Registerkarte Themenliste angezeigt.
- Wenn Sie in der Gliederungsansicht ein Verarbeitungsanweisungselement auswählen, wird das gesamte übergeordnete Tag anstelle des ausgewählten Elements hervorgehoben. (GUIDES-48318)
- Beim Ausführen von Löschvorgängen können einige geringfügige Inkonsistenzen in der Cursorbewegung und Navigation zwischen Imagemaps, strukturierten Elementen, Inline-Formatierungs-Tags und nicht zusammenführbaren Blöcken auftreten, was gelegentlich zu unerwartetem Cursor- oder Löschverhalten führt. (GUIDES-46756)
- Eine MathML-Gleichung, die in einen `foreign`- und `equation`-Block eingeschlossen ist, führt zu unerwünschten Abständen, und die Eingabe in die Gleichung verursacht Probleme, selbst wenn die Einrückung angepasst wird. (GUIDES-46606)
- Es ist nicht möglich, einen Cursor innerhalb eines `topicref` innerhalb eines `reltable` zu platzieren, wenn die Option **Tags anzeigen** aktiviert ist und die Option **Attribute anzeigen** in den Editor-Einstellungen deaktiviert ist. (GUIDES-46565)
- Durch Drücken der Rücktaste am Anfang eines Absatzes unmittelbar nach dem schreibgeschützten Inhalt (z. B. eines kontextabhängigen Absatzes) kann der bearbeitbare Absatz unerwartet gelöscht oder zusammengeführt werden, was zu einem unerwarteten Löschen des bearbeitbaren Absatzes führt. (GUIDES-45049)
- Wenn ein Inline-Tag mithilfe der Option Element umbenennen umbenannt wird, wird der Breadcrumb nicht sofort aktualisiert und spiegelt die Änderung erst wider, nachdem der Cursor in das Tag verschoben oder der Ansichtsmodus geändert wurde. (GUIDES-44993)<br>**Problemumgehung:** Aktualisieren Sie den Browser, nachdem Sie das Inline-Tag umbenannt haben, um den Breadcrumb zu aktualisieren.
- Wenn Bedingungsindikatoren auf Elemente wie BodyDiv angewendet werden, fließen die Indikatoren in der Ansicht Vollständige Tags in angrenzende Tags über, was zu falschem visuellen Rendering führt. (GUIDES-44971)

