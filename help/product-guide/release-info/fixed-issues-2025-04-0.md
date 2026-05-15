---
title: Versionshinweise | Behobene Probleme in Adobe Experience Manager Guides Version 2025.04.0
description: Erfahren Sie mehr über die Fehlerbehebungen in der Version 2025.04.0 von Adobe Experience Manager Guides as a Cloud Service.
exl-id: ad3e95b5-4903-4387-8e4d-c4b9ba77fee2
TQID: https://experienceleague.adobe.com/v7tg4-eP4JVt9bR0S4Ld4lWb0YbdlT-uJc7PrXPT4Wg
product_v2: id: fae5e35a-80c9-4b94-9352-1a060a6aab1did: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2: id: a3bd6397-2eb2-4908-a61c-226e26855dcaid: ab01a588-7dea-43f2-a699-0b3f128465d6
subfeature_v2: id: ad602516-aca3-4247-9ae8-f393d958efa9id: d4f22c6d-7923-41e5-9da3-527ff8df4bc8
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554
topic_v2: id: a004cc84-67b9-4a33-a3a7-8ec7273ef4dc
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 764
ht-degree: 6%

---

# Es wurden Probleme in der Version 2025.04.0 behoben

Dieser Artikel behandelt die in verschiedenen Bereichen der Version 2025.04.0 von Adobe Experience Manager Guides as a Cloud Service behobenen Fehler.

Weitere Informationen zu den neuen Funktionen und Verbesserungen finden Sie unter [Neue Funktionen in Version 2025.04.0](whats-new-2025-04-0.md).

Erfahren Sie mehr [Upgrade-Anweisungen für die Version 2025.04.0](upgrade-instructions-2025-04-0.md).

## Authoring

- Das Feld zum Einfügen von Sonderzeichen im Editor kann für das deutsche Gebietsschema nicht geladen werden. (24537)
- Kommentare und Beschriftungen, die beim Speichern einer neuen Version einer DITAVAL-Datei hinzugefügt werden, werden mit der neuen Version nicht im Versionsverlauf gespeichert. (24076)
- Die ausgehenden und eingehenden Verweise unter **Dateieigenschaften** im rechten Bereich werden beim Wechsel zwischen Zuordnungsdateien nicht ordnungsgemäß aktualisiert. Dieses Problem tritt insbesondere dann auf, wenn die Zuordnungsdateien eine große Anzahl von Verweisen enthalten. (23344)
- Der Repository-Filter behält die Reihenfolge der benutzerdefinierten Filter, die in der `ui_config.json` definiert sind, nicht bei. (21193)
- Durch das Löschen mehrerer Textzeilen in einem `codeblock` wird ein leerer Bereich erstellt, der nicht aus der Autorenansicht entfernt werden kann. (20672)
- Neue IDs können für Elemente nicht generiert werden, wenn solche Elemente über Ausschnitte hinzugefügt oder über Vorlagen erstellt werden, selbst wenn **Option „ID automatisch generieren** in `XMLEditorConfig` aktiviert ist. (21734)
- Beim Erstellen eines neuen DITA-Assets aus DITA-Vorlagen werden die Replikationseigenschaften aus den entsprechenden DITA-Vorlagen kopiert. (25145)
- Der Zugriff auf Dateieigenschaften über das Repository-Bedienfeld ist nicht möglich, wenn der Name des übergeordneten Ordners das Zeichen &quot;&amp;&quot; enthält. (25762)
- Durch Schließen einer Themendatei kann diese als neue Version gespeichert werden, auch wenn das Thema gesperrt ist. Dieses Problem tritt insbesondere auf, wenn die Option **Nach neuer Version beim Schließen** fragen“ in `XMLEditorConfig` aktiviert ist. (23875)
- Die aktuelle maximale Breite des Repository-Bereichs blendet Themen- und Zuordnungstitel aus, wenn die Inhaltshierarchie tief verschachtelt ist. (27751)

## Publishing

