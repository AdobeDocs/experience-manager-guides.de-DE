---
title: Versionshinweise | Behobene Probleme in Adobe Experience Manager Guides Version 2026.11.0
description: Erfahren Sie mehr über die Fehlerbehebungen in der Version 2026.11.0 von Adobe Experience Manager Guides as a Cloud Service.
source-git-commit: f33da832def2bf2cc8caf46f3b6f8102bcfafb19
workflow-type: tm+mt
source-wordcount: '1448'
ht-degree: 0%

---

# Es wurden Probleme in der Version 2026.11.0 behoben

Dieser Artikel behandelt die in verschiedenen Bereichen der Version 2026.11.0 von Adobe Experience Manager Guides as a Cloud Service behobenen Fehler.

Weitere Informationen zu den neuen Funktionen und Verbesserungen finden Sie [Neue Funktionen in der Version 2026.11.0](./whats-new-2026-11-0.md).

Erfahren Sie mehr [Upgrade-Anweisungen für die Version 2026.11.0](./upgrade-instructions-2026-11-0.md).

## Editor 2.0

- Wenn eine Tabellenzeile mithilfe der Breadcrumbs im Editor ausgewählt wird und die Option **Löschen** im Kontextmenü ausgewählt ist, werden nur die Zelleninhalte entfernt, anstatt die gesamte Zeile zu löschen. (GUIDES-56759)
- Wenn eine Tabelle aus Microsoft Word eingefügt wird, werden die Kopfzeilenzellen erstellt, ihr Inhalt geht jedoch verloren. (GUIDES-49847)
- Verfolgte Änderungen in Dateien, die vor dem Wechsel zu Editor 2.0 erstellt wurden, werden nicht im Bedienfeld **Änderungen verfolgen** angezeigt. (GUIDES-44777)
- Wenn Code mithilfe von Strg+V aus Microsoft Word oder ähnlichen Texteditoren in ein `codeblock`-Element eingefügt wird, gehen Zeilenumbrüche und führende Leerzeichen verloren und der Code wird in eine einzelne Zeile reduziert. (GUIDES-33247)

## Authoring

- Wenn die Unified Shell aktiviert ist, wird die Adobe Experience Manager Guides-Kopfzeile auch im Editor und in der Zuordnungskonsole angezeigt. (GUIDES-56812)
- In der Assets-Benutzeroberfläche werden DITA-spezifische Aktionen wie **Quelle anzeigen**, **Themen bearbeiten** und **UUID-Link freigeben** für Nicht-DITA-Assets angezeigt. Darüber hinaus generiert **UUID-Link freigeben** einen ungültigen Link für Assets, die keine UUID haben. (GUIDES-47043)
- Im Bedienfeld „Betreffschema“ wird der Anzeigetitel nur aus dem Attribut `navtitle` ausgewählt. Das `navtitle`-Element wird auch dann ignoriert, wenn beide vorhanden sind. (GUIDES-37722)
- In der **Titelansicht** des Repository-Bereichs sind die Auslassungspunkte für Dateien mit langen Namen zunächst nicht sichtbar. Wenn Sie mit der rechten Maustaste auf eine solche Datei klicken, werden die Auslassungspunkte und das Kontextmenü ganz rechts neben der Datei angezeigt, manchmal teilweise außerhalb des Bildschirms. (GUIDES-37118)
- Im Bedienfeld Bedingungen werden Bedingungen alphabetisch nach ihren Werten und nicht nach ihren Bezeichnungen sortiert. (GUIDES-14593)
- In Ausgabevorlagen wird die Schaltfläche **Neuer Stil** (+) im Bereich Stile nicht angezeigt, wenn ein Stylesheet wie „layout.css“ geöffnet wird. (GUIDES-49448)

## Asset-Management

- Wenn Sie eine geänderte Datei mit der Option **Vorhandene Datei überschreiben** hochladen, wird der Upload anscheinend abgeschlossen, wenn die vorhandene Datei keine Guides-UUID hat und in einem Ordner gespeichert ist, der unter **Ignorierte Pfade für die Nachbearbeitung** aufgeführt ist. Die vorhandene Datei wird jedoch nicht überschrieben, und es wird keine neue Version erstellt. (GUIDES-55866)
- Wenn ein `booktitle` mehrere Unterelemente wie `booklibrary` und `mainbooktitle` enthält, wird in einer Bookmap zwischen ihren Werten in den `dc:title` Metadaten ein zusätzliches Leerzeichen hinzugefügt. (GUIDES-28877)

## Publishing

