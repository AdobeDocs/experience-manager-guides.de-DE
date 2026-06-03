---
title: Versionshinweise | Behobene Probleme in Adobe Experience Manager Guides Version 2026.05.0
description: Erfahren Sie mehr über die Fehlerbehebungen in der Version 2026.05.0 von Adobe Experience Manager Guides as a Cloud Service.
source-git-commit: 4a22e6f8e2505a5e2a990ec38571913c838d0ea1
workflow-type: tm+mt
source-wordcount: '1255'
ht-degree: 0%

---

# Es wurden Probleme in der Version 2026.05.0 behoben

Dieser Artikel behandelt die in verschiedenen Bereichen der Version 2026.05.0 von Adobe Experience Manager Guides as a Cloud Service behobenen Fehler.

Weitere Informationen zu den neuen Funktionen und Verbesserungen finden Sie [Neue Funktionen in der Version 2026.05.0](whats-new-2026-05-0.md).

Erfahren Sie mehr [Upgrade-Anweisungen für die Version 2026.05.0](upgrade-instructions-2026-05-0.md).

## Authoring

- Wenn Sie ein Bild im Editor über das Dialogfeld **Datei auswählen** auswählen, werden nur Rasterformate (wie JPG, PNG und GIF) angezeigt. Vektordateien (z. B. .ai und .eps) werden nicht angezeigt und können nicht ausgewählt werden. (GUIDES-45110)
- Zum Zeitpunkt des Upgrades ist die `tagsView` standardmäßig deaktiviert, obwohl ihr Standardwert in `ui_config.json` auf `true` festgelegt ist. (GUIDES-44651)
- Im Editor werden Dateiverweise trotz der `xmleditor.uuid` als GUIDs anstelle von Dateipfaden angezeigt. (GUIDES-42438)
- Wenn Subjektschemata mit ähnlichen Schlüsselwerten in einem DITA-Thema angewendet werden, werden sie mit nahezu identischen Farben hervorgehoben, sodass es schwierig ist, sie zu unterscheiden und zu erkennen, welches Schema angewendet wird. (GUIDES-38472)
- Beim Bearbeiten einer Zuordnung eines Betreffschemas in der Autorenansicht wird durch Hinzufügen des `hasInstance` automatisch das Dateiauswahldialogfeld Trigger, sodass Autorinnen und Autoren eine unerwünschte `href` einfügen müssen, die auf ein AEM-Asset verweist. Darüber hinaus kann das Bedienfeld **Inhaltseigenschaften** für solche Zuordnungen nicht geladen werden. Dies verhindert, dass Autorinnen und Autoren Elementattribute in der Autorenansicht aktualisieren, und erfordert, dass sie die Source-Ansicht zum Aktualisieren von Attributen verwenden. (GUIDES-38164)
- Beim Bearbeiten einer `.ditaval` werden alle in der Source-Ansicht hinzugefügten XML-Kommentare entfernt, wenn Sie zur Autorenansicht wechseln und dann zur Source-Ansicht zurückkehren. (GUIDES-33228)


## Asset-Management

- Wenn Sie ein Thema in einem Ordner mit Leerzeichen im Namen erstellen, wird fälschlicherweise ein doppelter Ordner erstellt, in dem Leerzeichen durch Bindestriche ersetzt werden, und das Thema wird dort anstelle des ursprünglichen Ordners gespeichert. (GUIDES-41938)
- Bei der ersten Übersetzung großer Zuordnungen werden leere XML-Dateien für die Zielsprache erstellt, was zu erhöhter Serverlast und langsamerer Leistung führt. (GUIDES-41613)
- In DB-basierten Umgebungen werden gültige interne DITA-Links als fehlerhafte Links in **Asset-Eigenschaften** angezeigt, obwohl sie im Editor und in der veröffentlichten Ausgabe ordnungsgemäß funktionieren. (GUIDES-35048)

## Publishing

