---
title: Versionshinweise | Neue Funktionen in Adobe Experience Manager Guides Version 2026.06.0
description: Erfahren Sie mehr über die neuen und erweiterten Funktionen der Version 2026.06.0 von Adobe Experience Manager Guides
role: Leader
source-git-commit: f3f30400f776f746427e257e2c937ff3413aa9ac
workflow-type: tm+mt
source-wordcount: '943'
ht-degree: 0%

---

# Neue Funktionen in der Version 2026.06.0 (Juni 2026)

Dieser Artikel behandelt die neuen und erweiterten Funktionen, die mit der Version 2026.06.0 von Adobe Experience Manager Guides as a Cloud Service eingeführt wurden.

Eine Liste der in dieser Version behobenen Probleme finden Sie unter [Behobene Probleme in der Version 2026.06.0](fixed-issues-2026-06-0.md).

Erfahren Sie mehr [Upgrade-Anweisungen für die Version 2026.06.0](../release-info/upgrade-instructions-2026-06-0.md).


## Neue Zuordnungssammlung (Beta) zum Verwalten von Zuordnungen und Veröffentlichen von Ausgaben

>[!NOTE]
>
> Diese Funktion ist derzeit als Beta-Funktion verfügbar und standardmäßig deaktiviert. Um sie in Ihrer Umgebung zu aktivieren, wenden Sie sich an das Customer Success-Team.

Die neue Zuordnungssammlung (Beta) fasst die Verwaltung von Zuordnungen und die Generierung von Ausgaben in einer einzigen Oberfläche zusammen. Von einem Ort aus können Sie Karten und Vorgaben verwalten, Ausgaben generieren und veröffentlichen, den Generierungs- und Veröffentlichungsverlauf anzeigen und vieles mehr. Durch das Zusammenführen verwandter Veröffentlichungsaufgaben wird es einfacher, mit Zuordnungssammlungen zu arbeiten und die Ausgabeaktivität über mehrere Zuordnungen und die zugehörigen Sprachen hinweg zu verfolgen.

![](assets/new-maps-collection.png)

Weitere Informationen finden Sie unter [Verwenden einer neuen Zuordnungssammlung für die Ausgabegenerierung (Beta)](../user-guide/generate-output-use-new-map-collection-output-generation.md).

## Einführung einer neuen Publishing-Engine für Native PDF

Eine neue Publishing-Engine *Native PDF Engine v2* ist jetzt für Native PDF in Experience Manager Guides verfügbar. Es umfasst Rendering-Verbesserungen und -Fehlerbehebungen für Probleme der nativen PDF-Engine v1. Da das Renderingverhalten aktualisiert wurde, kann sich die mit *nativen PDF Engine v2* generierte PDF-Ausgabe von der Ausgabe unterscheiden, die mit der vorhandenen nativen PDF-Publishing-Engine (*native PDF Engine v1*) generiert wird.