- Nachdem die Ausgabe für eine Zuordnung generiert wurde, ist in der Map **Konsole die Schaltfläche** Generieren“ deaktiviert, wenn eine andere Zuordnung geöffnet wird. Durch Aktualisieren des Browsers wird die Schaltfläche erneut aktiviert. (GUIDES-54591)
- Das Veröffentlichen bestimmter Zuordnungen auf einer AEM-Site mit Komponentenzuordnung schlägt mit einem Fehler fehl, während das Inhaltsverzeichnis erstellt wird. (GUIDES-53807)
- Das Veröffentlichen einer Zuordnung auf einer AEM-Site mit Komponentenzuordnung schlägt fehl, wenn die Zuordnung ein `topicref` mit einem `navtitle` und ohne `href` enthält. Nachfolgende Versuche schlagen auch fehl, selbst nachdem das Element entfernt wurde, bis die generierten Site-Knoten gelöscht werden. (GUIDES-53707)
- In der AEM-Site-Ausgabe mit Komponentenzuordnung werden Markdown-Überschriften der Ebenen 2 bis 6 als Überschriften der Ebene 1 gerendert. (GUIDES-51134)
- Für die AEM-Site-Ausgabe mit Komponentenzuordnung werden die Prolog-Metadaten, wie Autor, Schlüsselwörter und Ressourcen-ID, im Seitentext der veröffentlichten Ausgabe angezeigt. (GUIDES-44087)
- Wenn ein Thema in ServiceNow veröffentlicht wird, enthält der Artikelinhalt die kurze Beschreibung und das Prolog des Themas. (GUIDES-47868)
- Wenn ein Thema, das bereits in ServiceNow veröffentlicht wurde, erneut veröffentlicht wird, wird ein neuer Artikel im Entwurfsstatus erstellt, anstatt den vorhandenen Artikel zu überschreiben. (GUIDES-37872)
- Wenn Bedingungsvorgaben Themenverweise während der Veröffentlichung in Salesforce ausschließen, wird die Ausgabegenerierung als fehlgeschlagen gemeldet, obwohl die restlichen Themen erfolgreich veröffentlicht wurden. (GUIDES-37807)
- Das Veröffentlichen einer großen Zuordnung in Salesforce schlägt mit einem Gateway-Zeitüberschreitungsfehler fehl. (GUIDES-33722)
- Das Veröffentlichen einer Zuordnung in Salesforce schlägt mit dem Fehler „Limit überschritten“ fehl, wenn eine Anfrage mehr als 25 Vorgänge enthält. (GUIDES-33721)
- Im Zuordnungs-Dashboard (alt) nimmt **Alle hinzufügen** in einer vorhandenen Bedingungsvorgabe keine Bedingungswerte auf, die nach der Erstellung der Vorgabe hinzugefügt oder geändert wurden. (GUIDES-45940)
- Protokolle auf der Seite **Ausgabehistorie**, die Warnungen enthalten, werden mit einem grünen Symbol angezeigt, was nicht bedeutet, dass Warnungen vorhanden sind. (GUIDES-27000)
- Das Glossar ist nicht in der Ausgabe enthalten, wenn kein Begriff im Zuordnungsinhalt auf einen Glossareintrag verweist. (GUIDES-52964)
- Themen aus einer Unterzuordnung, auf die in einem Anhang verwiesen wird, werden als Kapitel anstatt als Anhang gerendert. (GUIDES-52775)
- Einige Zeichen im vereinfachten Chinesisch werden in japanischer Schrift gerendert, wenn als Ausgabesprache Chinesisch (vereinfacht) festgelegt ist. (GUIDES-48094)
- Indexeinträge verlieren den Text von untergeordneten Elementen, z. B. `keyword`, `ph` und `sup`. Infolgedessen sind einige Indexbeschriftungen unvollständig oder leer. (GUIDES-40902)
- Leerzeichen um die Inline-`option` werden nicht beibehalten, sodass der angrenzende Text zusammengefügt erscheint. (GUIDES-40900)

## Übersetzung

- Verwenden Sie auf der Seite Übersetzung bei der Suche und Sortierung nach **Titel** den lokalisierten Metadatenwert anstelle des in der Spalte angezeigten Titels. (GUIDES-45396)

## Überprüfung

- Auf der Seite **Reviewer** sind während der Erstellung oder Bearbeitung einer Prüfungsaufgabe die Schaltflächen **Auswahl löschen**, **Reviewer hinzufügen**, **Reviewer entfernen** und **Reviewer neu zuweisen** standardmäßig aktiviert, auch wenn keine Zeilen ausgewählt sind. (GUIDES-35125)
- Im AEM-Posteingang werden Benachrichtigungen zu Prüfungsaufgaben wie Aufgabenzuweisung, eingegangenen Feedback, Erwähnungen und fälligen oder überfälligen Erinnerungen ohne Projektnamen angezeigt. (GUIDES-10912)
- In der nebeneinander angezeigten Ansicht eines Themas in einer Prüfungsaufgabe werden Inhalte, die mit Durchgestrichen gekennzeichnet sind, in den beiden Ansichten mit unterschiedlicher Formatierung angezeigt. (GUIDES-56079)