- Wenn Änderungen an einer Ausgabevorgabe in einem Ordnerprofil auf bestehende Zuordnungen angewendet werden, wird der gespeicherte **Veröffentlichungskontext** für die AEM Sites-Vorgabe zurückgesetzt. (GUIDES-38377)
- Das Markensymbol (®) wird nicht auf der Titelseite der nativen PDF-Ausgabe gerendert, wenn das `tm` Element im Titel einer Zuordnung oder einer Lesekarte verwendet wird. (GUIDES-28832)
- Beim Veröffentlichen einer Zuordnung mit einer nativen PDF-Vorlage enthält der **Zuordnungstitel** keine Inhalte aus den untergeordneten Elementen, die in der `title` verwendet werden, und die entsprechende Inhaltsfilterung wird nicht auf den Titel angewendet. (GUIDES-33730)
- Kreuzzuordnungs-Peer-Links in der AEM Sites-Ausgabe können nicht aufgelöst werden, wenn sie auf einen `topicref` verweisen, der `chunk="to-content"` verwendet. (GUIDES-37873)
- Während der Veröffentlichung werden Dateien, die mit dem DITAVAL-basierten Flag verknüpft sind, in einen neuen systemgenerierten Ordner verschoben, anstatt an ihrem erwarteten relativen Speicherort in der Ausgabe zu bleiben. (GUIDES-37564)
- Wenn mehrere DITAVAL-Dateien mit widersprüchlichen Bedingungen verwendet werden, schlägt die native PDF-Ausgabe fehl. (GUIDES-37484)

## Grundlinie

- Themenreferenzen innerhalb einer Zuordnung werden bei Verwendung eines benutzerdefinierten DITA-OT fälschlicherweise als indirekt angezeigt, obwohl sie direkt referenziert werden. Dieses Problem wurde mit der neuen Basiserfahrung behoben. (GUIDES-19286)
- Verweise mit `scope="peer"` werden fälschlicherweise in den Grundlinienkontext eingeschlossen, sodass die Veröffentlichung länger dauert als erwartet. Dieses Problem wurde mit der neuen Basiserfahrung behoben. (GUIDES-30048)

## Platform

- Wenn große Themen oder Zuordnungen geöffnet werden, reagiert die Autoreninstanz nicht mehr, was in einigen Fällen einen Neustart erforderlich macht. (GUIDES-43547)

## Gelöste Probleme mit Editor 2.0

Die folgenden Probleme wurden behoben und treten bei Verwendung des Editors 2.0 (auch als neuer Editor bezeichnet) nicht mehr auf:

