---
title: Versionshinweise zu | Es wurden Probleme in Adobe Experience Manager Guides Version 2026.01.0 behoben
description: Erfahren Sie mehr über die Fehlerbehebungen in der Version 2026.01.0 von Adobe Experience Manager Guides as a Cloud Service.
source-git-commit: 8a9a82e79c757e403141e853aafbc64e1618c30a
workflow-type: tm+mt
source-wordcount: '719'
ht-degree: 3%

---

# Es wurden Probleme in der Version 2026.01.0 behoben

Dieser Artikel behandelt die in verschiedenen Bereichen der Version 2026.01.0 von Adobe Experience Manager Guides as a Cloud Service behobenen Fehler.

Weitere Informationen zu den neuen Funktionen und Verbesserungen finden Sie unter [Neue Funktionen in Version 2026.01.0](whats-new-2026-01-0.md).

Erfahren Sie mehr [Upgrade-Anweisungen für die Version 2026.01.0](upgrade-instructions-2026-01-0.md).

## Authoring

- Beim Aktualisieren einer Inline-MathML-Gleichung mit der Option MathML bearbeiten im Kontextmenü wird der aktualisierte Wert erst angezeigt, nachdem die Seite aktualisiert wurde. (GUIDES-38198)
- Wenn ein Thema viele wiederverwendbare Elemente (mit IDs) enthält, die im wiederverwendbaren Bereich hinzugefügt wurden, können einige Elemente aufgrund der festen Container-Höhe möglicherweise nicht aufgerufen werden. (GUIDES-37220)
- Beim Einfügen eines Querverweises in eine Datei werden die Symbole für Karten und Themen identisch angezeigt.(GUIDES-36662)
- Beim Bearbeiten einer Zuordnung werden in der `navtitle` keine Sondersymbole zur `topichead` in der Autorenansicht angezeigt. (GUIDES-35435)
- Es können nicht mehrere Versionsbeschriftungen zu einem Thema aus dem Dialogfeld **Als neue Version speichern** hinzugefügt werden. (GUIDES-32716)

## Asset-Management

- Versionsbeschriftungen können nicht aus dem Bedienfeld Versionsverlauf in der Assets-Benutzeroberfläche entfernt werden. (GUIDES-38276)
- Beim Hochladen von Assets mit Dateinamen, die ungültige Zeichen enthalten, kann das Asset nicht hochgeladen werden und es wird eine falsche Meldung angezeigt **Datei wird von anderen Benutzern gesperrt** obwohl das Asset entsperrt wurde. (GUIDES-32680)
- Bei der Assets-Suche werden Teil-Assets und Metadatenknoten (z. B. Bilder und PDFs) fälschlicherweise in die Ergebnisse eingeschlossen. Darüber hinaus gibt die Suche für eine Ausgabevorgabe, wenn DITAVAL-Filter angewendet werden, intern generierte DITAVAL-Dateien zurück, die aus Bedingungsvorgaben erstellt wurden. (GUIDES-35418)

## Veröffentlichung

- Beim Generieren der AEM Sites-Ausgabe werden die Zuordnungstitel, die Keywords und Thementitel mit `<ph>` Element enthalten, nicht in die veröffentlichte Ausgabe aufgenommen. (GUIDES-36641)
- Beim Veröffentlichen mit einer benutzerdefinierten Vorgabe mit Inhalten, die Links zu PDFs ohne den als extern festgelegten Umfang enthalten, kann der Prozess nicht abgeschlossen werden. (GUIDES-21708)
- Bei der Massenaktivierung fügt die Paketerstellung Filter für alle Pfade hinzu, die unter der `fileReference`-Eigenschaft einer Seite aufgeführt sind, einschließlich externer und Peer-Pfade. (GUIDES-24887)
- In der nativen PDF-Ausgabe zeigt das `abbreviated-form` die `glossterm` anstelle der angegebenen `glossSurfaceForm` oder `glossAcronym` an. (GUIDES-26393)
- Für die native PDF-Ausgabe wird das `<alt>` für Bilder ignoriert, was verhindert, dass alternativer Text auf die Barrierefreiheit angewendet wird. (GUIDES-29087)
- Beim Herunterladen temporärer Dateien für eine Zuordnung mit einer Grundlinie während der Veröffentlichung einer Vorgabe verweist die `metadata.xml`-Datei fälschlicherweise auf die `versionPath` statt auf die `dampath`.(GUIDES-29815)
- Beim Erstellen oder Bearbeiten eines Themas, das ein Zitat enthält, wird die PDF nicht generiert, wenn das Feld „Autor“ nicht im Zitatdialogfeld hinzugefügt wird. (GUIDES-37934)
- Die CSS-Datei (`rhdefault.css`) wird falsch auf die PDF-Vorlage angewendet, obwohl kein CSS referenziert wird, was zu fehlenden CSS-Datei-Fehlerprotokollen führt.(GUIDES-31752)

## Platform

- Beim Versuch, ein Thema oder eine Zuordnung zu speichern, kann der Vorgang gelegentlich mit einem Fehler **Datei konnte nicht gespeichert werden** fehlschlagen, insbesondere während intensiver Asset-Verarbeitungsaufgaben oder Übersetzungs-Workflows, die im Hintergrund ausgeführt werden. (GUIDES-37837)
- Wenn Sie `scope="external"` für einen Verweis auf DAM-Inhalte in einem Thema oder einer Zuordnung verwenden, wird der relative Pfad des Assets durch eine GUID ersetzt. (GUIDES-38783)

## Berichte

- Der Bericht Beschädigte Liste enthält fälschlicherweise externe Links, gültige `keyrefs` und Schlüsselwörter, die im Rahmen der aktuellen Zuordnung ordnungsgemäß aufgelöst werden. (GUIDES-27774)

## Bekannte Probleme

Adobe hat die folgenden bekannten Probleme in Version 2026.01.0 identifiziert:

- Wenn ein zu überprüfendes Thema aus einer laufenden Prüfungsaufgabe entfernt wird, bleibt sein Dokumentstatus weiterhin **In Überprüfung**, auch wenn das Thema nicht mehr Teil einer Prüfungsaufgabe ist. (GUIDES-38709)<br>**Problemumgehung**: Ändern Sie den Dokumentstatus des Themas von **In Überprüfung** in den entsprechenden Status auf der Seite Eigenschaften oder im Bedienfeld Dateieigenschaften .
- Wenn Sie bei einer Suche mit **Suchen und Ersetzen** eine Datei aus den Suchergebnissen öffnen, schließen und dann versuchen, sie erneut zu öffnen, indem Sie das aufgelistete Ergebnis auswählen, kann die Datei nicht erneut geöffnet werden. (GUIDES-39050)<br>**Problemumgehung**: Öffnen Sie zuerst eine beliebige andere Datei aus den Suchergebnissen und öffnen Sie dann die zuvor geschlossene Datei erneut aus der Liste, um das Problem zu beheben.
- Bei Verwendung von Handbüchern mit dem DB-Server zeigt der Bericht mit der Themenliste für Inhalte, die Selbstverweise enthalten, ungültige Einträge für jede Selbstverweise an, was zu einer ungenauen Dateianzahl führt. (GUIDES-39420)