- Im alten AEM Sites-Output werden Abschnittslinks innerhalb verschachtelter Themen einer Zuordnung nicht korrekt aufgelöst, wenn sie manuell im Source-Modus festgelegt werden oder der Inhalt aus einer externen Quelle importiert wird. Anstatt zum vorgesehenen Abschnitt zu navigieren, leiten sie zum Hauptthema um, das das verschachtelte Thema enthält. (26103)
- Wenn das `scope=external` in externen Links in einem DITA-Thema fehlt, schlägt die Veröffentlichung von HTML5 fehl, ohne die Dateien anzugeben, in denen dieses Attribut in den Fehlerprotokollen fehlt, insbesondere wenn der Microservice aktiviert ist. (25969)
- Video-Links können nicht in natives PDF eingebettet werden, selbst wenn die Option **Multimediadateien einbetten** in der PDF-Vorgabe aktiviert ist. (9989)
- Die Metadateneigenschaften können nicht an Zuordnungs-Landingpages übergeben werden, die mit der neuen AEM Sites-Veröffentlichung generiert wurden. (27288)

## Verwaltung

- Der Dokumentstatus aus der Arbeitskopie eines Themas wird für alle Versionen dieses Themas in der Benutzeroberfläche „Übersetzung und Grundlinie“ angezeigt. (20674)


## Überprüfung

- Beim Aktualisieren der Details einer Prüfungsaufgabe im Überprüfungs-Dashboard wird nicht bestätigt, ob die Aktualisierung erfolgreich war oder nicht. (8051)

## Übersetzung

- Übersetzungen, die über Experience Manager Guides übermittelt werden, enthalten keine angehängten Assets, was dazu führt **dass die Schaltfläche** Starten“ für den Übersetzungsauftrag für Benutzende nicht mehr verfügbar ist.

## Bekannte Probleme

Adobe hat die folgenden bekannten Probleme in Version 2025.04.0 identifiziert:

- Die Anzahl der Verweise in der Baseline-Benutzeroberfläche wird beim Bearbeiten der Baseline nicht aktualisiert. Sie wird nur aktualisiert, wenn die Änderungen gespeichert werden. (28015)
- Wenn mehrere Registerkarten im Editor geöffnet sind, wird durch einen Vorgang **Rückgängig** in der Ansicht **Source** einer Datei die letzte Bearbeitung rückgängig gemacht, aber auch zur zuvor geöffneten Registerkarte gewechselt. (27891)
- Die Option **AEM-Rechtschreibprüfung** wird in der Dropdown-Liste **Menü** angezeigt, auch wenn die Option **Browser-**) in den Editor-Einstellungen aktiviert ist. (27993)
- Eine zusätzliche Version wird erstellt und im Bedienfeld **Versionsverlauf** angezeigt, wenn Sie ein Bild in der Assets-Benutzeroberfläche bearbeiten und speichern. (28001)
- Beim Einfügen eines neuen Inhalts in eine neue Zeile in einem `codeblock` wird automatisch eine leere Zeile eingefügt.(27842)
- Beim Wechseln zwischen Voreinstellungen, die dieselbe Baseline verwenden, wird die Schaltfläche **Speichern** für die aktuelle Voreinstellung deaktiviert. (28025)
- Ein Thema innerhalb einer DITA-Zuordnung kann nicht in der AEM Sites-Ausgabe veröffentlicht werden, wenn es sowohl als `keydef` als auch als `topicref` in seinen Unterzuordnungen verwendet wird. (22269)
- Ein Programmfehler tritt auf, wenn mehrere Themen einer Zuordnung bearbeitet und dann mit der Option **Alle schließen** geschlossen werden und die Einstellung **Beim Speichern der Version beim Schließen**.(27931)

Adobe hat das folgende bekannte Problem mit einer Problemumgehung identifiziert:

+++In der AEM Sites-Ausgabe werden Bilder beschädigt, wenn die Grundlinie beim Veröffentlichen nicht angewendet wird. (28043)
***Problemumgehung:*** Sie können solche Assets über die **Assets-Benutzeroberfläche** veröffentlichen, woraufhin der Link funktionsfähig wird.
+++