- Wenn zwei oder mehr Spalten aus einer Tabelle gelöscht werden, wird die Tabellenstruktur inkonsistent oder beschädigt. (GUIDES-35438)
- Wenn eine Spalte aus einer Tabelle gelöscht wird, die zusammengeführte Zellen enthält, wird eine neue leere Spalte hinzugefügt. (GUIDES-30147)
- Wenn eine neue Zeile aus dem Breadcrumbs-Menü in eine vorhandene Tabelle eingefügt wird, ändert sich die Tabellenstruktur unerwartet, was zu fehlenden Rahmen und einer zusätzlichen Spalte führt. (GUIDES-29194)
- Durch Kopieren und Einfügen einer Tabellenzeile wird der Inhalt in der Autorenansicht außerhalb der Tabelle platziert, anstatt ihn als neue Zeile in die Tabelle einzufügen. (GUIDES-24372)
- Wenn ein im Autorenmodus mit dem Mauszeiger ausgewähltes Schnittelement kopiert und eingefügt wird, wird es in `(<p>)` umgewandelt, anstatt die Abschnittsstruktur beizubehalten. (GUIDES-30023)
- Wenn markierter Text innerhalb von Elementen wie „step“ oder „uicontrol“ bearbeitet wird, wird der ausgewählte Text nicht korrekt ersetzt, sondern an den Text angehängt oder ihm vorangestellt, was zu Validierungsfehlern führt. (GUIDES-24371)
- Wenn eine Tabellenspaltenbreite mit relativen Werten festgelegt wird, werden die übrigen Spalten nicht proportional angepasst, was zu einem falsch ausgerichteten Tabellen-Layout führt. (GUIDES-26109)
- Wenn ein kopierter Thementitel eingefügt und Tags deaktiviert sind, wird beim ersten Einfügen ein falscher Stil angewendet und der Typ in den Inhaltseigenschaften als Thema anstelle des Titels zugewiesen. (GUIDES-28838)
- Wenn große Inhaltsbereiche bearbeitet werden, führt eine unbeabsichtigte Bildlaufbewegung dazu, dass die Editor-Ansicht vom aktiven Inhalt weg springt. (GUIDES-35436)
- Wenn die Rücktaste für Elemente verwendet wird, scrollt der Editor unabhängig von der Cursorposition zum Anfang des Themas. (GUIDES-32520)
- Wenn mit der Nach-links- oder Nach-rechts-Taste aus Inline-Tags heraus gewechselt wird, springt der Cursor beim ersten Versuch unerwartet. (GUIDES-26363)
- Die AEM-Rechtschreibprüfung funktioniert nur für die Standardsprache en-US und berücksichtigt keine anderen Gebietsschemata. (GUIDES-14731)
- Wenn große DITA-Themen im Editor entsperrt werden, wird dasselbe Thema erneut in einer doppelten Registerkarte geöffnet. Darüber hinaus wird eine Warnung zu Tag-Grenzwerten ausgelöst, bei der anstelle der tatsächlichen Tag-Anzahl `NaN` angezeigt wird. (GUIDES-34008)
- Acrolinx-Vorschläge werden im Editor für schreibgeschützte oder gesperrte Themen nicht korrekt hervorgehoben. (GUIDES-29614)
- Beim Erstellen eines neuen `reltable` ohne Kopfzeile in der Autorenansicht ändert sich das Tabellenlayout, nachdem ein Thema zur ersten Zelle hinzugefügt wurde. Dadurch wird die nächste Spalte ausgeblendet, was die Platzierung verwandter Themen erschwert. (GUIDES-19555)
- Wenn eine `xref` Relation zu einer kleinen Tabellenzelle im Autorenmodus hinzugefügt wird, bleibt die Relation nicht in der Zelle enthalten und wird über benachbarte Zellen in derselben Zeile angezeigt. (GUIDES-5489)
- Beim Wechseln von der Authoring- zur Source-Ansicht wird die Cursorposition nicht beibehalten und der Editor scrollt zurück nach oben. Darüber hinaus geht in langen Themen die Cursorposition verloren und springt beim Wechseln zwischen Authoring- und Source-Ansichten zufällig in die Mitte oder nach oben. (GUIDES-18114, GUIDES-21164)
- Wenn Sie *Eingabetaste* innerhalb eines `<li>` Elements drücken, wird ein neues `<li>` erstellt, aber durch Zurücknavigieren zu einem vorherigen `<li>` und Drücken der *Eingabetaste* wird der Inhalt des aktuellen Elements fälschlicherweise in ein `<p>` Element konvertiert, wodurch die Listenstruktur beschädigt wird. (GUIDES-27505)

## Bekannte Probleme

Adobe hat die folgenden bekannten Probleme in Version 2026.05.0 identifiziert:

- Wenn eine Zuordnung einen externen `topicref` enthält, der auf eine Nicht-DITA-Ressource verweist (z. B. `.html` oder `.htm`), wird ihre Vorschau nicht in der Assets-Benutzeroberfläche angezeigt. (GUIDES-45409)
- In der Assets-Benutzeroberfläche werden Inhalte, auf die mit `conref` verwiesen wird, für DITA-Themen nicht angezeigt, obwohl sie in der Editor-Vorschau korrekt gerendert werden. (GUIDES-45505)<br>**Problemumgehung**: Für solche Inhalte können Sie die Vorschau des Editors verwenden.
- Wenn `xmleditor.uniquefilenames` Eigenschaft aktiviert ist, enthalten neue Themen, die mithilfe einer Vorlage erstellt wurden, nicht den Thementitel. (GUIDES-44737)
- Die `getAsset`-, `startAssetProcessing`- und `getAssetProcessingStatus`-APIs sind nicht über die Java-SDK verfügbar.

