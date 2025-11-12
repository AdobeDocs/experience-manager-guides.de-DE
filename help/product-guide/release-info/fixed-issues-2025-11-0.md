---
title: Versionshinweise zu | Es wurden Probleme in Adobe Experience Manager Guides Version 2025.11.0 behoben
description: Erfahren Sie mehr über die Fehlerbehebungen in der Version 2025.11.0 von Adobe Experience Manager Guides as a Cloud Service.
source-git-commit: d9a46a009477b1110208a509d4ad8c0616139661
workflow-type: tm+mt
source-wordcount: '704'
ht-degree: 3%

---

# Es wurden Probleme in der Version 2025.11.0 behoben

Dieser Artikel behandelt die in verschiedenen Bereichen der Version 2025.11.0 von Adobe Experience Manager Guides as a Cloud Service behobenen Fehler.

Weitere Informationen zu den neuen Funktionen und Verbesserungen finden Sie unter [Neue Funktionen in Version 2025.11.0](whats-new-2025-11-0.md).

Erfahren Sie mehr [Upgrade-Anweisungen für die Version 2025.11.0](upgrade-instructions-2025-11-0.md).

## Authoring

- Wenn ein leeres `prop` ohne Attribute oder Werte zu einer DITAVAL-Datei hinzugefügt wird, können keine zusätzlichen `prop` hinzugefügt werden. (GUIDES-33597)
- Nach dem Upgrade von Experience Manager Guides auf Version 2025.08.0 wird die Option zum Aktivieren oder Deaktivieren der benutzerdefinierten Registerkarte **Acrolinx** nicht mehr in den **Workspace-Einstellungen** angezeigt. (GUIDES-35261)
- Benutzerdefiniertes CSS, das auf ein Profil auf Ordnerebene für Themen oder Zuordnungen angewendet wird, wird bei der Browser-Aktualisierung im Vorschaumodus auf den Standardstil zurückgesetzt. (GUIDES-31098)
- **Vorgänge** Rückgängig“ und **Wiederholen** funktionieren in der Source-Ansicht des Editors für DITA-Dateien nicht wie erwartet. (GUIDES-24914, GUIDES-25034)
- Beim Referenzieren einer DITA-Zuordnung in einem Thema mithilfe des `Xref` wird der Dateiname der referenzierten Zuordnung anstelle des Titels der Zuordnung angezeigt. (GUIDES-21759)
- Beim Hinzufügen mehrerer Schematron-Dateien zur Validierung über das rechte Bedienfeld der Editor-Benutzeroberfläche wird ein Fehler **Schematron-Datei(en) existieren nicht oder weisen Fehler auf** angezeigt, selbst wenn die hinzugefügten Dateien gültig sind und keine Fehler aufweisen. (GUIDES-33731)
- Große oder komplexe MathML-Gleichungen werden im Editor nicht angezeigt. (GUIDES-29095)

## Asset-Management

- Wenn Sie ein bearbeitetes Bild erneut über die Experience Manager Guides-Benutzeroberfläche hochladen, wird die ursprüngliche Ausgabedarstellung des Bildes aktualisiert, aber der zugehörige DITA-Inhalt zeigt weiterhin die vorherige Bildversion an. (GUIDES-33693)
- Beim Versuch, zwei oder mehr Ordner von ihrem Quellspeicherort an einen anderen Speicherort zu verschieben (mithilfe des Tools für die Massenverschiebung), schlägt der Vorgang fehl, wenn die Ordnernamen mit derselben Zeichenfolge beginnen (z. B. Product- und ProductImages). (GUIDES-29096)
- Beim Löschen eines gesuchten Assets aus der Omnisearch Assets-Benutzeroberfläche wird das Warndialogfeld **Löschen erzwingen** umgangen und das Asset wird direkt gelöscht, selbst wenn es in vorhandenen DITA-Inhalten referenziert wird. (GUIDES-17232)

## Publishing

- Beim Veröffentlichen einer DITA-Zuordnung mit Baseline auf AEM Sites (mit veralteter Komponentenzuordnung) werden auch die Zuordnungselemente mit dem Attribut `processing-role = resource-only` veröffentlicht. (GUIDES-37649)
- In einigen Fällen fehlt die `jcr:content/fmUuidOfSource`-Eigenschaft in den AEM Sites-Ausgabeseiten (mit veralteter Komponentenzuordnung), was dazu führt, dass neu erstellte Inhaltsseiten nicht auffindbar sind.
- Die Inhaltsfilterung über DITAVal-Filter und bedingte Vorgaben funktioniert für die Salesforce-Veröffentlichung nicht. (GUIDES-33515)
- Es kann keine native PDF-Voreinstellung für eine Zuordnung erstellt werden, wenn in der Inhaltshierarchie ein Ordner mit demselben Namen vorhanden ist. (GUIDES-33012)
- Wenn die native PDF-Ausgabe mithilfe einer dynamischen Baseline generiert wird, wird der **PDFProject** als PDF-Titel anstelle des eigentlichen Zuordnungstitels angezeigt. (GUIDES-31102)
- Das Generieren der nativen PDF-Ausgabe mit bestimmten `print` in Themenverweisen funktioniert nicht wie erwartet. (GUIDES-31101)
- Wenn ein Ordner, der DITA-Zuordnungen enthält, mithilfe der Benutzeroberfläche von Assets oder der Option **Massenverschieben** verschoben wird, können vorhandene Zuordnungssammlungen und Massenaktivierungssammlungen, die auf diese Zuordnungen verweisen, nicht geladen werden. (GUIDES-28355)
- Wenn Sie einen Ordner verschieben, der eine Zuordnung mit Bedingungsvorgaben enthält, werden die Bedingungen nach dem Verschieben nicht auf die generierte Ausgabe angewendet. (GUIDES-28352)
- Wenn Sie AEM Sites-Ausgaben mit der Zuordnung veralteter Komponenten generieren, werden Themen, die das `copy-to` verwenden, mit dem Namen des `copy-from` Themas anstelle des im `copy-to` festgelegten Namens veröffentlicht. (GUIDES-22155)
- Durch die Aktivierung einer oder mehrerer DITA-Zuordnungen über **Dashboard für die Massenveröffentlichung** werden zu große Protokolle generiert. (GUIDES-20746)

## Platform

- Fehlerprotokolle, die beim Hochladen eines Assets über die Assets-Benutzeroberfläche oder beim Erstellen einer neuen Datei über die Editor-Benutzeroberfläche generiert werden, verwenden fälschlicherweise den Begriff `predecessor` anstelle von `successor` in der Protokollmeldung. (GUIDES-35607)

## Bekannte Probleme

Adobe hat die folgenden bekannten Probleme in Version 2025.11.0 identifiziert:

- Das Erstellen eines doppelten Themas mithilfe `copy-to` -Attributs und dessen Verweis mit `scope=peer` -Attribut verursacht Weiterleitungsprobleme in der AEM Sites-Ausgabe, bei denen Links von AEM Sites (mit Zuordnung zusammengesetzter Komponenten) zu AEM Sites (mit Zuordnung älterer Komponenten) umgeleitet werden und umgekehrt. (GUIDES-37656)