Beispielsweise kann der Text in generierten PDF-Dateien aufgrund von Aktualisierungen in den von der (nativen PDF Engine v2 *verwendeten Kernschriftarten leicht* aussehen. Ebenso können Bilder aufgrund von Verbesserungen bei der Bildinterpolation und dem Rendering-Verhalten schärfer aussehen.

Erfahren Sie, wie [ native PDF Engine v2 ](../native-pdf/conf-new-pdf-engine.md) Ihrer Umgebung aktivieren.

Informationen zur **nativen PDF Engine v2** finden Sie unter [Arbeiten mit der nativen PDF Engine v2](../native-pdf/new-pdf-engine.md).


## Verbesserungen am Editor

### Unterstützung für AMA-Zitatstil

Experience Manager Guides unterstützt jetzt den Zitatstil der American Medical Association (AMA) und erweitert das bestehende Zitierungs-Framework, um die Dokumentationsstandards zu erfüllen, die von Kunden in den Bereichen Gesundheit, Regulierung und Biowissenschaften benötigt werden.

Wenn AMA in den **Workspace-Einstellungen** als Zitatstil ausgewählt ist, werden Zitate automatisch gemäß den AMA-Richtlinien formatiert, einschließlich hochgestellter numerischer Darstellung, sequenzieller Nummerierung und genauer Referenzlistenreihenfolge. Die Option **Zitat analysieren** im Editor ist nur verfügbar, wenn AMA ausgewählt ist, sodass Autoren Zitate hinzufügen und analysieren können, ohne den Kontext zu wechseln.

Der AMA-Zitatstil wird in allen nativen Ausgabeformaten von PDF und AEM Sites unterstützt. Um den Zitatstil zu konfigurieren, gehen Sie zu **Workspace-Einstellungen** wählen Sie AMA aus den Optionen für den Zitatstil aus. Weitere Informationen finden Sie unter [Arbeiten mit Zitaten](../user-guide/web-editor-apply-citations.md).


### Unterstützung für externe Datenquellen und Zitate ist jetzt im neuen Editor verfügbar

Der neue Editor unterstützt jetzt zwei bestehende Experience Manager Guides-Funktionen: die Möglichkeit, eine Verbindung mit externen Datenquellen herzustellen und Zitate in den Dokumenten zu verwenden.

Autoren können konfigurierte externe Datenquellen weiter verwenden, während sie Inhalte im neuen Editor erstellen oder aktualisieren. Zitate werden auch unterstützt, sodass Autoren Verweise in ihren Inhalten hinzufügen und verwalten können, ohne den Editor zu wechseln.

## Verbesserungen bei Überprüfungen

### Abschluss der Aufgabe „Überprüfung synchronisieren“ zwischen der Benutzeroberfläche für Überprüfungen und dem AEM-Posteingang (Beta)

>[!NOTE]
>
> Diese Funktion ist derzeit als Beta-Funktion verfügbar und standardmäßig deaktiviert. Um sie in Ihrer Umgebung zu aktivieren, wenden Sie sich an das Customer Success-Team.

Sie können jetzt den Abschluss der Prüfungsaufgabe zwischen der Überprüfungs-Benutzeroberfläche und dem AEM-Posteingang synchron halten. Wenn diese Funktion aktiviert ist, wird sie durch das Abschließen einer Aufgabe in der Überprüfungs-Benutzeroberfläche aus dem AEM-Posteingang entfernt, und durch das Abschließen aus dem AEM-Posteingang wird sie in der Überprüfungs-Benutzeroberfläche als abgeschlossen markiert. Dadurch wird vermieden, dass dieselbe Aufgabe zweimal ausgeführt wird, und der Überprüfungs-Workflow reibungsloser. Autoren und Aufgabeninitiatoren können weiterhin Feedback überprüfen und Aufgaben neu zuweisen, wenn eine zusätzliche Überprüfung erforderlich ist. Wenn eine Aufgabe neu zugewiesen wird, wird eine neue AEM-Posteingangsbenachrichtigung für den Reviewer generiert, sodass der Überprüfungszyklus nahtlos fortgesetzt werden kann.

Weitere Informationen finden Sie unter [Prüfungsaufgabe als Prüferin bzw. Prüfer ](../user-guide/review-complete-review-tasks.md).

## Verbesserungen an Lerninhalten

Die folgenden Verbesserungen sind in dieser Version für die Funktion „Produktschulungen und Lerninhalte“ verfügbar:

- Autoren können jetzt einen Wissenstest für Lernende obligatorisch machen, bevor sie in einem Kurs fortfahren. Für **in Kursen wird eine neue Option** Wissenstest erforderlich, um fortzufahren) eingeführt. Nach der Aktivierung müssen Lernende eine Wissenstest durchführen, bevor sie mit den nachfolgenden Kursinhalten fortfahren. Dadurch wird sichergestellt, dass die erforderlichen Wissenstests an bestimmten Punkten des Kurses abgeschlossen werden. Weitere Informationen finden Sie unter [Weitere Optionen im Menü Einfügen](../learning-content/lc-other-insert-options.md).
- Sie können jetzt mehrzeilige Texteingabefelder beim Erstellen von Lerninhalten verwenden. Diese Verbesserung erleichtert die Erfassung längerer Teilnehmerantworten, indem Zeilenumbrüche und Textumbrüche in einem einzigen Feld unterstützt werden, ohne auf benutzerdefinierte Skripterstellung angewiesen zu sein. Weitere Informationen über [Weitere Optionen im Menü Einfügen](../learning-content/lc-other-insert-options.md).
- SCORM-Ausgabevorlagen unterstützen jetzt die Zuweisung verschiedener Seiten-Layouts zu verschiedenen Thementypen innerhalb eines Kurses. Auf diese Weise können Sie spezielle Layouts für Lektionen, Quiz, Übersichtsseiten und andere Thementypen direkt in den Einstellungen der Ausgabevorlage konfigurieren.

  Dadurch kann jeder Thementyp ein Layout verwenden, das für seinen Inhalt und seine Struktur geeignet ist, anstatt dasselbe Layout auf alle Kursseiten anzuwenden. Weitere Informationen zum Konfigurieren von Seiten-Layouts für SCORM-Ausgabevorlagen finden Sie unter [Konfigurieren von Ordnerprofilen](../lc-config-guide/lc-folder-profile.md).
- Experience Manager Guides unterstützt jetzt die direkte Veröffentlichung von SCORM-Inhalten in Adobe Learning Manager (ALM). Nach der Konfiguration eines ALM-Veröffentlichungsprofils können Autoren eine SCORM-Ausgabe generieren und sie direkt in Adobe Learning Manager hochladen, ohne das Paket herunterzuladen und manuell zu importieren.

  Weitere Informationen finden Sie unter [SCORM-Vorgabe konfigurieren](../learning-content/config-scorm-preset.md).