## Lerninhalte

- Das Generieren einer SCORM-Ausgabe für einen großen Kurs, normalerweise 300 MB bis 600 MB, dauert mehr als 30 Minuten und schlägt ohne Fehlerdetails in den Protokollen fehl. (GUIDES-56101)
- Die Abschlusskriterien für eine SCORM-Ausgabe können in Experience Manager Guides nicht festgelegt werden. (GUIDES-55520)
- Bilder im AVIF-Format werden im Editor angezeigt, fehlen jedoch in der veröffentlichten Ausgabe. (GUIDES-55515)
- Das `href`-Attribut wird aus Anker-Tags in der veröffentlichten Ausgabe entfernt, sodass Links nicht angeklickt werden können. (GUIDES-55514)

## Plattform

- Wenn ein(e) Benutzende(r) als Admin-Benutzende(r) in einem Ordnerprofil zugewiesen ist, aber nicht zur Administratorgruppe gehört, kann er/sie keine anderen Admin-Benutzenden erfolgreich hinzufügen. Obwohl eine Erfolgsmeldung angezeigt wird, verschwinden die neu hinzugefügten Benutzer nach dem Aktualisieren der Seite. (GUIDES-50144)

## Bekannte Probleme

Adobe hat die folgenden bekannten Probleme in Version 2026.11.0 identifiziert:

## Authoring

- Wenn Sie eine Zuordnung aus einer Vorlage mit abhängigen Themen oder Unterzuordnungen erstellen, kann die Zuordnungserstellung gelegentlich mit einem Fehler fehlschlagen, insbesondere wenn der Server stark ausgelastet ist. (GUIDES-58715)

### Editor 2.0

- Die Option **Navigationstitelattribut aktualisieren** fügt das `@navtitle` nicht zu vorhandenen `topicref` in einer DITA-Zuordnung hinzu. (GUIDES-54348)

**Änderungen verfolgen**

Wenn **Änderungen verfolgen** aktiviert ist:

- Verschachtelte Löschungen durch denselben Benutzer werden nicht immer in einem einzigen Eintrag zusammengeführt, wenn das Element, das den gelöschten Inhalt enthält, umbenannt oder formatiert wird. (GUIDES-58429)
- Das Bedienfeld **Änderungen nachverfolgen** zeigt manchmal unvollständige Inhalte für das übergeordnete Element an, wenn ein verschachtelter Löschvorgang von einem anderen Benutzer durchgeführt wird. (GUIDES-58428)
- Die rote Abflussmarkierung wird nicht auf der linken Seite angezeigt, wenn Sie Inhalte löschen, die in einer von einem anderen Benutzer vorgenommenen Einfügung enthalten sind. (GUIDES-58418)

### Publishing

- In der nativen PDF-Ausgabe werden die Formatierung hochgestellt und tiefgestellt in den Indexeinträgen nicht beibehalten. (GUIDES-58349)
- Wenn Sie dieselbe globale Vorgabe für die Generierung von Ausgaben für verschiedene Zuordnungen verwenden, kann sich die Themenauswahl aus der vorherigen Zuordnung auf die Ausgabe der neuen Zuordnung auswirken. (GUIDES-58346)
- Wenn eine Buchzuordnung ein Kapitel mit einer gültigen `href` und eine verschachtelte Themenreferenz enthält, führt das Veröffentlichen der Zuordnung in AEM Sites zu einer leeren Seite. (GUIDES-58266)
- Wenn Sie von einer Vorgabe mit nicht gespeicherten Änderungen zur Registerkarte **Ausgabehistorie** navigieren, bleiben **Schaltflächen Speichern** und **Ausgabe generieren** sichtbar. (GUIDES-57989)
- Wenn ein Post-Publishing-Workflow für eine Voreinstellung konfiguriert ist, enthält die unter &quot;**&quot; angezeigte** nicht die für den Workflow benötigte Zeit. (GUIDES-57856)
- Sie können die native PDF-Ausgabegenerierung nicht über die Seite **Ausgabehistorie“**. (GUIDES-57821)

### Überprüfung

- Das Öffnen einer in der Version 2026.08.0 oder 2026.09.0 erstellten Prüfungsaufgabe kann zu Anwendungsfehlern führen. (GUIDES-56583) <br>**Problemumgehung:** Schließen Sie alle in diesen Versionen erstellten Prüfungsaufgaben ab, bevor Sie auf Version 2026.11.0 aktualisieren.

